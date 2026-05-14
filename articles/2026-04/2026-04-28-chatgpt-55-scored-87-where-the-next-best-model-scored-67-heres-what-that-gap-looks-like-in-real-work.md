---
title: "ChatGPT 5.5 scored 87 where the next best model scored 67. Here's what that gap looks like in real work."
author: "Nate Jones"
published: 2026-04-28
url: https://natesnewsletter.substack.com/p/chatgpt-55-scored-87-where-the-next
subtitle: "Listen now | GPT-5.5 Review: The best model in the world, and why that still matters."
audience: everyone
scraped_at: 2026-05-14 14:32:53
---

Using GPT-5.5 for the first time was the most blown-away I have felt about a model release in a while, and the reason is not benchmark scores. The reason is that I handed it the kind of work that breaks models, the kind with messy files and legal risk and 23 deliverables that have to open in the right format, and it came back with something close to a real executive handoff. That has not happened before.

For the last several months, Anthropic felt to me like it held the lead on practical knowledge work. Opus 4.7 was where I went first when the work was real, Sonnet was the workhorse for everything else, and ChatGPT was something I checked in on rather than something I built around. GPT-5.5 changes that. The model is stronger than anything I have used on complex, multi-step work. The harness around it, Codex plus computer use plus Images 2, turns that strength into a system that can actually finish things. I still use Anthropic models every day, and I will get to where Opus remains the right call later in this piece. But the gap on serious execution work is wide enough that I would have to invent reasons not to start here.

This review is also about where GPT-5.5 is not perfect, because the edges matter just as much when the work is going into production.

**Here’s what’s inside:**

- **Three hard tests, not benchmarks.** An executive knowledge-work package, a messy 465-file data migration, and an interactive 3D research build, each designed to fail in a different way.
- **Where GPT-5.5 won by a wide margin.** The Dingo test produced the closest thing to a real executive handoff I have seen from any model, with real files, real legal posture, and real artifacts.
- **Where it still needs help.** The Splash Bros data migration cleared the canary check for the first time, but backend hygiene is still not production-safe, and the Artemis visualization shows that blank-canvas visual taste remains Claude’s territory.
- **How I am actually routing work now.** The defaults that changed, the two-model workflows that did not, and the top 10 takeaways and prompt tips I would hand to anyone using these tools for real work.
- **Five prompts that raise the bar.** Not better questions for the model. Better *work* for the model. A stress-test finder that interviews you until it finds the most ambitious task you can realistically delegate, plus templates for multi-artifact business packages, validated data migrations, structure-first long-form writing, and routing your real weekly work to the right model and surface.

The clearest way to see what changed is through the tests themselves. Start with why the floor moved.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260427_ysh_promptkit_1)

The point of this kit is not to help you ask better questions. It is to help you give AI real work, the kind that used to break models a release ago. The frontier moved, and the way to feel the difference is not benchmarks or side-by-side screenshots. It is handing the model something you have never fully trusted AI to finish and seeing whether it comes back with something close to done.

Start with the Stress Test Finder. It will interview you about your actual work, dig into the projects you have been avoiding because they felt too messy or too fragile to hand off, and write a complete Codex prompt for the most ambitious task it can find. If you do nothing else from this kit, do that. The remaining four prompts are hard-task templates built from the tests in this review: the Multi-Artifact Work Package turns a messy business situation into a real deliverable set with an artifact contract and a verification layer, the Validated Data Migration takes the shoebox of files every small business accumulates and builds a clean database with rejection logic and a human review queue, the Structure-First Draft takes a pile of notes and evidence and produces long-form writing where the argument actually builds instead of listing things, and the Task Router maps your real upcoming work to the right model, tool, and surface based on what each combination is actually good at right now. Every prompt in this kit is designed to fail visibly if you test it on something easy. Give it the hard thing.


## The floor moved

We are living through a strange and remarkable scaling moment, and it is worth taking a moment to step back and notice that. Dario Amodei has used the image of being on a rainbow with no visible end to describe where we are, and OpenAI’s framing around this release lands in the same place: scaling laws are still holding, the gains have not stopped compounding, and the lab is not slowing down. What was impossible a year ago is comfortable now, what was hard last quarter is starting to feel routine, and the shape of the curve still points up. I think that is worth saying out loud, because it is easy to take the underlying progress for granted from inside the daily grind of using these tools.

The release feels like the first major new pre-train OpenAI has shipped in a while, and the difference is something you can feel rather than just measure. The fast modes are sharper than they were a release ago. The thinking modes are dramatically stronger. The model understands the shape of a task sooner, needs less handholding to stay on track, and can take a messier ask and turn it into something closer to a finished result. The launch numbers point in the same direction as the lived experience: 82.7% on Terminal-Bench 2.0, 84.9% on GDPval, 78.7% on OSWorld-Verified, and 98.0% on Tau2-Bench Telecom, with Artificial Analysis placing GPT-5.5 at extra-high reasoning effort at the top of its Intelligence Index by three points while noting that the model uses roughly 40% fewer output tokens than GPT-5.4 over the Index run.

The fact that the floor moved is what makes the release feel different from the recent run of models that leaned hard on inference-time compute. Inference-time tricks are useful when you can afford to wait for the answer, but they do not change much in everyday use. A bigger pre-train is different, because it makes the cheap, fast, default version of the model better at everything. The version of GPT-5.5 you talk to without any special effort is sharper than the equivalent version of GPT-5.4 was, and that kind of upgrade compounds quickly when you use the model dozens of times a day.


## Why the best model still matters

One of the lazier ideas floating around AI right now is that the best model matters less than it used to, because all the frontier models are already good enough. There is a small amount of truth in this argument, but only if the questions you are asking are easy ones. When the task is small, clean, and well defined, a lot of models will feel interchangeable, because most of them can summarize a document, write a decent email, build a basic landing page, or answer a normal coding question without breaking a sweat. The frontier has moved past those places, and so the differences between models on that kind of work are small.

The frontier matters now in the places where the work is ugly, multi-step, under-specified, and consequential. It matters when the model has to infer intent from a sloppy brief, use tools, read files, reconcile contradictions in the source material, make judgment calls with downstream consequences, produce real artifacts in the right formats, check its own work, and keep going long enough to actually finish. That territory is where GPT-5.5 feels different from what came before, and the difference is large enough to change the way I think about delegation.

The old question about a frontier model was whether it could answer a hard question. The question that matters now is whether it can carry the work. Can it carry a long context without losing the thread? Can it carry a deliverable across multiple formats without dropping the constraint that ties them together? Can it carry legal and ethical risk without smoothing over the uncomfortable parts? Can it carry a data migration far enough that the human reviewer is checking the hard cases instead of rebuilding the whole thing from scratch? That is the part of the frontier where the best model still earns its position, and it is the part I tested.


## The release cadence was not accidental

GPT-5.5 did not arrive in isolation, which is one of the more important things to hold in your head while evaluating it. The model landed shortly after the major Codex computer-use update and shortly after Images 2, and the order in which those three pieces shipped looks deliberate rather than coincidental.

Codex computer use gives the model a way to act across the operating system. Background computer use means the agent can drive software without hijacking your cursor, so it can click around, test flows, open pages, and operate the same kinds of interfaces that humans operate. This matters because not every useful system has a clean API or a maintained integration, and a great deal of work still happens inside graphical interfaces that no one has bothered to wrap. A model that can use the GUI directly can reach much more of the world than a model that can only call functions.

Images 2 covers one of the more obvious remaining weaknesses in OpenAI’s stack, which is visual taste and frontend direction. OpenAI’s models have historically been weaker than Claude on blank-canvas visual decisions, and Images 2 narrows that gap by making it cheap and fast to generate a strong visual reference that the implementation model can then follow. Asking a model to invent taste from scratch is a much harder problem than asking it to implement an image faithfully, and the new image model effectively converts the harder problem into the easier one.

GPT-5.5 then arrives as the piece that completes the workflow around those tools. The three components fit together in a way that the OpenAI stack has not really fit together before. Images 2 supplies the visual direction as its own image model, Codex computer use supplies the ability to act on the world, and GPT-5.5 supplies the reasoning, the artifact production, and the judgment about what to do next inside ChatGPT and Codex. People are already using the three pieces in combination: generating a UI mockup with Images 2, handing the image to GPT-5.5 inside Codex, and asking the model to build the working version against that reference. The workflow is meaningfully stronger than asking any single model to handle the whole job from a blank prompt.


## The competitive moment sharpens the picture

The other context worth keeping in mind is the competitive moment in which GPT-5.5 landed. Anthropic announced Opus 4.7 on April 16, OpenAI announced GPT-5.5 on April 23, and the reception of the Anthropic release was more mixed than I expected. Opus 4.7 is genuinely smart, and I still use it; my separate review of that model holds up, and the release fixed real problems that 4.5 had. But measured against the shadow of Mythos, the next-generation Anthropic model that has been hinted at for months, 4.7 felt like a bridge release rather than a phase change. Useful, but not the model that would redefine where Anthropic stands on the frontier.

At the same time, Anthropic has been visibly compute-constrained in ways that show up in normal use. Caps, latency, weird routing decisions, and limited availability have all mattered over the last month, and they affect whether a model is something you can build a daily workflow around or something you reach for on special occasions. When OpenAI shipped GPT-5.5 — and shipped it not just inside ChatGPT but inside Codex — the contrast was sharper than the raw benchmark numbers would suggest, because the OpenAI release came with both a stronger model and a stronger ability to actually serve it.

The point I want to draw from this is broader than a head-to-head comparison. In 2026, the system around the weights matters as much as the weights themselves, and each piece of that system is a place where a lab can win or lose ground that no benchmark will capture. As of right now, the combination of GPT-5.5 plus Codex is the strongest one I have used.


## Why hard tests matter

I designed three tests, each of which probes a different part of what a model has to do in real work and each of which fails in a different way when the model is not strong enough. Running all three together gives a more honest picture than any single eval can produce, because each test alone would push the review in the wrong direction.

The first test was the Dingo & Co. evaluation, which is a full executive knowledge-work test. The model has to take a fictional company, a messy set of source materials, real legal and ethical risk, product imagery, financial data, customer notes, and market research, and turn the pile into a 23-deliverable executive work package: Word documents, a PowerPoint deck, spreadsheets with formulas and charts, a PDF one-pager, an interactive dashboard, a press release, a Slack announcement, a team FAQ, a board update, an investor FAQ, customer personas, an email sequence, a risk assessment, a go-to-market plan, and several more pieces. The point of the test is that production discipline matters as much as judgment, because real executive work always lives inside files that other people have to open, edit, and send.

The second test was the Splash Bros “shoebox” evaluation, which is a dirty data migration. The setup is 465 files from a fictional mobile detailing business: CSV exports, Excel sheets in three different schemas, JSON backups (one of them deliberately corrupted), scanned PDFs of handwritten receipts, VCF contact cards, text notes, and a pile of stray junk that any real small business would accumulate over years of inconsistent operations. The model has to inventory the files, design a database, extract the records, resolve duplicate customers, reject fake records, normalize services, reconcile prices, surface conflicts, write a migration report, and build a review UI for a human to approve the canonical merges. The eval has planted traps, some of which are obvious to a human reader and some of which are not, and the test is designed to probe whether the model has the careful, somewhat boring instincts that production data work actually requires.

The third test was the Artemis II evaluation, which is an interactive 3D visualization challenge. The model has to research NASA’s Artemis II mission, build the SLS vehicle, animate the launch through lunar flyby and return, create the environment, add controls, support timeline scrubbing, make components clickable, and make the whole thing informative enough to be educational. No facts are provided, no tech stack is specified, and the prompt essentially asks the model to research the mission, build the artifact, and make it stunning. The test bundles together a different set of capabilities — research accuracy, 3D programming, interaction design, and visual taste — and it surfaces failure modes that the other two tests do not.

These three tests matter together because they probe different parts of the model, and each one alone would mislead you. Dingo on its own would make GPT-5.5 look like a runaway winner, while Splash Bros on its own would make you cautious about trusting the model with anything important, and Artemis on its own would make you think Opus is still ahead because the visuals are better. When you look across all three at once, you get a more accurate picture of what kind of model GPT-5.5 actually is, and the picture is more interesting than any single number on a leaderboard.


## The Dingo test: real work, not a demo

The Dingo & Co. test needs a careful setup, because if you do not understand the premise, the result just sounds like another score on another benchmark.

Dingo & Co. is a fictional Anchorage pet-tech startup that sells an automated litter box for dingoes and dingo-hybrid pets. The product is called DingoBox Pro, and the company has a related subsidiary called Northern Canid Imports that helps create some of the market by importing the animals themselves. The premise is intentionally absurd, and the absurdity is doing real work in the eval, because it forces the model to engage with the problem rather than fall back on a generic product-launch template.

A model cannot simply treat the brief as a normal product launch. It has to recognize that selling a waste-management product for dingo-hybrid households is commercially interesting, legally sensitive, ethically fraught, and operationally narrow all at once. It has to understand that a product company and an import funnel are not the same business, and it has to keep them separate in the work product. It has to distinguish existing qualified owners from future imported-animal demand when it sizes the market. It has to avoid the easy mistake of implying that the product makes exotic ownership legal, simple, or suitable. It has to use the product imagery it was given rather than inventing new visuals that contradict the source material. And it has to do all of this while producing real files in real formats that hold up when a human opens them.

The required package is 23 deliverables, which I listed earlier and will not repeat in full. The shape of the assignment is what matters: the test asks the model not to write a paragraph about the launch, but to assemble the entire packet that a real launch would need.

GPT-5.5 won this test by a wide margin. The scores were 87.3 for GPT-5.5, 67.0 for Opus 4.7, 65.0 for Sonnet 4.7, and 49.8 for Gemini 3.1 Pro, and the score was not a vibe check — the package was validated against the artifact contract. GPT-5.5 produced all 23 required deliverables in real artifact types rather than HTML or markdown wearing the wrong extensions. The deck contained 17 slides with 26 media files, ten of which were exact matches to the provided source images. The spreadsheets had real formulas and real charts. The dashboard worked and used the supplied logo and product hero image.

[![](https://substackcdn.com/image/fetch/$s_!rKQT!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4a3b701-865a-4472-8fbe-dc9ba6e8cf24_1265x950.png)](https://substackcdn.com/image/fetch/$s_!rKQT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4a3b701-865a-4472-8fbe-dc9ba6e8cf24_1265x950.png)

The GPT-5.5 Dingo & Co. dashboard: real product imagery, interactive filters, revenue data, and channel mix. Built from source files, not invented.

[![](https://substackcdn.com/image/fetch/$s_!tIPn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb71b8686-a184-4abe-8eba-5f92aef547d5_1275x1650.png)](https://substackcdn.com/image/fetch/$s_!tIPn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb71b8686-a184-4abe-8eba-5f92aef547d5_1275x1650.png)

The sales one-pager is a real two-page PDF and visibly uses source product imagery — embedded product photo, specs, pricing ($899 MSRP / $799 early-bird), and a “Serious, not reckless” framing that avoids implying exotic ownership is simple or legal.

The research file contained 34 URLs with strong official-source coverage on the legal and regulatory claims, which is the part of the assignment that actually carries risk.

That last piece matters because the legal trap is the whole test. Opus 4.7 produced polished artifacts, but its legal and regulatory posture was much shakier than GPT-5.5’s. It implied an Alaska permit path that the sampled official guidance did not actually support, and it took unsupported or contradicted positions in several other jurisdictions. It also drifted on important numbers, including whether Northern Canid Imports had completed seven imports or sixteen, and whether the first release gate sat at $240K or $185K.

Opus 4.7’s Dingo dashboard: polished with 6 chart panels, revenue trends, and an import funnel. The visual quality is strong, but the underlying legal and number claims did not hold up under verification.

[![](https://substackcdn.com/image/fetch/$s_!JOul!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9e68861b-c549-4869-842c-7ce09c8a04fa_1440x2411.png)](https://substackcdn.com/image/fetch/$s_!JOul!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9e68861b-c549-4869-842c-7ce09c8a04fa_1440x2411.png)

Opus 4.7’s Dingo dashboard: polished with 6 chart panels, revenue trends, and an import funnel.

Sonnet 4.7 had useful strategic instincts but underproduced on the artifact layer. The deck contained zero embedded media files, the sales one-pager referenced images instead of embedding them, the dashboard did not use the product image, and the source file had only a single URL. None of that is sufficient for a regulatory and market work package, regardless of how good the underlying strategy was.

[![](https://substackcdn.com/image/fetch/$s_!QsIH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb4e58e7b-8337-4642-9238-74e952709eab_2400x1800.png)](https://substackcdn.com/image/fetch/$s_!QsIH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb4e58e7b-8337-4642-9238-74e952709eab_2400x1800.png)

Sonnet 4.7’s 16-slide board deck: all text, zero embedded images. The strategic thinking was useful, but the artifact layer was underproduced for a board presentation.

Gemini 3.1 Pro understood parts of the premise, but the artifact layer collapsed entirely. Several of the required Word, PowerPoint, Excel, and PDF files turned out to be HTML or text files wearing the right extensions, which is an immediate failure for an executive work package. You cannot send a fake PowerPoint to a board and call it a deck.

[![](https://substackcdn.com/image/fetch/$s_!M1BZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fee37e743-ddf5-42cf-bf9d-fbb2f4678e89_1185x8590.png)](https://substackcdn.com/image/fetch/$s_!M1BZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fee37e743-ddf5-42cf-bf9d-fbb2f4678e89_1185x8590.png)

Gemini 3.1 Pro’s board deck: text-heavy slides with no embedded media, and several required Office/PDF files were actually HTML wearing the wrong extensions.

The strongest part of the GPT-5.5 run was not that it finished, but that it understood the shape of the problem before it started producing artifacts. Rather than treating dingoes as a fun pet segment, it framed the launch as a narrow qualified-household release with legal, ethical, import, and market-size constraints, and it kept that framing consistent across the entire package. It recommended a staged launch instead of a broad novelty campaign. It treated Northern Canid Imports as a central source of risk rather than as background color. It separated curiosity traffic from real buyers in the marketing plan. It repeatedly stated, in the right places, that the product does not make exotic ownership legal, simple, or suitable. That is the kind of judgment I want from a model that is going to do executive-level work.

The failures GPT-5.5 did make were real, but they were almost all final-mile production issues rather than failures to understand the assignment. The PowerPoint had invalid XML metadata because the ampersand in “Dingo & Co.” was not escaped correctly, which broke macOS Quick Look. One slide stated that the average NPS was 6.6 when the source average was 6.15 — rounded to 6.2, which is the number the dashboard and executive summary actually used. Some of the pricing claims were stale or imprecise. The workbooks were valid and useful but not as polished as a serious analyst-built model would be. I would fix all of those issues before sharing the package externally, but they are repairable production defects rather than fundamental failures of comprehension.

The distinction between final-mile defects and conceptual failures is what makes the Dingo result important. In real work, the painful part is usually not the last 10% of polish, but the move from nothing to a coherent first version that has the right structure, the right evidence, the right files, and the right posture. GPT-5.5 is unusually good at compressing that part of the work, which means the test does not just produce a high score — it shows the model crossing a threshold in knowledge work where it can take a strange business situation, a pile of evidence, a set of assets, and a long artifact contract, and produce something that feels close to a real executive handoff.

[![](https://substackcdn.com/image/fetch/$s_!pp_C!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbe5528a8-518f-4701-8031-9136454deb91_750x660.png)](https://substackcdn.com/image/fetch/$s_!pp_C!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbe5528a8-518f-4701-8031-9136454deb91_750x660.png)

Four pages of the GPT-5.5 executive summary: recommendation, business situation, risk posture, launch timeline, and board decisions. Structured as a real briefing document, not a wall of text.


## Splash Bros: canary passed, humans still needed

The setup is a fictional mobile detailing business with 465 files, and the folder is designed to look like the kind of mess a real small business might hand you after years of inconsistent operations. The pile contains CSVs and Excel files in three different schemas, PDFs of invoices, JSON backups (one of them deliberately corrupted), text notes, VCF contact cards, scanned images of handwritten receipts and schedules, service lists with conflicting names, and stray junk files that should not survive the migration. The hard part of the test is not any single record but the shape of the whole pile, which forces the model to make judgment calls at almost every stage.

The job is to migrate everything into a clean database, which means the model has to inventory every file, decide what matters, parse multiple formats, design a schema, extract records, merge duplicate customers, reject fake records, normalize services, reconcile prices, detect conflicts, preserve source provenance, write a migration report, and build a review UI that surfaces the conflicts to a human reviewer. The test has planted obstacles, and they range from the obvious to the subtle.

Among the obstacles, the obvious ones include three fake customers (Mickey Mouse, Test Customer, and Asdf Asdf), a fake $25,000 payment, several duplicate customer records with conflicting contact details, name typos in orders, service-name variants, a corrupted JSON backup, inconsistent date formats, raw status values like “paid,” “PAID,” “Done,” “completed,” “no show,” and “Cancelled - rain,” and payment methods scattered across “Square,” “square,” “Cash,” “cash,” “CASH,” “credit,” and “credit card.” The less obvious obstacles include an orphaned order attached to a customer named Terrence Blackwood, a service-code conflict around SVC-007, and handwritten receipt images that could easily produce false canonical customers if the OCR step is not handled carefully. The work sounds boring until you remember how much of the economy runs on exactly this kind of mess.

In the prior run of this evaluation, both Opus 4.7 and GPT-5.4 failed the canary check. Mickey Mouse became a canonical customer in their migrations, as did Test Customer and Asdf Asdf, and the fake $25,000 payment got normalized and counted as real revenue. These are the kind of mistakes a human reviewer catches in two seconds, and the fact that previous frontier models missed them was the most uncomfortable result of the original eval.

GPT-5.5 cleared the canary check, which is the cleanest single result in the evaluation. It rejected Mickey Mouse, Test Customer, Asdf Asdf, ORD-1001, ORD-1002, and the fake $25,000 payment. It correctly merged all seven planted duplicate customer pairs. It caught all 13 name-typo orders. It discovered all 465 source files. It produced a deterministic rebuild of the database. It generated a 7,287-line migration report with a per-file audit trail. It landed at 186 customers against a target of roughly 192, and the count was close for the right reasons rather than coincidentally close while the underlying records were a mess. None of the previous models in this eval combined those properties.

The progress is meaningful, because the prior version of this evaluation ended with a sobering conclusion: none of the frontier models were safe to trust with a one-shot business-data migration. GPT-5.5 narrows that claim significantly, even though it does not eliminate it. The remaining failures are exactly the kind of failures that matter in production, and they are worth listing in detail.

GPT-5.5 missed the SVC-007 service-code conflict, and the schema it produced did not include a service\_code column, which made the conflict unrepresentable in the output. It created Terrence Blackwood as a canonical customer instead of treating that record as an orphan that needed human review. It left payment\_status with 29 distinct raw values rather than a normalized enum. It left the payment method values unnormalized as well. It produced 22 services where the expected number was 18. It created 1,632 jobs against an expected range of 800 to 1,200. The frontend review UI it built showed 442 flagged items in one place and 677 in another, because different parts of the interface were counting different things against the underlying database.

The pattern in those failures is the part worth dwelling on. GPT-5.5 improved on the errors that are semantically obvious to a human reader (fake records, duplicate people, name typos, all of which look wrong on sight), and it still struggled with the boring backend hygiene that makes a migration production-safe. Enum normalization, service-code preservation, orphan handling, canonical job grouping, and reconciliation between the dashboard and the database are not glamorous problems, but they are the ones that determine whether the migration holds up over time. The model has crossed the threshold where it catches the obvious mistakes, and it has not yet crossed the threshold where it catches the careful ones.

This is exactly why running both Dingo and Splash Bros matters. If I had only run Dingo, I could honestly tell you that GPT-5.5 is close to replacing a whole knowledge-work pass. If I had only run Splash Bros, I would sound much more cautious about the entire release. Running both, side by side, gives the real answer: GPT-5.5 is good enough to do the first serious pass on a messy data migration, but it is not yet good enough to be the final authority on canonical data. That distinction is not an insult to the model. It is a description of how I would actually use it in production work.

What I would do in practice is use GPT-5.5 to compress the hardest middle part of the migration. I would ask it to inventory the files, build the extraction pipeline, design the initial schema, generate the audit layer, produce the review queue, and write the migration report. Then I would run validators against the result, check the row counts, inspect the enum maps, force any orphan records into a manual queue, require a service\_code column in the schema, compare the dashboard counts against direct SQL counts, and have a human approve canonical merges before the data left the staging environment. The model is strong enough that those instructions matter, because if you give it a better harness, it produces noticeably better work. That is one of the central lessons of the GPT-5.5 release: the model is powerful, and the harness around it determines whether the power turns into trust.


## The Artemis test: strong info, weaker taste

The task is to build an interactive 3D visualization of NASA’s Artemis II mission, with no facts provided and no tech stack specified. The model has to research the mission, construct the SLS vehicle geometry, animate the sequence from launch through lunar flyby and return, create a realistic space environment, add controls, support timeline scrubbing, make components clickable, and present enough information that a viewer could actually learn something from the artifact. The test is hard because the failure modes compound on each other. A model can get the research right and still build a bad visualization, and it can build a beautiful visualization while hallucinating the underlying mission. It can animate the rocket competently but fail the controls, and it can add controls without making the information possible to find. It can produce something technically impressive and still leave the viewer with a scene that is unpleasant to look at.

Both GPT-5.5 and Opus 4.7 handled the core facts well. They understood that Artemis II is a lunar flyby rather than a landing or a lunar orbit, and they got the basic shape of the mission right. The trajectories were not perfect in either case, but they were reasonable for a browser visualization, and neither model collapsed Artemis II into a different mission, which is a real risk on a topic where the public mental model often blends Apollo, Artemis I, Artemis II, and Artemis III together.

The split between the two models showed up in presentation. GPT-5.5 leaned hard on information density, with clickable bubbles, panels, dense labels, and several different ways to surface specific facts. If you cared about learning, the GPT-5.5 build did a great deal right. The visuals, however, looked more cartoonish than they should have: the scale felt off, the proportions were less grounded, and the overall scene lacked the visual authority that the topic deserves.

[![](https://substackcdn.com/image/fetch/$s_!pVQU!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd009801a-6039-437e-846a-57ad866b3ccd_1600x1000.png)](https://substackcdn.com/image/fetch/$s_!pVQU!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd009801a-6039-437e-846a-57ad866b3ccd_1600x1000.png)

GPT-5.5’s Artemis II visualization: dense information panels, mission telemetry, crew roster, clickable timeline, and research sources. Strong on data, weaker on visual authority.

Opus 4.7 produced the opposite tradeoff. The visuals were substantially stronger, with better lighting, better composition, and a more grounded sense of scene that made the artifact feel like something you would actually want to show to someone. The cost of that quality was that the information was less immediately discoverable, and a viewer had to explore more of the scene to find specific facts.

[![](https://substackcdn.com/image/fetch/$s_!FuZm!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdb73e770-6fb2-4bc4-b6bc-9d1f807aac8d_1440x900.jpeg)](https://substackcdn.com/image/fetch/$s_!FuZm!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdb73e770-6fb2-4bc4-b6bc-9d1f807aac8d_1440x900.jpeg)

Opus 4.7’s Artemis II visualization: better lighting, better composition, cinematic quality. The mission events panel is detailed, but the information requires more exploration to find.

Neither model nailed the controls completely, and both needed another pass: each one missed the obvious “take me back to the ship” button after the user zoomed out, Opus had a strange semi-transparent Earth issue, and GPT-5.5 had scale and style problems. If I were turning either build into a final public artifact, I would probably start from the Opus version and add GPT-5.5’s information density on top, which is the honest answer rather than a tidy one.

![](https://substackcdn.com/image/fetch/$s_!m3UK!,w_720,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F759735c4-a3c7-443d-86e6-694739c08015_1600x1000.png)![](https://substackcdn.com/image/fetch/$s_!y1ci!,w_720,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd464223e-adfc-46d4-90d9-eda4b585e3eb_1440x900.jpeg)

Left: GPT-5.5 at closest lunar approach: trajectory line, distance data (4,070 mi to Moon), event description, and research sources all visible. Information-rich but visually simpler.

Right: Opus 4.7 at closest lunar approach: detailed lunar surface, better lighting, cinematic composition. The visual authority gap is real, and it is the reason the routing answer for visual work still starts with Claude.

The Artemis result points to the remaining OpenAI weakness, which is frontend taste and visual composition from a blank canvas. The weakness is real, and it shows up across more than just this one test. It is also getting easier to mitigate. I do not yet trust GPT-5.5 to invent a beautiful frontend or visual style from scratch the way I trust Opus, but I do trust it to implement a strong visual reference faithfully, and this is exactly where the Images 2 workflow I described earlier becomes practical. Give it a target to hit rather than a canvas to invent from, and the results are noticeably better. The labs are diverging in interesting ways: OpenAI is ahead on backend volume, audit depth, tool use, and end-to-end work completion, while Anthropic is still ahead on a lot of frontend craft. The practical answer is to route work to the right combination, rather than to pick a single model and apply it to everything.


## Codex is where GPT-5.5 shines

I have been using Codex more than the ChatGPT app for serious work over the last few weeks, and the gap between the two surfaces is widening fast. ChatGPT is still the broad consumer interface that I reach for when I want quick questions, image work, voice interaction, search, and general assistance. Codex is increasingly the place where the work actually happens, and you can feel the influence of the Sky team (the macOS AI overlay startup OpenAI acquired in late 2025) on the direction the app is heading.

This distinction matters specifically for GPT-5.5, because the model is at its best when it can act on the world rather than just respond to a prompt. A model this strong, trapped inside a chat window, is dramatically underused. The same model placed inside Codex can inspect files, edit code, run commands, drive a browser, test interfaces, read documents, generate artifacts, and iterate against its own output. The shift from the first scenario to the second is the difference between having a smart assistant on standby and having a work system that finishes tasks while you are looking at something else.

The April Codex computer-use release was a large part of this shift. Background computer use means the agent can drive software without taking over your machine, so it can click around, test flows, open pages, and operate the same kinds of interfaces that humans operate, all while you continue working in another window. Most useful systems still do not have clean APIs or maintained integrations, and a great deal of real work happens inside graphical interfaces that nobody has wrapped, so a model that can use those interfaces directly can reach much more of the world than a model that is limited to function calls.

The combination of GPT-5.5 inside Codex is what makes the model-plus-harness argument so concrete. Claude can be brilliant in isolation, and Gemini can be excellent in specific contexts, but GPT-5.5 inside Codex has a clearer path to do end-to-end work because the environment is designed to let it do that work. The whole package is stronger than either piece would be alone, and you can also feel where the Codex app itself is heading: the Mac-native computer-use work, the background execution model, and the way the interface treats the agent as a peer rather than a tool. None of it feels like a code editor with an LLM bolted on. It feels like an agent surface that happens to be very good at code, and the distinction will matter more over the next year as the work people delegate keeps growing.

The gap between ChatGPT and Codex points in another direction worth noting. ChatGPT remains the place where the model talks to you, while Codex is becoming the place where the model works with your computer, and those are not the same product. For a model as strong as GPT-5.5, the second of those two surfaces is the one where the model feels most powerful, and the gap between “talking with the model” and “working with the model” is where I expect the most interesting product development to happen in 2026.


## Writing took a real step forward

Writing is another place where GPT-5.5 represents a real step forward, even though it is not at the level where I would publish raw output without editing. The improvement is large enough to change my workflow, but it does not replace the work of having taste.

The biggest change is structural rather than sentence-level. GPT-5.5 is meaningfully better at holding the shape of a long argument, understanding what a piece is really about, turning notes into a coherent article rather than a pile of sections, and preserving nuance across a long draft. Most AI writing failures have always been shape failures rather than sentence failures: the model gives you an introduction, then a string of body sections, then a conclusion, but the argument never actually builds, the sections sit next to each other rather than moving the reader forward, the connective tissue is generic, the contrasts are cheap, and the model writes like it is answering a prompt rather than making a case. GPT-5.5 is much better at the build than its predecessors were, and the difference shows up most clearly on longer pieces with more complicated arguments.

The model still needs to be steered. You still have to give it real examples of the voice you want, you still have to tell it what the point of the piece actually is, and you still have to edit the draft once it comes back. What has changed is how much of the work I am willing to delegate before I take over. I now trust the model with larger writing surfaces, and I can hand it a bigger pile of evidence and ask for a real article shape. I can ask it to preserve a particular view rather than averaging it into something safer, and I can ask it to explain a technical test to a reader who does not already know the context, with the expectation that the model will actually do the setup work rather than skip it. None of those properties were reliable in earlier OpenAI models, and the change has been large enough to shift my default writing process.

The improvement also connects back to the broader theme of the release. The model is better at complex work because it is better at understanding structure, and writing is just one expression of that capability. Coding is another; multi-artifact business work is a third, and the common thread across all of them is that GPT-5.5 sees the whole shape of the task earlier than its predecessors did and keeps that shape in mind as it works.


## Compute availability is part of the product

Availability is the part of the model picture that most reviews undervalue, and it has become important enough that no serious evaluation can leave it out. The best model in the world does not help you if you cannot use it when you need to, and compute constraints show up in the user experience as caps, slowdowns, degraded products, expensive pricing, limited sessions, and routing decisions that quietly send your work to a smaller model.

The public status pages from the two labs make the gap concrete rather than impressionistic. As of this writing, Anthropic’s status page shows 98.75% uptime on claude.ai, 99.09% on the Claude Console, 99.05% on the Claude API, and 99.22% on Claude Code over the last 90 days. OpenAI’s status page over its rolling four-month window shows 99.99% on APIs, 99.80% on ChatGPT, 99.98% on Codex, and 99.95% on Sora. The differences look small as percentages, but at the daily-workflow level they correspond to meaningfully more incidents on the Anthropic side, and they line up with what I have felt in normal use: more frequent caps, more retry loops, and more stretches where the model I wanted was not available at the effort level I wanted it. Anthropic has also been openly assembling more compute, including the publicly announced multi-billion-dollar Amazon Trainium expansion and the additional Google TPU capacity, which are exactly the moves you make when the constraint is real and you intend to fix it.

The point matters for adoption in a way that goes beyond convenience. When I am building a daily workflow around a model, I need to know which model gives the best answer in a controlled test, and I also need to know which model system can actually run when I need it, at the effort level I want, inside the harness I prefer, without forcing me to ration usage against arbitrary caps. That second question is downstream of compute, and compute has become a meaningful part of product quality rather than an infrastructure detail.

Part of why the GPT-5.5 release feels significant is that the model is stronger and OpenAI appears to have enough capacity to make it a real default for many users at once. All the labs are compute-constrained to some extent, and that constraint will not disappear, but the lab that can serve the better model more reliably ends up with a better product even when the underlying weights are similar. As of right now, OpenAI is winning that comparison in the places where I notice the most.


## How I am actually using it

My routing across the frontier models has shifted noticeably since GPT-5.5 shipped, and the new defaults are pretty straightforward to describe.

For complex multi-step execution, GPT-5.5 has become my default choice. If the work involves files, code, tools, browser use, data, documents, or artifacts of any kind, I start there, and the longer and messier the job is, the wider the gap between GPT-5.5 and the alternatives becomes.

For blank-canvas frontend taste, I still often start with Opus 4.7, because Claude continues to make better visual decisions when there is no design direction to anchor against. If the deliverable is meant to look beautiful from the start and there is no reference image to follow, Opus is still the right place to begin.

For UI work where I want both production strength and visual quality, I increasingly want to generate a visual reference first and then implement against it. Using Images 2 to create the mockup and GPT-5.5 inside Codex to build the working version captures the best of both inside the OpenAI stack and removes the part of the workflow where the model has to invent taste from nothing.

For engineering work, I prefer a two-model workflow over any one-model commitment. Opus 4.7 is very good at planning, architecture, and critique, and GPT-5.5 inside Codex is excellent at execution, testing, and carrying the work through. Combining the two is consistently better than relying on either model alone, and the workflow is mature enough now that the handoff between planning and execution feels natural rather than forced.

For writing, I have been using GPT-5.5 more than I expected to. The edits I make are still substantial, but I am willing to trust the model with more of the structure and the argument shape rather than just the sentences, and that change alone has compressed how long it takes me to produce a long piece.

For data work, I use GPT-5.5 aggressively but with explicit validation built into the prompt. I want source provenance, rejected records, conflict tables, normalized enum maps, row-count checks, schema constraints, and reconciliation reports as part of the output, and I do not let the model declare the migration finished on its own. Splash Bros is a permanent reminder that the canary can still get into the database if I do not check.

For research-heavy work, I want sources cited and I want the model to preserve uncertainty rather than smoothing it over. Artificial Analysis flagged a useful caution on this point: GPT-5.5 topped the Intelligence Index but paired its high accuracy with a relatively high hallucination rate on the Omniscience benchmark, which matches my general experience. The model is extremely capable, but capability is not the same thing as epistemic humility, and source discipline still matters.

The broader point I draw from all of this is that the future of AI use is not a single model but a routing strategy. Different models, different harnesses, different surfaces, and different strengths combine into the right answer for any specific piece of work, and the people who get the most out of the frontier are the ones who learn how to route across it. With that said, when I need a single default model for serious work today, the answer is GPT-5.5.


## The bottom line

GPT-5.5 is the strongest model in the world right now, and the ways in which it is strongest matter more than the ways in which it is not. It is especially good when the task is complex, multi-step, messy, and tool-heavy. It is meaningfully better at writing than the OpenAI models that came before it. It is excellent inside Codex. And the surrounding release cadence makes all of it land harder than model quality alone would suggest: Images 2 covers the visual direction, Codex computer use provides the ability to act, and GPT-5.5 completes the workflow around them.

The three tests I ran say something more useful together than any single benchmark could on its own. The Dingo test demonstrated that the model can take a strange business situation, a pile of evidence, and a long artifact contract and produce something that feels close to a real executive handoff. The Splash Bros test showed where the boundary still sits: GPT-5.5 cleared the canary check, merged the obvious duplicates, and produced the first defensible customer count, but it still missed the kind of backend hygiene that would matter in production. The Artemis test surfaced the remaining nuance in routing: GPT-5.5 was strong on information density and execution, while Opus retained the better visual foundation, and the right answer for a final product depends on which of those properties matters more.

GPT-5.5 is not a replacement for human judgment, it is not the best taste model on the frontier, and it is not safe to trust blindly with final production data. It still needs review, validation, and direction from a person who knows what good looks like. But it is the new high-water mark for what a single model can carry in real work, and high-water marks matter because they change what users are willing to try, how ambitious the prompts get, how much work people delegate, and what products become possible to build around the model.

If you test GPT-5.5 on easy tasks, you will probably miss the upgrade, because the previous models were already good enough for easy tasks and the differences at that level are small. The way to see what has actually changed is to give the model the kind of work that used to break models a release ago: the multi-artifact briefs, the messy data piles, the long agentic loops, the writing assignments where structure matters more than sentences, and the tool-heavy tasks that require the model to keep going long after a chat window would normally end the interaction. The model is smarter in quick mode because the underlying pre-train is better, it is much stronger in thinking mode for the same reason, it is better wrapped inside Codex than any previous OpenAI model has been wrapped, it pairs naturally with Images 2 on visual work, and it has enough availability to become a daily default rather than a special-occasion tool.

Taken together, those properties make the old question about model quality feel too small. The interesting question is no longer whether GPT-5.5 can answer better than its predecessors. The interesting question is what you can now ask it to do.

This was a long one, and the detail matters because the differences between models show up in the details. If you want the compressed version to keep next to your keyboard, here it is.


### Top 10 takeaways

1. The frontier moved enough that you should raise your ambition for what you delegate, especially on messy, multi-step work.
2. Do not evaluate models on easy tasks. Test them on real workflows with files, tools, ambiguity, contradictions, and artifacts someone actually has to use.
3. The best model is no longer just the smartest model in a chat box. The winning system is the model plus the harness: Codex, computer use, file access, browser control, image generation, and available compute.
4. GPT-5.5 is strongest when the work requires execution: reading sources, making judgments, producing deliverables, checking output, and carrying a task through multiple steps.
5. Use it aggressively for first serious drafts of complex work, but keep humans in the loop for final judgment, especially when legal, financial, operational, or data quality risks are involved.
6. For data work, never ask the model to “finish the migration” and trust the result. Require source provenance, rejected records, conflict tables, normalized enums, row-count checks, schema constraints, and reconciliation reports.
7. For visual and frontend work, do not rely on GPT-5.5 to invent taste from a blank page. Give it a strong reference image or mockup, then use it to implement faithfully.
8. Codex is where GPT-5.5 becomes most valuable, because the model can act on files, code, browsers, documents, and interfaces instead of only answering prompts.
9. Availability is part of model quality. A slightly better model you cannot reliably use is often less valuable than a strong model that is available inside the right workflow.
10. The practical skill now is routing: use the strongest default for complex execution, use other models where they still have an edge, and design workflows that combine their strengths instead of treating model choice as a single permanent bet.


### Top 10 prompt tips

1. Give GPT-5.5 the whole messy job, not just a clean slice. It performs best when it can see the full context, infer the shape of the work, and produce an end-to-end result.
2. Define the artifact contract up front. Tell it exactly what files, formats, charts, docs, decks, tables, dashboards, or reports you expect, and make “real usable artifacts” part of the assignment.
3. Ask it to separate understanding from execution. Have it first state the task shape, risks, assumptions, and plan, then produce the work. GPT-5.5 is strong at seeing the structure early, so use that.
4. For data work, require validation layers in the prompt. Ask for rejected records, duplicate logic, enum normalization, source provenance, row-count checks, conflict tables, and a human review queue.
5. Do not let it self-certify production data. Ask it to build the migration, but also ask it to surface what still needs human approval before anything becomes canonical.
6. Use Codex when the task touches files, code, apps, browsers, or artifacts. GPT-5.5 is much more valuable when it can inspect, edit, run, test, and iterate instead of only responding in chat.
7. For visual work, give it a reference instead of asking it to invent taste. Use a mockup, screenshot, generated image, or clear visual target, then ask GPT-5.5 to implement against that reference.
8. Prompt it for uncertainty, not just answers. On research-heavy work, explicitly ask for sources, confidence levels, unresolved questions, and places where the evidence does not support a firm claim.
9. Use it for the first serious pass, then review the final mile yourself. GPT-5.5 can compress the hard middle of the work, but legal posture, data quality, visual taste, and final polish still need judgment.
10. Route by task, not loyalty. Use GPT-5.5 as the default for complex execution, tool-heavy work, long writing structure, and artifact production, but pair it with other models or references where visual taste, critique, or planning would benefit from another pass.

[![](https://substackcdn.com/image/fetch/$s_!c-kw!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5a6cb887-7c79-4dfb-b033-9d9deda07f67_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!c-kw!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5a6cb887-7c79-4dfb-b033-9d9deda07f67_1024x1024.jpeg)
