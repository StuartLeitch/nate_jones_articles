---
title: "I Tested Cowork, Lindy, Sauna, and Opal Against 3 Questions. The Best Scored 1 out of 4."
author: "Nate Jones"
published: 2026-04-04
url: https://natesnewsletter.substack.com/p/every-ai-agent-you-use-has-the-same
subtitle: "Watch now | A single AI agent triggered a quarter-trillion-dollar selloff in enterprise software stocks."
audience: everyone
scraped_at: 2026-04-04 12:00:17
---

A single AI agent triggered a quarter-trillion-dollar selloff in enterprise software stocks. It’s a research preview that stops working when your laptop goes to sleep.

The tools behind that bet are still figuring out how to stay awake while you grab coffee. But that hasn’t stopped the pitch from spreading: Lindy, Sauna, Google Opal, Obvious, and a wave of startups are all selling the same thing. Software that does the work instead of helping you do the work. Outcomes, not answers.

The pitch might even be right — eventually. But there’s a question underneath it that almost nobody in the demo videos is asking, and it’s the question that determines whether any of this actually works: how does the agent know its own output is any good?

Code has a test suite. A strategy memo doesn’t compile. When an outcome agent drafts a report from your scattered notes, nothing tells it whether it captured the right insights or left out the thing that mattered most — and that distinction, between environments that give automated feedback and environments where you are the only feedback mechanism, is what separates the agents that work from the ones that quietly waste your time. That single fact is what this entire review is built on.

I tested four of the most prominent outcome agents against a framework built on this insight. Here’s what I found.

**Here’s what’s inside:**

- **Why code worked first.** The structural reason AI agents nailed software before anything else, and what it tells us about knowledge work.
- **The three questions that separate real from fake.** A framework for evaluating any outcome agent, starting with Cowork itself.
- **Four tools reviewed.** Lindy, Sauna, Google Opal, and Obvious, each tested against the framework.
- **The principles that outlast the tools.** Memory architecture, inspectable surfaces, and compounding context, whether you build or buy.
- **The evaluation prompt.** A two-phase prompt that scores any agent tool against the framework, then builds a delegation spec calibrated to its actual weaknesses — so you write the tests before the agent runs the work.

Let’s start with why this category exists at all.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260326_ken_promptkit_1)

The prompt kit for this article turns the evaluation framework into something you can actually run. You give it the tool you’re using and the task you’re delegating, and it does two things: scores the tool against the three structural questions for your specific use case, then builds a delegation spec that’s calibrated to the scores — patching the exact holes the evaluation found. If the tool has no persistent memory, the spec front-loads the full context package you need to provide every session. If inspectable surfaces are weak, it breaks the task into review gates so the agent can’t run to completion inside a black box. The whole point is that knowledge work agents can’t verify their own output, so the spec becomes your test suite — written before you hit go, not improvised after something quietly goes wrong.

---

In January, Anthropic shipped Cowork, an AI agent that works on your actual computer, in your actual files, autonomously. Point it at a folder, tell it what you want, and walk away. It plans the steps, opens apps, navigates browsers, creates documents, and delivers a finished result. No coding required.

Microsoft moved fast. Within weeks, they built Copilot Cowork directly on top of Claude’s agentic harness and announced it as their flagship AI product for 2026, despite having poured $13 billion into OpenAI. Fortune reported that the wave of AI agent announcements, led by Cowork, helped trigger a $285 billion selloff in enterprise software stocks as investors repriced every SaaS company whose core functionality (project management, writing, data analysis, workflow automation) overlapped with what an AI agent could now do on a desktop.

The market has decided: AI agents that produce outcomes are the future. Software that merely helps you do the work is dead. Software that does the work for you wins.

There’s one problem. The agent that caused all this chaos? It’s a research preview. It runs one task at a time. If your laptop goes to sleep, it stops. Enterprise audit logs don’t capture what it does. And Anthropic’s own safety guidance warns that agent safety is still in development and recommends taking precautions.

The market has priced in a future that doesn’t fully exist yet. The destination is clear. But the distance between the demo and the daily driver is larger than most people realize, for a reason that goes beyond any individual product.


## Why code worked first

To understand why outcome agents are hard, you have to understand why they worked for code before anything else.

Look at what happened on the coding side this year. It’s a different universe from knowledge work.

OpenAI shipped Codex, a cloud-based coding agent that runs tasks in parallel, in isolated sandboxes, for hours at a stretch. The Codex app launched in February with Skills (reusable agent capabilities) and Automations (agents that run unprompted, including issue triage, CI/CD, and alert monitoring). In March, Codex Subagents hit general availability: manager agents coordinating specialized workers across entire repositories, autonomously. Explorer agents scan codebases. Worker agents implement changes. The system produces pull requests while you sleep.

Claude Code crossed $2.5 billion in annualized run rate. Anthropic’s internal teams built Cowork using Claude Code in a week and a half. The tool is so good that non-developers at Anthropic (marketing, data, ops) started bypassing the chat interface to use the terminal-based coding agent for knowledge work. That’s what prompted Cowork in the first place.

Google shipped the agent step in Opal, turning its free, no-code workflow builder into something that reasons about your goal, picks the right tools, routes dynamically, and remembers context across sessions.

These aren’t demos. These are production products from the three most capable labs on earth, all pointed at the same destination: AI that does the work.

But notice the pattern. Code worked first, code worked best, and when you look at why, you find a structural reason that explains almost everything about where agents succeed and where they stall:

**Code is verifiable.**

You write code, you run tests, the tests pass or fail. There’s a compiler, a linter, a CI pipeline — the feedback loop is tight, fast, and binary. The agent knows immediately when it’s wrong, and it can iterate until it’s right. Codex can run for seven hours autonomously and produce useful pull requests because the environment itself tells it whether it’s succeeding.

Knowledge work doesn’t have that. A strategy memo doesn’t have a test suite, a client brief doesn’t compile, and a market analysis doesn’t return a pass/fail signal — which means when an agent drafts any of these things, there’s no automated way to know whether it got them right. You are the test suite. And that single asymmetry — automated verification for code, nothing but your judgment for everything else — changes everything about how agentic loops work once you leave the IDE.

Each new primitive the big players add — file access, browser control, phone dispatch, scheduling, integrations — expands what agents can reach, but each primitive also multiplies the ways the agent can fail. In code, failures are caught automatically; in knowledge work, they’re silent. What you get is a combinatorial expansion of capability and a combinatorial expansion of risk, with no corresponding expansion of the feedback mechanism that keeps it honest.

Cowork is a research preview for exactly this reason. Dispatch requires your computer to be awake and runs one task at a time. Codex’s most reliable work is still code. The big players are adding primitives carefully, one by one, because each new surface area is a new way to break in a domain where breakage is silent.

And that’s the opening a new wave of startups is trying to fill. The big players can see the destination clearly. But the startups are betting they can assemble the full stack faster, with tighter integration and memory that compounds across every interaction, while the big players iterate cautiously.

Whether that bet pays off depends entirely on three questions.


## The three questions that separate real from fake

1. ***Does the agent have persistent memory, or does every session start from zero?***
2. ***Does the agent produce artifacts you can inspect, edit, and build on, or does it produce opacity?***
3. ***Does the architecture let context compound over time, or is it a one-shot trick?***

These aren’t abstract design principles — they’re the exact complaints you’ll find in every agent thread on X right now. Agents that feel like “more efficient procrastination” because nothing carries forward. Agents that quietly fail with no way to debug why. Agents that prioritize task completion over task quality. The verification problem (how do you actually know the outcome is good?) is the recurring gotcha, and it’s the one most marketing ignores completely.

Before we get to the startups, it’s worth running the tool that started all of this through the same three questions. Cowork is the most mature outcome agent on the market. If anything passes, it should.

**Persistent memory?** Half a yes. Cowork has some memory across sessions, and the Anthropic team keeps improving it. But if you’ve spent any time with it, you know the real answer: you still have to obsessively manage context every single session. Load your docs. Attach your artifacts. Give the agent everything it needs so it doesn’t have to guess. That’s memory as a courtesy, not memory as architecture.

**Inspectable artifacts?** Clear yes. This is one of Cowork’s genuine strengths. It produces real work: PowerPoints, spreadsheets, documents you can open and edit. And I think this is partly why Wall Street panicked. They saw an agent producing actual deliverables, not just chat responses. For anyone who hasn’t been paying close attention to AI, that’s an eye-opener.

**Compounding context?** No. You’re not building on prior sessions in any meaningful way. Each task is, for the most part, a fresh start.

So the most mature outcome agent on the market scores roughly one and a quarter out of three. And people can’t get enough of it. Claude keeps having to adjust usage limits because demand outstrips capacity. That tells you something important: the appetite for agents that do the work is so strong that even a partial answer generates massive adoption. That’s what real product-market fit looks like. It also tells you just how hard this problem actually is.

Let’s run the main contenders through them.


## Lindy

Lindy dominates the outcome-agent conversation on X, and it’s not close. Founder Flo Crivello (formerly a product lead at Uber) and the team post constantly about real use cases: email triage, phone agents that turn inbound support into sales, full marketing teams running ad experiments end-to-end, meeting prep that researches guests and populates briefing docs. Greg Isenberg recommends it. Lenny Rachitsky says he built a “life-changing” agent in ten minutes. Users echo the narrative, and it does feel like a digital teammate that acts without prompting and remembers commitments.

The pitch: describe an outcome in plain language, Lindy figures out the steps. No flowcharting. No logic trees. 5,000+ integrations. Phone agents at $0.19/minute. Agentic reasoning in version 3.0.

**Where it works:** the delegation model is fundamentally different from Zapier or Make. You don’t design the process. You describe the result. For email management, meeting scheduling, and CRM updates, this works well. The “digital teammate” framing resonates because it describes what people actually want: less busywork, not more software to learn.

**Where it doesn’t:** the disconnect between the influencer narrative and the user reality is wider here than anywhere else in the category. Trustpilot sits around 2.4 out of 5. Credits burn unpredictably. One user described an agent consuming over 2,000 paid credits just to decide it wasn’t the right approach, then deleting everything. IP blocking limits web-based tasks. Billing continues after cancellation. A recent review called the platform “super laggy” with responses taking hours. Complex automations, the ones that would actually justify an outcome agent over a Zapier trigger, seem to be where Lindy struggles most.

No fresh flood of horror stories in the latest X chatter, so the product may be improving. But the structural issue isn’t unique to Lindy. It’s a pattern worth naming:

**The easier the interface, the harder the debugging.** When you describe an outcome in plain language and the agent “figures out the steps,” you lose visibility into what those steps actually are — and that’s fine when the output is good, but when something goes wrong you’re burning credits watching a black box fail with no way to understand why. This is the delegation trade-off: speed at the cost of inspectability. In agent threads on X (not just about Lindy) the black-box debugging problem is the single most recurring complaint. People love the magic right up until it quietly fails and they have no idea why.

This is the verification problem, showing up in product form. Code agents have tests. Lindy agents have... trust.


## Wordware / Sauna

The most interesting story in the category, because it’s a pivot story.

Wordware raised $30 million from Spark Capital, Felicis, and YC to build an IDE for AI agent development: natural-language programming, version control, one-click API deployment. Instacart and Runway were customers. The product worked. Then they killed it.

Mid-2025, the team realized people don’t wake up thinking “I want to build automation today.” They wake up thinking “I have too much to do.” Wordware became Sauna, an AI workspace for professionals. The framing: “Cursor for knowledge work.”

Founder Filip Kozera is hammering this thesis on X right now with demo videos that land directly on the questions this review is testing: memory as substrate (not a toggle), compounding context, 2,000+ integrations, a browser with persistent logins, proactive scheduled jobs that run while you sleep. Spaces organize your work (Hiring, Content Creation, Board Prep), each with its own context and rules. Cached automations called “recipes”: explain what you want once, and it runs automatically after that.

**Where it works:** the memory architecture is the strongest conceptual play in the field. Sauna explicitly describes memory as foundational, not a feature you enable, but the substrate everything else builds on. Context compounds. Patterns emerge. They kept the infrastructure layer from Wordware underneath, so the orchestration is real engineering, not a wrapper around an API. And they landed on a key insight: “We’re not asking knowledge workers to become programmers. We’re recognizing they’re already specification writers.” Every email you write, every brief, every set of instructions, that’s a spec. What matters is whether the execution engine honors it.

**Where it doesn’t:** Sauna is early — the pivot was recent, the user base is small, and “Cursor for knowledge work” is a powerful analogy but a dangerous one. Cursor works because code has structure, tests, and compilation. You know when code is wrong. Knowledge work is fuzzier. A memo doesn’t compile. And this is the same verification problem again: how do you know the agent’s output is actually good? Sauna hasn’t articulated a clear answer yet.

Demo energy on X is strong. But demo energy and production reliability are different things. The real test is whether the tenth week of daily use compounds or whether users hit a ceiling where memory gets noisy and recipes misfire.


## Google Opal

The tool most roundups are ignoring, and they shouldn’t be.

Opal is Google Labs’ free, prompt-to-workflow builder. In late February it got the agent step upgrade: Gemini 3 Flash powers a system that understands your objective, picks the right tools and models, self-corrects, remembers across sessions, routes dynamically, and asks clarifying questions when it needs more information. VentureBeat called it a working reference architecture for the capabilities that will define enterprise agents.

On X, people are building meeting-prep agents in ten minutes with voice input. Because Opal apps are shareable via links, people are remixing each other’s workflows, building in public in a way none of the venture-backed tools have achieved.

**Where it works:** it’s free. That alone makes it the most important tool in this review for most readers. It’s embedded in Google Workspace natively. And memory uses Google Sheets as the persistence layer, crude but accidentally brilliant for inspectability. Your agent’s memory is a spreadsheet you can open and edit. That’s more transparent than anything Lindy or Sauna offer.

**Where it doesn’t:** it’s Google. The memory model is a spreadsheet, with no lifecycle separation, no semantic retrieval, no structured query patterns. That works for preferences and shopping lists. It doesn’t work for compounding institutional knowledge. And every Opal workflow is locked into Google’s stack. Your memory, your recipes, your integrations don’t port. Google’s product graveyard is legendary. For a tool supposed to compound value over time, platform risk matters enormously.

Still, as the free on-ramp to the entire concept, Opal is the entry point most people don’t know about.


## Obvious

Obvious is the most ambitious entry. Full AI workspace: workbooks with SQL, documents with live charts, presentations, custom apps via a dev sandbox, Kanban boards. Cross-artifact relationships are first-class. Your slide deck references your spreadsheet, which references your dataset. The pitch is literally “outcomes, not answers.”

**The problem:** it’s the quietest tool in this review from a community standpoint. On X: almost no war stories, no user demos, no builder threads. When Lindy and Sauna dominate the conversation with daily demos and real-world anecdotes, silence is a data point. Worth watching, but hard to endorse without more signal from actual users.


## The principles that outlast the tools

The tools will keep changing. New features, new pivots, new entrants every month. But three principles are stable, and they’re the ones I built Open Brain around, a project for building an agent-readable personal knowledge store on Postgres and MCP that hundreds of people have now set up. These principles work whether you’re evaluating a startup or building your own.


### Memory is an architecture, not a feature

Every tool in this category has some version of “memory.” But memory-as-feature (passive accumulation of preferences) and memory-as-architecture (deliberate separation by lifecycle, storage pattern, and retrieval strategy) are fundamentally different.

Your permanent preferences live in one place, your project-specific facts in another, your session state in a third — and each layer maps to a different storage pattern: key-value for “what’s my style?”, relational for “what’s the exact client ID?”, vector for “what similar work have we done?”, event logs for “what did we try last time?”

When memory is a feature, the vendor controls it. When memory is an architecture, you control it. And control matters, because when you switch tools (and you will) your memory either comes with you or it doesn’t.

Work on context engineering has consistently shown that models operating from accumulated but unstructured context perform worse than fresh models starting clean. Memory doesn’t automatically compound. It can rot. The agents that improve are the ones with explicit memory management, not the ones that dump everything into a growing window and hope.

Most outcome agents treat memory as a feature. That’s their deepest structural weakness.


### Outcomes require surfaces you can see and edit

When an agent writes a document, can you see it? Edit it? Build on it? Can the agent see your edits and incorporate them next time?

Or did it produce something in a black box (a workflow that ran, an email that sent, a CRM field that updated) where you can’t inspect the reasoning, verify the quality, or course-correct until something breaks downstream?

Obvious gets this right with interconnected artifacts. Opal gets it accidentally right with Sheets-as-memory. Lindy prioritizes delegation over visibility, and the X discourse shows that’s where users hit the wall.

The principle: if the agent writes to a place you can’t inspect, edit, and build on, it’s not producing outcomes. It’s producing opacity.


### Context needs to compound

Does the tenth task go better than the first? If every task starts from roughly the same baseline, you have a tool, not a system. Tools are useful. Systems compound. The difference matters.

This is where /loop meets Open Brain. Claude Code’s /loop gives you a scheduling primitive. Open Brain gives you persistent, agent-readable storage. Stitch them together: the agent loops on a schedule, reads what it found last time, does work, writes results back. Each iteration builds on the last. The agent doesn’t just remember. It converges.

None of the commercial tools have fully solved compounding. Sauna is closest. But the winners will be the ones where usage compounds into knowledge, not the ones where every task is a fresh transaction.


## Build vs. buy

If you want to start this week:

**Opal** is the free on-ramp. Build a meeting-prep agent. See if the concept clicks. Just know nothing ports.

**Sauna** is the most architecturally sound commercial play, if it matures. Memory-as-substrate, recipe caching, proactive background jobs. Early, but worth watching closely.

**Lindy** is the fastest to “an agent did something useful today,” if you stick to email, scheduling, CRM. Watch your credits. Don’t ask for complex multi-step work.

**Cowork** is the most capable single-agent product on the market, but it’s a research preview with real limitations. If you’re on Claude Max and comfortable with the constraints, it’s impressive for desktop knowledge work right now.

And if you’ve built Open Brain, or any persistent knowledge store your agents can read and write to, you already have the hardest piece. The memory layer. The thing every tool in this review is trying to build for you and own.

From there, outcome agents are three layers:

**The knowledge store.** Postgres + MCP + embeddings. Separated by lifecycle. Matched to query pattern. Portable. Yours.

**Agent recipes.** Pre-wired workflows against your store. Meeting prep. Research capture. Weekly digest. Patterns, not products. Each one proves the store isn’t passive. It’s an active substrate.

**The scheduling loop.** /loop, cron, or event triggers. Agents write back. The store gets richer. The next run is better.

The commercial tools are bundled versions of these three layers, with varying sophistication and varying lock-in. Some are good. But they all share a structural limitation: they own the memory, which means they own the compounding, which means they own you.


## The verdict

The market is right that outcome agents are the future. It’s wrong about the timeline.

The big model companies (Anthropic, OpenAI, Google) are arriving at outcomes primitive by primitive. Code worked first because code is verifiable. Knowledge work is next, but the verification problem is hard, and the combinatorial expansion of primitives (files, browser, phone, scheduling, integrations) multiplies ways to break in a domain where breakage is silent.

The startups (Lindy, Sauna, Obvious) are betting they can assemble the full stack before the big players finish adding primitives. That’s a real window, but it’s a window, not a moat. And most of them are building on the same shaky foundation: memory as a feature instead of memory as an architecture.

Lindy has the loudest voice and the widest divide between hype and delivery. Sauna has the best architecture and needs to prove it survives contact with production. Opal is the free on-ramp everyone should try. Obvious is the most ambitious and the least proven.

And underneath all of them, three principles hold: memory is an architecture you own, not a feature someone sells you. Outcomes require surfaces you can see and edit, not black boxes you delegate to. And the only systems worth building are the ones where context compounds.

A $285 billion selloff says the market believes the future is agents that do the work. The products say we’re not there yet. And the principles — memory you own, surfaces you can see, context that compounds — say what “there” actually looks like.

The tools will change. The principles won’t.

[![](https://substackcdn.com/image/fetch/$s_!Wwb4!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6cce40d9-2bdb-4b92-82cd-fec41ad524a9_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Wwb4!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6cce40d9-2bdb-4b92-82cd-fec41ad524a9_1024x1024.png)
