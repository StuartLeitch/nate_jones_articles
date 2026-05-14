---
title: "Your team spends 5 hours a week on work a sales consultant automated in an afternoon + the 2 prompts that find your version"
author: "Nate Jones"
published: 2026-04-27
url: https://natesnewsletter.substack.com/p/your-team-spends-5-hours-a-week-on
subtitle: "Watch now | Which of your weekly workflows just became obsolete — plus the two prompts that find out."
audience: everyone
scraped_at: 2026-05-14 14:32:56
---

On April 22nd, OpenAI shipped ChatGPT Workspace Agents. Almost every piece of coverage I’ve read has framed this as a sequel to Custom GPTs. That framing is wrong in a way that will cost people real time. Workspace Agents is not really competing with the chatbot a few people on your team made last year and forgot about. It’s competing with the ops person you almost hired to manage Zapier flows.

A sales consultant at Rippling, no engineering support, built a Workspace Agent that researches accounts, summarizes Gong calls, and posts deal briefs into Slack on every active opportunity. Five to six hours a week per rep, now running in the background on every deal. The build took an afternoon. The detail nobody is putting in the headline is what got displaced: the work that consultant automated used to require either an engineer’s time or a Zapier-and-Gong-and-Salesforce stack somebody had to maintain. None of that is in the loop anymore. The agent just runs.

I’ve spent the past week with enterprise teams I advise, watching them stand up their first builds and comparing the output to what those same workflows produced under Custom GPTs and Projects a month ago. The pattern is consistent and it’s not subtle. Custom GPTs needed a person to carry the prompt. Projects needed a team to carry the context. This one carries itself, at least for the shape of work it handles well. And that’s a category change in what an enterprise can do without writing code or buying a platform.

The free window closes May 6th. After that, OpenAI moves to credit-based pricing they haven’t yet detailed. The reason to actually use the next eleven days is that this is the first agent launch where the answer to “should our team try it” is cheap to find out. The lightweight-automation tools your company has been quietly maintaining — Zapier, Make, Workato, the n8n flows somebody set up two roles ago — are not going away. But the question of whether they should keep growing just got harder to answer without testing this first.

**Here’s what’s inside:**

- **Whether your team’s work fits the shape this product handles.** Five properties that predict which workflows succeed, and the question to ask before you build anything.
- **What I’d build first, by role.** Concrete starting builds for sales, coordination, product, and customer success, with the Rippling pattern any team can copy this week.
- **The governance setting most admins will get wrong.** One toggle hands every user the builder’s credentials. What to lock down before you broaden access.
- **Why this squeezes Zapier, not Claude.** The competitive read most coverage missed, and what the OpenClaw hire tells you about where every major AI platform is heading.

Eleven days to test it for free. Here’s the honest version, plus the two prompts I’m using to decide which workflows belong in this product and which ones don’t.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260423_441_promptkit_1)

The teams that get this product wrong almost always get it wrong the same way. They pick the most interesting workflow, not the most agent-shaped one, and a week later they conclude Workspace Agents is overhyped because the agent they built was never going to work. These two prompts stop that. The first scores any workflow your team is considering against the five criteria that predict whether a Workspace Agent will hold up — repeats on a schedule, recognizable good versus bad, describable in a paragraph, crosses two or more tools, the path is known — and tells you whether to build, switch tools, or resolve the ambiguity that’s actually blocking you. The second writes the build spec at the level of specificity the agent builder needs to scaffold something that runs, not something that demos. Run them in order. Bring a real workflow you’ve watched eat your team’s time. Don’t bring an idea.


## What’s actually in the box

The build experience is the part that changes things. You click “Agents” in the sidebar, describe the workflow in a sentence or two (OpenAI’s documentation uses the example “Create an agent to help with sales meeting prep”), and ChatGPT runs a conversational builder that drafts the agent profile, picks the relevant connected apps, generates a skill matched to the output you want, writes the instructions, and produces a draft you can test in Preview. You can start from a blank prompt or from a template. The shipped templates include Chief of Staff, Data Analysis, and Customer Support, alongside workflow-specific ones like Software Review, Product Feedback Routing, Weekly Metrics Reporting, Sales Lead Qualification, and Supplier Risk Management. For agents you build from scratch, connectors out of the box cover Google Calendar, Google Drive, Gmail, Slack, SharePoint, and a growing list of enterprise apps including Salesforce, Notion, and Atlassian. You can add custom MCP servers for anything else, which opens the door to a lot of enterprise systems. Files, skills, and Memory (a separate feature that gives the agent a persistent folder for notes, drafts, and outputs across sessions) are all available too.

One thing deserves attention because almost nobody is covering it: the skills are built on the open-source agent skills standard, the same standard used by a growing list of other agent frameworks. A skill you build for a Workspace Agent is portable. That is quiet, but it matters if you’re thinking about vendor lock-in. You’re not committing to OpenAI’s format for the next five years. You’re committing to a format you can move.

Deployment is three surfaces. You can run the agent on demand inside ChatGPT. You can deploy it into Slack via the ChatGPT Agents app, where it can join channels, read threads, answer questions, or trigger on schedules. And you can schedule it to run automatically at whatever cadence you want. The Slack piece is the one I underestimated until I used it. The agent participates in conversations where work already happens, not in a separate AI surface your teammates have to remember to visit. That distinction is the difference between a tool your team uses and a tool your team forgets about.

A few environment details worth knowing before you try it. Workspace Agents is not available on ChatGPT Plus. It is off by default for Enterprise workspaces and unavailable to Enterprise customers running Enterprise Key Management. Everywhere it is available, it is free through May 6th, after which a credit-based pricing model kicks in that OpenAI has not yet detailed. If you’re on a Business or Enterprise plan and you’re going to try this, do it before May 6th or plan to budget for the credits.


## What Custom GPTs and Projects were trying to be

That comparison is the one I want to make directly, because a lot of people tired of agent news have quietly also been tired of Custom GPTs and Projects. Workspace Agents is what both of those aspired to be.

A Custom GPT is basically a prompt dressed up in a suit. You write instructions, upload a couple of files, maybe bolt on a few actions, and you ship it. The quality is entirely a function of how good the person who wrote the prompt was at prompting, and the product never escapes the individual-skill ceiling that sets. I tried Custom GPTs for customer service ticket triage more than once inside teams I was advising. It was bad. Not a little bad. The kind of bad where the team stopped using it within two weeks because the marginal lift over a rep reading the ticket themselves was negative once you counted the time spent second-guessing the GPT’s output. The same task, now running as a Workspace Agent, is producing drafts that ticket owners are actually sending. The difference is not a better prompt. The difference is that the agent has Codex underneath, can take action against the ticketing system, can chain steps, and can be governed to the point where admins will actually let it touch real customer data.

Projects were the next attempt, and they were better. File-heavy, context-rich, a shared surface for the team to work inside. I’ve used Projects for incoming RFP response work personally and I’ve watched sales teams try the same. The honest read on Projects is that they still assume a huge human lift. A person has to curate the files, structure the context, shape each session, keep the project’s state coherent, and do most of the thinking-about-thinking the team needs done. The value is real, and it beats a Custom GPT by a mile, but Projects never became autonomous. New RFPs got a Project. The Project still needed an AE to drive it every time.

The same RFP workflow, moved to a Workspace Agent inside a team I advise, runs on every new inbound without the AE touching it. It reads the RFP, pulls the three most similar prior responses from SharePoint, drafts a first pass against the company’s standard playbook, flags the fields it couldn’t answer, and posts the draft into the AE’s Slack DM with a summary of what’s missing. The AE takes twenty minutes of editing instead of three hours of assembling. That is the jump, and it is not a prompt jump. It is a jump from “this tool helps a person do work” to “this tool does the work and a person reviews.”

Across the enterprises I’m watching, the pattern is consistent. The workflows that failed under Custom GPTs — ticket triage, RFP response, inbound lead qualification, recurring report generation — are all workflows that are now running, unattended, inside Workspace Agents, and producing outputs the team is shipping. The teams are seeing nice jumps. Not marketing-deck jumps. Real ones, measured against the prior baseline inside the same company doing the same work.

The prompt-first and file-first approaches are not dead. They still matter for the kind of work each does best. They’re just no longer the default for team-shared recurring work, which is the shift this product makes.


## The pattern that works

The use cases that work share a common shape. The work repeats on a schedule, usually weekly or more often. The output has a clear good and bad because you’ve done the task by hand long enough to recognize both. The steps can be described in a paragraph. And the work crosses at least two or three tools that used to require you to do the coordination yourself. That is the pattern Workspace Agents handles well, and mostly nothing else yet.

The template build I keep pointing people to is the one Rippling shipped publicly. A Sales Opportunity agent built by a single sales consultant, no engineering support, that researches accounts, summarizes Gong calls, and posts deal briefs into the team’s Slack room on every active opportunity. Ankur Bhatt, who leads AI engineering at Rippling, said what used to take reps five to six hours a week now runs automatically on every deal. The shape of that build (done by a non-engineer, shipped to a team, reclaiming a whole workday per person per week) is the one you should be copying this month.

Concretely, here are the four builds I’d prioritize if you’re trying to see the product clearly.

If you’re in a sales role, copy the Rippling pattern directly. An inbound lead qualifier that scores against your ICP rubric and drafts a personalized first touch. A pipeline hygiene agent that flags deals without next steps and nudges the AE. A post-call CRM updater that turns call notes and transcripts into opportunity fields automatically. A competitive intel agent that monitors your target accounts for signals — funding, exec hires, product launches — and surfaces them in Slack with context. The template is right there in the product, the downstream variations are obvious, and the hours-per-rep-per-week math makes it the easiest internal sell of any agent build I know.

If you’re in a coordination-heavy role — chief of staff, exec assistant, ops lead — build a twenty-four-hour overnight feedback synthesizer. It reads the last day of team channels and surfaces emerging themes in the morning brief. The chiefs of staff I know who have built this first have all said the same thing: the weekly hour reclaim has been the biggest single win for them, and they notice it every day. OpenAI’s Chief of Staff template is a decent starting point, but the specific build I’d copy first is the overnight synthesizer, because the output is visible every morning, and because the failure modes are easy to see.

For product and product ops teams, the reference build is OpenAI’s own Product Feedback Router. It monitors Slack channels, support tickets, and public forums, extracts product feedback from the noise, deduplicates, prioritizes by impact and frequency, and publishes a weekly digest with linked tickets. The aggregation-and-synthesis layer is what used to consume half a day a week in the PM role. Getting that back, at reasonable quality, is the fastest legible win you can ship to your team, and it is immediately obvious whether the first draft is good enough.

Customer success and support teams have a different starting point. The highest-value first build is a support ticket router that reads incoming tickets, dedupes against the existing queue, tags by product area, and either drafts a first response or escalates with context. The manual version of this work eats a disproportionate amount of CS time, which is why it keeps coming up in the builder stories on X. Adjacent builds include a weekly customer health digest that pulls usage data, open tickets, and recent CSAT scores into a prioritized risk list, and a sixty-day-out renewal prep agent that builds a retention brief with usage trends and outstanding issues. The common thread is that CS work is already tracked in systems with structured data, and Workspace Agents is unusually good at turning structured data into narrative outputs your team will actually read.

The thread underneath all four is that none of these agents are being asked to make the call. They’re being asked to clear the pile so a human can make the call faster, with better inputs, on the right things. The good agent workflows automate the coordination layer around judgment. They don’t try to automate the judgment itself. That distinction is what separates the builds that survive past week three from the demos that quietly stop running because nobody trusted the output enough to ship it.

Across all four, the thing that ties them together is the same pattern: repeats on a schedule, recognizable good-versus-bad output because you’ve done it by hand, describable in a paragraph, crosses at least two tools. If your weekly work fits that shape, Workspace Agents is probably your right first build. If it doesn’t, keep reading.


## The pattern that doesn’t work

The simplest way to think about where Workspace Agents fits is whether the path is known. If the path is known, the product gets interesting fast. If the path isn’t known, you’re going to spend a week trying to figure out whether the failure came from the model, the workflow, the connectors, the permissions, or the lack of a stable definition of done, and you won’t get a clean answer to any of them.

What Workspace Agents doesn’t handle well, after a week of trying: novel research tasks where the path isn’t pre-specified, long-horizon autonomous work spanning multiple days of compounding context, and anything where the value is in producing a single polished artifact rather than executing a recurring process. For the artifact job, I reach for Kimi or Perplexity. For long-horizon autonomy, something in the Kimi K2.6 agent swarm family or Claude Cowork directly. For novel research, Perplexity is still the better choice. Workspace Agents is an automation and coordination platform first, a reasoning engine second, and the category error you want to avoid is pointing it at work that belongs in a different tool and then concluding the product is disappointing.

Said more plainly: if the work you do is novel, one-off, or judgment-heavy, this is the wrong product. If the work repeats, crosses tools, and you can describe the steps in a paragraph, this is the right product and probably the cheapest one.


## Governance is the real win

The governance story is the reason this will win enterprise seats this quarter. Admins control who can build agents, who can publish them, which connectors are allowed, and what level of approval a sensitive action requires. There’s a Compliance API for centralized monitoring. Agents can be paused centrally if they misbehave. Analytics show how many people are using each agent and how many runs have happened. Version history lets you roll back. All of that is what actually passes enterprise procurement, and most of the prior agent products failed on exactly these axes. When CIOs tell you the reason they haven’t moved is “governance,” this is the feature set they meant, and OpenAI now has it.

One governance note deserves direct attention because the documentation buries it. There is a setting called “publish with personal connections” that lets the person building an agent use their own authenticated app connections. That means anyone running that agent is acting with the builder’s credentials. OpenAI’s own documentation flags this as needing care: other people using the agent may be able to access data or perform actions as the creator. If you’re an admin, understand what you’re turning on before you enable it broadly. The right posture is least privilege: limit the audience, avoid sensitive or high-impact connectors, and audit regularly. The wrong posture is letting your best sales consultant publish their agent with their admin-level Salesforce token attached and not thinking about it again.

Under the hood, Workspace Agents runs on Codex. That matters because it means real action capabilities underneath: code execution, file manipulation, multi-step reasoning. This is not a glorified prompt template or a GPT with connectors bolted on. It is an autonomous execution engine with Codex’s code-running layer underneath, and that is the difference between “drafts an email for you” and “sends the email, confirms receipt, logs the outcome, and moves to the next step.” When you evaluate the product, assume it can actually do things in your systems, and design the review workflow accordingly. “Assume it can actually do things” is not the default posture with most AI products, and it is the correct one here.


## The strategic read

The competitor this launch actually squeezes is not ChatGPT itself and not Claude. The competitive pressure lands on Zapier, Make, Workato, n8n, and a meaningful portion of what teams were using Copilot Studio or Retool for. If your team was about to hire an ops person to manage Zapier flows, you probably now don’t need to. If your team already hired that person, they have a new job, which is building and maintaining Workspace Agents for the rest of the company, and it is a much higher-impact version of the job they signed up for.

One piece most of the coverage is missing. In February, OpenAI hired Peter Steinberger, the creator of OpenClaw, specifically to work on personal agents. Workspace Agents is, partly, the OpenClaw pattern productized with enterprise governance bolted on top. Persistent execution, proactive scheduling, deep tool integration, a skills system, memory, and a shared team surface. The local-first, hacker-ethic OpenClaw still lives as an open-source project under a foundation. But the pattern Steinberger popularized is now the default shape of the commercial product from the company that hired him. That is a bigger tell about where the industry is heading than any individual feature list, and it is worth sitting with for a minute, because the same hiring pattern is going to play out at Anthropic, Google, and Microsoft over the next year. The independent agent-framework builders are being acquired into the enterprise platforms, and the patterns they invented are becoming the defaults.


## What I’d build first

If you’re on a Business or Enterprise seat and you’ve read this far, here is the single move I’d make this week.

Pick one job your team does every week. Five or six hours of somebody’s time, with a recognizable good-versus-bad output, crossing two or three tools. Pattern-match it against the Rippling Sales Opportunity agent even if you’re not in sales.

Describe it in a paragraph. Something like: every Monday morning, read the last week of customer support tickets, group them by product area, deduplicate the repeated issues, flag anything tied to a high-value account, and post a summary with links into the customer success Slack channel. That sentence, that level of specificity, is the bar. If you can’t write it in one paragraph, you’re probably asking the agent to resolve ambiguity your team hasn’t resolved, and no amount of good prompting fixes that.

Open the agent builder. Let ChatGPT draft the scaffolding. Spend an hour tightening the instructions and the connectors. Ship it to the Slack channel where that work already happens. Run it for a week.

At the end of the week, three questions tell you whether you have a real agent or a demo. Did it save time against the old workflow, measured honestly. Did the review burden stay below the time saved, or did you end up spending the reclaimed hour second-guessing the agent’s output. And the one I think matters most: if you turned the agent off tomorrow, would the team miss it. The first two questions are about the math. The third is about whether the agent has actually become part of how the work gets done, which is the only test that predicts whether you’ll still be running it in three months.

The habit that compounds is measuring agent work against real work. The teams I’ve watched get sustained returns from these products are the ones who run that comparison every week for the first month and then quarterly after. The teams who churn off after six weeks are the ones who evaluated by vibes and never circled back. The first draft will get you about sixty percent of the way. You iterate from there.

The bar to try this is an afternoon. The bar to know whether it changes what your team does is a week of running it on real work. That’s a cheap experiment for a question this size, which is the entire reason to run it before May 6th. Whatever you conclude — keep building, kill it, narrow the scope — you’ll know more about where agents fit in your team’s work than you would from another month of reading launch coverage.

[![](https://substackcdn.com/image/fetch/$s_!zWIg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8f63ea3e-0037-46c0-826b-76807436e2a8_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!zWIg!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8f63ea3e-0037-46c0-826b-76807436e2a8_1024x1024.jpeg)
