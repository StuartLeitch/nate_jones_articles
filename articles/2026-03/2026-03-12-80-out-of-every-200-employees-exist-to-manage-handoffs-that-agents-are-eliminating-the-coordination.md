---
title: "80 out of every 200 employees exist to manage handoffs that agents are eliminating + the coordination tax audit to find yours"
author: "Nate Jones"
published: 2026-03-12
url: https://natesnewsletter.substack.com/p/pull-up-your-calendar-60-of-it-is
subtitle: "Watch now | Every AI workforce forecast published this year makes the same mistake."
audience: everyone
scraped_at: 2026-03-12 12:00:15
---

Every AI workforce forecast published this year makes the same mistake. They survey roles, decompose them into tasks, assess which tasks AI can perform, and produce a percentage. The methodology is clean. The math is precise. And the answer is dramatically wrong — because it measures AI capability against an organizational structure that is about to stop existing in its current form.

The assumption underneath every one of those studies is that a company is a fixed container — a set of roles performing a set of tasks — and AI is a force that acts on that container, automating some cells and leaving others to humans. But the tasks that exist in a 200-person tech company are not a natural set of things that need to be done. They’re artifacts of human coordination. Most of what knowledge workers do all day is not value creation. It’s coordination overhead: writing specs so that someone who wasn’t in the room can act on a decision, sitting in meetings so that eight people who can’t share a brain can synchronize state, preparing decks so that an executive who doesn’t have time to read the primary source can make a call. When the coordination layer evaporates, the task distribution it produced evaporates with it.

I’ll be honest: the math here is pretty brutal. This piece is the hardest of the three in this series to sit with, because it asks you to look at your own calendar and recognize how much of what feels like “the job” exists only because humans need coordination infrastructure to work together. But it’s also where the good news lives, because the work that remains when you strip that overhead away is the work that was always the most interesting.

**Here’s what’s inside:**

- **The coordination tax.** Why 60-70% of knowledge work hours exist to manage the friction of humans working with other humans, and why we’ve been categorizing that friction as “the role” instead of recognizing it as overhead.
- **When the org moves to code.** Not “learn to code” — what changes when every person in a company gets fingertip-close to the actual product.
- **The double compression.** The compounding loop that makes every workforce forecast you’ve read too conservative by a factor of two or three.
- **Function by function.** What’s already automatable, what’s genuinely hard, and what gets deleted entirely across engineering, product, marketing, sales, and customer success.
- **The real residual.** The work that survives is harder and more valuable than what gets cut, and the two qualities that separate people who catch this wave from people who get caught under it.
- **3 prompts to find your own number.** Audit your actual coordination tax, map what your role looks like when it drops to zero, and build a migration sequence for handing coordination tasks to agents — starting this week.

This is part 2 of 3. [Part 1](https://natesnewsletter.substack.com/p/cursors-coding-agents-solved-a-math) established that multi-agent harnesses are smoothing the jagged frontier by applying organizational structure to AI work. This piece is about what happens when you apply that same insight to the structure of the organizations themselves.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260305_442_promptkit_1)

After running this kit, you’ll have your own coordination tax number — not the 60% average from the article, but the actual split for your specific role, your specific calendar, your specific week. The first prompt walks you through categorizing every hour from last week into coordination (meetings, handoffs, translation artifacts), verifiable execution (the work agents can already do), and the residual (the judgment and vision work that’s actually yours). Most people who run it discover that what they’ve been calling “judgment” is mostly preparation wrapped in a job title. The second prompt takes your residual — whatever’s left after you strip the coordination and the verifiable execution — and helps you figure out what it would look like to spend 30 hours a week on it instead of 12. What would you build? What decisions would you finally have time to think through? What would your role look like if the coordination tax dropped to zero tomorrow? The third prompt is the practical one: it maps which coordination tasks in your week are ready for agent delegation right now, which ones need a verification layer first, and what the handoff looks like for each. You’ll walk away with an actual migration sequence, not a theory. The whole kit runs in about an hour. The first prompt alone will change how you see your next Monday.


## The coordination tax

Pull up your calendar from last week. Not the idealized version of your job — the actual version. Count the hours.

How many hours did you spend in meetings where the primary purpose was transferring information from someone who had it to someone who needed it? Status updates. Cross-functional syncs. Sprint planning. Design reviews. Standups. One-on-ones where you spent twenty minutes giving your manager context they needed for the meeting they had after yours.

Now count the hours you spent creating artifacts whose primary purpose was translating your knowledge into a form someone else could act on. PRDs. Specs. Briefs. Decks. Tickets. Handoff documents. That email you drafted for forty-five minutes because three different stakeholders needed to understand the same decision from three different angles.

Now count the hours doing the thing you were actually hired to do. Writing code. Designing interfaces. Closing deals. Building strategy. Creating something that didn’t exist before.

If your ratio looks anything like the research suggests, you spent roughly 60% on the first two categories and 40% on the third. Microsoft’s 2025 Work Trend Index found that the average employee spends 57% of their time communicating — in meetings, email, and chat — and 43% creating. Asana’s Anatomy of Work study put it at 60% “work about work.” The average knowledge worker now sits through 11.3 hours of meetings per week — nearly a third of the workweek. Microsoft’s data shows that number has tripled since 2020.

Those aren’t productivity failures. They’re organizational physics.

A product manager writes a PRD not because PRDs are inherently valuable, but because the engineer who builds the feature isn’t the person who talked to the customer, and the designer isn’t the person who understands the technical constraints. The PRD is a translation artifact — it exists to transfer context between humans who can’t share a brain. An engineering manager runs sprint planning not because the ceremony creates value, but because eight engineers working on the same codebase need to avoid stepping on each other’s work, understand shifting priorities, and make commitments visible. Sprint planning is state synchronization. A designer creates Figma mockups because the developer needs design intent transferred into a form they can implement against. A data analyst builds dashboards because decision-makers don’t have time to query databases themselves.

None of these artifacts is the product. They’re bridges between humans who can’t share a brain. I call this the coordination tax. In a typical tech company, it accounts for 60 to 70 percent of all labor hours.

We don’t see it because we’ve categorized it as “the job.” A PM’s job is writing PRDs and running standups and aligning stakeholders. An EM’s job is sprint planning and one-on-ones and cross-team dependency management. We don’t experience these activities as overhead. We experience them as the role. But the value is working software that solves a customer problem. A product that ships. Revenue that grows. Everything between “we understand what to build” and “the thing exists and works” is process — and process exists because the execution layer is made of humans.

This is not an insult to the people performing coordination work. The work is real, it’s often difficult, and the people doing it are frequently very good at it. But it exists because of a constraint — the constraint of human bandwidth, human context limits, human communication overhead — not because the work itself is the point. If you could snap your fingers and have everyone share perfect context at all times, with zero latency and zero translation loss, you’d delete most of these roles overnight. Not because the people are unnecessary, but because the problem they solve would simply no longer exist.

Think about what happens when a new engineer joins your team. For two to four weeks, they produce almost nothing — not because they’re incompetent, but because they’re absorbing context. Every decision the team made in the past year, every architectural choice, every workaround, every “we tried that and it didn’t work” lesson lives in people’s heads and in scattered documents. The new hire reconstructs all of it through conversations, old PRDs, commit history, and Slack threads where three people answer the same question differently. An agent harness starting a new task reads the codebase, the progress file, and the git history. Full context in seconds. The onboarding tax doesn’t apply because the coordination problem it solves — transferring institutional context from human brains to a new human brain — doesn’t exist.


## When the org moves to code

In [part 1](https://natesnewsletter.substack.com/p/cursors-coding-agents-solved-a-math), I established that multi-agent coordination harnesses — Cursor’s planner-worker-judge pipeline, Anthropic’s initializer-coder pattern, DeepMind’s generator-verifier-reviser architecture — all converge on the same structural pattern: decompose the work, parallelize execution, verify outputs, iterate toward completion. And the key variable determining what’s in range is verifiability — whether the work can be decomposed into sub-problems where progress is recognizable and dead ends detectable.

Now let’s explore what happens when you apply that insight to the structure of organizations themselves.

When I say “the org moves to code,” I don’t mean everyone needs to become a software engineer. That’s the 2015 version of this conversation, and it was wrong then, too. What’s changed is that code is now readable and writable in natural language. You describe what you want in English. The agent writes the implementation. You review the output by looking at what it does, not by parsing syntax. “The org moves to code” means the artifacts of work become machine-inspectable and testable — which is what makes the coordination layer compressible.

But there’s a deeper point that’s easy to miss, and it’s the thing that makes this transition exciting rather than just efficient. When the translation layers disappear, everyone gets closer to the product. Not closer to a description of the product. Closer to the product itself. The PM isn’t writing a document that an engineer will interpret — they’re shaping the actual artifact, reacting to it, iterating on it in real time. The designer isn’t producing a mockup that approximates the final thing — they’re working on the final thing. The marketing leader isn’t writing a brief for someone else to execute — they’re building the landing page, seeing what it looks like, testing the conversion, all in the same session.

Imagine instead of a world where only 20% of your people — the engineers — touch the actual product, 100% of your people touch the product. How much more could you accomplish if that were true?

That’s not hypothetical for a growing number of people. Here’s what the workflow actually looks like. You sit at a command line and iterate directly on design, specification, and code in the same session. The spec and the implementation converge into the same artifact — there’s no separate “spec phase” and “build phase.” You don’t write a PRD and hand it to an engineer. You don’t sit in a sprint planning meeting. You don’t send a status update because the state of the work is the code, inspectable at any moment. You don’t schedule a design review because you’re iterating on the design and the implementation simultaneously.

This is not theoretical. This is Tuesday. Cursor’s February 2026 update lets developers spin up eight parallel agents on cloud VMs simultaneously — each one working on a separate branch, testing its own changes, delivering video demos of working features, opening pull requests when done. Alexi Robbins, co-head of engineering for asynchronous agents at Cursor, told CNBC that instead of one to three things running concurrently, developers can now have ten or twenty. His counterpart Jonas Nelle put it more directly: the agents aren’t just writing code anymore, they’re “becoming full software developers.” Cursor has demonstrated hundreds of agents pushing to the same branch, generating over a million lines of code across a thousand files in a week. You don’t need a scrum master to coordinate that. You don’t need a standup.

And here’s what I want you to notice. It’s not that the “coding part” got automated. It’s that the translation layers between humans got deleted. No PRD needed because the person with customer insight works directly with the agent. No sprint planning because there aren’t eight engineers who need to coordinate. No status meeting because the state is the commit history. No design-to-engineering handoff because you iterate on the artifact directly. No QA as a separate function because verification is built into the agent loop.

Every one of those was a coordination function. Every one evaporates when the execution substrate shifts from a team of humans to a harness of agents directed by a human with full context.


## The double compression

This is where the analysis goes non-linear, and it’s the most important structural argument I’ll make in this series.

When you remove humans from the execution layer, you don’t just eliminate the coordination roles that existed to manage those humans. You simultaneously make the remaining work more verifiable. And verifiability, as I established in [part 1](https://natesnewsletter.substack.com/p/cursors-coding-agents-solved-a-math), is the variable that determines what agents can handle.

Here’s the loop. When the output of work is code — or something code-like, meaning machine-inspectable and testable — agents can verify it. A marketing campaign becomes a deployed landing page with conversion metrics that an agent can test. A sales proposal becomes a configured offering with win/loss data that an agent can optimize against. Once the artifact is code, you can test it. Once you can test it, agents can iterate on it. Fewer humans means less coordination. Less coordination means more work expressed as code. More code means more verifiability. More verifiability means agents can do more.

This is a compounding loop: fewer humans → less coordination → fewer coordination roles → remaining work more verifiable → agents handle more → fewer humans still. Each turn accelerates the next.

The implication is that the standard forecast model — “AI will automate X% of tasks” — fundamentally miscounts. It treats the current task distribution as fixed and asks which tasks AI can perform. But the distribution is an artifact of the current org structure. When AI changes the structure, the distribution changes with it. Most tasks that exist today are coordination tasks. Coordination tasks exist because the execution layer is human. Change the execution layer and you don’t just automate tasks within the existing org chart. You delete the need for the org chart to look this way at all.


## Function by function

Engineering is the furthest along because code is the most naturally verifiable knowledge work. Feature implementation, bug fixes, test generation, refactoring, code review, documentation — all within range today. Claude Code is at $2.5 billion in annualized revenue. Codex has over 1.6 million weekly active users. But the coordination tax argument matters here more than the automation argument: what gets deleted isn’t just the coding tasks. It’s the entire handoff chain from product spec to technical design to ticket decomposition to sprint planning to implementation to code review to QA. Seven handoffs. Seven opportunities for context loss. Seven coordination roles that vanish when one person directs an agent harness from problem statement to working, tested code.

The same pattern repeats across every function that produces verifiable output. In product management, competitive analysis, market sizing, A/B test design, and funnel analytics are all automatable — and PRD generation itself is following, because an agent harness can iterate a PRD to 80% quality in twenty minutes. That three-day cycle PMs currently endure — writing, circulating, collecting feedback, revising, re-circulating — is almost entirely coordination overhead. In marketing, SEO content, email campaigns, ad copy, landing pages, and attribution analytics are all measurable against engagement, conversion, and revenue, which means a single marketing leader directing an agent harness can produce more tested, optimized content than a team of twelve. Not because the leader is twelve times better, but because the harness eliminates the coordination between strategist, copywriter, designer, analyst, and ops person. What survives in both functions is the same thin layer: zero-to-one product insight on one side, brand positioning that creates genuine emotional resonance on the other. The Jobsian leap. Creative direction that defines the feel of a thing. Rare even among humans.

The coordination layer is already collapsing in customer-facing functions. Salesforce reduced its customer support headcount from 9,000 to roughly 5,000 after AI agents began handling about half of all customer interactions — and that was less than a year after deploying their agentic support product. In sales, lead scoring, prospecting, email sequencing, proposal generation, and pipeline reporting are all verifiable against conversion and revenue data. What survives is reading the room in live negotiation, building genuine trust across a conference table — the judgment layer that sits on top of preparation that agents now handle. The pattern holds everywhere, and it reveals something uncomfortable.


## What looks like judgment

The natural response to all of this is: “Sure, the routine stuff gets automated, but the judgment-heavy work stays human.” Partly right. But I’ve been turning this over for months now, and the thing that keeps surprising me is how much of what we call “judgment” dissolves under scrutiny. We’ve been conflating two very different things: genuine judgment under uncertainty, and coordination overhead that feels like judgment because it’s complex.

Consider “strategic vision.” Most strategic decisions decompose into probabilistic bets with researchable evidence. How big is the market? Calculable. Who are the competitors? Researchable. What capabilities do we need? Auditable. What’s the financial model? Computable. Risk profile? Modelable. It feels non-verifiable because the synthesis of all those inputs traditionally happens inside one person’s brain, in an opaque process we call “judgment.” An agent harness processing all inputs simultaneously does the same synthesis, except the reasoning is inspectable. The verifiability barrier was never the nature of the decision — it was the opacity of the decision process.

Consider “brand positioning.” It feels purely creative and subjective. But we measure brand positioning outcomes — NPS, sentiment, awareness, purchase intent, top-of-funnel conversion rates. It feels non-verifiable because the feedback loops are slow and noisy, quarterly studies confounded by dozens of variables. Make the feedback loops faster and cleaner — which AI can do by testing positioning variants at digital speed against real engagement data — and brand positioning starts looking a lot more like A/B testing and a lot less like pure creative instinct.

Consider “reading the room” in a sales negotiation. How much of the outcome is actually determined by in-the-moment interpersonal perception versus showing up with the right information, the right proposal structure, the right BATNA analysis, the right pricing framework, and the right understanding of the customer’s political dynamics? If agents handle that first 90% of preparation perfectly, the human’s room-reading is applied in a narrower, higher-leverage context.

This is the pattern everywhere I look. What appears to be a single “judgment-heavy” role is almost always a composite of verifiable preparation work and a thin layer of genuine non-verifiable judgment on top. We bundled them together because having one person do both was organizationally efficient. Agent harnesses unbundle them. The preparation becomes automated. The judgment layer remains human. And that judgment layer is much thinner than anyone’s job description suggests.


## The real residual

So what survives? And why is it more valuable, not less?

Product vision. Not the PRD, not the feature spec, not the competitive analysis — agents eat all of that. I mean the upstream conviction about what your product is and who it’s for. The willingness to kill a feature that’s working because it conflicts with where the product needs to go in two years. The instinct that your users’ stated needs and their actual needs have diverged, and the courage to bet on the actual ones.

Brand as thought work. Not the guidelines doc — that’s a spec, and agents execute against it. I mean the deep strategic thinking about what your company means, what emotional territory it occupies. The kind of work that decides Patagonia’s identity isn’t “outdoor apparel” but “environmental activism that happens to sell jackets.” This requires understanding currents that aren’t in any dataset and making commitments that constrain future optionality in ways that create long-term resonance.

Genuine care in customer relationships. Not ticket resolution — that’s automated. I mean the human judgment that says: this customer is telling us one thing but needs another. The decision to give a customer something they didn’t ask for because you know it will rebuild trust. Empathy isn’t a metric, and it isn’t decomposable.

Then there’s engineering architecture — and this one is harder to explain, because it’s the place where the line between verifiable and non-verifiable gets blurriest. Agents can implement architecture. They’re getting better at selecting between known patterns for known problem classes. What they can’t do yet is make the structural bet that says: given where this system needs to be in three years, given the scaling characteristics we’ll face, given the tradeoffs between consistency and availability specific to our domain — this is the right foundation. That’s a commitment that constrains everything downstream, made with incomplete information, where the quality of the decision only becomes apparent years later.

And one category nobody is talking about yet: agentic systems design. Someone has to build, tune, supervise, and evolve the agent harnesses themselves. Defining task decomposition strategies. Designing verification criteria. Choosing which work gets delegated and which gets retained. Debugging failure modes that emerge from the interaction of multiple agents over long time horizons. This is an entirely new discipline — part systems engineering, part organizational design, part quality assurance — and the demand for it will grow in direct proportion to the coordination layer shrinking. Within two years, it will be the most important operational competency in technology.

Notice what all of these have in common. They’re not “soft skills” in the dismissive sense. They’re the hardest skills — the ones requiring the deepest expertise, the most accumulated judgment, the highest-stakes decisions. And they’re the skills that coordination overhead has been starving of time and attention for decades. A typical product leader spends maybe 20% of their week on actual product vision. The rest is meetings, alignment, stakeholder management. A senior engineer spends maybe 15% on genuine architecture thinking. The rest is code review, sprint ceremonies, cross-team dependency negotiation, documentation.

The coordination tax didn’t just waste time. It suppressed the highest-value work that humans do. Removing it doesn’t diminish the role of humans in organizations. It concentrates human effort on the work that was always the most important — the work we were always too busy coordinating to do properly.


## The math

For a typical 200-person tech company, here’s how the decomposition nets out.

Roughly 60 to 70 percent of labor hours are coordination: meetings, translation artifacts, state synchronization, handoff management, information compression, context transfer. That maps to 120 to 140 people whose primary job function is coordination, even if their title says something else. Of the remaining 30 to 40 percent, that’s genuine creation and judgment work, roughly half is verifiable execution that agent harnesses can already perform or will within eighteen months — feature implementation, data analysis, content production, pipeline management, financial modeling, test generation, campaign optimization. That leaves 15 to 20 percent of current labor hours in the genuinely hard residual: zero-to-one insight, political navigation, moral judgment, aesthetic taste at the frontier.

Which means 40 to 60 percent of current headcount — 80 to 120 people out of 200 — exists to perform work that is either already automatable or will be within 18 months. Not because those people are doing easy work. Because they’re doing verifiable work wrapped in organizational overhead that made it look more complex than it structurally is.

This is where I want to be honest about the narratives already circulating. Jack Dorsey recently cut Block from roughly 10,000 employees to around 6,000 and told the stock market that “intelligence tools” had changed what it means to build and run a company. The market sent Block’s stock up more than 20%. The standard reading is that Dorsey proved the coordination-tax thesis in one announcement.

I think that reading is too simple. A significant portion of what Dorsey cut was over-hiring from the COVID era — a correction that was coming regardless of AI. He used the AI automation narrative, said he was going to do more with less, and the market rewarded the framing. That doesn’t mean the structural thesis is wrong. It means Dorsey is a sophisticated storyteller who dressed a workforce correction in the language of the moment.

The real test case isn’t a company cleaning up COVID-era bloat. It’s what happens at a company that *didn’t* over-hire — when leadership looks at the coordination overhead baked into a deliberately lean 200-person organization and realizes that agents have made most of it unnecessary. That company hasn’t made the announcement yet. But it will. And when it does, the numbers will be driven by structure, not by narrative. That’s the version of this story worth watching for.


## What this asks of us

I want to be careful here, because the “40 to 60 percent” number is easy to mourn in the wrong direction.

Yes, some people will be displaced. The transition will create real pain for people whose skills are tightly coupled to coordination functions that are evaporating. I don’t want to minimize that. But I also refuse to pretend that the thing being lost was good for the people doing it.

Nobody went into product management to spend three days writing a PRD that six people will half-read. Nobody went into engineering management to spend their week in sprint ceremonies and cross-team dependency negotiations. Nobody went into marketing to produce the twentieth blog post that exists because the content calendar demands a cadence, not because there’s something worth saying. The coordination tax wasn’t just inefficient. It was dehumanizing in a specific way — it took smart, creative, ambitious people and buried them in synchronization overhead until they forgot what it felt like to do the work that drew them to the field in the first place.

Pull up your calendar again. Look at last week. How many of those meetings did you enjoy? How many made you feel like you were doing your best work? How many did you sit through thinking, “I could have handled this in a five-minute Slack message if three other people had the same context I do”? Is that really the version of knowledge work we want to die on the hill defending?

The post-coordination-tax organization asks more of the people who remain, not less. When you can’t hide behind process, when the coordination overhead that absorbed 60% of your time disappears — what’s left is the hard stuff. Product vision. Strategic thinking. Genuine creativity. Deep technical judgment. The work that most people’s job descriptions claim they do but their calendars prove they don’t.

I’ve watched a lot of people navigate this transition over the past year — people from music, from development, from product, from customer success, from backgrounds that have nothing obvious in common. The two qualities that keep showing up in the people who are thriving are agency and ramp. Agency is the posture that says: this is a skill issue, and I can learn it. Not panic. Not denial. Just a stubborn confidence that the gap between where you are and where you need to be is closeable if you move. Ramp is the ability to learn quickly, to be curiosity-driven, to dive into something unfamiliar and start building competence before you have permission or a roadmap. Those two qualities together — agency and ramp — show up in every single person I know who is jumping into this headfirst and finding the work on the other side more engaging than what they left behind.

The coordination tax was never the good part of knowledge work. It was the part we endured to get to the good part. Removing it doesn’t diminish what humans do. It concentrates us on the work that was always the most important, and demands that we actually be good at it.

That’s the opportunity. And for the people with agency enough to see it and ramp enough to reach it, the work on the other side is more human, not less.

[![](https://substackcdn.com/image/fetch/$s_!CKq9!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F325f899f-5fe8-475e-b5f8-137df2475da1_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!CKq9!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F325f899f-5fe8-475e-b5f8-137df2475da1_1024x1024.png)
