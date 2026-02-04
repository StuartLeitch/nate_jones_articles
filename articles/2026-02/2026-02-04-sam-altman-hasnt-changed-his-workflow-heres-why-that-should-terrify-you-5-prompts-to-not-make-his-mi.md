---
title: "Sam Altman hasn't changed his workflow. Here's why that should terrify you + 5 prompts to not make his mistake"
author: "Nate Jones"
published: 2026-02-04
url: https://natesnewsletter.substack.com/p/the-capability-overhang-is-real-5
subtitle: "Watch now | Sam Altman has a confession."
audience: everyone
scraped_at: 2026-02-04 12:00:18
---

Sam Altman has a confession. Despite being the CEO of OpenAI, despite having the best access to the most capable AI models on the planet, despite his own internal data showing that AI now beats human experts on three-quarters of well-scoped knowledge tasks — he still hasn’t really changed how he works.

“I still kind of run my workflow in very much the same way,” Altman admitted in a recent conversation with Alex Kantrowitz, “although I know that I could be using AI much more than I am.”

Something fundamental shifted in December 2025. The people closest to the technology are calling it a phase transition, a threshold crossing, a break in the timeline. Andrej Karpathy — who helped build OpenAI and has been writing code professionally for two decades — says his workflow inverted in a matter of weeks: from 80% manual coding to 80% AI agents. Ethan Mollick, the Wharton professor who tracks AI adoption, put it bluntly: projects from six weeks ago might already be obsolete.

And yet most people, including the CEO of the company driving much of this change, haven’t caught up. The capability is here. The adoption isn’t — and the gap between those two things is where all the leverage lives right now.

**Here’s what’s inside:**

- **The December convergence.** Three frontier models in six days, two viral orchestration patterns, and a platform feature that made both obsolete within weeks.
- **The browser that shouldn’t exist.** What it means that agents generated 3 million lines of working code in a week — and why “existence proof” undersells it.
- **The self-acceleration loop.** Anthropic’s engineers stopped writing code. OpenAI is slowing hiring. The internal benchmarks explain why.
- **The capability overhang.** The growing gap between what AI can do and what most people are doing with it — and why that gap is a temporary, closeable arbitrage.
- **The specification shift.** Why the developers getting the most value aren’t the ones prompting fastest — they’re the ones who learned to describe what they want precisely enough that agents can build it.

Let me show you what happened — and what to do about it.


## **Grab the Resources**

The gap this article describes — between what AI agents can do and what most people are doing with them — doesn’t close by reading about it. It closes the first time you hand a real task to an agent with clear success criteria and let it loop. These resources exist because I’ve watched too many people read about agentic coding, agree it’s important, and then go right back to using ChatGPT like a search engine.

The companion guide covers the foundations: what agents actually are, how they differ from chatbots, the key concepts (context windows, looping, tool use, sub-agents), the tools people are using, and the patterns that work and fail. If any of the terminology in this article felt fuzzy, start here.

LINK: [AI Coding Agents: A Plain English Guide](https://docs.google.com/document/d/1go_lU-e1g9ChYz9jdBB5NOBzdYzpxVALYX_gTpnkmZg/edit?usp=sharing)

The prompt kit is for the next step — actually doing it. Five prompts that force the specific decisions most people skip: converting a vague intention into an agent-ready spec, calibrating how closely to supervise, designing a loop that won’t burn tokens on garbage, auditing your plan for footgun risk before you start, and decoding the jargon when the discourse moves faster than you can follow. The First Agent Task prompt in particular exists because the hardest part of this shift isn’t the technology — it’s the first time you describe what you want clearly enough that something else can build it. If you can’t fill in the fields, you’ve found exactly where your specification muscle needs work. That’s the point.

LINK: [The Six Weeks That Changed Software — Companion Prompts](https://www.notion.so/product-templates/The-Six-Weeks-That-Changed-Software-Companion-Prompts-2fc5a2ccb52680c99284d9f46eb95c8b?source=copy_link)


## **What Actually Happened in December**

The shift wasn’t one thing. It was a convergence of model releases, orchestration patterns, and proof points that all crossed their respective thresholds in the same compressed window.

Start with the models. In late November, three frontier releases landed within days of each other: OpenAI’s GPT-5.1-Codex-Max on November 19, Anthropic’s Claude Opus 4.5 on November 24, and Google’s Gemini 3 around the same window. OpenAI and Anthropic were explicit about what they’d optimized for: sustained autonomous work over hours or days rather than minutes. Google’s release pushed similar boundaries in reasoning and long-context capability, even if the framing was different.

GPT-5.1-Codex-Max was designed for 24-hour autonomous operation. Claude Opus 4.5 introduced an “effort parameter” that lets developers dial reasoning depth up or down, and Anthropic priced it ~67% cheaper than previous Opus pricing. Then in December, OpenAI released GPT-5.2-Codex with “context compaction” — a technique that lets the model summarize its own work as sessions extend, maintaining coherence over much longer timeframes.

The Cursor team tested these models head-to-head. GPT-5.2 could work autonomously for extended periods, following instructions precisely without drifting. Claude Opus 4.5 tended to end tasks early and hand control back to the user. Different tools for different jobs. But both represented a new category: models that don’t just help you write code, but can work on a codebase for hours without losing the thread.


## **The Orchestration Breakthrough**

Better models were necessary but not sufficient. The real unlock came from orchestration patterns that went viral in late December.

The first was Ralph, named after the Simpsons character known for cheerful obliviousness. Geoffrey Huntley, an open-source developer in rural Australia, had grown frustrated with agentic coding’s central limitation: models kept stopping to ask permission or report progress. Every pause required human attention. So he wrote a bash script that runs Claude Code in a loop, using git commits and files as memory between iterations. When the context window fills up, a fresh agent picks up where the last one left off.

The technique is almost embarrassingly simple. While the AI industry was building elaborate multi-agent frameworks, what Huntley stumbled into was that naive persistence often beats sophisticated architecture — a loop that keeps running until tests pass can be more reliable than carefully choreographed agent handoffs. VentureBeat called it “the biggest name in AI right now.” The pattern spread because it worked.

The second was Gas Town, released by Steve Yegge on January 1. Where Ralph is minimalist, Gas Town is maximalist: a workspace manager that spawns and coordinates dozens of AI agents working in parallel. You talk to a coordinator, and it manages workers across different tasks, branches, and codebases. If you’ve ever wished for a hundred Claude Codes, Gas Town is the answer.

Both patterns share the same core insight: the bottleneck has shifted. You are now the manager of however many agents you can keep track of. Your productive capacity is limited by your attention span and your ability to scope tasks clearly.

Then, in late January, Anthropic shipped Claude Code’s new task system — and suddenly Ralph looked like a clever workaround to a problem that now has native infrastructure.


## **The Platform Catches Up**

CJ Hess, a developer who stress-tests new AI tooling, was in the middle of a large auth refactor when Claude Code’s task system dropped. He pushed it to its limits: created a massive task list, had it orchestrate sub-agents to execute the whole thing. “And it nailed it?” he wrote. “I think we just crossed something that most people haven’t noticed yet.”

The task system looks like a to-do list. That’s not what it is. It’s a coordination layer for hierarchical multi-agent work.

Here’s what it actually does. Each task can spawn its own sub-agent, and each sub-agent gets a fresh context window isolated from the main conversation. Agent 1 is digging through authentication code. Agent 2 is refactoring database queries. Agent 3 is working through tests. None of them pollute each other’s context or get confused by what the others are doing because they literally can’t see each other.

The old approach was Claude trying to hold everything in one conversation — remembering decisions from earlier while implementing new things while tracking which files had been touched. That works for small stuff. For anything complex, context management becomes the bottleneck. Stuff falls through the cracks.

The task system changes the architecture. Each agent focuses on one thing. When a task completes, anything blocked by it automatically unblocks and the next wave kicks off. Multiple sub-agents can run simultaneously. The system can route to different models based on task complexity — lighter models for quick searches, heavier ones for deep reasoning. You define dependencies and the system handles orchestration.

The key innovation is that dependencies are structural, not cognitive. Without them, Claude has to hold the entire plan in working memory. The plan degrades the moment context fills up. You end up re-explaining what’s done, what’s left, what depends on what. With dependencies externalized, the graph doesn’t forget and doesn’t drift. It never needs to be re-explained because it was never stored in memory to begin with.

Hess’s assessment: “This is why Ralph was all the craze for reanchoring. Anthropic just killed Ralph.”

Ralph was a bash loop workaround to the context window problem. The task system is native platform infrastructure for the same capability. That’s how fast this is moving — patterns go viral, and weeks later they’re obsolete because they’ve been absorbed into the platform.


## **The Browser Demo**

On January 14, Michael Truell, the CEO of Cursor, posted what might be the year’s most important demo. His team used GPT-5.2 to build a web browser from scratch. According to Cursor’s published results, the agents ran for roughly a week and produced over 3 million lines of code — a rendering engine in Rust with HTML parsing, CSS layout, text shaping, and a custom JavaScript VM.

“It kind of works,” Truell wrote. Simple websites render correctly. It’s nowhere near Chrome or Safari, and it doesn’t handle extensions, security, accessibility, or thousands of edge cases. But that’s not the point.

Traditional browsers contain tens of millions of lines of code and took years of collective effort. Chromium alone is 35 million lines. The AI-generated browser is a fraction of that size and capability. But it exists. Hundreds of agents collaborated on a shared codebase for a week with minimal conflicts. A system that can do this — even imperfectly — is categorically different from a system that helps you autocomplete functions.

Cursor is running similar experiments with a Windows emulator, an Excel clone, and a Java language server. Codebases ranging from half a million to 1.6 million lines, generated autonomously. Not production systems. Existence proofs.


## **The Loop Closes**

At Davos in late January, Dario Amodei described what he called the most important dynamic in AI right now: the self-acceleration loop.

“I have engineers at Anthropic who say: I don’t write any code anymore. I let the model write the code, I just edit it.”

The mechanism is simple. AI writes code, which produces better AI, which writes better code faster. At Anthropic, engineers are moving into oversight roles as models write, test, and debug their own software. The company attributed its accelerated release pace partly to using Claude to speed its own development.

The labs aren’t forecasting here. They’re reporting. The timeline toward more capable AI has compressed because AI has begun to build itself in ways that were theoretical two years ago.


## **OpenAI Slows Hiring**

The same week, Altman announced that OpenAI plans to “dramatically slow down” its pace of hiring. The rationale was direct: “We think we’ll be able to do so much more with fewer people.”

This isn’t a hiring freeze. OpenAI will keep growing. But Altman wants to avoid the pattern where companies hire aggressively, then realize AI handles much of the work, then face uncomfortable conversations about headcount. Better to grow slowly and let AI amplify smaller teams.

He also described changes to the interview process. Traditional coding tests are “even less relevant” now. Instead, Altman wants to give candidates tasks that would have been impossible for one person to complete in two weeks a year ago — and watch them do it in 10 or 20 minutes with AI assistance. What matters now is whether you can direct systems that write code for you, not whether you can write code yourself.

The numbers behind this decision come from OpenAI’s internal benchmark called GDP-val. It measures how often AI output is preferred over human expert output on well-scoped knowledge work. GPT-5 Thinking tied or beat humans 38.8% of the time. GPT-5.2 Thinking hit 70.9%. GPT-5.2 Pro reached 74.1%.

On three-quarters of scoped knowledge tasks, the AI is now preferred. Altman’s reaction: “A co-worker that you can assign an hour’s worth of tasks to and get something you like better back 74% of the time is still pretty extraordinary.”


## **The Overhang**

This brings us back to the paradox. If models beat human experts most of the time on scoped tasks, why hasn’t work transformed already? Why is the CEO of OpenAI still running his workflow “in very much the same way”?

Altman calls this “the overhang.” Capability has leapt forward. Adoption hasn’t. Most knowledge workers are still using AI the way they used GPT-4: ask a question, get an answer, move on. Summarize this document. Draft this email. They’re not running agent loops overnight, not assigning hour-long tasks to AI co-workers, not managing fleets of parallel workers across their backlog.

The overhang explains why the discourse feels so disconnected. Someone running Ralph loops and Gas Town convoys is living in a different technological reality than someone who queries ChatGPT twice a day — even though they have access to the same underlying tools. One person sees a phase transition. The other sees incremental improvement.

It also creates a temporary arbitrage. If you figure out how to actually use these models before your competitors do, you have an edge. But if you’re waiting for AI to “get smart enough” before changing your workflow, you might be waiting for something that’s already here.


## **Getting Practical**

The developers who’ve made this shift tend to describe the same handful of changes in how they work, and the first one is the most disorienting: stop asking AI questions and start assigning it tasks.

The chatbot mental model is a trap. When you treat AI as an oracle that answers queries, you’re using a jet engine to power a bicycle. The shift is toward declarative specifications — describe the end state you want, provide success criteria, and let the system figure out how to get there. Instead of “how do I fix this bug,” try “fix this bug, run the tests, and keep iterating until they pass.” Instead of “what’s the best way to refactor this,” try “refactor this module to separate concerns, update the tests, and don’t stop until the build is green.” Karpathy’s advice is to write tests first and have the AI pass them, or write a naive algorithm and ask the AI to optimize it while preserving correctness. Don’t dictate steps. Give goals and let it loop.

This requires abandoning the expectation that AI should get things right the first time. It often won’t. Ralph works precisely because it embraces failure — if you’ve defined clear acceptance criteria, then mistakes become data for the next iteration, not showstoppers. The loop keeps running until it succeeds. The AI doesn’t get tired, doesn’t get demoralized, and will keep trying long after a human would have moved on.

What changes most is where your time goes. Less writing code, more defining what you want and evaluating whether you got it. Most engineers have spent years developing intuitions about implementation. The new skill is specification: describing a system precisely enough that an AI can build it, writing tests that capture your real requirements, reviewing AI-generated code for subtle conceptual errors rather than syntax mistakes. Maggie Appleton, a designer who has been analyzing these tools closely, puts it sharply: when agents write all the code, design becomes the bottleneck. “Gas Town churns through implementation plans so quickly that you have to do a LOT of design and planning to keep the engine fed.” The questions that slow you down aren’t about syntax anymore. They’re about architecture, user experience, composability, metaphor. What should this feel like? Is this the right abstraction? These are decisions agents cannot make for you. They require your context, taste, and vision.

The flip side of all this speed is recklessness, and it’s worth pausing on because the footgun is real. Appleton warns: “You can move so fast you never stop to think. It is so easy to prompt, you don’t fully consider what you’re building at each step. It is only once you are hip-deep in poor architectural decisions, inscrutable bugs, and a fuzzy memory of what you set out to do, do you realise you have burned a billion tokens in exchange for a pile of hot trash.” Gas Town itself is exhibit A. Yegge admits he never looked at the code — 100% vibecoded. The result is a system that fits the shape of his brain and no one else’s. Users report that the mayor is “dumb as rocks,” the witness “regularly forgets to look at stuff,” and the workers “have the object permanence of a tank full of goldfish.” The patterns are valuable. The execution is chaos. Speed without design discipline produces expensive messes.

Once you’ve internalized the task-assignment mindset and the specification discipline, the next move is scale. If one agent produces a pull request in an hour, what happens with ten agents working on ten parts of your backlog? Some developers report going from a few PRs per day to dozens. Ralph was designed for overnight sessions — define the work, start the loop, go to bed, wake up to commits. If you’re on Claude Code, the new task system externalizes your dependency graph and spawns sub-agents automatically. If you want something simpler, the Ralph pattern still works: a bash loop that keeps running until success criteria are met. Either way, the constraint moves from coding to coordination, and you’re moving state out of the model’s memory and into structures that don’t forget.

If you haven’t revisited your AI workflow since November, you’re operating on stale assumptions about what’s possible. The models improved dramatically in December. Techniques are evolving weekly. The developers furthest along are sharing prompts, workflows, and mistakes openly. No one has this figured out yet. The community is the curriculum.


## **The New Shape of Work**

Karpathy noted something important about the errors that current models make. They’re not syntax errors anymore. They’re subtle conceptual mistakes — the kind a hasty junior developer might produce. Models make wrong assumptions and run with them without checking. They don’t surface tradeoffs. They don’t push back when they should. They overcomplicate code and bloat abstractions.

But these are supervision problems, not capability problems. The solution isn’t to do the work yourself. It’s to get better at oversight. You watch the agents “like a hawk,” as Karpathy puts it, in an IDE on the side. You catch the moments when they’ve implemented a thousand lines to solve a problem you could solve in a hundred. You develop judgment about when to intervene and when to let the loop run.

This is what Altman means when he says “what it means to be an engineer is going to super change.” Less time typing or debugging. More time directing, reviewing, and coordinating. The comparison to managing junior employees is apt — except these employees work around the clock, never get demoralized, and can be cloned instantly.

Karpathy observes that he’s already starting to atrophy his ability to write code manually, and he doesn’t seem particularly alarmed. Generation and discrimination are different capabilities. You can review code effectively even as your ability to produce it from scratch declines — and reviewing is the skill that compounds now.


## **Where This Is Going**

Hess sees something in the task system’s architecture that points forward. Right now you work with Claude as the main agent. You give it something complex, it breaks the work down, creates a dependency graph, spawns sub-agents. That’s layer one.

But those sub-agents are just Claude instances with their own context windows. There’s no architectural reason they can’t use the same task system themselves.

You ask Claude to refactor an entire codebase. It breaks that into subsystems — auth, database, API routes, frontend, tests. Spawns five sub-agents. Now the auth agent looks at its piece and decides it’s still complex. So it breaks the auth work down further — login, logout, sessions, password reset, token refresh. Creates its own dependency graph. Spawns its own sub-agents.

You’re three layers deep. And nothing stops layer 3 from spawning layer 4. The architecture doesn’t have a built-in ceiling — the only constraints are cost and context management, not capability.

Hess’s framing of the skill shift is blunt: “In a couple years, maybe less, the main skill won’t be writing code or even architecting systems. It’ll be defining problems clearly enough that an agent swarm can solve them. Your job becomes knowing what to build, why it matters, and what success looks like. The implementation — refactoring, testing, debugging, coordinating across services — gets delegated through layers of agents.”

This isn’t “AI replacing developers.” That framing misses what’s happening. The role is moving up another level of abstraction, the same way it does every decade or so. You’re becoming the top of a coordination hierarchy that can execute at a scale that would have required twenty people not long ago.

The implication keeps him up at night: “Right now if you want to build something ambitious you need funding, a team, months of runway. Soon you’ll just need a credit card and the ability to describe what you’re building clearly enough that agents can execute.”


## **The Code Distance Question**

One debate is already heating up: how close should developers stay to the code? Yegge never looks at what Gas Town generates. Karpathy watches agents “like a hawk” in an IDE on the side. Some developers check every diff and hand-adjust specific lines. Others direct fleets from on high. Both camps mistake a contextual judgment for a personality trait.

Appleton argues the right answer depends on what you’re building. Front-end versus back-end makes a huge difference — language is a poor medium for describing whether an animation “feels calm enough.” Risk tolerance matters: breaking images on a personal blog is recoverable; miscalculating drug dosages in healthcare software is not. Greenfield projects let you restart cheaply if agents make bad architectural choices; brownfield codebases have years of accumulated conventions that agents will happily contradict. Team size creates coordination overhead that solo developers don’t face. Experience level determines whether you can recognize patterns like memory leaks or deadlocks that junior developers haven’t catalogued yet.

A Hacker News commenter captured the accountability dimension: “Gas Town sounds fun if you are accountable to nobody: not for code quality, design coherence or inferencing costs. The rest of us are accountable for at least the first two.”

The infrastructure matters as much as the models. Validation loops, tests, specialized sub-agents for security and debugging — these are what make hands-off orchestration feel less terrifying. Without them, you’re trusting vibes. With them, you’re trusting systems.


## **Where This Leaves Us**

The December convergence established a new baseline. Models can maintain coherence for days. Orchestration patterns exist to manage fleets of agents. The economics work. And the major labs are dogfooding their own thesis — slowing hiring because they believe their tools will amplify smaller teams.

None of this means you should bet on Gas Town or Ralph specifically. As Appleton notes, Gas Town is “a provocative piece of speculative design, not a system many people will use in earnest.” The execution is too chaotic to persist. But the problems these tools wrestle with — context persistence, parallel coordination, hierarchical supervision, merge conflict resolution — will show up in the next generation of development tools. The patterns are being sketched now. Claude Code’s task system is already absorbing them into native infrastructure.

At the same time, there’s an enormous gap between what’s possible and what most people are doing. The overhang is real. Even Altman admits he hasn’t caught up.

Amodei predicted at Davos that AI could handle end-to-end software engineering tasks within 6 to 12 months. That timeline might be aggressive. But a system that builds 3 million lines of browser code in a week — even buggy, incomplete code — is fundamentally different from a system that helps you write functions. The gap between that and full automation is smaller than the gap we just crossed.

The question isn’t when AI will get good enough. By the metrics that matter to the people building it, that threshold has already been crossed. The question is when you’ll change how you work. The capability overhang won’t last forever. The people who close it first will have compounding advantages over those who wait.

Altman knows this. He said it out loud. And then he admitted he hasn’t done it himself.

That’s the strangest part of this moment. The people building the future haven’t fully moved into it yet. They’re telling you it’s here, they’re showing you the benchmarks, they’re slowing their own hiring in anticipation of what’s coming — and they’re still running their workflows in very much the same way.

If they can’t shake old habits instantly, you shouldn’t feel bad that you haven’t either. But you should probably start.

[![](https://substackcdn.com/image/fetch/$s_!3bPn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F62bfd5d1-4478-40ba-9f88-d05619fb08d0_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!3bPn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F62bfd5d1-4478-40ba-9f88-d05619fb08d0_1024x1024.png)
