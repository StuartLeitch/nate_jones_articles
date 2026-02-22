---
title: "January is already obsolete. My honest breakdown of Opus 4.6 + what it means for developers, leaders, and everyone in between."
author: "Nate Jones"
published: 2026-02-11
url: https://natesnewsletter.substack.com/p/january-is-already-obsolete-my-honest
subtitle: "Watch now | The Opus 4.6 release changed three things at once. Most people only noticed one."
audience: everyone
scraped_at: 2026-02-22 15:13:01
---

Sixteen AI agents coded for two weeks straight — humans set the spec and validated the results, but didn’t write the code — and delivered a functional C compiler. Roughly 100,000 lines of Rust. According to Anthropic’s engineering blog, it compiles substantial real-world systems software — including the Linux kernel, PostgreSQL, FFmpeg, SQLite, QEMU, and Redis — and passes the vast majority of the GCC torture test suite. Cost: $20,000.

A year ago, autonomous AI coding topped out at about thirty minutes before the model lost the thread. Last summer, Rakuten got seven hours out of Claude and the engineering team passed the results around like a rumor. Seven hours was a breakthrough.

Thirty minutes to two weeks in twelve months. That’s not a trend line. That’s a phase change.

And it’s not just code. Rakuten put Opus 4.6 on their engineering issue tracker and it autonomously closed 13 issues and routed 12 more to the right team members in a single day — across a 50-person organization spanning six repositories. Anthropic pointed the model at open-source codebases with basic tools and it found over 500 previously unknown high-severity vulnerabilities in production software that human researchers and automated scanners had already reviewed. Two reporters with no engineering background sat down with Claude Cowork and built a project management dashboard in under an hour.

None of this was possible in January. Opus 4.6 shipped on February 5th. It has been less than a week.

**Here’s what’s inside:**

- **The three-month gap.** What changed between Opus 4.5 and 4.6 — a 5x context window, 4x retrieval improvement, nearly doubled reasoning scores, and agent teams — all in a single quarter.
- **What working memory actually means.** Why the MRCR v2 benchmark matters more than the context window number, and what it looks like when a model can hold 50,000 lines of code and actually know what’s on every line.
- **The Rakuten proof.** Production deployment data from a company managing 50 engineers across six repos with AI — not a pilot, not a demo.
- **Team swarms.** How sixteen agents coordinated to build a compiler using the same management structures that human teams use — and what it means that AI discovered hierarchy independently.
- **Revenue per employee.** The reported numbers from Cursor, Midjourney, and Lovable that suggest the relationship between headcount and output just broke.
- **The honest pushback.** What the skeptics are saying, why some of it is fair, and why this release is different from the ones that underdelivered.
- **A personalized briefing prompt.** Paste it into Claude and get a walkthrough of every Opus 4.6 change mapped specifically to your work, your tools, and how you actually use the model.

Let me walk you through what happened — and what it means for how you work, whether you write code or not.


## **[Grab the prompts](https://www.notion.so/product-templates/The-Opus-4-6-Personal-Briefing-Kit-3025a2ccb526805b88abf94bcf3416e1?source=copy_link)**

Every major model release generates the same problem: a wall of benchmarks, feature announcements, pricing changes, and product updates — and no clear answer to the only question that matters, which is *what does this actually change about how I work?* I built this prompt because I’ve watched too many smart people read an entire release announcement, feel vaguely impressed, and then change absolutely nothing about their workflows because nobody translated the specs into their specific context.

This is a single-turn prompt. You paste it into Claude, it reviews everything it knows about you — your conversation history, your stored preferences, your past projects — and produces a personalized briefing that maps every aspect of the Opus 4.6 release to your actual work, your actual tools, and how you actually use the model. Not a generic summary. A briefing written for you, explaining what each change is, what it does, what it means in practice, and whether it matters for the specific things you do. If a feature isn’t relevant to your work, it says so and moves on instead of inventing a reason you should care.

The full version includes complete reference material so the model doesn’t hallucinate capabilities. The quick version is five lines and relies on Claude’s own knowledge of the release — less precise, more portable, still useful. Use whichever fits how you work.


## **The Three-Month Gap**

Opus 4.5 shipped in November 2025. It was Anthropic’s most capable model — strong on reasoning, good at code, reliable on long documents. The consensus was that it represented roughly the state of the art.

Three months later, Opus 4.6 shipped with:

A 5x expansion in context window — from 200,000 tokens to one million. The ability to hold roughly 50,000 lines of code in a single context, versus 10,000 previously.

A 4x improvement in long-document retrieval — MRCR v2 scores jumped from 18.5% to 76% at a million tokens. That benchmark measures whether a model can actually find specific information buried deep in a long context. Anthropic’s system card reports Opus 4.6 scoring 93% at 256,000 tokens — the range where most real-world documents fall.

Nearly doubled reasoning capability — ARC-AGI-2 scores jumped from 37.6% to 68.8% in third-party benchmark evaluations. Not an incremental improvement. A generational leap compressed into a single quarter.

The top reported score on Terminal-Bench 2.0 — the benchmark that measures real-world agentic coding capability, not toy problems. Roughly 65% in published evaluations, up from ~60% for the previous best, though exact scores vary by evaluation setup.

And on the product side, Claude Code shipped a capability that didn’t exist in January: agent teams. Multiple instances of Claude working simultaneously, each in its own context window, coordinating through a shared task system — a lead agent decomposes and assigns work, specialists handle subsystems, and agents message each other directly. Not a metaphor for collaboration. Actual coordination between autonomous software agents, built on top of what the model makes possible.

All of this in three months. The pace of change in AI is a phrase people repeat without internalizing it. So let me put it concretely: the tools you mastered in January are a different generation from the tools that shipped this week. Not a minor update. A different generation. Your January mental model of what AI can and cannot do is already wrong, and it will be wrong again by March.


## **What Working Memory Actually Means**

The 5x context window expansion is the number Anthropic put in the press release. It’s the wrong number to focus on.

The right number is the MRCR v2 score. Multi-Round Coreference Resolution, version 2 — a benchmark originally developed by OpenAI to measure something that matters enormously and that nobody was testing properly: can a model actually retrieve and use information from deep inside a long context?

Not “can it accept a million tokens.” Every major model could accept long contexts by January 2026. The question is whether the model can find what you put in there. Retrieve clause 47 from page 130. Trace a function call through six files of imports. Hold the architecture of an entire system in its head and reason about how the pieces interact. That’s what MRCR v2 measures.

Sonnet 4.5, at a million tokens: 18.5%. One in five. Gemini 3 Pro: 26.3%. One in four. These were the best models available in January. They could hold your codebase. They couldn’t read it. The context window was a filing cabinet with no index — documents went in, but retrieving them was essentially random past the first quarter of the content.

Opus 4.6 at a million tokens: 76%. Anthropic’s system card reports 93% at 256,000 tokens.

That’s the number that matters. Not because it’s a benchmark score. Because it’s the difference between a model that can hold 50,000 lines of code and a model that can hold 50,000 lines of code and know what’s on every line. The difference between a model that sees one file at a time and a model that holds the entire system in its head simultaneously — every import, every dependency, every interaction between modules, all visible at once.

Here’s why that benchmark matters in practice. A senior engineer working on a large codebase carries a mental model of the whole system. They know changing the auth module breaks the session handler. They know the rate limiter shares state with the load balancer. Not because they looked it up — because they’ve lived in the code long enough that the architecture is intuition, not documentation. That holistic awareness is what separates a senior engineer from a contractor reading the codebase for the first time.

Opus 4.6 can do this for 50,000 lines simultaneously. Not by summarizing. Not by searching. By holding the entire context and reasoning across it the way a human mind does with a system it knows deeply. And because working memory improved this dramatically in the span of a single development cycle, it’s not hard to see where the trajectory goes. The C compiler project — 100,000 lines of Rust — required 16 parallel agents precisely because even a million-token context couldn’t hold the whole thing at once. At the current rate of improvement, it won’t require 16 agents for long.


## **The Rakuten Proof**

Rakuten — the Japanese e-commerce and fintech conglomerate — deployed Claude Code across its engineering organization. Not as a pilot. In production, handling real work, touching real code that ships to real users across one of the largest technology platforms in Asia.

Yusuke Kaji, Rakuten’s general manager of AI, reported what happened when they put Opus 4.6 on their issue tracker: “Claude Opus 4.6 autonomously closed 13 issues and assigned 12 issues to the right team members in a single day, managing a ~50-person organization across 6 repositories.”

Not “helped an engineer triage tickets.” Closed issues. Routed work. Across a 50-person organization spanning six repos. The model understood not just the code but the org chart — which team owns which repo, which engineer has context on which subsystem, what closes versus what escalates.

Think about what that implies — and I want to be careful to separate the reported fact from my inference here. The fact: an AI agent autonomously closed and routed issues across a 50-person org spanning six repos. The inference: a senior engineering manager at a company like Rakuten costs $200,000 to $350,000 a year fully loaded, and a meaningful part of their job — ticket triage, work routing, dependency tracking — is the operational coordination that Opus 4.6 just demonstrated it can handle. Not the judgment calls about what to build next. Not the career development conversations. The operational coordination that takes fifteen to twenty hours a week out of someone who should be making architectural decisions. When an AI agent handles that coordination for the cost of inference tokens, you don’t eliminate the manager. You free the manager to do the work that actually requires human judgment — and you do it at a cost that makes the old model of “hire more engineering leads to manage more engineers” look like paying ten people to carry a message when you could send an email.

The broader numbers tell the same story. Seven hours of sustained autonomous coding on a complex refactoring project. Not seven minutes of autocomplete. Seven hours. A 79% reduction in time to market — 24 days to 5. Engineers running five parallel tasks, delegating four to Claude Code. Not using AI as a tool. Operating AI as a team.

And then the number that should stop you cold: Rakuten is building an ambient agent that breaks complex tasks into 24 parallel Claude Code sessions, each handling a different slice of their massive monorepo. A month of human engineering. Running across 24 simultaneous agent streams. In production. Right now.

The detail that gets buried under the velocity numbers might be the most structurally significant: non-technical employees at Rakuten are now contributing to development through Claude’s terminal interface. People who have never written code are shipping features. The boundary between “technical” and “non-technical” — the distinction that has organized knowledge-worker hiring, compensation, and career paths for thirty years — is dissolving at the speed of deployment, not the speed of retraining.


## **Team Swarms**

The Claude Code feature most people haven’t fully absorbed is agent teams — what Anthropic internally calls team swarms. The name is accurate. Not a marketing term. An architecture.

Multiple instances of Claude Code run simultaneously, each in its own context window, coordinating through a shared task system with three states — pending, in progress, completed. One instance acts as the lead. It decomposes the project into work items, assigns them to specialists, tracks dependencies, and unblocks bottlenecks. The specialist agents work independently. When they need something from another agent, they don’t go through the lead. They message each other directly. Peer-to-peer coordination, not hub-and-spoke.

Frontend agent. Backend agent. Testing agent. Documentation agent. Each with its own context, its own reasoning chain, its own deep understanding of its piece of the system. The lead coordinates without bottlenecking. Dependencies unblock automatically when upstream tasks complete. Merge conflicts get resolved by the agents who wrote the conflicting code, not by a human scheduling a sync meeting.

This is how the C compiler got built. Not one model doing everything sequentially. Sixteen agents working in parallel — some building the parser, some building the code generator, some building the optimizer, some writing and running tests — coordinating through the same kinds of structures that human engineering teams use. Except they work 24 hours a day, they don’t have standup meetings, and they resolve coordination problems through direct messaging rather than waiting for the next sprint planning session.

One of the running questions in AI has been whether agents will reinvent management. They did. Cursor’s autonomous agent swarm independently organized into hierarchical structures — coordinator agents, specialist agents, review agents. StrongDM published a production framework called Software Factory built around exactly this pattern. And now Anthropic has shipped agent teams as a first-class Claude Code feature, with 13 distinct operations for spawning, managing, and coordinating agents.

This isn’t coincidence. It’s convergent evolution. Hierarchy isn’t a human organizational choice imposed on systems to maintain control. It’s an emergent property of coordinating multiple intelligent agents on complex tasks. Humans invented management because management is what intelligence does when it needs to coordinate at scale. AI agents discovered the same thing independently, because the constraints are structural, not cultural. You need someone tracking dependencies. You need specialists. You need communication channels. You need a shared understanding of what’s done and what isn’t.

We didn’t impose management on AI. AI discovered management. And Claude Code on Opus 4.6 is the first product that ships with the infrastructure to run it as a feature.


## **Five Hundred Vulnerabilities Nobody Knew Existed**

On the same day Opus 4.6 launched, Anthropic published a result that got less attention than the C compiler but might matter more in the long run.

They gave Opus 4.6 basic tools — Python, debuggers, fuzzers — and pointed it at open-source codebases. No specific vulnerability-hunting instructions. No curated targets. Just: here are tools, here is code, find problems.

It found over 500 previously unknown high-severity vulnerabilities in production codebases.

Five hundred. In code that had been reviewed by human security researchers, scanned by existing automated tools, deployed in production systems used by millions of people. Code that the security community considered audited.

When traditional fuzzing and manual analysis failed on GhostScript, the model independently decided to analyze the project’s Git history — reading through years of commit logs to understand the codebase’s evolution and identify areas where security-relevant changes had been made hastily or incompletely. It invented a detection methodology that no one had instructed it to use. It reasoned about the code’s history, not just its current state, and used that temporal understanding to find vulnerabilities that static analysis couldn’t reach.

This is what happens when reasoning meets working memory. The model doesn’t scan for known patterns the way existing tools do. It builds a mental model of how the code works — how data flows, where trust boundaries exist, where assumptions get made and where they might break — and then probes the weak points with the creativity of a researcher and the patience of a machine that never gets tired of reading commit logs.

The security implications alone would justify calling Opus 4.6 a generational release. But this wasn’t the headline feature. It wasn’t even the second headline feature. Five hundred previously unknown vulnerabilities was a side demonstration. That’s the density of capability improvement packed into a single model update shipped on a single Wednesday in February.


## **The Honest Pushback**

The skeptics aren’t stupid. Their skepticism tracks historically — AI benchmark improvements have underdelivered before, repeatedly, for years.

Within hours of launch, threads appeared on the Claude subreddit: “Opus 4.6 lobotomized?” “Nerfed?” The pattern repeats with every major model release. Power users who had fine-tuned their workflows for the previous version discover the new version handles certain tasks differently. The Reddit consensus, for what it’s worth: coding improved significantly. Writing regressed — particularly technical documentation where users had developed precise prompting strategies for Sonnet 4.5 or Opus 4.5.

This is real. Dismissing it would be dishonest. Model releases involve tradeoffs. You can’t optimize everything simultaneously, and the decision to prioritize agent capabilities over prose quality tells you where Anthropic thinks the value is heading. The developers complaining aren’t wrong. They’re experiencing the edge of a genuine tension: when you build a model for agents, you build it for sustained reasoning and coordination, and the texture of short-form writing can shift.

The broader skepticism — that benchmarks don’t translate to production, that the C compiler is a cherry-picked demo, that agent teams are a novelty — is a reasonable prior. It happens to be wrong here. And the reason it’s wrong is Rakuten. The C compiler is a demo, yes. Rakuten is not. Rakuten is running in production, with real headcount implications and real shipping velocity changes, at an organization large enough that the results aren’t dismissible as a startup stunt. When a company managing 50 engineers across six repositories reports that AI is autonomously closing issues and routing work correctly, that’s not a benchmark. That’s a deployed capability changing the cost structure of engineering management.


## **What This Feels Like If You Don’t Write Code**

The C compiler is a developer story. The benchmarks are developer metrics. But the change underneath them isn’t about developers. It’s about what happens when AI can sustain complex work for hours and days instead of minutes.

In a demo that circulated widely after launch, two CNBC reporters — neither of them engineers — sat down with Claude Cowork and asked it to build a project management dashboard. Calendar views, email integration, task boards, team coordination features. The kind of tool that enterprise software companies spend years and hundreds of millions of dollars building.

It took under an hour.

[![](https://substackcdn.com/image/fetch/$s_!7OqJ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe5713ff9-23cd-4409-803e-88ef365eb1c5_1260x922.png)](https://substackcdn.com/image/fetch/$s_!7OqJ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe5713ff9-23cd-4409-803e-88ef365eb1c5_1260x922.png)

That’s the non-developer version of the C compiler story. Not “AI can code.” That’s old news and it doesn’t mean much to someone who doesn’t code. The story is: AI can build the tools you use. The software you pay per-seat fees for, the dashboards your company spent six months speccing out with a vendor, the internal tool that’s been on the engineering backlog for three quarters — an AI agent can build a working version in an afternoon, and you don’t need to write a line of code to make it happen.

The daily experience is changing in ways that are harder to benchmark but just as structural. A marketing operations team using Claude Cowork reports content audits that took eight hours now finishing in ninety minutes. Finance analysts are running due diligence that used to take days in hours — the model reads the full document set, identifies risks, and produces lawyer-ready redlines. One early adopter described the rhythm: dispatch five tasks in five minutes — a PowerPoint deck, a financial model, a research synthesis, two data analyses — walk away to make breakfast, come back to finished deliverables. Not drafts. Finished work, formatted and in the right folders.

The pattern that’s emerging for non-technical users is what Anthropic’s Scott White calls “vibe working” — you describe outcomes, not procedures. You don’t tell the AI how to build the spreadsheet. You tell it what the spreadsheet needs to show, and it figures out the formulas, the formatting, the data connections. The shift is from operating tools to directing agents, and the skill that matters isn’t technical proficiency. It’s clarity of intent. Knowing what you actually want — being able to articulate the real requirement, not just the surface request — becomes the bottleneck.

That’s the same bottleneck the developers are hitting, just from a different direction. The C compiler agents didn’t need anyone to write code for them. They needed someone to specify what “a C compiler” means precisely enough that sixteen agents could coordinate on building one. The marketing team doesn’t need someone to operate the analytics platform. They need someone who knows which metrics actually matter and can explain why. The leverage has shifted from execution to judgment, across every function, whether you write code or not.


## **The Three-Person Team With Fifty Agents**

If you lead an organization, the number that should restructure your planning isn’t two weeks or 500 vulnerabilities. It’s what’s happening to revenue per employee — and I want to walk through what’s been reported, because the pattern is more important than any single number.

Cursor — the AI coding tool — reportedly crossed $100 million in annual recurring revenue with a lean team that multiple sources describe as remarkably small for that revenue scale. Midjourney has reportedly generated over $200 million in annual revenue with a team estimated at around 40 people. Lovable, the AI app builder, reportedly reached $200 million ARR in roughly eight months — with a team that, while growing, remained a fraction of what a traditional SaaS company would need to reach that scale.

Traditional SaaS companies consider $300,000 in revenue per employee excellent. $600,000 is elite — that’s Notion. The AI-native companies are running at multiples of that number. Not because they found better people. Because their people orchestrate agents instead of doing the execution themselves.

McKinsey published the framework last month: “A human team of two to five people can already supervise an agent factory of 50 to 100 specialized agents running an end-to-end process.” They’re targeting parity — matching the number of AI agents to human workers across the firm — by the end of 2026. That’s not a research lab talking. That’s McKinsey, the company that sells organizational design to every Fortune 500 on Earth, saying the org chart is about to invert.

The pattern is already visible in startups. Jacob Bank runs a million-dollar marketing operation with zero employees and roughly 40 AI agents. Micro1 conducts 3,000 AI-powered interviews daily, handling at a tiny fraction of the headcount what enterprise recruiting firms need floors of people for. Three developers in London built a complete business banking platform in six months — a project that would have required fifteen to twenty engineers and eighteen months pre-AI.

Amazon’s two-pizza team — the idea that no team should be larger than what two pizzas can feed — is evolving into something smaller. The emerging model is two to three humans plus a fleet of specialized agents, organized not by function but by outcome. The humans set direction, evaluate quality, make judgment calls. The agents execute, coordinate, and scale. The org chart stops being a hierarchy of people and becomes a map of human-agent teams, each owning a complete workflow end to end.

For leaders, this changes the fundamental question. Not “how many people do we need to hire?” but “how many agents per person is the right ratio, and what does each person need to be excellent at to make that ratio work?” The answer to the second question is the same thing it’s always been — judgment, taste, domain expertise, the ability to know whether the output is actually good — but the leverage those skills provide just multiplied by the number of agents each person can direct.

Dario Amodei, Anthropic’s CEO, put 70 to 80% odds on a billion-dollar solo-founded company emerging by the end of 2026. Sam Altman has a betting pool among tech CEOs on the same question. Whether or not you believe the extreme version, the direction is undeniable: the relationship between headcount and output just broke, and the organizations that figure out the new ratio first will outrun everyone still hiring linearly.


## **Where Two Weeks Becomes Two Months**

The C compiler took two weeks. Nearly 2,000 automated sessions. Sixteen parallel agents. Cost: $20,000. Output: a production-grade compiler that builds the Linux kernel.

In January, the longest sustained autonomous coding run that anyone had publicly documented was in the range of hours. Seven hours at Rakuten was considered remarkable. Two weeks — continuous, autonomous, multi-agent coordination across 14 days — was the kind of capability that serious people projected might arrive by 2027.

It arrived in the first week of February 2026.

Follow the trajectory honestly — and I’ll flag where I’m extrapolating versus reporting. Working memory expanded 5x in a single development cycle. Context windows went from 200K to 1M tokens in three months. Google DeepMind engineer Denis Teplyashin described their internal progression in a Google blog post: jumping from 128,000 tokens to 512,000 to 1 million, “and just recently, 10 million tokens in our internal research.” Ten million tokens. An entire Fortune 500 company’s codebase in a single context window.

By mid-2026, agents working autonomously for weeks will be routine rather than remarkable. By end of year, the agents that built a compiler in two weeks will be building full applications over months — not toy applications, production systems with architecture decisions, security reviews, test suites, and documentation, all handled by agent teams coordinating without human intervention. The trajectory from “hours” to “two weeks” took three months. The trajectory from “two weeks” to “months” may take less.

And the inference demand this generates — agents consuming tokens continuously, around the clock, across thousands of parallel sessions — is what makes the $650 billion in hyperscaler infrastructure spending look conservative rather than insane. Those data centers aren’t being built for chatbots. They’re being built for agent swarms running at a scale that nobody modeled because the capability didn’t exist until this week.


## **The Speed Is the Story**

The individual capabilities matter. But they’re not the story. The speed is.

Three months between Opus 4.5 and Opus 4.6. In that gap: a generational leap in every measurable dimension. Context. Retrieval. Reasoning. Coordination. All at once. OpenAI released GPT-5.3-Codex the same week. Anthropic’s response came twenty minutes later. The two most advanced AI companies on Earth are shipping frontier capabilities at a pace where the unit of competition is hours, not quarters.

CNBC called it the dawn of “vibe working.” The framing undersells what’s happening. This isn’t a vibe. It’s a new labor model. The C compiler wasn’t built by a human using an AI tool. It was built by AI agents working as a team. Rakuten’s deployment isn’t engineers getting AI assistance. It’s engineers managing AI teams — setting direction, evaluating output, allocating agent capacity the way a VP allocates headcount.

The vocabulary hasn’t caught up. We still say “AI tools” and “AI assistance” and “AI-powered features” to describe something that is functionally a new kind of workforce. Sixteen agents coordinating over two weeks to build a compiler isn’t assistance. It’s labor. The workers never sleep, never lose context, and get measurably better every three months.


## **What You Should Do This Week**

If you write code: run a multi-agent session on real work. Not a toy problem. A piece of your codebase with actual technical debt. Watch how the agents coordinate. The experience changes your model faster than any benchmark.

If you don’t write code: open Claude Cowork and hand it a task you’ve been procrastinating on — a competitive analysis, a financial model, a content audit across your last quarter’s output. Describe the outcome you want, not the steps to get there. See what comes back. The gap between what you expect and what you get is the gap between your current mental model and where the tools actually are.

If you manage people: look honestly at the twenty hours a week your team spends on operational coordination. Ticket routing. Dependency tracking. Status syncs. Cross-team handoffs. Ask which of those hours require human judgment and which are pattern matching. A system that autonomously manages a 50-person engineering org across six repos isn’t theoretical — it’s running at Rakuten right now.

If you run an organization: the question has moved. Not “should we adopt AI?” but “what’s our agent-to-human ratio, and what does each human need to be excellent at to make that ratio work?” Rakuten runs five tasks per developer — four delegated to Claude, one human-led. StrongDM runs fully autonomous. The operating model just forked, and the gap between the branches widens weekly.

The people who’ve already reorganized around this — who run parallel agent sessions, who describe outcomes instead of procedures, who have internalized that the question isn’t “can AI help me?” but “how do I orchestrate agents to do this?” — those people are operating in a different month from everyone else. The debate about whether AI is overhyped ended this week — sixteen agents built a compiler, a 50-person engineering org got managed by software, and two reporters with no engineering background built a project management tool in an hour.


## **Welcome to February**

Here is where we are. February 11, 2026.

AI agents can build production-grade compilers in two weeks. They can manage engineering organizations autonomously. They can discover hundreds of security vulnerabilities that human researchers missed. They can build your competitor’s product in an hour for the cost of lunch. They can coordinate in teams, resolve conflicts, and deliver at a level that didn’t exist eight weeks ago.

None of this was possible in January.

And nobody knows what the endpoint is. Two weeks to build a compiler. Two months to build an application? Two years to build — what, exactly? The agents are improving faster than the people directing them can articulate what to ask for. The trajectory from “thirty minutes” to “two weeks” took twelve months. The trajectory from “two weeks” to “months” may take less. At some point on this curve — and nobody can tell you when — the limiting factor stops being the agent’s capability and starts being the human’s ability to specify what they actually want and evaluate whether the result is right.

That’s the tension underneath all the benchmark scores and deployment numbers and revenue-per-employee ratios. The agents are here. They work. They’re getting better at a pace that makes quarterly planning look like a joke. But the harder question — the one that Rakuten’s engineers and McKinsey’s org designers and every leader trying to figure out next quarter’s headcount plan is quietly confronting — is whether the humans setting the objectives can keep up with the systems executing them. Whether judgment and taste and the ability to say “no, not that, this” can scale at the same pace as inference compute. Whether your org chart, your hiring plan, your career development framework, your entire theory of how work gets organized — whether any of it survives contact with a world where small teams generate hundreds of millions in revenue and a 50-person engineering team gets managed by software.

January is out of date. The agent world is here. The question isn’t whether you’ve noticed. The question is whether you — and your organization, and your industry — are asking the right things of systems that are already more capable than you expected and less capable than they’ll be next month.

Welcome to February. It’s moving fast and the fog is thick.

[![](https://substackcdn.com/image/fetch/$s_!_1G8!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb786ab6b-6f0d-4809-93f9-c952687ce081_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!_1G8!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb786ab6b-6f0d-4809-93f9-c952687ce081_1024x1024.png)
