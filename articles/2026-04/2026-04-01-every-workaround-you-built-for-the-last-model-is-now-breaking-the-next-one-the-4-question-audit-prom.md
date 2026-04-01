---
title: "Every workaround you built for the last model is now breaking the next one. The 4-question audit + prompts to fix it."
author: "Nate Jones"
published: 2026-04-01
url: https://natesnewsletter.substack.com/p/anthropic-just-built-a-model-that
subtitle: "Watch now | Claude Mythos is nigh! The four-question audit that tells you which parts of your AI stack it breaks, and the design principle that keeps it from happening again."
audience: everyone
scraped_at: 2026-04-01 12:00:17
---

Claude Mythos is Anthropic’s most powerful model ever. Not an incremental improvement — a whole new tier above Opus, the first time Anthropic has introduced a new tier name to signal a capability discontinuity. The cyber dimension is what spooked markets: Anthropic’s own draft language calls it “currently far ahead of any other AI model in cyber capabilities,” and cybersecurity stocks fell 4.5 to 7% at close on March 27 after investors read those words and believed them. Mythos isn’t even going to general release first. They’re starting with early-access to cyber-defense organizations so defenders can get a head start — a frontier lab deliberately slowing commercial release tells you something about what they think they’ve built.

Every Mythos take you’ve read this week is about the model. Benchmarks, cyber scores, a new tier, the leak, the stock drops. The leak handed everyone the capability story, the draft blog posts were *about* capabilities, so capabilities are what got covered.

Nobody’s covering what happens on the other side: what a step change does to the systems you already shipped. That requires a different frame: not looking down from the model at what it can do, but looking up from your stack at what it exposes. And what it exposes is this: **every AI system in production contains an invisible layer of workarounds for the last model’s weaknesses, and most teams stopped seeing them as workarounds a long time ago.** A step change is the event that makes them visible. A better model doesn’t just make your system work better. It can make your system work worse.

**Here’s what’s inside:**

- **The simplification pattern.** Every team building production agents is converging on the same finding, and it runs counter to most engineering instincts.
- **The Bitter Lesson for builders.** A 70-year pattern in AI research that most builder communities aren’t talking about, plus the Klarna case study that shows what ignoring it costs.
- **The four-question audit.** One diagnostic question per layer of your AI stack, with concrete before-and-after examples you can run the day a new model drops.
- **Four prompts that do the work for you.** A line-by-line system prompt audit, an outcome-based rewriter, an org-level dependency map, and a step-change readiness plan.
- **Five things to do Monday.** Principles your team can act on this week, before Mythos ships.

The evidence for all of this is already here. You don’t need to wait for Mythos to see the pattern in action.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260330_4ip_promptkit_1)

Most teams will read this piece and agree with every word of it. They’ll look at their 3,000-token system prompts and think, “yeah, we should probably audit that.” Then a deadline will hit, the new model will drop, and they’ll do what everyone does: swap the model string, cross their fingers, and fix whatever breaks. The audit never happens. The compensating complexity stays invisible until it causes a production incident.

These four prompts exist because the hard part was never understanding the concept — it was doing the work. The Compensating Complexity Audit walks through your actual system prompt or pipeline description line by line and categorizes every component as outcome logic, constraint, scaffolding, or duct tape, with specific deletion tests for each. The Outcome-Based Rewriter takes what the audit finds and produces a clean four-component prompt you can test immediately. The Org-Level Dependency Map applies the same diagnostic to your team structure — which roles scale with model limitations, which survive any upgrade, and where you’re carrying Klarna risk. The Step-Change Readiness Plan turns all of it into a phased action plan sized to your actual capacity, starting with what you can do in thirty minutes today.

If you can’t paste your production system prompt into Prompt 1 and categorize every line, you don’t know where your duct tape is yet. That’s the whole point of the audit.


## The pattern: simplification beats sophistication

Cursor’s engineering team spent months scaling multi-agent coding from a single-ticket tool to hundred-agent swarms building million-line codebases. Their first architecture was flat coordination: agents sharing a file, using locks to avoid collision. It failed. Twenty agents slowed to the effective throughput of two or three, with most time spent waiting on locks. Agents held locks too long, forgot to release them, or updated the coordination file without acquiring the lock at all. They switched to optimistic concurrency control, simpler, more resilient, but hit deeper problems. With no hierarchy, agents became risk-averse. Nobody took ownership of hard problems. The system defaulted to safe, small changes instead of end-to-end implementation. Activity without progress.

The fix was hierarchy and specialization: planners create tasks, workers grind until done, a judge decides whether to continue. But the real finding came after that. They built an integrator role for quality control and conflict resolution, the kind of coordination layer that looks essential on a whiteboard. It created more bottlenecks than it solved. Workers were already capable of handling conflicts themselves. They deleted it.

Cursor’s summary: “Many of our improvements came from removing complexity rather than adding it.” And: “A surprising amount of the system’s behavior comes down to how we prompt the agents.”

This isn’t an isolated finding. It’s the pattern across every team building production agents right now.

Anthropic, after working with dozens of agent teams across industries, concluded that “the most successful implementations use simple, composable patterns rather than complex frameworks.” Their core recommendation: start simple, add complexity only when it demonstrably improves outcomes. Their context engineering guide goes further: “As model capabilities improve, agentic design will trend towards letting intelligent models act intelligently, with progressively less human curation. ‘Do the simplest thing that works’ will likely remain our best advice.”

OpenAI’s Codex prompting guide says it plainly: their latest model “shows strong performance even without AGENTS.md files or custom scaffolding.” GPT-5-Codex is “more steerable, adheres better to AGENTS.md instructions, and produces higher-quality code, just tell it what you need without writing long instructions on style or code cleanliness.” The previous approach, ad-hoc scaffolding and conversation summarization to manage long context, has been replaced by first-class compaction built into the model. The scaffolding people built to work around context limits is now a feature the model handles natively. As the model got better, the scaffolding got simpler, and that connection is the mechanism.

Every one of these findings points the same direction: **when models get better, the teams that win are the ones that strip scaffolding, not the ones that add it.**


## The Bitter Lesson for builders

There’s a pattern in AI that’s held for 70 years and nobody in the builder community talks about enough: general methods that use raw computation beat human-engineered domain hacks, by a large margin, every time. Chess, Go, vision, language, every time researchers tried to hand-code expertise into a system, a dumber system with more compute and fewer human opinions eventually crushed it. In AI research this is called the Bitter Lesson, and it has a practitioner version that matters right now: don’t confuse the “what” with the “how.” Be specific about outcomes. Give the best tools to the best AI. Let it figure out execution.

The practitioner translation: **every piece of “how” you encode into your system is a bet against the model getting smarter.** When the model improves, your encoded “how” doesn’t just become unnecessary. It becomes a constraint. The model would find a better path if your instructions weren’t in the way.

This is what makes a step change different from a normal model update. A 5% benchmark improvement doesn’t break your compensating complexity. It makes it slightly less necessary. A step change — an entirely new tier above your best model — flips the equation. Your compensating complexity is actively fighting a model that’s trying to be better than your instructions allow.

You built a cast on a broken bone. The bone healed. The cast is now limiting range of motion. But you’ve worn it so long you think it’s part of your skeleton.

Klarna learned this the expensive way. They deployed an AI agent doing the equivalent work of 700 customer service agents, paused hiring, and saw headcount shrink from roughly 5,500 to 3,400 through attrition. The AI handled two-thirds of inquiries, improved response times by 82%. On paper, it worked. In practice, customer satisfaction fell sharply. The AI gave generic answers to complex questions. Forrester’s Kate Leggett called them “almost the poster child for bad AI deployment.” The CEO who said AI “can already do all of the jobs that we, as humans, do” was, months later, asking engineers and marketing staff to answer customer inquiries, and publicly admitting the company had prioritized cost over experience.

Klarna’s mistake wasn’t using AI. It was drawing their entire org around the model’s *current* capabilities without understanding what would break when those capabilities hit their limits. They hardcoded the model’s 2024 strengths and weaknesses into their headcount and processes. When the boundary between “AI can handle this” and “AI can’t handle this” shifted, they had already lost the people on the other side of the line.

That’s compensating complexity at the org-chart level. And it’s the same problem as compensating complexity in your code: you built for a specific model’s specific failure modes, and when the model changes, everything built around those failure modes breaks.


## The four-question audit

Each layer has a diagnostic question you can take to your production systems the day the new model is available. Until then, this is preparation, mapping where the compensating complexity lives so you can move fast when the floor shifts.


### 1. Prompt scaffolding

**Is this instruction here because the model needs it, or because I needed the model to need it?**

This is the most-validated layer. Anthropic’s recommendation is unambiguous: “consider adding complexity only when it demonstrably improves outcomes.” OpenAI’s Codex guide tells users of their latest model to “just tell it what you need without writing long instructions.” Cursor found that prompt design, not coordination machinery, not tools, was the dominant factor in agent behavior.

You have a customer support agent with a 3,000-token system prompt. Half of it is procedural: “first classify the intent, then check the knowledge base, then formulate a response using only verified information, then check your response for hallucinated URLs.” That sequence was written because the model would skip the knowledge base check 20% of the time and occasionally invent support URLs.

A model that’s smart enough to know support answers should be grounded doesn’t need your explicit sequence. Worse, your sequence constrains it to a fixed order that isn’t optimal for every query. A smarter model might check the knowledge base *and* the billing system *and* the user’s history, in whatever order the specific question demands, if you let it. Your scaffolding doesn’t let it.

The audit: pull every system prompt in production. Highlight every procedural instruction, every few-shot example, every output format constraint. For each one, test the new model without it. You’re looking for instructions where removal improves or doesn’t change output quality. Delete them.


### 2. Retrieval architecture

**How much of my retrieval logic is the model’s job?**

This one is more layered than “RAG is dead.” Long-context honeymoons feel great in demos and fail in production. Freshness, permissions, cost, latency, and auditability are real constraints that live outside the model. Models still don’t use long contexts uniformly well, and performance degrades when the relevant information sits in the middle of a long input.

But there’s a real Bitter Lesson inside the RAG conversation, and it’s not about whether to retrieve. It’s about who designs the retrieval logic. Your chunking strategy, your re-ranking weights, your hybrid search calibration, that’s human-engineered domain knowledge about how to find relevant information. And it’s the kind of domain engineering that general computation absorbs.

The shift, already documented in production, is from pipeline RAG to agentic RAG. Researchers have found agentic retrieval approaches delivering substantially better retrieval quality, not because someone built a better pipeline, but because they handed retrieval control to the model and it made better decisions about what to look for and when to stop looking. Anthropic’s Claude Code already works this way: lightweight references up front, then tools like glob and grep to navigate and retrieve just-in-time, bypassing the problems of stale indexing and rigid retrieval hierarchies.

The audit: map every stage of your retrieval pipeline. Identify the stages that exist because the model couldn’t assess relevance, rewrite queries, or judge sufficiency on its own. Test whether the new model with tool access to your search index can manage those stages better than your hand-tuned logic. Keep the stages that enforce business rules. Question everything that encodes retrieval intelligence the model might now have natively.


### 3. Hardcoded domain knowledge

**Which of these rules did I write because the model couldn’t infer this from context?**

Open the system prompts in your production systems and count the rules. Decision trees, lookup tables, explicit if-then logic. Each was added because the model kept getting something wrong. Each one is a bet that the model will keep getting it wrong.

Now multiply that across a production system that’s been live for a year. You don’t have one rule. You have 40 or 80 or 200. Together, they form a decision tree that encodes how the *old model* should have thought about your domain, not how a *better model* would think about it from first principles with good context.

The audit: for each hardcoded rule, test the new model without it. Give it access to the source context the rule was derived from, the return policy document, the compliance handbook, the product spec, and see if it reaches the same conclusion from first principles. Rules where it does? Delete them. Rules where it doesn’t? Keep them, some domain knowledge is genuinely non-obvious. But be honest about which category each rule falls into.


### 4. Verification placement

**What’s the interception rate at each verification stage, and how does it change on the new model?**

I’m not arguing you remove verification. Verification is trust. The audit is about *where* you verify, not *whether*.

Most production systems verify at multiple pipeline stages. This makes sense when models have high per-step error rates. But verification has a cost: latency, compute, sometimes human attention. When you add a second LLM call to check the first call’s output for hallucinations, you’ve doubled your inference cost on every single request.

If the model’s hallucination rate was 15%, that cost was worth it. If the new model’s rate is 3%, you’re spending 97% of your verification budget confirming things that were already correct. And if you verify at three pipeline stages, and the error rate drops by 70% at each stage, your three checkpoints are collectively catching a fraction of what they used to catch while adding the same latency they always did.

The audit: run your existing pipeline on the new model. Measure where verification catches real errors versus where it confirms correct output. Shift your budget toward the stages where the model still fails. You might find that one verification step at the end catches everything three intermediate steps used to catch, at a third of the cost.


## What “simple” actually looks like

“Simplify your AI systems” is advice. It’s not an architecture. Here’s what the architecture actually looks like when teams get it right, based on what’s working in production.

A well-built system has four components and nothing else:

**An outcome specification.** This is what you want the system to achieve, expressed as a goal with success criteria, not a procedure. “Resolve this customer’s issue using our knowledge base, policies, and account history. The customer should leave satisfied and the resolution should comply with our return policy.” That’s an outcome spec. Compare it to what most production systems have: “First classify the intent into one of 14 categories. Then route to the appropriate handler. Then retrieve the top 5 knowledge base articles using hybrid search with alpha=0.7. Then generate a response using only the retrieved context. Then check for hallucinated URLs. Then...” That’s a procedure. The procedure was necessary when the model couldn’t figure out the steps on its own. Every step you encoded is a step the model is now locked into, even if a better model would take a different, and better, path.

**Constraints and guardrails.** These are the things that must be true regardless of how the model achieves the goal. “Never disclose customer financial data.” “Always verify refund eligibility against the 30-day policy before processing.” “Escalate to a human if the customer requests it.” These survive every model upgrade because they aren’t about model capability. They’re the “what stays” layer, and separating them cleanly from the procedural layer is the whole game.

**Tools the model can use.** Search your knowledge base. Look up an account. Check order status. Process a refund. Run a query. The model decides which tools to call, in what order, based on the situation. You define what the tools *do*. The model decides *when and how* to use them. This is the critical difference between a simple system and a complex one: in a complex system, you designed the orchestration, you decided which tools get called in which order for which query type. In a simple system, the model is the orchestrator. You gave it capabilities. It figures out the workflow.

**A coordination pattern, if you need multi-agent.** This is where Cursor’s finding matters most. Their Planner-Worker-Judge harness works because it defines *organizational structure* without encoding *domain knowledge*. Planners decompose work. Workers execute independently. A judge evaluates and decides whether to iterate. That’s the whole thing. No domain-specific logic in the coordination layer. No rules about how to approach a specific type of problem. The domain intelligence comes from the model. The coordination pattern comes from the harness. When the model gets smarter, the coordination pattern doesn’t change, it just coordinates a smarter model doing smarter work.

This is why it generalized from code to spectral graph theory without modification. And why Anthropic, Google DeepMind, and OpenAI independently converged on structurally similar coordination patterns, with Cursor’s planner-worker-judge architecture following the same structural logic. Decompose, parallelize, verify, iterate. The convergence isn’t accidental. It’s the natural structure that emerges when you stop encoding domain hacks and start encoding coordination.

**That’s what simple means.** Outcome spec + constraints + tools + coordination pattern. Everything else, the classification routers, the retrieval pipeline stages, the chain-of-thought preambles, the few-shot examples, the decision trees, the verification waterfalls, is either application logic that belongs in a constraint, or compensating complexity that was waiting for a better model to make it unnecessary.

The core insight: **the less your system knows, the more it gains from a model that knows more.** Systems that encode outcomes are upgradeable. Systems that encode procedures are disposable. When Mythos drops, or whatever comes after Mythos, the team with outcome specs and tools upgrades by swapping the model. The team with 3,000 tokens of procedural scaffolding starts a rewrite.


## What this means for teams, not just systems

Compensating complexity isn’t only technical. It’s organizational.

Atlassian’s CTO Rajeev Rajan told the Pragmatic Summit in February 2026 that some of his teams are now writing zero lines of code: “it’s all agents, or orchestration of agents.” Those teams produce 2-5x more output. Rajan’s framing: “Efficiency framing is missing the point. It’s more about what you can create now with AI which you could not before.”

A head of engineering at a 200-year-old agriculture company told The Pragmatic Engineer at the same summit: “We are already seeing the end of two-pizza teams thanks to AI. Our teams are slowly but surely becoming one-pizza teams across the business.” Around 20 engineering leaders confirmed the trend.

The question for your team is the same as the question for your code: **which parts of your org are application logic (genuinely needed regardless of model capability) and which parts are compensating for the model’s limitations?** The human review step that catches the 3% of cases where the model is wrong — that’s application logic. The five-person team maintaining prompt templates that a better model won’t need, that’s compensating complexity in your headcount.

The model improvement is free. The organizational adaptation is the work.


## What to do Monday

Five principles you can take to your team this week.

**1. Treat every model upgrade as a deletion opportunity.** Before you test whether the new model does your current workflow better, test whether pieces of it can be removed entirely. Run your prompts with sections deleted. Run your pipeline with stages bypassed. Measure what gets worse versus what stays the same or improves. The right first test is measuring how much of the existing system the new model makes unnecessary.

**2. Separate your “what” from your “how” in writing, today.** Tag every component in your system prompts and retrieval pipelines as either an outcome specification or a procedural instruction. When the new model drops, you test by removing “how” components and keeping “what” components. If you haven’t tagged them, you won’t know which is which under time pressure.

**3. Log your interception rates now.** For every verification step, human review stage, and fallback path in production, start measuring how often it actually changes the output. Not how often it runs, how often it *matters*. When the new model arrives, you re-measure. If the rates drop, you know which steps to thin out.

**4. Identify your org chart’s model dependency.** Look at every role and process that exists because of AI limitations. For each one, ask: “If the model’s error rate dropped by 80%, would this role or process still exist in its current form?” You’re not making staffing decisions today. You’re building the map so you can move fast when the capability jump is real and measurable.

**5. Build your next system around outcomes and tools, not procedures.** Define what you want accomplished, the constraints it must satisfy, and the tools it can use. Stop there. Don’t write the procedure. If it doesn’t work, add the minimum scaffolding necessary and tag it as compensating complexity so you know to re-test it on the next model.

These five principles compound. Every step change becomes a free upgrade instead of a migration project.


## What stays

Not everything is compensation. Permissions are a business rule. Human-in-the-loop before a financial transaction is risk management. Regulatory logic is compliance. Medical review steps are liability and ethics. These survive any model upgrade because they aren’t about model capability.

The purpose of the audit isn’t “delete everything.” It’s to know which parts of your system are bets against model improvement, so when the model improves, you re-evaluate in days instead of discovering six months later that your reliability layer is adding 400ms of latency to catch errors that no longer occur, and your team is staffed for a frontier that moved three months ago.

The teams that extract value from a step change fastest are the ones who already know where their duct tape is, in the code and in the org chart. Everyone else will be doing this audit after the fact, while their competitors are already shipping.

[![](https://substackcdn.com/image/fetch/$s_!qmK3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc79f797c-49ca-4d05-b1b1-b595c96d57da_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!qmK3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc79f797c-49ca-4d05-b1b1-b595c96d57da_1024x1024.png)
