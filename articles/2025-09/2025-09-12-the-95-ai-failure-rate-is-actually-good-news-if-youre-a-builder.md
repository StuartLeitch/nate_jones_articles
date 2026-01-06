---
title: "The 95% AI Failure Rate is Actually Good News (If You're a Builder)"
author: "Nate Jones"
published: 2025-09-12
url: https://natesnewsletter.substack.com/p/beat-the-95-ai-fail-rate-a-builders
audience: everyone
scraped_at: 2026-01-05 19:18:17
---

*That MIT study really is viral. I think the internet likes doom and gloom headlines (big surprise there).*

*Just look at Google!*

[![](https://substackcdn.com/image/fetch/$s_!0JhQ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fffd5a74d-bea4-4f22-882c-820d36b31ca3_1344x556.png)](https://substackcdn.com/image/fetch/$s_!0JhQ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fffd5a74d-bea4-4f22-882c-820d36b31ca3_1344x556.png)

*Basically the same dark headline over and over again. Everyone’s reading the MIT study as some sort of nail in the coffin of AI projects everywhere. But no one is digging under the headlines.*

*I couldn’t find anything digging deeper into **why****the AI projects in the study worked or didn’t, and no one at all asking if that actually connected with the real world experience of builders.*

*You know, the people who actually build those AI projects we all talk about? Engineers. Vibe coders. AI enthusiasts from all backgrounds. You!*

*MIT didn’t bother to talk to them. They just interviewed 150 execs and called it good. And that right there is exactly why the study failed. It’s why the lessons learned felt generic. And somewhat contradictory, like they were out of touch with how AI projects are actually implemented on the ground. Because they were!*

*So I dug deeper. I acutally analyzed the report in depth, I pulled out the report’s insights, and I cross-checked every one against how I’ve actually seen AI play out in the real world, the world of builders.*

*And I realized that we need a builder’s playbook that actually tracks the real world problems and real world success patterns. We need a playbook with teeth that shows builders how to go from playing hero on individual teams to building AI systems that actually work.*

*And that’s what this is. A deep dive into how AI projects actually work, with actionable build principles you can apply tomorrow.*

*Fair warning: if you're looking for "10 tips to AI success" or "why executives should embrace AI," you're in the wrong place. This is about the nitty-gritty of making AI work when everyone around you is either panicking about the bubble or drunk on hype.*

*Let's dig in.*


# The 95% AI Failure Rate is Actually Good News (If You're a Builder)

Everyone's sharing that MIT study about 95% of enterprise AI failing. I spent six hours reading it, plus every rebuttal, critique, and LinkedIn hot take. Then I spent another six hours digging through real implementation stories from Spotify, IBM, Atlassian, and a dozen other companies.

Here's what I learned: MIT got the failure rate right but the reasons completely wrong.

They interviewed 150 executives about their AI initiatives. Executives! That's like asking hospital administrators why surgeries fail without talking to a single surgeon. Of course they missed what actually matters.

The real story isn't in boardrooms. It's in the shadow AI workflows your accounting team secretly shares. It's in the confidence scores that made lawyers suddenly trust AI drafting. It's in the RAG system that went from useless to essential because someone actually tracked what led to closed deals.

I've watched this pattern too many times now. Company announces AI initiative with fanfare. Six months later, it's dead. Meanwhile, three floors down, someone's ChatGPT workflow is quietly saving their team 10 hours a week. The disconnect is almost comedic.

So I did what the MIT researchers didn't—I looked at what builders actually built. Not the PowerPoints, not the vendor contracts, but the systems that stuck. The patterns are remarkably consistent. And they have nothing to do with whether you "buy or build" (MIT's big conclusion) and everything to do with whether you understand how AI systems actually take root in organizations.

I'm going to save you those hours of research and show you the five technical principles that separate the 5% who succeed from everyone else. Not executive frameworks. Not vendor pitches. The actual architectural patterns that determine whether your AI implementation becomes essential infrastructure or another dead pilot.


## What MIT Measured (And Why It's Wrong)

The study made four critical errors that explain why their conclusions don't match what I see in actual implementations:

**First**, they only measured six-month P&L impact. I've never seen a meaningful AI system deliver ROI that fast. The successful implementations I know took 12-18 months to hit their stride. Six months is barely enough time to get past the "wow, ChatGPT can write emails" phase.

**Second**, they only interviewed C-suite executives. These are people who see vendor contracts and pilot dashboards, not the guerrilla ChatGPT workflow that's actually saving the sales team four hours a week. The gap between what executives think is happening with AI and what's actually happening is astronomical.

**Third**, they pushed a false "buy versus build" binary. Every successful implementation I've seen is hybrid—organizations need both vendor dependability and a willingness to build to succeed. They leverage OpenAI's models but build their own context management. Pure vendor solutions fail. Pure custom builds fail. Reality lives in between.

**Fourth**, they correctly identified that workflow integration matters but offered zero guidance on how to actually do it. "AI should adapt to enterprise workflows" is about as useful as saying "food should taste good." True, but how?

---


## Quick Self-Assessment: Are You in the 5% or 95%?

Yes, we’re going to do this without revenue! Not because revenue doesn’t matter, but because revenue isn’t a leading indicator for builders.

Answer honestly:

**☐ Do you instrument a wide suite of AI leading indicators, not just usage numbers?**
**☐ Have you done a shadow AI audit in the last 60 days?**
**☐ Can your AI system get better without a full retrain?**
**☐ Do users voluntarily adopt your tool (no mandates)?**
**☐ Can you explain which AI workflows really matter to a 12 year old?**
**☐ Is your AI system so accurate and quick that stakeholders assume it just works?**

**Scoring:**
5-6 Yes: You're in the 5%
3-4 Yes: You're close—focus on the gaps
0-2 Yes: You're building theater, not infrastructure

*It’s ok, most projects start out at at 0-2. Want to see how to actually build systems that work? Read on…*

---


## The Five Principles That Actually Drive AI Success

While executives debate vendor contracts, builders keep discovering the same patterns independently. I see people stumbling into these principles over and over, usually after their third failed pilot. Here are the five technical patterns that separate the 5% from the 95%:


### Principle 1: Hybrid Architectures Are Mandatory

Forget the buy versus build debate. Every successful AI implementation I've seen is hybrid. You're not choosing between Microsoft's Copilot and rolling your own. You're using Anthropic's models with your own orchestration layer. You're combining OpenAI for creative tasks with a fine-tuned Llama for structured data extraction.

The companies succeeding treat AI vendors like AWS—powerful infrastructure that needs careful integration, not magic solutions. They recognize that even when you "buy," you're buying work. There's no such thing as a plug-and-play AI solution that actually delivers value.

Spotify's engineering team learned this the hard way. Their first attempt was pure vendor solution. Failed. Second attempt was pure custom build. Also failed. Their third attempt—documented in their engineering blog—combined best-in-class models with custom workflow logic. That's when developer productivity jumped 26%.

The key insight: you need the power of frontier models but the control of custom logic. You can't have one without the other and succeed.


### Principle 2: Build Learning Systems, Not Static Deployments

The difference between a POC and production isn't scale—it's whether the system gets better over time. This means three specific things:

**Feedback loops:** Every interaction should make the next interaction better. When a user corrects an output, that correction feeds back into the system. When a draft leads to a closed deal, that pattern gets reinforced.

**Retraining pipelines:** Not full model retraining (that's expensive and usually unnecessary), but continuous fine-tuning of prompts and context based on actual usage patterns. The system that worked in January won't work in June without updates.

**Context persistence:** The system needs memory across sessions. That chatbot that answers HR questions? Useless. The one that remembers what confused people last month and preemptively clarifies? Essential.

I watched a sales team implement this. Their first RAG system was static—it pulled from their knowledge base but never evolved. Six months later, it was giving the same outdated answers. Their second attempt logged every question, tracked which answers led to closed deals, and continuously refined its responses. New sales reps were performing like three-year veterans within weeks. That's a learning system.


### Principle 3: Intelligent Friction Builds Trust

Everyone thinks AI should be frictionless. Nope. MIT got this one right, actually. The implementations that stick have deliberate friction in smart places. Here's what intelligent friction actually looks like:

**Confidence thresholds:** Show users when the model is guessing. McGuireWoods and LexisNexis proved this with their legal AI—color-coding contract clauses by confidence (green/yellow/red) increased adoption from 25% to 72% in three months. Lawyers loved knowing exactly where to focus their attention.

**Human review gates:** Not everything needs human review, but high-stakes decisions do. The trick is making these gates feel empowering, not insulting. Show users why something triggered review. Let them adjust thresholds. Give them override authority with audit trails.

**Graceful degradation:** When the model operates outside its training distribution, it should say so. "I haven't seen this pattern before, here's my best guess but please verify" beats confidently wrong every time.

IBM's research found that companies with intelligent friction had 60% lower error rates and, counterintuitively, 3x higher user satisfaction. Users trust systems that acknowledge their limitations.


### Principle 4: Instrumentation Provides Leading Indicators

Executives wait six months to check P&L. Builders who succeed track technical metrics daily that predict business outcomes months in advance. Here's what actually matters:

**Accuracy by category:** Not overall accuracy—accuracy per use case. Your contract review might be 95% accurate while your compliance checks are 60%. You need to know.

**Latency percentiles:** Not average latency—p50, p95, and p99 if you’re operating at real scale. Treat it like serving streaming video.

**Override rates:** The golden metric. When you let the user override, and override rates drop from 60% to 20%, your system is learning. When override rates spike, well that’s not great news and you should probably dig into the pipeline to figure out what’s going on.

**Error rates and patterns:** Not just frequency but taxonomy. Are errors random or systematic? Are they clustered around specific inputs? This tells you whether to retrain or rebuild.

Look at [this sample dashboard I knocked together in Claude](https://claude.ai/public/artifacts/43a12d89-921d-4421-b112-b55921a49be7). Notice what's missing? Vanity metrics. Notice what's there? Useful metrics you can drive a technical business against. Stuff like model accuracy rates. Override rates. Response latency. When done right over time, those add up to ROI.

[![](https://substackcdn.com/image/fetch/$s_!Dc6E!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb2e0e971-70e0-437d-9831-c10ce5fd2f77_2428x1558.png)](https://substackcdn.com/image/fetch/$s_!Dc6E!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb2e0e971-70e0-437d-9831-c10ce5fd2f77_2428x1558.png)

The lesson? Measure what you can drive.


### Principle 5: Shadow AI Mining Uncovers What Actually Works

Here's the pattern nobody in the MIT study mentioned: the best AI implementations don't start in boardrooms. They start when someone builds a GPT that actually works and secretly shares it with their team.

Every organization has shadow AI right now. Someone in accounting has a Claude prompt that reconciles expenses perfectly. The marketing team passes around a Perplexity workflow that beats your official research process. Customer success has a janky but effective chatbot they built in two hours that outperforms the vendor solution you paid $50k for.

Your job as a builder isn't to shut this down—it's to mine it for gold. Shadow AI is user research you didn't have to conduct. It's proof of concept with actual validation. It's your roadmap to the 5% that succeed.

Reco.ai's 400-day study found the average enterprise has 17 different shadow AI workflows in active use. The companies that succeeded didn't fight this—they formalized it. One B2B SaaS company turned their top two shadow workflows into native features and saw 3x adoption versus their vendor pilot.

The process is simple: Survey. Document. Systematize. Scale. But you have to be willing to admit that your users might have already solved the problem better than your official solution.


## What This Looks Like in Practice

The examples I referenced, let’s dive a bit deeper to get the details.

**How Spotify Built Confidence Scoring for GenAI**

Spotify Engineering published a detailed case study on how they solved the trust problem in their GenAI applications. Their developers were spending weeks prototyping features without clear paths to production.

Their solution incorporated all five principles: hybrid architecture (combining Copilot with custom logic), learning systems (weekly retraining based on merged PRs), intelligent friction (confidence scores on suggestions), instrumentation (tracking acceptance rates), and shadow AI formalization (building on workflows developers already created).

According to their published metrics: developer productivity rose 26%, time from prototype to merge fell 45%, and code quality improved 30%.

**IBM's Study: Shadow AI Surge in Canadian Enterprises**

IBM Research released a study in September 2025 showing that Canadian workers are outpacing their employers in AI adoption through shadow AI. They found employees were 35% more likely to use unauthorized AI tools than official company solutions.

The key finding: organizations that conducted shadow AI audits and formalized the top workflows saw 3x higher adoption rates than those pushing vendor solutions. One bank discovered a compliance officer using custom GPT prompts for AML detection—when they built this into a secure workflow with proper instrumentation and confidence scoring, review throughput increased 4x.

**McGuireWoods and LexisNexis: The Legal Trust Journey**

LexisNexis published research with McGuireWoods showing how confidence scoring transformed legal AI adoption. They started with a standard RAG system—25% adoption after months of pushing.

Then they added intelligent friction: color-coded confidence scores on every clause. They instrumented everything, tracking which sections lawyers revised most. They built learning loops, retraining weekly on revision patterns. Trust jumped to 72% in three months. Review cycles dropped 30%.

**Atlassian's Documentation Revolution with Evidently AI**

Evidently AI documented how Atlassian solved their documentation lag problem using all five principles. They built a hybrid system (RAG plus custom update detection), created learning loops (the system learned from writer edits), added intelligent friction (flagged low-confidence updates), instrumented everything (tracking doc accuracy by product area), and formalized shadow workflows (writers were already using ChatGPT for summaries).

Result: Documentation lag shrank from two sprints to one day. User-reported errors dropped 80%.


## The Missing Skills to Become an AI Leader

If you want to translate these principles into organizational impact, you can actually pull these principles into leadership skills you can practice today.

**Shadow AI detective work:** Learn to identify and document guerrilla workflows. Run surveys. Watch Slack. Look for screenshots of ChatGPT. This is your goldmine.

**Friction design:** Engineer guardrails that build trust without destroying usability. Know when to surface confidence scores, where to put human review gates, how to make limitations visible without creating alarm.

**Learning system architecture:** Design systems that improve with each interaction. Capture feedback, persist context, create improvement loops that don't require ML expertise to maintain.

**Technical health monitoring:** Track metrics that predict success before ROI appears. Explain why a 15% drop in override rate means you'll hit targets in three months.

**Context translation at scale:** Turn your prompt expertise into templates others can use. Build libraries that encode best practices without requiring everyone to become prompt engineers.

And the good news is that by leaning in on these leadership principles you’re materially increasing the odds the business will actually build AI systems that matter, that have teeth, that deliver real ROI. That’s how you beat the odds.


## Ideas to get started

The MIT study says 95% fail. Fine. Here's how you join the 5% based on your role:

**Product Managers:** Run a shadow AI survey this week using the [Shadow AI Survey Template](https://docs.google.com/document/d/1T_JR6t92yepYdkDVGQjivW5GTviiIb1jfj-8xx8rLOM/edit?usp=sharing). Document the top workflows exactly. Build native versions. Watch your metrics explode.

**Engineers:** Start instrumenting everything. Use the [Builder's Success Checklist](https://docs.google.com/document/d/1T4vCnybQltSU5tSTy68TpzHbFnlYPrkWu7sm0h0ZKOg/edit?usp=sharing) to track the right metrics. When something breaks, you'll know before users complain.

**Solo Founders:** Pick one narrow workflow and nail it. Implement all five principles on that one workflow. You can expand later.

**Designers:** Make AI's limitations visible without creating fear. Design confidence indicators that help users trust appropriately.

**Team Leads:** Surface and celebrate shadow AI. Turn guerrilla success into official infrastructure.

You get the idea. The point is your role doesn’t limit you here. Your willingness to jump in and go beyond being a super-prompter is the key skill to get started, and I’m giving you ideas about how to turn that willingness into concrete action here.


## Yep, Don’t Panic

I’ve said it before! When the headlines are full of doom and gloom, builders have opportunities.

While executives panic about ROI and vendors push magic solutions, you know the five principles that actually work. You know hybrid architectures beat pure approaches. You know learning systems outperform static deployments. You know intelligent friction builds trust. You know instrumentation predicts success. You know shadow AI reveals what to build.

You don’t have to build one-off AI projects, and you don’t have to wait for your leaders to change to start influencing the business. Start engineering AI systems that learn, adapt, and deliver compound value. You have advantages the MIT study didn't even consider. Use them.

The next time someone shares that "95% fail" headline, smile. You know something they don't. You know the five principles that put you in the 5%.

> PS. Want to go farther? I built a couple of cool worksheets for you to dive into to make life easier. Grab the [Shadow AI Survey](https://docs.google.com/document/d/1T_JR6t92yepYdkDVGQjivW5GTviiIb1jfj-8xx8rLOM/edit?usp=sharing) and

[![](https://substackcdn.com/image/fetch/$s_!nJKq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F909d3b4c-b94d-4f6a-aa6b-05251309a155_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!nJKq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F909d3b4c-b94d-4f6a-aa6b-05251309a155_1024x1024.png)


### Sources

**Spotify Engineering GenAI Case Study:**
<https://engineering.atspotify.com/2024/12/building-confidence-a-case-study-in-how-to-create-confidence-scores-for-genai-applications>

**IBM Shadow AI Research Study:**
<https://canada.newsroom.ibm.com/2025-09-03-IBM-R-Study-Shadow-AI-Use-Surges-as-Canadian-Workers-Outpace-Employers-in-AI-Adoption>

**LexisNexis Legal AI Trust Research:**
<https://www.lexisnexis.com/community/insights/legal/b/thought-leadership/posts/trust-me-i-m-a-legal-ai-can-the-legal-profession-close-the-trust-gap-with-gen-ai>

**Atlassian Documentation Case Study (Evidently AI):**
<https://www.evidentlyai.com/blog/rag-examples>

**Reco.ai Shadow AI Study:**
<https://www.reco.ai/blog/new-study-reveals-400-days-of-hidden-ai-tool-usage-across-enterprises-creating-mounting-data-exposure>
