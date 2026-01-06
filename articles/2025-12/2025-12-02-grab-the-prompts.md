---
title: "Grab the prompts"
author: "Nate Jones"
published: 2025-12-02
url: https://natesnewsletter.substack.com/p/pms-have-it-worst-in-the-al-era-but
audience: everyone
scraped_at: 2026-01-05 19:10:44
---

*PMs have it rough. As someone who’s been (and led) PM teams for a long time now, I can’t stay quiet anymore. This piece is all about what’s happening to product management in the age of AI, why we should all care about it, and (of course) very practical ways we can make things better.*

*Start with the pain: over 80% of product managers have experienced burnout. Two-thirds of senior PMs are actively looking for new roles. And the people we’re asking to lead the AI transition are already running on fumes.*

*AI is attacking the role from four directions at once: faster artifact generation that makes the easy parts trivial while the hard parts stay hard, probabilistic products that break every planning framework we know, automation that’s eating the glue work, and technical requirements that keep ratcheting upward without shedding anything. One large survey found 88% of heavy AI users report burnout — and they’re twice as likely to consider quitting.*

*I’ve spent a decade managing products, another five managing PMs, and the last year watching this profession get turned inside out. So I built something: a complete library of AI prompts designed to make any product manager operate at a senior, strategic, decision-driving level.*

*Here’s what’s in the box:*

- ***Morning Technical Deep-Dive** — understand any AI/infra topic with a 5-part structured briefing*
- ***Technical Decision Pre-Read** — get a high-signal breakdown before an architectural meeting*
- ***Engineering → Executive Translation** — rewrite technical detail into an exec-ready narrative*
- ***AI Reliability / Hallucination Diagnosis** — identify root causes, guardrails, and what’s fixable*
- ***Innovation Theater Detector** — stress-test whether a feature request creates real value*
- ***Case to Kill a Feature (Diplomatic)** — craft a “no” that preserves trust and aligns incentives*
- ***Prioritization Pressure Test** — force-rank a roadmap using cost of delay, demand, and strategy*
- ***Meaning Check** — determine whether the work matters, and what would make it matter*
- ***Customer Feedback Synthesis** — extract patterns, contradictions, outliers, and signals*
- ***Gut Check (Data vs. Instinct)** — analyze the tension between intuition and metrics*
- ***Pre-Mortem (Six Months After Failure)** — reveal hidden risks before a launch*
- ***Decision Journal Entry** — capture reasoning, uncertainty, expectations, and falsifiers*

*Below I’ll tell you why PMs have it worst right now, what actually still matters, and how these prompts address each of the four threats bearing down on the role.*


# [Grab the prompts](https://www.notion.so/product-templates/PM-Prompt-Library-2ba5a2ccb52680eba827e24575404467?source=copy_link)

This library is a complete, high-authority set of AI prompts designed to make any product manager operate at a senior, strategic, decision-driving level. It covers the four core PM competencies—technical fluency, working on things that matter, product intuition, and cross-functional alignment—and provides clear, structured, ready-to-use instructions for every scenario a PM encounters: architectural decisions, feature evaluation, roadmap prioritization, customer synthesis, pre-mortems, stakeholder mapping, executive updates, and difficult conversations.

Each prompt is written for real-world use, tuned for modern LLMs, and designed to generate high-signal, high-clarity output without ambiguity, fluff, or hand-holding. The collection is both exhaustive and practical: a toolkit you can hand to an entire product organization and immediately raise the quality, velocity, and rigor of decision-making.


# Why PMs Have It Worst in the Age of AI

I’ve been avoiding writing this piece for months. Not because I lack opinions—Lord knows I have plenty—but because every time I sit down to write about what’s happening to product managers, I get that sick feeling in my stomach. The same one I got when a ten-year PM on my team told me she wasn’t switching companies. She was leaving product altogether because the job had become impossible to sustain.

Here’s what nobody wants to say out loud: product managers have it worst right now with AI. I know every job family thinks they’re getting screwed — engineers worry about Copilot, designers panic about Midjourney, marketers freak out about ChatGPT. But PMs? We’re getting hit from every conceivable angle, and not in ways that make clean narrative sense.

The data backs this up. Mind the Product found over 80% of product managers have experienced burnout. Separate surveys show roughly two-thirds of senior PMs are actively looking for new roles — not switching companies, but questioning whether the job is sustainable at all. And here’s the kicker: heavy AI users report both higher productivity *and* higher burnout. One large survey found 88% of AI-intensive workers feel burned out, and they’re twice as likely to consider quitting compared to peers using AI less. The people we’re asking to lead the AI transition are already running on fumes.

After a decade managing products, another five managing PMs, and now watching this profession I love get turned inside out — I can’t stay quiet anymore.


# **Why PM Exists at All**

Before I explain how bad things are, I need to tell you why product management exists in the first place—because that context changes everything about how to survive what’s coming.

Large organizations are caught between two necessities that constantly work against each other. On one side: the need to make work *legible*—structured, measurable, predictable. This is why we have quarterly planning cycles, OKRs, roadmaps, and formal reporting. These processes exist so leadership can allocate resources, make commitments to enterprise customers, and coordinate across hundreds of people who’ve never met each other.

On the other side: the need to actually get things done, which almost never happens through official channels. The most important work in any organization flows through backchannels, hallway conversations, and relationships that don’t appear on any org chart. When something urgent breaks, nobody convenes a steering committee. Someone texts the engineer who actually knows where the bodies are buried.

Product management evolved to live in that gap. We’re the sanctioned illegibility operators—officially empowered to navigate the unofficial routes. When the quarterly plan says one thing but reality demands another, PMs broker the conversation that makes the adjustment possible without blowing up the system. When engineering and leadership are living in different realities, we translate between them without making either side feel stupid.

This isn’t glamorous work. It’s often invisible. But it’s structurally necessary because the tension between legibility and efficiency never resolves—it just has to be managed, constantly, by humans who can read rooms and know which rules can bend.

Every time someone says “we don’t need PMs, engineers can talk directly to stakeholders,” they’re proposing to collapse that gap. It never works. Within eighteen months, someone gets hired to coordinate between technical teams and business priorities. They might call the role something different, but it’s the same function reasserting itself.

This matters right now because AI operates entirely in the legible domain. It can synthesize documented feedback, generate artifacts that fit templates, and process information faster than any human. What it cannot do is sense that the real blocker on your project is a grudge between two directors from a reorg eighteen months ago—and it definitely can’t broker the lunch that resolves it.


# **What’s Actually Happening to PMs**

So why is this the worst moment to be a PM? Because AI is attacking the role from four directions simultaneously—and unlike other job functions, PMs can’t point to one clear engagement model and adapt to it.

If you’re in customer success, AI picks up triage tickets. Predictable. If you’re in sales, AI listens to calls and coaches your follow-ups. Predictable. If you’re in marketing, AI accelerates creative and asset generation. Predictable. For PMs, though, the threats stack on top of each other in ways that make the ground constantly shift underfoot.


## **The Asset Problem**

Yes, AI can generate PRDs, specs, and documentation at unprecedented speed. Every PM I know is being told to produce these artifacts three times faster. But here’s what nobody mentions: the easy parts are the parts AI accelerates. Product insight—the delicate alchemy of data, storytelling, engineering feasibility, and that gut feeling you develop after watching a thousand features die in production—that still takes the same blood, sweat, and political capital it always did.

AI makes the mechanical work faster while making the judgment work relatively more valuable. You can generate a PRD in minutes now. But is it the *right* PRD? That question hasn’t gotten any easier to answer.


## **Probabilistic Products**

Unlike anything PMs have dealt with before—not waterfall to agile, not desktop to mobile—AI products are fundamentally probabilistic. The same input can yield different outputs as models learn and evolve. Your CEO wants a deadline for when the AI feature will hit 95% accuracy. Your engineering team looks at you like you just asked them to predict next week’s lottery numbers.

You’re stuck in the middle, trying to explain why the AI feature that worked perfectly in the demo just told a customer their insurance claim was denied because Mercury is in retrograde. I’m barely exaggerating. And when it hallucinates something dangerous? That’s on you too.


## **The Glue Role Under Question**

Product management evolved to keep engineers out of meetings. We became the translation layer, the human API between business and technology. But AI can now do parts of that translation—synthesizing customer feedback, generating roadmaps, even drafting stakeholder updates.

The uncomfortable truth is that maybe 80% of what junior PMs do today can be automated. Not well, not with nuance, but adequately. And adequate is often good enough for companies looking to cut costs. When Brian Chesky combined PM roles with product marketing at Airbnb, he wasn’t just restructuring. He was sending a signal about which parts of the function he still considered essential.


## **The Technical Requirements Keep Growing**

It used to be enough to understand basic technical concepts, maybe write some SQL. Now product managers are expected to prototype directly using tools like Lovable, commit actual code, understand schema validation, debate LLM architectures, and have informed opinions on whether to use RAG or fine-tuning. Only 5% of current PMs can actually code, yet suddenly we’re all supposed to make architectural decisions about probabilistic systems we barely understand.

Every decade, the technical requirements ratchet upward. But we never shed anything. We still do everything from the 1990s plus data analysis plus prototyping plus AI architecture plus growth metrics. The pile only grows.

Stack these threats on top of each other and you understand why the ten-year veterans are walking away. Not switching companies—leaving the profession entirely.


# **The Four Things That Still Matter**

Here’s what took me too long to realize: the crisis is real, but the solution isn’t revolutionary. It’s a return to what always mattered, with new tools in the toolkit.


## **Technical Fluency**

I’m not talking about becoming an engineer. I’m talking about developing a high-fidelity mental model of how AI systems actually work. When your engineering team debates whether to use RAG or fine-tuning, you need to contribute meaningfully to that conversation—understanding the cost implications, performance trade-offs, and user experience impacts.

You need to understand why your model hallucinates, what temperature settings mean, how context windows affect performance, and when to enforce schema validation versus when to let outputs flow freely. This isn’t optional anymore.

The good news: ChatGPT is literally the best teacher you could ask for. Schedule actual lessons. “Explain vector databases to me like I’m a PM who needs to make a decision about them tomorrow.” Thirty minutes every morning. Within three months, you’ll be dangerous.


## **Work That Matters**

The epidemic of PM burnout isn’t just about workload—it’s about meaning. Too many PMs are grinding themselves to dust on AI features that exist because the CEO read about them on LinkedIn, not because they solve real problems.

You’re smart enough to know the feature won’t move the needle. Your team knows it. But you push forward anyway because that’s the job, right? Wrong. The job has always been to build products with genuine impact. You need the courage to fight for what matters, kill what doesn’t, and have the uncomfortable conversation about why adding a chatbot to your B2B logistics platform is innovation theater, not innovation.

If you’re not motivated, if you don’t feel like there’s meaning in the work, you can’t convince your stakeholders. You can’t sell the product. You can’t energize your engineering team. So yeah—meaning making isn’t soft. It’s operational.


## **Product Intuition**

AI can read every customer call transcript, analyze every support ticket, synthesize every piece of feedback—better and faster than you ever could. Use it. But here’s what a decade of product management taught me: the best product decisions often contradict the data. They come from that feeling in your gut when you watch a user struggle with something that analytics says is working fine.

Product intuition is a craft skill, developed through thousands of micro-decisions, failures, and occasional triumphs. It’s fingertipy, learned in the shop, impossible to replicate. The moment you give AI too much deference on judgment calls, you’ve already been replaced.

If you have a hunch about your product and you’re an experienced PM, follow that hunch. If you think it needs to launch now, it probably does. Trust your gut. Trust your intuition. You will burn out less, the product will be better, and you’ll put AI in its right place: as an assistant, not a colleague that calls the shots.


## **Alignment**

Here’s the one thing AI absolutely cannot do: get your engineering team and leadership aligned when they’re living in different realities. It can’t navigate the delicate politics of explaining to your CEO why their pet feature is technically impossible without making them feel stupid. It can’t build the trust needed to push back on unrealistic deadlines. It can’t read the room when tensions are high and know whether to push forward or table the discussion.

This is the illegible work. The backchannels. The pre-meeting before the meeting. Knowing which engineer to ask when you need the real timeline instead of the official one. This alignment work—the exhausting, thankless, political navigation between engineering reality and business fantasy—remains irreplaceable. It’s been the core of product management since the role was invented, and it’s still the core now.

Yes, AI can help you build the deck. But it can’t deliver it with the right tone, emphasize the right points for your specific audience, or know when to abandon the slides entirely and just have a real conversation. If you can’t do this, your career flatlines regardless of how well you prompt ChatGPT.


# **Why This Matters Beyond PM**

If you’re not a PM, you might be wondering why you should care that product managers are drowning. Here’s why: your outcomes depend on our survival.

Engineering leaders: you know your best work often happens outside the official process. Someone has to protect that space while still giving leadership enough visibility to keep funding your team. That someone is your PM. When PMs burn out or get cut, the illegible work doesn’t disappear—it either falls on you, or it doesn’t get done at all.

Marketing and sales: the quarterly planning deck rarely reflects how decisions actually get made. PMs are the ones who know what’s actually shipping, what’s actually blocked, and what commitments you can actually make to customers. When that function degrades, you’re selling roadmaps that won’t materialize.

Executives: you need work to be legible so you can plan. But you also know that rigid process kills the responsiveness that wins markets. PMs are how you get both—legibility for planning, flexibility for execution. Eliminate the function and you collapse into one extreme or the other.

The PM crisis isn’t a PM problem. It’s an organizational problem that happens to be landing hardest on the people whose job is to absorb organizational dysfunction.


# **What Doesn’t Change**

Everything I’ve told you to focus on—technical fluency, meaningful work, product intuition, stakeholder alignment—these aren’t new. They’re what great PMs have always done. We just forgot, somewhere between the democratization of product management and the AI gold rush, that these fundamentals matter more than any tool.

AI isn’t going to replace product managers. But product managers who don’t use AI? They’re already being replaced. The paradox is that the more powerful these tools become, the more critical our judgment becomes. When everyone can generate a PRD, the value shifts to knowing which PRD to write. When anyone can analyze customer feedback, the premium is on knowing which insights actually matter.

Use AI aggressively for documentation, analysis, prototyping—all the mechanical work that’s been eating your soul. But don’t let it atrophy the muscles that make you irreplaceable: your ability to see what others miss, to bridge unbridgeable gaps, to make meaning from chaos, and to have the hard conversations that move products forward.

The job is harder now than it’s ever been. If you’re feeling overwhelmed, you’re not alone. If you’re thinking about walking away, I understand. But if you’re willing to evolve—to embrace both the tools and the timeless skills, to be both technically fluent and deeply human—then this might be the most interesting time to be a product manager in history.

Every crisis creates opportunity. The PMs who adapted to Agile became the leaders of the next era. Those who learned mobile constraints defined a generation of products. Now it’s our turn.

The old joke goes: How many product managers does it take to change a light bulb? None—it’s on the roadmap for Q5.

Some things never change. Hold onto those.

[![](https://substackcdn.com/image/fetch/$s_!iI2C!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa648b5af-28b5-43eb-9b80-bf03b99677ee_512x512.png)](https://substackcdn.com/image/fetch/$s_!iI2C!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa648b5af-28b5-43eb-9b80-bf03b99677ee_512x512.png)
