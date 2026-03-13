---
title: "You built an AI memory system. Now your agent needs hands. Here are 6 extensions that compound — from household knowledge to the job hunt."
author: "Nate Jones"
published: 2026-03-13
url: https://natesnewsletter.substack.com/p/you-built-an-ai-memory-system-now
subtitle: "Watch now | Open Brain was just the start."
audience: everyone
scraped_at: 2026-03-13 12:00:18
---

“I built it. Now what?”

That’s been the most common message since the [Open Brain guide](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres) shipped. People aren’t writing in with bug reports or setup questions. They’re staring at a working personal AI memory system and having no idea what to do next.

I know the feeling. You followed the guide, the database is live, your agent reads from it and writes to it and remembers what you said last Tuesday. The infrastructure works. And now you’re sitting there realizing that the hard part was never the build. The hard part is knowing what to put in it.

The usual advice doesn’t help much. “Capture your thoughts.” “Ask it questions.” That’s like handing someone who just built a workshop full of beautiful tools a piece of sandpaper and telling them to get sanding.

Here’s what changed for me: I started building extensions on Open Brain where both I and my agent could see and act on the same data. A maintenance log where my agent catches that a warranty is about to expire based on something a technician mentioned eighteen months ago, and I pull up the same log on my phone when the repair tech asks what was done last time. A family schedule where my agent cross-references both parents’ calendars and every kid’s activity simultaneously, and Sunday night we’re both looking at the same view on a tablet planning the week. A job search dashboard where my agent spots that a warm introduction is going cold while I’m drowning in eleven other workstreams, and I see the whole pipeline at a glance over coffee.

The pattern underneath all of these is the same: a shared surface with two doors. Your agent enters through one. You enter through the other. Both sides read the same data, both sides write to it, and each one does what it’s best at.

**Here’s what’s inside:**

- **The two-door principle.** Why every Open Brain extension needs an agent door and a human door, and why a chat window alone will always be a keyhole into your own data.
- **Six use cases from household knowledge to the job hunt.** Each one built around the problems that actually defeat people, with specific examples of how conversational AI and autonomous agents handle them differently.
- **Four design principles that generate your own use cases.** Time-bridging, cross-category reasoning, proactive surfacing, and the judgment line that determines whether you trust the system or abandon it.
- **The pull/push paradigm.** Why Claude, ChatGPT, and OpenClaw are three different interfaces to the same database, and understanding when to use each one changes everything.
- **The full build guide and companion prompts.** An open-source repo with six extensions you build in order, companion prompts, and a community contribution system — everything you need to go from principles to working tables.

Let me show you what this looks like when it’s running.


## **LINKS: [GitHub Repo w/ Guides](https://github.com/NateBJones-Projects/OB1) and [Prompts](https://promptkit.natebjones.com/20260305_395_promptkit_substack_1)**

The principles in this article are worth nothing if you can’t build the tables they describe. I’ve watched too many people read something like this, nod at the concepts, and then open Supabase and freeze — because “create a table for household knowledge” sounds obvious until you’re staring at an empty schema trying to decide what the columns should be, what types to use, how to wire the MCP server to a new table, and whether you’re going to break the setup you already have.

So we built the whole thing. Six extensions, one for each use case in this article, designed to be built in order. Each one teaches new concepts through something you’ll actually use — and they compound, because your CRM knows about thoughts you’ve captured, your meal planner checks who’s home this week, and your job hunt contacts automatically become professional network entries. The repo includes the SQL, the edge functions, the table schemas, and step-by-step instructions written for the same audience that built the original Open Brain in 45 minutes.


#### Start here: [OB1 on GitHub](https://github.com/NateBJones-Projects/OB1)

And this isn’t a read-only repo you clone and forget. OB1 is built for community contributions — recipes, schemas, dashboard templates, new integrations — with a real contribution process behind it. Every PR runs through an automated review agent that checks eleven rules before a human admin ever sees it, and nothing ships without passing both gates. If you build something useful on your Open Brain, you can submit it — but it has to meet the standard. This is infrastructure that gets better because people use it and build on it, and the quality holds because every contribution goes through the same rigor.

The repo also includes five companion prompts that help you migrate existing knowledge into your Open Brain, discover which use cases matter most for your life, and build the capture habit that makes the whole system work over time. And if you get stuck, we built dedicated AI assistants that know this system inside out — a Claude Skill, a ChatGPT Custom GPT, and a Gemini GEM — so whatever tool you’re already using can walk you through it.


#### The Discord is live for real-time help: [Join here](https://discord.gg/Cgh9WJEkeG)


## The amnesia problem no one solved

Agents are the fastest-growing category in software. OpenClaw became the fastest-growing open-source project in GitHub history — over 250,000 GitHub stars in two months, surpassing React’s decade-long record. Its companion social network Moltbook claimed 1.5 million agents within weeks of launch before Meta acquired it this month. Devin grew from $1 million to $73 million in annual recurring revenue in nine months. Sierra hit a $10 billion valuation. And every one of these agents has the same problem: they can’t remember you. New sessions start from zero, tool switches wipe the slate, and you’re burning your best thinking catching the agent up instead of doing actual work.

That’s the problem Open Brain solves. It’s a personal database you own, connected to your AI through MCP, with access to every frontier model through OpenRouter. You talk to it through whatever client you already use (Claude, ChatGPT, OpenClaw, anything that connects via MCP) and the agent reads and writes to your database directly. Your memory travels with you across every tool, every model, every session. Thousands of people built it in the last few weeks, following a guide that took 45 minutes and costs roughly a dime a month to run.

So the system works. Now: what do you actually do with it?

That’s what this piece answers. Specific, tangible use cases you’ll recognize from your own life. But I’m also going to name the principles underneath those use cases as we go, because one good principle will take you further than a hundred ideas you copied from someone else.

The principle I keep coming back to: every extension you build on Open Brain should be a surface both you and your agent can see and act on. Agent-readable and agent-writable, human-readable and human-writable, where both sides operate on the same information and each one does what it’s best at.


## **Why you need both sides**

Right now, your Open Brain lives in a chat window. That works for capture and retrieval. But a chat window is a keyhole. You can ask one question and get one answer. You can’t see the landscape.

Ask your agent “what’s on the family schedule this week?” and you get a text list. Fine. But you can’t scan it at a glance while packing lunches, hand your phone to your partner, or spot the Thursday conflict by looking at two columns side by side. A calendar app gives you the visual layer — but it can’t cross-reference your partner’s work schedule against the school calendar, or flag that you promised snacks for Saturday’s game but haven’t bought them yet.

You need both. The agent reasoning across the data, and you seeing the data with your own eyes. The agent writing to the data when it catches something in conversation, and you writing to it when you’re standing in the kitchen and need to add something fast.

Neither interface alone is enough. Both together solve problems that nothing else on the market touches — because nothing else was designed for agents and humans to operate on the same information through different interfaces at different times.


## **Household knowledge**

Every household runs on information that lives nowhere. Paint colors. Kids’ shoe sizes. The plumber you used two years ago. The WiFi password for the guest network. I’ve watched this pattern in my own house for years — the answer always exists somewhere, a text thread, a receipt in a drawer, someone’s memory, and you can never find it in the moment you need it.

One structured table. Start feeding it information as you encounter it. You’re talking to Claude about something else entirely and mention the paint color — “Hey, save this — the living room paint is Benjamin Moore Hale Navy, we got it at Sherwin-Williams in October.” Claude writes the entry. Two seconds. Done. You could have that same conversation with ChatGPT or any other client connected to your Open Brain — the data lands in the same table regardless.

The agent-writable side captures facts in structured form from ordinary conversation. Over weeks, the table fills with the institutional knowledge of your household. The human-readable side gives you a simple view on your phone, browsable by category (paint, appliances, contacts, medical info), the way you’d glance at a list on the fridge, except it’s searchable and your agent keeps it current. And the human-writable side lets you update an entry directly when you’re standing in the shoe store with your kid’s new measurements. Some moments call for talking to your agent. Some call for tapping a screen. Both paths write to the same place.

This is the simplest use case — storing and retrieving household knowledge. But it already illustrates the design principle: all four modes (agent reads, agent writes, human reads, human writes) operating on the same data.


## **Home maintenance — and the principle of time-bridging**

When did you last service the HVAC? Is the roof still under warranty? The dishwasher is making a noise — what did the repair tech say a year and a half ago?

Structured maintenance data. Asset, purchase date, warranty expiration, service history, vendor contacts, notes. Every time a tech comes out, you log what they found and what they recommended. Takes two minutes.

Here’s where the first real principle emerges. You open Claude on a Sunday morning and ask, “Anything I should deal with around the house?” Claude sees the whole timeline across every asset and catches things invisible to daily life: “The dishwasher warranty expires March 15th. The last tech noted pump wear in September. You might want to schedule service before the warranty lapses.”

Stop and notice what just happened. The agent bridged an eighteen-month gap between two events — a technician’s offhand comment about a pump and an approaching warranty deadline — and synthesized them into a recommendation at the exact right moment. You didn’t ask about the dishwasher. You didn’t remember the pump comment. You certainly didn’t have the warranty date in your head. The agent held the entire timeline and surfaced the connection because the dates made it urgent *now*.

No human does this. Human memory simply doesn’t work this way. You don’t wake up on a random Tuesday and think “what did that repair tech say eighteen months ago and how does it relate to my warranty expiration?” Your brain flushed those details months ago to make room for things that felt more pressing. The agent flushed nothing. It holds the complete timeline, and nothing falls out.

Now imagine the autonomous version. OpenClaw is scanning your maintenance data on a schedule, and Monday morning you wake up to that same insight as a notification — without asking. You didn’t think about the dishwasher. OpenClaw caught it because it was running overnight and the dates made it urgent. Same data, same table, same insight. The difference is whether you had to think to ask.

Principle one: your agent bridges time. Its memory doesn’t decay. Something logged six months ago is exactly as accessible as something logged this morning. Anywhere the value comes from connecting events spread across months or years — home maintenance, medical history, financial decisions, career moves — that’s your agent’s territory.

The human side earns its keep too. The HVAC tech is in your living room asking what was done last time. You pull up the maintenance view on your phone and hand it to him. Service dates, parts replaced, notes. He reads it himself. A visual interface solving a problem no chatbot can, because the tech needs to scan information quickly, not have a conversation.


## **Kid logistics — and the principle of seeing across categories**

If you have children, this is the use case that will make everything else click.

Pickup is at 3:15 except Wednesdays when it’s 2:00. Soccer practice moved to field B starting next week. Permission slip due Friday. Picture day is the 14th but your kid needs a haircut before then. Teacher conference is Thursday, but your partner has a client dinner that night and someone needs to swap. The older kid has a birthday party Saturday but you haven’t bought a gift yet, and the younger kid has a playdate at the same time in the opposite direction.

Every parent holds this graph in their head and drops things. Regularly. I know because I live this. It’s not about being disorganized — it’s that the complexity genuinely exceeds what a single human brain can track in real time while also holding a job, feeding people, and remembering to pick up the dry cleaning.

And a calendar doesn’t fix this. This is the part people don’t see until I point it out: a calendar shows events. It does not show conflicts and dependencies. It will happily display the Thursday teacher conference and your partner’s Thursday client dinner on separate calendars without ever telling you those two things are a problem. Picture day is on the 14th, but the calendar has no idea your kid needs a haircut first. The birthday party is Saturday, but nothing in the interface knows you haven’t bought a gift.

Your agent sees both parents’ schedules and all kids’ events simultaneously. You ask ChatGPT on Sunday night, “Walk me through next week — any collisions?” and it comes back: “You signed up for the Thursday conference, but your partner has the client dinner. Wednesday at 4pm is open for both of you — want me to check if the school has that slot?” That’s cross-referencing two people’s constraints, finding a conflict neither noticed, scanning for alternatives that work for both, and proposing a resolution — all because you asked one broad question and the data was structured for reasoning.

Now keep going. The birthday party Saturday — has a gift been bought? If not, that’s a task that needs to happen before Saturday and it’s already Wednesday. The playdate across town — who’s driving? Does it overlap with the party dropoff? Picture day is in three days and the haircut hasn’t been scheduled. Each of these queries spans events, tasks, logistics, and deadlines. A human can handle any single one. The agent handles all of them simultaneously because they’re all in the same database and the agent sees the whole graph at once.

Principle two: your agent sees across categories. When multiple types of structured data exist in your Open Brain — schedules, tasks, contacts, logistics — the agent cross-references them in ways no human would do manually. The power isn’t in any single table. It’s in the connections between tables.

The visual layer matters just as much. Sunday night, both parents at the kitchen table. The family view is on a tablet — both schedules, all activities, conflicts highlighted, undone tasks flagged. You can see the week as a single picture and plan together while pointing at the screen. That’s fundamentally different from asking an agent to read you a list, because planning is visual — it requires scanning and comparing and making quick decisions while you’re both looking at the same picture. Both sides write in whatever way is natural — voice to the agent, tap on the screen — and the system stays current because both paths update the same source of truth.


## **Meal planning — the collision of four datasets**

Not recipes. The problem that actually defeats families week after week is the collision of what everyone eats, what’s in the house, what the weekly schedule demands, and what needs to go on the grocery list.

Your agent holds all four simultaneously. You’re talking to Claude about the week ahead — not about food, just about what’s coming — and it volunteers: “You haven’t done fish in three weeks. Thursday is soccer night so you need something fast. Last busy Thursday you did sheet-pan chicken and everyone ate it. You’re out of chicken thighs. Adding it to the list, putting fish on Saturday when you have time.” You didn’t say “plan my meals.” Claude noticed a gap because it could see the meal history, the schedule, the pantry, and the shopping list in the same pass.

That’s what a conversational client can do when you give it a broad opening. An autonomous agent like OpenClaw goes further — it generates the meal plan and shopping list on Sunday night without you asking, ready for you to review Monday morning.

Principle three: the most valuable answers are to questions you didn’t ask. A database waits for queries. An agent notices things proactively — gaps, patterns, deadlines, conflicts. A conversational client does this when you give it room in a broad question. An autonomous agent does it on a schedule. Both are valuable. Design your tables for what you want your agent to notice, not just what you want to look up.

The human-readable layer is what makes this practical: you’re standing in the grocery store on Thursday afternoon. The shopping list is on your phone, populated by the agent, organized by aisle. You grab the chicken thighs, check it off. You see the avocados look good and add guacamole ingredients on the spot. The agent will see those additions next time it looks at what’s in the house. The grocery list is the canonical shared surface — the agent fills it by reasoning across data no human would cross-reference, and you read it, mark things off, and add things the agent didn’t know about because you’re the one standing in front of the shelves.


## **Professional relationships — and the judgment line**

You have dozens of professional relationships that matter and limited ability to maintain them all. The context is scattered across emails, messages, and a memory biased toward the most recent interaction.

You ask Claude, “Anyone I’ve been neglecting?” and it scans the full picture: “You haven’t reached out to James in four months. Last time you talked, he was worried about his team’s reorg. That kind of thing typically resolves in a quarter — might be a good time to check in.” Time-bridging and cross-category reasoning working together, triggered by one open-ended question. Or OpenClaw catches the same gap autonomously and flags it in a Monday morning digest — you didn’t ask, but the window was closing and the data made it obvious.

But here is the fourth principle, and the most important: agent surfaces, human decides, agent executes. Your agent should absolutely tell you James is overdue for a reach-out and give you every piece of relevant context. It should not draft and send the email. Because the right message depends on things no database captures: the politics at his company, the tone your relationship calls for, whether this week is actually the right moment given what else is happening in your life. The agent handles memory and pattern recognition. You handle judgment. The division is clean and it’s what makes the system trustworthy. Blur the line and you’ll stop using it. Hold the line and it makes you sharper at everything.

This applies to every use case in this piece. The agent notices the scheduling conflict, flags the warranty deadline, spots the pattern in your interview data. You decide what to do about each one. The system works because the division of labor is clean: the agent does what agents do well (holding vast amounts of data, seeing connections across time and categories, never forgetting) and you do what humans do well (making judgment calls, reading social situations, weighing values and priorities that can’t be quantified).

Get this line wrong and you build something you don’t trust. Get it right and you build something that makes you better at everything it touches.


## **The job hunt: where every principle fires at once**

A job hunt is a dozen parallel workstreams pretending to be one activity — companies, roles, contacts, applications, interviews, follow-ups, resume versions, compensation data, and your own shifting sense of which opportunity you actually want.

This is where the full architecture earns its keep.

**Cross-category reasoning:** You paste a posting into ChatGPT and say, “What do I have on this company?” It doesn’t just read the posting. It scans your contacts, conference notes, relationship data. “You met someone from their data team at the conference in October. You noted a good conversation about distributed systems. He said they were hiring.” A warm introduction instead of a cold application, surfaced by connecting data across tables you’d never cross-reference manually. Any conversational client can do this — you asked, and the data was there.

**Time-bridging:** Maria offered to introduce you to a VP nine days ago. You meant to follow up. Life intervened. OpenClaw catches the gap overnight and flags it Monday morning: “That was nine days ago. The window on a warm intro is roughly two weeks.” You didn’t ask. You didn’t remember. An autonomous agent running on a schedule caught what a session-based client never would — because you’d have had to think to ask, and the whole problem is that you forgot. Job hunts don’t die because people aren’t qualified. They die because warm introductions go cold while you’re drowning in the other eleven workstreams.

**Proactive pattern recognition:** After several interviews, you ask Claude, “What patterns do you see across my interviews?” It reads every note simultaneously: “You keep getting energy from platform team conversations and losing it in direct-to-consumer ones. Your four strongest interviews were at companies under 200 people. You might be optimizing for the wrong company size.” You’d figure that out eventually — maybe after two months of scattered results and a general sense that something wasn’t working. Claude sees it in two weeks because you asked and the data was structured for reasoning.

**The human-readable layer:** You pull up your search dashboard with coffee. The whole pipeline is visible at once — which companies are active, where you are in each process, what’s due today, what’s stalled. You can see the shape of your search in a way no chat window provides, because a pipeline is spatial. You need to see what’s at the top of the funnel, what’s in the middle, what’s close to an offer. You need to spot the applications that went quiet and decide whether to follow up or let them go. That’s a visual task, not a conversational one.

**The emotional corrective:** This is the one that surprised me most. Job hunting is demoralizing in a specific way that most productivity tools ignore entirely. You get ghosted after a great conversation. You bomb a final round you prepared extensively for. You get a form rejection from a company where you knew someone on the inside. And your brain — which is wired to construct narratives from recent experience — starts telling you a story. The story says you’re not good enough. The story is wrong, but it feels true because the most recent data point is negative and your memory is biased toward recent events.

Your agent has the actual record. You open ChatGPT and say, “I’m losing confidence — am I actually getting anywhere?” and it comes back: “You’ve advanced past five of seven first-round interviews, a 71% conversion rate. The two rejections were both in industries where you have no direct background — biotech and fintech. In your core domain, you’re five for five. The rejections are telling you something about fit, not ability.”

Data correcting a distortion your brain produces automatically under stress. And it’s only possible because the full history is structured, queryable, and interpreted by something that isn’t emotionally invested in the outcome.

And the judgment line holds here too: your agent gives you the normalized compensation comparison, the pattern analysis, the conversion data, the full pipeline view. It does not tell you which offer to take. Because that decision depends on what kind of work you want to wake up to every morning, which team felt right when you were in the room, what your family needs from this transition, whether you’re optimizing for learning or stability or compensation or trajectory. The agent gives you the clearest possible picture any human has ever had going into a career decision. You make the call that only you can make.


## **Why this only works because of where you built it**

Everything described here depends on one architectural decision you already made. Your data is agent-readable. Your AI reaches it directly, queries it, reasons about it, writes to it, connects it to other data, without scraping a UI, without an export step, without asking permission from a platform that controls the access layer. And because the data layer is yours, any client can reach it. Claude for a deep reasoning session. ChatGPT for a quick question. OpenClaw for autonomous monitoring while you sleep. They all hit the same tables, and none of them needs the others’ permission.

That’s the real architectural advantage: conversational clients handle the pull — you ask a broad question and the agent reasons across your data in the moment. Autonomous agents handle the push — they scan your data on a schedule and surface what’s urgent before you think to ask. Same database, different interfaces, each doing what it’s best at. The data doesn’t care which model is reading it.

When your schedule lives in someone else’s calendar app, a human can see it. An agent can’t — not without a limited API that the platform controls and can restrict whenever it chooses. When it lives in your own database, your agent sees it the same way you do — first-class access, no intermediary, no one else’s permission required.

And here’s the long-term bet: every time the models get smarter, every extension you’ve built gets more valuable automatically. The agent reading your family schedule today is good. Next year’s model will be better at spotting conflicts, anticipating needs, doing things you can’t even imagine prompting for right now. You’re building on a foundation that appreciates with every model improvement, because the data is structured for reasoning, not just storage.


## **The four principles, named**

Your agent bridges time. Its memory doesn’t decay. Anywhere the value comes from linking events spread across months or years, that’s your agent’s territory.

Your agent sees across categories. The power isn’t in any single table. It’s in the connections between tables that no human would cross-reference manually.

The most valuable answers are to questions you didn’t ask. A database waits for queries. An agent notices things proactively — gaps, patterns, deadlines, conflicts. Design for what you want your agent to notice.

Agent surfaces, human decides, agent executes. The agent handles memory and pattern recognition. You handle judgment. The division is clean and it’s what makes the system trustworthy.

Any problem in your life that involves scattered information, events spread over time, or multiple categories that need cross-referencing — point your Open Brain at it. Create the table. Feed it data. Let the agent do what it was built to do.

The visual layer — the dashboards, the mobile views, the shared surfaces — is the next build, and it’s coming. But the tables don’t wait for the frontend. Pick the use case that hit you hardest. Start there. You built a system where your agents can see your data.

Now give them something worth seeing.

[![](https://substackcdn.com/image/fetch/$s_!Nhsq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbed3e9bf-cf16-45d4-9074-10ee39dab36e_6293x6251.png)](https://substackcdn.com/image/fetch/$s_!Nhsq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbed3e9bf-cf16-45d4-9074-10ee39dab36e_6293x6251.png)
