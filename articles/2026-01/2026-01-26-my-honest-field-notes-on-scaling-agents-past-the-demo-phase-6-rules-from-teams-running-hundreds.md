---
title: "My honest field notes on scaling agents past the demo phase + 6 rules from teams running hundreds"
author: "Nate Jones"
published: 2026-01-26
url: https://natesnewsletter.substack.com/p/why-dumb-agents-mean-smart-orchestration
subtitle: "Watch now | Turns out more does not actually mean better--and when it comes to agents, more is actually worse."
audience: everyone
scraped_at: 2026-01-26 12:00:18
---

A December 2025 study from Google and MIT found something I wasn’t expecting: adding more agents to a system can make it perform worse. Not diminishing returns—actual degradation. The researchers documented configurations where more agents produced worse outcomes than fewer—a finding that directly challenges the field’s working assumption that adding agents means adding capability.

I’d been operating on that assumption. The whole pitch for multi-agent systems is parallelism: more workers grinding on your problem means faster results. That’s how compute has always worked. But agents aren’t GPUs. They’re entities that need to coordinate, and coordination creates overhead that grows faster than capability. Past some threshold, most of your agents are effectively standing in line.

What got me digging deeper was noticing that the teams who’ve actually scaled past the prototype phase—Cursor running hundreds of agents on week-long autonomous coding, Steve Yegge orchestrating 20-30 simultaneously in Gas Town—weren’t comparing notes. They solved the same problem independently and landed on the same counterintuitive patterns. That kind of convergence usually means something real is going on underneath.

So I spent a couple weeks sorting through what they actually built versus what the frameworks recommend. The gap is uncomfortable. The industry consensus says agents should collaborate like human teams, share context, coordinate dynamically, operate continuously. The architectures that actually scale do almost none of that. They look too simple to work—until you understand why simplicity is the point.

**Here’s what’s inside:**

- **The scaling problem the frameworks don’t warn you about** — Why coordination overhead compounds, and the research quantifying when it starts hurting more than helping.
- **Six rules from the teams running hundreds of agents** — The specific patterns Cursor and Yegge converged on independently, from strict two-tier hierarchies to treating agent endings as a feature rather than a bug.
- **Where complexity should actually live** — The case for dumb agents and smart orchestration, and why that inversion determines whether your system absorbs compute or chokes on it.
- **What this means if you’re making bets in 2026** — The questions that reveal whether a project or vendor has figured this out, and why Gartner’s prediction that over 40% of agentic AI projects will be canceled by the end of 2027 is probably right.

Let me start with what the Google-MIT researchers actually found, because the numbers are more specific—and more uncomfortable—than the headline suggests.


## **Grab the prompts (links below)**

The prompts below are designed as a diagnostic sequence. Run through them and you’ll produce the actual artifacts you need: a scale-or-fix decision, a map of your coordination choke points, system prompt templates for Planner/Worker/Judge roles, worker boundary documents, a tool diet, a session lifecycle with checkpoint protocols, judge criteria, and a merge policy.

Each section forces you to make the architectural decisions the article describes—separating generation from decision, eliminating serial dependencies, pushing complexity into orchestration instead of agents. Skip the sequence and you’ll default to the intuitive design that breaks at scale. The prompts exist because “I’ll figure out coordination later” is how 40% of agentic projects end up canceled.

Two versions, same outcome:

- ***[Multi-Step Kit](https://www.notion.so/product-templates/The-Scale-with-Simplicity-Prompt-Kit-Multi-Prompt-2f15a2ccb52680b8a3e6fae7448c2daf?source=copy_link)*** — Eight separate prompts you run in order, pasting each output into the next. Use this if you want to work in chunks, think between sections, or customize individual prompts.
- ***[Single-Session Guide](https://www.notion.so/product-templates/The-Scale-with-Simplicity-Prompt-Kit-Single-Prompt-2f35a2ccb5268001b754eaaacc11d44d?source=copy_link)*** — One guided conversation that walks you through all eight sections, asking questions one at a time. Use this if you want to knock it out in 30-60 minutes without managing handoffs.


## **The Problem Everyone’s About to Hit**

The pitch for multi-agent AI systems is seductive: instead of one AI working on your problem, what if you had ten? Or a hundred? Specialized agents handling different parts of the task, coordinating like a well-run team, accomplishing in hours what would take weeks.

The intuition that fails: if one agent finishes a task in an hour, ten agents should finish in six minutes. This is how every other computational resource works. More GPUs, faster training. More servers, higher throughput. Agents should scale the same way.

What actually happens: when you add agents, you add entities that need to coordinate. Each coordination point is where agents wait for each other, duplicate work, or create conflicts needing resolution. As agent count grows, coordination overhead grows faster than capability. Past some threshold, twenty agents produce less than three would have—seventeen are effectively standing in line.

The Google-MIT study quantified this. Once single-agent accuracy exceeds about 45%, adding more agents yields diminishing or negative returns. In tool-heavy environments, multi-agent systems required roughly 1.6–6.2× the token budgets to match single-agent performance—a coordination tax that often wiped out any parallel processing gains.

In 2025, you could avoid this by not scaling. In 2026, compute costs will make it economically attractive to run hundreds of agents—if your architecture can absorb them. The teams that can will outship the teams that can’t. The question is whether you’ve built the architecture that scales or the architecture that chokes.


## **The Consensus That Works—Until It Doesn’t**

The agentic AI community has converged on design principles that feel like settled wisdom. If you’ve read the framework documentation or watched the conference talks, you’ve heard these ideas repeated until they seem obviously true.

Multiple specialized agents should collaborate, interacting and delegating in patterns that mimic human teams. Agents should integrate as many tools as possible to extend their capabilities. They should operate continuously, accumulating context over long periods as they learn the codebase or the problem domain. They should be autonomous enough to set their own sub-goals without needing explicit instructions for every step. And you should be able to scale by adding more agents—parallelism should translate to throughput.

Here’s the thing: these principles actually work. At small scale. With three to five agents running for an hour, you’ll see the vision realized. The agents coordinate, the work gets done, and you think you’ve figured it out.

They fail at large scale, in ways the frameworks don’t warn you about. The pattern across every failure mode is the same: intuitive implementations create serial dependencies between agents. A serial dependency is any point where one agent’s work blocks another’s—waiting for a lock, checking shared state, coordinating on who handles what. At small scale, you don’t notice the overhead. At large scale, it dominates. Enough serial dependencies and your parallelism collapses. You’re paying for a hundred agents but getting the throughput of five.

The rules that actually scale are the ones that eliminate serial dependencies. They look almost too simple compared to the sophisticated architectures that seem like they should work better. But they’re what the teams running hundreds of agents actually use, and they didn’t arrive at these patterns because they’re philosophically committed to simplicity. They arrived here because everything else failed when they tried to scale.


## **Rule 1: Two Tiers, Not Teams**

The consensus says agents should collaborate like human teams—interacting, delegating, debating, reaching consensus.

Cursor tested this directly. They gave agents equal status and let them coordinate through a shared file—each agent checking what others were doing, claiming tasks, updating status. Locking mechanisms prevented conflicts.

It failed in ways that matter. Agents held locks too long or forgot to release them. Even when locking worked, it became a bottleneck—most time was spent waiting. In Cursor’s tests, twenty agents slowed to the effective throughput of two or three. They tried simpler concurrency control, but the deeper problems persisted.

The unexpected failure mode was behavioral. With no hierarchy, agents became risk-averse. They gravitated toward small, safe changes. Hard problems sat unclaimed because claiming meant taking responsibility for potential failure while other agents racked up easy wins. Work churned without progress. The diffuse responsibility that was supposed to enable autonomy instead meant nobody took responsibility for anything that mattered.

The “team dynamics” metaphor imports human coordination patterns that are inherently serial. Meetings are synchronization points where everyone waits for everyone else. Status updates create read-after-write dependencies. Shared documents require conflict resolution. These mechanisms work for humans because human work is slow enough that coordination overhead is a small fraction of total effort, and because humans are good at the informal negotiation that resolves ambiguity without explicit protocols. For agents operating at machine speed on tasks that take seconds rather than hours, the coordination overhead dominates.

The rule: Strict two-tier hierarchy. Planners create tasks, workers execute them, a judge evaluates results. Workers don’t coordinate with each other—they don’t even know other workers exist. Each picks up a task, executes in isolation, pushes changes, terminates. Git handles conflicts after the fact.

Yegge arrived at the same structure independently with Gas Town. His “polecats” are ephemeral workers that spin up, execute a task, hand it to the Merge Queue, and get fully decommissioned. They don’t coordinate with other polecats. The Mayor and Deacon sit above them, creating and assigning work. The architecture emerged from four failed orchestrators, each teaching him what didn’t work until he converged on what did. Four complete failures is a lot of tuition, but the lesson was clear: peer coordination doesn’t scale.

Practitioner experience points in the same direction. Flat systems maximize serial dependencies. Deep hierarchies—three levels or more—accumulate drift as objectives mutate through delegation layers; by the time instructions reach the bottom, they may bear little resemblance to what the top level intended. Two tiers is the minimum structure that enables coordination while preserving parallelism.


## **Rule 2: Workers Stay Ignorant**

The consensus says agents should understand context and adapt to overall goals. Smarter, more aware agents should produce better results.

The opposite is true. Workers perform better when deliberately kept ignorant of the big picture.

When Cursor’s workers understood broader project context, they experienced scope creep. They’d decide adjacent tasks needed doing, or reinterpret assignments based on their understanding of goals. Each decision potentially conflicted with other workers, and resolving conflicts required coordination—serial dependencies.

A worker that only knows “implement this specific function” can’t decide to refactor the whole module. The narrow scope eliminates coordination needs and enables parallel execution.

Yegge’s polecats work identically. They receive a task, execute it, terminate. No knowledge of other polecats. No context about project direction. Planning happens at the Mayor level; polecats just grind.

The rule: Minimum viable context. Workers receive exactly enough to complete their assigned task, no more. Enforce this through information hiding, not instructions workers might override.


## **Rule 3: No Shared State**

The consensus says parallel agents should share state to stay coordinated. The Google-MIT study found the opposite: in tool-heavy environments, multi-agent systems paid massive coordination taxes. Tools become shared state. Multiple agents accessing the same resources create contention. Contention requires coordination. Coordination creates serial dependencies.

The same dynamic applies to context. The assumption that more tools mean more capability drives the MCP ecosystem, where developers connect dozens of integration servers. But in practice, many teams report tool selection accuracy degrading as catalogs grow beyond a few dozen options—though the exact threshold varies by architecture and retrieval approach. The problem isn’t fitting tools into the context window; it’s that selection accuracy drops when agents face too many options. This is a serial dependency with the tool catalog itself.

The rule: Workers operate in complete isolation. No shared state, no communication, no awareness of each other. Keep tool sets small—three to five core tools always available, others discoverable on demand through progressive disclosure. Coordination happens through external mechanisms designed for concurrent access—git for code, task queues for assignment, test suites for validation.

This creates a downstream problem: isolated workers pushing changes that need merging. Both Cursor and Gas Town discovered you need dedicated infrastructure for this. Gas Town has the Refinery—an agent responsible for merging all changes, one at a time, to main. The Refinery exists because workers don’t coordinate; something has to reconcile their outputs. The complexity of merging moves out of workers and into a dedicated system that handles it as a queue.


## **Rule 4: Plan for Endings**

The consensus says agents should operate continuously, accumulating context over long periods. Long context windows enable this; memory systems extend it further. The vision is an agent that builds up understanding over hours or days, becoming more effective as it learns.

But context accumulation creates a serial dependency with the agent’s own past. As histories grow, context fills with information that may no longer be relevant. The agent doesn’t forget—it stops prioritizing correctly because signal dilutes in noise. Researchers call this “context pollution.” It contributes to drift—progressive degradation of behavior and decision quality that emerging research suggests affects a meaningful fraction of long-running agents, though the dynamics are still being mapped.

The problem isn’t just that context windows fill up. Even when there’s technically room, the agent’s attention gets diluted across accumulated history. The “lost in the middle” phenomenon—where models lose track of information in the middle of long contexts—persists even with massive context windows. An agent that’s been running for hours has accumulated so much context that it struggles to prioritize what matters now.

Cursor found drift unavoidable during continuous operation. Quality degraded within hours, regardless of context window size. Specifications would mutate as agents misremembered or misinterpreted earlier decisions. The system would gradually lose coherence.

Yegge built this directly into Gas Town with GUPP—the “Gastown Universal Propulsion Principle.” It exists because “the biggest problem with Claude Code is it ends. The context window fills up, and it runs out of steam, and stops.”

Rather than fighting this, Gas Town treats endings as a design parameter. Sessions are ephemeral cattle. Work is expressed as “molecules”—chains of tasks stored externally. When an agent ends, the next session picks up by reading the molecule state. “If the workflow is captured as a molecule, then it survives agent crashes, compactions, restarts, and interruptions.”

This is what Yegge calls “Nondeterministic Idempotence”—the path is unpredictable, but the outcome is guaranteed because workflow state lives outside any agent’s context. The agent might crash, restart, make mistakes and correct them. Doesn’t matter. The molecule tracks progress, and the next session continues from where the last one stopped.

The rule: Episodic operation with planned resets. Each cycle runs for a bounded period, captures results to external storage, terminates. Next cycle starts fresh with clean context. External memory—vector databases, structured logs, state files—provides reference points immune to drift. The question isn’t whether agents will end—it’s whether your architecture treats endings as failures to prevent or natural boundaries to design around.


## **Rule 5: Prompts Over Infrastructure**

The consensus says coordination infrastructure is where the hard engineering happens—message passing, state management, error handling.

Cursor found that “a surprising amount of behavior comes down to how we prompt the agents.” Infrastructure matters, but prompts matter more.

Sophisticated coordination infrastructure often adds serial dependencies rather than removing them. Message queues serialize access to shared resources. State synchronization requires agents to agree on what exists before proceeding. Good prompts reduce coordination needs. An agent that clearly understands its role, boundaries, and success criteria doesn’t need to check with other agents. It just executes.

A March 2025 study analyzing over 1,600 execution traces across seven multi-agent frameworks found that system design problems (44%) and inter-agent misalignment (32%) together account for over three-quarters of all breakdowns—with task verification issues making up most of the rest. The crashes, race conditions, and performance problems that engineers obsess over? A small fraction of what actually goes wrong. Systems don’t fail because the code is wrong. They fail because the design created serial dependencies, or specifications were ambiguous enough that agents did wrong things while functioning correctly.

The rule: Treat prompts like API contracts, not prose documentation. Invest more in clear specifications than sophisticated coordination mechanisms. When systems underperform, remove components before adding them.


## **Rule 6: Tests as Architecture**

There’s a question the previous rules leave unanswered: if workers don’t coordinate with each other, how do they stay aligned? How does the system catch errors before they compound?

The consensus treats test suites as validation—a way to check whether work is correct after it’s done. But tests serve a deeper architectural function that matters specifically for multi-agent systems: they provide coordination without creating dependencies between agents.

Cursor chose to build a browser specifically because web standards provide extensive conformance test suites. When a worker’s changes break tests, the worker discovers this by running the tests—not by asking other agents whether anything went wrong, not by checking with a coordinator, not by reviewing what others have done. Multiple workers can consult the test suite independently without creating any dependencies between them. The tests coordinate without serializing.

Without test suites, agents either need external judges evaluating every decision—which creates serial dependencies on the judge—or they accumulate errors silently because nothing tells them when they’ve drifted from the specification. The agent doesn’t know it picked the wrong approach. Errors compound until recovery becomes impossible.

The rule: Design work around domains with testable correctness. Tasks with clear conformance criteria—building against specifications, migrating between frameworks, implementing well-defined interfaces—are tractable in ways that open-ended tasks aren’t. If you don’t have test suites, you need shorter feedback loops and more human oversight. The tests become an architectural element that enables parallel work by providing shared ground truth without shared state.


## **Where Complexity Actually Belongs**

There’s an apparent contradiction here. I keep saying simplicity scales, but Gas Town is complex. Seven worker roles. Patrols and molecules and wisps and convoys. A Deacon with Dogs. Yegge himself says it “looks like Kubernetes mated with Temporal and had a very ugly baby.”

The resolution: complexity can live in agents or in the orchestration layer that keeps simple agents running. These have very different scaling properties.

Complexity in agents creates serial dependencies. An agent that coordinates with others, maintains shared state, understands the big picture—that agent is entangled with everything else. Adding more such agents adds more entanglement. The system becomes harder to parallelize, not easier.

Complexity in orchestration enables parallelism. Gas Town has a Witness watching polecats because someone needs to notice when workers get stuck—but polecats stay simple. It has a Refinery because isolated workers create merge conflicts—but workers don’t know about each other. It has GUPP and nudges and Boot the Dog because agents end—but each session is disposable.

The orchestration complexity exists because the agents are simple. Simple agents need external systems to keep them running (they stop), feed them work (they don’t plan), merge their outputs (they don’t coordinate), track progress (they don’t remember).

This is the inverse of where most teams put complexity. The intuition is to make agents smarter, more capable, more autonomous—push intelligence into the workers. But that creates serial dependencies. The architecture that scales pushes coordination up into external systems and keeps workers dumb.

Yegge’s Kubernetes comparison is apt: “Both systems coordinate unreliable workers toward a goal.” Both have a control plane watching over execution nodes, each with a local agent monitoring ephemeral workers. But “Kubernetes asks ‘Is it running?’ while Gas Town asks ‘Is it done?’” Workers are cattle either way. Intelligence lives in the systems that herd them.

The implication for 2026 is that the investment should go into orchestration, not agent sophistication. Build systems that can feed, monitor, and merge the outputs of many simple workers. Don’t build elaborate agents that need to understand the world to function.


## **What This Means for 2026**

The teams that win this year will be the ones who can absorb compute—who can add agents and get proportional throughput gains instead of coordination collapse.

The architecture that scales:

- Two tiers. Planners and workers, clean separation. Never deeper.
- Isolated workers. No shared state, no communication. Workers don’t know each other exist.
- External orchestration. Complexity in systems that feed, monitor, and merge worker outputs.
- Episodic operation. State lives outside agent context. Plan for endings, don’t fight them.
- Prompts over infrastructure. Clear specifications beat sophisticated coordination.
- Small tool sets. Three to five core tools, others on demand.
- Test suites as coordination. Shared ground truth without shared state.

Cursor now runs systems producing over a million lines of code autonomously in sustained experiments. Gas Town, just seventeen days old, lets Yegge “use 20-30 agents at once, productively, on a sustained basis.” Different teams, different systems, same principles—discovered independently through experimentation.

For technical teams: The Gartner 40% will come from those who built what the frameworks recommended: rich coordination, continuous operation, sophisticated inter-agent communication. They’ll scale up, hit coordination ceilings, and conclude agentic AI doesn’t work for their use case. They’ll be wrong about the cause. The problem won’t be the models or the compute—it’ll be an architecture that created serial dependencies faster than it created capability.

For executives and strategists: When you’re evaluating AI vendors or internal projects, ask how they handle coordination at scale. If the answer involves agents “collaborating like teams” or “sharing context dynamically,” you’re looking at an architecture that works in demos but breaks in production. The teams that understand these dynamics will dramatically out-produce the teams that don’t—not because they’re working harder, but because their architecture converts compute to capability instead of burning it on coordination.

For everyone watching this space: The conventional wisdom isn’t stupid. It’s intuitive, which is why everyone converged on it. But intuition breaks at scale, and 2026 is the year scale arrives. Compute costs are dropping. The economic pressure to run hundreds of agents is building. The teams that figured out what actually works—dumb agents, smart orchestration, clean separations—will have capabilities that look like magic to the teams still debugging coordination overhead.

My bet is that the future isn’t one brilliant agent running for a week. It’s ten thousand dumb agents running for an hour, coordinated through external state, each one simple and isolated and disposable. That’s the architecture I think 2026 rewards. That’s what the evidence suggests actually scales.

The transition will be gradual, then sudden. It’s already underway, and this year will sort the teams who understood this from the teams who didn’t.

[![](https://substackcdn.com/image/fetch/$s_!i6NN!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5475f772-e24a-4421-b89b-77760c41fddf_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!i6NN!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5475f772-e24a-4421-b89b-77760c41fddf_1024x1024.png)
