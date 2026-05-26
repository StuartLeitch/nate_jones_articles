---
title: "One person's best AI session vanishes the second they close the tab. Grab the 3 prompts that make it your team's."
author: "Nate Jones"
published: 2026-05-26
url: https://natesnewsletter.substack.com/p/public-ai-work-team-learning
subtitle: "Watch now | The AI work your company cannot see is the AI work your company cannot learn from."
audience: everyone
scraped_at: 2026-05-26 19:16:55
---

5,938 Shopify employees worked alongside the same AI agent in a single month, all of it in public. When those numbers surfaced this spring, everyone fixated on the scale. The scale is not the interesting part.

Almost no other company works this way, and most of them have the opposite problem. Their people are using AI constantly, asking ChatGPT to rewrite emails, using Claude to reason through customer issues, running coding agents against repos, quietly building small workflows that save hours. And almost none of it is visible to anyone else.

A good prompt disappears into one person’s chat history. A clever correction stays inside one employee’s browser tab. The workflow your best operator nailed last month gets rebuilt from scratch by a new hire who never knew it existed. A senior person figures out how to load context, challenge the model, and review what comes back, and the junior across the team never gets to watch how any of that judgment works.

The result: individuals get smarter, the company does not.

That is the missing layer in most AI adoption plans. Companies are buying tools, writing acceptable-use policies, measuring logins, running the occasional training session. None of it touches the actual problem, which is that your best AI work is invisible to everyone who could learn from it. So every quarter, the same lessons get rediscovered from nothing. You are paying tuition on the same lesson over and over, across hundreds of people, and the bill never stops arriving.

Shopify’s answer is not surveillance. It is not scraping everyone’s chat history and calling it knowledge management. It is something smaller and far more useful: a deliberate way to make non-sensitive AI work visible enough that the people around it can actually learn. The agent that produced those numbers runs only in public. That single design choice is the whole game, and any team can copy it.

**Here’s what’s inside:**

- **What Shopify actually built.** Not the AI mandate everyone argued about, but the design choice underneath River, the agent that runs in public and turns one engineer’s judgment into the whole team’s.
- **Why a prompt library will not save you.** The most valuable part of AI work is the part a prompt library cannot hold, and what you have to make visible instead.
- **Where to draw the line.** A workflow-by-workflow boundary for regulated and sensitive work, so you capture the learning without exposing anything that should stay private.
- **The room, the rules, and the one constraint that makes it work.** A setup any team can run in ninety minutes, the metrics that actually signal learning, and the single binding rule that bends a team toward sharing instead of hoarding.
- **How to bring this into your org.** A three-part prompt kit: one that turns a messy AI session into a post your team can learn from, one that draws the line between what’s safe to share and what stays private, and one that helps your senior people model real work in public without it feeling staged.

Private AI work helps the person at the keyboard. Public AI work helps the company learn. That difference is small today and decisive in a year.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260512_837_promptkit_1)

These three prompts exist because the hardest part of public AI work is not deciding to do it. It is the first concrete move. Most teams stall at the same three places. A useful session happens and nobody can turn it into something teachable, so it evaporates. Somebody wants to share but freezes because they cannot tell what is safe to put in a public channel. And the senior people whose judgment is most worth watching have no low-friction way to work in the open without it feeling like a performance. Each prompt clears one of those blocks, and they run clean on first paste in ChatGPT, Claude, or Gemini.


## The Shopify example is not about a memo

This is where the Shopify story gets more interesting than the mandate discourse.

The public argument around Tobi Lütke’s AI memo has mostly been about whether AI should be mandatory, whether companies are using AI as cover for headcount discipline, and whether AI-first management is inspiring or threatening. I have already written about that elsewhere. The memo was a filter. It changed what kind of person would thrive at Shopify and what kind of person would want to work there.

But the fresher lesson is River.

River is Shopify’s internal AI coding agent. A [ZenML case summary](https://www.zenml.io/llmops-database/building-a-public-ai-agent-workspace-for-organizational-learning) of Tobi Lütke’s public post says River works in public Slack channels rather than private one-on-one workspaces. The reported numbers are striking: in one 30-day period, 5,938 Shopify employees engaged with River across 4,450 Slack channels; in one week, River opened 1,870 pull requests in Shopify’s main monorepo, roughly one in eight merged pull requests.

The specific numbers are useful, but they are not the point.

The point is the design choice. Shopify did not only ask, “How can an agent help one employee do work?” It asked, “How can the agent’s work become visible enough that the organization learns?”

A different question entirely.

If a senior engineer works with River in a public channel, other engineers can see how she scopes the task, what context she gives the agent, where the agent gets stuck. They watch the human correct it. They watch what gets accepted and what gets rejected. A new hire can scroll through prior interactions before making their own request. A support engineer can watch a backend engineer construct the right query and reuse the pattern later.

Apprenticeship.

For most of human history, people learned skilled work by being near skilled workers. You watched how the senior person framed the problem, what they noticed, what they ignored. You learned the craft from the process as much as from the finished product.

AI is quietly breaking that model because so much AI work happens in private windows.

The junior employee does not see how the senior person prompts. The new manager never watches the experienced operator verify an answer. The correction that made the workflow reusable stays invisible. Everyone is alone with the model, which means everyone has to rediscover the same lessons.

Call it the apprenticeship gap.

[Anthropic’s published case study on how its own teams use Claude Code](https://www.anthropic.com/news/how-anthropic-teams-use-claude-code) is a softer version of the same lesson, because it makes the work pattern visible instead of celebrating the output alone. The useful part is what the case study names: the workflows. Data teams using Claude Code to navigate pipelines and update documentation, finance teams describing data workflows in plain text, product engineers using it to find the right files in unfamiliar codebases. That kind of public description lets another team copy the habit, not admire the result.

The public-sector analogue is less flashy but useful. The UK Department for Work and Pensions’ [evaluation of its Copilot trial](https://www.gov.uk/government/publications/an-evaluation-of-dwps-microsoft-copilot-365-trial/an-evaluation-of-dwps-microsoft-365-copilot-trial) (published January 2026) covered 3,549 staff and found that peer demonstrations, acceptable-use guidelines, and informal sharing shaped adoption more than formal training. The design differs from River, but the lesson travels outside Big Tech: adoption improves when people can see how competent colleagues actually use the tool, not when the organization buys licenses.


## Why AI prompt libraries are not enough

A prompt library is a start, but not enough.

A prompt library captures the static instruction. It usually misses the work. It misses the messy context that made the prompt useful. It misses the revisions. It misses the judgment. It misses the moment when the model produced something plausible and the human said, “No, that is wrong for our customer,” or “No, that violates our tone,” or “No, that analysis skipped the important constraint.” When people watch me work with a model, what surprises them is [how often I say no](https://natesnewsletter.substack.com/p/your-comprehension-is-worth-more), and how fast. The speed comes from having been wrong before, and none of it is visible to anyone who was not in the room.

The most valuable part of AI work is rarely the prompt. It is the habit around it.

Manufacturing learned this the expensive way. There is a generation of machinists nearing retirement who can feel quality in a piece of steel through their fingertips, and who cannot fully say how. Companies like John Deere have spent real money trying to capture that knowledge before it walks out the door, and the people doing the capturing will tell you how hard it is to get right. You can approximate the felt sense of a master machinist. You cannot transcribe it. This is Polanyi’s paradox, the old observation that we know more than we can tell, and it is why some of the most stubborn bottlenecks in a supply chain still trace back to one person with a skill that lives in their hands. There is one person who knows how to paint the racing stripes on a Rolls Royce. The senior operator’s judgment about when to trust a model and when to override it is the same kind of knowledge. It resists being written down, which is why a static instruction captures so little of it.

Good AI work includes knowing what to ask, what context to load, what standard to apply, what output to distrust, what to verify manually, and when to stop iterating. A clean prompt pasted into Notion does not capture that. It is learned by watching the work unfold.

Public AI work needs to make four parts of the work visible: the task the person was trying to get done, the context they gave the model, the interaction pattern they used to prompt and correct it, and the review standard they applied before trusting the output.

If you only share the final answer, the team learns almost nothing. If you share the process, the team starts to build shared taste.

And shared taste is one of the real bottlenecks in AI adoption.


## This is not surveillance

The obvious objection is privacy, and it is a serious objection.

Most employees should not assume their private AI chats will become public. Companies should not quietly ingest everyone’s ChatGPT history and tell themselves they are building a learning system. That will create fear, not learning. It will push good work further underground. It will also create real legal, security, and HR problems.

The right model is intentional public work, declared and bounded.

Teams should create declared spaces where non-sensitive AI work can happen in the open. A product team might have an AI workbench channel. A sales team might have a sanitized customer-research workflow channel. A finance team might have a read-only analysis-pattern channel. An engineering team might have public agent channels for certain classes of non-sensitive tasks.

The boundary matters. Employees need to know what belongs there and what does not.

A safe public AI work system does not ask people to expose everything. It asks people to share the parts of the work that help others learn and that can be shared without creating risk.

That means the company needs rules.

Customer PII stays private. HR stays private. Legal strategy stays private. Compensation stays private. Sensitive financials stay private. Confidential product plans stay private. Personal coaching and interpersonal conflict stay private. If the learning value can be preserved through a sanitized example, sanitize it.

A regulated team should draw the boundary by workflow, not by enthusiasm. A hospital IT group can share non-PHI workflows such as scheduling cleanup, policy search, radiology operations planning, or claims-process documentation while keeping clinical decision support, patient records, and treatment reasoning fully private. A bank can make reusable research, controls testing, and internal-document workflows visible while keeping customer data, suspicious-activity details, and trading strategy out of the channel. The lesson is not “make regulated work public.” It is “create a safe public surface for the parts of AI work that can teach without exposing protected information.”

The competitive-intelligence objection deserves the same treatment. Public internal channels are not public to the internet. They sit inside the same confidentiality, access-control, and departure-policy regime as code, customer playbooks, internal docs, and product plans. If a workflow is too sensitive to be written down anywhere, keep it private. But ordinary internal AI work is not more leak-risky than any other internal operating practice because it involves a model.

The labor-relations objection is real too, but hiding senior AI work often makes it worse. Visibility can show that AI is not replacing senior judgment; it is changing where that judgment gets applied.

The goal is to make useful work teachable.

The difference between apprenticeship infrastructure and productivity theater lives in that goal.


## What leaders should make public

The most important public AI work should come from senior people.

This is uncomfortable, but necessary.

In most companies, senior people have the most valuable judgment and the least visible process. They write the final memo. They make the decision. They edit the strategy deck. They approve the customer plan. But the actual thinking often happens offstage.

With AI, that offstage thinking becomes even more hidden. A senior leader may use an agent to pressure-test a plan, rewrite a board update, compare scenarios, or identify risks. If that all happens privately, the organization never learns how a strong operator uses AI.

A company that wants to build AI fluency should ask senior people to run some non-sensitive work in public.

Not performative demos. Real work. A leader might ask an agent to critique a launch plan in a team channel. A senior engineer might use an agent to investigate a low-risk bug and narrate the review. A sales leader might show how they turn account notes into a call-prep brief, with customer-sensitive details removed. A product leader might show how they ask AI to find weak assumptions in a roadmap narrative.

People do not copy the exact prompt. They see judgment in action, and that is what they carry forward.

They see how senior people frame ambiguity, how much context is enough, how often the first answer is wrong. They watch good operators push back. They learn that using AI well is active supervision, not passive consumption.

Most AI training misses this.

Training tells people what the tool can do. Public senior workflows show people how capable people actually use it.


## How to set up a public AI channel

A practical system does not need to be complicated.

Start with one declared channel per team. Make the purpose explicit: this is for non-sensitive AI work that others can learn from, including reusable workflows, useful failures, prompt revisions, review examples, and playbooks. It is not a dumping ground for every chat transcript and it is not a surveillance feed.

Then pin three examples from senior people in the first week: one research workflow, one drafting or review workflow, and one failure that produced a better review rule. As patterns repeat, turn them into short playbooks with a use case, inputs, prompt or context pattern, output standard, review step, risk level, owner, and last-updated date. Once a week, spend 30 minutes on what saved time, what failed, and what should travel to another team.

This is where the company starts getting smarter.

The piece that makes this work is a constraint, and it is worth being honest about how binding it feels. At Shopify, you cannot work with River in a direct message. The agent only operates in public channels. Direct messages are the most popular thing in Slack and arguably the worst thing for team learning, because they take the most useful exchanges and seal them off one conversation at a time. Forcing the agent into the open is a deliberate friction. Some people will find it annoying, and that annoyance is doing the work. A constraint that individuals find mildly inconvenient is often the thing that bends a whole team toward shared learning, and the leaders worth watching are the ones auditing their own environment for where a small, intentional constraint would do the same.


## What to measure in public AI work

Do not measure token volume.

Do not rank people by how many prompts they submit.

Do not celebrate the person who produces the most AI sludge.

The useful metrics are about learning and reuse.

How many reusable workflows did the team create? How many were adopted by another person or team? How many examples were pinned because they changed how people work? How often did a public workflow prevent duplicated effort? How many stale examples were retired? How many failures turned into better review rules?

The best signal is not “AI usage is up.”

The best signal is “the same mistake is happening less often.”

Organizational learning looks like that. The same lesson stops getting relearned from scratch in five different corners of the company.

The principle that holds these together is simple: share artifacts, not surveillance. Senior people model the work in declared channels. Customer, employee, legal, financial, and strategic sensitivity stays out. Failures are training material, not blame material. And the metric is reusable workflows and avoided rework, not token volume.

Anything that does not pass those tests does not need to be in the public channel. These rules are intentionally plain because the problem is not complicated in principle. It is complicated in practice because companies keep collapsing three different things into one bucket.

They confuse visibility with surveillance, adoption with learning, and prompt sharing with apprenticeship.

The Monday-morning version is small. Create the channel, write one pinned message that says what belongs there and what stays private, and have the senior person post one real piece of non-sensitive work: the request, the back-and-forth, the correction, the version accepted, and the review note. Pin two more examples in the first week. By month two, mid-level operators should be posting their own. By month four, the channel should be producing reusable playbooks. Total senior-time investment to start the flywheel: about ninety minutes across the first two weeks.

A company does not become AI-native because every employee has a private conversation with a model. That may make some individuals faster. It may even produce meaningful pockets of value. But it does not automatically make the company smarter.

A company becomes smarter when the lessons travel.

What travels goes beyond the prompt. The correction, the review standard, the failure mode, the reusable workflow, and the senior person’s judgment all become visible enough for the next person to learn from them.

That is the real promise of public AI work. Not mandatory usage, not productivity theater, not another dashboard showing how many people opened a chatbot this week.

The practical question for leaders is direct: what AI work inside your company is making one person better, but leaving everyone else behind?

If that work stays private, the company keeps paying the same tuition.

The promise is apprenticeship at scale.

[![](https://substackcdn.com/image/fetch/$s_!X9Ur!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F240553da-409a-4efc-a4fa-3181a5689246_1254x1254.png)](https://substackcdn.com/image/fetch/$s_!X9Ur!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F240553da-409a-4efc-a4fa-3181a5689246_1254x1254.png)
