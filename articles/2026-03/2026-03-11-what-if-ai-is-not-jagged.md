---
title: "What if AI is not jagged?"
author: "Nate Jones"
published: 2026-03-11
url: https://natesnewsletter.substack.com/p/cursors-coding-agents-solved-a-math
subtitle: "Watch now | The “jagged frontier” framing that shaped three years of AI strategy was never describing AI intelligence."
audience: everyone
scraped_at: 2026-03-11 12:00:13
---

The “jagged frontier” framing that shaped three years of AI strategy was never describing AI intelligence. It was describing what happens when you remove all organizational structure from the work and ask for one answer in one shot.

The evidence: a general-purpose coding harness built by Cursor solved a research-grade spectral graph theory problem after running for four days with no human guidance, no domain-specific modifications, and no mathematical reasoning machinery. It didn’t just solve it. It improved on the human-written solution. And four organizations independently arrived at the same structural answer: decompose, parallelize, verify, iterate.

The skill that survives this transition isn’t doing the work. It’s evaluating whether the work is correct. That shift is already underway, and it’s moving faster than the model improvement curve would predict.

This is Part 1 of a three-part series. Part 2 covers how knowledge organizations should restructure around this shift. Part 3 covers the new categories of value creation that open up when the execution layer is automated.

The breakdown:

- **Why the Cursor result matters more than purpose-built math systems.** When a coding harness outperforms a domain-specific agent, you’ve learned something about harnesses, not math. The generalization is the finding.
- **The verifiability spectrum.** A framework for classifying your work into machine-checkable, expert-checkable, and genuinely judgment-dependent tiers — and why the judgment-dependent bucket is smaller than you think.
- **Why architectural advances beat the model curve.** Organizational insights transfer across domains at near-zero cost. That’s the mechanism behind the METR data showing task completion horizons doubling every four to seven months.
- **What “sniff-checking” actually means for your career.** The evaluation meta-skills in your domain that are about to get more valuable, not less — and the ones that are about to get cheaper.

But first — how a tool built to write code ended up producing better mathematics than the mathematicians’ own solution, and what that means for the way you work right now.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260305_622_promptkit_1)

After running the kit, you’ll have a concrete map of which parts of your job are ready for structured AI delegation today — and which ones need verification infrastructure before you hand them off. You’ll know where you’ve been overestimating how much of your work is genuinely judgment-dependent versus “involved but routine.” The second prompt gives you the Planner-Worker-Judge pattern as a reusable workflow — bring any complex task and walk away with output that’s materially better than what a single-shot prompt produces, because the AI catches its own errors before you have to. The third prompt produces a 90-day development plan built around the evaluation skills that are gaining value in your specific field, not generic career advice. The whole kit runs in about an hour across three separate conversations. You’ll reference the outputs for months.


# What if AI is *not* jagged?

For three years, the smartest people in every industry built their AI strategy around a single, reasonable observation: AI is jagged. Brilliant at some things, inexplicably bad at others, with no obvious pattern. It could draft a persuasive brief in seconds and fail to count the r’s in “strawberry.” It passed the bar exam and hallucinated a citation that didn’t exist. It wrote poetry and mangled arithmetic.

That jaggedness became the organizing frame for everything. For hiring decisions: AI handles these tasks, humans handle those. For product strategy: build where the model is strong, avoid where it’s weak. For enterprise deployment: find the seams in the frontier where your domain happens to fall on the good side. The “brilliant intern” framing took hold — capable of remarkable output on some days, unreliable on others, and you never quite knew which you were going to get.

Here is what we got wrong: the jagged frontier was never a property of AI intelligence. It was an artifact of how we were asking AI to work.

Single shot. Single agent. One inference, one output, done.

When you ask a model for one answer in one turn, all the variance in task difficulty shows up as jaggedness in outcomes. That’s not because intelligence is jagged. It’s because no organizational structure was being applied to the work. We were asking a capable analyst to solve every problem in thirty seconds with no notes, no colleagues, no ability to try something, recognize it wasn’t working, and try something else.

The mental model that shaped three years of AI strategy was accidentally describing a problem we accidentally created.

Consider what single-turn, single-agent interaction actually means. You present a problem. The model produces one response. If it contains an error midway through, the error propagates through everything that follows. If the first approach is wrong, there’s no mechanism to detect that and try something else. If the task requires more information than fits in one context window, it cannot accumulate that information incrementally. Every problem must be solved in one shot.

This is not how any competent human professional works. It’s not how a lawyer researches a case, how an engineer designs a system, or how a scientist runs an experiment. All of these involve trying things, recognizing when they aren’t working, adjusting, accumulating information over time, getting feedback at intermediate stages, and revising. The organizational structures we’ve built around professional work — review processes, sprint cycles, peer feedback loops, the draft-revise-publish pipeline — exist precisely because serial one-shot cognition is insufficient for hard problems.

We deployed AI into a paradigm that removes all of that structure. Then we described the resulting limitations as a property of the AI.


## The proof

The proof arrived on March 3, when Cursor CEO Michael Truell announced that Cursor had discovered a novel solution to Problem 6 of First Proof — research-grade mathematics problems drawn from the unpublished work of Stanford, MIT, and Berkeley academics. Not just solved it. Improved on the official human-written solution. Stronger bounds, better coverage of the vertex set. They did it using the same harness that six weeks earlier had autonomously built a web browser. The harness ran for four days with no hints, no human nudging, no mid-course guidance.

A system designed to write code looked at a problem in spectral graph theory and produced mathematics that the problem’s own authors hadn’t found.

This is not the most impressive thing to happen in AI mathematics by strict benchmark count. Google DeepMind’s Aletheia — a purpose-built math agent on Gemini 3 Deep Think — solved six of ten First Proof problems within the submission window. OpenAI threw an internal model at the same problems and claimed several solutions. The frontier labs are serious about mathematics.

That’s exactly why the Cursor result matters more than all of them.

Aletheia is purpose-built. Every design decision was made by people thinking about how to do mathematics. When Aletheia solves a math problem, you’ve learned something about math AI. When a coding harness solves a math problem, you’ve learned something about harnesses. The generalization is the finding. Truell’s key claim: “This suggests that our technique for scaling agent coordination might generalize beyond coding.”

That is an understatement so large it may be unintentional.


## The architecture that ate the problem

In January, Wilson Lin published a Cursor blog post on scaling long-running autonomous coding. Their first attempt was flat coordination: agents sharing a single file, using locks to avoid collision. It failed badly. Agents held locks too long, became risk-averse, avoided difficult tasks, and ground without progress. No individual agent took responsibility for the hard problems. The system optimized for safe, small changes instead of end-to-end implementation. What you got was activity without progress — a lot of tokens burning, nothing shipping.

The breakthrough came from hierarchy and specialization. Planners explore the codebase and create tasks, spawning sub-planners recursively. Workers pick up individual tasks and grind until done, ignoring everything else. A Judge determines whether to continue, and the next iteration begins fresh. The Judge’s ability to restart cleanly — bringing in a new agent with fresh context — turned out to be one of the system’s most important properties.

The test case: building a web browser in Rust — a rendering engine, CSS support, and page layout — using the agent swarm with no human code review during the run. The agents ran for close to a week and wrote over a million lines of code across a thousand files. Critics pointed out that early builds had issues, that CI was failing, that this wasn’t exactly Chrome. They were right and also missing the point. The system sustained coherent autonomous work at a scale that would have required a team of engineers and months. Cursor ran the same harness at a Solid-to-React migration (266,000 lines added, 193,000 deleted), a Java language server (550,000 lines), a Windows 7 emulator (1.2 million lines), an Excel clone (1.6 million lines).

Two lessons emerged. First, model choice matters for long-horizon tasks — GPT-5.2 consistently outperforms Claude Opus 4.5, which tends to stop earlier and take shortcuts. Second, and more counterintuitive: “Many of our improvements came from removing complexity rather than adding it.” The actual improvement came from stripping out coordination machinery, adding hierarchy, and letting agents work in clean isolation. And the deepest observation: the system’s behavior is disproportionately determined by prompt design. All that machinery — the parallel execution, the hierarchical roles, the cycle management — and a surprising fraction of what makes it work is how the agents are instructed to think about their work.

When Cursor pointed this system at First Proof Problem 6, they ran it for four days without modification. The problem concerns partitioning vertices of a graph so the Laplacian of each component has bounded eigenvalues. Cursor’s system found an approach using the Marcus-Spielman-Srivastava interlacing polynomial method, improved the constant in the bound from 0.03 to 0.13, and covered the entire vertex set rather than just a subset. If it holds up to final review, it’s not just correct. It’s better.


## The convergence nobody planned

Here is the part I find genuinely strange, and I’ve been watching enterprise AI closely enough that strange is a high bar. Four organizations — Anthropic, Google DeepMind, OpenAI through Codex, and Cursor — independently built multi-agent coordination systems for long-horizon tasks. None of them coordinated with each other. None of them announced a shared design philosophy. And all four systems exhibit the same structural pattern: decompose the work, parallelize execution, verify outputs, iterate toward completion.

Anthropic’s engineering team described their approach in a November 2025 post on effective harnesses for long-running agents. The core challenge they identified: agents work in discrete sessions, and each new session begins with no memory of previous sessions. They compared it to engineers working in shifts with no handoff notes. Their solution was an initializer agent that sets up environment state and a progress file at the start of work, and a coding agent that makes incremental progress and leaves structured artifacts — specifically a claude-progress.txt file and git history — that the next session can read to understand where to continue. The failure modes without this structure are vivid: the agent tries to one-shot an entire implementation, runs out of context mid-build, and leaves things worse than they started. Or it marks features complete without testing them. Or it stops as soon as something looks roughly right rather than verifying that it actually works.

All of this came from watching software engineers work well. Their initializer-coder pattern is a formalization of how good engineers handle handoffs. The shared artifact is the standup note. The git history is the audit trail. There is nothing exotic about the organizational insight; it’s standard engineering practice encoded into an automated system.

Google DeepMind’s Aletheia separates generation, verification, and revision into distinct roles. The Generator proposes. The Verifier attacks. The Reviser corrects. DeepMind’s paper states explicitly that separating verification helps the model recognize flaws it initially overlooks during generation. This is not a new organizational observation either. It’s a generalization of the same principle that underlies code review, legal adversarial proceedings, and scientific peer review: the person generating output and the person checking output have different attentional profiles, and putting them in conflict produces better outcomes than having one entity do both.

OpenAI’s Codex runs tasks in parallel, sandboxed environments with verification loops. It can work independently for more than seven hours on complex tasks. Cursor’s Planner-Worker-Judge pipeline is, as Cursor noted, structurally similar to how software teams with multiple engineers and a PM actually operate.

This convergence isn’t a coincidence. It’s a solution to a real problem: how do you get useful work from computational units with finite context, finite per-step reliability, and no persistent memory? The answer is organizational. You create roles, handoffs, verification, restart procedures. These aren’t AI-specific insights — they’re management insights that generalize down to autonomous agents as naturally as they generalize up to human teams.

Anthropic’s November 2025 post included a “Future work” section that flagged generalization to scientific research and financial modeling as obvious next applications. Four months later, Cursor’s coding harness walked into that future on its own, without anyone at Anthropic specifically pointing it there.


## Not just token burn

The obvious critique: multi-agent is just a more expensive way to do what a single long inference could do. I want to engage this honestly because it’s not entirely wrong. At the most fundamental level, multi-agent systems generate a lot of tokens that wouldn’t be generated in single-turn interactions. Cost is real. Litt notes that per-token cost decline is a critical lever: “Were the per-token cost of existing models to decline substantially, we would already see substantial improvement at fixed cost.” He’s right.

But the “it’s just token burn” framing misses the qualitative difference.

Serial inference gives you depth along one trajectory. If a model makes a wrong turn at step 100 of a 500-step problem, the error compounds for the remaining 400. Extended context doesn’t fix this — it gives the model more wrong trajectory to treat as evidence for continuing in the wrong direction.

Multi-agent coordination gives you structural diversity. Parallel workers explore different decompositions simultaneously. Dead-end results inform the next planning cycle without contaminating other workers’ context. The planner can spawn sub-planners to go deep on specific sub-problems without consuming context budget from the main thread. Partial progress accumulates across context windows rather than resetting when a session ends.

The right analogy is organizational design. A brilliant individual with unlimited time can in principle solve almost anything. But certain problem classes are structurally inaccessible to serial cognition — not because the individual lacks capability, but because the problem requires too many exploratory paths to hold in working memory simultaneously, too many dead ends to avoid contaminating reasoning, too much accumulated context to fit in any single window of attention. We don’t structure organizations as “one very smart person trying everything sequentially.” We structure them with roles and handoffs and verification because doing otherwise doesn’t work, regardless of individual talent.

Applying that insight to AI agents was not obvious. The flat-coordination failure mode that Cursor documented — agents becoming risk-averse, churning without progress, no one taking ownership of hard problems — is exactly what you’d predict from a flat organizational structure with no clear roles. The fix — hierarchy, specialization, judge cycles, clean restarts — is equally predictable from basic organizational theory. What’s remarkable isn’t that these principles apply to agent systems. It’s that it took until 2025-2026 to prove they do.


## The verifiability spectrum

The most practically important question isn’t “can AI do research math?” It’s “what makes a domain amenable to multi-agent harness approaches?” And the answer comes down to verifiability.

Tier 1: machine-checkable. Code compiles or doesn’t. Tests pass or fail. Proofs satisfy a formal checker or don’t. Tier 2: expert-checkable with clear criteria. Informal mathematical proofs, engineering designs meeting specs, legal briefs addressing relevant precedents. A judge agent can meaningfully evaluate quality even without formal automated checking. Tier 3: genuinely judgment-dependent. Original theory-building, aesthetic choices, strategic decisions depending on values rather than facts.

The Cursor result demonstrates something consequential: a Tier 1 harness — built entirely around code — can operate effectively in Tier 2. The Planner-Worker-Judge architecture, designed for a domain where the judge is a compiler, produced valid results in a domain where the judge is a mathematician. The structural design generalized even though domain-specific verification machinery didn’t exist.

What harnesses actually need isn’t machine-checkable verification at every step — they need enough signal to distinguish progress from non-progress, enough structure to identify when a worker has failed and needs restarting. In mathematics, partial progress toward a proof is usually recognizable, even before the proof is complete. In legal analysis, identifying whether a brief has addressed the relevant precedents can be assessed iteratively, even before confirming the overall argument is correct.

The practical question for any knowledge worker: how much of your work can be decomposed into subproblems where partial progress is recognizable and dead ends detectable? The honest answer is: most of it. What looks like holistic judgment is almost always an assemblage of sub-tasks — data gathering, precedent review, hypothesis testing, consistency checking — each more verifiable than the composite.

Litt makes a version of this point about mathematical labor specifically. A large fraction of proving a theorem involves executing arguments that experts would characterize as “involved but routine” — they require sophistication and knowledge, but they’re not the creative leaps that constitute genuine mathematical discovery. Those leaps are Tier 3. But a lot of the surrounding work is Tier 2. The Cursor harness operating on Tier 2 mathematical labor is not doing mathematical research in the full sense. It’s doing something that makes mathematical research faster by handling the parts of it that have enough structure to be automated.

The portion of work that most people think is Tier 3 but is actually Tier 2 is much larger than they expect. And it’s getting larger.


## Why the smoothing rate beats the model curve

This is the most important point in this piece.

When commentators try to explain rapid AI improvement, they reach for two levers: better models and cheaper inference. Both are real and important. But neither explains why a general-purpose coding harness solved a spectral graph theory problem without modification.

If capability improvement were purely about model intelligence or cost per token, domain-specific systems should outperform general ones. Aletheia has purpose-built mathematical reasoning and verification. Cursor’s harness has none of this. And yet Cursor produced what appears to be a novel, stronger result on at least one problem.

What Cursor found: organizational architecture transfers across domains even when domain-specific knowledge doesn’t. The discovery that you need planners, workers, and judges in a clean hierarchy is a discovery about the mathematics of coordination, not about code or math or biology. Once you’ve made it for code, you’ve made it everywhere. The cost of the architectural insight doesn’t increase with each new domain it’s applied to. Before the Cursor result, publicly available scaffolds had not clearly outperformed frontier models running out of the box on First Proof — something Litt and others found notable. Cursor broke that pattern.

This is qualitatively different from model improvement or cost decline. When a new model arrives, you get whatever capability increase that generation provides, then wait for the next. When an architectural insight transfers to a new domain, you get a capability increase essentially for free. Architectural advances don’t depreciate. The Planner-Worker-Judge pattern Cursor validated in January is still valid in March because they pointed it at a math problem and it worked.

This is why I think the METR smoothing rate — task completion horizons doubling every four to seven months, with an apparent acceleration to every four months in 2024-2025 — will continue to beat predictions based on model improvement alone. The METR data is measuring exactly this. Task length is a proxy for decomposability and error recovery. Simple tasks can be done in one shot. Long tasks require sustained coherent work across multiple steps, error detection, and iterative correction. The exponential improvement in task length completion isn’t primarily about models getting smarter — it’s about coordination architectures getting better at applying model intelligence across extended time horizons. Every architectural discovery that transfers to new domains provides free capability expansion in those domains. Cursor didn’t spend six weeks building a math harness. They spent a few days pointing an existing one at a math problem. If the same harness works for spectral graph theory, it probably works for significant pieces of chemistry, materials science, financial modeling, legal research, and clinical trial design. Not all of it. Not the Tier 3 parts. But more of it than anyone predicted, faster than the model improvement curve would imply.

I want to be honest about the countervailing concern, because Litt raises it seriously and he’s right to. Models produce convincing garbage. The First Proof exercise is littered with submissions that looked plausible long enough to fool early readers before experts found the errors. What looks like a harness solving a hard problem might be a harness producing very confident nonsense at scale. This is a real risk and it compounds with system complexity — more agents, more coordination steps, more opportunities for an error at one stage to propagate undetected through the rest.

The honest scorecard on First Proof: perhaps six to eight problems solved across all attempts by all teams, combined. A lot of garbage was also produced. Litt expected two or three solutions; six to eight is more than double the upside case. But the noise floor is also higher than expected — there was more confident incorrect output per correct output than anyone wanted.

This is actually an argument for harness importance, not against it. What distinguishes Cursor’s result from much of the noise is the four-day autonomous runtime — the harness forced coherence over time in a way one-shot attempts don’t. But verification is still the binding constraint. A harness generating more output per unit time is only valuable if you can verify the output. For math, that still requires expert mathematicians, and there aren’t enough to keep up with autonomous proof generators running in parallel. The medium-term resolution is better automated verification — Lean formalization, automated proof checkers, formal methods applied to informal system outputs. Tom de Groot manually orchestrated a formalized Lean proof of one First Proof problem, which Litt describes as the gold standard. That’s the direction. But it’s not yet industrialized.


## What this means for work

The Anthropic 2026 agentic coding trends report describes engineers delegating tasks where they “can relatively easily sniff-check on correctness.” What engineers are doing isn’t delegating easy work — they’re delegating verifiable work. The skill that survives this transition isn’t “can do the work.” It’s “can evaluate whether the work is correct.” That’s a different skill, though it’s deeply related.

Litt’s framing of what’s hard about automating math is instructive here: the binding constraints are truth-seeking (models produce convincing incorrect proofs), creativity (identifying which questions are worth asking), and learning (building mathematical intuition over time through engagement with problems). None of these are proof-execution skills. They’re meta-skills about mathematical research.

In coding, the equivalent meta-skills are things like: knowing whether the architecture a harness produced is maintainable, recognizing when a technically correct solution is fragile, understanding when tests cover the important cases versus when they only cover the obvious ones. These are skills that get more valuable as harnesses get better at the execution layer, not less valuable. The engineer who can’t evaluate AI-produced code is in trouble. The engineer who can evaluate it quickly and well is in an excellent position.

The question for other knowledge domains is: what are the equivalent meta-skills? What does “sniff-checking” look like for financial modeling, or legal research, or clinical trial design? In each case, there’s an evaluation competency that sits above execution competency and becomes more valuable as execution gets cheaper. The people who develop that evaluation competency now are the ones who will find themselves well-positioned when harnesses come for their domains.

This is not a comfortable analysis for everyone. There are domains where execution competency is most of the job because there isn’t much evaluation infrastructure — where the work product is the expertise and there’s no clean separation between doing the work and verifying it’s correct. Those are the domains where the transition is going to be most disruptive. I don’t have a reassuring framework for that. The honest thing to say is that the verifiability spectrum maps imperfectly onto how work is currently organized, and the reorganization implied by improving harness capability is going to create friction in places where people aren’t expecting it.


## What the convergence implies

The fact that four organizations independently built structurally similar harnesses tells you the organizational insight was overdetermined — latent in the problem structure, waiting to be discovered. The specific techniques differ, the specific models differ, the verification approaches differ. But decompose-parallelize-verify-iterate shows up everywhere because it’s the right answer to the problem of getting coherent work from agents with limited context and uncertain per-step reliability.

And once discovered in coding, it transferred to mathematics in under two months with apparently minor modification. The next question is where it transfers next, and at what cost.

The Anthropic harness post mentioned scientific research and financial modeling as obvious next applications. Both share the key property that makes First Proof tractable for a general harness: there is enough structure to allow a judge agent to evaluate partial progress. Experiments have expected outcomes. Trades have verifiable returns. Literature has citable sources. The work is complicated but not fundamentally unstructured.

The Cursor result suggests the timeline for those applications is shorter than anyone’s forecast. You don’t need a purpose-built science harness or a purpose-built finance harness. You need someone to point a coding harness at a science problem and run it for four days. That experiment is probably already happening in several labs as I write this.


## Three caveats and the direction

First: the Cursor solution is still pending final expert review. The mathematics I’ve described might not hold up under scrutiny from Srivastava and Spielman. If it doesn’t, the structural argument about harness generalization is unaffected — a four-day autonomous run on a research-level math problem is still unprecedented regardless of whether the specific solution is correct — but the claim about producing a novel stronger result would have to be walked back, and I want to be clear about that.

Second: reliability jaggedness may matter more than capability jaggedness for real-world adoption. The First Proof exercise showed that harnesses can produce correct outputs on hard problems, but they produce a lot of incorrect outputs too. For production use in law, medicine, or finance, the false positive problem is as important as the capability problem. Better automated verification is the path, but we’re not there yet.

Third: cost remains a real constraint. Four days of hundreds of concurrent agents is not cheap. The math works at scale only if per-token prices continue to decline, and they will, but access to long-running harness compute is not democratized yet.

The direction, though, is clear. The smoothing of the jagged frontier is happening faster than model improvement alone would predict, because the architectural insight that drives the smoothing transfers across domains at close to zero marginal cost. The relevant question for anyone doing knowledge work is shifting from “can AI do my specific task?” to “can my work be decomposed into verifiable sub-problems?” The answer to the second question is “yes” for far more work than most people currently assume.

And the organization that figures out how to structure its work in a way that can be handed to a general-purpose harness — rather than waiting for a purpose-built domain-specific one — will move faster than the organization waiting for the specialists to arrive.

That’s not the AI story people have been telling. But it’s the one the evidence is pointing toward. The harness is the story.

[![](https://substackcdn.com/image/fetch/$s_!R4xh!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3fd34478-d104-49bd-bb99-0e4221694fff_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!R4xh!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3fd34478-d104-49bd-bb99-0e4221694fff_1024x1024.png)
