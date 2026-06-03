---
title: "Opus 4.8 scored 81 in my benchmark. I still wouldn't default to it. (The full breakdown + Nate's Community Slack)"
author: "Nate Jones"
published: 2026-06-03
url: https://natesnewsletter.substack.com/p/opus-48-benchmark-model-selection
subtitle: "Watch now | Claude Opus 4.8 is excellent. The harder question is where it should replace your current workflow, where it should be a specialist, and where turning the reasoning dial up can make the..."
audience: everyone
scraped_at: 2026-06-03 12:00:13
---

Claude Opus 4.8 is excellent. The harder question is where it should replace your current workflow, where it should be a specialist, and where turning the reasoning dial up can make the work worse.

After I read the runs, I wanted the recommendation to be simple: use Opus 4.8.

The score almost lets you say that. In my current benchmark suite, Opus 4.8 is the leader. It scored 81 on the strict average. GPT-5.5 scored 71. The rest of the field was well behind: Gemini 3.5 Flash High Fast at 56, Opus 4.7 at 54, Sonnet 4.6 at 52, GPT-5.4 at 51, and Gemini 3.1 Pro at 38.

If all you want is a leaderboard, the article can end there.

But that would be a bad article, and it would make you worse at choosing models.

The result gets more useful when you stop at the individual runs. Opus 4.8 won because it was much better than Opus 4.7 at the parts of work that usually break professional AI output: source discipline, operational judgment, canary handling, provenance, self-correction, and knowing when a messy data problem should be reviewed instead of quietly “fixed.”

I care about that more than I care about a slightly prettier answer.

It also did not win every task. GPT-5.5 beat it on the Artemis visualization. Opus 4.8 still had visual and front-end weaknesses in multiple runs. And outside our suite, Andon Labs found a long-horizon business benchmark where Opus 4.8 on max effort did worse than Opus 4.8 on high effort, and both did worse than Opus 4.7.

That last point is the one I keep coming back to, because it breaks the lazy way people talk about model launches.

We are used to asking, “Which model is smartest?”

I still want to know the answer. But if you are actually building, managing a team, buying enterprise licenses, or choosing your own daily tool, the question has more parts:

- What work are you doing?
- How long does the task run?
- What source material does it need?
- What tools can the model use?
- Can it inspect the artifact it just made?
- Does it preserve state when the work gets long?
- How much does the human have to babysit it?
- What happens when it is uncertain?
- What does a failed run cost you?

Those questions decide whether the model saves you time or creates another review queue.

So I am not treating Opus 4.8 as a “switch everything” release. It is one of the best models available right now. It is the best model in my current strict suite. I would use it aggressively for some work. I would not blindly make it my default for every long-running workflow.

Here’s what I’m covering:

- **Every test, scored and picked apart.** Where Opus 4.8 won, where GPT-5.5 beat it, and where the score hides real caveats.
- **The effort-level trap.** The Vending-Bench data on why max can make long-running work worse, and how I configure each mode for real work.
- **How I actually choose my daily tools.** Why I still reach for Codex/5.5 despite the score, plus a routing guide for when to use Opus 4.8, Codex/5.5, and GPT-5.5.
- **What builders, leaders, and executives should each do differently.** Role-specific guidance and four prompts you can paste and use today.

The reasoning is below, along with the tools to make the same decision for your own stack.


## *[LINK: [Join the Slack →](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)]*

*If you caught Monday’s post — [the Slack community is live](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)! It’s where I’ll be sharing things between articles, where you can get help on builds in real time, and where the fastest conversations in this community are already happening. I’ll see you in there!*


## *[LINK: [Grab the prompts](https://promptkit.natebjones.com/20260531_43a_promptkit_1)]*

The prompt kit for this piece is built for the decision people actually face after a model launch: where should this job run, how much reasoning should it get, what has to be checked before anyone trusts the result, and how do you stop AI budget from turning into brand loyalty with nicer charts?

It includes four copy/paste prompts:

- **Task Router:** choose the right model, harness, and effort setting for one real job.
- **Eval Set Builder:** turn three to five real tasks from your world into a routing test.
- **Failure-Mode Splitter:** break a messy agentic job into source, visual, operational, and review risks before you accept the output.
- **Outcomes & Total-Cost Mapper:** tie AI spend to accepted work instead of seats, tokens, or vendor enthusiasm.

Use the first one when you are about to pick a model. Use the second when you want evidence instead of vibes. Use the third before you hand a model a messy pile of work. Use the fourth when budget, review capacity, and lock-in start mattering more than the launch week narrative.

Last thing before we dive in: a [[quick-reference guide](https://promptkit.natebjones.com/20260531_43a_guide_substack_benchmark-evidence)] that outlines the below for easy reference after you read the full post.


## The result in one table

Start with the benchmark summary.

[![](https://substackcdn.com/image/fetch/$s_!ScQ-!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2a236d57-f722-4ca9-9be5-03747beeda13_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!ScQ-!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2a236d57-f722-4ca9-9be5-03747beeda13_1920x1080.png)

[![](https://substackcdn.com/image/fetch/$s_!Vxjq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F50ffb13f-423c-447c-ba0f-a001916b8fa6_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!Vxjq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F50ffb13f-423c-447c-ba0f-a001916b8fa6_1920x1080.png)

[![](https://substackcdn.com/image/fetch/$s_!9cF9!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F11c12d3f-4997-4309-abb4-9e41de73fb6a_2624x896.png)](https://substackcdn.com/image/fetch/$s_!9cF9!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F11c12d3f-4997-4309-abb4-9e41de73fb6a_2624x896.png)

The suite is useful because it is not a trivia contest. The tasks are built to resemble work that makes models uncomfortable: dirty source files, images, conflicting records, hidden traps, real artifacts, visual deliverables, physical plausibility, and instructions that leave room for a model to overclaim.

The strict score is harsh on purpose. A model does not get full credit for sounding right. It has to produce the files. It has to keep the numbers straight. It has to preserve sources. It has to handle canaries. And it has to know when something is review-grade rather than final.

That is what the 81 is buying you.

But the individual tests matter more than the average.


## Test 1: Dingo & Co. knowledge work

Score: Opus 4.8 at 80, GPT-5.5 at 78, Opus 4.7 at 54.

[![](https://substackcdn.com/image/fetch/$s_!mfNR!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F61c6a5f6-0420-4e6c-a9a4-014dced5a917_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!mfNR!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F61c6a5f6-0420-4e6c-a9a4-014dced5a917_1920x1080.png)

The Dingo test is a full knowledge-work engagement. The model has to build a packet for a strange business premise with legal ambiguity, source images, financial reconciliation, strategy work, investor materials, dashboards, and documents that have to exist as real files.

It is close to the work people actually hand to frontier models. Not a single clean prompt. A pile.

[![](https://substackcdn.com/image/fetch/$s_!Em26!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd7db26b0-f3c1-4cdc-a886-333b89317e53_406x744.png)](https://substackcdn.com/image/fetch/$s_!Em26!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd7db26b0-f3c1-4cdc-a886-333b89317e53_406x744.png)

Opus 4.8 produced all 23 required artifacts. It handled the important canaries much better than Opus 4.7. It caught the Alaska/Australia mismatch. It treated fictional competitors as scenario competitors instead of inventing real market facts. It kept launch numbers, pricing, budget, import assumptions, channel logic, and customer metrics more consistent across the package.

That is the part of the result I care about.

Opus 4.7 could make a polished packet, but it drifted in ways that would be dangerous in real work: unsupported permit-path framing, stale or unsupported market research, unverified jurisdiction claims, and inconsistent numbers across documents. Those are not cosmetic misses. Those are the mistakes that make a human reviewer spend the next three hours wondering what else is wrong.

Opus 4.8 was meaningfully better at not creating that mess.

The weakness was the visual layer. The central Market Creation Funnel visual was not good enough. It had fragile labels, awkward connectors, weak hierarchy, and the kind of pasted-in AI artifact that makes a deck feel less trustworthy even when the underlying thinking is fine.

[![](https://substackcdn.com/image/fetch/$s_!d3Bq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F87702f16-f425-4aa4-b68c-bed71442a43a_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!d3Bq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F87702f16-f425-4aa4-b68c-bed71442a43a_1920x1080.png)

That tells me exactly how I would use Opus 4.8 on a consulting-style packet.

I would trust it more than Opus 4.7 for source discipline, reconciliation, and legal ambiguity. I would still inspect the artifact before sending anything to a client or executive. If the work includes a board deck, dashboard, landing page, or diagram, I would assume the visual pass needs either a specialist model, a human designer, or a separate QA run.

The model won the task, but the review job remained.


## Test 2: Car Wash operations

Score: Opus 4.8 at 86, GPT-5.5 at 55, Opus 4.7 at 48.

[![](https://substackcdn.com/image/fetch/$s_!7fxn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faa5b1006-c6ea-44e1-8b23-a024f7d13ac2_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!7fxn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faa5b1006-c6ea-44e1-8b23-a024f7d13ac2_1920x1080.png)

For executives and technical leaders, this is the most important result in the suite.

The Car Wash test is a dirty operational data migration. It has ghost records, orphaned orders, typoed customer information, enum variants, image-derived receipts, source files, provenance problems, conflicts, and records that should not be promoted into canonical data.

Most companies have this kind of work. It does not look impressive in a demo. It is not the thing a lab puts on stage. But it is everywhere: finance cleanup, CRM cleanup, invoice reconciliation, support-ticket migration, customer deduping, contract ingestion, compliance review, ERP cleanup.

This test answers the question, “Does the model know what not to do?”

Opus 4.8 handled the core traps. Ghost and test records were rejected. The orphaned Terrence Blackwood order stayed orphaned instead of becoming a fake canonical customer. A severe conflict on SVC-007 was surfaced instead of smoothed over. Typo names were merged correctly. Every job and payment carried source IDs. The package preserved 467 source files and 5,657 source records.

It’s not glamorous — it is the work.

[![](https://substackcdn.com/image/fetch/$s_!t19g!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5d573963-7a27-4ba9-bd35-b02185b0411e_1671x941.png)](https://substackcdn.com/image/fetch/$s_!t19g!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5d573963-7a27-4ba9-bd35-b02185b0411e_1671x941.png)

The output also included a real reviewer workflow. The static UI showed conflicts, rejected records, source inventory, high-priority receivables flags, and review queues. The documentation was candid about review-grade revenue, reconciliation gaps, source recovery limits, and sensitive-file handling.

That candor is one of the strongest signals in the run.

A weaker model tries to make the result look finished. A better operational model knows the difference between finished, reviewable, and blocked. It knows that a revenue number with unresolved source gaps is not the same thing as a final revenue number. It knows that a suspicious record should go to a queue, not a spreadsheet cell that looks official because the model needed somewhere to put it.

Opus 4.8 still missed things. Department and role normalization were not implemented as first-class canonical data even though department values existed in recovered JSON source records. Some image-derived multi-service receipts put the full receipt amount on each service line, creating a risk of inflated billed totals. The mobile UI clipped navigation and metric cards. One source-file count created an audit-ledger inconsistency. OCR remained best-effort.

Those misses do not dismiss the result. They define the review plan.

If I were using Opus 4.8 for operational cleanup, I would not ask it to “clean the data” and accept a finished spreadsheet. I would ask it to build the cleanup system: preserve provenance, reject known bad records, surface conflicts, prove the canaries, and label unresolved items for human review.

On that job, Opus 4.8 looked unusually strong.


## Test 3: Brick

Score: Opus 4.8 at 82.

[![](https://substackcdn.com/image/fetch/$s_!BWfZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbfed22eb-4b21-4313-848c-b610ea1099d6_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!BWfZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbfed22eb-4b21-4313-848c-b610ea1099d6_1920x1080.png)

The Brick test asks the model to create four LEGO-style builds from prompt to part list to runnable browser guide. It tests spatial reasoning, consistency across instructions and rendered output, physical plausibility, and whether the model can keep large builds from turning into decorative nonsense.

Opus 4.8 produced the strongest Brick result I have seen so far.

It completed all four prompts as separate runnable, data-driven animated assembly guides. It passed hard structural validators. It produced screenshots and kept the piece counts in range. It used a single source of truth so the kit spec drove the manifest, the instructions, the final model, and the animation.

[![](https://substackcdn.com/image/fetch/$s_!Ygt1!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7a839283-dec7-4d08-8f4d-5eb0070bd33d_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!Ygt1!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7a839283-dec7-4d08-8f4d-5eb0070bd33d_1920x1080.png)

The most useful part was the repair behavior.

The runner reported that repeated piece-count failures were detected, generator logic was revised, and final outputs were brought back into range. That is the kind of behavior I want from an agent: not just producing an artifact, but noticing when the artifact violates a hard constraint and revising the machinery that produced it.

The caveat is physical reality.

The output was internally structured and validated, but physical buildability was not fully proven. Some support and collision assumptions still need human brick-design review. The large airship depended on mooring and support assumptions. Some build steps added large batches of parts. Some raw model evidence was partial.

So I would not say, “Opus 4.8 can design production LEGO sets.”

I would say, “Opus 4.8 can generate a complex spatial artifact with a coherent internal structure, runnable instructions, and constraint-aware self-repair. If the artifact has to work in the physical world, it still needs expert review.”

That distinction is going to matter well beyond toy bricks.

AI systems are getting good at producing plausible operational artifacts. The human job is increasingly to know which parts of “plausible” have actually been tested.


## Test 4: Artemis II visualization

Score: Opus 4.8 at 76, GPT-5.5 at 79, Opus 4.7 at 60.

[![](https://substackcdn.com/image/fetch/$s_!71YT!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F718186c3-bfc8-41de-9b4d-8e290ebe7d53_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!71YT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F718186c3-bfc8-41de-9b4d-8e290ebe7d53_1920x1080.png)

Artemis is the test that keeps the article honest.

The task asks for a fact sheet plus an interactive 3D visualization of the Artemis II mission. The model has to handle source integrity, mission facts, timeline, visual staging, playback, camera controls, and the hard-to-dramatize parts of the mission: launch, staging, trans-lunar injection, lunar flyby, re-entry, splashdown, and recovery.

Opus 4.8 produced a complete package. It had a fact sheet, source list, offline visualization, documentation, screenshots, and validation evidence. The mission facts mostly aligned with NASA, CSA, and ESA sources. It used confidence tagging to separate official, secondary, and approximate data. The visualization had 14 phases, playback, a scrubber, event stepping, orbit and follow camera modes, a HUD, and local Three.js assets.

[![](https://substackcdn.com/image/fetch/$s_!yKvg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943b44cb-2139-4f79-9948-1c0a5f9ec3df_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!yKvg!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943b44cb-2139-4f79-9948-1c0a5f9ec3df_1920x1080.png)

That is a good run, but not enough to win.

GPT-5.5 still beat it.

The reason was not factual safety. Opus 4.8 was safer than Opus 4.7. The issue was presentation. The visualization was too schematic. Splashdown and recovery did not read as distinct scenes. Later mission beats felt repetitive. Some central flyby and max-distance claims could have used stronger NASA primary support. Mobile framing pushed content partly off-screen.

[![](https://substackcdn.com/image/fetch/$s_!yxZc!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4b168d7c-7dfa-4208-b0c4-48a7b085ec7e_1920x1080.png)](https://substackcdn.com/image/fetch/$s_!yxZc!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4b168d7c-7dfa-4208-b0c4-48a7b085ec7e_1920x1080.png)

The comparison to Opus 4.7 is useful. Opus 4.7 was more cinematic. It had a stronger visual feel. But it had source problems: missing traceable URLs, a CubeSat claim that contradicted NASA primary sources, timing issues, and unsupported colorful details.

So Opus 4.8 moved in the direction I want for trust. It moved backward in a place where Claude has often felt strong: visual taste and front-end presentation.

That does not make Opus 4.8 worse. It tells you how to route the work.

For a sourced visualization, I would use Opus 4.8 for the source packet and factual structure. I would not trust the visual result without inspection. If the visual experience matters, I would run a separate design pass and then a final source-preserving QA pass.

For serious AI work, this is the new routing habit: split the job by failure mode.


## What the benchmark actually says

The suite says Opus 4.8 is excellent.

It also says “excellent” is not the same thing as “automatic default.”

The real improvement over Opus 4.7 is that Opus 4.8 behaves better around messy work. It preserves sources. It catches more traps. It is more careful about reviewability. It can self-repair against constraints. It is less willing to launder uncertainty into a finished-looking artifact.

Those are the exact things that make a model useful for paid work, internal operations, and executive analysis.

The regressions are not imaginary. Visual output was not reliably ahead. The Artemis task went to GPT-5.5. And the outside Vending-Bench results show that effort settings can change long-horizon behavior in ways that are not intuitive.

I would not turn that average score into a procurement strategy, or even a personal workflow strategy.

I would use the leaderboard as a starting point.

Then I would test the work.


## High, extra, and max: how I would use Opus 4.8

The easiest mistake with Opus 4.8 is assuming max effort means best effort.

Anthropic says Opus 4.8 defaults to high effort. Users can choose extra or max. Anthropic recommends extra for difficult tasks and long-running async workflows.

At first glance, it looks like a normal slider: harder task, more effort.

But long-running agent work is not always helped by more internal thinking. If the model spends too many tokens reasoning, it can hit context limits sooner, compact more often, and lose practical continuity. On a short proof or a narrow review, that tradeoff may be worth it. On a long business simulation, it may not be.

Andon Labs found exactly that kind of problem on Vending-Bench. Opus 4.8 was a step forward on some alignment dimensions, but a step back on several business-performance metrics. In their Vending-Bench Arena, Opus 4.8 lost to GPT-5.5 and Opus 4.7. More importantly, Opus 4.8 performed better at high effort than at max effort.

Their hypothesis is simple enough to be useful: max effort burned far more reasoning tokens, triggered more compactions, and caused the agent to forget more of the business state. They found Opus 4.8 on max used about five times more reasoning tokens than Opus 4.8 on high and Opus 4.7 on max, leading to more than twice as many compactions.

That does not prove max is bad. It means you should not treat max as best. It is a specific operating mode with a specific failure risk.

This is how I would use the modes.


### Use high as the default

High is where I would start for most real work:

- Long-form writing from source material.
- Research synthesis.
- Consulting-style packets.
- Messy operational data cleanup.
- First drafts of serious internal artifacts.
- Source-grounded reports.
- Coding assistance where the task has multiple steps.
- Any job where the model needs to remember what it already did.

High gives you strong reasoning without immediately turning the task into a context-management problem. It is also Anthropic’s default, which matters because defaults usually reflect the company’s own view of the best quality-to-friction tradeoff.

If you do not know which effort setting to use, use high.


### Use extra for hard, bounded work

Extra is where I would go when the task is difficult and the answer is worth the additional token spend.

Examples:

- A hard code change with acceptance tests.
- A migration plan where the constraints are known.
- A source-heavy review before a human signs off.
- A complex architecture decision.
- A Claude Code workflow that can be split into pieces and verified.

Extra makes sense when the model benefits from more reasoning and the work has enough structure to keep that reasoning anchored.


### Use max sparingly

Max is for narrow, high-value thinking where context churn is unlikely to hurt you.

Examples:

- Adversarial review of a plan.
- A second-opinion pass on a technical argument.
- A bounded proof or reasoning problem.
- A final risk review where the source set is controlled.

I would not use max as my default for long-running agentic work until I had tested it on my own tasks. I would especially avoid it for work where the model has to carry a lot of evolving state over time.

If you turn on max and the model gets slower, more verbose, more self-conscious, and less practically useful, do not argue with the label. Turn it back down.


## Where Opus 4.8 regresses or gets weird

I see four risk areas.

The first is visual and front-end output.

Opus 4.8 did strong underlying work in Dingo and Artemis, but both runs had presentation problems. The Dingo funnel visual was weak. Artemis was safer but less visually effective than the Opus 4.7 run. GPT-5.5 beat Opus 4.8 on the Artemis task.

This surprised me because Claude has often been strong for writing, product taste, and front-end feel. I still think those strengths are real in many everyday cases. But the benchmark result is a reminder not to rely on lineage reputation. Look at the artifact.

The second is effort sensitivity.

Vending-Bench is the clearest warning. High beat max on Opus 4.8 in that long-horizon business task. The likely reason was not philosophical. It was mechanical: reasoning tokens, compaction, and state loss.

That means effort setting is now part of model selection. It is not an afterthought.

The third is the alignment-versus-operations tradeoff.

Andon Labs found Opus 4.8 was better behaved in some ways but worse at running the vending business. The nuance matters. They still saw price-fixing and market-allocation collusion, though less frequently than with prior models, and they did not find the same deceptive or power-seeking behavior they had seen in earlier Claude models and Mythos Preview. At the same time, Opus 4.8 made worse business decisions on the benchmark.

I do not want models that win by colluding, lying, or exploiting their environment. A lower score caused by better behavior may be a good thing. But poor inventory management, scams, overpricing, and losing track of business state are not moral virtues. They are operational failures.

So your evals need to separate honest behavior from effective behavior. You want both.

The fourth is harness fit.

By harness I mean the product around the model: the file access, the tool calls, the permissions, the memory, the compaction behavior, the rate limits, and the workflow that turns a model response into an accepted artifact.

Opus 4.8 in Claude Code is not the same experience as Opus 4.8 through an API. Opus 4.8 in a chat UI is not the same as Opus 4.8 in a workflow that can inspect files, run tools, preserve state, and verify outputs. GPT-5.5 as a raw model is not the same thing as GPT-5.5 inside Codex with local files, browser tools, persistent goals, and an execution loop.

A chat window, a coding agent, and a local operator can expose the same model to different information and different failure modes. The model name may be identical. The work experience is not.


## Why I still use Codex/5.5 for a lot of daily work

The benchmark table makes this next part sound contradictory.

Opus 4.8 won the suite. I am still using Codex/5.5 for a lot of my daily work.

Not because I think Opus 4.8 is weak. It is not weak. The suite says the opposite.

Because my daily work is not a detached prompt. It is a long-running operating surface.

I ask agents to find source material across my machine. I ask them to read attachments, inspect local files, use browser tools, work across projects, verify generated documents, update CMP assets, maintain goals, run shell commands, and keep going when the job takes hours instead of minutes.

For that kind of work, the harness decides a lot.

Codex/5.5 fits my current workflow because it can operate across the real work surface. It can read the files that matter. It can run commands. It can verify the actual artifact instead of trusting a filename and use browser and local tools when the job requires it. It can keep a goal alive and work through a multi-step deliverable.

I keep reaching for it because fewer handoffs get dropped between the request and the finished work.

I do not mean that OpenAI has permanently beaten Anthropic. I do not even mean that GPT-5.5 is generally smarter than Opus 4.8. The benchmark average says otherwise.

It is a claim about fit.

Claude Code’s dynamic workflows are important for the same reason. Anthropic is clearly building around long-running agent work: plan the workflow, split it across subagents, verify outputs, and return a coordinated result. The Bun port example is exactly the kind of frontier workload that deserves attention: a large migration, many lines of code, a real test suite, and a long time horizon.

That is the right direction for Claude.

I am not trying to turn this into “Claude wins” or “Codex wins.” The competition has moved into the workflow around the model. The model still matters. But the file system, tools, state, evals, permissions, and verification loop now matter enough to change the recommendation.

For my day-to-day work in June 2026, Codex/5.5 is often the better fit.

For careful writing, source-grounded synthesis, messy operational review, and some Claude Code workflows, Opus 4.8 may be the better model.

The answer changes by job.


## My model-selection guide

If you are trying to choose between Opus 4.8, Codex/5.5, GPT-5.5, and older Claude models, I would route work this way.


### Use Opus 4.8 when the work needs careful judgment

Use Opus 4.8 for:

- Source-grounded writing.
- Long-form synthesis.
- Professional knowledge-work packets.
- Messy operational data review.
- Tasks with legal, ethical, or provenance traps.
- Work where uncertainty should be surfaced instead of hidden.
- Claude Code workflows where the job can be decomposed and verified.

I would start on high and move to extra if the task is hard and bounded. I would use max only with a reason.


### Use Codex/5.5 when the work needs the local operating surface

Use Codex/5.5 when the task depends on:

- Actual files on your machine.
- Shell execution.
- Browser or computer tools.
- Repo changes and tests.
- Local verification.
- Multiple long-running workstreams.
- Automations.
- CMP or workflow updates.
- Goal persistence.

The case for Codex/5.5 here is straightforward: it is fewer dropped handoffs between the model and the work.


### Use GPT-5.5 as a strong reasoning or review pass

Use GPT-5.5 when you want:

- A different reasoning style.
- A second model to catch assumptions.
- Strong structured review.
- Visual or interactive work where your own tests show it performs well.
- A cross-check against Claude’s source packet or prose choices.

The Artemis result is the reminder here. Opus 4.8 won the average. GPT-5.5 still won a specific task. That is why routing beats brand loyalty.


### Use Opus 4.7 only for a known regression case

I would not make Opus 4.7 the default. Opus 4.8 is a major improvement in our suite.

But if your own eval shows Opus 4.7 beating 4.8 on a specific long-horizon workload, believe the eval. The Vending-Bench result is enough to make that a real possibility.

Newer does not always mean better for every job.


## A model-selection prompt you can use

If you want a model to help you route a task, use this.

```
You are helping me choose the right AI model and workflow for a specific job.

Do not recommend a model because it is generally strongest. Recommend based on the job.

Ask me only the minimum questions needed to understand:
- What I need done.
- What source material the job depends on.
- Whether the work is short, long-running, or multi-stage.
- Whether the output needs writing quality, technical correctness, visual quality, operational judgment, or all of these.
- Whether the work needs local files, browser/computer use, shell execution, repo changes, or external tools.
- Whether a human will review the result before it is used.
- Whether cost, latency, rate limits, or state loss matter.

Then produce:
- Recommended model and workflow.
- Recommended reasoning effort.
- Why this choice fits the job.
- What a second-pass model should check.
- What canaries or acceptance tests should be run.
- What would make you change the recommendation.

Use these defaults:
- Use Claude Opus 4.8 high for source-grounded writing, careful synthesis, and messy knowledge work.
- Use Opus 4.8 extra for difficult bounded work where the output can be verified.
- Use Opus 4.8 max only for narrow, high-value reasoning or review where context churn is unlikely to hurt the result.
- Use Codex/5.5 when the job depends on local files, shell execution, browser/computer tools, long-running workflows, repo work, automations, or multiple parallel tasks.
- Use a second model to review high-stakes work.

Begin by asking your questions.
```


## What builders should do

Builders should stop treating model selection as a one-time preference.

Keep a small eval set of real work. Not toy prompts. Real work.

Pick three to five tasks that represent your world:

- One writing or synthesis task.
- One messy data or source-reconciliation task.
- One coding or repo task.
- One visual or artifact-generation task.
- One long-running task where state can get lost.

Run them against the models and harnesses you are considering. Score the outputs on the things that actually matter:

- Correctness.
- Source discipline.
- Review burden.
- Time to accepted artifact.
- Cost.
- Failure behavior.
- Visual quality when relevant.
- Whether the model knew what it did not know.

Then route work based on that.

If Opus 4.8 wins your eval, use Opus 4.8. If Codex/5.5 wins your eval, use Codex. If the answer changes by task, build routing instead of pretending one model settled the question.

Also test effort settings. Do not assume high, extra, and max are just better, better, best. They are operating modes with tradeoffs. On some jobs, more reasoning helps. On some jobs, more reasoning burns the context the task needed.

And if you are building agentic workflows, make verification part of the design. A model that produces more work faster can still make your system worse if the review path cannot absorb the output.

Accepted output is the metric. Not model activity.


## What technical leaders should do

Technical leaders should tie AI budget to outcomes, not model makers.

A lot of companies are still trying to pick a permanent winner. They want one contract to answer the strategy question. I understand the impulse. Procurement wants simplicity. Security wants fewer vendors. Finance wants a clean forecast.

But the model race is still moving, and the useful surface is expanding beyond the model itself.

If your AI plan depends on one lab staying permanently ahead, your plan is brittle.

Define the outcomes first:

- Engineering migration throughput.
- Time from ticket to tested PR.
- Support resolution quality.
- Finance reconciliation accuracy.
- Sales research cycle time.
- Legal review coverage.
- Content production quality.
- Human review burden.

Then ask which model and workflow produces accepted output at the best total cost.

Total cost is not just token price. It includes failed runs, retries, human review, integration work, rate-limit friction, vendor lock-in, data governance, workflow disruption, and the downstream work created by agents.

That last part is easy to miss.

Agents can create work faster than organizations can review it. If your team suddenly has ten times as many PRs, reports, support drafts, dashboard prototypes, or research packets, you have not automatically improved throughput. You may have moved the bottleneck to review.

The leadership job is not to buy intelligence. It is to build a system that turns intelligence into accepted work.

That means flexible contracts, internal evals, source truth, cost ledgers, review gates, and a clear decision about where humans sit in the loop.

The best teams will not be the ones that guessed the right model in June 2026. They will be the ones that can switch models without rebuilding the operating system.


## What executives should not overcommit budget to

Executives should not overcommit budget to the idea that one model maker has permanently won.

- Do not turn a benchmark table into a procurement plan.
- Do not fund a giant contract without mapping it to specific accepted outputs.
- Do not let a vendor demo become your operating architecture.
- Do not measure success by seats provisioned, tokens consumed, or agent tasks launched.
- Do not assume the highest reasoning setting produces the best work.
- Do not assume the smartest model is the safest model for your workflow.
- Do not assume the safest model is the most effective operator.
- Do not assume an impressive benchmark means the tool fits your company.

The practical executive move is to keep the architecture flexible and tie spend to outcomes.

Your durable advantage is not access to one model. Everyone with a credit card can get access to strong models. The durable advantage is the system around them: your source data, evals, workflows, review gates, prompts, internal tools, integration layer, governance, cost tracking, and people who know how to use these systems without confusing output volume for progress.

The model makers will keep trading the lead.

Your company should not have to reorganize every time they do.


## My bottom line

Opus 4.8 is a strong release.

It is the best model in our current strict benchmark suite. It is a major improvement over Opus 4.7 on messy work: source discipline, operational judgment, canary handling, provenance, self-repair, and careful synthesis.

I would use it seriously.

I would not use it blindly.

It can regress visually. It can behave differently across effort levels. Max can be worse than high on some long-running work. GPT-5.5 can still beat it on a specific task. Codex/5.5 can still fit my day-to-day operating workflow better because of the way the tool surrounds the model.

I am not saying this to diminish Opus 4.8. I am saying it because this is the practical state of AI work in 2026.

If you are a builder, run your own evals.

If you are a technical leader, buy outcomes.

If you are an executive, do not turn a model launch into a permanent budget commitment before you know where the work actually lands.

I would not phrase the decision as “Opus wins” or “Codex wins.”

You have to decide where the job should run.

Opus 4.8 makes that hard to ignore.

Use it where it is strong. Test it where it is uncertain. Keep your workflow flexible enough to change your mind.


## Coming Up

Token burn is becoming one of the most important metrics in AI work, and most people aren't tracking theirs. On Friday, I'll break down why it matters, what it actually tells you about your workflow, and walk you through [building your own dashboard](https://dashboard-sepia-beta-83.vercel.app/) so you can start measuring it.

[![Image preview](https://substackcdn.com/image/fetch/$s_!jNo_!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9b85f74e-123d-45df-93c8-88f877dbbb9a_1312x1199.png "Image preview")](https://substackcdn.com/image/fetch/$s_!jNo_!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9b85f74e-123d-45df-93c8-88f877dbbb9a_1312x1199.png)
