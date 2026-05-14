---
title: "Your AI agent is rediscovering 85% of its context every run. Here's the architecture fix (+ Contract Spec, Failure Triage, and Stack ADR)"
author: "Nate Jones"
published: 2026-05-13
url: https://natesnewsletter.substack.com/p/rag-agents-knowledge-layer-architecture
subtitle: "Watch now | There’s a debate going on right now about whether vector search is obsolete."
audience: everyone
scraped_at: 2026-05-14 14:32:08
---

There’s a debate going on right now about whether vector search is obsolete. That’s the wrong layer to be arguing about. The agents I’m watching fail in production aren’t failing because the retrieval method is wrong — they’re failing because the retrieval system can’t assemble what the agent actually needs before it starts acting.

A vector database can find text semantically related to a question. Useful, but nowhere near enough. Agents need the current account record, the user’s permissions, the controlling policy, the right section of a long document, the table behind a metric, the prior decision from a meeting, and the source trail that lets a human reviewer reconstruct why the agent did what it did. When the system doesn’t prepare that context, the model improvises — and the cost shows up everywhere except the place you’re looking. Wrong refunds get issued. Stale policies get cited. Outdated metrics make it into board decks. The agent burns tokens and wall-clock time rebuilding context every run, and when the answer finally lands, it lands confidently — which is the most expensive way to be wrong. That’s the new RAG problem — not a retrieval problem, an assembly problem.

So the next move isn’t “vectors versus something else.” It’s that vector search is quietly getting demoted from the whole architecture to one component inside a broader knowledge layer for agents — a layer that includes retrieval, but also document structure, semantic data models, access control, provenance, memory, and write-back. I want to be careful not to overstate this: vector search isn’t going anywhere. But the conversation about where the real work happens has moved.

**Here’s what’s inside:**

- **Why classic RAG worked — and where it stops working.** How to spot the moment your retrieval architecture became the bottleneck instead of the solution.
- **What Pinecone, PageIndex, SAP, and Dremio are all saying.** Four different companies, one shared shift in what “retrieval” actually means for agents.
- **The practical architecture.** Seven questions to test whether your knowledge layer can support a production agent.
- **What could go wrong.** Where this new architecture quietly breaks, and how to tell if you’re overbuilding.
- **How to put this to work.** A Retrieval Contract Spec, a Failure Triage, and a Stack ADR: paste-ready artifacts for the three states a builder hits when working on retrieval.

Let’s walk through how this shift is playing out across the stack, and what it means for how you build.


## LINK: Grab the [prompts](https://promptkit.natebjones.com/20260508_639_promptkit_2)

Most teams discover their retrieval architecture is wrong after the agent is already in production — when the support bot cites an outdated policy, the finance agent pulls a stale metric, or the code reviewer misses the convention that would have prevented the bug. The prompts below help you get ahead of those failures with three engineering artifacts you can paste straight into your team’s docs: a **Retrieval Contract Spec** for designing what your agent needs to receive before it acts, a **Retrieval Failure Triage** for diagnosing what’s actually breaking when something goes wrong in production, and a **Retrieval Stack ADR** for documenting an architectural change with honest tradeoffs and a rollback plan you can defend in a design review.


## Why traditional RAG breaks for agents

Classic RAG worked because the early use case was mostly question answering.

A customer asks “How do I reset my password?” and a support bot retrieves a few help-center chunks. An employee asks about the travel policy and gets back the relevant section of a policy document. Someone uploads a PDF and asks about it. The assistant pulls passages from the file. For these cases, vector search was a strong default. It handled messy wording well, the user didn’t need to know the exact phrasing in the source, and the model could produce a grounded answer from a small number of relevant passages.

The unit of retrieval was usually a chunk of text. That worked when the task was simple and the answer lived in one or two paragraphs.

Chunk-based retrieval has a hidden assumption: that the information the model needs can be safely separated from the structure around it. That assumption breaks in plenty of real business settings.

A paragraph in a contract may depend on a definition twenty pages earlier. A metric in a board deck may depend on a table in a warehouse. A policy exception may matter more than the policy summary. A section in a 10-K only makes sense in relation to the larger filing. A support answer may depend on the customer’s plan, geography, product version, and entitlement. A code change may depend on tests, prior review comments, architectural conventions, and issue history.

In those cases, the relevant retrieval object isn’t “a chunk.” It’s a structured bundle of context.

Classic RAG often leaves the model to assemble that bundle itself. It retrieves fragments and asks the model to infer the structure. Sometimes that works. Often it works just well enough to be dangerous: the agent has the right passage in the prompt but misses that it’s outdated, cites a paragraph without seeing the exception, answers from a summary when the underlying table is the source of truth, applies a policy it isn’t allowed to apply for this user, or redoes background reading every time because nothing in the system preserves the result of the last run.

That isn’t only a model problem. It’s a retrieval architecture problem.


## What Pinecone Nexus is actually saying

Pinecone’s Nexus launch matters because it names this shift directly. Pinecone isn’t claiming vector search is dead — its business is still built on vector infrastructure. The more interesting claim is that agents need a different retrieval contract than chatbots do.

In its [Nexus announcement](https://www.pinecone.io/blog/knowledge-infrastructure-for-agents/), Pinecone argues that agents waste too much effort rediscovering information. Pinecone’s CEO and CTO write that roughly 85% of agent effort goes to knowledge retrieval. I wouldn’t treat that figure as an independent industry fact. It’s Pinecone’s framing and should be attributed as such. But the failure mode is real.

If an agent needs to prepare a customer escalation, it shouldn’t have to search the help center, the CRM, prior tickets, policy documents, Slack discussions, and product release notes from scratch every time. A useful system should already know how to assemble customer context, entitlement, relevant policy, prior history, and approved answer constraints into a usable object.

If an agent is doing financial analysis, it shouldn’t answer from whatever paragraph happens to be nearest to the query vector. It needs to know whether the source of truth is a filing, a governed table, a metric definition, a prior forecast, or a current dashboard.

If an agent is reviewing code, it shouldn’t only retrieve files that look semantically related. It needs the issue, the diff, the tests, the ownership, the repo conventions, and the mistakes this codebase has made before.

This is the shift Pinecone is trying to capture with KnowQL and Nexus: moving from a retrieval call that returns chunks to a knowledge interface that returns task-shaped context. In Pinecone’s framing of KnowQL, retrieval goes beyond “top-k similar text.” It includes intent, filters, access policy, provenance, desired response shape, confidence, and budget.

Those details matter because they’re exactly the things production agents need.

A support agent doesn’t only need related documentation. It needs documentation this user is allowed to receive and that applies to this product version. A compliance agent doesn’t only need a policy summary. It needs the current policy, the controlling source, the jurisdiction, and the audit trail. A research agent has to distinguish which claims are vendor claims, which are independent evidence, and which facts have changed recently. Relevant sources are not enough without that classification.

That’s a different interface. A vector database can power part of it, but it doesn’t define all of it. The retrieval layer has to take responsibility for preparing context. Locating text is the starting point, not the destination.

The takeaway from Pinecone isn’t the specific benchmark claim. It’s the category direction: agents create repeated, expensive context-preparation work, and infrastructure vendors are trying to move that work out of the model loop.


## How document structure improves RAG retrieval

PageIndex makes a concrete point: many documents shouldn’t be retrieved as arbitrary chunks.

In its [research introduction](https://pageindex.ai/blog/pageindex-intro), PageIndex argues that document structure is often the missing retrieval primitive. That’s right. A long document isn’t just a sequence of semantically searchable paragraphs. It has hierarchy, sections, subsections, tables, references, footnotes, and relationships between parts. That structure carries meaning.

Take a financial filing. The risk factors are not the management discussion. The notes to financial statements are not the narrative summary. A table is not interchangeable with the paragraph before it. Retrieve a few semantically similar chunks and you may miss the part of the filing that controls the answer.

Contracts are an even cleaner example. A clause may look relevant, but the definitions section can change its meaning. A schedule may override a general term. An exception may sit far from the paragraph that triggers the search. Chunk retrieval can find text that looks relevant while losing the legal structure that makes it relevant.

PageIndex’s approach is to preserve document hierarchy. Instead of flattening a document into chunks and asking the model to make sense of the pile, the system represents the document as a navigable tree with table of contents, section summaries, node IDs, metadata, and source pointers. The model can move through the structure, and retrieval can return coherent document units rather than isolated fragments.

This is more than a better document search technique. It’s an instance of a larger rule: the retrieval unit should match the work.

For some questions, the right unit is a paragraph. For others, it’s a section, a table, a definition plus every clause that depends on it, a customer record, a graph neighborhood, a code symbol, a prior decision, or a project brief. Pick the wrong unit and the model has to compensate — reconstructing hierarchy, inferring missing references, deciding whether the retrieved text is even enough. That’s where errors come from, and it’s where context windows go to die.

The same logic explains why “just improve embeddings” doesn’t solve the whole problem. Better embeddings can find more relevant text. They can’t decide what kind of object the agent actually needs.


## SAP Dremio and governed data for agents

SAP’s plan to acquire [Dremio](https://news.sap.com/2026/05/sap-to-acquire-dremio-unify-sap-and-non-sap-data-power-agentic-ai/) belongs in this article because it shows the same shift from the enterprise data side.

Most companies don’t store their important knowledge only in prose. They store it in ERP systems, CRMs, data warehouses, dashboards, spreadsheets, customer records, supplier records, payment systems, HR systems, ticketing systems, and governed tables. A large share of enterprise knowledge is structured data, not text.

Basic RAG systems often turn enterprise knowledge into documents anyway. Export a report, index the PDF, retrieve a paragraph, ask the model to answer. That can work for summaries, but it’s a weak way to run business operations. If an agent needs a revenue number, it should query the governed source of truth. For supplier risk, the supplier record and risk model are the right call. If it needs payment status, it should use the payment system. If it needs customer entitlement, it should use the customer system. The source of truth shouldn’t be a stale document that happened to get indexed.

SAP’s Dremio move is about giving agents governed access to business data across SAP and non-SAP systems. Dremio brings a lakehouse, semantic layer, query federation, access controls, and lineage. Those aren’t cosmetic features. They’re the difference between an agent that can talk about business data and an agent that can safely use it.

For enterprise agents, permissions and lineage aren’t optional. The agent has to know who can see the data, where the data came from, how the metric is defined, and whether the result is fit for the proposed action. When a procurement, finance, or sales agent answers from the wrong source, the failure isn’t only answer quality. It can move money, lose customers, break compliance, and corrupt downstream decisions.

That’s why this is part of the RAG war. The market is realizing that “retrieval” doesn’t always mean “search documents.” Sometimes it means query a semantic layer. Sometimes it means retrieve a governed business object. Sometimes it means combine a table with a policy and a prior approval. The agent needs a usable representation of the business, not text about the business.

SAP’s [Prior Labs acquisition](https://news.sap.com/2026/05/sap-to-acquire-prior-labs-establish-frontier-ai-lab-europe/) adds another piece. Prior Labs works on tabular foundation models — models built to reason over structured table data. That matters because general-purpose language models aren’t always the best tool for structured business prediction. Churn risk, supplier risk, invoice patterns, payment behavior, renewal forecasts, and operational anomalies often live in tabular data, and turning all of that into text is the wrong abstraction.

So the SAP story isn’t a detour. It’s the enterprise version of the same argument. Agents need knowledge in the shape the business actually uses. Sometimes that shape is a document, sometimes a table, sometimes a metric definition, sometimes a workflow state. A serious knowledge layer respects those shapes instead of flattening everything into chunks.


## When to use GraphRAG for agent retrieval

GraphRAG fits when the missing structure is relationships.

Vector search is good at finding passages close to a query. It’s weaker when the question depends on relationships across many documents or entities. Which suppliers are connected to which delayed shipments? Which research themes show up across a corpus? Which teams depend on which systems? Which customers share a failure pattern? Which policies conflict? Which incidents share a root cause? Those aren’t text similarity questions. They’re relationship questions.

Microsoft’s [GraphRAG work](https://www.microsoft.com/en-us/research/project/graphrag/) is one attempt at that class of problem. The system extracts entities and relationships, builds graph structures, and uses summaries of graph communities to answer questions that need a broader view of the corpus.

GraphRAG isn’t a universal replacement for vector search. Graphs are expensive to build. Entity extraction can be wrong. Relationships go stale. Community summaries can hide the detail that matters. But the reason graph approaches keep coming back is that some kinds of knowledge are naturally relational. If your agent needs to understand dependencies, ownership, influence, sequence, lineage, or clusters of related facts, a flat list of chunks won’t be enough. The model can try to infer the graph during the run, but that’s an expensive and unreliable way to do graph construction.

The broader principle holds: don’t start with the retrieval technology. Start with the shape of the knowledge the agent needs. If the knowledge is fuzzy prose, vectors may be right. For long structured documents, a document tree. For business data, a semantic layer or SQL interface. For relationships, a graph. For repeated workflows, a compiled context object or memory layer. The right architecture often uses several of these at once.


## Long context doesn’t eliminate the problem

There’s an obvious objection: if model context windows keep growing, maybe we can hand the model more material and stop worrying about retrieval.

Larger context helps in some cases. It doesn’t solve the core problem.

A bigger window gives the model more room. It doesn’t decide what belongs in the room. It doesn’t mark which source is authoritative, enforce permissions, preserve document hierarchy, confirm a table is current, tell the agent which prior decision should govern the next step, or distinguish user-confirmed memory from model-inferred memory. Long context can reduce the need for aggressive retrieval. It can’t replace context design.

Chroma’s [Context Rot](https://www.trychroma.com/research/context-rot) work is useful here because it tracks what builders see in practice: model performance degrades when the context gets too large or too cluttered. The problem isn’t only whether the answer is present somewhere. It’s whether the answer is presented in a form the model can use reliably. Dump twenty documents into a context window and the model may have access to the right fact and still answer from the wrong one. It blends sources, misses exceptions, over-weights distractors, and treats stale and current sources as equal.

The goal for production agents isn’t maximum context. It’s appropriate context.

That’s why retrieval systems matter more, not less, as agents get more capable. The agent calls more tools, touches more systems, and accumulates more intermediate output. Without a context strategy, the agent’s own work becomes noise.


## What serious builders are changing

The best builders aren’t arguing about whether to use vectors. They’re changing where context lives and how it moves through the system.

Cognition’s [Don’t Build Multi-Agents](https://cognition.ai/blog/dont-build-multi-agents) is useful because it explains the context problem behind multi-agent failures. When multiple agents work on a task, the hard part isn’t only splitting the work. It’s making sure the right context moves between them. Decisions, constraints, discoveries, and partial state have to survive the handoff. When they don’t, each agent starts with an incomplete picture and the system gets brittle.

Anthropic’s [multi-agent research system writeup](https://www.anthropic.com/engineering/multi-agent-research-system) shows the same issue from the other direction. Multi-agent systems can outperform single-agent setups on broad research tasks, but they can also burn far more tokens. That may be acceptable for high-value work, and it shows the cost of brute-force context gathering. If your system improves by having many agents search, read, summarize, and pass notes around, the architecture needs a way to control context cost and preserve useful work between runs.

LangChain’s [context engineering essay](https://www.langchain.com/blog/context-engineering-for-agents) names the practical patterns: write context somewhere, select the right context, compress what’s too large, isolate context so irrelevant material doesn’t pollute the main task. That’s the right frame. Context engineering isn’t prompt polishing. It’s the design of the information environment the agent operates in.

This is why the RAG story connects to broader agent infrastructure. In my article on [work primitives](https://natesnewsletter.substack.com/p/ai-work-primitives-access-vs-meaning), the argument was that agents need more than access to software. They need to understand the meaning of the actions they take. A browser can let an agent click a refund button. A better system tells the agent what a refund is, who is authorized to issue one, whether it’s reversible, whether it crosses a threshold, and what policy applies.

The retrieval version of that argument is direct. A vector database can let an agent find a paragraph. A better system tells the agent what the paragraph is, whether it’s current, whether the user can rely on it, what source it came from, how it relates to other parts of the document, and whether it should be saved for future tasks.

Access to information isn’t the same as usable knowledge.


## How to build an agent knowledge layer

I’m using “knowledge layer” in a practical engineering sense: the set of services that sits between your systems of record and your agents. Ingestion, parsing, indexing, document structure, table access, graph relationships, permissions, citations, reusable context objects, and the memory or state that persists after an agent run. If your agent depends on information outside the model, that layer already exists in some form. The question is whether you designed it intentionally or whether the model is improvising it during every run.

A production agent knowledge layer should answer seven questions.

**What is the work object?** The agent shouldn’t begin with an abstract search query if the task is actually about a customer, contract, filing, supplier, metric, code change, incident, ticket, or decision. Naming the object changes the retrieval problem. A customer-support task assembles customer context. A legal task assembles document and clause context. A finance task assembles metric and source-of-truth context. A code task assembles issue, repo, diff, test, and convention context.

**What’s the right retrieval unit?** Pick the wrong one and the model wastes effort. A chunk may suffice for a simple FAQ. A section is needed for a filing. A table for financial analysis. A record for customer work. A graph neighborhood for dependency reasoning. A compiled brief for a repeated workflow.

**Which source is authoritative?** This is where many systems fail. They retrieve something relevant but not controlling. A sales deck mentions a metric, but the warehouse defines it. A Slack thread discusses a policy, but the policy document controls it. A meeting note mentions a decision, but the project tracker shows what was actually assigned. A support article is outdated. The knowledge layer has to help the agent distinguish relevant sources from authoritative ones.

**What permissions apply?** Agents can’t be allowed to treat retrieval as a free-for-all. The user’s role, customer relationship, geography, data sensitivity, and action type all matter. Retrieval has to be permission-aware before the model sees the content, not cleaned up afterward.

**What provenance has to be preserved?** For low-stakes tasks, a summary is fine. For business decisions, legal work, finance, compliance, customer actions, and code changes, the system needs source trails. The agent should be able to show where a claim came from and what evidence supports it.

**What context should be compiled ahead of time?** If an agent repeatedly works on the same project, customer, codebase, or workflow, don’t make it rediscover everything every run. Maintain a project brief, customer packet, repo memory, policy bundle, or task context object. Keep it current. Keep it sourced. Make it cheap to retrieve.

**What should the agent write back?** An agent should leave useful state behind: what it did, what it learned, what changed, what blocked it, what sources it used, what a future agent or human should know. But write-back needs discipline. Model-generated memory shouldn’t silently become instruction. Label it as observed, inferred, user-confirmed, stale, rejected, or authoritative.

That labeling is what separates a useful memory layer from a pile of accumulated model guesses.


## The builder takeaway

The action item isn’t “replace your vector database.” It’s to design the retrieval contract.

Before choosing a vendor or architecture, write down what your agent has to receive to do the job reliably. Be specific. If you’re using phrases like “relevant context,” you’re being too vague. Define the actual bundle.

For a support refund agent, the bundle might be: customer plan, region, product version, purchase history, refund policy, refund threshold, prior exceptions, current ticket, approved response language, and whether the agent can issue the refund or only draft a recommendation.

For a contract review agent: clause, definitions, related exceptions, schedule references, governing law, negotiation history, prior fallback language, and source citations.

For a finance agent: metric definition, current value, source table, lineage, reporting period, variance explanation, owner, and whether the number is approved for external use.

For a code review agent: issue, diff, touched files, tests, failing logs, ownership, repo conventions, recent related bugs, and prior review lessons.

Once you’ve defined the bundle, the technology decisions get clearer. You may still use vector search. You may also need exact search, metadata filters, SQL, graph retrieval, document trees, semantic layers, or memory. Those choices follow the knowledge contract — they don’t precede it.

A vector database should sit behind the retrieval interface. It shouldn’t define the interface. That’s the practical change.


## What could go wrong

There are real risks in this shift.

Compiled context goes stale. A project brief that isn’t updated is worse than no project brief, because it gives the agent confidence in old information.

Graphs encode bad relationships. Get extraction wrong and the agent reasons from a false structure.

Document parsers miss formatting and table relationships. That’s dangerous in legal, finance, and technical workflows.

Semantic layers are incomplete or politically contested. In many companies, “source of truth” isn’t a technical fact — it’s an organizational fight.

Memory accumulates bad conclusions. If an agent stores its own inference as confirmed fact, future runs get worse in a personal way, specific to how you’ve been using the agent.

Knowledge infrastructure can also be overbuilt. A simple help-center assistant doesn’t need GraphRAG, PageIndex, a warehouse semantic layer, and a memory system. Complexity has a cost: every new layer needs ownership, monitoring, evaluation, freshness checks, and failure modes.

So the right conclusion isn’t that every team needs the most elaborate version of this architecture. It’s that agent systems should make context preparation an explicit design problem.

If your system handles simple documents and low-risk answers, classic RAG may be enough. If it does repeated, high-context, permissioned work, it probably isn’t.

You can tell from the logs. How many retrieval calls happen before useful work starts? How often does the agent open the same sources? How much of the token budget is raw context? How often does the agent ask the user for information the system already has? How often does it cite a weak source when a stronger one exists? How often does the next run rediscover what the prior run learned?

Those aren’t abstract architecture questions. They’re operating metrics.


## The new RAG market

This is why Pinecone, PageIndex, SAP, Prior Labs, GraphRAG, context engineering, and agent memory all belong in the same conversation. They aren’t all solving the same narrow problem. They’re responding to the same pressure from different parts of the stack.

Pinecone is moving from vector retrieval toward agent-ready knowledge objects. PageIndex is preserving document structure so agents don’t have to rebuild it from chunks. SAP and Dremio are building governed access to enterprise data so agents can use business facts, not just reports about business facts. Prior Labs points toward models that understand tables as tables. GraphRAG makes relationships retrievable. Context engineering gives builders a language for controlling what enters, stays in, and leaves the agent’s working environment.

The common thread is that production agents need prepared context. Prepared context means the system has done enough work before generation that the agent isn’t starting from raw search results. It means the agent receives information in a form close to the task it’s performing — text, tables, records, citations, permissions, summaries, prior state, and structured fields.

That’s the new RAG war. It isn’t a fight over whether vector search survives. It’s a fight over who owns the layer that turns company knowledge into usable agent context.

The teams that win won’t be the ones with the most fashionable retrieval primitive. They’ll be the ones that reduce wasted agent work, preserve source authority, handle permissions correctly, and make context reusable across runs.

For builders, the instruction is clear. Keep vectors where they help. Add structure where chunks fail. Use governed data where documents are the wrong source of truth. Use graphs where relationships matter. Compile context for repeated workflows. Preserve provenance for decisions. Write back carefully when the agent learns something useful.

Don’t ask your model to rebuild the business every time it runs. Build the layer that gives it the part of the business it actually needs.

[![](https://substackcdn.com/image/fetch/$s_!ha-w!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F222fe587-cc73-46c0-a86c-2ee94bd7f9e2_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!ha-w!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F222fe587-cc73-46c0-a86c-2ee94bd7f9e2_1024x1024.png)
