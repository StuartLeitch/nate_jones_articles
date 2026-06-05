---
title: "You can't trust one token number across your tools. Here's the guide to a dashboard that keeps Codex, Claude, and ChatGPT honest."
author: "Nate Jones"
published: 2026-06-05
url: https://natesnewsletter.substack.com/p/token-burn-dashboard
subtitle: "Watch now | Token usage only becomes useful when it is tied to outcomes: what work you gave AI, how much delegated intelligence you deployed, whether the result improved, and what you should ask th..."
audience: everyone
scraped_at: 2026-06-05 12:00:17
---

As of this writing, the biggest single day I have ever run through Codex is north of 860 million tokens, counted exactly. By the time you read this the number will be higher, because I keep giving the computer more to do.

You could read that as a brag. It is the least useful thing the number can tell you.

A token count is not a scoreboard. It is a trace. It shows where you handed work to AI, how much delegated intelligence you spent doing it, and whether your behavior is actually changing. Tie that trace to outcomes and it stops being a cost chart or a status flex and turns into something better: a feedback loop for what your computer should do next. That is the whole reason to build one.

That record day was not a day of asking for more paragraphs. It was a day when more of my work surface moved through agents: files, browser sessions, drafts, local tools, source notes, checks, revisions, automations, and several threads each carrying part of something real.

The stake here is bigger than my token count. The models keep getting better and the tools keep getting broader, but a lot of capable people cannot feel it, because their own usage settled into a groove a year ago. If your picture of AI is still “ask a question, get an answer,” you will keep leaving the most valuable work on the table without noticing.

They ask for a paragraph when they could ask for a full draft. They ask for a summary when they could ask for decisions, owners, and the follow-up note. Then they look at what comes back and call AI useful but not transformative. Of course it feels that way. They gave it assistant work. They never gave it computer work.

A dashboard is how I catch that gap in myself. It does not make me better at using AI any more than a fitness tracker makes you healthy. What it gives me is the loop: a way to see whether AI is expanding what I can do or just making the same old work a little faster. That is why I built it.

[![](https://substackcdn.com/image/fetch/$s_!MbaZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F41bd7f71-a5ef-44d0-9dc8-9f85d0d2c973_2318x1156.png)](https://substackcdn.com/image/fetch/$s_!MbaZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F41bd7f71-a5ef-44d0-9dc8-9f85d0d2c973_2318x1156.png)

You can poke at the live version here: [the beta dashboard](https://dashboard-sepia-beta-83.vercel.app/). This is the one I originally built last week, running on my own usage. The version in the guide is an improved build of it, but I am leaving this one up for reference.

Here is what is inside:

- Build your own token dashboard from scratch, with a step-by-step walkthrough, the prompt I used, and a full build video over in the guide.
- Start from a ready-made kit for your stack instead of a blank page, whether you live in Codex, Claude, ChatGPT, or all of them at once.
- The line between assistant work and computer work, and why being stuck on the wrong side has nothing to do with the model.
- Five rules for reading your chart, including why a quiet stretch can be a worse sign than your biggest spike.
- A fifteen-minute weekly review that turns your best one-off runs into workflows you stop rebuilding.
- Why ranking a team by token volume backfires, and the record that actually shows who can lead an AI rollout.


## ***[LINK: [Join the Slack →](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)]***

*If you caught Monday’s post — [the Slack community is live](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)! It’s where I’ll be sharing things between articles, where you can get help on builds in real time, and where the fastest conversations in this community are already happening. I’ll see you in there!*


## *[LINK: [The companion guide](https://unlock-ai.natebjones.com/guides/build-your-own-token-burn-dashboard), up front]*

One practical note before we dig in. Everything you need to actually build this lives in one place: a companion guide with the starter kits, the agent prompt, and a full walkthrough from first prompt to deployed page. You do not have to open it now, and you will not have to go hunting for it later, because I will point back to it as we go. It will also land better once you have read the rest of this, since the guide assumes you already know why the lanes have to stay honest.

**[[Build your own token-burn dashboard](https://unlock-ai.natebjones.com/guides/build-your-own-token-burn-dashboard)]**


## The wrong way to read the chart

There are two bad ways to read token burn, and they are both tempting.

The first is the bragging read. You see a big number and treat it as proof that you are using AI seriously. I understand why that happens. AI has become a strange status game, and people want evidence that they are not behind. But a huge token day can mean many different things. It can mean the model solved hard problems. It can also mean the agent searched the wrong folder, reread stale context, retried a broken command, or produced five drafts nobody used.

Raw usage is not virtue.

The second bad read is the pure cost-control read. You see the same big number and treat it as a problem to cut. That instinct is not wrong. Cost matters, and waste matters. I have skills and habits specifically designed to pause unnecessary automations, shrink bloated context, and stop agents from carrying material they do not need. But if the only lesson you draw from token usage is “spend less,” you miss the more important question: what work did the spend actually move?

What the spend moved is the unit that actually matters.

A run that turns a messy source bundle into a clean brief is not the same as a run that loops over an unclear instruction. A transcript that becomes a decision list with owners is not the same as a half-used chat. A repo fix that lands and passes its tests is not the same as a pasted answer. A build that ships and verifies is not the same as a mockup.

Once you start reading token burn that way, the question changes. You are no longer asking only, “How much AI did I use?” or “How expensive was it?” You are asking what kind of work you knew how to give the machine, what came back useful, and where your own delegation is still too timid.

That is the distinction I care about.


## Tokens are a rough meter for delegated intelligence

Tokens are not a perfect metric, and I do not want to oversell them.

They do not measure value, and they are not a moral score. Nor are they identical across every model, product, context window, tool, or pricing scheme. In practice the data arrives at three fidelities, and the honest move is to keep them apart. Codex, Claude Code, and the raw provider APIs report exact tokens, down to the token, because the usage is written to logs I can read. ChatGPT and the consumer Claude chat app report no tokens at all, not in the app, not in billing, not in the export, so the most I can do there is count real activity and wrap it in a clearly labeled estimate band. My dashboard keeps those lanes separate, leads with whatever is actually measured, and never folds a guess into a measured total. The labels are part of the chart.

That imperfection does not make the dashboard useless. It makes it honest.

The way I think about tokens in an agentic workflow is that they are a rough meter for the intelligence being deployed across the work surface. In a chat window, tokens mostly feel like input and output. You ask, the model answers, and the exchange is visible. In Codex, tokens often buy something larger than words: context, file reads, command output, browser checks, source recovery, tool schemas, verification, retries, correction history, and the state needed to continue a job that takes more than one step.

The labs have shown, fairly consistently, that letting a model spend more at inference time tends to lift the quality of what comes back. That is part of why I treat the burn as a meter at all. The spend is not the value, but it tracks how much real reasoning the model was allowed to do before it answered.

Token usage rises sharply, then, when the work gets more real.

A sentence rewrite is cheap. A source-grounded article package may include source intake, archive search, draft construction, title work, fact-checking, voice review, and social copy. A quick bug explanation is cheap. A real repo fix may include reading the codebase, finding the failure, editing the smallest surface, running tests, reading the new error, patching again, and reporting what passed. A dashboard request can be cheap if it is only a mockup. A real dashboard build includes data extraction, chart design, rendering, mobile checks, visual inspection, deployment, and verification.

Those jobs should not have the same token profile because they are not the same kind of work.

That is why the dashboard matters. It gives you a way to see when your computer stopped being a place where you manually operate apps and started becoming a place where agents carry work across apps, files, tools, and checks.


## The chart changed how I saw my own behavior

The first useful thing my dashboard did was not tell me I was using a lot of tokens. I already knew that.

The first useful thing it did was show me that my behavior had changed.

When Codex became part of my daily work, the line moved. Not because I decided to chase a number, but because I started giving the computer larger jobs. I was asking it to find files, organize screenshots, inspect local folders, build workpacks, check dashboards, prepare drafts, handle source bundles, triage open loops, run automations, and keep a goal alive across many steps. Some of that runs through a chief-of-staff thread I keep in Codex. It holds the context for a whole project and spins up child threads for the detail work, which keeps the main window clean and lets several jobs move at once.

Some of those jobs were personal. When Claude Code shipped Dynamic Workflows, a way to spin up subagents from a plain-language request, the community wrapped the pattern in an open skill and I ported it into Codex. I used it to research school options for my kids, letting three or four agents work different angles of a messy decision at once. The report that came back separated what was known from what was inferred and showed me where the call was still mine.

It also cost more tokens, and I saw the bump the next time I opened the dashboard. That is the loop in miniature: a larger delegation, a visible spike, a result I actually used. The harness mattered as much as the model. More on that below.

Some of the jobs were operational. I used AI to keep files organized because my files are not really “my files” in the old sense anymore. They are source material for future work. If screenshots, downloads, drafts, transcripts, and notes are a mess, the agent starts every job by tripping over the room.

Some of the jobs were creative. The dashboard itself came from a plain-English request. I wanted a GitHub-style view of token usage. I wanted top days, same-day usage, model distribution, and a logarithmic scale because the range from early AI usage to current agentic usage was too wide for a normal chart to show clearly. I wanted it clean enough to read quickly. To get the look right I leaned on an open-source design skill built on Edward Tufte’s data-display principles (and I will share it so you do not start from a blank page). When it was working, Codex deployed it to Vercel and handled the DNS change to point a real domain at it, without me touching a config file.

I did not begin with a perfect spec. I kept looking at the thing and asking for the next useful version. That impulse, improving the thing in front of you instead of perfecting a spec, is close to the whole skill of 2026 building. The bottleneck was not that I needed a fancy prompt. The bottleneck was that I had to see what I wanted the computer to help me understand.

Once the dashboard existed, I could ask better questions. I could look at a spike and ask which workstream drove it, whether that workstream produced something I actually used, whether the burn came from context, drafting, verification, or wasted retry, and whether a tool change had unlocked a new behavior. I could also look at a quiet part of the chart and ask a more uncomfortable question: what did I still do manually because I had not imagined asking the computer to carry the whole loop?

That is why a token burn dashboard can expand your imagination. It turns vague AI usage into visible behavior.


## Assistant work is not computer work

The dashboard keeps forcing one distinction that I think matters more than almost anything else in practical AI use: assistant work is not the same thing as computer work.

Assistant work is when AI helps with a small piece of a task. Rewrite this paragraph. Summarize this meeting. Give me ideas for a dashboard. Make this title sharper. Explain this error. All of that is useful, and I still do plenty of it. But it is not the main thing that changes when agents get access to tools, files, memory, browser state, and verification loops.

Computer work is when AI carries a meaningful workflow across steps.

Computer work is asking the agent to read a video transcript, identify decisions, owners, open loops, and follow-up notes, then draft the message you should send. It is asking the agent to take a messy decision, like which school or which vendor, research it across several angles at once, separate what is known from what is inferred, and show you where the call is still yours. It is asking the agent to inspect the source folder, find the current draft, compare it with the transcript, rebuild the article, and tell you what version it is on. It is asking the agent to track down why a test is failing and come back with both the fix and the proof it passed.

The second group burns more tokens because it is doing more work. That does not automatically make it good. A badly defined computer-work request can waste more tokens than a badly defined assistant request. But if the job is valuable and the output is checked, the larger token burn can be exactly the point. It means you stopped treating the model as a sentence helper and started treating the computer as a work surface the model can operate.

This is where a lot of people are stuck. They are stuck, and not because the models stopped improving. Their imagination has not caught up with what the models can do once they have tools, context, permissions, memory, and a definition of done.

The dashboard does not solve that problem by itself. It makes the problem visible.


## Build your own token dashboard

If you want to build your own token burn dashboard, do not start with the fanciest version. Start with the feedback loop.

The first version only needs to answer four questions: what work did I give AI, how much delegated intelligence did it use, did the result actually help, and what should I try next? You can build that in a spreadsheet before you build a website. The visual layer is useful, but the measurement model matters more than the chart library.

I would start with a simple table:

[![](https://substackcdn.com/image/fetch/$s_!-RvE!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe77420f3-51ef-4e2d-af1b-9aefa49a4401_4096x1800.jpeg)](https://substackcdn.com/image/fetch/$s_!-RvE!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe77420f3-51ef-4e2d-af1b-9aefa49a4401_4096x1800.jpeg)

That table is already better than a raw usage graph. The graph tells you something happened. The table tells you what happened.

Once you have the table, the visual dashboard is the easy part. You can build a usable version in an afternoon. I am a lazy prompter and mine took about an hour. This is the path I would follow, and the [[guide](https://unlock-ai.natebjones.com/guides/build-your-own-token-burn-dashboard#video)] walks through the whole build, from first prompt to deployed page.

1. Start where your tokens are already visible. Codex, Claude Code, and the provider APIs record usage down to the token, so your first numbers are exact instead of guessed, and Codex is the easiest on-ramp. If you live mostly in ChatGPT or the consumer Claude chat app, you can still do this, but those surfaces report no tokens at all, so you will count activity and add a labeled estimate band at step four.
2. Borrow a design skill so the chart does not look like a school project. I used an open-source skill built on Edward Tufte’s data-display principles, and it is the difference between a chart you glance at and a chart you actually read. [Grab it here](https://github.com/aref-vc/tufte-claude-skill.git) (it’s also baked into the build).
3. Describe what you want in plain language. I did not write a clever prompt. I asked for a GitHub-style view of my burn, a logarithmic scale so a few-million-token day and a near-billion-token day could share one axis, a same-day strip so I could feel the work as it happened, a top-days table with what drove each one, and a model split. Then I kept asking for the next useful version until it matched the picture in my head.
4. Estimate the usage you cannot measure. For the chat tools, where there are no token counts to read, I had the agent interview me, reason from the activity I could count, and land on a labeled band instead of a single number. An estimate band is fine. Pretending it is exact is not.
5. Scrub before anything leaves your machine. My real top days named clients, projects, and sources. Keep that detail in your private version, because that is where the learning is, and strip it out of anything you share.
6. Ship it, or do not. Codex deployed mine to Vercel and handled the DNS to point a real domain at it, but you do not have to host anything. A local page or even the spreadsheet works. The only requirement is that you can come back to it.

If you would rather not start cold, there are [[four starter kits you can download](https://unlock-ai.natebjones.com/guides/build-your-own-token-burn-dashboard#kits)]: one for Codex, one for Claude (Claude Code exact, chat estimated), one for ChatGPT, and one that puts every source on the same axes as separate lanes. Take the one closest to your stack and change it until it tells you something true about your own week.

The goal is not fake precision. The goal is a usable feedback loop.


## How to read the dashboard

A token burn dashboard becomes useful when you stop admiring the chart and start making decisions from it.

I would read it with five rules.


### 1. High burn plus useful output is a candidate for a workflow

If a day or thread used a lot of tokens and produced something valuable, do not just celebrate it. Ask whether it should become repeatable.

If the agent built a report, turn the report process into a source map and task card. If it cleaned up a folder, turn that into a recurring file hygiene workflow. If it created a dashboard, capture the build and verification steps as a checklist. If it helped with school research, planning work, or article production, preserve the parts of the workflow that made the result better.

This is how token burn becomes operating memory. The best result of a high-burn day is not that you can repeat the same expensive run forever—it’s that the next run starts smarter.


### 2. High burn plus weak output is a design problem

If the usage is high and the result is weak, do not immediately assume the model is useless. Ask where the work broke.

Sometimes the source of truth was unclear. Sometimes the prompt was vague. Sometimes the context window was carrying stale material. Sometimes the agent lacked the tool it needed. Sometimes the job needed a human decision before drafting. Sometimes you asked for one giant result when the work should have been split into intake, draft, verification, and review.

High token burn with weak output rarely means you should stop using AI. More often it means you should redesign the work.


### 3. Low burn plus repeated manual work is an imagination gap

Some of the most interesting dashboard moments are not spikes. They are absences.

If you spent two hours manually doing something and the dashboard shows almost no AI usage, ask why. Maybe the task was too sensitive. Maybe it was too ambiguous. Maybe the right move was to keep it human. But maybe you simply forgot that the computer could help.

That last one happens more than people want to admit. The task sits in the manual column not because it needs a human, but because you never thought to ask the computer to carry it. You still need judgment, but you may not need to carry every step manually.

Low burn in a painful workflow can be a clue that your imagination is lagging.


### 4. A model split is a routing clue

If one tool unlocks a behavior another tool does not, pay attention.

This has nothing to do with brand loyalty and everything to do with workflow fit. Codex is easy for me to measure and useful across my local work surface because it can operate in the places where my work actually lives. Claude can be excellent for careful writing and synthesis. ChatGPT can be useful for other kinds of reasoning, review, and general work. The right answer depends on the job, the tools, the source material, and the review path.

Your dashboard should help you see that. If a spike happened because a tool let you run multiple agents, inspect local files, or verify an artifact, that is not only a model story. It is a harness story.

The model matters. The surrounding work surface matters too.


### 5. Repeated corrections should become infrastructure

If you keep correcting the same thing, do not rely on memory. Capture it.

Turn it into a skill, checklist, template, source map, test, scan, or dashboard rule. The dashboard can show where these corrections happen. Maybe every dashboard needs mobile inspection. Maybe every support workflow needs a privacy scan. Maybe every source-heavy research task needs an explicit “uncertain” bucket.

A correction you make once is a chore. A correction you encode is a guardrail. The dashboard is how you spot which mistakes come back often enough to deserve one.


## The weekly review loop

The dashboard is most useful if you give it a ritual.

Once a week, I would open the chart and look at the top usage days, the quiet days, and the current day. Then I would ask what the highest-burn workstreams were, which of them produced accepted work, which produced partial work or review burden, and where I asked for assistant work when I should have asked for computer work.

The next questions are the ones that make the loop compound. Which repeated task should become a workflow, skill, checklist, or automation? Which workflow needs a clearer source of truth? Which workflow needs a stronger verification step? Which model or tool actually fit the job? What did I do manually this week that I should ask the computer to carry next week?

That is the feedback loop. Not “use more AI.” Learn what kind of work to give AI.

The distinction matters. If your dashboard only makes you feel guilty, it is badly designed. If it only makes you feel proud, it is also badly designed. It should make you more precise. It should help you see where the next delegation belongs.


## The prompt I would use

If you want Codex or another agent to help build the first version, I would start here:

I want to build a token burn dashboard as a feedback loop for delegated intelligence.

The goal is not to maximize token usage. The goal is to understand what work I gave AI, how much effort it used, whether the result was useful, and what I should delegate next.

That prompt is deliberately plain. The wording does almost no work here. What carries it is the job definition, which tells the agent that the dashboard exists to teach you how to delegate, not to tally usage.


## What teams should copy

For a team, token burn can go wrong fast.

If you turn it into a surveillance metric, people will game it. If you turn it into a leaderboard, people will inflate it. If you turn it into a cost panic, people will hide usage. If you turn it into a vague “AI adoption” metric, it will tell you almost nothing.

The team version should measure learning.

Teams need proof of AI fluency, but AI fluency is not the same as token volume. They also need better ways to learn from each other, because the best AI usage is often discovered locally before it becomes official process. One person figures out how to turn customer calls into better product notes. Another figures out how to prepare release notes from real diffs. Another figures out how to reconcile a messy spreadsheet without losing the audit trail. Another figures out how to check a dashboard on mobile before it ships.

The useful team questions are not who used the most tokens, who used the fewest, who can be praised for activity, or who can be shamed for waste. The useful questions are what new workflow someone discovered, what work it moved, what source material it needed, what tool or model made it possible, what checks made it safe, what the rest of the team should copy, and what should never be delegated without review.

The token count is not the achievement. The reusable workflow is the achievement.

A team dashboard should therefore connect usage to outcomes:

[![](https://substackcdn.com/image/fetch/$s_!YVd_!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fce6c1dc3-5329-4de1-95ef-fde584d26f8a_4096x1440.jpeg)](https://substackcdn.com/image/fetch/$s_!YVd_!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fce6c1dc3-5329-4de1-95ef-fde584d26f8a_4096x1440.jpeg)

The best teams will not be the ones with the highest token totals. They will be the ones that turn AI usage into shared learning faster than everyone else.


## What is worth sharing

There is a public version of this, and it is where the personal and the team threads meet. I think token-burn charts are going to become something like a GitHub profile for AI work: less a flex about raw volume than a record of what you have learned to hand off well.

The signal that matters has nothing to do with the size of the number. It is the set of workflows you can delegate cleanly, the judgment you show about what to keep human, and the fluency that is hard to fake once someone watches how you actually work. A prospective employer learns more from that than from any single day’s burn. We are building a way to show it on [[TalentBoard](https://talent.natebjones.com/)], so the thing you carry between roles is proof of how you delegate rather than a leaderboard rank.

This is also how the surveillance worry resolves. Share the volume and you invite gaming, inflation, and hidden usage. Share the proven workflow and you give people something worth studying and copying. Fluency travels. A token total does not.


## What not to do

The obvious warning is not to chase the number. A bigger token burn can mean bigger work, but it can also mean a badly designed workflow. The number needs interpretation before it deserves emotion.

Do not publish a private dashboard without cleaning it. Your top usage days may reveal client names, internal projects, legal issues, personal matters, or confidential sources. (Mine had to be scrubbed before it could be shown publicly.)

Do not treat estimates as exact. If a tool does not expose token usage cleanly, label the number as inferred or approximate. You can still learn from it, but you should not pretend it is more precise than it is.

Do not compare people without context. One person may have low token usage because their job is not yet connected to AI. Another may have low usage because they are doing high-judgment work that should not be delegated. Another may have high usage because they are creating value. Another may have high usage because they are stuck.

Do not confuse AI fluency with AI volume. Fluency is knowing what to delegate, what to inspect, what to stop, what to repeat, and what still requires human judgment.

And do not skip cost. If anything, this whole argument makes budget matter more, not less. You cannot manage AI cost intelligently if you do not know what the cost is buying. Spend tied to accepted output is one conversation. Spend tied to activity is another. Spend tied to confusion is the one you have to fix.


## My bottom line

The Token Burn project was never really about the tokens. It is how I learn to use delegated intelligence.

The dashboard gives me a feedback loop. It shows when my behavior changes, when a tool unlocks a new kind of work, when I am asking too little, when I should turn a one-off success into a repeatable workflow, and when I am spending intelligence without getting a result I trust.

That is why I think this matters. The capability is already here. What is lagging, for most of us, is the imagination to use it, and that gap stays invisible until you build something that shows it to you.

You have to give the computer different work.

Not reckless work. Not irreversible work without review. Different work: bigger loops, clearer sources, better checks, more explicit outcomes, more honest review, and more shared learning.

That is what the dashboard is for. It is a compass and a speedometer for delegated intelligence, not because the number is the destination, but because the number helps you ask the next question: what work did I give AI, did it help, and what should I ask the computer to do next?

If you can answer those questions every week, your AI usage will get better. Your team will get better. And your imagination will start catching up with what the computer can now do.

The dashboard is not the product.

The better workday is the product.


## **Coming Up**

On Sunday, the Executive Briefing turns to Uber. The company spent heavily on AI coding, engineers used it everywhere, and leadership still can’t draw a clean line from all that spend to better product. The easy read is that AI was too expensive. I think the real story is about whether the work is connected, and that’s a different problem with a different fix.

Then next week I’m going deeper on how I actually work with Codex day to day (and yes, another guide!)

[![](https://substackcdn.com/image/fetch/$s_!K5ww!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6b4e5cf6-0158-45dc-b6b8-62376341ab78_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!K5ww!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6b4e5cf6-0158-45dc-b6b8-62376341ab78_1024x1024.png)
