---
title: "Here's How I Pick the Right AI for Jobs that Matter: My 5 Prompts + a ChatGPT 5.2 vs. Claude Opus 4.5 vs. Gemini 3 Deep Dive"
author: "Nate Jones"
published: 2025-12-15
url: https://natesnewsletter.substack.com/p/grab-the-5-prompts-i-use-to-discover
audience: everyone
scraped_at: 2026-01-05 19:09:59
---

Video game graphics took decades to evolve from 8-bit to 4K. AI models just made a similar jump in about a year.

We’re still squinting at them like they’re 8-bit.

[![](https://substackcdn.com/image/fetch/$s_!9UFH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1497701b-4aa9-4718-9631-6922204274bc_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!9UFH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1497701b-4aa9-4718-9631-6922204274bc_1408x768.jpeg)

The differences between GPT-5.2, Claude Opus 4.5, and Gemini 3 are real and meaningful—but they don’t show up in benchmark charts or Twitter arguments about “which model is best.” Those tools are too low-resolution. They’re like evaluating 4K graphics on a CRT monitor.

Perhaps it was relevant to ask which model was best overall a year or two ago. But I don’t think it’s a useful question now. And I think we need to stop asking it.

[![](https://substackcdn.com/image/fetch/$s_!uR8v!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F54ae804e-2a42-4b31-b475-95af363af84a_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!uR8v!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F54ae804e-2a42-4b31-b475-95af363af84a_1408x768.jpeg)

In a world where LLMs are literally advancing science, we should be asking much more detailed questions to evaluate real work.

Because, after all, the real work we do IS detailed. That texture matters. Which model can read tally marks? Which can read a 10,000 row spreadsheet? Which can code for 10 hours in a token efficient way? Which one is ok with contradictory and confusing data? Which one produces the powerpoint most compatible with my style?

There’s an essay by John Salvatier called “Reality Has a Surprising Amount of Detail” that’s become my lens for this. He tells the story of building basement stairs—something that seems simple until you discover that lumber warps after it’s cut, screws pull brackets off-angle, and getting every step aligned requires techniques you didn’t know existed. The details aren’t incidental. They’re where all the real problems live.

I built stairs with my granddad, so this hits for me.

Model capabilities have become similarly detailed. And I think we’re busy trying to simplify them too much. Maybe because we’ve been missing the lens to see the detail.

Which is too bad, because the detail is what’s going to help us get real work done!

So this is what I’ve got for you: a full breakdown in detail of ChatGPT 5.2 vs. Opus 4.5 vs. Gemini 3, plus some prompts I use to start to tease out what’s in my head and what I need to observe—the details—for really important work.

**Plus there’s more:**

- **Why the “best model” question dissolves:** The discourse is too coarse to capture what’s actually different, and the details that matter for your work aren’t the same as the details that matter for mine.
- **Simple wins as a way of seeing:** How to get granular enough that you notice what benchmarks miss—and why the filter is “work you care about being good.”
- **The five prompts that make detail visible:**

  - *The Filter* — Identify which of your recurring tasks actually warrant careful model selection (most don’t).
  - *The Preference Interview* — Surface the standards you’ve been applying unconsciously, so you have something concrete to test against.
  - *The Detail Map* — See the hidden complexity in work that seems simple—where the real failure modes live.
  - *The Comparison Setup* — Design a clean head-to-head test that reveals real differences, not surface variation.
  - *The Observation Log* — Capture what you actually noticed before the details fade into vague impressions.
- **Field notes on GPT-5.2, Opus 4.5, and Gemini 3:** Not rankings, but observations about where I’ve seen surprising detail in how these models actually behave.
- **The coding deep-dive:** Where practitioners have gotten most specific about model differences—and what their observations reveal about how to see capability surfaces clearly.
- **Finding your own detail:** The real question isn’t which model is best. It’s where you do work that you care about enough that the detail matters.

Remember, the goal isn’t to crown a winner. It’s to remember that models have a surprising amount of detail, to build the kind of intuition that only comes from direct contact with reality—and to give you a set of tools for seeing detail you might otherwise miss. Get out the magnifying glass!


## [GRAB THE PROMPTS](https://www.notion.so/product-templates/Simple-Wins-Model-Discovery-Prompts-2ca5a2ccb52680639a5fd8f29e6bf2df?source=copy_link)

These aren’t evaluation frameworks—they’re interview prompts that help you see what you already know but haven’t articulated.

The first helps you identify which of your recurring tasks are actually worth careful model selection (most aren’t). The second surfaces the preferences you’ve been applying unconsciously—the things that make you accept an output, edit it, or start over.

The third maps the hidden complexity in work that seems simple. The fourth designs a clean head-to-head test. The fifth captures what you noticed before the details fade. They work because they force you to get specific enough that you start noticing things benchmarks can’t measure. Run them in sequence or pick the one that fits where you are.

---


## Models have a Surprising Amount of Detail


### The Problem With Coarse Assessments

Every week I get messages from readers asking which model is best. Sometimes they’re genuinely curious. Sometimes they’re frustrated—I recommended one model and they think I’m missing something obvious about another. The discourse has become tribal in a way that reminds me of the old Mac versus Windows wars, where your choice of tool became a marker of identity rather than a practical decision about fit.

[![](https://substackcdn.com/image/fetch/$s_!Ru2g!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffe81665b-9e1b-4f25-aea3-06829eabacb1_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!Ru2g!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffe81665b-9e1b-4f25-aea3-06829eabacb1_1408x768.jpeg)

But here’s what I’ve learned from actually using these models on real work: the question “which model is best” dissolves when you get detailed enough. It’s not that there’s no answer—it’s that there are many answers, and they depend on details that most people aren’t tracking.

Think about what happened with graphics. In the 8-bit era, you could reasonably ask “which console has better graphics?” and get a meaningful answer. The differences were coarse enough to compare directly. But try asking that question about modern gaming platforms and it fragments immediately. Better at what? Texture detail? Lighting? Draw distance? Frame rate stability? Anti-aliasing? The category “graphics” has exploded into dozens of specific capabilities that different systems handle differently.

Model capabilities have undergone the same fragmentation, just faster. “GPT-5.2 is better at coding” is a claim that dissolves into dozens of more specific observations when you get close enough. Better at what kind of coding? In what harness? With what kind of feedback loop? On what timescale? The practitioners who’ve gotten most granular about this don’t talk about models being “better” or “worse.” They talk about specific behaviors in specific contexts—observations that only become visible when you’re actually doing the work.

This is [Salvatier’s point about stairs](http://johnsalvatier.org/blog/2017/reality-has-a-surprising-amount-of-detail). At a high level, stairs are simple. But as you actually build them, you run into the reality that wood warps, screws don’t go in straight, and “cut at the right angle” turns out to require either creative tracing or actual trigonometry. The details aren’t complications layered on top of a simple task. They’re where the task actually lives.


### Simple Wins: Getting Close Enough to See

Salvatier makes the point that details are invisible before you notice them and obvious after. The only way to see them is to get close enough to reality that you run into them.

For model evaluation, that means trying models on work where you have genuine expertise—work where you’ll notice if the output is subtly wrong in ways that would fool a novice. Not toy tasks designed to test the model. Real work with real stakes, where you know what good looks like because you’ve done it yourself many times.

I call these simple wins because the task should be small and bounded enough that you can actually tell whether it worked. Not “write me a strategy for entering the Japanese market” but “take these three analyst reports and tell me where they contradict each other.” Not “build me an app” but “refactor this function and don’t break the tests.” The simpler the task, the clearer the signal about whether the model’s output is actually usable.

But there’s a more important filter than task size: do you actually care about this work being good?

Most of what we do with AI assistance doesn’t warrant careful model selection. Quick lookups, first drafts, brainstorming, administrative tasks—for these, the right answer is to use whatever’s convenient and move on. The detail that separates models doesn’t matter if you don’t have opinions about what “good” looks like for that task.

The tasks worth this level of attention are the ones where you’d notice subtle wrongness. Where mediocre output would bother you—not because the stakes are high or someone’s watching, but because you have real standards for this kind of work. Where a 15% improvement would feel meaningful because you know enough to see it.

These are the tasks where model differences actually matter to you. They’re worth discovering, not defaulting.


### What I Mean by “Capability Surface”

When I talk about model capability surfaces, I mean something specific: the topology of what a model can and can’t do, mapped across the space of possible tasks. Not a single score, but a landscape with peaks and valleys—places where the model excels and places where it struggles.

[![](https://substackcdn.com/image/fetch/$s_!qBCL!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff69f9624-154c-42f7-aa7d-f4b94d7aa2fa_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!qBCL!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff69f9624-154c-42f7-aa7d-f4b94d7aa2fa_1408x768.jpeg)

The graphics analogy helps here too. An 8-bit system has a simple capability surface—there’s not much variance because there’s not much capability. A modern GPU has an enormously complex capability surface, with different performance characteristics for different rendering techniques, different shader models, different memory access patterns. The surface got more detailed as the underlying capability increased.

The same thing has happened with language models, but compressed into a much shorter timeframe. A year ago, you could make reasonable generalizations about model capabilities. Now, the differences between models show up at a much finer grain, and generalizations that were roughly true have started breaking down.

Consider what this means practically. “Opus is good at writing” used to be a reasonable summary. Now, practitioners are noticing that Opus has specific strengths in certain kinds of writing—executive communication, nuanced persuasion, prose that sounds like a human with good judgment wrote it—while being less distinctive in other areas (I don’t like it for creative writing). The category “writing” has fragmented into dozens of more specific capabilities, and models have different profiles across them.

**This is good news for anyone trying to get work done.** More detail in capability surfaces means more opportunity to find the right tool for specific tasks. But it requires a different approach to evaluation—one that gets granular enough to see the topology.


### Field Notes: Where I’ve Seen Surprising Detail

What follows isn’t a ranking. It’s a set of observations about where I’ve noticed fine-grained differences in how these models behave—the kind of details that don’t show up in benchmarks but matter when you’re trying to get work done. I’m holding these with appropriate uncertainty. Capability surfaces shift when contexts change, and what I’ve seen may not match what you see in your domain.

**Gemini 3**

Gemini’s distinctive strength is bandwidth. Google built it around a massive context window—up to a million tokens in the Pro configuration—and the practical effect is that it can hold an enormous amount of material in working memory without losing the thread. When I need to ingest a sprawling mess of documents and build a mental map fast, Gemini often gets me to orientation faster than anything else. It’s genuinely impressive at compression: turning scattered inputs into a coherent picture of what’s actually being claimed, where the contradictions are, and what questions I should ask next.

The detail I’ve learned to watch for is what happens downstream. Gemini’s strength is synthesis and mapping, but the business world is still deeply Office-shaped. When I need to take a great synthesis and turn it into a spreadsheet or deck in the exact format my organization expects, there’s often a conversion tax. The model gives me clarity, but getting that clarity into a usable artifact sometimes costs more time than I saved.

The other pattern is edge-case smoothing. Global compression can round off exceptions and anomalies unless you explicitly ask for them. One practitioner I spoke with found that Gemini couldn’t locate a specific quote that another model found easily—not because Gemini is worse at search, but because its default tendency is to build a clean map, and clean maps sometimes sand down the details that don’t fit.

**GPT-5.2**

GPT-5.2’s distinctive strength is structured execution. OpenAI built it explicitly around professional tasks—artifacts like spreadsheets and presentations, tool use, long bounded assignments that need to stay organized. When I give it a tight brief and a clear deliverable, it often comes back with something that looks like a junior analyst actually did the work. Not a clever response. A work product I can use.

The detail that matters most is what I’d call commitment style. GPT-5.2 wants to make things cohere. It maps the problem, reconciles constraints, builds a stable model, and then executes against that model. This is a strength when the underlying reality is clean and the task is well-specified. It becomes a problem when reality is messy or contradictory—the model will produce a beautiful, confident output that’s cleaner than the truth. You have to force it to show its work, cite evidence, flag uncertainty. Without that structure, it can hand you a compelling narrative built on shaky ground.

The other detail is instruction fidelity. GPT-5.2 follows instructions with almost excessive literalness. It will contort solutions around constraints you forgot you wrote. This is excellent for some tasks—code review, checklist verification, anything where you want the model to catch deviations from spec. It’s frustrating for generative work, where you want the model to make judgment calls instead of asking permission for every decision.

**Opus 4.5**

Opus 4.5 has two distinct strengths that people often conflate: taste in writing and momentum in agentic contexts.

The taste piece is real. When I need something that sounds like a human with good judgment wrote it—executive communication, persuasive writing, anything where tone and nuance matter—Opus produces the most polished output of the three. This isn’t about pretty words. It’s about the model understanding that sometimes admitting uncertainty is better than forcing false coherence, that how you frame something can matter as much as what you say.

The agentic strength is more situational. It depends heavily on context. Opus in a well-configured agentic harness can feel like it’s cooking—it commits early, maintains momentum, uses tools as part of its thinking rather than a separate step. Developers I’ve talked to describe a moment where the model stops feeling like an assistant and starts feeling like a collaborator who can actually ship.

The detail I’ve learned to watch for is what one practitioner called “going for it.” Opus wants to move. That’s a strength when you want momentum, but it can mean the model burns cycles on wasted iterations if your objective isn’t crystal clear. The same developers running long sessions found that Opus was harder to convince to be methodical—to validate assumptions, record what worked and what didn’t, iterate systematically rather than confidently.


### The Coding Deep-Dive: Where Practitioners Have Gotten Granular

I want to spend a bit more time on coding because it’s the domain where practitioners have gotten most specific about model differences. Not because coding is more important than other work, but because the community has developed a shared vocabulary for talking about capability details that I think generalizes.

This is what “4K evaluation” looks like. Not “which model is best at coding” but a detailed map of which model handles which workflow, with what tradeoffs, in what contexts.

When developers talk about “AI coding tools,” they’re actually talking about several distinct workflows with different requirements. The details that matter for “take the wheel and make changes across a repo” are completely different from the details that matter for “find the root cause of a thorny bug” or “catch what humans miss in code review.” Each workflow has its own capability surface, and models have different profiles on each.

**Repo-agent execution** is where you want the model to read a codebase, propose a plan, touch multiple files, run tests, and produce a mergeable PR. This is where harness behavior matters most—permissions, tool APIs, context management, whether the system can sustain a multi-step loop without losing the plot. Anthropic positions Opus 4.5 as excelling at “heavy-duty agentic workflows,” and community reports support this for repo-agent work. But the same “go for it” tendency that creates momentum can also mean broad changes when you asked for a surgical fix. The model might ignore constraints as sessions progress, depending on how context is managed.

**Hard debugging**—reproducing from logs, forming hypotheses, isolating minimal fixes—rewards different capabilities entirely. Here you want local fidelity, verification behavior, and “don’t change anything unnecessary.” Practitioners report GPT-5.2 excels at this kind of methodical work, particularly when the bug is low-level or multi-factor. Its context management supports extended debug sessions, and its literalness becomes an asset when you need the model to prove its hypotheses rather than assert them.

**Code review** is yet another profile. This is mostly artifact analysis plus discipline—reading diffs carefully, grounding comments in code, maintaining consistent standards. OpenAI has built explicit product surfaces for this (tagging @codex review to get comments “the same way your team would”). It’s one of the most concrete workflow-specific features in any stack.

**Large refactors and migrations** need long-horizon state management, consistent changes across many files, and coordination across touchpoints. This is where “just generate code” fails completely. You need multi-agent orchestration, artifact tracking, and careful delta control. Gemini in its agent-first IDE is designed for exactly this kind of work, though practitioners flag real autonomy risks—there are credible reports of dangerous command execution defaults and at least one widely reported incident of catastrophic deletion after a misinterpreted instruction.

What I find valuable about the coding discourse isn’t the specific conclusions—those will shift as models and harnesses evolve. It’s the level of granularity. Practitioners have moved past “which model is best at coding” to observations like “Claude Code’s context compaction preserves more detail across long sessions, which means Opus can pick up where it left off while GPT-5.2 sometimes burns cycles relearning the basics.” That’s a stair-building observation. It only becomes visible when you’re actually doing the work, and it matters enormously for whether a tool fits your workflow.


### Finding Your Own Detail

The coding example matters because it shows what granular model evaluation looks like when a community gets serious about it. But unless you’re a developer, those specific observations aren’t directly useful to you. They’re useful as a pattern—as evidence that this level of detail exists in model capabilities and that practitioners who look for it find it.

The question is: where does this level of detail matter for your work?

I’ve been thinking about this for my own practice, and I want to share what I’ve found—not as a template, but as an example of what “getting granular” actually looks like when you’re not writing code.

My version of simple wins lives in strategic synthesis. I spend a significant part of my working life taking messy inputs—executive interviews, market research, competitor analyses, internal documents that often contradict each other—and turning them into coherent narratives that executives can actually use to make decisions. This is work I care about being good. Not just because clients are paying for it, but because I have strong opinions about what separates a useful synthesis from a dressed-up summary.

A dressed-up summary tells you what the documents said. A useful synthesis tells you what to believe and why—it resolves contradictions instead of listing them, it identifies the two or three things that actually matter among the dozens of things that might matter, it gives you a clear picture of the decision landscape without pretending the uncertainty isn’t there. I’ve done this work long enough that I can feel when a synthesis is landing versus when it’s just organized information.

When I started paying attention to model differences at this level, I noticed things I’d been feeling but hadn’t named.

Gemini gets me oriented fast. When I’m drowning in documents—a hundred pages of interview transcripts, three competing analyst reports, internal strategy decks that use the same words to mean different things—Gemini builds the map faster than anything else. It’s remarkably good at answering “what is actually being claimed here, and where do the sources disagree?” I use it at the beginning of almost every synthesis project now, just to get my bearings.

But when I need to turn that map into a deliverable that sounds like a human with judgment wrote it, I switch to Opus. There’s something about how Opus handles uncertainty—the way it can acknowledge “we don’t actually know this” without undermining the rest of the analysis—that matches how I think about executive communication. Executives don’t want false confidence. They want honest assessments from someone who’s thought carefully about the problem. Opus captures that tone better than anything else I’ve used.

GPT-5.2 fits a different slot. When the deliverable is highly structured—a spreadsheet model with specific calculations, a presentation following a client’s template, a competitive analysis that needs to hit fifteen specific dimensions—its commitment to coherence becomes an asset. It wants to make things neat and complete, and sometimes neat and complete is exactly what the work requires. I’ve also found it useful for pressure-testing my own syntheses. Its literalness means it will flag logical gaps and unstated assumptions that I might gloss over.

The handoffs between models aren’t elegant. I haven’t figured out a smooth workflow for moving context from Gemini to Opus to GPT-5.2. But even with the friction, I’m getting better outputs than I did when I used one model for everything. The detail in capability surfaces is real, and it shows up in the quality of the work.

Here’s the thing: these observations are specific to strategic synthesis. They’re the equivalent of a developer saying “Opus maintains better context across long sessions” or “GPT-5.2 is more methodical in debugging.” They only became visible because I was paying attention to work I actually care about—work where I have real standards, where I know what good looks like, where subtle wrongness would bother me.

That’s the filter. Not “what tasks do I do with AI” but “what tasks do I care about doing well.” The intersection is where simple wins live.


### Building Your Toolbelt

Most tasks don’t reward careful model selection. The effort of discovering which model fits best exceeds the value of the improvement. For those tasks, use whatever’s convenient and move on.

But you probably have a few recurring pieces of work where you’d notice the difference. Work where you have real opinions about quality—not because someone’s watching, but because mediocre output would bother you. Work where a 15% improvement would feel meaningful because you know enough to recognize it.

The method is straightforward: try the task in your current default tool to establish a baseline. Try it in one alternative. Pay attention to what happens—not just whether the output is good, but where the friction showed up, what surprised you, what you had to fix. Let the observations accumulate.

Over time, you stop chasing “the best model” and start building a small toolbelt calibrated to your actual work. Maybe Gemini is your orientation tool—you open it when you’re drowning in documents and need a map fast. Maybe GPT-5.2 is your artifact execution tool—you reach for it when the deliverable needs to be a spreadsheet and the brief is clear. Maybe Opus is your writing partner for anything that needs to sound like a human with judgment wrote it.

That’s not a wishy-washy “it depends” answer, even if it feels like one. It’s recognition that model capabilities now have enough detail to reward that level of attention. We’re not comparing 8-bit graphics anymore. We’re comparing high-resolution surfaces with real topology, and the topology matters differently depending on where you’re standing.


### The Stakes

Salvatier ends his essay with a warning: if you’re trying to do difficult things—things that aren’t known to be possible—the details that turn out to be critical are often invisible until you run into them. And you might be stuck right now, with the evidence in front of your face, unable to see it because you don’t know what you’re looking for.

I think about this in the context of how people adopt AI tools. The practitioners who’ve gotten most value aren’t the ones who found “the best model.” They’re the ones who built enough direct experience with their actual work that they started noticing which tools fit where. They got close enough to reality that the details became visible.

We went from Pong to photorealism in about forty years. Models went from party trick to genuine capability in about 2.5 years. The resolution of what they can do has increased faster than our ability to perceive it. Benchmarks are still 8-bit. Twitter discourse is still 8-bit. The only way to see in 4K is to get close enough to your own work that you start noticing the texture.

The models will keep improving. New releases will shift the landscape. But if you’ve built intuition from direct contact with reality—from simple wins accumulated over time—you’ll be able to evaluate those new releases against your actual work instead of someone else’s benchmarks.

The direction for improvement is clear: seek detail you would not normally notice. When you try a model on real work, pay attention to what actually happened, not just whether it “worked.” When something feels off but you can’t articulate why, that’s a detail trying to become visible. When you find yourself editing the same thing over and over, that’s a pattern worth naming.

If you wish to see what the models can actually do, seek to perceive what you have not yet perceived.

[![](https://substackcdn.com/image/fetch/$s_!j4QL!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb18993ea-97fa-4d61-92f2-67790cb9b976_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!j4QL!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb18993ea-97fa-4d61-92f2-67790cb9b976_1024x1024.jpeg)
