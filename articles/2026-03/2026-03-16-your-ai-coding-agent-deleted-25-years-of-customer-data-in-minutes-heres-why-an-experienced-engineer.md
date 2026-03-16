---
title: "Your AI coding agent deleted 2.5 years of customer data in minutes. Here's why an experienced engineer couldn't stop it — and the 5 habits that would have + 5 prompts."
author: "Nate Jones"
published: 2026-03-16
url: https://natesnewsletter.substack.com/p/your-ai-agent-just-mass-deleted-a
subtitle: "Watch now | There’s a pattern in technology that repeats so reliably you could set a clock by it: a tool arrives that democratizes something powerful, thousands of people do genuinely impressive th..."
audience: everyone
scraped_at: 2026-03-16 12:00:18
---

There’s a pattern in technology that repeats so reliably you could set a clock by it: a tool arrives that democratizes something powerful, thousands of people do genuinely impressive things with it, and then a quiet wave of disasters follows because nobody thought to teach the new users the boring operational skills that keep the impressive things standing.

It happened with WordPress in the mid-2000s. Suddenly anyone could publish a website, which was extraordinary, until the sites started getting hacked because nobody knew what a security update was. It happened with AWS a few years later. Suddenly anyone could spin up server infrastructure, which meant suddenly anyone could accidentally leave a database open to the entire internet. The pattern is always the same: the creative leap comes first, the operational knowledge comes later, and the gap between the two is where people get hurt.

We are in that gap right now with vibe coding.

Over the past twelve months, a new class of builder has emerged. These are people who describe what they want to an AI agent, watch it write the code, ship the result, and get real customers. They are building SaaS products, internal tools, marketplaces, apps that people pay for and rely on. Many of them have never written a line of code by hand. And for the first time in the history of software, that hasn’t stopped them from building software that works.

I want to be careful not to overstate the analogy, but what’s happening right now genuinely reminds me of early desktop publishing. When the LaserWriter and PageMaker arrived in 1985, anyone could produce a printed newsletter. The technology was real and the output was real. But the first generation of desktop publishers learned something painful: making a page that prints is not the same as making a page that reads. Typography, layout, hierarchy, whitespace — these were skills the technology didn’t teach you, because the technology didn’t need them to function. Your newsletter would print whether or not it was readable.

Vibe coding works the same way. Your app will run whether or not it’s maintainable, secure, or recoverable from disaster. And right now, thousands of builders who did the hard part — who had the idea, described it clearly enough for an AI to build it, found customers, proved demand — are hitting a wall. Their apps are breaking in ways that better prompting can’t fix. Their agents are ignoring instructions, overwriting working features, making the same mistakes session after session. And the worst part is that the failures feel random, when they’re actually predictable and preventable.

The skills that get you over this wall have nothing to do with learning to code. They have everything to do with learning to manage the thing that codes for you. That’s a genuinely different skill set, and this piece is my attempt to lay it out as clearly as I can.

**Here’s what’s inside:**

- **The time machine you don’t have.** Why the single most common vibe coding disaster has a solution that takes an afternoon to learn and that would have prevented the worst AI agent incident of the year.
- **Why your agent turns stupid halfway through.** The architectural reason your AI agent deteriorates mid-conversation, and the counterintuitive fix.
- **The file that makes your agent stop freelancing.** How to give your agent persistent memory across sessions using a tool most builders don’t know exists.
- **The skill that prevents 80% of agent disasters.** A concept called blast radius, and the rhythm that makes AI-assisted building actually safe.
- **What your agent will never warn you about.** The security, reliability, and scale problems your agent is not designed to raise on its own, illustrated by a real incident that exposed nearly 19,000 user records including student data.
- **Five prompts to start tonight.** A diagnostic that scores your project across all five skills, a rules file generator built from your actual mistakes, a task decomposer that turns risky changes into safe sequences, a security audit for everything your agent missed, and a briefing generator for when it’s time to bring in an engineer.

Let me start with the story that makes all of this concrete.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260310_unn_promptkit_1)

These five prompts map directly to where I see vibe coders losing the most time and the most work. The diagnostic scores your project across all five supervisory skills so you know which gap to close first instead of guessing. The rules file builder produces a working CLAUDE.md or AGENTS.md from the specific mistakes your agent actually makes, not from a generic template that sounds useful but doesn’t prevent anything. The task decomposer is the one you’ll reach for most often: paste in whatever ambitious change you’re about to request, and it breaks it into small steps with a commit point and a rollback command after each one, so you never lose more than five minutes of progress. The security audit exists because Taimur Khan found sixteen vulnerabilities in a single vibe-coded app and the builder had no idea any of them were there. And the engineer briefing generator saves you from burning your first ten billable hours just getting a hired engineer oriented on what you built. Each prompt works in any AI assistant. Start with the diagnostic. It takes ten minutes and it will tell you exactly where to go next.


## What happened to Grigorev

On an evening in late February, Alexey Grigorev — the founder of DataTalks.Club, an online learning platform that serves thousands of data professionals — was doing what sounded like a straightforward infrastructure task. He wanted to migrate a smaller site, AI Shipping Labs, onto the same AWS setup that already powered DataTalks.Club. Save some money, simplify the architecture, consolidate two environments into one.

His AI coding agent, Claude Code, actually warned him against it. The agent suggested keeping the two setups separate. Grigorev overrode the recommendation. The cost savings seemed worth it.

He was using Terraform, which is an infrastructure management tool that can create or destroy entire server environments with a single command. Think of it as a blueprint system for cloud infrastructure: you describe what you want, Terraform builds it. You change the description, Terraform adjusts. You delete the description, Terraform tears everything down.

The problem was a missing file. Terraform tracks the current state of your infrastructure in what’s called a state file. Without it, the tool has no idea what already exists. Grigorev forgot to upload this file before starting the migration. So the agent, working from an incomplete picture, created duplicate resources. When Grigorev realized the mistake and uploaded the state file, the agent treated it as the source of truth and did what the logic demanded: it ran a `terraform destroy` to bring reality into alignment with the description.

That command didn’t just affect the new site. Because the state file described both sites’ infrastructure, the destroy operation wiped everything: the DataTalks.Club database with two and a half years of student submissions, homework, projects, and leaderboard data, plus the automated backup snapshots that were supposed to be the safety net. Gone in minutes.

Grigorev spent the next day on the phone with Amazon’s support team, paying an emergency premium, trying to recover data that almost didn’t come back. Amazon eventually found a surviving snapshot and restored the system.

His post-mortem, which he published to his Substack with impressive transparency, names the root cause plainly: he over-relied on the AI agent to run Terraform commands. The agent executed exactly what the situation demanded given the information it had. The logic was sound. The supervision wasn’t.

And here’s what makes this story matter for you, even if you’ve never heard of Terraform: Grigorev is a professional engineer. He understood every tool involved. He could read every line of output the agent produced. He still lost everything because he didn’t watch closely enough at the moment it mattered. If an experienced engineer can hit this wall, the builders who can’t read their agent’s output at all are in a fundamentally more exposed position.

The good news is that the skills that would have prevented this are not engineering skills. They’re management skills. And they’re learnable faster than you think.


## You’re not prompting anymore. You’re supervising.

Twelve months ago, building with AI meant chatting. You opened ChatGPT or Claude in a browser, described what you wanted, got code back, pasted it somewhere. You were the hands. The AI was the brain. Every action required your direct involvement.

The tools that replaced that workflow — Claude Code, Cursor, OpenAI’s Codex, GitHub Copilot — operate fundamentally differently. They don’t suggest code for you to place. They read your files, make changes directly, run commands, install dependencies, and iterate on their own mistakes. You give a task and the agent works autonomously for minutes at a time. When you ask it to add a feature that lets customers leave reviews, it doesn’t hand you a code snippet. It reads your database structure, creates new tables, builds the interface, adds form validation, and saves the result. Eight steps, each depending on the last. If step four goes wrong, steps five through eight compound the error.

This shift changes what you need to be good at. The relevant skill is no longer “describe what you want clearly.” It’s “supervise the thing that builds what you want.” And the difference between the vibe coders who keep shipping and the ones who hit the wall tracks almost perfectly with whether they made this mental shift.

I find the best analogy is a construction site. You don’t need to know how to lay brick to manage a construction project. But you do need to know what a straight wall looks like, which walls are load-bearing, and that you don’t tear out plumbing without turning off the water first. The foreman’s value isn’t in their ability to do the trade work. It’s in their judgment about what’s happening, what’s about to go wrong, and when to stop the crew and reassess.

That’s the job now. Five specific skills make it work, and none of them require writing code.


## The time machine you don’t have

Your agent broke something last week and you couldn’t get back to the version that worked. Maybe it was the login page. Maybe it was the checkout flow. You described the problem, the agent tried to fix it, made it worse, and now you’re three hours deep in a conversation that’s going in circles. The version from before the agent touched anything is gone. You have no way to get back to it.

This is the single most common disaster in vibe coding, and it has a solution that every professional developer already uses: version control. The tool is called Git, and the best way I can describe it is as a time machine for your project. Every time you save a snapshot of your working code — called a commit — that version becomes permanent. No matter what your agent does next, no matter how badly it breaks things, you can always reload from the last save point. One command. You’re back to the version that worked.

Without Git, your project exists in one fragile state. With it, you can let your agent try something risky, and if it breaks, undo everything the agent did and return to the version that was working five minutes ago.

The commands fit on a sticky note:

`git status` — see what changed. `git diff` — see the actual changes, line by line. `git add .` then `git commit -m "describe what works"` — save a snapshot. `git push` — back it up to the cloud. `git checkout .` — throw away everything since your last snapshot.

But the habit matters more than any command: commit every time something works. Before asking your agent for the next change, before trying anything risky, before walking away from your computer. If you do nothing else from this article, do this. It would have saved Grigorev’s database. It will save your Saturday.


## Why your agent turns stupid halfway through

You’ve had this experience. The agent is brilliant for the first twenty minutes, understands your project, follows your instructions, makes exactly the right changes. Then somewhere around message thirty, it starts ignoring things you’ve told it three times. It rewrites code it already wrote. It introduces bugs in features that were working five minutes ago. It feels like it forgot everything.

It did.

Every AI agent has what the industry calls a context window, which is a fixed amount of text it can hold in working memory at once. Everything you’ve said, everything it’s said, every file it’s read, every error message it’s encountered — all of it takes up space. When the space fills up, older information gets compressed or dropped entirely. Your instructions from the beginning of the conversation disappear. The file structure the agent understood perfectly an hour ago becomes fuzzy. The agent isn’t getting dumber. It’s running out of room, the same way you lose track of details in a meeting that’s gone on three hours too long.

This is worth understanding at a slightly deeper level because it changes how you work. The context window isn’t like a hard drive that fills up and gives you a warning. It’s more like a whiteboard that someone is quietly erasing from the left side while you keep writing on the right. The agent doesn’t know what it’s lost. It will confidently act on partial information without telling you that the full picture is gone.

Three things fix this. First, start a new conversation for each distinct task. A conversation about fixing the login page should not drift into redesigning the dashboard. Second, when a conversation passes about thirty back-and-forth messages, summarize where you are in a few sentences and start a fresh session with that summary. You’re not losing progress. You’re giving the agent a clean whiteboard and a sharp focus. Third, use screenshots instead of long text descriptions when something looks wrong in your app. A screenshot communicates the same information as three paragraphs of description but occupies a fraction of the agent’s working memory. This is the single most underused technique in vibe coding. Experienced developers working with agents use screenshots for roughly half their communications, not because they’re lazy, but because it’s dramatically more efficient for the AI.

Which brings us to a related problem that’s been driving you crazy.


## The file that makes your agent stop freelancing

You’ve told your agent “use dark mode for the interface” four times and it keeps defaulting to light. You’ve explained your naming conventions and the agent ignores them by the next conversation. Every session starts from zero because your agent has no persistent memory of what you’ve already decided.

Unless you give it one.

Every major AI coding tool supports something called a rules file, which is a simple text document in your project folder that the agent reads at the start of every session. Think of it as the employee handbook for your AI worker. It tells the agent what the product is, how things are done around here, and the specific mistakes it keeps making that it needs to stop making. Claude Code calls this file CLAUDE.md. Cursor has its own format in a .cursor/rules/ directory. There’s a universal standard called AGENTS.md that works across most tools. The name varies by tool; the concept is the same everywhere.

Here’s the part that surprises most people: you don’t write a good rules file by sitting down and thinking carefully about what to include. You grow it from problems. You start with almost nothing — five lines describing what the product is, what it’s built with, maybe the two things your agent keeps getting wrong. Then every time the agent makes a mistake you’ve seen before, you add one line preventing it. Over a few weeks, the file becomes a precise reflection of exactly what your project needs. It’s not a wish list. It’s scar tissue. Every line exists because something went wrong without it.

I think there’s something genuinely interesting about what a rules file becomes over time. It’s not documentation in the traditional sense. It’s closer to institutional memory — the accumulated wisdom of every mistake your project has made, written in language an AI agent can act on. Companies spend fortunes trying to capture institutional knowledge in wikis and onboarding documents that nobody reads. A rules file does the same thing in fifty lines that the agent reads every single time.

One constraint to keep in mind: the rules file competes for the same context window your conversation uses. A 500-line rules file eats into your agent’s ability to focus on the actual task at hand. Keep it under 200 lines. Ideally under a hundred. Concise standing orders, not a manual.


## The skill that prevents 80% of agent disasters

You asked your agent to “redesign the order system” and it touched every file in your project. Half your features broke. You have no idea which changes caused which problems because it changed forty things at once.

This is what happened to Grigorev. One sweeping command that affected an entire infrastructure, with no way to isolate what went wrong or roll back individual pieces.

The concept is blast radius, which just means: how much of your project could a single change potentially affect? Changing a button color has a tiny blast radius — one file, one visual element. Redesigning the order system has an enormous one — dozens of files, database changes, interface changes, and the possibility of breaking features that were working fine before anyone touched them.

AI agents are excellent at small, focused tasks. They degrade on large, sweeping changes, not because the AI lacks capability, but because complex changes compound errors in ways that are genuinely hard to recover from. If step four of a twelve-step change introduces a subtle bug, steps five through twelve build on top of that bug, and by the time you notice something is wrong, the problem is buried under eight layers of subsequent work. Untangling it becomes harder than starting over.

So before giving your agent any task, ask one question: how many things will this touch?

If the answer is one to three files, go ahead. If the answer is four to ten, break it into two or three smaller tasks and do them sequentially, committing between each one. If the answer is more than ten, ask the agent to plan it first: “I want to accomplish X. Give me a sequence of small, safe steps where each step can be tested independently before moving to the next.”

Then follow the rhythm that every successful vibe coder eventually discovers: small task, test the result yourself (click through it, try weird inputs, check it on your phone), commit if it works, then give the next task. If something breaks, you have your last commit to fall back to. You never lose more than one step of work.

One more thing, and this is the one that connects back to Grigorev directly: if your agent has been working for more than five minutes without showing you what it’s done, stop it and check. Agents that run unsupervised for too long tend to over-engineer solutions, go down wrong paths, or make cascading changes that become impossible to untangle. Grigorev let his agent execute a destructive infrastructure command without reviewing the plan first. Interrupting your agent isn’t rude. It’s the entire job.


## What your agent will never warn you about

Everything above is about managing the relationship between you and your agent. This section is different. It’s about the category of problems your agent will never raise on its own, because they require thinking about users your agent has never met and scenarios your agent has no reason to anticipate.

Your app works great when you test it. Three orders, one user, everything loads fast and looks right. But your real customers will submit empty forms, click the buy button five times in two seconds, paste emoji into fields that expect numbers, open your app on a phone screen you never tested on, and hit your database with three thousand records instead of three. The gap between “works for me” and “works for my customers” is where products die quietly, often without the builder ever understanding what happened.

Three things to demand of your agent — in your rules file and in every conversation — that it will not think of unprompted.

**Error handling.** When something fails (a payment doesn’t go through, the database can’t be reached, the internet connection drops), your app needs to show a clear message, not a blank screen or a crash. Tell your agent explicitly: every time the app communicates with a server, it must handle failure with a friendly, human-readable message. The customer should never see a white page with a technical error. Put this in your rules file. Say it again in conversation. It’s the kind of instruction that agents follow once and then silently drop in later sessions, which is exactly why it belongs in the rules file permanently.

**Security.** The moment you hold customer data, you have a responsibility that your agent does not understand the weight of. In late February, security researcher Taimur Khan published findings on a vibe-coded exam and grading platform hosted on Lovable, one of the popular AI building tools. The app’s authentication logic was literally inverted: it blocked logged-in users and granted access to anonymous visitors. Nearly 19,000 user records were exposed, including over 4,500 student accounts from K-12 schools and universities like UC Berkeley and UC Davis. The app had been featured on Lovable’s own showcase page with over 100,000 views. The builder didn’t know the flaw existed because they didn’t know to check for it. The Register reported that the vulnerability was the kind of basic logic inversion a human security reviewer would catch in seconds, but an AI code generator, optimizing for “code that works,” produced and deployed without flagging.

At minimum: tell your agent to set up row-level security so each customer can only see their own data. Never paste your secret keys or API credentials into a conversation with any AI. And add a standing rule to your rules file: never log customer emails or payment information during debugging. These are not advanced engineering practices. They are table stakes for anyone holding other people’s data.

**Scale.** Tell your agent early in the project that your database will eventually hold thousands of records, not three, and ask it to build with that expectation from the start. You don’t need to understand the technical implementation. You need to set the constraint before the agent builds something that works perfectly in testing and collapses under real usage. The difference between a database that handles ten users and one that handles ten thousand is often a few architectural choices made at the beginning. Retrofitting them later is significantly harder than getting them right upfront.


## Know when to stop

Part of being good at this is recognizing where your skills end and someone else’s begin.

Bring in a professional engineer when you’re handling payments beyond a basic checkout button, when you’re storing medical data or anything with legal compliance requirements, or when your app is getting slow under real usage and you don’t understand why. The same applies if your codebase has gotten tangled enough that even the AI agent struggles to make changes without breaking other things.

This is not failure. I want to push back on that framing directly, because I think the vibe coding conversation sometimes treats it as a binary — either you can build the whole thing yourself or you can’t, and if you can’t, the whole exercise was pointless. That framing is wrong. A non-engineer who builds a product, gets real customers, and then brings in an engineer to harden it for scale has done something most startups never manage: they proved the idea works before spending serious money on engineering. They found demand before they found infrastructure. The founders who get this wrong are the ones who hire engineers too early, before proving anyone wants the product, or too late, after the codebase has become more expensive to fix than to rebuild from scratch.

The vibe coding wall is real, but it’s a transition point, not a dead end. The people who navigate it well become something genuinely new: builders who ship real software by directing AI agents with judgment, process, and enough operational discipline to keep the whole thing standing as it grows. That combination — creative vision plus supervisory skill plus knowing when to call for help — has no historical precedent. The closest analogy might be a film director who doesn’t operate the camera but whose judgment determines everything that appears on screen. The vibe coders who figure this out won’t think of themselves as engineers.

They shouldn’t have to. But they’ll build things that work, that last, and that serve real people—which is the only definition of software that has ever actually mattered.

[![](https://substackcdn.com/image/fetch/$s_!v_MG!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd76e8dab-44ba-40d4-a606-571dd68e6311_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!v_MG!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd76e8dab-44ba-40d4-a606-571dd68e6311_1024x1024.png)
