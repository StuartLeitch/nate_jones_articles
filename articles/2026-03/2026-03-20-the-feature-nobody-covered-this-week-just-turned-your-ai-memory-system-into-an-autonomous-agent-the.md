---
title: "The feature nobody covered this week just turned your AI memory system into an autonomous agent + the guide to wire it up"
author: "Nate Jones"
published: 2026-03-20
url: https://natesnewsletter.substack.com/p/your-ai-agent-needs-three-things
subtitle: "Watch now | Well, we're just going to keep adding body parts."
audience: everyone
scraped_at: 2026-03-20 12:00:15
---

Anthropic shipped a feature earlier this month called /loop. It’s a command inside Claude Code that lets an agent run a task on a schedule, every five minutes, every hour, every morning at 9am, without you sitting there prompting it. The coverage so far has been about developer convenience. Automated monitoring and background polling.

That framing misses what actually happened. And not just because Claude Code isn’t only for developers anymore. Anthropic has said as much, I’ve said as much, and the user base moved past that assumption months ago even if the coverage hasn’t. Marketers are in Claude Code now. Product managers. Anyone willing to type in a terminal window, because it turns out a terminal is just a chatbot without the guardrails.

The real story is that /loop is the last Lego brick. If you’ve been following the agent conversation, you know there’s a short list of primitives an agent needs before it stops being a chatbot and starts being something you can actually delegate to. Memory. Proactivity. Tools. We solved memory a few weeks ago with [Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres). Tools have been here through MCP. What was missing was the heartbeat, a way for the agent to wake up on its own and do work without you being the one to poke it every time. /loop is that heartbeat. And if you’ve already built Open Brain and connected it to tools, you’re now holding all the pieces.

That combination is, functionally, ***an*** ***OpenClaw you control***.

**Here’s what’s inside:**

- **The three Lego bricks and what happens when you stack them.** I’ll add one primitive at a time so you can see exactly what changes at each layer, from a parrot that repeats advice to a detective that builds a case.
- **Use cases from energy tracking to sales pipelines.** Specific examples of how memory plus proactivity plus tools creates compound value that no single pass can match.
- **Why this is the OpenClaw stack without the chaos.** Same core capability, none of the security nightmare. And why the architectural separation between scheduling and memory is what makes it durable.
- **The morning briefing where every primitive fires at once.** The capstone use case that shows what genuine delegation looks like when the agent has been working overnight.
- **What’s still missing, and why the terminal is time travel.** Honest gaps, and the argument for why using Claude Code right now puts you months ahead of everyone waiting for the friendly UI.
- **Prompts and two companion guides to build it yourself this weekend.** A step-by-step walkthrough to set up the /life-engine skill with Claude Code, MCP, Telegram, and /loop — plus a second guide that turns those briefings into short animated videos on your phone.

Let me show you what I mean by adding one brick at a time.


## **Grab the prompts and guide to build your /life-engine (links below)**

Everything in this article describes what happens when memory, proactivity, and tools work together. The guide gives you the build.

- **LINK: [Prompt Kit](https://promptkit.natebjones.com/20260309_j7w_promptkit_1)**

  The prompt kit tells Claude Code to use the guide to get everything done for you.
- LINK: **[Life Engine Guide](https://github.com/NateBJones-Projects/OB1/tree/main/recipes/life-engine)**

  The guide walks through setting up Claude Code with MCP integrations, building the basic /life-engine skill, scheduling it with /loop, and how Claude proposes improvements over time.
- LINK: **[Video Briefing Guide](https://github.com/NateBJones-Projects/OB1/tree/main/recipes/life-engine-video)**

  This bonus guide shows you how to wire Remotion and ElevenLabs into your existing Life Engine, rendering short animated video briefings with AI voiceover, synced subtitles, and data cards, and delivering them to Telegram in place of (or alongside) plain text messages.

Instead of handing you five separate loop recipes to copy-paste, the entire guide is built around one concept: a single Claude Code skill — your /life-engine — that you schedule once and let evolve. Every 30 minutes, Claude wakes up, checks the time, and decides what you actually need right now. Morning? It pulls your calendar and gives you a daily rundown. Got a client call in 30 minutes? It checks your Open Brain for that client’s history, past conversations, and open items. Quiet afternoon? It sends a check-in through Telegram — “How are you feeling?” — so it doubles as a health journal you talk to from your phone. End of day? Summary of everything that happened.

But here’s the part that matters: you don’t build all of that on day one. You start simple — just calendar and Telegram. That’s it. Then Claude starts noticing patterns and suggests additions. “You keep checking your Open Brain before client calls manually. Want me to add that to the skill?” Or “You haven’t used the weather check in two weeks. Want me to drop it?” The skill evolves. It’s not a static automation — it’s a self-improving system that gets more valuable the longer you run it, and no two people’s will look the same.

If you built [Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres), you can build this. Same skill level, same afternoon-sized commitment, and by tomorrow morning your agent is working while you sleep.


## What an agent needs

There are three things an agent needs before it stops being a chatbot and starts being something you can actually send work off to. I think of these as Lego bricks because, like Legos, each one is simple on its own. The magic is in how they snap together.

**Memory.** The ability to read and write to a persistent store, to remember what happened yesterday, last week, three weeks ago. Without memory, every interaction starts from zero and the agent is perpetually a new hire on its first day.

**Proactivity.** The ability to act without being prompted. To wake up, check on things, do work, and go back to sleep on its own schedule. Without proactivity, the agent only moves when you push it. You are the metronome, and every minute you spend being the metronome is a minute the agent could spend on actual work. Honestly, who has the time to remember to bug their agents?

**Tools.** The ability to reach out and touch systems. Pull data, call APIs, generate artifacts, write to databases, trigger workflows. Without tools, the agent can think but it can’t act. It’s a brain in a jar.

A few weeks ago, I introduced Open Brain, a personal knowledge database you own, connected to your AI tools through MCP. Thousands of people in this community built their own. That solved memory — a dime a month to run, no platform lock-in, no amnesia.

What Open Brain was missing was a heartbeat. /loop is that heartbeat. It solves proactivity. And if you’ve already built Open Brain and connected it to tools via MCP, you now have all three Lego bricks snapped together. That’s not an incremental improvement. That’s a different kind of system.

Let me show you what I mean by adding one brick at a time and watching what changes.


## Proactivity alone: the agent that asks

Start with the simplest case. You’re trying to get your energy levels under control and you ask an agent to check in with you every morning.

With /loop and no memory system, the agent asks how you slept, what you ate, and how you feel. You say “tired, skipped breakfast, groggy.” It gives you some advice: drink water, take a walk, eat something. Tomorrow it asks again. “Tired, had coffee but no food, headache by 2pm.” More advice: eat a real meal, maybe cut back on caffeine.

This is already a step forward. The agent is proactive and it reaches out to you instead of waiting for you to come to it. That matters more than it sounds, because most people don’t think to check in with their AI. The prompt is the bottleneck. /loop removes the bottleneck.

But each check-in is independent. The agent has no idea what you told it yesterday. It doesn’t know you’ve said “tired” nine of the last twelve mornings. It doesn’t know that the three mornings you felt good were all days after you ate dinner before 8pm. It sees one morning at a time, and each morning is the only thing in its world.


## Add memory: the agent that learns

Now add Open Brain.

The agent does its morning check-in. It writes what you report, energy level, sleep quality, meals, anything notable, back to the database. The next morning, before it gives you advice, it reads what it wrote yesterday. And the day before. And the week before that.

“You’ve reported low energy nine of the last twelve mornings. The three good mornings were March 1st, 4th, and 7th. Checking what those days had in common...” It queries the brain and finds its own notes: all three followed evenings where you ate before 8pm and were in bed by 11.

“Your energy problems correlate strongly with late eating and late sleep, not caffeine. The caffeine experiment you ran two weeks ago didn’t help because the underlying pattern is meal timing. Suggestion: eat dinner by 7:30 tonight and get to bed by 11. I’ll check how you feel tomorrow and update the pattern.”

Stop and notice what happened. The agent didn’t just respond to a single morning’s complaint. It recognized a pattern across weeks, retrieved its own prior observations, identified the actual variable that mattered, dismissed the one that didn’t, and gave you a specific action tied to evidence it accumulated itself.

That’s the difference between a parrot repeating a phrase and a detective building a case. One recites. The other accumulates evidence and acts on the pattern. And you can’t get pattern recognition without memory.

The same principle scales directly to business. Take customer success: an agent running weekly health checks across your accounts, pulling usage metrics, support tickets, engagement data. Without memory, it tells you “Initech usage down 15%” and moves on. With memory, it reads what it wrote last week, sees that Initech was already declining and is now down 28% total, queries the brain, and finds that Meridian Systems showed a nearly identical trajectory five months ago. Declining usage, a champion departure, then silence, then churn sixty days later.

“This looks like the Meridian pattern. That account was recoverable until week three but not after. We’re in week two. Flagging for executive outreach before Friday.”

The agent didn’t just surface a metric. It pattern-matched against its own history of account failures and recommended action with a deadline. Proactivity got it running. Memory made it smart.


## Add tools: the agent that acts

Now we have an agent that can wake up on its own and learn from what it finds. But so far it can only talk to you. The third Lego brick changes that.

Tools, connected through MCP, give the agent hands. It can pull data from systems, generate artifacts, trigger workflows, reach into the services where your work actually lives. And when you combine all three bricks, you get something qualitatively different from any two of them.

Here’s an example. You go to a networking happy hour every Friday evening. I’ll admit this is partly personal: whenever I’ve been networking, it’s always been tough for me to think about what I strategically want to accomplish. Who should I talk to? What matters? These kinds of small personal challenges add up, and you may not realize how many gaps like this an agent could close.

Your agent knows about the happy hour because it’s in the brain. On Friday afternoon, /loop fires. The agent queries Open Brain for every person you’ve interacted with in the past two weeks, meetings, emails, Slack threads. It pulls context on who they are, what you talked about, what’s outstanding.

Then it calls a tool. Maybe it’s Remotion, a video generation tool you can connect via MCP. The agent passes all of those names, conversation summaries, and context to Remotion and generates a personalized briefing video. Faces, talking points, follow-ups you owe. You watch it on the way to the event. Not a text dump, but a produced visual briefing built from your own data, assembled by the agent, rendered by a tool, delivered on a schedule. That’s three Lego bricks working in concert.

Or maybe you don’t need a video. Maybe the agent just queries your calendar, cross-references it with the brain, and sends you a Slack message: “You’re seeing Sarah tonight. Last time you talked, she mentioned her team was evaluating a new data platform. You said you’d send her the writeup you did on Snowflake vs. Databricks. You didn’t. Here’s the link. You might want to send it before you walk in the door.”

Now think about the same pattern applied to other rhythms in your week. You do job applications every Thursday afternoon. /loop fires at noon. The agent reads your brain for what happened since last Thursday: projects you shipped, conversations that went well, metrics that moved. It pulls your resume from a connected drive, cross-references the roles you’re targeting, and drafts a tailored update to your cover letter with this week’s evidence baked in. It writes the draft to a doc and pings you: “Updated cover letter ready. Added the deployment metric from Tuesday and the client testimonial from the Slack thread on Wednesday. Review before your application session.”

Or you’re managing a content calendar. The agent runs every morning, checks what’s scheduled to publish this week, reads the brain for recent news or conversations relevant to upcoming posts, searches the web for breaking developments, and flags conflicts: “Your Thursday post on AI coding tools references Cursor pricing. They announced a new tier yesterday. Might want to update the comparison table before it goes live.”

Each of these follows the same cycle: wake up, read the brain, call the tools, take action, write back to the brain. You set the rhythm once and stop thinking about it. That’s not a chatbot and it’s not even an assistant you have to remember to ask. I have worked with people where you have to chase them for every single deliverable, and the exhaustion of being someone else’s metronome is exactly the exhaustion that proactivity eliminates.


## The compound loop

Here’s the principle that ties all of this together: the value of a loop isn’t in any single cycle. It’s in the accumulation across cycles.

One of the most popular uses of AI agents in the last few months is the overnight code loop. You give your agent a goal, improve test coverage, refactor a module, migrate a dependency, and let it work through the codebase while you’re not at your desk. The technique blew up because it works. Developers went from 0% test coverage to 80% overnight. Entire framework migrations happened between dinner and breakfast.

But every implementation until now required elaborate scaffolding. External tools to manage the loop. Markdown files to carry context between iterations. Completion conditions bolted on with duct tape. The reason was simple: the agent had no native way to run on a schedule, and no native way to remember what it did last iteration.

/loop solves the first problem. A memory system solves the second. Together, they turn a fragile hack into a clean architecture. And the pattern works well beyond code.

Your agent runs every morning at 6am against your sales pipeline. Each cycle, it reads the memory system: “Yesterday I reviewed 34 inbound leads. Eight met ICP criteria. Of those, three already had active conversations in the CRM and I flagged them for follow-up with context notes. Two were duplicates of leads we lost in Q2; I tagged them as winback candidates and pulled the original loss reasons from the deal notes. The remaining three are net-new and qualified, and I drafted first-touch emails using the messaging that got the highest reply rate last month. The SMB segment is fully triaged. Mid-market has 140 unreviewed leads and is the priority for tomorrow.”

Next morning, it picks up with mid-market. It doesn’t re-triage SMB. It doesn’t redraft emails it already queued. It doesn’t miss that two of today’s leads work at the same company as a winback candidate it identified yesterday, because it remembers yesterday. By Friday, it has triaged the full pipeline with a coherence that no single pass could achieve, because Thursday’s triage was informed by patterns it only noticed on Wednesday.

Twelve passes where each one builds on the findings of the previous eleven is not twelve times as good as one pass. It’s qualitatively different, because later passes have access to insights that earlier passes generated. The eighth cycle knows things the first cycle couldn’t have known, because the first cycle hadn’t happened yet. Without memory, you get twelve first passes, each one starting from zero, each one as uninformed as the first.

Andrej Karpathy open-sourced a project recently called autoresearch that illustrates this perfectly. It gives an AI agent a training setup for a small language model, a single GPU, and a clear success metric, then lets it run experiments overnight. The agent modifies the code, trains for five minutes, checks if the metric improved, keeps or discards the result, and loops. About a hundred experiments overnight with zero human intervention.

The key architectural decision was the same one we’ve been talking about: a persistent log of what the agent tried, what worked, and what didn’t. Without that log, the agent would be running random experiments, no better than a brute-force search. With it, each experiment is informed by the full history of previous experiments. The search becomes intelligent. It converges.

Shopify’s CEO Tobi Lutke adapted the approach, let it run overnight against an internal model, and woke up to a 19% improvement in validation scores after 37 experiments. An agent-optimized 0.8 billion parameter model outperformed a 1.6 billion parameter model that had been configured by a human. Not because the agent was smarter in any single cycle, but because it ran dozens of cycles and remembered all of them.

Now generalize beyond ML research. Maybe you’re tracking a competitor, or researching a market, or monitoring regulatory changes in your industry, or following a technical domain like AI that moves fast.

Without memory, an agent checking on these things every morning gives you a snapshot. Useful, but flat. You’re still the one holding the longitudinal picture in your head, connecting this morning’s news to last week’s trends to last month’s strategic shift.

With a memory system, the agent builds that picture for you. Each morning it reads what it wrote previously, the trends it identified, the predictions it made, the questions it flagged, and uses that as context for interpreting today’s information. “Three weeks ago I noted that Company X was hiring aggressively in the payments space. Last week they filed two patent applications in cross-border settlement. This morning they announced a partnership with a Southeast Asian bank. This looks like a coordinated push into cross-border payments, not a one-off hire.”

That’s three data points across three weeks, none of which means much in isolation, all of which tell a clear story when connected. A human doing this manually would need to remember the hiring signal from three weeks ago, notice the patent filing, and connect both to this morning’s announcement. In practice, the hiring signal would be long forgotten, flushed from working memory to make room for whatever was urgent that week.

Your brain can’t hold a three-week thread while also running your day. The agent holds it natively, because nothing falls out.


## The OpenClaw stack without the chaos

If you’re thinking that everything I’ve described sounds a lot like OpenClaw, you’re right. It is. Just without the chaos.

About a month ago when I wrote about OpenClaw, I had to talk about the fact that it was a security nightmare. People were opening their networks to the wider internet. They were giving their agents access to data they shouldn’t have been exposing. They were downloading extensions with severe security vulnerabilities that generated Cisco threat reports. Security researchers called it dangerous, the project went through three different names after trademark disputes and crypto hijackings, and none of it slowed down the demand. Jensen Huang called it the most popular open-source project in the history of humanity and “definitely the next ChatGPT.” More than 200,000 GitHub stars, the fastest-growing open-source project on record. People are hungry for agents that do real work, and the obstacles got routed around.

What /loop plus Open Brain gives you is the same core capability, an autonomous agent with persistent memory and the ability to act, without the security exposure. The heartbeat comes from Anthropic’s runtime, not a bash script on a Raspberry Pi. The memory lives in a database you control, accessed through a standard protocol, not a rogue orchestration layer with prompt injection vulnerabilities.

Now, common sense still applies. If you store your blood type in your personal database and then tell the agent to use an MCP tool with open internet access without constraining it properly, there’s a potential risk that the agent could get prompt-injected somewhere on the web and exfiltrate that data. Think about what you put in the memory and what tools you give the agent access to. But the risk profile is fundamentally different from running OpenClaw with unchecked extensions on your home network.

And here’s the architectural point that matters most: you own the memory layer. The scheduling is Anthropic’s. The knowledge is yours. If Claude adds native persistence next month, you’ve lost nothing. If you switch to a different AI tool entirely, your Open Brain comes with you. The scheduling primitive is platform-specific. The memory is infrastructure you control. That separation is what makes this durable. Peter Steinberger, who created OpenClaw, has been clear that he doesn’t see the project as something non-technical users should run because of the risks involved. Part of why he joined OpenAI is because he wants to build something with OpenClaw-like capability that’s secure enough for everyone. While he’s building that, you don’t have to wait. The basic Lego bricks are on the table right now.


## The morning briefing: where every brick fires at once

There’s one use case where all three primitives run simultaneously and the compounding is most visible. The daily standup with yourself.

You’re running projects. Code is in flight. PRs are open. Teammates are posting in Slack. Clients are sending emails. Your agent has been working overnight, monitoring, reviewing, researching, writing everything it found to your Open Brain, acting through its tools.

You sit down with coffee. Your agent already knows what happened since you left.

“Three things overnight. First, the staging deploy I was monitoring went unhealthy at 1:40am. I identified a memory leak in the new caching layer, rolled back to the previous version, and it stabilized by 2:15am. The caching layer had a similar issue on February 22nd, same root cause, same resolution. I’ve flagged this as a recurring pattern that probably needs an architectural fix rather than another rollback.”

That’s memory bridging sessions, connecting tonight’s incident to one two weeks ago you’d already forgotten.

“Second, the PR I’ve been reviewing got updated overnight. The author addressed the performance issue I flagged yesterday, but the fix introduced a new edge case in the error handling. I’ve commented on the PR with a suggested fix and a test case.”

That’s the compound loop: three cycles of review building on each other, each one informed by the last.

“Third, that Southeast Asian payments push I’ve been tracking? They announced pricing this morning. They’re undercutting the market by 40%. Given the patent filings and the hiring pattern from the past three weeks, this looks like a loss-leader strategy to grab market share. Might be worth discussing in the strategy meeting Thursday.”

That’s tools pulling data, memory connecting it across weeks, and proactivity surfacing it before you asked.

A morning briefing without memory is a news feed. A morning briefing with all three Lego bricks is a chief of staff.


## What’s still missing

I’ll be direct about the gaps, because this is a composable stack, not a finished product.

There’s no built-in “done” signal. /loop runs until it expires or you stop it. For goal-directed work like “keep improving test coverage until you hit 80%,” you need to tell the agent to check the brain for a completion state and stop when it finds one. That works, but it’s manual. It should be native.

Everything is session-scoped. Close your laptop and the heartbeat stops. Anthropic offers desktop-level scheduling, but seamless always-on operation across restarts isn’t here yet.

And the skill ceiling is real. /loop lives in Claude Code, and whether we like it or not, the terminal is still daunting for a lot of people. Telling an agent what to check every five minutes is easy. Telling it what to write to the brain, how to interpret patterns across sessions, and when to escalate versus act autonomously, that’s a design problem, not a prompting problem. It requires thinking about memory hygiene the same way you think about code hygiene. What’s worth remembering? What’s noise? When does accumulated context help the next cycle, and when does it create confusion?

These are new questions. But they’re the kind that close fast once the base primitives exist. And the base primitives exist now.

I want to leave you with something I think about a lot when I talk about tools that live in the terminal. The tools I’m describing will eventually come through in more user-friendly environments. Cowork, Claude’s chat interface, ChatGPT. It’s going to happen. But developers are the deliberate, strategic beachhead for every hyperscaler right now, which means developer tools get agent capabilities before anyone else.

If you’re willing to go to the terminal, you get free time travel. You get to go months ahead of everyone who’s waiting for the friendly UI to arrive. If I told you that you could time travel by using a different window on your computer, most people wouldn’t believe me. And the ones who did would try it immediately.

That’s what the terminal is right now. If you’re willing to dip a toe in, you can time travel.


## Where this goes

Everything in this piece works with what you already have. Open Brain is the memory. /loop is the heartbeat. Claude Code is the hands. MCP is the nervous system connecting them. No new tools, no new infrastructure. Just a new way of thinking about what your system can do now that the agent doesn’t wait for you to wake up.

The next build is the visual layer, the dashboard you check with your morning coffee to see what the agent found overnight. That’s coming. But the loops don’t wait for the dashboard. You can start every use case in this piece today, right now, with what you have.

Pick the one that resonated. Set the heartbeat. Let the agent compound.

You built a brain. Now it has a pulse.

[![](https://substackcdn.com/image/fetch/$s_!FjKD!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdab8d780-588e-4a99-98dc-8086445f4231_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!FjKD!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdab8d780-588e-4a99-98dc-8086445f4231_1024x1024.png)
