---
title: "Stop Asking How to Get an AI Job. Start Asking How to Turn Your Job Into One."
author: "Nate Jones"
published: 2025-11-18
url: https://natesnewsletter.substack.com/p/stop-asking-how-to-get-an-ai-jobstart
audience: everyone
scraped_at: 2026-01-05 19:11:38
---

Everyone is saying 2026 is the year of AI jobs.

And they mostly mean go out and find those roles.

They’re wrong.

The point for 95% of us isn’t the AI job we go and get somewhere else.

Instead, we need to be asking: “How do I turn the job I already have into an AI job?”

If that feels unsettling, that’s fair—most of us have never been taught how to do this.

This is all so new!

But here’s the reality: most of us won’t switch into an AI-title role. AI will just quietly change how our existing jobs work.

And the hard truth is this: either you design the AI-native version of your job, or someone else does it for you—and that’s what this piece is about helping you avoid.

That sounds abstract, so let me make it concrete: if you don’t figure out how to design your AI role, someone else in your organization becomes “the person who knows how to wire AI into our workflows.”

So your work gets decomposed and partially automated without your input. You find out about the new process when it shows up in your inbox (or Teams), not in the planning meeting.

But there’s another option. You can become the person who can say, “Here’s what we automate, here’s what stays human, here’s how we keep it safe.” That’s the person managers ask for input, not the person they surprise with a new process.

If you think I’m kidding, I’m not. People leaders talking to me are all looking for people like this *within existing roles.* Sothis isn’t a thought experiment. This is the shape of your day job a year from now.

I’m writing this now because 2025 has given us enough agentic rollouts and experimentation to know that AI agents actually work. The stack is finally stable enough for non-specialists to do meaningful work inside their roles. And that’s actually good news for you! Because it means you’re not late, you’re arriving right when the tools and guardrails are finally usable.

So who am I actually talking to here? This piece is for you if you’re in engineering, in product, in marketing, ops, finance, support, legal— especially managers and senior ICs at orgs that already have ChatGPT Enterprise, Copilot, Gemini, or internal bots.

It’s also for you if you’re not there yet, but you’re looking to show you can fill one of those roles. Why? Because to get one of these roles in 2026, you’ll be expected to be able to think, interview, and frame your work in terms of AI agents.

Here’s what’s in the box:

- **A clear map of where AI hits your job first:** The specific categories of work most likely to be automated or heavily assisted across job families
- **Three mental models to reason about AI at work:** How to talk about (and think about) AI in you role in the way leadership will expect in 2026
- **A concrete way to decompose your role into workflows:** How to turn “I do marketing” into explicit, repeatable workflows that AI can help with
- **A four-step roadmap to turn your job into an AI job:** Map your work like a systems designer, use the tools your company already has, ship one meaningful AI-augmented workflow, and plug into the platform and security people
- **And a custom prompt to help you develop a custom path forward:** Decompose your job and spot solid AI workflow integration points—something you can actually use, not just read about

My whole goal here is to give you a practical kit you can use on your own job.

Look, most people have never been asked to think about their work this way, which is exactly why it’s such an advantage if you start. If you can find the bits of the work that are AI workflow-able, and if you lead the way on those yourself, you’ll get the chance to define what YOU want your role to be as it evolves.

And you don’t get that every year. 2026 is going to be one of those special years, one of those pivotal years when we get to shape our careers. Let’s make the most of it!


## [Grab the AI Workflow Architect Prompt](https://www.notion.so/product-templates/AI-Workflow-Architect-2af5a2ccb52680e397c4c41da59085ac?source=copy_link)

Use this prompt when you want to turn your *existing* job into an AI-native job without changing roles, titles, or breaking your company’s rules.

It walks you through a structured, step-by-step process: mapping your real workflows, identifying which steps are good candidates for AI, designing safe “AI-augmented” versions of those steps using approved tools, and then generating concrete, reusable prompts you can run every week.

The goal isn’t to fantasize about a new AI career; it’s to redesign the way your current job actually gets done—keeping you in the driver’s seat while AI drains the repetitive, checkable work out of your day.

---


# Stop Asking How to Get an AI Job. Start Asking How to Turn Your Job Into One.

My inbox is drowning in the same question: “How do I get an AI job?” Wrong question. The right question—the one that actually matters for 95% of you reading this—is: “How do I turn my current job into an AI job?”

In 2026, the people who win are the ones who take the job they already have and quietly turn it into an AI job. Not by changing careers. Not by becoming a “prompt engineer.” But by changing how work actually gets done using the AI infrastructure their company is already rolling out.

We talk about changing jobs all the time, but that’s a tiny sliver of how AI will show up. For most of us, it’s going to reshape the work inside the job we already have.

Here’s what changed in 2025, how to think about it, and what to actually do in the next six to twelve months.


## What Actually Changed in 2025 (Under the Hood)

The first thing people need is context that isn’t vibes.

For the last two years, most people’s experience of AI has been a chat box, a writing assistant, maybe some code completion. That’s now the most superficial layer.

Under the surface, three big shifts happened in 2025 that changed how serious teams are approaching AI.


### AI Moved From a Chat Interface to an Infrastructure Layer

Architecture got standardized. Google’s “Introduction to Agents” paper didn’t invent agents, but it did something more important—it normalized them.

The paper gave enterprises a clear definition of an agent as a loop: goal, gather context, reason, act, observe. It provided patterns for multi-agent systems with recognizable roles—planners, retrievers, executors, validators, critics. It gave us a maturity model from simple tool-calling up through experimental self-improving systems that almost nobody is running in production. And it established design principles for the hard parts: identity for agents, budgets and rate limits, boundaries around what they can and can’t do.

Until we had that architecture, agents were mostly theoretical or narrow point solutions; 2025 made them something we can design around at scale.


### Security Stopped Being Hypothetical

2025 was the year of shadow IT: bring your own AI to work and hope security doesn’t notice. That window is closing fast.

Security and IT teams have now had a year to inventory usage, approve tools like ChatGPT Enterprise and Claude, and lay down basic guardrails. Increasingly, the tools that are allowed are inside the fences.

At the same time, we saw real-world incidents where agents were used as the operational layer in cyber-espionage campaigns. The lesson was blunt: model guardrails aren’t enough. You need orchestration-level controls—identity, permissions, logs, human oversight at key decision points.

This changes how CISOs look at AI adoption, how CIOs think about tool access and permissions, how regulators think about accountability. The meaningful AI work in 2026 will be done in partnership with your security and platform teams, not around them.


### Enterprises Learned Where Agents Actually Work

This is the biggest one. Across hundreds of deployments in 2025, the pattern is boringly consistent. Agents are reliable and deliver strong ROI when the work is bounded in scope, objectively verifiable, repetitive, and has clearly defined inputs and outputs.

Think about back-office operations: processing claims, reconciling accounts, checking documents for compliance. In practice, this means triage—routing support tickets, qualifying leads, prioritizing queues. It means customer support flows where you’re executing the same decision tree hundreds of times a day. It includes document workflows where you’re pulling data from PDFs and forms, checking them against policies, filling templates, generating standard letters.

Not “invent our product strategy.” Not “make high-stakes decisions with ambiguous tradeoffs and organizational nuance.” Just “execute this same twelve-step process ten thousand times a week without getting tired, without making careless mistakes, without needing breaks.”

So 2025 gave us clarity on four critical questions: What are agents? How do they operate at scale? Where are they safe and useful? Where are they dangerous if you’re sloppy?

If your work fits that pattern, it’s in the first wave.


## Three Mental Models You Need to Survive 2026

If I had to condense what people must internalize to survive this year, it’s three mental models. Not tools, not techniques, but fundamental shifts in how you think about AI and work.


### Mental Model One: AI as a Collaborator on Structured Work, Not a Magic Brain

LLMs are pattern machines. They’re very good at transforming text and code, mapping messy inputs to structured outputs, following explicit instructions, and doing the same thing a thousand times without getting bored.

They’re not inherently good at making high-stakes decisions with ambiguous tradeoffs, understanding your organizational politics, knowing your context unless you give it to them, or respecting boundaries you never defined.

The right question is never “Can AI do my job?” The right question is: “Which parts of my job are repetitive, checkable, describable, and verifiable, and how do I turn those into workflows an AI can run or assist with?”

The catch is simple: if you can’t describe the work clearly enough to write it down in a structured way, the model has no chance.

But if you can decompose your work into explicit steps with clear inputs, clear decision logic, and clear outputs, then you can start thinking about where AI slots in. Not to replace you, but to handle the repetitive, boring, checkable parts while you focus on the judgment calls, the exceptions, the strategy.


### Mental Model Two: Agents Plus Orchestration Are the New Middleware

Middleware has always existed in our software stacks. In between backend and frontend, there has always been a piece that translates. That part of the stack just got intelligent—through agents.

An agent is just a loop around a model with tools, state, and decision logic. That’s it. The label doesn’t matter. What matters is the orchestration—the infrastructure layer that makes agents actually useful and safe at scale.

Let me break down what orchestration means in practice:

- What tools can the agent use?
- Under which identity is it operating?
- With what budget and rate limits?
- What actions require human approval before execution?
- What does the agent do when it’s uncertain or encounters an exception?

This is the part most people don’t see because it’s not visible in the chat interface. But for 2026, it’s crucial that you at least understand the vocabulary, even if you’re not implementing it yourself.

MCP or equivalent standards define how models talk to tools and data. Agent-to-agent protocols govern how teams of agents coordinate—how a planner agent hands off to a retriever agent, how an executor agent reports back to a validator agent. Control planes and gateways serve as chokepoints where organizations enforce policy and observe behavior. Identity systems treat agents as first-class actors with roles and permissions, not anonymous scripts running with your credentials.

You don’t have to implement this yourself. Very few people will. But if you want to be taken seriously in conversations about AI adoption in your organization, you need to be able to talk about your AI workflows in these terms. That makes you translatable. That makes you accessible to the people who will be building these systems.


### Mental Model Three: Governance Isn’t a Bolt-On—It’s the Operating System

Governance is not a bolt-on. It’s becoming the operating system. If your AI adoption story doesn’t include security, privacy, auditability, and human oversight, it’s not a serious story. Full stop.

So you have to get concrete. Where would you allow AI to act autonomously? Where would you allow it to only draft, not send? Where would you require a human approver?

And on the data side: What gets logged, and who can inspect those logs? How do you shut something down safely when it misbehaves or starts producing garbage?

This is no longer just the CISO’s problem. If you’re the person designing AI-augmented workflows in your function, you own part of that governance whether you’ve been told that explicitly or not. AI agents will not roll out successfully if they don’t know your local information and data—your customer records, your internal policies, your product specs, your pricing sheets. And they won’t get that access without proper governance in place.


## Where AI Will Actually Reshape Your Job

Now the part people care about: what does this mean for my work?

Fundamentally, you need to think of your job as a stack of workflows. Your job is going to be decomposed, whether you’re the one doing it or not.


### Every Knowledge Job Is a Stack of Workflows

You don’t “do marketing.” You run campaigns, create briefs, analyze performance, manage stakeholders. You don’t “do product.” You collect requirements, prioritize features, write specs, review designs, coordinate launches. In reality, finance is a set of recurring workflows: reconciling accounts, forecasting budgets, analyzing variances, producing reports.

Each of those decomposes further. Take “run campaigns” as an example. There’s a trigger—maybe it’s the beginning of a quarter, maybe it’s a product launch, maybe it’s a competitor move. There are inputs—past campaign performance, current budget, audience segments, creative assets. There are transformations—you analyze what worked before, you draft messaging, you build targeting criteria. There are decisions—which channels to use, how much to spend, what success looks like. There are outputs—campaign briefs, media plans, budget allocations. And there are checks—how do you verify the targeting won’t waste money?

AI slots into that structure. It doesn’t replace it. AI will handle the boring and repetitive parts of those workflows. It’s up to you to figure out what that looks like in your role. It doesn’t magically “do marketing” for you. But it can absolutely help with specific steps in that workflow.


### The Parts AI Will Eat First

Across industries, the same categories keep getting automated or heavily assisted first, and the pattern is remarkably consistent.

**Triage and routing.** Classifying tickets, leads, cases, and requests into categories. Assigning priorities and queues based on defined criteria. Escalating high-priority items and routing routine ones to the right team. This is bounded, repetitive work with clear decision logic, and AI is already very good at it.

**Summarization and synthesis.** Turning raw text and data into briefs, status updates, and executive summaries. Producing first drafts from structured inputs. Taking ten documents and pulling out the three key points for a decision-maker. Taking a week of customer support tickets and identifying the top three emerging issues. This is transformative work with clear inputs and outputs, and AI handles it well.

**Policy and rule application.** Checking documents against policies and flagging violations or anomalies. Reviewing contracts for standard clauses and missing terms. Verifying that expense reports match company guidelines. Proposing standard responses based on defined scenarios. This is rules-based work that’s tedious for humans and straightforward for AI.

**Repetitive document workflows.** Pulling data from forms and PDFs and putting it into structured formats. Filling templates with the right information from the right sources. Generating standard letters, emails, and reports that follow established patterns. This is high-volume, low-judgment work that burns human time and attention.

**Glue work across tools.** Moving information between systems that don’t talk to each other. Normalizing formats so data from one tool works in another. Keeping trackers and dashboards up to date so people have current information. This is the invisible work that keeps organizations running but adds zero strategic value.

If you look at your job honestly, a non-trivial percentage is in these buckets. That is what’s going to move first. Not because AI is coming for your job, but because organizations are going to recognize that having expensive knowledge workers do repetitive, checkable work is a terrible use of resources.


### The Parts That Stay Human (For a Long Time)

Also important: there are parts AI is not going to do well for a while, and you need to know where those boundaries are.

Negotiation, trust-building, and politics—the work of building relationships, reading a room, understanding what’s unsaid. Deciding which problems to solve and setting strategy under uncertainty, when you’re operating with ambiguous information and high stakes. Handling truly novel, messy situations when something breaks in a way you’ve never seen before. And being accountable when things go wrong—organizations need humans to own outcomes and explain decisions.

So the arc is this: AI drains the repetitive, checkable work out of your role.

Your value shifts toward defining the workflows, supervising them, handling exceptions, and choosing what to build or improve next. If you want to stay relevant, you move into that supervisory, architectural, judgment layer sooner rather than later.


## What You Actually Need to Do in the Next Six to Twelve Months

Here’s the part people need: not “play with tools,” but an adult roadmap for taking control of this transformation.


### Step One: Map Your Work Like a Systems Designer

Pick three to five recurring workflows you own. Not your entire job, just the repeating patterns.

For each workflow, write down the trigger (what starts the work?), the inputs (what information do you need?), the steps (what do you actually do?), the decisions (where do you make judgment calls?), the outputs (what do you produce?), how you verify it’s correct (what checks do you run?), and what happens when something goes wrong (what’s your exception handling?).

You’re not coding anything. You’re not building infrastructure. You’re building a mental API for your own job, making explicit what’s usually implicit.

This alone puts you ahead of 90% of your peers, because most people have never made their own work explicit. They just do it, often inefficiently, often inconsistently, often in ways that can’t be taught to anyone else. Making your work explicit is the first step toward improving it, whether AI is involved or not.


### Step Two: Learn to Express Those Workflows to the AI Tools You Already Have

Most companies by now either have or are piloting ChatGPT Enterprise, Copilot, Gemini, or other embedded AI assistants. Some have internal bots or workflow automation platforms with AI features. Use the surfaces that are already approved and learn how to work with them effectively.

Even if it’s just prototyping in ChatGPT Enterprise, Copilot, or Gemini, get a living feel for what AI agents working with you would look like. Learn to give AI structured instructions scoped to a specific workflow, not vague requests. Feed it clean inputs—tables, bullet lists, JSON-ish structures—not walls of unformatted text. Ask for outputs in formats you can use directly: checklists you can follow, email drafts you can edit and send, status updates you can paste into Slack, SQL queries you can run, whatever fits your role. Iteratively refine until you have a reliable pattern.

Your goal is to develop stable recipes for your workflows. Not “AI wrote me an email once and it was kind of good,” but “I have a prompt template that consistently produces 80% of the work for this weekly status report, and I spend 10 minutes reviewing and refining instead of 45 minutes writing from scratch.”

Don’t spin up rogue infrastructure. Prototype inside the tools you have so you’re ready when IT comes with a proper agent initiative.


### Step Three: Ship an MVP of One Meaningful AI-Augmented Workflow in Your Function

Pick something that runs weekly or daily, is painful or time-consuming, has clear success criteria, and has low blast radius if it goes wrong. Something where a mistake won’t cost you your job or damage an important relationship, but where success will be obvious.

Map it using the framework from step one. Use your existing AI tools to automate or heavily assist 60–80% of the steps. Keep yourself in the loop for approval and exceptions—you’re not trying to eliminate human involvement entirely, you’re trying to shift it toward oversight and judgment.

Measure the impact: time saved; error rate; throughput; how often you have to intervene to fix something or handle an exception.

This doesn’t have to be production-grade—what matters is that it’s real enough to show what’s possible and where the guardrails need to be.

Document this. Turn it into a one-pager (yes, it’s not just for PMs anymore). Bring numbers. “We were spending six hours a week on lead qualification. Now we spend ninety minutes reviewing AI-generated summaries and flagging edge cases. Throughput went up 40% and our false positive rate dropped from 15% to 8%.”

That one workflow—done right—changes how your team sees you. You shift from “the person who executes the work” to “the person who redesigns how the work is done.” That’s a fundamentally different value proposition.


### Step Four: Build a Relationship With Whoever Owns AI and Platform in Your Org

This part is usually completely missing from “learn AI” advice, but it’s critical.

Find the data or AI platform team, the head of AI initiatives, or whoever is responsible for governance and infrastructure. Show them what you’ve done. Not in a “look what I built without permission” way, but in a “I’ve been experimenting within approved tools and I want to do more of this inside the guardrails” way.

Ask them:

- How do I do more of this inside the guardrails?
- What patterns or tools are you standardizing on that I should be using?
- Where are you nervous about AI usage in my function that I should be aware of?
- Where are the highest-priority workflows you want teams to modernize?

Now you’re no longer a random person. You’re a champion who speaks both the messy business reality and the constraints of the platform. You understand what the work actually looks like on the ground, and you understand why security and governance matter. That’s a very valuable position to be in.


## What Not to Do

People also need a “do not cross” list, because there are failure modes that will waste your time or get you in trouble.

**Don’t chase every new model.** Claude whatever, GPT-6, Gemini 3.0, whatever comes next—yes, the frontier models will keep improving. Your relative advantage won’t come (only) from tracking each release. It will come from making your function work differently, from having workflows that leverage AI effectively regardless of which specific model your organization standardizes on. You pick the model to suit that workflow (and don’t worry I’ll give you clues along the way).

**Don’t build bespoke infrastructure unless it’s literally your job.** If you’re not on the platform or infrastructure team, you shouldn’t be spinning up your own vector database, building your own RAG cluster, wiring together APIs to production systems. That’s how you create shadow IT, security vulnerabilities, and technical debt that someone else will have to clean up.

**Don’t settle for toy demos either.** “Look, it wrote an email” is not interesting anymore. What matters is: Does this run every week? Does someone other than you rely on it? Does it save real time or money? Is it robust enough that people would notice if it stopped working?

**Don’t assume your job is safe because your title sounds “creative” or “strategic.”** Creativity and strategy still matter, but a surprising amount of jobs with those labels are filled with repetitive, checkable tasks. The creative director who spends half their time resizing assets for different platforms. The strategist who spends six hours a week pulling data into PowerPoint. That’s what will move first.


## The Real Question

The question for 2026 is not “Will AI affect my job?” It’s “Do I want to be the person who designs the new version of this job, or the person who waits for it to arrive?”

You don’t need to become an AI engineer. You don’t need to build agents from scratch.

You need to:

- Understand how your work decomposes into workflows
- Learn to use the AI infrastructure your company is already investing in
- Ship one or two real AI-augmented workflows that other people rely on
- Plug yourself into the governance conversations so you’re part of the solution, not an exception

This is what I wish I could tell the 95% of people who aren’t switching into an “AI role” next year. This is how you stay in the driver’s seat as AI agents show up everywhere.

And if you start now, you’ll be a year ahead of most of your peers.

[![](https://substackcdn.com/image/fetch/$s_!oFCU!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F098f19a5-4a20-4716-9428-636170efe224_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!oFCU!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F098f19a5-4a20-4716-9428-636170efe224_1024x1024.png)
