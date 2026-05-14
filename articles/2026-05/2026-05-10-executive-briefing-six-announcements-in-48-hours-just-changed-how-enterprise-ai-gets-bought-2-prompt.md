---
title: "Executive Briefing: Six announcements in 48 hours just changed how enterprise AI gets bought (+ 2 prompts for the new process)"
author: "Nate Jones"
published: 2026-05-10
url: https://natesnewsletter.substack.com/p/enterprise-ai-buying-build-room
subtitle: "Watch now | Capital just moved. The question is whether the platform you’re buying can be built on."
audience: everyone
scraped_at: 2026-05-14 14:32:17
---

In 48 hours last week, six things happened in enterprise AI.

Anthropic announced a new enterprise AI services company with Blackstone, Hellman & Friedman, and Goldman Sachs; press reports put the venture at roughly $1.5 billion. Bloomberg reported that OpenAI had raised more than $4 billion for a similar enterprise deployment venture backed by firms including TPG, Brookfield, Advent, and Bain. SAP said it would acquire Dremio and Prior Labs. Pinecone launched Nexus, a “compilation-stage knowledge engine” with the claim that 85 percent of agent compute is wasted on rediscovery. ServiceNow shipped Action Fabric at Knowledge 2026, opening its workflow engine to any external agent through MCP, with Anthropic as launch partner.

These were reported as separate stories. They are the same bet, and the bet is roughly $5.5 billion that capital is moving from buying the model to buying the build. What is being repriced is not intelligence. Intelligence is cheap and getting cheaper. What is being repriced is the surrounding infrastructure that lets an agent reach real data, act through real permissions, run real workflows, and stay inside audit boundaries at a cost the company can plan around. The frontier labs call it forward-deployed engineering. The platform vendors call it governed action. Whatever the label, it is what enterprise AI value depends on, and the people writing the checks have noticed it is more decisive than the model line item ever was.

If that sounds abstract, the concrete version already happened. In February, an autonomous agent built by CodeWall reached full read-write access on McKinsey’s internal AI platform, Lilli, in under two hours, through one of 22 unauthenticated API endpoints, on a system used by roughly 70 percent of the firm’s 43,000 consultants. The exploit was SQL injection, a vulnerability class from 1998. The story everyone told was about security. The story underneath was about procurement: a platform shipped without the technical voices in the room who would have caught what was on the wire. That is the build room. That is what the $5.5 billion bet is trying to fix.

**This briefing covers:**

- **Why most enterprise AI plans are running on the old buying sequence.** Strategy upstream, implementation downstream — agents reverse that order, and the budget allocation is still pointed at the wrong layer.
- **What the $5.5 billion concession means.** The labs putting capital behind forward-deployed engineering is not a marketing posture. It is the bottleneck they are admitting they cannot solve from the model side.
- **Why context, not tokens, is the line item ruining agent economics.** And why capping usage kills the use case without fixing the cause.
- **The new buying sequence, and where the next quarter’s capital should flow.** Three changes that do most of the work — and the test that exposes whether a vendor’s roadmap can survive the build room.

The next year of enterprise AI will not be won by the most ambitious roadmap. It will be won in the room where the roadmap meets the build.


## LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)

A read-only MCP server that gives your AI direct access to my entire published content library. You connect once, and then the archive just shows up inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Think of it as a research assistant that’s already read every word we’ve put out — and it’s sitting inside the tool you’re already using. You can even paste in something you’re working on and ask it to surface the most relevant posts. It’s six read-only tools — search posts, read full posts, browse recent content, search prompt kits, read full kits, browse all kits — available the moment you need it.

Setup takes about ninety seconds.

- Register once at **[promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)**
- Enter your access code (executive\_circle) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

The way I think about it: your subscription now works inside your AI. Have fun!


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260508_eub_promptkit_1)

The Lilli incident did not fail because McKinsey lacked security expertise. It failed because the people who would have caught what was on the wire were not in the room when the purchasing decision shaped the platform’s architecture. That is the failure mode this kit is built to prevent. Two prompts, two moments. The **Agent Access Map** is the artifact a CFO should require before any major AI platform commitment — it forces a technical lead to test one real workflow against the proposed platform and return a one-page buildability verdict with a cost estimate. GREEN means buildable now. YELLOW means buildable with defined gaps. RED means stop. The **Platform Repair Playbook** is for the deal you already signed. It runs the six diagnostic questions from the end of this briefing against your specific situation and produces a remediation memo: what is fixable through configuration, what requires vendor negotiation, what needs architectural workarounds, and what is a hard constraint you need to plan around. Both produce one-page artifacts designed to carry information from the build room into the executive room in a form that survives the trip.


## The buying process built for the old technology

Enterprise software was bought one way for thirty years. A senior team evaluated the roadmap, negotiated the contract, sized the security posture, and decided whether the platform was strategic for five to ten years. Implementation came after the strategic commitment. You bought the system, funded the rollout, staffed a transformation program, and pushed the organization onto the platform. Whether the platform was usable was a project management problem. The strategic decision was upstream.

Agents break that sequence. Whether an agent can reach the right data, act through the right permissions, trigger the right workflows, stay inside audit boundaries, and do it at a sane cost is no longer downstream of strategy. It is the strategy. If those things do not work, the capital allocation does not work, no matter how good the vendor presentation was.

This is why a roadmap can sound right in the executive meeting and fail when the technical team tries to build on it. The CEO hears that the system is controlled. The CFO hears that the data will stay governed. The CIO hears that autonomous agents will not be allowed to roam freely across mission-critical systems. That all sounds correct, and in many cases it is. No serious company should want unmanaged agents improvising across ERP, finance, procurement, HR, security, or customer data.

But six months later the same CEO asks why the AI program is moving so slowly, and the answer from the builders is different from the answer in the vendor meeting. The agent cannot access the system it needs, because the approved APIs do not cover the actual workflow. The data exists, but the agent cannot retrieve it with enough context to make a decision, and the workflow lives in the user interface in a form no agent can call. The permission model works for humans clicking through screens — software agents acting across systems hit a wall. The pilot worked because it was manually staged. Production fails because the integration path is too narrow, too expensive, or too slow.

The real tension in enterprise AI right now is not whether vendors are safe enough. It is whether the safe path is usable enough. Both questions matter. Most companies are still overweighting the first and underweighting the second.


## What the labs already learned

The cleanest signal of the week is that the two leading model labs helped form or prepare new enterprise ventures backed by roughly $5.5 billion in reported capital. They did not have to.

Anthropic and OpenAI both already had enterprise sales. They both already had Fortune 500 customers. What they did not have was a way to reliably make their models useful inside the customer’s actual operations, and they have decided that this is now their problem to solve. Anthropic’s services company is structured around forward-deployed engineering: people inside the customer, sitting next to the work, building connectors, mapping permissions, designing context, writing evals, and running the agent through real workflows. OpenAI’s reported deployment venture is the same idea with different partners and a bigger check.

When the leading labs invest this heavily in forward-deployed engineering, that is not a marketing posture. It is a concession that the model alone is not enough. The implementation layer is where the value is created, and it requires hands-on engineering inside real operations.

This should change how the rest of the budget is built. Most enterprise AI plans currently overfund the visible layer — licenses, pilots, a central AI team — and underfund the layer where the work actually happens: integration, data preparation, context design, evals, permission mapping, workflow redesign, change management, and ongoing operations. Then the program stalls and leadership concludes that AI is overhyped. The better conclusion is that the budget was pointed at the wrong layer. If Anthropic and OpenAI cannot make their own models useful inside an enterprise without sending engineers in, the assumption that internal teams can do it cheaper, faster, and without that work is the assumption to question first.


## The data layer is being repriced

SAP’s two acquisitions on the same day — Dremio and Prior Labs — are coherent in a way that is easy to miss if you read them as separate stories. They are not separate stories. They are SAP saying that it intends to own the agent-ready data layer.

Dremio is the unification piece: SAP and non-SAP data, queryable in the same place, governed under one model. Prior Labs is the modeling piece: structured business data, which is what most enterprise systems actually run on, is not the same shape as internet text, and tabular foundation models are a real category. SAP is right about the underlying problem. Enterprise AI does stall when data is fragmented, locked in formats, disconnected from business context, or impossible to govern across SAP and non-SAP systems. The companies that solve that problem capture leverage that the model layer cannot.

SAP understands enterprise data. No one disputes that. Whether it can turn that understanding into a buildable surface that technical teams want to use is what remains unproven.

That is where the [SAP API policy reaction](https://www.theregister.com/2026/04/29/new_sap_api_policy_provokes/) matters. SAP’s updated policy restricts API use for autonomous and generative AI systems outside SAP-endorsed architectures, and DSAG, the German-speaking SAP user group, has [formally pushed back](https://www.theregister.com/2026/04/30/germanspeaking_user_group_slams_uncertainty/), asking for contractual clarity, transition timelines, and protection for existing integrations. SAP’s instinct is understandable. It wants to protect system integrity, customer data, and supported integration patterns. ERP is not a place to be cavalier. But from the builder’s point of view, the concern is also understandable. If the approved path is too narrow, too slow, or too dependent on SAP’s own architecture, the company has not solved the agent problem. It has moved the bottleneck into the permission model.

This creates a real executive risk. A CEO may hear “SAP has a controllable AI strategy” and think, *good, that is what we want*. The developers then discover that the controls are not paired with enough usable access, and the program slows. The CEO experiences this as confusion: we bought the responsible enterprise strategy, why is the program stalled? The answer is that control without buildability does not produce leverage. It produces governed inaction.

Every vendor in the stack deserves this same scrutiny. SAP is the case study here, but the principle applies across the board. The right question is not whether agents can be governed. They obviously can. The right question is whether the governed path is usable enough that real workflows can be built on it without the team copying data into shadow systems to get anything done.


## The hidden cost is context, not tokens

When AI bills surprise executives, the first instinct is to look at model pricing. Model pricing is part of the story. It is rarely the most important part.

A large share of agent cost comes from context. The agent needs to know what is going on. It needs policies, prior decisions, customer history, product context, financial definitions, process rules, approvals, exceptions, current state. If that context is not prepared in a usable way, the model has to reconstruct it every turn. The agent rereads long documents because no one has compiled the relevant policy into a durable artifact. It retrieves twenty chunks because the knowledge system cannot return a direct answer with provenance. The same account history gets reprocessed every run because the CRM data is not shaped for the task. Multiple tools get called because no single system can hand the agent the business object it actually needs. And every conflict between sources becomes the model’s problem to reason through, because the company has not resolved which source is authoritative.

That is how agent bills get out of control. The company is not paying for intelligence. It is paying for the absence of infrastructure.

This is the architectural point underneath Pinecone’s 85 percent claim. Whether the exact number holds is less important than the direction it points. Agents need a knowledge layer that gives them task-specific, permission-aware, cited context. Forcing every agent to assemble its own context from raw documents at inference time is a tax on every workflow, paid every time the workflow runs. It also makes agents less reliable. An agent that builds its own context from scratch each turn is slower, more expensive, and more likely to miss something important. The reasoning path also changes from run to run, which makes the system harder to govern.

There is a practical implication for the budget. Token spend should not be tracked as one undifferentiated AI cost. Separate model usage, system access, context infrastructure, workflow integration, evaluation, observability, and human oversight. If token spend is rising because the agent is doing useful work at scale, that may be acceptable. If token spend is rising because the agent keeps rereading, re-searching, and reassembling context, that is an architecture failure, and capping usage will only kill the use case while leaving the cause intact. The better question is why the agent is spending so much to complete the task, and whether the company has a knowledge layer that an agent can actually use.

For most companies, the honest answer right now is no.


## The vendor week, read in one pass

Salesforce, ServiceNow, and Workday all moved this quarter. Read together, they are different answers to the same strategic question.

Salesforce’s [Headless 360](https://www.salesforce.com/news/stories/salesforce-headless-360-announcement/), announced at TDX 2026, is explicit repositioning around surfaces that agents and developers can use: more than 60 MCP tools, 30-plus preconfigured coding skills, agent-callable APIs, and CLI commands that work directly inside Claude Code, Cursor, Codex, and Windsurf. Salesforce also open-sourced [Agent Script](https://developer.salesforce.com/docs/ai/agentforce/guide/agent-script.html), which is the part of the announcement worth slowing down on. Agent Script recognizes that enterprise agents cannot be pure vibes — some parts of an agent workflow can use language and reasoning, other parts need deterministic rules, explicit transitions, variables, and controlled action sequences. That is much closer to how serious builders think about production AI. They do not want a magic box. They want a way to decide where the model can reason and where the system has to behave predictably.

ServiceNow’s [Action Fabric](https://newsroom.servicenow.com/press-releases/details/2026/ServiceNow-opens-its-full-system-of-action-to-every-AI-Agent-in-the-enterprise/default.aspx) is the most consequential of the three for the question of governed buildability. Most enterprise AI gets stuck at the answer layer — the agent can summarize the ticket, explain the policy, draft the response. The work begins when something has to happen. An employee needs access. A laptop needs to be provisioned. A risk review needs to be routed. A customer escalation needs to follow the right approval chain. A security incident needs to trigger a playbook. A finance exception needs to be logged, reviewed, and closed. Reading data is not enough. Writing a field is not enough. The value is in governed execution. Action Fabric exposes flows, playbooks, approvals, and catalogs to any external agent through MCP, with identity, permissions, audit trails, and consumption metering inherited automatically. Anthropic is the design partner. The fact that ServiceNow is willing to be the execution layer for agents it did not build — including Claude — is a more confident bet than most enterprise vendors are making.

Workday’s [Agent System of Record](https://blog.workday.com/en-us/managing-ai-powered-future-of-work.html), generally available since February, approaches the shift from a different angle. If agents become a real labor layer, companies will need to manage them the way they manage any other workforce. Which agents are running. Who owns them. What they cost. What systems they touch. What they produce. Which ones to retire, retrain, or scale. These sound administrative but they are capital allocation questions in a thin disguise. A company that cannot see its agents will either underuse them or let them sprawl. Workday is right that the management layer is going to matter. The honest caveat is that visibility is not leverage by itself. A system of record for agents only helps if the agents being recorded are doing useful work in the first place.

The collective signal from this week is not which vendor wins. The signal is what the strongest vendors are converging on: open enough that agents can act, governed enough that the enterprise can trust the action, observable enough that the executive team can see what was done, why, and at what cost. The vendors moving in that direction are pulling developer attention. The vendors that stop at “agents inside our platform, on our terms” are losing it.


## What changes in the buying process

The useful response to this week is not to become more pro-Salesforce, more anti-SAP, or more excited about whichever vendor had the best launch. The useful response is to change the buying process so that what gets bought has a chance of becoming useful.

Three changes are doing most of the work.

The first is to require an agent access map before any major AI platform commitment. An access map is a plain inventory at the workflow level: the systems involved, the data required, the actions required, the permission model, the audit requirements, the rate limits, the integration path, and the cost model. “We are buying enterprise AI” is too vague to test. “We want an agent to handle supplier onboarding exceptions across procurement, finance, legal, and vendor master data” is concrete. “We want an agent to prepare account renewal briefs from CRM data, support tickets, contract terms, product usage, and call transcripts” is concrete. “We want an agent to reconcile month-end close exceptions and route journal entries for review” is concrete. Concrete workflows expose the truth about whether the platform is ready. Vague workflows let the vendor stay safe.

The second is to put a builder-readiness review in front of the commercial commitment, not after it. This does not mean giving developers veto power over enterprise strategy. It means asking the people who will build on the platform to test the claims that matter, against a real workflow, with real permissions and real data. Can they authenticate cleanly? Can they call the needed tools? Can they retrieve the right context? Can they trigger the workflow? Can they observe what happened? Can they control cost? Can they handle failure gracefully? The output should be blunt: this workflow is buildable now, buildable with defined gaps, or not buildable on the current path. That is the information the executive team needs before allocating real capital, and it is information no vendor presentation can produce on its own.

The third is to fund context as a capital asset, not as a project expense. Most companies already know their data is messy. What they underestimate is how expensive messy context becomes when an agent runs the same workflow a thousand times a week. Human workers can carry a lot of context in their heads. Agents need it supplied. If the company supplies it badly, the model bill and the error rate will both show it. For workflows that matter, reusable context artifacts deserve real funding — knowledge layers, semantic models, policy representations, process maps, source-of-truth definitions, document parsing, retrieval infrastructure. The exact implementation will vary. The principle is stable: do not make every agent reconstruct the business from scratch every time it acts.

Two more practices follow from the first three. Separate governance from blockage. A governance model that forces developers to route around the official platform to build anything useful has failed, regardless of what the policy document says. And stage the capital release. Do not fund a large AI roadmap as one giant belief exercise. Fund it in gates. Prove the workflow is technically reachable. Then prove the agent can complete the task with the right context and controls. Then prove the economics work at expected volume. Then scale.


## Where the next quarter’s capital should flow

The week’s news points to a clear allocation.

Fund the implementation layer first, because the labs themselves are showing it is the bottleneck. That means engineering capacity for connector work, evals, context design, permission mapping, and workflow redesign. License seats without implementation capacity are the most common way AI programs underperform. If the internal team is not staffed for it, expect the program to stall, and budget accordingly for partners who do this work seriously.

Fund the knowledge layer next, because context cost is the silent line item that ruins agent unit economics at scale. For every workflow that matters, the question is whether durable, reusable context exists or whether the agent has to rebuild it on every run. The first is a one-time investment that compounds. The second is a tax that grows with usage.

Defer broad platform commitments until at least one named workflow has been built end-to-end on the platform with real data, real permissions, and a real cost reading. Concrete workflows expose vendor readiness in a way that demos cannot. The cost of the test is small. The cost of buying a five-year story that does not survive the build is enormous.

And reserve a real line for evaluation and operations. Agents are not traditional software. They have to be tested, scored, observed, and sometimes constrained. A company that cannot tell whether an agent is producing the right answer, following policy, escalating correctly, staying within cost bounds, and respecting permissions has an agent program in name only.


## What the strongest vendors will do

The next time an enterprise vendor presents an AI roadmap, listen for what is missing. If the deck spends most of its time on agents but very little on access, that is a warning. A deck that talks about governance but cannot explain the developer path is a louder warning. If it shows a polished assistant but cannot explain how actions flow through identity, permissions, approvals, and audit, that is a warning. If it promises lower cost but cannot show how context is reused, that is a warning. And if it requires a large services engagement before the team can even test the real workflow, that is the loudest warning of all.

The strongest vendors will be able to sit in front of executives and builders in the same room and answer both at once: why the platform is strategic, how the unit economics work, how governance and interoperability hold up, and how the technical team builds against the system without resorting to unofficial workarounds. That is the standard. The vendors moving toward it are the ones generating real developer pull. The ones that cannot are losing the layer where enterprise AI value will actually be created, even if their logo still appears on the procurement page.

A roadmap that does not survive the build room is not a strategy. It is a slide.


## What your developers should be asking

The Lilli incident worked as a public diagnostic for a problem most enterprise AI programs have not yet named. Twenty-two of two hundred endpoints shipped without authentication. That is not a single engineer’s mistake on a Friday afternoon. That is a default posture — the shape a team takes when the people who would have raised the question are not in the room. The six questions below are what your technical team should be asking your vendors before signing, asking your internal builders before launch, and asking the platform you already deployed last quarter. Each one has a failure mode that has already shown up in the wild, and a vendor answer that should make you uncomfortable if you cannot get it.

**1. Does the platform distinguish between a human user and an AI agent?**

*Failure mode:* Humans authenticate, agents do not. One compromised agent credential becomes blast radius across everything the user touches. There is no scoped permission for the agent because there is no agent identity. There is no kill switch because there is nothing to revoke.

*Vendor answer to look for:* Separate identity primitives for agents, scoped permissions that cannot exceed the underlying user’s permissions, and revocation that works in minutes from a console — not a code deploy, not a ticket queue.

**2. What is the platform’s default posture when the team is under deadline pressure?**

*Failure mode:* The architecture’s secure path requires deliberate configuration that gets skipped when timelines tighten. The default ships unauthenticated, unscoped, or unlogged. Teams under pressure ship the default.

*Vendor answer to look for:* The secure path is the easy path. Authentication is on by default. Scoping is required, not optional. Audit logging is automatic. Going faster does not mean going looser.

**3. How do permissions compound when an agent delegates to another agent?**

*Failure mode:* Agent A has scoped access. Agent A calls Agent B. Agent B inherits Agent A’s permissions, then calls Agent C, which inherits both. Three hops in, the effective permission set is larger than anyone authorized.

*Vendor answer to look for:* Explicit delegation chains with permission narrowing, not widening, at each hop. Audit trails that follow the chain. Limits on delegation depth. The platform refuses delegation that would expand scope.

**4. What do token costs actually look like at production scale, on a representative workflow?**

*Failure mode:* Pilot economics looked fine because the pilot ran ten times. Production runs the workflow ten thousand times a week, and most of the cost is the agent reassembling business context every run. The bill is an architecture problem disguised as a usage problem, and capping usage kills the workflow without fixing the cause.

*Vendor answer to look for:* A breakdown of cost per run on a real workflow, with line items for model usage, retrieval, context assembly, and tool calls. A clear story for how context is reused across runs. A path to bringing context cost down as volume rises, not up.

**5. Can the audit trail answer a regulator’s question quickly enough to matter?**

*Failure mode:* Something goes wrong. The regulator asks what the agent did, on whose behalf, with what permissions, against what data, at what time. The platform’s logs answer some of that. The compliance team spends three weeks reconstructing the rest from system logs and Slack threads.

*Vendor answer to look for:* A single audit surface that captures agent identity, the calling user, the permissions invoked, the systems touched, the actions taken, the data read or written, and the outcome — queryable in minutes, exportable in a format a regulator will accept.

**6. What is reversible when the agent makes a mistake?**

*Failure mode:* The agent updates a record, sends an email, triggers a workflow, posts to a customer-facing system. The mistake is detected an hour later. Some of the actions were reversible. Some were not. Nobody documented which.

*Vendor answer to look for:* A clear classification of agent actions by reversibility — what can be undone, what triggers a rollback, what requires human confirmation before it commits. Confirmation gates on irreversible actions. A documented list of what cannot be undone, accepted by the team that owns the system before the agent ships.

[![](https://substackcdn.com/image/fetch/$s_!ZqA3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffb922b2e-7db7-4dde-a8d6-29b7f8efcf6f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!ZqA3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffb922b2e-7db7-4dde-a8d6-29b7f8efcf6f_1024x1024.png)
