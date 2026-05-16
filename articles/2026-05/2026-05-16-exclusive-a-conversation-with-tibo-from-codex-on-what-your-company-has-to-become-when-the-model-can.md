---
title: "Exclusive: a conversation with Tibo from Codex on what your company has to become when the model can actually do the work"
author: "Nate Jones"
published: 2026-05-16
url: https://natesnewsletter.substack.com/p/codex-five-leadership-chairs-tibo-interview
subtitle: "Watch now | Between the launch of the new Codex and GPT-5.5 and now, something happened in my own house that has stayed with me more than any benchmark."
audience: everyone
scraped_at: 2026-05-16 12:00:16
---

Between the launch of the new Codex and GPT-5.5 and now, something happened in my own house that has stayed with me more than any benchmark. My wife, who is not an engineer, built and shipped a working full-stack app. She is using GitHub for the first time. That is one anecdote, not a trend, and I am wary of overreading it. But it is the cleanest signal I have for what the April release actually did. The model can now carry the work, and the surface area of who can ship working software has widened far enough that the question of where human judgment lives inside a company stops being a developer question and starts being a leadership one.

I sat down with Tibo, who leads Codex at OpenAI, to ask what changes for companies now that the model can do the work. I’ve written about this a few times since GPT-5.5 and Codex dropped in late April: the bottleneck has moved twice. The first move was from “the model can’t do the work” to “the model can’t do the work the way our team would do the work” — the workflow-packaging problem, which I covered last week. The second move does not land in a workflow file at all. It lands in five different leadership chairs across the company, and each of those chairs has to develop a new instinct that almost nobody is teaching. Our conversation kept circling back to a single organizing point: the model is good now, and the question that matters has shifted to where you put the human judgment around it. What follows is my attempt to write down the takeaways from that conversation and push the framing further than we got to in the room.

I’ve been thinking about what happens to companies that skip this layer. Some will over-restrict to the point that the agents are useless and the team works around them. A smaller number will under-restrict and end up with an incident that turns into a board-level event. The companies that do the quiet work of building the five layers will look unremarkable for two quarters and then will be impossible to catch. Watching who joins that last group is going to be one of the more interesting things to track over the next year.

I’m going to walk through a practitioner template that’s already running this way, the five chairs, and the work each one has to do this quarter. Let’s go.

Late last year — a million years ago in AI timing, fairly recent in calendar time — Addy Osmani, Director of Engineering at Google Cloud AI, published his LLM coding workflow for 2026. It is a quietly important document, because a senior engineer who could write any line of code himself describes how he has restructured his entire workflow around the model now doing the writing. His one-line summary: “Specs, skills, MCPs, small iterative chunks, and always review what the AI suggests.”

What is worth studying is the practical detail underneath that summary. Osmani spends the first part of every task on a robust spec, before any code generation begins. He breaks the work into small iterative chunks rather than asking for monolithic outputs. He keeps standing custom instructions in the repo that capture team conventions. He runs automated quality gates — tests, linters, even AI-on-AI code review — to catch what skim-reading misses. And he is unambiguous about where accountability lives: “No matter how much AI I use, I remain the accountable engineer. In practical terms, that means I only merge or ship code after I’ve understood it.”

Notice where the human judgment goes. The model produces the code, but Osmani applies his own judgment in two specific places, and neither one is runtime line-by-line review. The first placement is at design time, in the spec and the standing instructions that shape what the model writes. The second is at the gate, in the automated checks that flag the parts actually worth his attention. Everything in between, the part that used to consume his week, is handled by the agent operating under instructions that have already absorbed his taste. As he frames the underlying principle: “Treat the LLM as a powerful pair programmer that requires clear direction, context and oversight rather than autonomous judgment.” Twelve years of accumulated taste no longer live only in his head. They live in the spec, the plan, and the standing instructions the agent reads before it runs.

Plugins, skills, and MCP are how you fix the first move: they package the workflow so the agent inherits the standard, and Osmani’s piece is the most legible practitioner-grade example I’ve seen of that move done well. Packaging the workflow does not fix the second move. The workflow file knows what to do. It does not know what your company should be careful about, who decides when something is wrong, what context persists when an employee leaves, or when a human gets pulled back in. Those are leadership questions, not workflow questions, and they live in five different chairs.


## The five chairs

The second move did not land in one place. It landed in five different roles, and each role needs a different new instinct. Most companies have not built any of them. Some have started one, but I have not seen a company yet that has begun all five.

The senior practitioner used to be the human catch in review. She now has to encode the catch upfront, before the agent runs. The engineering manager and platform lead used to permission users by role. They now have to permission actions, scoped per task and audited. The engineering lead and ops leader used to be the second pair of eyes on every meaningful change. They now have to design the second pair of eyes as a system rather than personally being it. The chief of staff and people leader used to manage documentation. They now have to manage context architecture, with portability and curation as first-class concerns. The operator and owner used to run on vigilance. They now have to run on triggers.


## The senior practitioner

The senior engineer on your team has spent twelve years developing taste. She knows when a refactor is over-engineered. She knows when a test is testing the wrong thing or when an interface looks elegant but will hurt you in six months. Most of that knowledge lives in her head. Some of it surfaces in her review comments, but almost none of it lives anywhere a system can read.

That worked when her presence in the workflow was the guarantee. The team’s quality bar was, in practice, the bar she would call out in review, and that was a perfectly serviceable model when there were a handful of pull requests a week. With agents in the workflow, it stops working. The agent will produce roughly ten times the output she can review, which means her judgment shifts from being a catch to being a bottleneck — and the team’s quality bar reverts to whatever the agent does by default, which is usually plausible-looking work that misses everything she would have flagged.

The old instinct was to develop your taste and then apply it through your presence in the review queue. The new instinct is what Osmani is teaching. Your taste is a spec, not a final-line catch, and your judgment has to live in artifacts the agent can read before the agent runs.

It’s tempting to think of this as a prompt-engineering problem. In practice, it is a documentation-of-taste problem, and most senior practitioners have never been asked to do it explicitly. Their taste is a sense, and asking them to write it down feels reductive in roughly the way that asking a chef to write down what they mean by “balanced” feels reductive. It is also the work.

Concretely: the senior reviewer who would catch a race condition in the payment path needs to write down what triggers her suspicion. The reviewer who hates implicit type conversions needs to encode that as a non-functional eval criterion. The reviewer who pushes back on tests that mock too much surface area needs to articulate the threshold. None of this is novel logic. All of it is judgment that previously only lived in her head, and the output is a living constitutional document the agent reads. Not a style guide written for new hires, but a living set of evals, AGENTS.md-style files, and standing instructions that encode what good and what bad look like in concrete terms for this team and this codebase. Done well, the senior practitioner’s review time concentrates on the small fraction the agent flags as borderline, instead of being uniformly distributed across every PR.

If your senior people are still spending most of their week catching things in review, you have not shipped their taste yet. The goal is for their judgment to compound through the agent rather than get re-applied PR by PR.

The leading edge of this is already visible inside OpenAI itself. Jos Visser, a member of technical staff there, wrote in February: “In the year so far, I have not written five lines of code, despite committing many thousands of lines, including entire features and complete rewrites of pieces of code; all done by Codex with minimal oversight.” His role has not disappeared. It has shifted. He spends his time on design docs, plan reviews, and corrective feedback when the agent gets confused. The taste is still his, the execution is the agent’s, and the accountability is exactly where it always was. Most senior practitioners are not yet operating at Visser’s extreme, and most do not need to. The instinct is the same at every point on the spectrum: write down what used to be a feeling, because the agent will read what you wrote.


## The engineering manager and platform lead

Your platform lead spent the last three years building a careful permissioning system for humans. Production access requires a ticket and a review. Read access to customer data needs a security training course. Database write access is gated by role. Then the team starts deploying agents, and the entire permissioning model breaks in a specific way: the agent inherits the permissions of whoever invoked it, which means the agent invoked by a senior engineer can do everything the senior engineer can do. That seems like a reasonable extension of the existing model at first glance. It turns out to be the wrong model.

Human permissioning is built around identity and role, with an implicit assumption that the human will apply judgment at runtime. They will not delete the production table by accident. They will not send the customer email with the staging coupon code. They will not run the migration without checking the rollback. The permission grants the access. The human’s judgment supplies the safety. Agents do not supply that. They do exactly what they were asked to do, often well, sometimes catastrophically.

Identity is the wrong axis. Blast radius is the right one. The old groupings (trusted versus untrusted, admin versus contributor, internal versus external) lived at the identity level. The new question lives at the action level: what is the worst thing this action could do, and is it reversible? Permission gets scoped per task.

Concretely, a reasonable agent permission catalog has tiers. Read-everything access at the bottom is fine because reads are reversible. Write access to staging unlocks per-project with logging. Write access to production payments has a hard sandbox, a second-agent check, and an explicit human approval. Deletion is its own category and almost always escalates regardless of the system. External sends get their own gate, whether the action is an email, an API call to a customer, or a post to a public channel.

The platform lead’s job becomes designing this catalog, which is closer to building a permissions matrix than maintaining an access control list. The matrix has actions on one axis and risk class on the other, and the answer to “can the agent do this” depends on the cell, not on who invoked it. Both major ecosystems expose primitives for this kind of work — OpenAI through Codex’s app and plugin action controls, Anthropic through Claude Code’s permissions system and MCP servers — but the pattern matters more than the surface. The shift is from identity-based access to action-based access.

If your agent can write to anything your most senior engineer can write to, you are permissioning agents like users. The right model is closer to how you would permission a script that runs in production: narrow, specific, audited, revocable. The new instinct is graduated scope per action, not blanket scope per identity.


## The engineering lead and ops leader

Your engineering lead used to be the human in the loop. Every PR landed in his queue. Every release plan ran through his judgment. Every postmortem named him as the second pair of eyes that should have caught it. The model worked because his attention was the bottleneck and the bottleneck was tolerable when there were six PRs a week.

Now there are sixty, and most of them were written by agents. He is still trying to be the second pair of eyes, and he is failing because attention does not scale and the volume now exceeds what he can cover by an order of magnitude. He has two failure modes available. The first is to slow down to the speed at which he can actually review, which kills the throughput the agents created and frustrates the team. The second is to keep up by skimming, which is the failure mode he picks when honest about it.

Tibo named the underlying principle in our conversation more cleanly than I’ve heard it framed anywhere else: “we’re optimizing for outcome per human attention.” Human attention is now the scarce resource, and agent attention is the abundant one. The whole stack — review, permissioning, memory, escalation — is downstream of getting that ratio right. (And yes, I have a proper write-up coming on this topic.)

Maja Trębacz, on OpenAI’s alignment team, named the version of this that lives inside the verification problem in her work on scaling code verification, and the line is direct enough to quote in full: “Human verification is becoming the bottleneck. So we need to make sure that we’re also training powerful models to help humans in verification, and that our verification abilities are scaling as fast as AI capabilities.” That is a sentence with implications most companies have not yet absorbed.

The maker-checker pattern at the human level has stopped working at the volumes agents now produce. The way out is not to find a third human review pattern. It is to recognize that the structurally correct version of maker-checker now lives at the agent level. The reviewer is no longer the engineering lead. The reviewer is an agent whose objective function he wrote, monitored by the team that wrote the function. The old instinct was to be the second pair of eyes. The new instinct is to design the second pair of eyes as a system.

This is the most underdiscussed shift in the entire stack, and OpenAI has shipped the production version of it. Inside OpenAI, every PR is automatically reviewed by a Codex-based reviewer trained for high-signal review. Not just diff inspection but repo-wide reasoning, hypothesis-driven testing, and intent matching against the stated PR description. The published numbers are striking. When the reviewer leaves a comment, the author addresses it with a code change 52.7 percent of the time, which is a remarkable signal-to-noise ratio for any review tool. The reviewer has “protected high-value experiments and caught launch-blocking issues” — work that would not have been visible in the diff alone. Trębacz and her colleagues frame the result as “defense in depth,” explicitly a support tool, not a replacement for careful judgment, with the warning that “teams could start treating a clean review as a guarantee of safety rather than as one layer of defense.” That warning is the part most companies will skip, and it is exactly the part that matters.

Anthropic exposes adjacent primitives in Claude Code through hooks, subagents, MCP, plugins, and permission controls. Hooks can block tool calls at lifecycle boundaries. Subagents can run with separate tools and context. The product surface differs from OpenAI’s, but both ecosystems expose versions of the same broad control problem: instructions, tool access, permissions, review, memory, and workflow packaging. The exact product surfaces differ, and the principle behind any of these primitives is the same: agent execution needs a control system, and the structurally correct version of that control system is another agent with different incentives.

What this looks like for the engineering lead in practice: define what the review agent should catch, then encode those as the review agent’s prompt and evals. The list usually includes drift from the original intent, scope expansion beyond what was asked, missing tests where the change touches a critical path, and irreversible operations without explicit approval. OpenAI’s customization layer for this is called AGENTS.md and lives in the repo. Claude Code uses similar mechanisms with different names. The principle is to write team-specific review standards into a file the review agent reads, rather than hold them in a senior engineer’s head.

Then spot-check the review agent itself, not the worker. Your judgment moves from runtime to design time. You build the checker once, it runs on every PR or every customer-support ticket or every research experiment depending on the workflow, and your attention concentrates on the small fraction the review agent flags. As Trębacz’s team emphasized, that residual attention is not optional. The review agent is a support tool, not a substitute for one.

A review agent adds inference cost and latency. The bet is that the added review layer is cheaper than spreading senior human attention uniformly across every generated change. OpenAI’s verification work argues that with reasonable budgets, verification can run cheaper than generation, which makes the economics favorable when you do it right.

If your “checker” is a human spot-checking on a screen, you have collapsed the maker-checker pattern. The structurally correct version is two agents, deliberately misaligned, with a human resolving the small fraction that requires real judgment. OpenAI is running this in production. Most companies have not started. The new instinct is to design the check rather than to be the check.


## The chief of staff and people leader

Your chief of staff has spent two years building an institutional memory. She knows which Slack channels matter and which are noise. She knows where the strategy decks live. She knows that the Q2 pricing deck has a data error everyone has been told about but nobody has fixed. She knows which decisions were never written down because they were made in a hallway, and she has tracked the consequences of those decisions ever since.

None of that knowledge is reaching the agents, and her knowledge is structurally invisible to the agent stack. The agent reads what it can index. It reads docs. It reads whatever’s in connected systems. It does not read her. When she leaves the company, the artifacts stay. Almost everything else goes with her.

This used to be a knowledge management problem, which is to say a documentation problem, and the accepted answer was to make the docs better, train the team to update Notion, reward the people who write things down. That answer was always partial, and now it is wrong, because the audience has changed. The audience is no longer humans browsing Notion. It is agents reading whatever you point them at, with whatever priority you assign, with whatever structure you give the corpus. The right question is no longer “are the docs current.” The right question is what context persists, who curates it, and what travels when a person leaves.

The old instinct treated knowledge management as documentation: make the artifacts better. The new instinct treats context architecture as workforce infrastructure, distinguishing three layers explicitly — personal, team, and company — and designing how each one persists, who owns it, and what happens at boundaries.

Personal memory is what an individual’s agent has learned about how that person works (preferences, patterns, taste), and it belongs to the person. When they leave, it goes with them, the way personal documents do. HR needs to draft this policy now, before the precedent gets set badly by accident. The first time an employee asks “can I take my agent memory with me when I leave,” the answer should not be improvised on a Tuesday. Tibo put it more directly than I’ve heard anyone at a platform put it: “Memories are not sensitive IP. Can I just take them with me?” When the person running Codex at OpenAI is sketching the right answer in real time, the org policy on the other side of the API call ought to keep up.

Team memory is what an agent has learned about a team’s working context. It belongs to the team as a whole, and it needs a curator, which is a role most companies have not named since the last time they had a librarian. Designate one explicitly. The curator’s job is to keep the team’s context corpus clean, current, and useful, the same way a good ops lead keeps a runbook clean. The curator role is not glamorous, and it is exactly the role that makes everything else compound.

Company memory is the deliberate corpus the agent reads from across the organization. It is the curated subset that an agent should treat as authoritative, distinct from the ambient mass of Slack and Notion and Drive content. The chief of staff’s accumulated knowledge belongs here, deliberately written into the corpus rather than left to be inferred from chat logs.

Tibo was honest about this in our conversation: the question of how personal, team, and company memory should interact is still an open research problem. He’s right at the platform level. At the org level it is also a problem that has to be solved now, not later, because the failure mode is silent. Bad team memory does not crash. It produces mediocre output across thousands of agent runs, and you don’t notice until you compare yourself to a competitor that built the layer well.

A related point Tibo made matters here too. The failure mode he sees most often inside companies deploying Codex is not under-adoption. It is “almost dogmatic, top-down” rollout, where leadership picks the approved use cases and pushes them across the org. What actually works is letting different pockets of the company discover what fits their work, then building forums where the good recipes propagate quickly. That is a curator’s job, not an executive’s. The leadership move is to designate the curator and protect the forum, not to author the recipe book.

If you can name a librarian on your team, you are ahead of most companies. If you cannot, you have a gap that will widen quietly for the next eighteen months. The new instinct is to treat context as infrastructure, not as documentation.


## The operator and owner

Your COO walked through the office last quarter and watched an agent send a customer-facing email that almost shipped without anyone reading it. She caught it because she happened to be looking. She has been looking less since then, and thinking about it less, because every time she asks “should this have a human checking it,” the honest answer is “probably, maybe, depends.” She has ambient anxiety dressed as a process, and ambient anxiety does not scale.

This pattern shows up in every operator I talk to. The early phase of agent deployment runs on the operator’s nervous system. They feel something is off, they look, they catch the bad thing, they intervene, they relax a little, they go back to running the company. After a few months of this, two things happen. They get tired, and the catches start slipping, because the volume of agent activity has by then exceeded what nervous-system vigilance can cover.

The way out is the explicit replacement of vigilance with documented triggers that the system enforces. Triggers do the work the gut used to. Write them down, set thresholds the system enforces, audit them quarterly.

The triggers themselves are not new. A good ops team has always had escalation paths in runbooks. What is new is that most companies have not yet written them down for agents. Four categories cover most of what matters.

Cost triggers come first. Any agent action above a dollar threshold escalates, and the threshold is not the same for every workflow. A research agent burning a hundred dollars on a single deep research run is fine. A customer-support agent issuing a hundred-dollar refund without review is not.

Irreversibility is the second category, and it is the most underrated. Any deletion, any external send, any production change escalates, because reversible actions can be undone if the agent gets it wrong and irreversible actions cannot. The cost of the trigger is low. The cost of skipping it is occasionally enormous.

Confidence is the third. When the agent itself flags low confidence in its own output, escalate. Most agents have some form of self-rated confidence. Most operators ignore it, and the habit of ignoring it is a holdover from the era when models hallucinated constantly. That era is mostly over for frontier models, and when a frontier agent flags itself as uncertain, that signal carries real weight now.

The fourth is drift, which is what review-agent patterns are good at catching: the agent that was asked to refactor and decided to also rewrite the auth layer while it was in there. Drift is where reasonable-looking work shipped against a plan nobody approved. Catch it at the review-agent layer described above, not at the operator’s desk — it is the failure mode review agents are built for.

Each trigger maps to a specific risk class. The point is to write them down, give them numerical thresholds where you can, and stop relying on the operator’s nervous system to be the safety net. The other point is to audit them. Triggers set six months ago for a different model are probably wrong now, and quarterly review of the triggers themselves is part of the discipline, the same way runbook review is part of the SRE discipline.

If you cannot articulate the conditions under which a human gets pulled in, you don’t have escalation. You have ambient anxiety. Every operator I know has experienced that this year. The answer is to write the triggers down, test them against real cases, and update them when they fail. The conditions of intervention have to live somewhere outside the operator’s head.


## What happens when you build all five

Step back. The senior practitioner has shipped her taste. The platform lead has scoped permissions by action. The engineering lead has designed the review-agent pattern. The chief of staff has built context architecture with named curators. The operator runs on documented triggers, audited quarterly.

The company that has done all five looks like a company where humans concentrate on the small set of decisions that actually require human judgment, and agents execute the rest. It looks like a company that compounds. The taste shipped once gets applied a thousand times. The permission catalog gets refined as new failure modes appear. The review-agent objective function gets sharpened with every miss. The team’s context corpus gets cleaner with each curator pass. The triggers tighten or loosen based on real outcomes.

The company that has built none of these has two ways to fail, and neither one is dramatic at first. The dominant failure mode is quiet over-restriction: agents get permissioned so narrowly that the team treats them as toys, the rollout stalls, leadership concludes “agents don’t work for us,” and the company writes off the technology while a competitor compounds. The louder failure mode is the one that gets the postmortem — the under-restricted agent that deleted the production table or sent the wrong customer email at scale, and now legal is involved. Most companies will land in the quiet version. A smaller number will land in the loud one. Both versions hand the long-run advantage to the companies that built the layer.

The mistake the companion piece could leave for this one is the implicit suggestion that workflow packaging is sufficient. Workflow packaging is necessary and not sufficient. You can package the perfect plugin and ship it across your team and still hit every failure mode in this piece, because the plugin does not tell the platform lead how to permission, does not tell the chief of staff how to architect context, and does not tell the operator when to escalate. Those are five different jobs, each one needs a different instinct, and the plugin layer assumes those instincts already exist.

This is also why the question “Codex or Claude Code” is the wrong question to spend most of your strategic thinking on. Both ecosystems expose versions of the same broad control problem: instructions, tool access, permissions, review, memory, and workflow packaging. The exact product surfaces differ, and the platform you pick matters for integration, security review, and team habits. But it does not remove the need to build the five leadership instincts described here, and those instincts determine whether your company benefits from the platform at all.


## The work to do this quarter

If you are a senior practitioner, start writing down what triggers your suspicion in review. Not every rule, just the ones you know you would catch. Those become your eval seed. Osmani’s piece is the cleanest public template I know.

If you are an engineering manager or platform lead, draft the action-by-risk-class permission matrix for one workflow. Not all of them, just one. The exercise will surface the questions you have not asked yet.

If you are an engineering lead or ops leader, design the review-agent prompt for one high-stakes pipeline. Run it as a shadow check on real PRs for two weeks. See what it catches that you don’t. The OpenAI alignment post on scaling code verification is the best public worked example of this pattern in production.

If you are a chief of staff or people leader, name a librarian for one team and draft a one-page memory portability policy for HR to review. Not the final version. The draft that forces the conversation.

If you are an operator, write down four escalation triggers for one workflow — cost, irreversibility, confidence, drift — with numerical thresholds where you can and vibes-based thresholds where you must, with a note to revise.

Each of these is a week of work, not a quarter. The compounding takes longer.

Most companies will deploy agents and skip all five. They will conclude that agents don’t work for them, or they will hit an incident that gets attributed to the agent when the actual cause was the missing layer. The companies that build the layer will look unremarkable for two quarters and then will be impossible to catch.

In my own workflow, Codex now does a large share of the execution. Whether a company benefits from that kind of agentic work depends on whether the people in those five chairs have started. Most haven’t, which is the opportunity worth taking.

[![](https://substackcdn.com/image/fetch/$s_!6t_T!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2b9d57a2-dc48-4532-90e0-385284a0b901_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!6t_T!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2b9d57a2-dc48-4532-90e0-385284a0b901_1024x1024.png)
