---
title: "I’ve reviewed 20+ enterprise AI builds this year—they all skip this conversation + 7 prompts that force it before anyone writes code"
author: "Nate Jones"
published: 2025-12-16
url: https://natesnewsletter.substack.com/p/ive-reviewed-20-enterprise-ai-builds
audience: everyone
scraped_at: 2026-01-05 19:09:56
---

*A few months ago I was planning a family trip—a reunion we’d been looking forward to for a while. I asked Claude to help me research logistics. Flights, hotels near the venue, restaurants that could handle a big group. The response was detailed and confident. It recommended specific restaurants by name, mentioned their capacity for large parties, even noted which ones had outdoor seating.*

*I almost booked based on those recommendations. Then I checked. Two of the restaurants didn’t exist. One had closed years ago. The “outdoor patio” at another was a fiction. The AI had hallucinated details that sounded exactly like real details, and I’d been about to make reservations at places that weren’t there.*

*A week later, different context, same problem. My dishwasher was leaking. I looked up the model number, asked for help diagnosing the issue, got a confident explanation about replacing a specific gasket. Part number included. Installation steps. The works. Except when I searched for that part number, nothing came up. The gasket it described didn’t exist for my model. The AI had invented a plausible-sounding repair for a part that wasn’t real.*

*These weren’t high-stakes situations. Nobody got hurt. I caught the errors before they cost me much. But I keep thinking about how easily I almost didn’t catch them. The responses were fluent. They had the shape of expertise. They sounded like someone who knew what they were talking about.*

*How would I have known they were wrong if I hadn’t checked?*

*That question is the one I keep coming back to. We’re living through a moment where AI can generate remarkably confident, helpful-sounding responses to almost any question—travel planning, home repair, medical concerns, financial decisions, educational support. And most of us have no systematic way to know when those responses are actually correct.*

*I don’t mean “correct” in some philosophical sense. I mean something practical: does the output do the job you needed it to do, without leading you somewhere you don’t want to go?*

*That question turns out to be harder than it looks.*

*H**ere’s what’s inside:***

- ***Why this matters for your daily prompts, not just enterprise systems**: I’ll start with the personal stakes. When you ask an AI for help planning a trip, fixing an appliance, understanding medical results, or supporting your kid’s homework, you need some way to know if the answer is actually helping you. I’ll break down what correctness looks like at the prompt level, with examples you can steal.*
- ***The hidden failure mode: moving goalposts**: Most teams—and most individuals—redefine what “good” means without noticing. Week one, a plausible answer feels like success. A few weeks later, you need it to match specific numbers. A few weeks after that, you need it to never say anything risky. Those aren’t tweaks. Those are different products. I’ll show you how to catch yourself before you end up blaming the model for your own shifting standards.*
- ***Why we stay vague on purpose (and why AI exposes it)**: Vagueness is social lubricant. It keeps options open and avoids conflict. AI systems don’t tolerate it. I’ll explain why the discomfort you feel trying to configure AI is actually the system surfacing trade-offs you’ve been avoiding.*
- ***A working definition you can actually use**: Correctness is the set of claims your system is allowed to make, the evidence required for each claim, and the penalties for being wrong versus staying silent. I’ll unpack each piece and show what it looks like in practice.*

***Plus, seven prompts that force the conversation before you build.***

- ***The Correctness Discovery Prompt**: Walks you through six questions that define what “correct” means for any task, from planning a family trip to building an enterprise dashboard.*
- ***The Tradeoff Forcer:** Makes you choose between competing values that can’t all be maximized. Boldness or caution? Completeness or speed? You can’t have both at maximum. This prompt makes you commit.*
- ***The Vague Requirements Translator:** When someone says “make it more accurate” or “reduce hallucinations,” this decomposes the vagueness into observable, testable behaviors.*
- ***The Prompt Specification Audit:** Diagnoses why an existing prompt produces inconsistent results by checking what’s defined and what’s been left to chance.*
- ***The Correctness Pre-Mortem:** Before you build, anticipate the failure modes that would otherwise surprise you in production.*
- ***The Eval Design Prompt:** Builds the measurement system: golden sets, metrics, test cases that actually catch failures.*
- ***The Production Monitoring Setup:** For live systems, catches the correctness failures that your test cases missed.*

*This isn’t really about prompts. It’s about developing the skill of being specific about what you want—and honest about what you’ll tolerate when you don’t get it perfectly. That skill turns out to be the thing that separates people who get genuine value from AI in 2026 from people who keep cycling through frustration. Let’s dig in.*


## [Grab the Prompts](https://www.notion.so/product-templates/The-Correctness-Contract-Collection-2cb5a2ccb52680eaa05cc91a812f1bbc?source=copy_link)

After watching teams cycle through this failure pattern—building elaborate systems without defining what success means, discovering requirements through production failures rather than upfront specification—I wrote a set of prompts that force the conversation before anyone writes code.

They’re not magic. They’re structured questions. Their value is in making you answer things you’d otherwise avoid.

There are seven of them, and they follow a sequence: define what correct means, choose between tradeoffs that can’t all be maximized, translate vague requirements into testable criteria, audit existing prompts for specification gaps, run a pre-mortem on failure modes, design the evaluation system, and set up monitoring for production.

The first one—the Correctness Discovery prompt—is the foundation. It walks you through six questions that define what “correct” means for your specific task. Who uses this output, and what decision will they make based on it? What would make this output useless? What would make it dangerous? What should the AI do when it’s uncertain? What’s worse—a confident wrong answer or a refusal to answer? How would you check whether the output is correct?

The Tradeoff Forcer makes you choose. Boldness or caution—pick one as the priority. Completeness or speed. Precision or coverage. You can’t have everything at once. The prompt forces you to commit, which is the thing most people avoid.

The Vague Requirements Translator handles the common situation where a stakeholder says something like “make it more accurate” or “reduce hallucinations.” Those phrases sound clear. They aren’t. The prompt decomposes them into specific, observable behaviors and surfaces the hidden tradeoffs.

The Prompt Specification Audit is for when you have an existing prompt that produces inconsistent results. It diagnoses the gaps—what’s defined and what’s been left to chance.

The Correctness Pre-Mortem is for before you build. It walks through failure scenarios: what could “wrong” mean here, what requirements might you discover too late, what would you not want an executive to ask?

The Eval Design prompt builds the measurement system. What categories of inputs must the system handle? What test cases catch the likely failure modes? What metrics actually tell you if the system is working?

The Production Monitoring Setup is for after you launch. What signals should you log? What thresholds trigger investigation? How do production failures become new test cases?

All seven are in the download, with worked examples. I’ve used them with enterprise teams. The most common reaction is some version of “I wish we’d done this earlier.”


## **The Personal Stakes—Why Care About Good?**

Let me start with the situations where getting this wrong actually hurts.

My son needed help with algebra. The explanations ChatGPT provided were patient, clear, nicely formatted. They walked through the steps in a way that seemed pedagogically sound. But some of them were subtly wrong—not obviously wrong, but wrong in a way that taught an incorrect mental model. The kind of thing where you don’t realize the foundation is broken until you try to build on it later.

A friend of mine was preparing for a job interview at a company he really wanted to work for. He used AI to research the company, prepare answers to likely questions, draft follow-up emails. Most of it was helpful. But the AI had scraped outdated information—turns out it was pulling from old LinkedIn data that didn’t reflect a recent strategy pivot. He built his entire interview narrative around a direction the company had already moved away from. He didn’t get the job. Would he have otherwise? Who knows. But he walked in telling a story that didn’t match reality, and he had no way to catch that before it mattered.

Or take the medical questions we all ask. Something feels off, you describe symptoms to an AI, you get a response that sounds informed and thorough. Sometimes you follow up with a doctor. Sometimes—if you’re honest with yourself—you don’t. The AI’s answer was reassuring, or the issue seemed minor, or you didn’t want to deal with scheduling an appointment. But you have no real way of knowing whether that reassurance was warranted.

I’m not saying stop using AI for these things. I use it for all of them. But I’ve started asking myself a question I didn’t used to ask: How would I know if this was wrong?

That’s what this piece is about. The question applies everywhere—from personal ChatGPT use to sophisticated enterprise systems. The failure mode is the same. The solution is the same. We need to get better at defining what “correct” means before we trust outputs that merely sound correct.


## What “Correct” Actually Means (And Why It’s Not as Obvious as You Might Think)

Here’s something that tripped me up for a while: I assumed “correct” was a simple concept. The answer is right or it’s wrong. What’s complicated about that?

Quite a lot, it turns out.

In traditional software, we can pretend correctness is simple because the program either passes tests or it doesn’t. Binary. The function returns the expected value or it throws an error. We write unit tests. We automate verification. We know when we’re done.

AI doesn’t work that way.

When you ask Claude to summarize a quarterly report, there’s no single “correct” answer. There are many possible summaries, emphasizing different things, at different lengths, for different audiences, with different levels of detail. Some would be useful to you. Some wouldn’t. Most would be somewhere in between.

So “correct” in AI isn’t really about truth in some abstract sense. It’s about fit. Does this output actually do the job I needed it to do?

That question is harder than it sounds because the job usually involves competing requirements.

You want the answer to be truthful—but also complete. Sometimes those conflict. A complete answer might require caveats that muddy the core point.

You want the answer to be confident—but also appropriately uncertain. Too much hedging feels unhelpful. Too little hedging leads you astray when the AI doesn’t actually know.

You want speed—but also depth. You want citations—but also readability. You want the AI to always try to help—but also to know when it should refuse.

Most of us never think about these tradeoffs explicitly. We prompt and hope. Sometimes we get something useful. Sometimes we don’t. When we don’t, we might iterate, but we’re iterating without knowing what we’re iterating toward. We’re adjusting the prompt without having defined what would make the output correct.

This is why the same person can use the same model for months and never get consistent results. They’re not consistent about what they want. The goalposts move. What felt like a good answer last week doesn’t feel good enough this week. The shift happens without anyone noticing.


## An Example You Can Use Today

Let me make this concrete.

Say you ask Claude: “Write me a summary of this quarterly report.”

That’s a reasonable request. It’s also wildly underspecified. What kind of summary? For whom? At what length? Emphasizing what? With what level of detail on the numbers? Should it highlight risks or downplay them? Should it include recommendations or just describe what happened?

When you don’t specify, the model guesses. It picks a length based on the input. It picks an emphasis based on what seems statistically typical. It picks a tone based on patterns in its training data. Sometimes that guess happens to match what you wanted. Often it doesn’t.

Now compare this version:

“Write me a 3-paragraph executive summary for our CEO. Focus on revenue trends and customer acquisition costs. Include the specific Q3 versus Q2 comparison numbers. Flag anything that might come up in the board meeting as a surprise. If you’re uncertain about any number, say so explicitly—I’d rather know you’re not sure than get a confident wrong answer.”

Notice what changed.

You specified the format: three paragraphs, executive summary. You specified the audience: CEO. You specified the focus: revenue trends, customer acquisition costs. You specified the evidence requirements: actual Q3 versus Q2 numbers. You specified the use case: board meeting, flag surprises. And—this is the part most people miss—you specified what to do with uncertainty: be explicit about it rather than papering over it with confident-sounding prose.

Now you can evaluate the output. Did it give you three paragraphs? Did it focus on the things you asked for? Did it include the comparison? Did it flag surprises? Did it acknowledge uncertainty where it existed?

You have something checkable. That’s what correctness at the prompt level looks like.


## Why This Isn’t Extra Work (No Really)

I can hear the objection. “That’s so much more effort. I just want to ask a quick question and get an answer.”

Fair. Here’s the thing, though: you’re going to do the specification work either way.

Either you specify upfront and get usable output on the first or second try, or you leave it vague and spend five iterations getting to something usable—with each iteration being a form of post-hoc specification. “No, shorter than that.” “Actually, more focus on the numbers.” “Wait, I meant for a technical audience.”

Those refinements are you discovering what you wanted through trial and error. The information was always necessary. The question is just whether you surface it before the first response or after the fourth.

For any task where the output actually matters—something you’re going to send to someone else, use for a decision, or rely on for something important—upfront specification tends to save time. The reason it feels like more work is that the effort is concentrated and conscious rather than distributed and unconscious. But the total effort is often less.


## The Hidden Failure Mode: Moving Goalposts

There’s a pattern I’ve watched play out over and over again in enterprise AI projects. The timeline varies. The shape is consistent.

Early on, the team is excited. They’ve built a demo. It answers questions, pulls from multiple data sources, the UI looks good. They show it to stakeholders. Everyone nods. At this point, “correct” means the answer sounds plausible and saves time. That’s the unstated definition. Nobody writes it down.

A few weeks later, someone in finance notices a discrepancy. A number in the AI’s response doesn’t match their system. Now there’s a new requirement: correct means matching the finance numbers. But nobody updates the spec. It’s just understood.

A few weeks after that, the CFO wants more context. Not just what the numbers are—what they mean. Now correct means matching the numbers and including narrative context from policy documents. More scope. Still not written down.

Then legal gets involved. Someone said something in a demo that made the lawyers nervous. Now correct means never saying anything risky in front of leadership. But what counts as risky? That’s not defined.

Then the CEO is frustrated. The responses are too hedged, too cautious. She wants confident answers, not endless caveats. Now correct means answering boldly, fast, no waffling.

Do you see what happened?

The team has been building against a target that keeps moving. They never defined correctness at the start, so they couldn’t notice they were redefining it every few weeks. Each change felt like a minor adjustment. In aggregate, they’ve been asked to build several different products without anyone acknowledging the shifts.

The engineers are confused. The stakeholders are frustrated. Everyone blames the AI for being unreliable.

But the AI wasn’t unreliable. The humans were. They kept changing what they wanted without admitting—even to themselves—that they were changing it.

This happens in personal use too. You ask for help with something. The first response is fine, you’re satisfied. A week later you ask for something similar, get a similar response, and now it feels inadequate. You’re annoyed at the AI. But the AI didn’t get worse. Your standards shifted, and you didn’t notice.

If you want consistent value from AI, you need to catch yourself when this happens. Name what you want. Notice when it changes. Update your prompts accordingly. Otherwise you’re just going to keep being disappointed by systems that are giving you exactly what you asked for—you just don’t remember what you asked for.


## Why We Stay Vague (And Why AI Exposes It)

This is the part that’s awkward to talk about, because it’s not a technology problem. It’s a human problem.

Vagueness is useful. It’s how we navigate complex social situations without constant conflict. When you’re in a meeting and everyone “agrees” on a direction, you might all have slightly different understandings of what that direction means. But the ambiguity keeps things moving. The gaps might never need to be resolved. Or if they do, they get resolved later, in context, when there’s more information. This is adaptive behavior. It’s not a bug.

At Amazon, we called this “weasel words.” You’d say “a lot” instead of a number. You’d say “significant impact” without defining significant. You could commit without really committing. It was a survival strategy, and honestly, it often worked.

The problem is that AI systems don’t tolerate weasel words.

If you’re building an AI system, you have to answer questions like: Should it be bold or cautious? If you say “both,” you haven’t answered. Should it always try to help, or should it refuse when uncertain? If you say “use good judgment,” you haven’t answered. Should the output be optimized for speed or thoroughness? You can’t pick both at maximum.

These are real tradeoffs with real consequences. In human organizations, we often avoid making these choices by leaving them ambiguous and letting whoever’s downstream figure it out. But AI systems are downstream, and they don’t figure it out the way humans do. They guess. And when their guess doesn’t match what you wanted—which it often won’t, because you never said what you wanted—you experience that as “the AI doesn’t work.”

Here’s an uncomfortable truth: when you find yourself frustrated that an AI system isn’t giving you what you want, the first question to ask is whether you’ve actually specified what you want. Not in your head. In the prompt, in the configuration, in the system design. Have you made the hard choices?

The frustration you feel trying to get AI to work the way you want? That’s often the system surfacing trade-offs you’ve been avoiding. It’s asking you questions that humans around you were polite enough not to ask.


## Towards A Working Definition of Good

Let me give you something concrete.

Here’s how I think about correctness: it’s the set of claims your system is allowed to make, the evidence required for each claim, and the penalties for being wrong versus staying silent.

Three parts. Let me unpack each one.

**The set of claims your system is allowed to make.** This is about boundaries. What’s in scope and what’s out? If you’re building a customer service bot, maybe it can answer questions about product features and order status, but it shouldn’t give legal advice or make promises about future products. If you’re using ChatGPT for travel planning, maybe you’re okay with it suggesting restaurants—but you’ve learned (as I did) that you need to verify they actually exist before you make reservations. Defining the allowed claims is how you prevent the system from wandering into territory where it’s likely to be wrong in ways that hurt.

**The evidence required for each claim.** Different claims need different levels of support. If I ask an AI for the capital of France, it can just answer—that’s established knowledge. If I ask for my company’s Q3 revenue, it better be pulling from an actual source, not confabulating. If I ask for a medical recommendation, it should probably be citing guidelines or studies, not just generating plausible-sounding advice. The evidence requirement depends on the stakes and on what kind of error you can tolerate.

**The penalties for being wrong versus staying silent.** This is the piece most people miss.

In some contexts, wrong is much worse than no answer. If an AI system confidently tells your CEO the wrong revenue number in a board meeting, that’s not just an error—it’s a trust-destroying event. In that context, the system should be biased toward saying “I’m not confident about this number, let me check” rather than guessing.

In other contexts, no answer is basically useless. If you’re brainstorming ideas, you don’t want the AI refusing to engage because it’s not certain. You want it to generate options, even speculative ones. Silence isn’t helpful here.

Most systems—and most prompts—never specify which world they’re in. The AI doesn’t know whether you’d rather have a confident guess or an honest “I don’t know.” So it defaults to whatever its training suggests, which is usually somewhere in between, which is usually not quite right for your specific situation.


## What This Looks Like in Enterprise Systems

The same dynamics that apply to personal prompts apply—in amplified form—to enterprise AI systems.

I sat in a conference room recently watching a very expensive AI demo fall apart in real time. The system was impressive—multi-agent orchestration, beautiful UI, RAG pipeline pulling from six data sources. The product team had been building for four months. A VP of Finance asked one question: “When this shows me a revenue number, how do I know it’s right?”

Silence.

Then: “Well, it pulls from Salesforce and NetSuite and—”

“That’s not what I asked. What does ‘right’ mean? If it’s off by 2%, do I care? If it’s off by 0.2%, do I care? If it can’t find the number, what does it show me? If two sources disagree, which one wins?”

More silence.

They’d built orchestration middleware, context layers, semantic chunking, the whole architecture—on top of a definition of correctness that didn’t exist. And the moment someone asked what “good” actually meant, the whole thing revealed itself as elaborate engineering built on an unnamed target.

Before you decide whether to use RAG or fine-tuning, before you pick a model, before you design the orchestration, you need to answer questions like:

When this system gives a revenue number, what source does it have to come from? Can it synthesize across sources, or does it need a single authoritative source? If sources conflict, what’s the hierarchy?

How precise do the numbers need to be? Is “approximately $2.3M” acceptable, or does it need to be “$2,312,847.23”? Under what circumstances?

What should the system do when it can’t find the information? Say “I don’t know”? Make a best guess? Redirect to a human? Refuse to engage?

Who’s the audience? An analyst who can evaluate the answer? An executive who’ll take it at face value?

These aren’t technical questions. They’re business questions with technical implications. The answers determine what the architecture needs to accomplish. Without them, you’re building something and hoping it fits a use case you never specified.


## **The Prompt-Level Version**

Everything I just said about enterprise systems applies to personal use. The scale is smaller but the structure is the same.

Think about a prompt you’ve used recently that didn’t give you what you wanted. Maybe you asked for help drafting an email and the tone was wrong. Maybe you asked for research on a topic and got surface-level fluff. Maybe you asked for feedback on your writing and got generic encouragement instead of useful critique.

In each case, ask yourself: did I actually specify what “correct” would look like?

For the email: did I say who it’s to, what our relationship is, what I’m trying to accomplish, what tone fits the situation?

For the research: did I say what level of depth I need, what kind of sources are credible, what I already know and don’t need repeated?

For the feedback: did I say what kind of critique I want, what’s already working that shouldn’t change, where I feel uncertain and want focused attention?

Usually the answer is no. We leave the important stuff implicit and hope the AI infers it. Sometimes it does. Often it doesn’t. And when it doesn’t, we experience that as the AI being bad, rather than our specification being incomplete.

I’m not saying this is entirely your fault. The AI could be smarter about asking clarifying questions. The interfaces could be better designed to elicit specifications. These are real product problems.

But we’re not waiting for them to be solved. We’re using the tools that exist today. And with today’s tools, the skill that makes the biggest difference is the ability to specify what you want clearly enough that the AI can actually give it to you.


### Where Correctness Lives

Here’s a concept that’s helped me think about this more clearly.

The question is: where does the ground truth live?

Sometimes ground truth lives in a structured, authoritative source. There’s a database with the real numbers. There’s an official policy document. There’s a canonical answer, and the AI’s job is to find it and present it accurately.

Sometimes ground truth lives in human judgment and interpretation. There’s no canonical answer. Different people might legitimately disagree. The AI is helping with synthesis, or presenting options, or structuring thought—but it’s not going to produce a single “correct” answer because a single correct answer doesn’t exist.

These are different situations that require different approaches.

When ground truth lives in a structured source, correctness means: did the AI find the right source, interpret it correctly, and present it without adding fabrications? The failure mode is hallucination—making up things that don’t exist in the source. Like my restaurants that didn’t exist, or my dishwasher gasket that was never manufactured.

When ground truth lives in human judgment, correctness means something else. It’s more like: did the AI help me think about this more clearly? Did it surface considerations I’d missed? Did it present the options fairly? Here the failure mode is less about factual errors and more about biased framing, missing perspectives, or false confidence in contested claims.

Most tasks are a mix. You’re asking about facts (ground truth in sources) and asking for interpretation (ground truth in judgment). The AI has to handle both, and it doesn’t always know which mode it’s in.

When you’re prompting, it helps to be explicit about which mode you want. “I need the actual figures from the report” is different from “help me think through what these figures might mean.” The AI behaves differently when it knows which one you’re asking for.


## The Painful Part: Measurement

If correctness matters—and I’ve been arguing it does—then eventually you have to ask: how do I actually measure it?

This is where things get uncomfortable, because measurement requires commitment. It requires saying, explicitly, what would count as success and what would count as failure. It requires being willing to discover that your system doesn’t work as well as you thought.

For enterprise systems, I think about three layers of evaluation.

First, a golden set. A curated collection of test cases with expected behavior. Real prompts, not synthetic ones. Edge cases that have actually caused problems. You run this set every time you change something—prompts, models, chunking logic, retrieval parameters. It catches regressions. It prevents the thing where you “improve” one behavior and quietly break three others.

Second, statistical discipline. If you’re comparing two approaches, you need enough test cases to know the difference is real, not noise. Not “I tried five examples and B felt better.” That’s not measurement. That’s vibes.

Third, production monitoring. Because users will do things you didn’t anticipate. Edge cases will appear that weren’t in your test set. You need to instrument, log, and review—especially for high-stakes outputs. The goal is a feedback loop that continuously improves your understanding of what’s working.

For personal use, the measurement is simpler but the principle is the same. Did the output actually help you do the thing you were trying to do? Not “was it impressive” or “was it fluent” but did it work?

If you’re using AI for travel planning, did the restaurants actually exist? Did the logistics hold up when you tried to book them?

If you’re using AI to help your kid with homework, did they learn the right thing? Not “did they get the homework done” but did they develop the correct understanding?

If you’re using AI to prepare for an interview, did you walk in better prepared than you would have been otherwise? Or did outdated information steer you wrong?

These are judgment calls, not metrics. But making the judgment explicitly—asking “did it actually work?”—is the start of being intentional about correctness rather than just accepting whatever sounds good.


## The Skill We’re All Developing

Let me pull this together.

The skill that determines whether you get genuine value from AI in 2026 isn’t knowing which model is newest, or how to jailbreak content filters, or even “prompt engineering” in the way people usually mean it.

It’s the ability to be specific about what you want.

That sounds simple. It isn’t. Being specific requires knowing what you want, which requires thinking clearly about what you’re trying to accomplish, which requires confronting tradeoffs you’d rather avoid.

Most of us resist this. We’d rather keep options open. We’d rather not commit. We’d rather let things stay vague because clarity forces choices.

But AI systems don’t tolerate vagueness the way humans do. They need instructions. When the instructions are unclear, they guess. When they guess wrong, we blame them—but the fault is often upstream, in our own failure to specify.

Here’s the thing that gives me hope: this is a learnable skill. You get better at it with practice. You develop an instinct for what needs to be specified and what can be left implicit. You learn to catch yourself when your standards shift. You build the habit of checking whether the output actually worked, not just whether it sounded good.

The people I know who get the most value from AI aren’t the ones with the cleverest prompts or the deepest technical understanding. They’re the ones who’ve developed the discipline of clarity. They know what they want before they ask. They notice when they don’t know and take the time to figure it out. They evaluate outputs against something concrete, not just vibes.

This isn’t just useful for AI. It’s useful for everything—managing people, commissioning work, setting goals, thinking clearly about what you’re trying to accomplish in any domain. AI just makes the skill more immediately valuable, because the feedback loop is so fast and the costs of unclear thinking are so immediate.


## What To Do Now

If you take one thing from this piece, let it be this: before you prompt, before you build, before you trust an AI output with anything that matters—ask yourself what “correct” would look like.

Not in some abstract sense. Concretely. For this specific task, with this specific audience, with these specific stakes.

What would make the output useless? What would make it dangerous? What should happen when the AI isn’t sure? How would I check if it’s right?

Answer those questions, and you’ve done more than most people ever do. You’ve moved from hoping the AI gives you what you want to specifying what you want.

The prompts in the download walk you through this systematically. The first one takes about ten minutes. By the end, you’ll have a one-paragraph correctness definition you can paste into future prompts. Try it on something that actually matters to you—a task where getting it wrong would have consequences.

And then notice what happens. Notice whether the output is more useful. Notice whether you’re less frustrated. Notice whether you can actually evaluate the result instead of just reacting to it.

That’s the skill. That’s what we’re all developing, whether we realize it or not. The AI keeps getting better at execution. Our job is to get better at direction.​​​​​​​​​​​​​​​​

[![](https://substackcdn.com/image/fetch/$s_!BoPh!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8b2c8cf4-b050-488c-9cab-f6ce5f8f0f38_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!BoPh!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8b2c8cf4-b050-488c-9cab-f6ce5f8f0f38_1024x1024.png)
