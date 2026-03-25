---
title: "You're using the wrong kind of agent. Here's the one question that tells you which one you actually need + 3 diagnostic prompts"
author: "Nate Jones"
published: 2026-03-25
url: https://natesnewsletter.substack.com/p/there-are-4-kinds-of-agents-and-youre
subtitle: "Watch now | Dark factories aren't coding tools. Auto research isn't a dark factory. If those distinctions don't mean anything to you yet, this article is going to be very useful."
audience: everyone
scraped_at: 2026-03-25 12:00:17
---

There are four kinds of agents. Most people think there’s one.

I hear this confusion everywhere now. Senior engineers evaluating tools. PMs writing roadmaps that say “integrate agentic capabilities.” ICs on Twitter arguing about whether Cursor or CrewAI is “better” — as if that comparison even makes sense. Founders pitching “agent-powered” products without being able to explain what kind of agent they mean. The word “agent” has become the “cloud” of 2026. Everyone uses it. Almost nobody means the same thing.

I’ve watched someone try to use a dark factory to write a novel. I’ve watched someone reach for CrewAI to solve a coding problem that needed a single agent and a good test suite. I’ve watched someone point an auto research loop at writing new software from scratch — which, if you understand what auto research actually does, is like pointing a profiler at an empty file. There’s nothing to optimize.

Every one of those people thought they were using “agents.” They were. They just picked the wrong subspecies for the problem, and the reason they couldn’t tell the difference is that every landing page, every pitch deck, every hot take uses the same word to describe four architectures that have about as much in common as a forklift and a bicycle.

Analysts project the AI agent market will grow from roughly $8 billion in 2025 to over $50 billion by 2030 (MarketsandMarkets, BCC Research). The money is real. The confusion about where to point it is the expensive part.

**Here’s what’s inside:**

- **The four architectures.** Coding harnesses, dark factories, auto research, and orchestration frameworks — what each one actually does, who’s using them in production, and what breaks when you pick the wrong one.
- **The Karpathy-Lütke-StrongDM-DocuSign map.** How the people getting this right choose different tools for different problems — and why none of them confuse one architecture for another.
- **The one-question test.** One diagnostic question that cuts through the ambiguity — works whether you’re an IC choosing tools or a CTO setting strategy.
- **The operating principles.** Decomposition, specification-as-code, metric-plus-guardrail, and handoff contracts — one governing principle per architecture that determines whether it works or wastes your quarter.
- **The prompts.** Three diagnostic prompts that classify your problem into the right architecture, pressure-test whether you’re actually ready for it, and catch mismatches before they cost you a quarter.

The taxonomy matters because the fix for each problem lives in a different place than most people are looking. Let me show you the map.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260321_gfr_promptkit_1)

The taxonomy above gives you the map. These three prompts make it usable before your next planning cycle. The **Architecture Diagnostic** runs you through the one-question test for a specific problem you’re facing — it classifies your situation, names the tools, and flags the mismatch you’re most likely to make. The **Readiness Assessment** takes the architecture you’ve chosen and pressure-tests whether your team actually has the preconditions: spec maturity for a dark factory, a computable metric for auto research, decomposition skill for a coding harness, defined handoff schemas for orchestration. Most teams skip this step and discover the gap three months in. The **Mismatch Detector** is for teams that have already committed — paste in your current tool and problem, and it tells you whether you’ve built an expensive solution to the wrong question. Start with the Diagnostic.


## The four architectures


### Coding harnesses

Claude Code, Cursor, Codex, Windsurf, Cline. At the task level — which is where most of the real production work is happening right now — these all follow the same pattern: a single powerful language model with a tool belt (read file, write file, execute bash, search code) running in an agentic loop: think, act, observe, repeat. Not multi-agent orchestration. Not role-based crews. One model, working iteratively against your codebase, using tools the way a developer uses a terminal.

Multiple practitioners have converged on the same observation: for human-directed coding, the tools actually shipping production code all landed on this single-agent design independently. One model. Tool belt. Agentic loop. The orchestration is minimal by design.

This is what Andrej Karpathy is describing when he talks about running Claude Code sessions for sixteen hours a day. He hasn’t typed a line of code since December. What he’s doing is directing single-agent sessions — describing functionality at the level of macro actions, reviewing output, spinning up the next session on a non-conflicting task. “It’s not just like here’s a line of code, here’s a new function,” he said on the No Priors podcast. “It’s like here’s a new functionality and delegate it to agent one. Here’s a new functionality that’s not going to interfere with the other one. Give it to agent two.”

A widely shared screenshot of a monitor full of Codex agents captures this visually — each agent running against its own repo checkout, each taking about twenty minutes, the developer moving between them assigning work and checking output. The parallelism comes from many independent agents, not from wiring agents together into a pipeline.

Karpathy calls the experience “AI psychosis” — the sense that you’re always the bottleneck in a system with more capability than you can saturate. When something doesn’t work, the default assumption is skill issue. Not that the tool can’t do it, but that you haven’t figured out the right decomposition, the right agents.md file, the right way to instruct it. That psychological texture tells you what this architecture demands: judgment about what to delegate, how to decompose work into non-conflicting chunks, and how much review each piece needs. The quality gate is you. The limiting factor isn’t the model — it’s your ability to keep pace with it.

Task-scale coding covers features, bug fixes, modules — the work that takes an agent twenty minutes to an hour. The architecture changes when the ambition scales to months-long migrations or building from scratch at hundreds of thousands of lines. Cursor published research in January on this problem, and their core finding is that single agents hit a wall at project scale. They tried flat peer coordination first — agents with equal status, self-organizing through a shared file. It failed. Twenty agents slowed to the effective throughput of two or three. Without hierarchy, agents became risk-averse, avoided hard problems, and churned without progress.

What worked was a planner-worker hierarchy: planner agents that decompose work into tasks (and can spawn sub-planners, making planning itself recursive), worker agents that grind on assignments until done, and a judge agent that evaluates each cycle. They pointed this at building a web browser from scratch — a research demo testing whether the coordination pattern could sustain coherent progress, not a shipping product — and the agents ran for close to a week, producing over a million lines of code across a thousand files. They migrated their own codebase from Solid to React over three weeks: 266,000 lines added, 193,000 removed. One unexpected finding: GPT-5.2 turned out to be a better planner than GPT-5.1-Codex, even though Codex was trained specifically for coding. They now use the best model for each role rather than one universal model.

At task scale, single-agent loop. At project scale, multi-agent coordination with explicit role hierarchies. Both are coding harnesses — different subspecies within the subspecies. But across both scales, the quality gate remains human judgment. The agents don’t validate themselves against holdout scenarios the way a dark factory does.

**The governing principle: decompose on boundaries of isolation.** Two agents on the same file will fight. Two agents on independent modules will compound. The human skill isn’t coding anymore — it’s triage. Knowing which output to scrutinize and which to accept. Karpathy calls it developing “muscle memory” for a new kind of work. It’s learnable. But it does need to be learned.


### Dark factories

The term comes from manufacturing — factories run entirely by robots with the lights off, because robots don’t need to see. Dan Shapiro published a five-level taxonomy of AI-assisted programming in January, borrowing from the NHTSA’s self-driving framework. Level 0 is spicy autocomplete. Level 5 is the dark factory. StrongDM built one.

Three engineers. July 2025. Charter: no human-written code, no human-reviewed code. Their CTO Justin McCarthy’s benchmark: “If you haven’t spent at least $1,000 on tokens today per human engineer, your software factory has room for improvement.”

Consider what they were building. Not a CRUD app. Access management and security software for enterprises — infrastructure that controls who can touch what across Okta, Jira, Slack, Google Drive. The kind of software where bugs have consequences. A team building security infrastructure decided that human code review is an obstacle, not a safeguard. Stanford Law’s CodeX program published an analysis two days after StrongDM went public, and zeroed in on exactly this: existing legal frameworks assume someone, somewhere, looked at the work. Here, nobody did.

A dark factory is not a coding agent doing your work while you review it. It’s an industrial process. Specifications go in. Working software comes out. The humans define intent — what the system should do, the scenarios it needs to handle, the constraints that matter. After that, the agents take over. They generate code, validate it against behavioral scenarios, and iterate until it converges. No human reads the code. The humans designed the system that designed the system.

I’ll be honest that the line between a project-scale coding harness and a dark factory gets blurry. If you get your project harness stable enough that you can do large runs without human involvement until the eval passes, you’re approaching dark factory territory. Think of it as a spectrum — the farther you push human involvement toward the beginning and end, away from the middle of the process, the closer you get. The distinguishing feature of a true dark factory is that the validation is fully automated. No human in the quality gate loop at all.

The critical innovation at StrongDM was treating validation like a machine learning holdout set. Traditional tests live in the codebase, which means the coding agent can read them and game them. StrongDM discovered this immediately — agents cheat. Not deliberately, but effectively. If a test checks whether a function returns a specific value, the agent will hardcode that value. `Return true` passes a narrowly written test beautifully. Their fix: borrow the holdout concept from ML. Store test scenarios outside the codebase where agents can’t access them during development. They call these “scenarios” rather than tests — end-to-end user stories validated by a separate LLM acting as evaluator. Success is probabilistic: across all simulated user trajectories, what fraction actually satisfied the user’s intent?

They paired this with a Digital Twin Universe — behavioral clones of third-party services like Okta, Jira, Slack, and Google Docs, running as self-contained Go binaries that replicate APIs, edge cases, and failure modes. Thousands of scenarios per hour. No rate limits. No API costs. No production risk. Building high-fidelity SaaS replicas used to be economically insane — generations of engineers may have wanted a full in-memory replica of their CRM to test against, but self-censored the proposal because they knew the answer would be no. Agentic development reversed that cost equation.

When Simon Willison visited the team in October 2025 — three months after founding — they already had working demos of the full system. Three people, three months. Their GitHub repo for Attractor, the core non-interactive coding agent, contains no code at all. Just three markdown files describing the spec in meticulous detail.

That’s the precondition most people miss. A dark factory doesn’t eliminate the need for engineering skill. It relocates it. The skill moves from writing and reviewing code to writing specifications precise enough that agents can converge without human intervention. If your team can’t produce specs at that level of detail, the dark factory pattern will produce precisely specified garbage. And if your domain doesn’t have verifiable behavioral scenarios — if you’re trying to produce a novel, where quality is subjective and there’s no holdout set that can tell you whether chapter seven works — you’ve picked the wrong architecture entirely. The dark factory requires a quality gate that doesn’t need human taste. Novels need human taste. That’s a mismatch at the foundation.

**The governing principle: the specification is the product.** Code becomes disposable. Specs become permanent. This inverts the normal relationship, and it’s why most teams aren’t ready — they’ve spent decades building skill in maintaining code and almost no time building skill in maintaining specs.


### Auto research

People keep conflating this with dark factories because it also involves agents running autonomously for extended periods. But the architecture is fundamentally different, and understanding why is the key to the whole taxonomy.

Here’s the simplest way I can frame it: is your problem software-shaped or metric-shaped? If you need to build a thing, that’s a coding harness or a dark factory. If you need to make an existing thing measurably better, that’s auto research. Once I put it that way, people usually know which one they have. And if you point auto research at building new software from scratch, you’re pointing a profiler at an empty file. There’s nothing to measure. There’s no gradient to follow. You’re not optimizing — you’re wandering.

Auto research is gradient descent scaled across problem spaces. The agent doesn’t produce software. It produces optimization. You give it a codebase, a metric, and boundaries. It brainstorms potential improvements, experiments with them one at a time, measures the result, keeps what works, reverts what doesn’t, and loops. The output isn’t a product. It’s a better version of whatever you pointed it at.

Karpathy built the canonical implementation — 630 lines of Python — as part of his nanochat project. He’d been training a GPT-2 model, had already tuned it extensively by hand over weeks using two decades of ML researcher intuition, and thought it was fairly well optimized. He let auto research run overnight. It came back with tunings he’d missed. The weight decay on value embeddings wasn’t right. His Adam betas weren’t sufficiently tuned. Critically, these changes interact — once you tune one parameter, the optimal setting for others shifts. That’s exactly the kind of combinatorial exploration that humans don’t have the patience for but machines do.

“I shouldn’t be a bottleneck,” Karpathy said on the No Priors podcast. “There’s objective criteria in this case. You just have to arrange it so that it can just go forever.”

That’s the key constraint. Auto research requires a computable metric. If you can’t score the output as a number, you can’t auto research it. Karpathy is explicit: writing CUDA kernels for faster inference? Perfect fit. Training a language model? Perfect — you have a validation loss and you want it lower. But anything softer — user experience, prose quality, design taste — falls outside the verifiable domain.

When Tobi Lütke ran auto research on Shopify’s Liquid codebase, the pattern held at a scale that made the implications impossible to ignore. Liquid is the template engine behind every Shopify storefront. It’s been tweaked by hundreds of contributors over twenty years. By any reasonable standard, already well optimized. Tobi gave the agent a benchmark script and 974 unit tests. Over two days: 120 experiments, 93 commits, zero test failures. The twenty-year-old codebase got 53% faster with 61% fewer object allocations.

What the agent found was instructive. It replaced the StringScanner-based tokenizer with String#byteindex — single-byte searching roughly 40% faster than the regex-based approach humans had used for years. It pre-computed frozen strings for integers 0 through 999, eliminating 267 redundant allocations per render. Each individual optimization was the kind of thing a senior Ruby engineer could have found. But finding all of them, in the right combination, across 120 experiments, while verifying zero regressions against 974 tests? That’s a search problem, not a skill problem. And search problems are what machines are for.

Notice the structure. Tobi wasn’t producing new software. He was optimizing existing software against a measurable objective. The agent didn’t need specifications or behavioral scenarios. It needed a benchmark, a test suite, and permission to experiment. Completely different preconditions from a dark factory.

Karpathy frames the boundary of what auto research can and can’t do through a simple observation: ask a frontier model to tell you a joke and you’ll get the same material you got three years ago. The models have improved tremendously on verifiable tasks, but humor lives outside the reinforcement learning loop. It’s not being optimized. It’s stuck. That jaggedness — superhuman on verifiable domains, mediocre on everything the RL boundary doesn’t reach — defines the ceiling. If the domain isn’t verifiable, the loop has nothing to optimize against.

OpenAI’s “North Star” is this pattern taken to its logical extreme. Jakub Pachocki, OpenAI’s chief scientist, told MIT Technology Review this week that they plan to build an autonomous AI research intern by September — a system you can delegate tasks that would take a person days. By 2028, they want a fully automated multi-agent research system targeting math, physics, biology, chemistry, and potentially economics and policy. Not producing software. Running experiments, forming hypotheses, evaluating results against quantitative objectives, and iterating. The target domains aren’t chosen because they’re the hardest problems — they’re chosen because they’re the most verifiable. Auto research doesn’t need general intelligence. It needs computable metrics and the ability to run experiments faster than humans can.

**The governing principle: metric plus guardrail.** Without a number to optimize, there’s no gradient. Without tests, the agent will “optimize” by deleting functionality — faster because it does less. You need both. If you have a robust benchmark and a comprehensive test suite and a human is still doing the optimization by hand, you should be asking why.


### Orchestration frameworks

DocuSign faced a workflow problem that none of the other three architectures could solve. Their sales reps were spending hours researching each prospect — reading company reports, checking recent news, pulling data from Salesforce and Snowflake — before they could draft a single personalized email. The problem wasn’t software-shaped (nothing to build), wasn’t metric-shaped (nothing to optimize against a benchmark), and wasn’t a coding problem. It was a pipeline problem: research feeds into composition feeds into validation feeds into delivery, and each step requires a different kind of intelligence.

They built a five-agent system on CrewAI Flows: an Identifier that qualifies leads, a Researcher that pulls prospect context from Salesforce and Snowflake, a Composer that drafts personalized outreach, a Validator that checks quality, and an Orchestrator that manages the sequence. The agents don’t run wild — they’re embedded in a deterministic flow that controls sequencing, handles errors, and manages state. Each agent gets context from the previous step. The Researcher feeds the Composer. The Composer feeds the Validator. Control always returns to the flow.

DocuSign A/B tested it rigorously: same customers, same time period, agent-generated outreach versus rep-generated. The agents matched or beat human reps on engagement metrics — open rates, reply rates, conversion — while cutting turnaround from hours to minutes. They’re now using the same architecture across multiple use cases beyond outreach. Their lead AI architect and lead data engineer presented the system at CrewAI’s Signal Conference in late 2025.

That’s what orchestration frameworks are for. CrewAI, LangGraph, AutoGen, OpenAI Agents SDK — these are middleware for coordinating LLM calls across multi-step workflows. The value proposition is coordination, not intelligence. The intelligence lives in the individual model calls. The framework provides structure for sequencing them, routing between them, maintaining state, and handling failures. CrewAI has over 45,000 GitHub stars, 100,000 certified developers, and real enterprise adoption powering over a billion agentic workflows. It works — for the problems it’s designed for.

Earlier I described Cursor’s planner-worker hierarchy for project-scale coding. That’s multi-agent coordination too — so how is it different from what DocuSign built? This is exactly where the confusion gets expensive.

The difference is what the coordination is doing. Cursor’s system coordinates agents around a shared codebase toward a unified goal — the intelligence lives in each agent’s deep reasoning about code. DocuSign’s system routes work through specialized roles in a sequence — each agent does its job and passes a defined output to the next. The value is in the pipeline structure, not in any single agent’s reasoning depth.

Multi-agent coordination isn’t wrong for coding — Cursor proved that at project scale. The question is whether the coordination pattern matches the problem. Coding problems need deep reasoning about code within a shared codebase. Workflow problems need agents that execute specialized steps and pass structured outputs between them. Reach for an orchestration framework when you have a workflow. Reach for a coding harness when you need reasoning depth.

One of the most reliable signals that someone doesn’t understand the current landscape is hearing them compare CrewAI to Cursor, or ask whether auto research could replace their dark factory pipeline, or describe their Cursor workflow as “orchestration.”

**The governing principle: design the handoffs first.** Each step’s output becomes the next step’s input. If the formats don’t match, the pipeline fails silently — the second agent processes garbage and returns confident-sounding garbage. Start with the schema of what flows between agents. Make the contracts explicit. Validate at every step. The framework is plumbing. The contracts are what make it reliable.


## The decision framework

The four architectures are defined by where the verification happens and who does it. Every architecture is a different answer to the same question: how do you know the agent’s output is good?

When someone says “we should use agents for this,” one question resolves the ambiguity: what are you optimizing against?

Each answer maps to a different architecture. Here's the cheat sheet:

[![](https://substackcdn.com/image/fetch/$s_!81yl!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe8e97149-d6cb-4b9a-bd1f-8067bd464ad4_1158x1118.png)](https://substackcdn.com/image/fetch/$s_!81yl!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe8e97149-d6cb-4b9a-bd1f-8067bd464ad4_1158x1118.png)

The table maps the clean version. The next section shows what happens when people get it wrong.


## The Karpathy test

Karpathy described the state of the field as “AI psychosis” — the feeling that capability is expanding faster than anyone can map it, that everything is possible and everything is skill issue. He’s right. But the psychosis gets worse, not better, when you treat everything as one undifferentiated blob of “agents.”

I’ve watched this confusion cost real money. A team spends three months building a CrewAI pipeline for code generation when they needed Claude Code and a testing harness — three months of orchestration overhead on a problem that required one agent with good tools. A PM writes a roadmap for “autonomous research capabilities” and the engineering team builds an auto research loop, except the domain has no computable metric, so the loop runs experiments that can’t be scored and produces nothing useful. A founder pitches a “dark factory for content” without understanding that content quality is precisely the kind of thing you can’t validate with a holdout set — which is why Karpathy puts it outside the RL boundary.

Same root cause every time. The person making the decision couldn’t distinguish between the four architectures, so they pattern-matched on the word “agents” and picked the one they’d heard about most recently.

The cure for psychosis is taxonomy. Name the things. Draw the lines. When someone says “let’s use agents,” hear the incomplete sentence — like hearing “let’s use a vehicle” without knowing whether they mean a forklift, a sedan, a cargo ship, or a bicycle. The right response isn’t “great idea” or “agents are overhyped.” The right response is: what are you optimizing against?

Four architectures. One question. Start there.

[![](https://substackcdn.com/image/fetch/$s_!AFzN!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe47d3ed0-54f7-42fa-883f-e08d4d60e4bb_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!AFzN!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe47d3ed0-54f7-42fa-883f-e08d4d60e4bb_1024x1024.png)
