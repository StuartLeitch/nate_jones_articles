---
title: "Building Agents That Actually Work"
author: "Nate Jones"
published: 2025-10-22
url: https://natesnewsletter.substack.com/p/everyone-misread-andrejs-podcastheres
audience: everyone
scraped_at: 2026-01-05 19:13:46
---

A podcast in Silicon Valley blew up the world in the last couple of days.

AI legend Andrej Karpathy joined [the most famous podcast](https://www.youtube.com/watch?v=lXUZvyajciY) in the Valley for a no-holds-barred 2.5 hour conversation on the future of AI.

I think most people skipped the episode, but nobody missed the screaming headlines after. The news was filled with breathless claims that the AI bubble had been popped, that Andrej thought AI agents were ‘slop’ and that the AI hype cycle was over.

That’s a lot of power for one podcast!

So why the firestorm? I dug into both the podcast, the reaction, and Andrej’s [clarification after](https://x.com/karpathy/status/1979644538185752935). I think the headlines are wrong, but I think that’s beside the point.

The real story is how well-aligned Andrej’s story is to the world I’ve been living and wrestling with every day on this blog: *how do we build interesting production AI agents that do real and useful work? What does that actually look like?*

Since the podcast, I’ve had people reach out to me, asking if they should stop building agents. Asking if things are overhyped and they should pull back.

And that’s frustrating, because if listen to Andrej, that’s not the message he sends.

And if you read this blog, you know I call out over and over again the real returns people and teams get from investing in useful agents today.

So I got inspired, and I decided to put together a guide to building with the agents we have today that reflects both my experience and the notes / insights Andrej had on the podcast.

I really went all in:

Three in-depth prompts on agent design:

- **Conversational Agent Design Prompt**: End-to-end architecture interview covering memory, reliability, economics, tools, testing, and governance with forced trade-off decisions.
- **Conversational Memory Blueprint**: Deep-dive on what your agent remembers and forgets across working, episodic, and semantic memory with explicit storage and update patterns.
- **Conversational Production Ops Runbook**: Prototype-to-production transformation with monitoring, SLOs, alerting, incident response, and operational discipline.

Plus the principles that align with Andrej’s insights:

- Why memory architecture beats models
- How architecture creates agent reliability
- Test outcomes, not agent steps
- Model economics before writing code
- Start with boring, expensive problems
- Follow cost, ignore the hype
- Use patterns that actually work
- Avoid these predictable failure modes
- Run production with operational discipline
- Build patterns that compound value

I went deep on this one, because I want you to have both a realistic take on the podcast and also a really hands-on perspective on agent-building from someone who’s in it today.

So watch the video for my take on Andrej, dig into the principles below for how to build, and jump into those prompts to start building for yourself!

Good luck, and don’t panic :)


## [Grab the prompts on conversational agent design](https://www.notion.so/product-templates/Agent-Design-Conversational-Prompts-2945a2ccb52680f6953eeece0a3fab18?source=copy_link)

These three prompts work together as a complete design-to-production system for building agents that actually ship.

The Conversational Agent Design Prompt handles the overall architecture—walking you through memory, reliability, economics, tools, and testing in a structured interview that surfaces constraints and forces decisions.

The Conversational Memory Blueprint zooms in on the hardest architectural problem, helping you map exactly what your agent needs to remember, where that memory lives, and how it updates across working, episodic, and semantic layers.

The Conversational Production Ops Runbook takes your prototype and turns it into a monitored, cost-controlled service with real SLOs, alerting, incident response, and change management.

Each prompt uses the same question-first interview style—asking what matters, reflecting understanding back, offering 2-3 options with clear trade-offs, then ending with crisp decisions and next actions. They’re designed to move you from idea to production systematically, forcing you to answer the hard questions before they become production incidents. Use them in sequence or jump to whichever matches where you’re stuck.

---


# Building Agents That Actually Work

Andrej Karpathy’s recent podcast sparked a small controversy when he said “useful agents are a decade away.” The reaction was predictable—people heard what they wanted to hear and missed his actual point. He wasn’t saying agents are useless. He was saying that fully autonomous, reliable, self-learning agents that operate without guardrails are a decade away. And he’s right about that.

But here’s what matters more: agents that deliver tremendous value exist today. I’ve built them. I’ve seen companies save millions with them. The trick is architecting for the constraints we actually have, not the capabilities we wish for.

This isn’t about waiting for better models. It’s about understanding what works now and building systems that get better as models improve. After shipping dozens of agent systems and watching most of them succeed or fail in production, I’ve learned that success comes down to a handful of principles that most builders miss.


## Memory Is Everything

Andrej identified memory as the core architectural problem for agents, and he’s absolutely correct. Without durable memory, agents can’t approximate human learning trajectories. They can’t improve from past mistakes. They can’t build on previous successes. The memory problem underlies almost every other agent limitation.

But here’s where theory meets practice: memory isn’t a feature you bolt on after the fact. It’s an engineering discipline that informs every architectural decision from the beginning. I’ve seen too many teams treat memory as an afterthought, then wonder why their agents can’t learn or improve.

When I start designing an agent system, I force myself to answer specific questions about memory before writing any code. What memory does this agent actually need to function? The question sounds simple but demands precision. Are we talking about remembering tool outputs from three turns ago? Learning from failed attempts across sessions? Maintaining domain knowledge that evolves quarterly? Each type requires completely different infrastructure.

Memory splits into three distinct types, and understanding the difference determines whether your agent works or wastes tokens. Working memory lives in the immediate context window and handles ephemeral task state. When you’re asking an agent to analyze a document and write a summary, working memory tracks the current analysis, references specific sections, and maintains the draft summary. It exists only for the duration of that session.

Episodic memory persists across sessions and stores experiences that inform future behavior. This is where agents learn from past failures and recognize patterns that span multiple interactions. When your agent encounters a problem it’s seen before, episodic memory lets it apply lessons learned last week or last month.

Semantic memory encodes domain knowledge and reference information. Product catalogs, company policies, technical specifications—information that agents need but shouldn’t have to rediscover with every interaction. This memory type changes slowly and deliberately as domain understanding evolves.

Where each type lives determines everything about how it performs. Working memory operates within the model’s context window, typically spanning 2,000 to 200,000 tokens depending on which model you’ve selected. Access stays fast—under 100 milliseconds—because you’re reading from in-memory structures. But it vanishes when the conversation ends, which is exactly what you want.

Episodic memory moves into persistent storage, usually vector databases that enable semantic search across past experiences. Capacity becomes theoretically unlimited but practically cost-bounded. You’ll hit economic constraints before technical ones. Access latency jumps to somewhere between 10 and 500 milliseconds depending on index size and query complexity. Updates occur after significant events rather than every turn: completed tasks, recognized failure patterns, successful problem-solving strategies.

Semantic memory lives in knowledge bases and structured data stores. Access latency typically runs 50 to 200 milliseconds, faster than episodic memory because you’re querying structured data rather than unstructured experience logs. Updates happen periodically—weekly, monthly, or quarterly depending on how rapidly your domain knowledge evolves.

The temporal dimension completes the picture. Working memory resets between sessions by design. Episodic memory grows indefinitely unless you implement explicit pruning strategies based on relevance decay or storage economics. Semantic memory requires versioning and migration paths as understanding evolves. These aren’t implementation details to defer—they’re architectural constraints that shape everything built above them.

I’ve learned this the hard way: design memory systems explicitly before building agent logic. Memory architecture determines agent capabilities more than model selection does. You can upgrade from GPT-4 to o1 and see marginal improvements if your memory architecture constrains what the agent can learn and remember. Fix the memory architecture first, and even older models become significantly more capable because they can access and build upon past experience.


## Reliability Comes From Architecture, Not Prompting

Andrej’s second major insight separates production-ready systems from research prototypes: agents lack inherent reliability. You cannot prompt an LLM into reliability, no matter how carefully you craft instructions or how many examples you provide. Current sophisticated multi-agent implementations achieve robustness through architecture, not through agent capabilities themselves.

I see this confusion constantly. Builders write increasingly elaborate system prompts trying to make agents more reliable. They add examples. They add reasoning steps. They add validation checks in natural language. None of it works reliably because non-deterministic components require deterministic containers. The architecture creates reliability boundaries around fundamentally unreliable agents.

Constraining the solution space turns out to be the primary mechanism for preventing runaway behavior. When I design an agent system, I define exact tool sets with no ambiguity about what tools exist. If an agent tries to use a tool that doesn’t exist, that should fail at the architecture level before the agent attempts the operation. Hallucinated tools are a failure of architecture, not prompting.

I specify output formats rigorously using schema validation, not gentle suggestions in prompts. I set hard iteration limits that kill loops before they consume the token budget. The metaphor that clarifies this approach: I’m creating narrow hallways with locked doors, not open plazas where agents can wander indefinitely.

The separation between planning and execution implements a critical safety boundary. I let agents gather information freely through read-only operations. Query databases, fetch documents, analyze data—all fine. They can plan multi-step processes using internal reasoning that doesn’t touch external state. But they commit to external actions deliberately, through explicit write operations that cross architectural boundaries and trigger validation.

I never conflate internal reasoning with external writes. The distinction seems obvious when stated but gets blurred in implementation when developers let agents chain operations without intermediate verification. I’ve debugged too many production incidents caused by agents that planned something reasonable but executed something catastrophic because no architectural boundary existed between the two.

Validation happens at boundaries, not within agent logic. When an agent wants to write to a database, send an email, or modify a document, that request crosses an architectural boundary where deterministic validation occurs. Does this action match the expected schema? Does it fall within resource limits? Does it target an allowed system? These checks happen in code, not in prompts.

The human-in-the-loop pattern applies selectively based on action risk. Read operations proceed automatically. Low-risk writes with clear success criteria and easy rollback proceed automatically. High-risk operations—those that are difficult to reverse or have significant consequences—require human approval. I design the approval interface to make decisions easy: show context, explain intent, make consequences clear.

Checkpointing and rollback capability separate production-ready systems from prototypes. Before any state-changing operation, I capture enough information to reverse it. For database writes, I track what changed. For file modifications, I maintain previous versions. For external API calls, I log request parameters and responses. When agents make mistakes—and they will—I can roll back cleanly rather than leaving systems in inconsistent states.

The circuit breaker pattern prevents cascading failures. When an agent operation fails, I don’t let it retry indefinitely. After a configurable number of failures within a time window, the circuit opens and subsequent attempts fail fast. This prevents a confused agent from hammering external systems or consuming the token budget on operations that won’t succeed.

Monitoring and observability aren’t optional. I instrument every agent system with structured logging that captures decision points, tool invocations, and reasoning steps. When something goes wrong—and understanding why requires tracing back through the decision chain—good observability means the difference between quick diagnosis and multi-hour debugging sessions.


## The Testing Challenge

Testing agents isn’t like testing traditional software, and pretending otherwise leads to false confidence. Deterministic inputs don’t produce deterministic outputs. The same prompt with the same tools can yield different results because LLMs introduce inherent randomness.

I’ve developed testing strategies that work despite non-determinism. The first principle: test outcomes, not implementation details. I don’t care if an agent uses tool A then tool B or tool B then tool A, as long as it produces the correct result. This shifts testing from “did the agent follow these exact steps” to “did the agent achieve the goal with acceptable resource consumption?”

For well-defined tasks with clear success criteria, I create evaluation datasets with input-output pairs. Process this invoice, extract these fields, classify this document. The evaluation checks whether the agent produced the correct output, regardless of how it got there. I run these evaluations repeatedly—at least 10 times per test case—to catch failures that occur probabilistically.

For tasks without clear correct answers, I use model-based evaluation. A separate LLM judges whether the agent’s output satisfies quality criteria. This approach works surprisingly well for summarization, content generation, and analysis tasks where multiple valid outputs exist but quality remains assessable.

I maintain a growing library of edge cases discovered in production. Every failure that reaches production becomes a test case. This library compounds in value because it captures the weird, unexpected scenarios that initial testing misses. Over time, the edge case library becomes more valuable than the happy path tests.

The escalation path matters as much as the test results. When an agent encounters a scenario it can’t handle, what happens? I design explicit escalation: flag uncertainty, explain what failed, provide context for human intervention. An agent that knows its limits and escalates appropriately is more valuable than an agent that appears confident while producing garbage.


## Economics Determine Viability

Token consumption patterns determine whether agent approaches remain economically viable at scale. I’ve seen brilliant technical implementations fail because nobody calculated the actual cost per transaction until production invoices arrived.

Before building any agent system, I model the economics explicitly. What’s the token consumption pattern for typical tasks? How does that translate to dollars per successful outcome? What’s the alternative cost—human time, existing automation, or doing nothing? The agent approach must deliver better economics than alternatives, not just better technology.

Intelligent routing by task complexity optimizes costs dramatically. Simple tasks use smaller, cheaper models. Complex tasks use larger, more capable models. The routing decision happens before the agent starts working, based on task characteristics that predict required reasoning depth. I’ve seen this approach reduce costs by 60% while maintaining quality.

The cost structure changes as you scale. Initial deployments handle dozens or hundreds of tasks daily. At that volume, model costs dominate and infrastructure costs round to zero. But scale to thousands or tens of thousands of daily tasks and infrastructure costs—vector databases, orchestration, monitoring—start mattering. I model both curves before building because the optimal architecture differs based on expected scale.

Caching strategies reduce redundant computation. When multiple tasks require the same information retrieval or analysis, I cache results and reuse them. The caching layer needs careful design because naive caching can serve stale results, but intelligent caching reduces token consumption significantly.

The measurement discipline separates successful from failed projects. I define success metrics before deployment, not after. I measure actual cost savings or revenue impact, not proxy metrics like “user satisfaction” or “task completion.” I track adoption rates—if users avoid the agent, it’s not delivering value regardless of technical capability. I monitor failure patterns to distinguish transient issues from systematic problems.

I set kill criteria upfront: if we don’t see X improvement in Y timeframe, we stop. This discipline prevents zombie projects that consume resources without delivering returns.


## Start Simple, Scale Deliberately

The biggest mistake I see builders make is starting too complex. They design elaborate multi-agent systems with sophisticated reasoning capabilities for problems that need simple automation. The complexity becomes the project instead of the value delivered.

I’ve learned to start with the simplest architecture that could possibly work. Single-purpose agents with narrow, well-defined scope. Clear success criteria that eliminate ambiguity about whether the agent worked. Contained failure modes that prevent individual failures from creating system-wide problems.

Document processing provides a perfect starting point. Extract information from invoices, contracts, or forms. The task is well-defined, the success criteria are clear, and the failure mode is contained—if extraction fails, a human can review it. ROI measurement stays straightforward: FTE time saved, multiplied by loaded cost, compared to agent implementation and operating costs.

Data entry and triage systems offer similar characteristics. Take information from one system, transform it according to rules, and write it to another system. Or categorize incoming requests and route them to appropriate handlers. These tasks are boring, repetitive, and expensive when done by humans. Perfect agent territory.

The pattern I follow: deploy a simple agent, monitor it closely, let it handle increasing volume as confidence grows, then identify the next problem to tackle. Each deployment teaches lessons about what works, what fails, and where constraints actually bind. This experience compounds—I develop intuition about which problems will work and which won’t.

As models improve, the same architectural patterns don’t become obsolete—they become more valuable. The memory systems I build today will extract more learning from better models tomorrow. The containment strategies prevent new failure modes that more capable models introduce. The tool interfaces give improved models more leverage.


## The Three Tiers of Agent Capability

I think about agent capabilities in three tiers, and understanding which tier your problem occupies determines whether you should build it today or wait.

Tier 1 represents point solutions deployable today with current technology. Single-purpose agents with narrow, well-defined scope deliver measurable value without introducing massive complexity. Clear success criteria eliminate ambiguity. Contained failure modes prevent individual failures from creating system-wide problems. Document processing, data entry, triage systems—all Tier 1. ROI measurement stays straightforward: time saved versus cost of implementation and operation.

Most builders should focus here because the value is accessible and the risk is manageable. I’ve seen companies save millions annually with Tier 1 agents despite their limitations. The problems are boring, which makes them perfect—nobody wants to do these tasks manually, and automation value is obvious.

Tier 2 encompasses workflow agents emerging over the next 2-3 years as models improve. Multi-step processes with decision points require agents to maintain context across steps and make judgment calls based on intermediate results. Learning from outcomes within sessions lets agents improve their approach during extended interactions. Cross-system orchestration coordinates multiple tools and data sources to accomplish complex tasks.

ROI shifts from pure time savings to process efficiency improvements—tasks that couldn’t be automated previously become automatable. The technical bar rises significantly because coordination complexity compounds. I’m starting to build Tier 2 systems now, but they require more sophisticated architecture and more careful risk management than Tier 1.

Tier 3 describes autonomous agents genuinely arriving in 5-10 years, not tomorrow. Self-directed goal pursuit means agents set their own subgoals based on high-level objectives. Persistent learning and memory allow agents to improve continuously across sessions without human intervention. Minimal human oversight becomes possible because agents reliably handle edge cases and unexpected situations.

ROI enters new territory: capabilities that were previously impossible at any cost become economically feasible. This tier requires breakthroughs in memory, robustness, and reliability that don’t exist yet. Andrej was talking about Tier 3 agents when he said “a decade away,” and he’s right.

Most builders overestimate what Tier 3 will look like—imagining capabilities that remain science fiction—and underestimate the value available in Tier 1 today. The opportunity isn’t waiting for Tier 3. It’s building excellent Tier 1 systems today that naturally evolve into Tier 2 as models improve.


## Follow the Cost, Not the Hype

The most successful agent implementations I’ve seen solve problems that are expensive and boring, not problems that are exciting and cheap. Customer support triage saves millions annually because humans are expensive and the volume is enormous. Document processing eliminates entire FTE positions because manual review is slow and error-prone. Data entry and validation prevent costly mistakes while freeing humans for higher-value work.

When I evaluate whether to build an agent, I calculate the fully-loaded cost of the manual process. Not just salary—benefits, management overhead, training, turnover, errors. Then I estimate agent costs including development, operation, and failures. If the agent delivers 3x ROI within six months, I build it. If not, I wait for models to improve or find a different problem.

The volume question matters tremendously. Agents aren’t justified for tasks that occur weekly. They’re justified when the task happens hundreds or thousands of times, when the manual cost adds up, when the boring repetition drives people to distraction. Find the expensive, boring, high-volume problems and you’ll find where agents deliver immediate value.

I watch for what I call “cost concentration”—scenarios where small improvements in efficiency translate to large cost reductions. A 20% improvement in customer support triage might eliminate the need for two support team members. A 30% improvement in document processing might let you cancel a vendor contract. These concentrated value opportunities justify higher development costs because the return is substantial and immediate.

The competitive analysis includes doing nothing. Sometimes the right answer is to live with the manual process because automation costs exceed benefits. I’d rather deploy no solution than deploy an agent that costs more to operate than the problem it solves. This discipline keeps me focused on real value rather than technical elegance.


## The Patterns That Actually Work

After building dozens of agent systems, certain patterns emerge as consistently effective while others consistently fail. The successful patterns share common characteristics: they constrain agent behavior, they make failures visible and recoverable, and they align economic incentives with desired outcomes.

The state machine pattern constrains agent behavior by defining explicit states and valid transitions. The agent can be in state A, B, or C, and can transition from A to B but not from A to C. This prevents the agent from wandering into unexpected states and makes reasoning about system behavior tractable. I use state machines for multi-step workflows where order matters and certain operations must complete before others begin.

The approval queue pattern handles operations that require human judgment. High-risk actions don’t execute immediately—they enter a queue where humans review context and make decisions. The queue interface shows enough information to make good decisions quickly: what the agent wants to do, why, what the consequences are, what the rollback plan is. This pattern lets me deploy agents in domains where full automation would be risky.

The confidence scoring pattern makes agent uncertainty explicit. When the agent performs classification or makes recommendations, it reports a confidence score alongside the result. Low-confidence results get flagged for human review while high-confidence results proceed automatically. Over time, I adjust the confidence threshold based on observed accuracy—if high-confidence results prove reliable, I raise the automation threshold.

The tool result caching pattern reduces redundant computation. When the agent retrieves information or performs analysis, I cache the result with appropriate TTL. Subsequent tasks that need the same information reuse cached results rather than consuming additional tokens. This pattern requires careful thinking about cache invalidation, but the token savings justify the complexity.

The parallel execution pattern handles tasks that don’t depend on each other. Instead of processing sequentially, I dispatch multiple agents in parallel and aggregate results. This pattern dramatically reduces end-to-end latency for batch operations and improves resource utilization. The aggregation step requires careful design to handle partial failures gracefully.


## The Failure Patterns to Avoid

I’ve also seen consistent failure patterns that builders should avoid. These patterns look reasonable during design but fail predictably in production.

The unconstrained reasoning loop is the classic failure. The agent tries approach A, which fails. It tries approach B, which also fails. It keeps trying variations until it exhausts the token budget or hits an iteration limit. The problem: it’s not learning from failures, just burning tokens. I prevent this by setting hard limits and requiring explicit escalation after a small number of failures.

The implicit state problem occurs when agents assume state that isn’t explicitly tracked. The agent remembers something from earlier in the conversation and acts on that memory, but the memory isn’t persisted anywhere. When the session ends, that state vanishes. Next time, the agent has to rediscover everything. I fix this by making all persistent state explicit and storing it deliberately.

The permission confusion problem happens when agents have access to tools they shouldn’t use for particular tasks. The agent can technically call any tool in its repertoire, but some tools are inappropriate for specific scenarios. Without explicit permission management, agents occasionally invoke wrong tools with bad consequences. I solve this by defining tool availability per task type rather than per agent.

The error propagation problem occurs when agents treat errors as facts. External API calls fail, the agent receives an error message, and then incorporates that error into its reasoning as if it’s valid data. I prevent this by making error handling explicit at architectural boundaries and never letting raw errors propagate to agent context.

The cost explosion problem hits when agents use expensive models for simple tasks or invoke expensive tools unnecessarily. Without explicit cost awareness and routing logic, agents default to maximum-capability approaches for all problems. I fix this by routing tasks to appropriately-sized models and making agents aware of tool costs.


## Building for Production

The gap between prototype and production is enormous. Prototypes demonstrate possibility. Production systems deliver reliability. The difference is architectural discipline applied consistently.

Production systems need comprehensive logging that captures every decision, tool invocation, and outcome. When something goes wrong three days after deployment, I need to reconstruct exactly what the agent was thinking. Structured logs with consistent schemas make this possible. I capture input state, reasoning steps, tool calls with parameters and responses, confidence scores, and final outputs.

Production systems need monitoring that detects degradation before users complain. I track success rates, failure rates, latency distributions, token consumption, and cost per outcome. I set alerts based on deviations from normal patterns rather than absolute thresholds. If success rate drops 10% in an hour, I want to know immediately even if the absolute rate remains acceptable.

Production systems need graceful degradation when dependencies fail. If the vector database is slow, can we fall back to keyword search? If the knowledge base is unavailable, can we proceed with reduced capability? I design fallback paths that maintain partial functionality rather than complete failure.

Production systems need deployment discipline. I never deploy directly to production. I test in staging with production-equivalent data and load. I deploy incrementally—a small percentage of traffic first, then gradually increase as confidence grows. I maintain the ability to roll back quickly if problems emerge.

Production systems need clear ownership and operational responsibility. Someone wakes up when the system fails. Someone reviews logs and metrics regularly. Someone makes decisions about when to intervene versus when to let the system self-correct. This operational discipline makes the difference between systems that stay healthy and systems that slowly degrade.


## The Next Two Years

Models are improving rapidly. The capabilities I struggled to coax from GPT-4 last year emerge naturally from today’s models. This trajectory continues and accelerates. The question for builders isn’t whether agents will become more capable—they will—but how to build systems today that benefit from tomorrow’s improvements.

The architectural patterns I develop now compound in value. Memory systems designed for today’s limitations will work better with tomorrow’s models. Tool interfaces created for current capabilities will give improved models more leverage. Containment strategies that prevent today’s failure modes will prevent the new failure modes that more capable models introduce.

I’m building for a future where models handle more complex reasoning, maintain longer-term context, and exhibit fewer failure modes. But I’m not waiting for that future to deliver value. The agents we have today are capable enough to solve expensive problems when properly architected.

The builders who win this decade aren’t waiting for perfect agents. They’re building with imperfect agents today, developing architectural patterns that scale with model improvements, and delivering ROI that justifies continued investment. Each production deployment teaches lessons about what works, what fails, and where constraints actually bind.

This experience compounds. Early builders develop intuition that latecomers will lack. They understand which problems yield to current capabilities and which require future breakthroughs. They recognize failure patterns before they manifest. They architect systems that benefit from model improvements without requiring rewrites.


## What This Means for You

If you’re building agents today, focus on Tier 1 problems. Find expensive, boring, high-volume work that nobody wants to do manually. Design explicit memory architecture before writing agent logic. Constrain behavior through architecture rather than prompting. Test outcomes rather than implementations. Model economics carefully. Deploy incrementally. Monitor obsessively.

If you’re evaluating whether to build agents, calculate the fully-loaded cost of manual processes and compare to agent costs including failures. Look for cost concentration where small improvements yield large savings. Start with narrow scope and clear success criteria. Plan for the capability you have, not the capability you wish for.

If you’re waiting for better models, you’re leaving value on the table. The agents we have today deliver tremendous ROI when properly architected. The patterns you develop now will compound as models improve. The experience you gain will separate you from builders who waited.

The decade of agents begins not with perfect technology but with disciplined builders who understand how to extract value from imperfect tools. The opportunity is enormous precisely because the gap between current capabilities and ultimate requirements creates space for people who know how to bridge it.

Build with the agents we have. Focus on problems that matter. Use patterns that scale. The time is now.

[![](https://substackcdn.com/image/fetch/$s_!8jtQ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0b9744af-4587-4f5e-a51e-0fd3962154be_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!8jtQ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0b9744af-4587-4f5e-a51e-0fd3962154be_1024x1024.png)
