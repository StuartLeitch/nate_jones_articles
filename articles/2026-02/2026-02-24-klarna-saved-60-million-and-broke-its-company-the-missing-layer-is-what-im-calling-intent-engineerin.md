---
title: "Klarna saved $60 million and broke its company. The missing layer is what I'm calling intent engineering + 2 prompts to find yours"
author: "Nate Jones"
published: 2026-02-24
url: https://natesnewsletter.substack.com/p/klarna-saved-60-million-and-broke
subtitle: "Watch now | Earlier this year, Klarna’s Q3 earnings revealed its AI agent now does the work of 853 full-time employees and has saved the company $60 million."
audience: everyone
scraped_at: 2026-02-24 12:00:18
---

Klarna’s Q3 2025 earnings revealed its AI agent now does the work of 853 full-time employees and has saved the company $60 million. But six months earlier, its CEO had already admitted publicly that the AI strategy had cost Klarna something far more valuable — and he’s still trying to buy it back.

This is not another “AI was overhyped” story. It’s the opposite. The AI worked too well. And that distinction — between AI that fails and AI that succeeds at the wrong thing — is the most important unsolved problem in enterprise AI right now. It’s bigger than context engineering, though it includes it. It’s bigger than prompt engineering, which now looks like a warm-up act. The right name for what’s missing is intent engineering: the discipline of making organizational purpose — goals, values, tradeoffs, decision boundaries — machine-readable and machine-actionable so that when you deploy an autonomous system, it optimizes for what your company actually needs, not just what it can measure.

The disorienting part is worth sitting with. MIT reports 95% of generative AI pilots fail to deliver measurable impact. Gartner predicts 40% of agentic AI projects will be cancelled by 2027. And yet the money has never flowed faster — Deloitte found the majority of enterprises putting 21–50% of their digital transformation budgets into AI automation. These numbers don’t contradict each other. They describe organizations that have solved “can AI do this task?” and completely failed to solve “can AI do this task in a way that serves our organizational goals?”

That’s the intent gap. Klarna is the clearest case study. Its AI agent handled 2.3 million conversations in its first month and cut resolution times from eleven minutes to two. Then the CEO went on Bloomberg to explain why the strategy had backfired — and started hiring humans back. The full story is more nuanced than the headline, and it illustrates exactly why “the AI worked” and “the AI failed” can both be true at the same time.

The progression matters: prompt engineering told AI what to do in a single session. Context engineering — where the industry is right now — tells AI what to know. Intent engineering tells AI what to want. And almost nobody is building for it yet.

**Here’s what’s inside:**

- **The three disciplines.** Prompt engineering told AI what to do. Context engineering tells AI what to know. Intent engineering tells AI what to want — and almost nobody is building for it yet.
- **The Klarna post-mortem and the Copilot stall.** How $60 million in AI savings destroyed the thing that actually made customers stay — and why 90% Fortune 500 Copilot “adoption” producing just 3.3% paid uptake is the same failure at different speed.
- **Three missing layers.** Unified context infrastructure, coherent AI workflow architecture, and organizational alignment frameworks — what each one prevents, and what it costs to skip.
- **Why this is fractal.** The same intent failure breaking enterprise AI deployments is breaking your personal AI workflow right now. The fix is the same architecture at a different scale.
- **The prompts.** An intent audit and a delegation framework you can run this week to find out whether your agents actually know what you’re optimizing for.

I want to show you how this happened — and why the fix is architectural, not inspirational.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260214_b63_promptkit_1)

These prompts exist because I’ve watched too many teams — and too many individuals — deploy agents that optimize beautifully for the wrong objective. The intent audit forces you to take your three highest-stakes workflows and pressure-test whether your AI tools actually know what “good” looks like for each one — not as a vague system prompt instruction, but as structured decision boundaries, escalation triggers, and tradeoff hierarchies an agent can execute against. The delegation framework makes you define, for a specific workflow, exactly which decisions an agent can make autonomously, which require you in the loop, and where the hard boundaries live that can’t be crossed regardless of context. If you find yourself writing “use good judgment” where the decision logic should go, that’s the diagnosis. Your agents are running without intent, and every autonomous decision is a coin flip between optimization and damage.

These prompts won’t build your full intent layer. They’ll show you exactly where it’s missing — and which missing piece is costing you the most.


## **The age of Intent Engineering**

Klarna’s Q3 2025 earnings revealed its AI agent now does the work of 853 full-time employees and has saved the company $60 million. But six months earlier, its CEO had already admitted publicly that the AI strategy had cost Klarna something far more valuable — and he’s still trying to buy it back.

This is not another “AI was overhyped” story. It’s the opposite. The AI worked too well. And that distinction — between AI that fails and AI that succeeds at the wrong thing — is the most important unsolved problem in enterprise AI right now. It’s bigger than context engineering, though it includes it. It’s bigger than prompt engineering, which now looks like a warm-up act. I’m going to call it what it is: intent engineering. The discipline of making organizational purpose — goals, values, tradeoffs, decision boundaries — machine-readable and machine-actionable so that when you deploy an autonomous system, it optimizes for what your company actually needs, not just what it can measure.

The timing matters. MIT found that 95% of generative AI pilots fail to deliver measurable impact. S&P Global found that 42% of companies abandoned most of their AI initiatives in 2025 — up from 17% the year before. Gartner predicts 40% of agentic AI projects will be cancelled by 2027. And yet the technology has never been better. The frontier models are extraordinarily capable. Agents are running in production at 57% of organizations surveyed by LangChain. The money is flowing — Deloitte found 57% of enterprises putting 21–50% of their digital transformation budgets into AI automation, with another 20% investing more than half. None of these numbers contradict each other. They describe the same phenomenon: organizations have solved “can AI do this task?” and completely failed to solve “can AI do this task in a way that serves our organizational goals?”

That’s the intent gap. And Klarna is the clearest illustration of how it works.

The backstory, briefly: in early 2024, Klarna rolled out an OpenAI-powered customer service agent. It handled 2.3 million conversations in its first month, across 23 markets, in 35 languages. Resolution times dropped from eleven minutes to two. The CEO projected $40 million in savings. Then customers started complaining — generic answers, robotic tone, no ability to handle anything requiring judgment. By mid-2025, CEO Sebastian Siemiatkowski told Bloomberg that cost had been “a too predominant evaluation factor,” and the result was “lower quality.” Klarna began recruiting human agents again — initially as freelancers in a pilot program — to handle the complex interactions where AI couldn’t substitute for judgment. The AI still handles two-thirds of inquiries, and Klarna has since claimed satisfaction scores are on par for simple queries. But the reversal signaled something the metrics hadn’t captured.

Most people tell this story as proof that AI can’t handle nuance. That’s the comforting reading, and it’s wrong. The AI agent was extraordinarily good at resolving tickets fast, and that was the wrong objective. Klarna’s organizational intent wasn’t “resolve tickets fast.” It was “build lasting customer relationships that drive lifetime value in a competitive fintech market.” Those are profoundly different goals, and they require profoundly different decision-making at the point of interaction.

A human agent with five years at the company knows the difference intuitively. She knows when to bend a policy, when to spend three extra minutes because the customer’s tone says they’re about to churn, when efficiency is the right move and when generosity is. She knows this because she absorbed Klarna’s actual values — not the ones on the website, but the ones encoded in the decisions managers make every day, in the stories veterans tell new hires, in the unwritten rules about which metrics leadership actually cares about when push comes to shove.

The AI agent knew none of it. It had a prompt and plenty of context. What it didn’t have was intent. And the gap between context and intent is where $60 million in savings turned into a CEO on Bloomberg explaining why he broke his own company.


## **The progression that matters**

I want to be precise about how we got here, because the naming matters. Naming things is how industries create shared understanding, and shared understanding is how they stop making the same mistakes.

Prompt engineering was the first discipline. It was individual, synchronous, and session-based. You sat in front of a chat window, you crafted an instruction, you iterated on the output. The skill was personal, the value was personal, and the ceiling was whatever one person could extract from one conversation. This is the era that produced a thousand “how to write the perfect prompt” blog posts and a brief, strange moment where “prompt engineer” appeared on LinkedIn as a job title.

Context engineering is the second discipline, and it’s the one the industry is currently grappling with. Anthropic published the foundational piece in September 2025, defining it as the shift from crafting isolated instructions to curating “the entire information state that an AI system operates against.” LangChain’s Harrison Chase put it more bluntly in a Sequoia Capital interview: “Everything’s context engineering. Context engineering is such a good term. I wish I came up with that term. It actually describes everything we’ve done at LangChain without knowing that that term existed.” Context engineering is where the action is right now — building RAG pipelines, wiring up MCP servers, structuring organizational knowledge so agents can access it. It’s necessary. It’s also not sufficient. And I think the industry is about to discover that in a very expensive way.

Intent engineering is the third discipline, and it’s the one almost nobody is building for yet. Context engineering tells agents what to know. Intent engineering tells agents what to want. It’s the practice of encoding organizational purpose into infrastructure — not as prose in a system prompt, but as structured, actionable parameters that shape how agents make decisions autonomously. It’s the layer that would have told Klarna’s AI agent: “Yes, you can resolve this ticket in 90 seconds, but this customer has been with us for four years and their tone indicates frustration. Spend the extra time. Offer to connect them to a specialist. The goal isn’t ticket velocity. The goal is retention.”

Without intent engineering, you get what Klarna got: a technically brilliant agent optimizing for the wrong objective. You get what Deloitte’s 2026 State of AI in the Enterprise report found across 3,235 leaders in 24 countries: 84% of companies haven’t redesigned jobs around AI capabilities, and only 21% have a mature model for agent governance. You get what S&P Global documented: the average organization scrapping 46% of its AI proofs-of-concept before production, with the abandonment rate more than doubling year-over-year.

Those numbers describe an intent failure, not a technology failure — the models work, the context pipelines are getting better. What’s missing is the organizational infrastructure that connects AI capability to organizational purpose.


## **The scale of the Intent Gap**

I cited the failure stats above. The other side of the ledger is what makes this so disorienting.

The investment is massive and accelerating. Deloitte’s 2025 Tech Value survey found that 57% of respondents were putting 21-50% of their digital transformation budgets into AI automation, and 20% were investing 50% or more — an average of $700 million for a company with $13 billion in revenue. KPMG’s Q4 2025 AI Pulse Survey showed capital flowing, ROI confidence rising, and agents moving from pilots to professionalized platforms. Gartner predicts that by 2028, 15% of day-to-day work decisions will be made autonomously by AI agents, up from effectively zero in 2024.

So the money is real. The deployments are real. And the results are... mostly not there. BCG found that 74% of companies globally have yet to show tangible value from AI. McKinsey’s 2025 State of AI survey found roughly two-thirds of organizations remain stuck in experimentation or piloting — only about a third have scaled AI beyond individual use cases. These numbers coexist with the investment numbers. They don’t contradict them. They describe the same pattern from a different angle: technical capability racing ahead of organizational readiness to direct it.

Look at what happened with Microsoft Copilot, one of the most heavily invested enterprise AI products in history. Microsoft poured billions into infrastructure, embedded AI into every Office application, and launched an aggressive enterprise sales campaign. By late 2025, Satya Nadella was telling investors that more than 90% of the Fortune 500 “use” Microsoft 365 Copilot. And then Microsoft disclosed the number that mattered.

In January 2026, Microsoft finally revealed it had 15 million paid Copilot seats — against a base of roughly 450 million commercial Microsoft 365 users. That’s 3.3% paid adoption after two years on the market and $37.5 billion in AI investment in a single fiscal quarter. Gartner’s 2025 survey found that only a single-digit percentage of enterprises had moved beyond pilot deployments. Bloomberg reported Microsoft slashing internal sales targets after the majority of salespeople missed their goals. Even inside companies that signed six-figure Copilot deals, employees resisted — Reddit threads are full of engineers at multi-billion-dollar companies describing their organizations downgrading licenses because employees preferred ChatGPT.

The standard explanation for Copilot’s struggles centers on UX problems and model quality. Those are real issues. But they’re not the fundamental issue. The fundamental issue is that deploying an AI tool across an organization without organizational intent alignment is like hiring 40,000 new employees and never telling them what the company does, what it values, or how to make decisions. You get activity, not productivity. You get AI usage metrics in a dashboard and almost no measurable impact on what the organization is actually trying to accomplish — which is the intent gap showing up at a different altitude.


## **Three missing layers**

Time to get structural, because vague hand-waving about “AI transformation” is the enemy of actually doing it. The intent gap operates across three distinct layers, each at a different altitude. Getting any one of them right helps. Getting all three right is the difference between having AI tools and having an AI-native organization.

Layer One: Unified Context Infrastructure. This is the layer the industry is most aware of, and it’s still mostly unbuilt.

Right now, every team building agents is rolling their own context stack. One team pipes Slack data through a custom RAG pipeline. Another manually exports Google Docs into a vector store. A third built an MCP server that connects to Salesforce but not to Jira. A fourth team doesn’t know the other three exist.

This is what one analyst called the “Shadow Agents” problem, and it mirrors the Shadow IT crisis of the early cloud era — except the stakes are higher because agents don’t just access data, they act on it. Security and compliance teams can’t allow arbitrary, unvetted agents running on developer laptops to access critical systems like customer PII, financial data, or healthcare records. But without sanctioned infrastructure, that’s exactly what’s happening.

The Model Context Protocol, which Anthropic introduced in November 2024 and donated to the Linux Foundation in December 2025, is the most promising attempt at standardization. MCP has seen remarkable adoption — OpenAI, Google, Microsoft, and over fifty enterprise partners have committed to it. Anthropic reports monthly SDK downloads have surpassed 97 million. But protocol adoption and organizational implementation are different things. Having a USB-C standard doesn’t help if your company hasn’t decided which ports to install, who maintains them, or what gets plugged in.

The context infrastructure question isn’t ultimately technical. It’s architectural and political. Which systems become agent-accessible? Who decides what context an agent can see across departments? How do you version organizational knowledge so agents aren’t operating on stale information? How do you handle the fact that the sales team’s Slack context and the engineering team’s Slack context encode completely different institutional assumptions?

Deloitte’s 2025 survey found that nearly half of organizations cited data searchability (48%) and data reusability (47%) as top challenges blocking AI automation. As their analysts put it, the shift required is from traditional ETL data pipelines to enterprise search and indexing — “similar to how Google made the World Wide Web discoverable.” The data exists. The agents exist. The connective tissue between them — the organizational context layer — mostly doesn’t.

Layer Two: Coherent AI Worker Toolkit — And How Individual Capability Ladders Into Organizational Productivity.

Everyone is rolling their own AI workflow. One person uses Claude for research and ChatGPT for drafting. Another uses Cursor for code and Perplexity for fact-checking. A third has built a custom agent chain using LangGraph. A fourth is still copy-pasting into a basic chat window. None of them can articulate their workflow in a way that’s transferable, measurable, or improvable by anyone else.

This matters because the difference between individual AI use and organizational AI leverage is enormous. It’s the difference between having one good hire and having a system that makes everyone better. It’s the difference I’ve been writing about for a year — between AI activity (the 30% gains you get from bolting AI onto existing workflows) and AI fluency (the 300% gains you get from rethinking the workflow itself around AI capabilities).

But something I hadn’t fully worked out until recently: fluency doesn’t scale through training alone. It scales through shared infrastructure. Whether any individual person has Slack doesn’t matter much. Whether an agent can search fifty people’s Slack context, plus their docs, plus the project plan, plus the customer data — that’s what determines whether the agent can do organizational work rather than just individual tasks.

Deloitte’s 2026 report found that workforce access to sanctioned AI tools expanded by 50% in just one year — from fewer than 40% to around 60% of workers now equipped with AI tools. But of those workers with access, fewer than 60% use it in their daily workflow. Access is necessary but insufficient. Organizations are giving people tools without giving them — or their agents — the organizational context and alignment those tools need to deliver real value.

This is where Klarna’s story intersects with Copilot’s story intersects with the MIT data. Tools deployed without organizational infrastructure become expensive toys. The 74% of companies reporting no tangible value from AI aren’t failing because of models. They’re failing because there’s no shared understanding of how AI tools connect to organizational workflows, where agent automation should replace human effort, where it should augment it, and where human judgment remains non-negotiable.

Layer Three: Organizational Alignment Frameworks for Agents — Intent Engineering Proper.

This is the layer that doesn’t exist yet. It’s the one I think matters most. And it requires something genuinely new.

OKRs were designed for people. They encode human-readable goals. They assume human judgment about prioritization, tradeoffs, and exceptions. They assume a manager can look a direct report in the eye and say “here’s what matters this quarter” and trust that the report will interpret that guidance through a mesh of institutional context, professional norms, and personal judgment developed over months and years.

Agents don’t have any of that.

An agent doesn’t know your company’s OKRs unless you put them in its context window. It doesn’t know which tradeoffs your leadership team would prefer unless you encode those preferences in a way it can act on. It doesn’t know the difference between a decision that should be escalated and one it should make autonomously unless you’ve defined that boundary explicitly. And unlike a human employee, an agent won’t absorb your company culture through osmosis over six months of all-hands meetings, hallway conversations, and watching how senior people handle ambiguous situations.

When a human employee joins a company, alignment happens through a hundred informal mechanisms. They read the wiki. They watch how their manager makes decisions. They learn which Slack channels have real conversations and which are performative. They absorb tenets and principles not from a document but from watching those tenets get applied in ambiguous situations. They develop judgment. The organizational alignment of a human employee is a distributed, continuous, largely unconscious process that takes months and never fully completes.

None of that works for agents. Agents need explicit alignment, and they need it before they start working — not six months after. This means organizations need to develop something that mostly doesn’t exist yet: machine-readable expressions of organizational intent.

Think about what that actually requires. It’s not just “put the OKRs in the system prompt.” It’s a cascade of specificity that most organizations have never had to produce because humans could fill in the gaps.

At the top, you need goal structures that agents can interpret and act on. Not “increase customer satisfaction” — that’s a human-readable aspiration, not an agent-actionable objective. An agent needs to know: what signals indicate customer satisfaction in our specific context? What data sources contain those signals? What actions am I authorized to take to improve them? What tradeoffs am I empowered to make — speed versus thoroughness, cost versus quality — and where are the hard boundaries I cannot cross?

Below that, you need what I’d call delegation frameworks — tenets translated into decision boundaries. Amazon’s leadership principles work for humans because humans can interpret “customer obsession” through contextual judgment. An agent needs the principle decomposed: when customer request X conflicts with policy Y, here’s the resolution hierarchy. When data suggests action A but the customer expressed preference for B, here’s the decision logic. These aren’t rules in the traditional sense. They’re encoded judgment — the kind of organizational knowledge that a senior employee carries in her head after five years and a new hire absorbs gradually through osmosis. Agents need it on day one, in structured form, updated continuously.

And at the base, you need feedback mechanisms that actually close the loop. When an agent makes a decision, was it aligned with organizational intent? How do you measure that? How do you correct drift? OKRs for people include quarterly reviews where a manager says “you nailed this objective but the way you achieved it created problems over here.” What’s the equivalent for an agent that makes three thousand decisions a day?

This is exactly what happened at Klarna. The agent optimized for resolution speed because that was the objective it could measure. Nobody had encoded the objectives that mattered most — relationship quality, brand trust, customer lifetime value, the contextual judgment about when to be efficient and when to be generous. Those objectives lived in the heads of the human agents. They walked out the door carrying institutional intent that had never been made explicit.

The age of “humans just know” is ending. Intent engineering is the discipline of making what they know explicit, structured, and machine-actionable. Not because the humans are leaving (though some will), but because the agents arriving to work alongside them can’t function without it.


## **Why this hasn’t been built yet**

Before I sketch the solution, it’s worth understanding why organizations haven’t built the intent layer already. Three reasons.

First, the need is new. Before agents could run autonomously over long time horizons — making decisions in loops, calling tools, operating against organizational data for hours or days without human intervention — the intent alignment happened in real time, in the human’s head, at the point of prompting. The human was the intent layer. You’d paste some context into a chat window, write a prompt that encoded your goals implicitly, evaluate the output through your own judgment, and iterate. The agent never needed to understand organizational intent because you were standing right there, mediating every interaction. Long-running autonomous agents break that model completely. When an agent is making its three-hundredth decision at 2 AM with no human in the loop, the intent layer either exists in the infrastructure or it doesn’t exist at all.

Second, the people who understand organizational strategy — executives, product leaders, operations chiefs — are not the people building agents. And the people building agents — engineers, data scientists, AI platform teams — are not the people who understand organizational strategy. This is the classic “two cultures” problem, and it’s acute in AI because the technology moves so fast that the organizational thinkers can’t keep up and the technologists don’t think it’s their job. MIT found that AI investment is still viewed primarily as “a technology challenge for the CIO rather than a business issue that requires leadership across the organization.” That framing guarantees an intent gap. CIOs build infrastructure. Intent requires the CEO, the CFO, the COO — the people who actually decide what the organization values and how it makes tradeoffs.

Third, the prerequisite — making organizational intent explicit and structured — is harder than it sounds. Most organizations have never had to do it. Their goals live in slide decks, in OKR documents that people half-read, in leadership principles that get cited in performance reviews but rarely operationalized, in the tacit knowledge of experienced employees who know what to do in ambiguous situations because they’ve seen how the company handles them. Extracting that knowledge, structuring it, and maintaining it as a living system that agents can consume — that’s a new organizational muscle. Nobody has strong muscles they’ve never exercised.


## **What the solution architecture looks like**

The conversation needs to move from diagnosis to construction.

At the infrastructure level, you need what McKinsey’s QuantumBlack team recently called an “agentic mesh” — a composable, vendor-agnostic architecture that enables agents to operate across systems, tools, and models securely and at scale. MCP is the protocol layer. But the organizational implementation requires decisions about data governance, access controls, freshness guarantees, and semantic consistency that no protocol can make for you. The companies that build this well will treat it like they treated their data warehouse strategy in the 2010s — as a core strategic investment, not an IT project.

At the workflow level, you need what I’d call an organizational capability map for AI — a shared, living understanding of which workflows are agent-ready (fully autonomous), which are agent-augmented (human-in-the-loop), and which remain human-only, along with the context requirements and decision authorities for each. This isn’t a static document filed in Confluence. It’s an operating system that evolves as agent capabilities improve and as organizational context infrastructure matures. The companies that do this well will create a new role — something like “AI Workflow Architect” — that sits between engineering, operations, and strategy.

At the alignment level, you need the genuinely new thing: goal translation infrastructure that converts human-readable organizational objectives into agent-actionable parameters. This includes decision boundaries (what the agent can decide autonomously), escalation triggers (when the agent must involve a human), value hierarchies (how the agent resolves tradeoffs between competing goods), and feedback loops (how you measure and correct alignment drift over time).

Google’s Agent Development Kit is one of the earliest attempts to formalize this at a technical level, separating agent context into distinct layers — working context, session memory, long-term memory, and artifacts — each with specific governance. There’s also emerging academic work: a recent paper from researchers at Google DeepMind proposed five levels of AI agent autonomy — operator, collaborator, consultant, approver, and observer — each with different intent alignment requirements and human oversight models. These are early sketches. The integrated system — context infrastructure plus workflow mapping plus intent alignment, operating as a coherent organizational capability — that’s the white space. And it’s enormous.

If OKRs were the management innovation that let Intel align thousands of humans to shared objectives in the 1970s, intent engineering is the management innovation that lets organizations align hundreds of agents to those same objectives in 2026 — while those agents operate at speeds and scales no human manager can directly supervise. The parallel is direct. The urgency is greater. OKRs took twenty years to become standard management practice. We don’t have twenty years.


## **Your agents don't know your life**

This is where it connects to you, personally, right now.

The same three-layer gap that prevents organizations from capturing the full value of AI — missing context infrastructure, missing workflow coherence, missing intent alignment — exists at the individual level. You’re living it every day.

You don’t have a unified context layer for your own work. Your notes are in one app, your emails in another, your documents in a third, your project plans in a fourth. Your agent can see whatever you paste into the chat window. It can’t see the rest. You are manually performing context engineering every time you copy information from one system into a prompt — and you’re doing it imperfectly, because you’re human and you forget things, and the agent doesn’t know what it doesn’t know.

You don’t have a coherent model of your own AI-augmented toolkit. You use different tools for different tasks based on habit, not strategy. You haven’t mapped your workflows against AI capabilities in a systematic way. You haven’t identified which of your daily activities are candidates for full agent automation, which benefit from augmentation, and which should remain purely human. You’re optimizing locally — this task, this tool, this afternoon — when the gains come from optimizing systemically.

And you almost certainly don’t have explicit intent alignment for your own AI use. You’re prompting reactively — “help me with this thing right now” — rather than proactively: “here are my objectives for the quarter, here’s the context you need to understand them, here are the boundaries of what you should do autonomously and what you should flag for my attention.” You’re treating AI as a tool you pick up and put down. The people who are getting 10x results are treating it as a collaborator that operates against a persistent, structured understanding of what they’re trying to accomplish.

The individual version of the intent gap is this: your agent doesn’t know your life. It doesn’t know your goals, your constraints, your preferences, your communication style, your team dynamics, your quarterly priorities, or the seventeen things you’re juggling that create the real context for every decision you make. Every time you open a new chat window, you’re starting from zero — unless you’ve built your own intent layer.

The individual version of the alignment problem is this: you haven’t told your agent what “good” looks like for you. Not in a single prompt. In a persistent, evolving, structured way that lets the agent make judgment calls on your behalf without checking in every thirty seconds.

The people who figure this out at the individual level — who build their own context layers, map their own workflows, and create their own intent frameworks — will be the ones who build it at the organizational level. Because the skills are the same, the architecture is the same, the thinking is the same — just at different scales.


## **The race is intent, not intelligence**

The punchline reframes the entire AI strategy conversation for 2026.

For the past three years, the AI race has been framed as an intelligence race. Who has the smartest model? Who tops the benchmarks? Who has the biggest context window? That framing made sense when models were the bottleneck. Models aren’t the bottleneck anymore. Not for most organizational use cases. The frontier models — Opus 4.6, GPT-5.2, Gemini 3.1 — are all extraordinarily capable. The differences between them matter far less than the differences between organizations that can give them clear, structured, goal-aligned intent and organizations that can’t.

The race is now an intent race. Not who has the smartest AI, but who has built the organizational infrastructure that lets AI operate with the fullest, most accurate, most strategically coherent understanding of what the organization is actually trying to accomplish. The company with a mediocre model and extraordinary organizational intent infrastructure will outperform the company with a frontier model and fragmented, inaccessible, unaligned organizational knowledge — every time.

This means the most important AI investment in 2026 isn’t a model subscription. It’s not another copilot license. It’s organizational intent architecture — making your company’s goals, values, decision frameworks, and tradeoff hierarchies discoverable, structured, and agent-actionable. It’s building the alignment infrastructure that lets agents make decisions that aren’t just technically correct but strategically coherent. It’s developing the shared language and shared systems that let AI capability scale from one heroic engineer to forty thousand knowledge workers operating in concert.

Klarna’s story wasn’t “AI doesn’t work.” The AI worked brilliantly — that was the whole problem. It was so good at optimizing for the measurable objective that nobody noticed it was destroying the unmeasured ones. The hundreds of experienced human agents who left — through attrition and a hiring freeze Klarna maintained for over a year — took with them the institutional knowledge of what Klarna actually valued. That knowledge had never been documented because it had never needed to be. Humans just knew. The lesson isn’t to hire the humans back (though Klarna did). The lesson is to build the intent layer so the agents don’t need to absorb organizational values through osmosis — because they can’t.

Deloitte’s agentic AI strategy team recently described a future where agents are managed as a “silicon-based workforce that complements and enhances the human workforce.” They’re right about the destination. But they understate the implication. If agents are workers, then organizations need everything for those workers that they built for human workers over the past century: onboarding that transmits organizational values, management structures that align daily decisions with strategic goals, performance systems that detect and correct drift, and a shared language of intent that connects the work to the mission. For humans, we built all of that — imperfectly, slowly, through decades of management science. For agents, we need to build it now, deliberately, from scratch, and it needs to work at machine speed from day one.

The prompt engineering era asked: “How do I talk to AI?” The context engineering era asks: “What does AI need to know?” The intent engineering era asks the question that actually matters: “What does the organization need AI to want?”

Context without intent is a loaded weapon with no target. We’ve spent three years building the weapon. 2026 is the year we learn to aim.

Build the layers. The clock is running.

[![](https://substackcdn.com/image/fetch/$s_!VJRx!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc59c7e12-02c3-4388-8b40-3a9f32bae286_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!VJRx!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc59c7e12-02c3-4388-8b40-3a9f32bae286_1024x1024.png)
