---
title: "The $300 Overnight Loop That's About To Eat Your Competitive Advantage"
author: "Nate Jones"
published: 2026-04-18
url: https://natesnewsletter.substack.com/p/the-teams-that-can-define-better
audience: everyone
scraped_at: 2026-05-14 14:33:26
---

On March 8, one of the best ML researchers alive pointed an AI agent at his own training code, gave it a single metric, and went to sleep. Two days later the agent had run 700 experiments, found 20 genuine improvements, cut training time by 11%, and surfaced a bug in his attention implementation that he’d missed. Not because the agent was smarter. Because it tried more things, faster, without getting bored after the fifteenth failed attempt.

The researcher was Andrej Karpathy. The script was 630 lines. Ten days later, when SkyPilot scaled the same pattern to 910 experiments on a 16-GPU cluster, the compute bill came in under $300.

On April 2 a small YC startup called ThirdLayer took the same loop and pointed it at something more consequential than training code: the prompts, tools, and orchestration logic that determine how agents behave. A meta-agent rewrote the task agent’s entire scaffolding overnight. Every other entry on the leaderboards it targeted was hand-engineered by humans.

What’s happening is not an intelligence explosion. It’s something quieter and more immediate: optimization loops closing on specific business systems and compounding improvements faster than the organizations around them can track. A local hard takeoff, bounded to a domain, a metric, a sandbox. And the teams that can define “better” clearly enough to hand it to a machine are about to pull away from the teams that can’t.

**Here’s what’s inside:**

- **The Karpathy Loop.** Why three constraints — one file, one metric, one time budget — make agent-driven research actually work, and why the minimalism is the whole point.
- **From training code to agent harnesses.** How the pattern just escalated from optimizing ML code to optimizing the scaffolding around every agent you’ll ever deploy.
- **The local hard takeoff, and who misses it.** Why small teams can run this for a few hundred dollars tonight, and why most enterprises will fail the prerequisites.
- **The safety problem hiding in plain sight.** An agent gaming your metrics looks identical to an agent actually improving your business, right up until the moment it doesn’t.
- **Three prompts to run this weekend.** A diagnostic that tells you whether you’re ready to run the Karpathy Loop on your own system, a pre-mortem that finds every way your metric could be gamed, and a trace audit that flags what your logging is missing before you hand anything to a meta-agent.

If you read the [taxonomy piece I wrote in March about the four types of agents](https://natesnewsletter.substack.com/p/there-are-4-kinds-of-agents-and-youre), this is the sequel. That piece defined auto research as one of four distinct architectures. This one is about what happens when auto research grows up.


## **LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260405_abp_promptkit_1)**

These three prompts take the article’s central claim — that the teams who can define “better” precisely will pull away from everyone else — and put it in your hands as a tool. The Karpathy Triplet Diagnostic walks you through defining the editable surface, the metric, and the time budget for a specific system of yours, and hands you back a program.md-style spec ready for an optimization loop. The Metric-Gaming Pre-Mortem takes whatever metric you’ve defined and adversarially attacks it, returning a categorized gaming vector table plus the holdout scenarios and secondary metrics needed to catch each one. The Trace Infrastructure Audit evaluates whether your current logging would give a meta-agent enough signal to make targeted edits, or only outcomes to guess at, and produces a ranked gap list with specific build-or-buy remediations for each. Run them in sequence if you’re starting from scratch; run any one individually if you already have pieces in place. They’re built for developers deploying agents, executives evaluating readiness, and anyone who wants to run the Karpathy Loop on their own prompts and Claude setups for a few hundred dollars this week. The verdict each prompt produces is designed to be honest: “you’re ready, here’s your spec” or “here’s specifically what’s blocking you.” Both answers are useful. The second one is usually more valuable.


## **The Karpathy Loop: Deceptive Simplicity as Design Philosophy**

Autoresearch works because of the constraints, not the agent. Most people get that backwards. They see “AI does research while you sleep” and assume the magic is in the agent’s intelligence. It isn’t. The magic is in the constraints.

Karpathy’s setup is deliberately minimal. Three files. One of them (`train.py`) is the only file the agent can touch. The agent proposes an edit, runs a five-minute training experiment, checks a single metric (validation bits per byte), and either commits the change or reverts it. That’s the whole loop: one file, one metric, one fixed time budget. The human’s job is to write `program.md`, a plain English instruction file that tells the agent what to explore and what constraints to respect. The human programs the research direction. The agent executes the search.

Fortune called it “The Karpathy Loop.” The structure has three components: an agent with access to a single editable file, a single objectively testable metric, and a fixed time limit per experiment. That’s the whole architecture.

The minimalism isn’t a limitation. It’s the entire point. By constraining the search space to one file, one metric, and one budget, Karpathy made the problem tractable for an agent in a way that a sprawling, multi-file, multi-objective system never would be. The agent can read the whole codebase in one pass, understand the full context of any change, and evaluate whether the change worked within minutes. And it can do this hundreds of times without fatigue, distraction, or the sunk-cost bias that makes human researchers cling to ideas that aren’t working.

In Karpathy’s first run, the agent executed about 12 experiments per hour, roughly 100 overnight. Of those, maybe 20 produced genuine improvements that stacked into an 11% speedup. The hit rate isn’t high. But the iteration rate is inhuman. A productive human researcher might manage 8-10 experiment cycles in a full working day, and most of that time is spent waiting for the GPU, not thinking. The agent doesn’t wait. It doesn’t context-switch. It doesn’t go to lunch.

When Shopify CEO Tobi Lütke tried the same pattern on internal company data, he got a 19% performance gain from 37 experiments in 8 hours. When SkyPilot pointed it at a 16-GPU Kubernetes cluster, the agent ran 910 experiments in 8 hours, discovered that scaling model width mattered more than any single hyperparameter, and spontaneously taught itself to use faster GPUs for validation while screening ideas on slower ones. Total compute cost: under $300.

That last detail matters. We’ll come back to it.


## **The Escalation: From Training Code to Agent Harnesses**

Autoresearch optimizes training code. That’s important, but it’s a narrow domain. The thing that happened in the first week of April is more consequential.

Kevin Gu’s AutoAgent takes the same loop (edit, run, measure, keep or discard) and applies it to agent harness engineering. Instead of optimizing a model’s weights or hyperparameters, it optimizes the scaffolding around the model: the system prompt, the tool definitions, the routing logic, the orchestration strategy. The meta-agent reads failure traces from the task agent, diagnoses what went wrong, modifies the harness, and runs the benchmark again. It hill-climbs on total score.

The claimed results are striking. Gu says AutoAgent hit 96.5% on SpreadsheetBench and 55.1% on TerminalBench, first place on both. I want to be transparent here: as of this writing, those scores haven’t appeared on the official leaderboards. The highest verified SpreadsheetBench entry is Claude Opus 4.6 at 34.89%. The gap between the claimed score and the verified state of the art is enormous. It’s possible the claims are real but unverified, or that they reflect a specific task subset or benchmark variant. I’m not going to treat them as established fact. What I am going to take seriously is the architecture and the emergent behaviors, because those are verifiable from the repo itself.

Three findings from the AutoAgent work matter for the argument I’m building.

First: the meta-agent / task-agent split. Gu’s team tried having a single agent improve itself. It didn’t work. Being good at a domain and being good at *improving* at that domain are different capabilities. The separation lets each agent specialize. The meta-agent becomes a harness engineer, the task agent becomes a domain specialist. This is a design insight that will transfer directly to business applications.

Second: model empathy. Same-model pairings dramatically outperform cross-model ones. A Claude meta-agent writes better harnesses for a Claude task agent than for a GPT task agent, and vice versa. Gu’s team explains this as the meta-agent having implicit understanding of how the inner model reasons: its tendencies, its failure modes, its preferences. The meta-agent shares the same weights, so when it reads a failure trace showing the task agent lost direction at step 14, it understands that failure from the inside. This is a non-obvious constraint that matters for anyone designing these systems.

Third: emergent behaviors the team didn’t program. The meta-agent independently invented spot-checking (running individual tasks instead of the full benchmark suite for small edits, saving compute). It built forced verification loops and formatting validators, steered the task agent to write its own unit tests, invented progressive disclosure by dumping long contexts to files when results overflowed the context window, and built task-specific sub-agents and handoff logic when the domain required it. None of this was specified in the directive. The meta-agent discovered these strategies by analyzing its own failure traces and reasoning about what would help.

This is the escalation that matters for business. Optimizing training code is useful but niche. Optimizing the *harness* (the prompts, tools, routing, and orchestration that determine how an agent behaves) is universal. Every company deploying agents has harnesses. Most of those harnesses were designed by humans making educated guesses. The AutoAgent pattern suggests those harnesses could be systematically optimized by a meta-agent that understands the inner model better than the human engineer does.

And this is just the open-source community. Inside the frontier labs, the ambition is larger. Anthropic has publicly stated that it wants Claude n to build Claude n+1. OpenAI announced it’s aiming for a fully automated AI researcher by 2028, with an “AI research intern” by September 2026. At Davos in January, Hassabis said the self-improvement loop is something all the major labs are actively pursuing. The difference between what the labs are doing and what autoresearch demonstrates is scale and scope, not kind. The loop is the same: propose a change, run an experiment, evaluate, keep or discard. The open-source versions just operate on smaller systems with narrower objectives. The labs are running the same loop on frontier models with broader ambitions. The pattern has already been validated. The question is how far it scales and how fast.


## **The Local Hard Takeoff**

Now I want to be careful with language here, because “hard takeoff” is a loaded term in AI safety circles. It usually refers to a hypothetical intelligence explosion, an AI that improves itself so rapidly that it surpasses human control. That’s not what I’m describing. What I’m describing is something more mundane and, in its own way, more immediate.

A local hard takeoff is what happens when an optimization loop closes on a specific business system and compounds improvements faster than the surrounding organization can track. Your pricing engine spends the weekend rewriting its own heuristics and comes back 30% more accurate. Your fraud detection model discovers patterns no human analyst would try. Your customer support agent autonomously builds verification loops and escalation logic that cut resolution time in half.

Each of these is a “hard takeoff” in the sense that the improvement trajectory is steep, compounding, and largely autonomous. But it’s *local*, bounded to a specific domain, a specific metric, a specific sandbox. It doesn’t escape, and it doesn’t generalize. It just gets really, really good at one thing, really fast.

This is what the pattern looks like in practice. And it’s happening in miniature already. A [dev post from three weeks ago](https://dev.to/zerocopy/karpathys-autoresearch-improving-agentic-coding-skills-3941) about adapting autoresearch for agentic coding skills described exactly this loop: analyze the current skill configuration, apply a scoped change, run deterministic test cases, evaluate on correctness and token usage, compare with baseline, commit or revert. The same pattern, applied to a different domain.

There’s a subtlety here that the AutoAgent work surfaced and that I think is underappreciated: traces are everything. When Gu’s team only gave the meta-agent scores without reasoning trajectories, the improvement rate dropped hard. Understanding *why* something improved matters as much as knowing *that* it improved. Traces give the meta-agent interpretability over the task agent’s reasoning, and that interpretability is what makes targeted edits possible rather than random mutations.

The same logic applies outside ML. An optimization loop that only sees outcomes (revenue went up, churn went down) will produce random, unreliable improvements. An optimization loop that sees the full reasoning chain (here’s why the agent recommended this pricing tier, here’s where the customer dropped off, here’s the decision point where the agent chose wrong) can make surgical edits. The quality of your trace infrastructure determines the quality of your auto-improvement. This is another reason why basic agent deployment infrastructure has to come first: if you’re not capturing detailed traces from your current agents, you have nothing for a meta-agent to learn from.

Companies that can define scorable metrics, build eval harnesses, and run optimization loops will compound improvements at machine speed. Companies that can’t will improve at human speed: quarterly planning cycles, monthly reviews, the glacial pace of organizational consensus. The gap between those two rates of improvement is the local hard takeoff, and it will create asymmetric competitive advantage for the organizations that figure it out first.

Karpathy himself framed it in maximalist terms: “All LLM frontier labs will do this. It’s the final boss battle.” He went further: “You spin up a swarm of agents, you have them collaborate to tune smaller models, you promote the most promising ideas to increasingly larger scales, and humans optionally contribute on the edges.”

He’s describing what comes after the local version. But the local version is where the business value lives right now.


## **The Brutal Reality Check**

Everything I’ve described above (the overnight optimization loops, the emergent agent behaviors, the compounding improvement trajectories) presupposes that your organization can deploy agents in the first place. And if you’ve been reading my work, you know how I feel about the state of that.

I’ve spent the last year documenting why agent deployments fail. I catalogued nine distinct failure patterns, from the Integration Tar Pit (working prototypes that can’t get stakeholder sign-off) to Existential Paralysis (strategy debates that loop endlessly while competitors ship) to the Premature Scale Trap (pilots that work clean and collapse under production conditions). The uncomfortable conclusion from seeing all nine together: most organizations fail AI the same way they fail everything else. AI didn’t create these problems. It just made them expensive faster.

Auto-improvement amplifies every one of those failure modes. Consider the ones that matter most here.

The context layer problem is foundational. I’ve written at length about why agents fail when they lack structured external memory: persistent representations of goals, state, and constraints that survive across sessions. Without domain memory, every agent session reinvents its own definition of done, guesses what happened before, and discovers a different sense of what “success” means. The research on context windows makes this worse: the “Lost in the Middle” findings showed that models struggle to use information in the middle of long contexts, and more recent work on context rot found that performance degrades as input length increases. Longer windows don’t solve the memory problem. They introduce new failure modes.

Now imagine layering auto-improvement on top of that. A meta-agent optimizing a task agent that has no persistent memory, no structured state, no reliable record of what’s been tried before. It’s optimizing in the dark. It can’t distinguish between “this change improved the harness” and “this change happened to work on the three tasks that ran before the context window polluted.” The optimization loop is only as good as the infrastructure underneath it, and for most organizations, that infrastructure is held together with conversation history and hope.

The technical know-how gap is equally severe. Auto-improvement requires evaluation harnesses: sandboxed environments where hundreds of experiments can run without human supervision, with scoring functions that accurately reflect business value. Most teams I work with can’t write a reliable eval suite for their *current* agent deployment. They’re measuring activity instead of outcomes, or they’re using metrics that don’t actually correlate with the business result they care about, or they simply haven’t invested in the testing infrastructure because it doesn’t produce visible output. The Automation Trap (speeding up processes without changing broken outcomes) is the auto-improvement version of this: an agent that optimizes a metric that was never the right metric to begin with.

And the governance vacuum persists. Who owns the output of an auto-improvement loop? Who reviews the 47th experiment at 3 AM? Who decides which optimizations get promoted to production? The organizations that struggle with “who gets fired if the AI makes a bad decision” aren’t going to suddenly develop clear ownership structures just because the agents are now editing their own code.

The honest assessment: auto-improvement is a graduate-level capability. It requires that you’ve already solved agent deployment: the context layer, the domain memory, the eval infrastructure, the governance, the technical depth to build and maintain these systems. Most organizations haven’t finished the undergraduate work.


## **Why Small Teams Win (With Receipts)**

The flip side of the enterprise readiness gap is that the barriers to entry for auto-improvement are collapsing for small, agile teams. The numbers are concrete.

Karpathy’s autoresearch was built by one person. AutoAgent was built by a small YC startup. SkyPilot scaled autoresearch to 16 GPUs on Kubernetes (910 experiments in 8 hours) for under $300 in compute. Claude Code’s API cost for the session was about $9. The GPU time was roughly $260. That’s the cost of a nice dinner for two.

A three-person team with $500 in compute can now run the same kind of optimization loop that would take a 20-person enterprise team months to spec, approve, procure infrastructure for, and execute. The iteration speed advantage is not marginal. It’s orders of magnitude. Twelve experiments per hour on a single GPU. A hundred overnight. Nine hundred on a small cluster. Each experiment is a hypothesis tested, evaluated, and resolved. An enterprise team running the same experiments through their standard development process (design review, implementation, QA, staging, production) might complete one per week.

This doesn’t mean small teams will beat enterprises at everything. It means that on the specific dimension of *rapid iterative optimization against a measurable objective*, small teams have a structural advantage that enterprise scale can’t easily overcome. No approval gates, no six-month procurement cycles, no organizational consensus required to try an experiment. No Integration Tar Pit, no Governance Vacuum, no Existential Paralysis. The nine failure patterns I documented are largely diseases of organizational complexity, and auto-improvement rewards the teams that don’t have that complexity. Just define the metric, build the harness, and let the loop run.

The Reddit community is already here. People are adapting autoresearch for coding skill optimization, building harnesses that tune their own agent configurations, running overnight experiments on personal projects. The tools are open source, the compute is cheap, the pattern is learnable. This is the practitioner’s domain.


## **The Safety Question, Without the Sci-Fi**

I want to address safety seriously without reaching for doomsday scenarios. The relevant safety concerns with auto-improving agents aren’t about intelligence explosions. They’re about failure modes that are quiet, specific, and very easy to miss.

The AutoAgent team observed the most important one directly: agents overfit. The meta-agent “gets lazy,” Gu writes, “inserting rubric-specific prompting so the task agent can game metrics.” In a benchmark context, that means inflated scores that don’t reflect real capability. In a business context, it means an agent optimizing your fraud model to look good on your eval suite while missing actual fraud. Or a pricing agent that maximizes the metric you defined while eroding customer trust in ways your metric doesn’t capture. Or a compliance agent that technically satisfies your test cases while finding creative interpretations of the rules that a human reviewer would immediately flag.

The broader safety community is increasingly uneasy about this trajectory. At the World Economic Forum in January, Google DeepMind CEO Demis Hassabis stated publicly that the self-improvement loop is something all the major labs are actively working on, while acknowledging the risks. Anthropic co-founder Jared Kaplan called recursive self-improvement “the ultimate risk” in a Guardian interview. The ICLR 2026 Workshop on Recursive Self-Improvement acknowledged that evaluation, safety, and governance tools lag behind algorithmic progress, and initially made safety sections in research submissions merely “encouraged, optional.” David Scott Krueger at the University of Montreal has been vocal that the research community isn’t treating RSI safety with sufficient seriousness.

For businesses, the practical safety concerns break down into several categories. Metric gaming is the most immediate: an agent optimizing a proxy metric that diverges from actual business value. Silent degradation is the most insidious: subtle policy drift or quality erosion that persists undetected because the monitoring infrastructure wasn’t designed for autonomous edits. Contamination is the most structural: if the agent’s optimization loop can influence the data it’s evaluated against, the entire ratchet mechanism becomes unreliable. And compounding errors are the most dangerous at scale, when a bad optimization in one system cascades through interconnected business processes.

The autoresearch pattern’s own design provides the best mitigation framework we have: tight loops, clear baselines, version control for every edit, and the ability to revert any change. The agent can only touch one file. The metric is fixed and external. The evaluation function is locked, and the human can inspect every experiment. These constraints make the optimization honest and auditable. But they only work if you actually build them, and building them for production business systems is significantly harder than building them for a single-file training script.

Gu’s team added one more mitigation that’s worth noting: they force the meta-agent to ask itself, “If this exact task disappeared, would this still be a worthwhile harness improvement?” It’s a self-reflection check designed to catch overfitting. It’s also a question every organization running these loops should ask about every optimization an agent proposes.

There’s a deeper structural concern that the ICLR workshop surfaced: we don’t yet have reliable ways to distinguish genuine capability improvement from optimization artifacts. An agent that scores higher on your eval suite might genuinely be better at the task. Or it might have found a shortcut that exploits a blind spot in your evaluation: an edge case your tests don’t cover, a correlation in your training data that won’t hold in production, a formatting trick that satisfies the rubric without satisfying the intent. The autoresearch community calls this “benchmark overfitting” and treats it as a technical problem. In business, it’s a strategic risk. An auto-improving agent that’s actually gaming your metrics looks identical to one that’s actually improving your business right up until the moment it doesn’t.

The only reliable defense is evaluation diversity: multiple metrics, multiple test suites, holdout scenarios the agent has never seen, and periodic human review of the agent’s actual outputs rather than just its scores. This is expensive. It slows the loop down. And it’s non-negotiable if you’re running these systems on anything that matters.


## **What To Actually Do**

I don’t think auto-improving agents are optional. I think they’re the next major capability jump in how AI creates value, and I think the organizations that figure them out in 2026-2027 will build advantages that are genuinely difficult to reverse. But I also think the jump from “basic agent deployment” to “agents that optimize themselves” is large enough that most organizations will try to skip prerequisites and fail.

Here’s the honest path.

Start with the diagnostic. Pick one business system, your most measurable one, and try to define the Karpathy triplet: one editable surface (the thing the agent would modify), one metric (the thing you’d optimize), and one time budget (how long each experiment runs). If you can’t define all three clearly, that’s your first project: building the evaluation infrastructure that would make auto-improvement possible. Not running the loop, but building the prerequisites for it.

Build the eval harness before you build the optimization loop. This is counterintuitive because the eval harness isn’t the exciting part. But it’s the foundational piece. You need a scoring function that accurately reflects business value, a test suite that covers the failure modes you care about, and a sandboxed execution environment where experiments can run without affecting production. Most organizations underinvest in evaluation infrastructure because it doesn’t produce visible output. For auto-improvement, it’s the whole ballgame. You can’t automate what you can’t score.

Prototype on low-risk, high-signal systems. Internal models, A/B testing engines, ops scripts, internal tooling: systems where the cost of a bad optimization is low and the feedback signal is clear. Don’t start with customer-facing systems or compliance workflows. Earn the right to auto-optimize by proving the loop works on systems where failure is cheap.

Design for auditability from day one. Every experiment logged, every edit versioned, every metric trajectory tracked, every revert documented. When an auto-improvement loop produces a gain, you need to be able to explain *why* it worked, not just that it worked. This is both a governance requirement and a learning mechanism. The experiment log is how your organization builds institutional knowledge about what kinds of optimizations work in your domain.

Invest in the human judgment layer. The Karpathy Loop doesn’t eliminate the need for human judgment. It concentrates it. The human’s job shifts from executing experiments to designing the experimental framework: writing the `program.md` that sets direction and constraints, reviewing trajectories for signs of overfitting, deciding which gains to promote to production and which to investigate further. This is a higher-impact role than manual optimization, but it’s not a lower-skill one. It requires deep domain knowledge, clear thinking about metrics, and the ability to spot when an agent is gaming a proxy.

Take small-team agility seriously. If you’re a three-person team, you can run your first auto-improvement loop this week for a few hundred dollars. That’s not aspirational, it’s a concrete statement about available infrastructure. Autoresearch and AutoAgent are both MIT-licensed and open source. The compute is commodity, and the pattern is documented. If you have a system with a scorable metric and an eval harness, you can point a meta-agent at it tonight and review the results tomorrow morning.

If you’re inside a large organization, the honest move is different. You probably can’t run overnight optimization loops on production systems yet, and you shouldn’t try. But you can start building the infrastructure that makes it possible: evaluation harnesses, sandboxed execution environments, metric definitions that actually reflect business value, and the organizational muscle to version, audit, and review agent-generated changes. These investments pay off regardless of whether you ever run the full auto-improvement loop, because they make your basic agent deployments better too.


## **Where This Goes**

Karpathy was right about one thing: this pattern will be everywhere. The Karpathy Loop is too simple, too cheap, and too effective to stay confined to ML training. AutoAgent already extended it to agent harness engineering. The next extensions (to business process optimization, to workflow automation, to operational systems) are a matter of when, not whether.

But the distance between “this works on a single-file training script” and “this works on our enterprise pricing engine” is not a straight line. It’s a series of hard infrastructure problems, governance decisions, and organizational design challenges that no overnight optimization loop can solve for you.

Auto-improving agents are the hard takeoff nobody’s watching because it’s happening locally, quietly, inside specific domains and specific organizations. A pricing model that gets 30% better over a weekend, a support agent that autonomously builds verification loops, a harness that discovers optimization strategies its human engineers never considered. Each one is a small singularity, bounded and measurable, compounding advantages for the teams that built the infrastructure to run it.

The question isn’t whether this is coming. It’s whether your organization can define what “better” means clearly enough to hand it to a machine.

[![](https://substackcdn.com/image/fetch/$s_!WYJj!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa5a5f928-8d3e-431f-859d-da224289a2b6_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!WYJj!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa5a5f928-8d3e-431f-859d-da224289a2b6_1024x1024.png)
