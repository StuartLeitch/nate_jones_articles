---
title: "Claude vs. Codex isn't about code. It's about whether you steer or dispatch."
author: "Nate Jones"
published: 2026-06-10
url: https://natesnewsletter.substack.com/p/claude-code-vs-codex-agents
subtitle: "Watch now | Everyone treats Claude Code and Codex as rival coding tools. They are really teaching us two different ways to manage machine work: stay close and steer, or write the assignment and dem..."
audience: everyone
scraped_at: 2026-06-10 12:00:18
---

The strange moment is not when an AI answers you.

We have gotten used to that. You type something into a box. A model writes back. Sometimes it is useful. Sometimes it is nonsense. Either way, it still feels familiar. You asked. It answered. You are sitting there, judging the response in real time.

The strange moment is when an AI comes back with work.

It read the folder. It edited the file. It ran the command. It compared the sources. It says it is done.

And now you have a new problem. You did not do the work. You may not have watched every step, or know which assumptions it made, which branch of the task it abandoned, or which shortcut it took because the shortcut made the answer look cleaner. But the work is sitting in front of you.

Is it real?

That question is the real Claude Code versus Codex story, and almost nobody frames it that way. Everyone wants to know which tool is better, which model is smarter, which writes cleaner code, which wins the benchmark. Fair questions. They are not the main event.

These tools are training us to manage AI labor, and they train us to do it differently. Claude teaches you to steer agents. Codex teaches you to dispatch them. That sounds like a workflow note. It is deeper than that. Use one long enough and it changes what you reach for when a problem lands: another conversation, or a better assignment.

I run into this every working day. Getting the machine to do work is the easy part. The hard part is deciding when the work is good enough to leave the machine. That decision is going to define a lot of white-collar jobs, and not because everyone will learn to code. More people are simply going to start receiving work from machines they did not supervise. The first time it happens, it feels like magic. The tenth time, it feels like management.

That is why these tools matter even if you never write code. They showed up in software first because code has clean feedback loops, but the habit is already spreading into research, sales notes, spreadsheets, legal summaries, support triage, and every kind of knowledge work that lives in files and messages. Neither one is really just a coding tool anymore. The useful question is what kind of AI worker each tool is training you to become, and those habits will outlast this month’s leaderboard.

**Here’s what’s inside:**

- **The two ways agents fail you.** Understanding theater, where a good conversation convinces you the work was understood, and completion theater, where a finished run feels far more done than it is.
- **The jargon, decoded.** Context, permissions, worktrees, hooks, and proof stop reading like programmer-speak and start reading like the moving parts of any assignment you hand a machine.
- **Why the real test comes after the output.** A head-to-head where both agents reached the same result in completely different ways, and what that says about trusting work you did not watch happen.
- **The standard I would teach everyone.** The five shapes every agent run takes, the six questions to answer before you launch one, and the cost almost nobody budgets for.
- **Four prompts you can paste today.** A Run Spec that turns a fuzzy task into a bounded assignment, a steer-or-dispatch diagnostic for when you cannot tell which the work wants, an “is it real?” audit for work an agent hands back, and a cross-check that makes one agent grade another.

Let me show you how each tool trains you, where each one fails, and the standard I use to keep the work honest.

*If you experience issues joining Slack, please email **support@natebjones.com** for help and we’ll get you sorted within 48 hours of your request.*


## ***[LINK: [Join the Slack →](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)]***

*The Slack community is live! It’s where I’ll be sharing things between articles, where you can get help on builds in real time, and where the fastest conversations in this community are already happening. I’ll see you in there!*


## ***[LINK: [Grab the prompts](https://promptkit.natebjones.com/20260607_b5e_promptkit_1)]***

Here are the prompts before we go further. I built four because agreeing with an idea is easy and using it under pressure is hard. When a real task lands, the pull is to start typing, not to stop and define the run.

The Run Spec turns a fuzzy task into a bounded assignment and forces the six decisions this piece ends on, including the one most people skip: how much of your own review time the result is worth. The Steer-or-Dispatch Diagnostic tells you whether the work wants closeness or distance, so you stop reaching for a tool out of habit. The “Is It Real?” Audit is for the moment an agent says it is done, the exact moment completion theater and understanding theater are hardest to catch. The Cross-Check makes one agent grade another, so the agent that produced the work is never its only judge.

Each one asks a short batch of plain questions and then stops. No jargon required.

---

The split is not abstract for me. Claude changed how I think with AI first. Codex changed what I was willing to hand to the computer. They are different enough that I do not want to blur them together under one lazy phrase like “AI agents.”


## Chat taught us to ask. Agents teach us to manage.

The first era of generative AI trained us to ask better questions.

That was useful. People learned how to describe what they wanted, add context, ask for alternatives, revise tone, request summaries, and push back on bad answers. The center of gravity was still the exchange. You asked. The model answered. You judged the answer.

The agent era changes the unit of work. What used to be a single chat conversation is now an agentic run.

A run has a goal. It has context. It has a permission boundary. It has tools. It has instructions or memory. It has a place where the work happens. It has artifacts. It has failure modes. It has a review burden. It has proof, or it has vibes.

This is why the vocabulary matters, even though it sounds like programmer talk.

A context window is what the agent can keep in working attention. If you fill it with stale assumptions, irrelevant files, old mistakes, and half-correct corrections, the agent gets worse. Context is the attention budget for the run, not a junk drawer for whatever might be relevant.

A permission mode is what the agent can do without stopping to ask. Reading a file is different from editing one. Editing is different from running a command. Running commands is different from controlling your screen. Controlling your screen is different from sending, publishing, deleting, deploying, or spending money.

A worktree is a separate copy of the work. In ordinary terms, it is a contained version where an agent can try something without damaging the main version.

A hook is an automatic checkpoint. Before you say you are done, run the test. Before you finish the document, render it. Before you touch this folder, stop and ask. Before you merge, show the diff. Hooks matter because a rule that lives only in the model’s memory is a rule the model can forget.

MCP, plugins, and connectors are reach. They let the agent interact with the systems where work lives: GitHub, Google Drive, Slack, a calendar, a database, a browser, a file system, a ticketing tool, a design tool. It is tempting to treat them as a way to feed the agent more facts. Their real job is to set a capability boundary. What can the agent reach? What can it change? What credentials and state travel with that access?

A skill is reusable method. It is the difference between explaining your editorial standard every time and giving the agent a playbook it can load when the job calls for it.

A subagent is thinking space. It is a way to send a narrow worker to read logs, inspect a folder, compare sources, review a draft, or test an objection without stuffing the main thread with noise.

A sandbox is a boundary. It is a technical fence around what the agent can touch, not a substitute for judgment.

Proof is the receipt: a diff, a test result, a source list, a rendered document, a screenshot, a package validation, a log, a comparison table, or a second-agent review. It is something you can inspect that is not merely the agent’s confident final paragraph.

The new literacy is learning how those pieces fit together. Skills are what the agent knows. MCP and plugins are what the agent can reach. Subagents are where the agent thinks. Hooks, permissions, sandboxes, approvals, and auto-review are what the agent must obey. Artifacts, logs, diffs, tests, screenshots, source lists, and rendered files are how the agent proves what happened.

Once you see that stack, Claude versus Codex stops being a brand fight. It becomes a question about how each tool teaches you to compose a run.

Which part of the stack does it make obvious, and which does it hide? Which mistakes does it make easy to miss? Which kind of judgment does it strengthen, and which does it wear down?

This is the lens I want to use here. Claude and Codex are not just competing products. They are two schools for managing machine work.


## Claude is the school of staying close

Claude Code feels like a cockpit.

That metaphor can sound dramatic, but the point is simple: you are close to the work while it is happening. You can ask the agent to read the project and tell you what is going on. You can make it interview you before writing a plan. You can stop it, redirect it, challenge it, ask it to compare options, or say that something feels wrong before you can fully explain why.

That closeness matters.

A lot of important work is not ready to be delegated when it first appears. You do not always know what the assignment is. You think you need a rewrite, but the real issue is a missing source. You think you need a bug fix, but the real issue is a product decision. You think you need a new dashboard, but the real issue is that nobody has agreed on the metric. You think you need a prompt, but the real issue is that you have not decided what good means.

If you dispatch too early, you get a machine efficiently solving the wrong problem.

Claude is strong in the phase before the job is fully defined. That is why people reach for it in writing, architecture, product thinking, design judgment, ambiguous debugging, strategy, and planning. It feels like a place where the problem can become clear.

This is why Claude mattered to me before Codex did. Claude was the first AI product that consistently made me feel like I could bring a half-formed thought into the room and not have to apologize for it. I could say, “something is off here,” and use the conversation to find what was off. For writing and strategy work, that is not a side benefit. That is often the work.

The model matters here, but the harness matters too. Claude Code has grown well past a single terminal window. You can make it plan before it touches anything, hand it a standing set of project instructions it reads on every run, give it reusable methods, wire in automatic checkpoints, and send narrow workers off to investigate without cluttering the main thread. It now follows you across the terminal, the editor, the browser, Slack, and your phone, and it keeps working in the background after you have walked away.

The feature list matters because of the behavior it invites.

Claude invites you to stay with the agent while judgment is still forming. Its subagents can run in separate context windows. Its hooks can enforce checks around lifecycle events. Its agent-team and dynamic-workflow direction points toward richer coordination among multiple workers. The tool is moving toward a programmable environment for agent thinking.

That matters because the hardest part of work is often not doing the obvious next step. It is discovering the real next step.

The same strength creates Claude’s danger.

Claude can make understanding feel more complete than it is.

A good Claude session can be deeply persuasive. The model sounds thoughtful. It concedes the tradeoffs. It adapts when you correct it. It reflects your framing back to you in a way that feels aligned. The work feels close because the conversation feels close.

Then the artifact is wrong.

The source was missing. The test did not run. The plan carried forward a false assumption. The context got polluted by earlier corrections. The agent silently relaxed a constraint because the relaxed version made the answer cleaner. The conversation made you feel like the work had been understood, but understanding was never proven.

The first failure mode is understanding theater.

It is not unique to Claude, but Claude’s strength can make it easier to fall into. If the interface teaches you to stay close, the risk is that closeness itself starts to feel like evidence.

Good Claude users learn how to resist that. They use plan mode before execution. They keep project instructions clean. They use hooks for checks the model should not be trusted to remember. They isolate research in subagents. They ask for independent critique. They clear or compact context when the conversation becomes stale. Eventually, they stop talking and demand proof.

Claude teaches steering, but mature steering is not endless conversation. It means knowing when conversation is the right work surface and when the work has to leave the conversation and become inspectable.


## Codex is the school of sending work out

Codex feels more like an operations desk.

The natural motion is different. You do not keep one long conversation alive forever. You split the work into runs: one thread reads the folder, another drafts the document, another checks the package, another opens the browser, another validates the output, another turns the repeated task into a skill, and another reviews what came back.

The job has a boundary. The result has a file path. The run has a summary. The work queue is visible. The proof is supposed to come back with the artifact.

That trains a different mind.

Codex rewards people who can write clean assignments. Goal. Context. Constraints. Done when. Source of truth. Allowed files. Forbidden actions. Escalation rule. Verification. It pushes you to turn a fuzzy wish into a bounded job.

This is why Codex feels bigger than coding to me. My bottleneck is often not whether I can think about a task. My bottleneck is moving work across the computer. Find the transcript. Read the source. Compare it to the draft. Render the document. Open the site. Inspect the file. Check the package. Copy the output to the right location. Verify it exists. Produce a source list. Do it again tomorrow.

That is ordinary knowledge work, dressed up as a coding problem.

This is where Codex got personal for me. It made me stop thinking of AI as a place where I go for help and start thinking of my computer as a place where work can be delegated, checked, packaged, and continued. That sounds abstract until you have five small, annoying jobs sitting between you and a finished artifact: find the current file, compare it to the transcript, make sure the document renders, put it in the right folder, and verify the handoff path. None of those jobs are glamorous. Together, they are a large part of getting real work out the door.

OpenAI’s Codex is clearly moving into that world too. It can drive a browser, run jobs in the background, turn a repeated thread into a standing automation, and reach into documents, dashboards, research, design, and operations that have nothing to do with writing code. Its safety model is built around boundaries you set before the run: what the agent may touch, when it must stop and ask, what gets checked automatically, what it can reach over the network, and what an organization can lock down centrally.

Again, the feature list matters because of the habit it builds.

Codex teaches you that AI work can be assigned, separated, run in parallel, checked, and continued. It makes the computer feel less like a place where you ask for help and more like a place where jobs can be launched.

Once you use it enough, you start to see work differently. A folder becomes a work surface. A source list becomes a trust object. A screenshot becomes evidence. A rendered document becomes proof that the thing exists in the format you actually need. A task becomes a run you design and review.

That expands what one person can get done.

It has its own danger.

Codex can make completion feel more complete than it is.

The run finishes. The message is tidy. The files exist. The agent says it verified the result. It lists the changes. It names the artifacts. It may even have run commands. The operation looks complete.

But completion is not quality.

The agent may have used the wrong source. It may have followed the instruction too literally. It may have optimized for a check that did not matter. It may have created a technically valid artifact that misses the human point. It may have generated so much output that the review burden is larger than the original job.

The second failure mode is completion theater.

It is not unique to Codex, but Codex’s strength can make it easier to miss. If the interface teaches you to dispatch work, the risk is that a finished run starts to feel like finished work.

Good Codex users learn how to resist that. They define proof before the run starts. They keep the scope narrow enough to review. They ask for source lists, screenshots, diffs, rendered files, and logs. They use second-agent review. They understand that sandboxing and auto-review are boundary tools, not replacements for judgment. They do not trust the final message. They trust the receipts.

Codex teaches dispatch, but mature dispatch is not launching more agents. It means knowing which work deserves a run, what boundary it needs, and what proof would make the result worth trusting.


## The real difference shows up after the output

Most comparisons focus on the output.

Which agent built the better app, fixed the bug, wrote cleaner code, finished faster?

Those are useful questions, but they miss the part that will matter most as agents move into serious work.

The real difference often shows up after the output, when a human has to decide whether the work can be trusted.

That means being able to audit what happened, tell which instruction was followed and which was silently reinterpreted, separate a good-looking artifact from a correct one, gauge the review burden before you accept the work, and judge whether the agent made the right kind of mistake for the job.

One early arXiv paper compared Claude Code and Codex on the same end-to-end scientific workflow using simulated Einstein Telescope gravitational-wave data. Both agents completed the work, but completion was not the interesting part. The interesting part was the shape of the runs.

The two agents produced nearly identical science, but they got there in completely different ways. Claude Code started executing right away and moved fast, correcting itself silently as it went and even raising its own token budget partway through without being asked. Codex paused before it ran anything and asked what the job actually was, then left a cleaner trail of what it had done. The interesting axis was speed versus auditability, silent self-correction versus a transparent record, and very different review burdens at the end. Which agent won is the wrong question.

That is the layer worth studying.

If an agent silently improves a bad instruction, that might be wonderful in a brainstorm and dangerous in a scientific pipeline. If an agent follows your instruction literally, that might be reassuring in a compliance workflow and useless in a strategy session. If an agent finishes quickly without much trace, that might feel magical until you need to audit it. If an agent restarts and leaves a trail, that might feel slow until the trail is what saves you.

So you end up asking a different question. What kind of run produced this?

Axios recently described a related pattern outside software. Stanford professor Andrew Hall used Claude Code to update an academic paper. The agent gathered data, ran analyses, produced figures and tables, and drafted the paper with relatively little prompting. That is an astonishing amount of knowledge work. Then the human audit found the limit: the agent had missed some necessary data collection and coding. It did a lot right. It still needed expert oversight.

That example is the future in miniature.

Agents will do enough right that ignoring them will be irrational, and they will make enough mistakes that trusting them blindly will be reckless. The scarce skill is going to be designing, supervising, and auditing runs without losing the human point of the work. Prompt-typing was never the hard part.

This is why Dan Shipper’s recent writing about agents needing human operators lands for me. The paradox is that more automation does not eliminate human work. It moves the human toward setup, maintenance, review, judgment, and the next decision. Steve Yegge’s agent writing comes from a very different voice, but it is obsessed with the same underlying shift: the future is not one magic agent in a box but a crowd of them, and the real work is orchestration, observability, coordination, and the human burden of managing many machine workers.

This is the layer Claude and Codex are teaching in different ways.

Claude teaches you how to keep the machine close enough to shape the work.

Codex teaches you how to send the machine far enough away that it can do work without you.

The hard part is knowing which distance the job requires.


## This is going to shape work culture

The individual habit matters, and the organizational habit may matter even more.

When agents become normal at work, organizations will not simply “use AI.” They will build operating cultures around AI labor.

Some teams will default to conversation. They will keep agents close, use them to shape thinking, generate plans, explore ambiguity, and move quickly through uncertainty. That can create better judgment, but it can also create a culture where a persuasive session is mistaken for alignment.

Some teams will default to dispatch. They will break work into tasks, launch runs, collect artifacts, automate recurring checks, and route more work through agent queues. That can create enormous throughput, but it can also create a culture where completed artifacts pile up faster than humans can inspect them.

Both failure modes are real.

Picture the bad future. Agents do a great deal of work, and the human review layer never matures fast enough to keep up.

This is what people miss when they say AI will make everyone more productive.

Productive at what? Producing more documents, more tickets, more dashboards, more plausible summaries, more work nobody can responsibly verify?

The agent age creates a throughput problem and a truth problem at the same time. We will be able to generate more work than we can inspect, so we will need better habits for knowing what happened, what changed, what was sourced, what was assumed, what was verified, and what still requires a human.

The interface is where those habits get practiced.

This is why Claude Code and Codex matter. They are not the final form of agents. But the habits people learn now will be sticky.

If your first serious agent experience is Claude, you may expect AI to be close, conversational, interruptible, and good at helping you discover the real shape of the work.

If your first serious agent experience is Codex, you may expect AI to be assignable, parallel, bounded, and responsible for coming back with receipts.

Both expectations are useful, and either one becomes dangerous when it becomes the only expectation.


## The standard I would teach everyone

Do not start by asking which tool to use. Start by naming the run.

This is the standard I am trying to teach myself as much as anyone else. I do not want to become the person who launches ten agents because it feels productive. I also do not want to become the person who stays in a beautiful conversation forever because it feels thoughtful. Both can become ways to avoid the harder question: what kind of work is this, and what would make me trust the result?

There are five common run shapes.

A steering run is for work that is still becoming clear. Use it when you need conversation, taste, problem discovery, architecture, writing judgment, design direction, or a plan. Claude often shines here because it keeps the agent close.

A dispatch run is for work that can be written down as a bounded assignment. Use it when you can define the source of truth, allowed actions, output, and proof. Codex often shines here because it makes separated runs and receipts feel natural.

An investigation run is for gathering evidence without polluting the main context. Use subagents to inspect logs, compare sources, scan folders, test claims, or challenge assumptions.

A verification run is for checking work another agent or human produced. Its only job is to inspect that work against a standard.

A recurring run is for work that should happen again: a daily brief, weekly audit, open-loop check, package validation, source refresh, inbox triage, report update, or test sweep.

Before any serious run, write six things:

1. What kind of run is this?
2. What is the source of truth?
3. What can the agent touch?
4. What should the agent do if it gets stuck or finds a contradiction?
5. What proof should come back?
6. How much review am I willing to spend?

Most people skip that last question.

Review cost is the economic center of agent work. A ten-minute run that creates an hour of review may be worse than doing the work yourself. A two-hour run that returns a tight artifact with clean proof may be a bargain. The agent did not save you time unless the inspection path works.

This is also where Claude and Codex should be combined more often.

Use Claude to turn ambiguity into a real assignment. Send the assignment to Codex for execution. Use Codex to produce the artifact and receipts. Use Claude to review for taste, coherence, and whether the artifact actually answers the human question. Or reverse the order when the task calls for it. Let one agent generate and another critique. Let one agent implement and another audit. Let one agent produce the report and another compare it to the transcript.

The principle is simple: do not let the agent that made the thing be the only judge of whether the thing is good.

That was true for humans. It is more true for agents.

There is a catch worth naming. Early evidence suggests that when two agents pass work back and forth on their own, with no human in the loop, quality can drop below what either would produce alone. That reads like an argument against combining them. Looked at more closely, it is an argument for staying in the seam between them. The handoff is where your judgment does the real work, and it stops working the moment you treat the two agents as a closed loop you can walk away from. Use one to sharpen the assignment and the other to stress-test the result, and stay the one who decides what survives.

The deeper principle is not to let the interface decide your standard without you noticing.

If you use Claude, remember that feeling understood is not proof.

If you use Codex, remember that a completed run is not quality.

If you use both, remember that cross-checking sharpens your judgment rather than replacing it.


## The question is what kind of worker you become

Beyond the extra output, working with AI changes what the work itself feels like.

You start to see tasks as runs and folders as work surfaces. You start to care about source-of-truth documents, write instructions differently, and ask for receipts. You start to separate planning from execution and execution from review. And you start to notice the warning signs: a conversation getting bloated, an artifact that exists but cannot be trusted.

That is good, and it is also unsettling.

Doing the work yourself is tiring in one way. Managing agents is tiring in another. You have to trust work you did not personally do without becoming careless. You have to stop micromanaging every step without becoming gullible. You have to let the machine run and then be ruthless about what came back.

That creates a new relationship to your own labor.

This is why getting it right feels personal to me. My work is increasingly about helping people use AI without either worshiping it or dismissing it. If I teach people to admire the conversation but ignore the artifact, I have failed them. If I teach people to launch agents and accept the final summary as proof, I have failed them in the other direction. The goal is to make people more capable around AI, not just more impressed by it.

People who learn it early will look strange for a while. They will have too many threads open. They will talk about worktrees, skills, hooks, verification, and source lists even when they are not coders. They will ask agents to review what other agents did. They will spend a surprising amount of time refining the handoff instead of doing the task manually.

Then much of that will look normal.

This is how interface shifts usually go. Picture the people carrying BlackBerrys in 2007 and 2008, thumbing out email on the train while everyone else waited to get back to a desk. For a while they looked like a strange little tribe with an expensive habit. What they were early to was an assumption: that serious work could happen anywhere, in small pieces, without a building wrapped around it. The smartphone spread because it rewrote what a computer was for, and once enough people lived inside that new grammar, the weird tribe became the baseline. Agent interfaces are rewriting the same kind of expectation right now. This time the grammar is less about where work happens and more about how you hand work to a machine and how you decide whether to trust what comes back.

So do not reduce Claude Code versus Codex to a benchmark fight. The benchmark will change. The models will change. The products will copy each other’s features. The winner of one month will not settle the category.

The habits will last longer.

Claude is training the habit of staying close to an agent while the work is ambiguous.

Codex is training the habit of dispatching agents into bounded work and demanding receipts.

The future will require both habits, because AI work will require both intimacy and distance. You need enough intimacy with the model to shape unclear problems and enough distance from the model to inspect its work without being seduced by it.

That is the balance.

The most important question is not which agent is smarter. It is: what kind of AI worker am I becoming when I use this tool?

Am I getting better at finding the real question?

Am I getting better at writing assignments?

Am I getting better at setting boundaries?

Am I getting better at demanding proof?

Am I getting better at knowing when the machine should run and when I need to think?

That is the real Claude versus Codex question.

Not because everyone needs to pick a side.

Because everyone is about to be trained.


## Coming Up

Tomorrow I head to [YouTube](https://www.youtube.com/@NateBJones) to break down Apple's WWDC. TL;DR: The Siri demos are the distraction. The real story is hardware, and the company that should be nervous is not OpenAI. It is NVIDIA.

Friday I am dropping a Codex guide that takes everything this piece is about and makes it real, your first personal delegation loop, start to finish, with receipts.

And Saturday, the full Claude Fable 5 breakdown (with Legos!)

Big week!


## Related reading on my Substack:

- [You can’t trust one token number across your tools. Here’s the guide to a dashboard that keeps Codex, Claude, and ChatGPT honest.](https://natesnewsletter.substack.com/p/token-burn-dashboard)
- [Exclusive: a conversation with Tibo from Codex on what your company has to become when the model can actually do the work](https://natesnewsletter.substack.com/p/codex-five-leadership-chairs-tibo-interview)
- [Opus 4.8 scored 81 in my benchmark. I still wouldn’t default to it.](https://natesnewsletter.substack.com/p/opus-48-benchmark-model-selection)
- [Claude vs Codex: Inside the Trillion Dollar Battle for Agents](https://natesnewsletter.substack.com/p/claude-vs-codex-inside-the-trillion)

[![02-is-it-real (1:1)](https://substackcdn.com/image/fetch/$s_!h6rP!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd15985c1-58bf-45b5-b33e-51425ae0fb3c_1600x1600.jpeg "02-is-it-real (1:1)")](https://substackcdn.com/image/fetch/$s_!h6rP!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd15985c1-58bf-45b5-b33e-51425ae0fb3c_1600x1600.jpeg)
