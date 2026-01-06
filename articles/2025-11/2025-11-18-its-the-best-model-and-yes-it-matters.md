---
title: "It’s the best model, and yes it matters"
author: "Nate Jones"
published: 2025-11-18
url: https://natesnewsletter.substack.com/p/gemini-3-is-1-day-1-impressions-heremore
audience: everyone
scraped_at: 2026-01-05 19:11:34
---

Gemini 3 is out, it’s EASILY #1, and it’s a big deal.

I’ll do a deeper post tomorrow on how to work with Gemini 3, but I wanted you all to get an early peek here.

My focus with this piece is simple: *what does it mean to have an unambiguous #1 model after years without one?*

Tomorrow I’ll dive deeper into practical applications and how you actually work with the model. Fun times!

---


# It’s the best model, and yes it matters

Gemini 3 is, as of Nov 18, the clear number one model in the world—and for once, that’s not a controversial statement. I’m not cherry-picking when I show you a chart like this one, because they all kinda look like this today.

[![Image](https://substackcdn.com/image/fetch/$s_!P8aq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb8fec216-8165-46a3-b3e0-f70aa8ad7d1a_1200x708.jpeg "Image")](https://substackcdn.com/image/fetch/$s_!P8aq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb8fec216-8165-46a3-b3e0-f70aa8ad7d1a_1200x708.jpeg)

In this piece I want to stay on one question: what does #1 actually mean? And why should we care? Not in a leaderboard-nerd way, but in terms of how we think about progress, risk, and what’s now on the table.

Tomorrow I’ll publish a separate, longer breakdown on the practical side: early indicators of how we should actually work with Gemini 3, integration points where it might fit in a work stack, and which workflows it unlocks. Today is about the frame.

When I say “number one,” I’m not just parroting a press release. Gemini 3 sits at the top of almost every serious benchmark we have, and it passes the sniff test in the places benchmarks can’t see—developer stories, Reddit threads, people playing with it and publishing results all over social media.

Take reasoning. On Humanity’s Last Exam, it posts the highest published score, and that score is without tools. That matters. You’re seeing the raw model, not a scaffolding stack quietly doing half the work. On ARC-AGI-2, which is full of weird abstract visual puzzles, it’s not just edging out the others—it’s in a different band. Same story on hard science QA.

[![Table displaying benchmark performance comparisons for Gemini 3 against Gemini 2.5 Pro and Claude 4 Opus models across categories like HARC-GPT2 XL Exam with scores such as 45.8 percent for Gemini 3 versus 4.4 percent for others Diamond Science Reasoning showing 91.7 percent for Gemini 3 versus 88.4 percent AME 2025 Challenge Math at 100 percent for Gemini 3 versus 88.5 percent MMLU-Pro at 83.4 percent for Gemini 3 versus 66.5 percent ChartScreening at 82.7 percent for Gemini 3 versus 61.4 percent VideoMME15 with scores like 0.15 for Gemini 3 versus 0.145 LiveCodeBench at 8.49 for Gemini 3 versus 1.76 SWEBench at 54.2 percent for Gemini 3 versus 32.6 percent VendingBench at 85.46 percent for Gemini 3 versus 57.34 percent FACTS at 70.5 percent for Gemini 3 versus 65.4 percent MMMU at 92.1 percent for Gemini 3 versus 85.5 percent GPQA at 93.4 percent for Gemini 3 versus 85.5 percent MRCR v2 at 27.0 percent for Gemini 3 versus 15.0 percent](https://substackcdn.com/image/fetch/$s_!Urq3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4bccbca3-b2d4-4cd8-8488-ccf18ea1f65d_1200x1068.jpeg "Table displaying benchmark performance comparisons for Gemini 3 against Gemini 2.5 Pro and Claude 4 Opus models across categories like HARC-GPT2 XL Exam with scores such as 45.8 percent for Gemini 3 versus 4.4 percent for others Diamond Science Reasoning showing 91.7 percent for Gemini 3 versus 88.4 percent AME 2025 Challenge Math at 100 percent for Gemini 3 versus 88.5 percent MMLU-Pro at 83.4 percent for Gemini 3 versus 66.5 percent ChartScreening at 82.7 percent for Gemini 3 versus 61.4 percent VideoMME15 with scores like 0.15 for Gemini 3 versus 0.145 LiveCodeBench at 8.49 for Gemini 3 versus 1.76 SWEBench at 54.2 percent for Gemini 3 versus 32.6 percent VendingBench at 85.46 percent for Gemini 3 versus 57.34 percent FACTS at 70.5 percent for Gemini 3 versus 65.4 percent MMMU at 92.1 percent for Gemini 3 versus 85.5 percent GPQA at 93.4 percent for Gemini 3 versus 85.5 percent MRCR v2 at 27.0 percent for Gemini 3 versus 15.0 percent")](https://substackcdn.com/image/fetch/$s_!Urq3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4bccbca3-b2d4-4cd8-8488-ccf18ea1f65d_1200x1068.jpeg)

Math is a good example of how to read these numbers. On AIME, these models are basically saturated; arguing about 94% vs 95% is like arguing about which calculator is better. But on MathArena Apex, where previous models have hovered around 1–2%, Gemini 3 hits roughly 23%. That’s not perfection; that’s a regime change. You’ve moved from “usually clueless” to “often competent” on genuinely hard, contest-style problems.

Then there’s multimodality. Gemini 3 leads on MMMU-style multimodal understanding, it posts the best reported Video-MMMU scores, and it’s very strong on OCR and document understanding. More interesting to me is what’s happening with visual interfaces.

On ScreenSpot-Pro—a benchmark that measures how well a model can read real screenshots of real apps—Gemini 3 scores around 72.7%. Claude Sonnet 4.5 lands around half that. GPT-5.1 is down in low single digits. That gap is enormous. It means we’re not just throwing a language model at your browser and hoping for the best. You have a model that can actually read the damned UI.

This kind of convergent intelligence seems to be paying off in important general intelligence benchmarks, like whether the model can make cash:

[![Line graph with x-axis labeled Days in simulation from 0 to 350 and y-axis Money balance from $0 to $3500. Multiple colored lines represent different AI models performance: pink for Gemini 3 Pro starting low and rising steeply to $3000, green for Claude Sonnet 4 fluctuating around $1500, black for Grok 4 steady at $2000, blue for GPT 5.1 dipping then recovering to $1000, and others in lighter shades. Title Money balance over time Average across runs. Legend identifies models by color.](https://substackcdn.com/image/fetch/$s_!igOV!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4abe7505-0fa7-48a7-959a-61fafa27abcd_1200x865.jpeg "Line graph with x-axis labeled Days in simulation from 0 to 350 and y-axis Money balance from $0 to $3500. Multiple colored lines represent different AI models performance: pink for Gemini 3 Pro starting low and rising steeply to $3000, green for Claude Sonnet 4 fluctuating around $1500, black for Grok 4 steady at $2000, blue for GPT 5.1 dipping then recovering to $1000, and others in lighter shades. Title Money balance over time Average across runs. Legend identifies models by color.")](https://substackcdn.com/image/fetch/$s_!igOV!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4abe7505-0fa7-48a7-959a-61fafa27abcd_1200x865.jpeg)

The key point is NOT “wow, OpenAI and Anthropic are trash now.” They’re not. Your existing models didn’t get worse last night, and OpenAI and Anthropic have better models in the can that they haven’t released yet (as does Google).

The important lesson is simple: **there is no wall.**

I mostly agree with Andrej Karpathy here:

[![](https://substackcdn.com/image/fetch/$s_!SOZg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F881f52a0-bb50-4560-87dd-a9531582342d_1168x1030.png)](https://substackcdn.com/image/fetch/$s_!SOZg!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F881f52a0-bb50-4560-87dd-a9531582342d_1168x1030.png)

I think Andrej is correct that we should take the living feel of the model over benchmarks.

But I will add that I think in this case the early evidence shows a pretty convincing alignment between both benchmarks and people in real-world situations. Here are a few examples of MANY:

[![](https://substackcdn.com/image/fetch/$s_!ps5g!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2bd58e57-03b9-4928-bad9-57babd6d9934_1164x896.png)](https://substackcdn.com/image/fetch/$s_!ps5g!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2bd58e57-03b9-4928-bad9-57babd6d9934_1164x896.png)

[![](https://substackcdn.com/image/fetch/$s_!Htx0!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F24bf2e55-04f0-40f6-9328-fdb723d30607_1160x1126.png)](https://substackcdn.com/image/fetch/$s_!Htx0!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F24bf2e55-04f0-40f6-9328-fdb723d30607_1160x1126.png)

[![](https://substackcdn.com/image/fetch/$s_!LbWP!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8d3c8d16-4fc9-4368-a063-e27067c68cc3_1172x1166.png)](https://substackcdn.com/image/fetch/$s_!LbWP!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8d3c8d16-4fc9-4368-a063-e27067c68cc3_1172x1166.png)

You get the idea.

People love to say we’ve hit some kind of ceiling, that progress is tapering off and we’re in a bubble. Gemini 3 is very strong evidence against that. We do not see a plateau in pre-training. We do not see a plateau in post-training. When labs push, they still find big gains—sometimes surprisingly big.

That doesn’t mean you’ll feel it in every use case. If you’re asking for weekend plans, or you want a one-pager summarized, Gemini 3 won’t feel like alien intelligence. The step change shows up in complex work: multi-step reasoning, tricky math, deep science questions, gnarly code, and anything that involves “see and think” together—parse this diagram, read this dashboard, watch this video and critique my form.

That’s where “number one” matters in 2025. It’s the difference between a model that can talk convincingly about hard problems, and a model that can actually move the needle on them.

Being number one also has some meta implications.

1. Gemini 3 proves that decisive leads are still possible. We’ve been stuck in a “tight horse race” narrative—everyone bunched together, trading blows. Gemini 3 looks more like someone suddenly several lengths ahead. That can happen again. If you’ve been operating under a comfy assumption that “everyone’s roughly equal, nothing huge will change soon,” you’re miscalibrated. The race is not over yet!
2. Gemini 3 forces you to keep updating your mental model of what AI can do. Every time we get a new frontier model, the surface area of viable workflows expands. We have to relearn:

   1. Which problems are now tractable?
   2. When do you actually need the smartest model vs a cheaper one?
   3. How do you combine models, tools, and agents intelligently?

That’s why there’s still so much to say about AI. The ground keeps moving.

One caveat: Gemini 3 is not a “does everyone’s job end-to-end” model. No model does that. That being said, Gemini 3 absolutely strengthens the “PhD-level researcher / strong junior colleague” analogy in many ways: it can reason, push back, ask sharper questions, and handle higher-stakes tasks than its predecessors. But the places where humans thrive—ambiguity, value trade-offs, messy stakeholders, inventing the question in the first place—those look to me to still be firmly human territory.

So it’s very very good at the things language models are good at. It is not magically good at the things language models are bad at. For example, it does not necessarily know it’s 2025. (I know, I know.)

The other underappreciated story is that the model is finally starting to feel multimodal all the way around. For a long time, image and video were second-class citizens: fun for demos, brittle in practice. With Gemini 3, we’re starting to see a model that can treat visuals as native—it reads screenshots, diagrams, PDFs, video frames and uses them in its reasoning without obviously falling over. That closes a weak spot we all knew existed. A system that can both see and think is much more interesting than one that can only talk about text.

So what does #1 mean, in practice, today? It means you now have a colleague who is measurably sharper—especially in math, science, code, and visual reasoning—than anything you’ve worked with before. That colleague is not going to take your entire job. They are going to let you cover more ground, faster, on the parts of your job that are verifiable: analysis, exploration, refactors, experiments, drafts.

And they’re going to keep getting smarter. If your takeaway is “well Google probably won,” that’s not gonna age well. ChatGPT is sitting on a better model than GPT-5.1. They’re incentivized to ship it quick. Ditto Anthropic. The race is heating up, not slowing down.

Tomorrow, I’ll publish a much more specific followup focused on new workflows we’ve unlocked with this model, along with specific recommendations for when to reach for this model vs. others.

For today, the takeaway is simpler: we just got an unambiguous number one—and that should expand both your imagination and your sense of urgency.

[![](https://substackcdn.com/image/fetch/$s_!XBK2!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F000c619a-9553-48b7-bdb6-a77652c8c015_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!XBK2!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F000c619a-9553-48b7-bdb6-a77652c8c015_1024x1024.png)
