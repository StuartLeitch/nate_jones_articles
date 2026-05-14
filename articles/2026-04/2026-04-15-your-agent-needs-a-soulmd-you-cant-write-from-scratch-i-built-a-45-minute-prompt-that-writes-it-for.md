---
title: "Your agent needs a SOUL.md you can't write from scratch. I built a 45-minute prompt that writes it for you."
author: "Nate Jones"
published: 2026-04-15
url: https://natesnewsletter.substack.com/p/your-agent-needs-a-soulmd-you-cant
audience: everyone
scraped_at: 2026-05-14 14:33:34
---

The most expensive problem in the agent space right now isn’t infrastructure, model selection, or security. It’s that the people adopting these tools can’t describe what they actually do all day — not in the resolution an agent needs.

OpenClaw has 250,000 GitHub stars. Jensen Huang compared it to Linux. Meta bought Manus for $2 billion, Nvidia shipped NemoClaw, Anthropic shipped Dispatch, Perplexity built a dedicated hardware product around the concept. A thousand engineers lined up outside Tencent’s headquarters in Shenzhen to get it installed on their laptops. The install problem is solved — you can have a personal AI agent running on Telegram in the time it takes to make coffee. And the most common message in every agent community after a successful setup is three words long: “Okay... now what?”

That’s not a tech support question. It’s what happens when you sit down to delegate and realize you’ve never described your own work in the resolution anything else can act on — human or machine. I’ve been reading those threads for months. The install goes fine, the first task goes fine — and then the agent sits there waiting for instructions the human doesn’t know how to write. There’s a structural reason for that, and it matters for your career whether you ever touch an agent or not.

**Here’s what’s inside:**

- **The 40-hour wall.** What actually happens when people try to spec their own work for an agent — and why every product in the space skips this step.
- **The expertise trap.** The more senior you are, the less visible your own operating system becomes to you. That’s not a character flaw — it’s the intended outcome of how expertise develops.
- **The career problem hiding inside the agent problem.** Delegation failures, promotion ceilings, and institutional knowledge loss all trace to the same root cause.
- **What to do about it.** The first agent worth running isn’t an assistant. It’s an interviewer — and I’ve built one.

The agent revolution has a prerequisite nobody’s selling. This piece is about the prerequisite.


## **LINK: [Elicitation Workflow](https://github.com/NateBJones-Projects/OB1/tree/main/recipes/work-operating-model-activation)**

This is a structured elicitation workflow — an AI interviewer that walks you through five layers of how your work actually runs, one conversation at a time, with checkpoint approvals between each layer so nothing gets saved that you haven’t confirmed. When it’s done, it generates the operating artifacts every agent platform needs but none of them help you create: operating-model.json, USER.md, SOUL.md, HEARTBEAT.md, and schedule-recommendations.json. If you’ve built [Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres), the output feeds directly into your knowledge store as structured data agents can query. If you haven’t, the files stand on their own.

You can start it cold right now. But keep reading first — the rest of this piece explains why you’ll stall partway through if you don’t understand what’s actually happening when you try to describe your own work, and why this tool was designed the way it was.


## The cold start problem nobody will name

A developer named Brad Mills spent 40 hours building a delegation framework for his OpenClaw agent. Not 40 hours installing — the install took 10 minutes. He spent 40 hours writing standards, accountability rules, and a definition of done for a single project: transcribing 200 hours of video into a searchable knowledge base. Forty hours of trying to describe what he wanted clearly enough for the agent to act on it. And it still didn’t work.

“Constant failure,” he wrote. “Fail after fail after fail. 2 steps forward 1 step back.” He ended up micromanaging the agent harder than he’d micromanage a human. The autonomy everyone promises felt, in practice, like a second job supervising something that confidently reports tasks complete when it hasn’t started them.

Brad isn’t an outlier. He’s closer to the median than the agent community wants to acknowledge. One prominent OpenClaw guide creator reports getting flooded with DMs that all say the same thing after setup. The stuck point isn’t installation, it’s figuring out what to actually do with the agent and how to make it understand your specific context. Another user asked his agent to write five cold email variants. The agent said “Done” and had written nothing. His solution: build a second “adversarial auditor” agent whose only job was to verify the first agent completed its tasks. He needed a management layer because the worker couldn’t be trusted to self-report, and the root issue was that the task spec wasn’t clear enough for the agent to self-verify.

When one user tried rolling out agents to a team, he gave everyone access and called it done. “It technically worked,” he said. But it was useless because nobody had mapped their workflows, decisions, or data needs. Without that upstream work, the agent stayed generic. And a generic agent with write access to your email is worse than no agent at all, it’s a liability with a chat interface.

There’s a guy on X selling a $49 pack of pre-written configuration files (SOUL.md, HEARTBEAT.md, USER.md, the whole stack) specifically marketed to “skip 40 hours of OpenClaw setup.” Someone built a small business around the gap between “installed” and “useful.” Forty hours. Of trying to describe your own job.


## What successful setups look like

Before we get into what’s broken, let’s look at what works. Because there is a pattern. Across hundreds of thousands of OpenClaw installations, the deployments that stick, the ones where people are still getting daily value weeks and months later, share a specific architecture. And it has almost nothing to do with which model they picked.

The successful setups all have a set of markdown files that function as the agent’s operating system. If you open the `.openclaw` directory on anyone running a working agent, you’ll find the same structure: SOUL.md defines the agent’s role, tone, and boundaries, basically a job description. IDENTITY.md is the name and personality constraints. USER.md is a detailed profile of the human, including preferences, schedule patterns, communication style. HEARTBEAT.md is a checklist the agent reviews every 30 minutes to decide if there’s work to do. And a cron schedule that maps to the human’s actual operating rhythm.

None of this is technically difficult, it’s all plain text, but the quality of those files determines everything.

The people who run multiple specialized agents, not one do-everything bot, but a team with clear roles and scoped access, are the ones who report the strongest results. One well-known setup runs nine agents across personal and professional life: a personal assistant on email and calendar, a family manager tracking kids’ schedules and logistics, a marketer scanning social media and drafting content, a sales agent qualifying inbound leads and sweeping the CRM, a helpdesk bot triaging support tickets, a podcast producer managing guest pipelines, a developer picking up Linear tickets and opening PRs, and a course operator project-managing a launch. Each agent has its own identity, its own tools, its own workspace. They don’t share context. They have clear jurisdictions.

The multi-agent pattern shows up everywhere the tool is working. People running specialist bots in Slack that delegate to each other like actual coworkers, where someone asks a question, the orchestrator agent decides which specialist handles it, and the conversation never leaves the team channel. A five-model “R&D council” that meets twice daily at 9am and 5pm, where five different models review products and content, debate growth ideas with one rotating as idea generator and the rest as critics, then output a memo with next steps. The human just approves. A full ad creative pipeline where you drop a brand URL into Telegram and the agent does brand analysis, strategy, copywriting, generates five creative variants, and logs everything with images to a Google Sheet. These are not toy demos. They run daily, and the people running them report that the second agent deploys 10x faster than the first, because the hard work was learning to describe the job, not learning the tool.

There’s another pattern worth naming: the file-system-as-brain architecture. The most successful deployments treat the `.openclaw` directory like an evolving codebase. SOUL.md isn’t written once and forgotten. It gets edited as the human discovers what the agent handles well and what it doesn’t. MEMORY.md accumulates institutional knowledge over time. You can literally `cat MEMORY.md` and watch context build up like a work journal. Skills folders contain modular procedural knowledge that the agent can reference: how to do research, how to write copy, how to run a specific type of analysis. People are putting these directories under version control, treating their agent’s brain like a git repo with commit history. It’s software engineering applied to natural language, and it works because it makes the agent’s behavior auditable and improvable.

What ties all of these together: every one of these setups required the human to do something rarely attempted. They had to sit down and describe, in specific, triggerable, verifiable language, what they actually do all day. Not in generalities like “I handle marketing” or “I manage the family schedule,” but in actual conditional logic: “Every Friday, group message me and my husband to confirm the kids’ weekend activity logistics. If there is a conflict, confirm who will pick up each kid and any adjustments we need to make to lunch or dinner plans. Ask us to explicitly confirm the plan and update our shared family calendar.”

That’s the resolution an agent needs. And producing that resolution requires an act of self-knowledge that few professionals have ever attempted. They’ve never had a reason to. Until now.

There’s a reason the earliest OpenClaw success stories came overwhelmingly from engineers. Peter Steinberger built OpenClaw for developers, and developers have a professional habit that sets them apart from other knowledge workers: they’re trained to demand specifics about inputs, expected outputs, and edge cases before they write a line of code. That discipline translates directly to writing good agent configuration files. The challenge, and the opportunity, is that OpenClaw has outrun its original audience. It’s no longer a developer tool. It’s a consumer product, and the people adopting it fastest are the ones least practiced at decomposing their own workflows into explicit instructions.


## The me-too wave and what they’re all missing

The industry’s response to this moment has been predictable. Everyone is building agents. Nobody is building the prerequisite — the step where the human sits down and produces a usable description of their own work. Every product in this wave competes on the implementation layer: installation, UI, model selection, security, pricing, cloud versus local. And every one of them breaks against the same wall.

**OpenClaw** is the open-source original: 250K GitHub stars, runs locally, connects to any LLM, infinitely configurable. The cold start problem is entirely on you.

**Manus**, now owned by Meta for $2 billion, takes the opposite approach — you describe a goal in plain language and Manus decomposes it into subtasks. It works well for simple, bounded tasks like research and report generation. But it struggles the moment workflows get complex, personal, or recurring, because it has no persistent model of who you are, how your work flows, or what “done” looks like in your specific context.

**Perplexity Personal Computer** is the most audacious brand play in the space. A dedicated Mac Mini running a “Computer” orchestration layer that routes tasks across 20 frontier models. CEO Aravind Srinivas framed the pitch at their Ask 2026 developer conference: “A traditional operating system takes instructions. An AI operating system takes objectives.” It’s $200/month, waitlist-gated, and Perplexity claims it completed 3.25 years of enterprise work in four weeks during internal testing. The security posture is tighter than OpenClaw, but the fundamental bet is the same: you state an objective, and the system figures out the rest. Which works right up until the objective requires knowledge about your life, your judgment patterns, and your operating rhythm that no system has, because you’ve never written it down.

**NemoClaw** is Nvidia’s enterprise security wrapper for OpenClaw — sandboxed environments, OpenShell for privacy guardrails, hot-swappable security rules, and a partner list that includes Salesforce, Cisco, Google, Adobe, and CrowdStrike. It solves the security problem, which is real and serious. It does not solve the problem of what to put in the agent’s operating instructions.

**Claude Dispatch** is Anthropic’s answer. Scan a QR code, pair your phone with your Mac, and Claude becomes a persistent agent you can text from anywhere while it executes on your desktop. It’s cleaner, safer, better integrated than the open-source alternatives. I tried the obvious workaround with one of the text-first agent apps: I wrote fifteen paragraphs of context about my role, my workflows, my decision patterns, the full download. It produced nothing useful. Fifteen paragraphs, and the agent still couldn’t act on any of it, because a wall of unstructured text is not operational knowledge. The volume was there. The architecture wasn’t.

**The hosted wrappers** (StartClaw, MyClaw, SimpleClaw, UniClaw, and a dozen more launching every week) are solving installation friction, which is a real UX problem. But the guy selling a $49 pack of pre-written SOUL.md and HEARTBEAT.md files is selling something much more interesting, because he’s addressing the actual bottleneck: people don’t know what to put in those files.

That wall isn’t a product bug. It’s a structural property of how expertise works.


## Why knowledge workers can’t spec their own work

I want to go deeper than “people can’t describe what they do,” because that observation, while true, doesn’t explain the mechanism. And if you don’t understand the mechanism, you’ll waste time on solutions that don’t address the root cause.

Knowledge work has a structural property that makes it uniquely resistant to delegation, human or machine. The property: **the more senior and valuable you become, the more your work migrates from explicit processes to tacit judgment, and the less visible your own operating system becomes to you.**

This isn’t a failure of self-awareness. It’s the intended outcome of how expertise develops. When you’re a beginner, everything is conscious and deliberate. You follow checklists. You think through each step. As you gain expertise, those steps compress into automatic patterns. Think about learning to drive. The first year, every lane change is a conscious sequence: mirror, signal, shoulder check, turn the wheel, accelerate. After a decade, you merge on a freeway while holding a conversation and adjusting the climate control. You don’t think about the steps anymore because they’ve been compiled into something faster than conscious thought. Knowledge work follows the same compression curve. You stop thinking about what to check and just check it. You stop reasoning through decisions and just make them. The thing that makes you fast and effective is the same thing that makes your knowledge inaccessible: it’s been compiled from source code into machine code, and you no longer have the source.

A senior product manager doesn’t think “I should cross-reference the revenue dashboard with the churn data before forming an opinion.” She opens three tabs, glances at numbers, and knows. Ask her what she checked and she’ll reconstruct something plausible, but she’s narrating backwards from the conclusion, not describing the actual process. The real decision involved a hundred micro-evaluations she’s never articulated to anyone, including herself. The pattern-match that told her the churn number was off. The instinct to check whether the feature request came from a high-LTV cohort. The contextual awareness that Q2 numbers always look worse than they are because of a billing cycle artifact nobody documented.

A strong salesperson doesn’t consciously decide to mirror their prospect’s phrasing and slow their cadence when they detect defensiveness. They just do it. A senior engineer doesn’t think “this code has a concurrency issue that’ll surface under load on Tuesdays when the batch job overlaps with peak traffic.” They feel it. Then they go look, and they’re right, and everyone calls it experience.

This is worth lingering on because it’s the root cause of a product failure happening at massive scale. The entire agent ecosystem is built on a model where the human provides instructions and the machine executes them. That model works when the instructions are explicit: “summarize this document,” “translate this email,” “reformat this spreadsheet.” It breaks completely when the instructions require expertise the human possesses but cannot articulate. And most valuable knowledge work lives in that second category.

Think about what a good SOUL.md actually contains. It’s a decision framework, not a personality description: when to escalate versus handle autonomously, what tone to use with different audiences, which data sources are authoritative versus advisory, what “good enough” looks like for different task types. That’s the same thing a strong VP would put in an operating memo for their team, and few VPs have written it either, for exactly the same reason. The judgment lives in their head, gets applied in real-time, and produces results. Why write it down? Because now something needs to read it that doesn’t have your 15 years of context.

It’s also the same reason senior engineers write terrible onboarding docs. Not laziness. The knowledge that would make the doc useful has been compressed into automatic behavior. The doc lists the steps but misses every nuance. An agent configured by the same person ends up in the same state: technically correct instructions that miss everything that makes the work actually work.

The structural trap: **the people with the most to gain from agent delegation are exactly the people whose work is hardest to delegate.** The most senior, most overloaded knowledge workers carry the highest ratio of tacit-to-explicit knowledge. Their work is the most compressed, the most invisible to themselves. They need the advantage most. The cold start problem hits them hardest.

Junior people, ironically, are closer to being agent-ready. Their work is still explicit. They still follow checklists. They can tell you exactly what they do because they’re still consciously doing it. It’s one reason companies like Shopify have leaned into hiring junior talent for AI-augmented roles — their work hasn’t been compiled yet. But they’re also the people with the least to delegate, they’re still learning the judgment calls that would make delegation valuable.

If you plotted it on a graph, two curves would emerge. The value of delegation increases with seniority, and so does the difficulty, for the same reason. The intersection sits somewhere mid-career: senior enough to have meaningful work to hand off, not so senior that your entire value proposition is compiled intuition.

And the exercise of decompiling your expertise doesn’t just enable delegation. It changes how you see your own work. People who go through this process come out saying “I didn’t realize I spend four hours a week on something that doesn’t matter” and “I never noticed my entire Monday depends on a single email from finance that arrives at a random time.” Making your work visible to an external system makes it visible to you. Visibility is the prerequisite for improvement, not just delegation.


## Why this problem is bigger than agents

The inability to externalize operational knowledge is the root cause of at least three chronic problems in every organization I’ve ever worked in:

**Delegation fails.** Managers cite it as a top challenge. The standard explanation is that they’re control freaks. The structural explanation: they can’t describe what they do in enough detail to transfer it. “Handle the weekly report” is a delegation instruction containing zero usable information. The manager knows what “handle” means, which data to pull, which comparisons matter, what the skip-level actually wants versus what they say they want, which anomalies are real and which are artifacts of the reporting tool. The recipient doesn’t know any of that. Neither does the agent. And the manager can’t easily tell them because they’ve never decomposed “handle” into its component operations.

**People can’t get promoted.** The most common reason strong ICs plateau is that they can’t be replaced. Their knowledge is locked in their head. Moving them up creates a hole. Every promotion framework talks about “scaling your impact beyond yourself.” What that requires is making your work legible enough for someone else to do it, the exact same exercise an agent demands.

**Institutional knowledge evaporates.** People leave. The unwritten rules, the contextual judgment, the “we tried that in 2019 and here’s why it failed but it might work now because the vendor changed their API,” it walks out the door. Companies spend millions on knowledge management after the fact. It rarely works, for the same structural reason agents stall: the knowledge is tacit, extracting it requires skilled facilitation, and by the time someone thinks to capture it, the person is already halfway gone.

Agents didn’t create these problems. But agents create the first universal, selfish incentive for every knowledge worker to fix them. Not from HR launching a knowledge management initiative or a consultant running a workshop. Because you personally want a robot to stop asking you to confirm calendar entries you already approved, and the robot needs you to describe your calendar rules first.

That’s new. We’ve had decades of top-down pressure to externalize knowledge. It never worked at scale because there was no direct personal upside for the individual. The benefit accrued to the organization, not the person doing the documentation. Agents flip that incentive structure completely. The person who documents their expertise is the person who gets the compound returns. The organization benefits secondarily. It’s a bottoms-up knowledge management revolution disguised as a consumer AI product, and I don’t think anyone, including the people building these products, fully appreciates that.

There’s an uncomfortable corollary worth naming. If the value of agents depends on your ability to articulate your work, agents are about to create a very visible divide. Right now, tacit knowledge is invisible. Nobody knows you can’t describe your own process because nobody asks. Performance reviews measure outputs, not self-knowledge. You can be a phenomenal operator with zero ability to explain how you operate, and the system never penalizes you.

Agents change that. In a world where everyone has access to the same tooling, the differentiator isn’t which model you use or how many Mac Minis you stack. It’s whether you can feed the thing well enough to get real returns. The people who invest the time, who decompose their expertise into explicit, delegatable components, will get compounding advantages. Their agents improve because their specs improve. The second agent deploys faster than the first. The tenth deploys in an afternoon.

The people who skip it will install, play for a weekend, hit the wall, and conclude agents are overhyped. They’ll be wrong. The agent worked fine. The problem was upstream of the agent the entire time.


## **The first agent you should run isn’t an assistant**

So here’s the question: if the bottleneck is self-knowledge, and self-knowledge is genuinely hard to produce alone, what do you actually do about it?

You use the tool to prepare for the tool.

The first agent worth deploying isn’t a personal assistant, a morning briefing bot, or a calendar manager. It’s an interviewer. One designed to do what expertise elicitation researchers do: ask you the right questions, in the right order, with the right follow-ups, to extract the operational knowledge you carry but can’t easily access on your own.

That’s what the workflow at the top of this piece is. Not another agent wrapper — the layer upstream of every wrapper. A structured, conversation-first elicitation that walks you through five layers in order: your operating rhythms (what your days, weeks, and months actually look like — not the calendar version, the real one), your recurring decisions (what judgment calls you make and what inputs you need), your dependencies (who you need things from and when), your institutional knowledge (what you know that nobody else on your team knows), and your friction (the recurring annoyances that eat your time). After each layer, you review and approve a checkpoint summary before anything gets saved. Nothing is inferred behind your back. It takes about 45 minutes.

The output is not a transcript you’ll file and forget. It gets stored as structured Open Brain data that agents can query later, while also writing a small number of durable summary memories back into the core brain — the personal knowledge store we published earlier this year, where everything becomes searchable and available to any agent that speaks MCP. When the interview is complete, it generates the actual operating artifacts agent systems need: operating-model.json, USER.md, SOUL.md, HEARTBEAT.md, and schedule-recommendations.json. Brad Mills’ 40 hours. The $49 config-file pack. The gap that Manus, Perplexity, NemoClaw, and Dispatch all skip over — built from your answers, not your guesswork.

It’s practical in the ways that matter. You can stop mid-interview and pick up where you left off. The system distinguishes confirmed facts from patterns it synthesized, so you always know what’s verified and what’s provisional. Exports are stored server-side, so it works even if your client can’t write local files.

But honestly, the configuration files are the least interesting output. The more valuable artifact is the structured map of how you actually work — what you know, where your leverage points are, which decisions you make on autopilot, and which dependencies you’ve never noticed. That map is the missing step between “the agent is installed” and “the agent is useful.” It turns tacit work into explicit structure. It makes you better at delegating to humans. It makes you easier to promote. It makes your expertise survivable. And yes, it makes your agents work.

If you’ve built [Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres) from the earlier guide, this is the activation layer. If you haven’t, start there. The elicitation workflow is more powerful with a persistent store underneath it, but it stands on its own.

- LINK: [Elicitation Workflow](https://github.com/NateBJones-Projects/OB1/tree/main/recipes/work-operating-model-activation)

Every agent product in the market today competes on the implementation layer — installation, UI, model selection, security. None of them touch the prerequisite. The prerequisite is: can you answer a question that sounds simple and isn’t?

What do you actually do all day?

The first agent worth running is the one that helps you find out.

[![](https://substackcdn.com/image/fetch/$s_!TiVt!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F75827047-0510-43f2-9436-8713b78f0bf2_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!TiVt!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F75827047-0510-43f2-9436-8713b78f0bf2_1024x1024.png)
