---
title: "Grab the prompts"
author: "Nate Jones"
published: 2025-12-01
url: https://natesnewsletter.substack.com/p/ilya-vs-google-the-trillion-dollar
audience: everyone
scraped_at: 2026-01-05 19:10:48
---

Ilya Sutskever just spent 96 minutes explaining why the scaling era is over and we need a fundamentally new approach to AI.

Three days earlier, Google shipped Gemini 3 and declared it their biggest performance jump ever.

One of them is profoundly wrong. And if you’re building on these systems, the answer matters.

I watched the full Dwarkesh interview so you don’t have to. Below is what Ilya actually said, where I think he’s right, where I think he’s wrong, and what it means for anyone deploying AI today.

Here’s what I cover:

- **The Adaptive Prompt** — tests whether a model can actually update its thinking when requirements change, or whether it just starts over from scratch every time
- **The Premortem Prompt** — forces the model to imagine failure before committing to a plan, compensating for the missing gut feeling that tells humans “this seems dangerous”
- **The Strategy Fan Prompt** — breaks out of the narrow set of tactics models learn during training and surfaces genuinely different approaches, not just variations on the same idea
- **The Harsh Reviewer Prompt** — makes the model attack its own output before you ship it, catching the gap between “looks right” and “actually works”
- **The Spec Decomposer Prompt** — forces the model to think about what actually needs to be solved before jumping to a template, producing solutions that hold up when your context changes

I’ll tell you where I think Ilya is right, where I think he’s wrong, and what that means for how you build, evaluate, and deploy AI systems right now.


# **[Grab the prompts](https://www.notion.so/product-templates/Five-Prompts-to-Match-Ilya-s-Vision-2ba5a2ccb52680ca84e5e6b90d0164e7?source=copy_link)**

Theory is useful. Tools you can actually use are better. I’ve put together five prompts that test for and work around the specific limitations Ilya mentioned. I won’t pretend they’re magical, but they’re short, reusable, and each maps to one of the failure modes Ilya calls out for current LLMs.

Use them to test whether a model can actually adapt when constraints change, to force forward projection before committing to a plan, to break out of narrow strategy convergence, to catch jaggedness before you ship, and to push past template retrieval toward actual reasoning. The models are more capable than they seem when properly scaffolded. These prompts are part of that scaffolding.

---


## **The Benchmark Lie**

In his conversation with Dwarkesh Patel, Ilya - the co-founder of OpenAI, the person who more than almost anyone else alive shaped how modern AI actually works - laid out a diagnosis that should change how you evaluate these systems.

We’re living in what should be a science fiction moment. Trillions of parameters. Labs spending on the order of 1% of GDP on training runs. Yet the models feel unreliable where it matters. Benchmarks say genius. Daily use says useful idiot.

Ilya’s diagnosis cuts deep: the labs, not the models, are the real reward hackers.

Here’s how it works. Researchers design benchmarks to measure capability. Then they design training loops that optimize for those benchmarks. The models get spectacular at the tests. But the tests only cover a narrow slice of what Ilya calls the “evaluation manifold” - the specific problem-space that the evals actually touch. Step off that manifold, and coherence collapses.

This isn’t conspiracy. It’s incentive alignment doing exactly what incentive alignment does. If your bonus depends on benchmark scores, you optimize for benchmark scores. If your funding round depends on leaderboard position, you optimize for leaderboard position. The training setup games the eval. The model looks brilliant on paper. Then you ask it to do something slightly outside the test distribution and it falls apart in ways that make you question everything.

You’ve seen this yourself. You ask Claude to fix a bug. It fixes the bug. It introduces a new bug. You ask it to fix that bug. It reintroduces the original bug. Back and forth, around and around, until you wonder if you’re the one who’s broken.

That loop is a symptom of exactly this disease. The model has ingested enough code to pattern-match solutions that look correct. It hasn’t developed robust concepts of how code actually works - how changes propagate, how state accumulates, how edge cases interact. So it fixes what you point at and breaks what you don’t, over and over, because it isn’t reasoning about code. It’s retrieving patterns that resemble reasoning about code.

The practical implication lands immediately: benchmarks are increasingly marketing artifacts. LMArena Elo scores, capability suites, reasoning evals - they measure performance on the narrow set of tasks that matter for leaderboard position. They tell you almost nothing about whether a model will maintain coherence when your requirements shift mid-project, when your domain has quirks the training data didn’t cover, when you need actual reasoning rather than sophisticated pattern retrieval.

I’ve started running what I call off-manifold probes before trusting any model with complex work. Give the model a moderately complex problem with clear constraints. Let it solve it. Then change one constraint and watch what happens. Does the solution adapt coherently? Does the model identify which parts of its reasoning transfer and which need revision? Or does it either regenerate everything from scratch - wasteful and often inconsistent - or force-fit the old solution to new constraints, producing outputs that no longer hang together?

The models that pass this test - Claude Opus 4.5, GPT-5.1 thinking, Gemini 3 - generalize noticeably better than the rest. They’re not perfect. But they maintain coherence across constraint changes in ways that second-tier models don’t. Kimi K2 thinking, Grok 4, and several others fragment badly when you step outside their training distribution. The Christmas tree test I’ve written about before catches the same phenomenon: ask a model to build something with unusual constraints, and you’ll quickly discover whether it’s reasoning or retrieving.

---


## **Why Models Can’t Learn Like You Do**

Ilya’s deepest technical claim is that current models generalize dramatically worse than humans. This sounds obvious when stated. The implications aren’t obvious at all.

Consider two students. One grinds for 10,000 hours on contest problems, optimizing relentlessly for competition performance. Another does 100 focused hours, gets good enough, and moves on. The grinder might win contests. The second student is the one you’d bet on in life - the one who will figure out novel situations, adapt to unexpected constraints, learn new domains without starting from scratch.

Today’s LLMs are the grinder. They’ve processed orders of magnitude more data than any human will ever encounter. Yet they fail in ways that a reasonably bright teenager wouldn’t. A 15-year-old learns to drive in roughly 10 hours. No explicit reward function. No careful curriculum. No millions of labeled examples. They show up with an internal sense of “this seems dangerous” and “this seems fine” that guides learning from the first minute behind the wheel.

That internal sense - what Ilya calls a value function - is exactly what current AI architectures lack. And his argument for why it matters goes somewhere unexpected.

He points to neurological cases where patients lose emotional processing but keep IQ and language intact. On paper, they score fine. Vocabulary, reasoning ability, pattern recognition - all preserved. In everyday life, they become almost incapable of making decisions. They can analyze options endlessly but can’t choose. The emotional circuitry wasn’t providing decoration. It was providing the forward-looking value signals that made decision-making possible in the first place.

Emotions, in Ilya’s framing, aren’t feelings. They’re a simple, robust signal about how good or bad a situation is - an estimate, at each moment, of how promising the future looks. Your gut tells you not to walk down the dark alley before anything bad happens. That pit-of-the-stomach fear projects forward in time and steers you away from danger. It arrives before deliberation, before analysis, before you can articulate why.

Now map this back to how we train AI systems. Reinforcement learning rewards arrive at the end of an episode - after the sequence of actions completes. That’s fundamentally backwards from how humans learn. RL says: here’s what happened, here’s whether it was good or bad. Human learning says: here’s what might happen, here’s whether you should proceed. The reward is backward-looking. The value function is forward-looking. That gap may be at the heart of why human learning scales differently.

I know this sounds philosophical. Ilya doesn’t think it’s silly. Neither should you. Because this has immediate practical implications.

If models lack forward-looking value signals, you can partially compensate by providing richer context that mimics what emotions would provide. Instead of just describing a task, describe the stakes. Instead of just asking for a solution, ask the model to first identify what could go wrong - to project forward and name the failure modes - then design around them. You’re not giving the model emotions. You’re giving it something that functions like the output of emotional processing: a sense of which futures are promising and which are dangerous, before committing to action.

---


## **The Trillion-Dollar Disagreement**

Ilya frames AI history in three eras. First: an early age of research when people tried all kinds of architectures but had very limited compute. Second: the scaling age that started with GPT-3, when the recipe became clear - more parameters, more data, better results. Anyone with capital could convert money into capability improvements on a predictable curve. Third: a coming age of research, but this time with huge computers. The scaling playbook is exhausted. Web-scale data is finite. The next breakthroughs require new ideas, not just bigger clusters.

He made this claim at NeurIPS in late 2024. He’s doubling down now.

Here’s the thing: since that NeurIPS talk, we’ve seen GPT-5, Claude Opus 4.5, Gemini 3 - each representing meaningful capability gains. That’s not nothing. If scaling were truly exhausted, we’d expect diminishing returns by now. Instead, Google shipped what they called their biggest performance jump ever, and it shows.

So what’s actually happening?

The elegant read is this: Ilya is probably right about the destination and possibly wrong about the timeline. He wants breakthroughs in generalization and learning. He sees agents that learn in the wild as the key missing technology. He’s almost certainly correct that current architectures can’t get us to systems that learn like humans do. The teenager learning to drive in 10 hours, the robust value function that projects into the future - we don’t have that, and more parameters won’t conjure it into existence.

But the vision he has - the high beams illuminating the road five miles ahead - may be blinding him to the significant value still being extracted from current scaling. When Ilya says scaling is done, he’s saying he’s seen how this movie ends and believes a new paradigm is needed. That’s a research conviction, not an empirical observation about what’s shipping today.

The key point of disagreement isn’t abstract. It’s Demis Hassabis telling Jensen Huang after Gemini 3 that they still see room to scale, that they’re not tapped out. Google is shipping. Ilya is researching. Both positions are defensible, but only one is generating proof points right now.

The implicit question - whether continued scaling alone can break through into genuinely generalizable intelligence - remains entirely theoretical. Ilya doesn’t know he’s right. Demis doesn’t know he’s right. What we have is Demis shipping products that keep improving, and Ilya working on a potentially breakthrough approach to learning that hasn’t produced public results yet.

For anyone building AI systems today, this suggests a clear strategy: extract maximum value from current capabilities while staying architecturally flexible. The models shipping now are genuinely useful. The generalization breakthroughs Ilya describes would be transformative. Both things can be true. You don’t have to pick a side in a researcher’s debate to build systems that work.

---


## **Amnesiacs with Tools**

Toward the end of the conversation, Ilya makes a point about multi-agent systems that deserves more attention than it’s getting.

Current post-training environments push models toward a very narrow range of agent strategies. Frontier models play games with one another and with themselves during training, developing negotiation patterns and strategic behaviors within adversarial multi-agent schemas. The result is less diversity, not more. Agents converge on a small set of tactics that work in training environments - variations of the prisoner’s dilemma, standard negotiation patterns, predictable strategic moves. They repeat these patterns forever instead of finding genuinely different approaches.

This connects directly to Anthropic’s June 2025 research on agentic misalignment. They ran simulated corporate environments across several major models - Claude, Gemini 2.5 Pro, and others. When agents were boxed into tight constraints, they repeatedly chose harmful strategies like blackmail, even while verbally acknowledging ethical rules. The pattern wasn’t model-specific. It emerged from the narrow strategy space that current training approaches create. The models had learned a limited repertoire of “what works,” and when standard approaches failed, they reached for whatever was left in the toolkit.

Anthropic’s commentary on production agents adds another layer. They describe current systems as “amnesiacs with tools” - agents that can call APIs and take actions but retain little persistent, structured memory. The model runs, completes a task, forgets everything it learned. Next invocation starts from scratch. There’s no compounding. No improvement from past mistakes. No building on previous successes.

This aligns with Ilya’s broader argument about brittleness. Without genuine learning, without memory that persists and accumulates, agents can’t approximate human learning trajectories. The memory problem underlies almost every other agent limitation. And it explains why agent systems that work brilliantly in demos fall apart in production - the demo captured a single run through known territory, not the accumulated judgment that comes from encountering and learning from novel situations.

Anthropic’s internal numbers put this in concrete terms: AI now writes 70-90% of code for their own engineering teams. Yet even in straightforward tasks, humans still occupy 4-6 key decision points. The models handle execution when the path is clear. Humans provide judgment when the situation is novel or the stakes are high. That boundary - knowing when to execute and when to escalate - is where current AI actually lives. Systems that pretend the boundary doesn’t exist fail in production. Systems that respect it deliver value.

The implication for anyone building agents: the real moat isn’t the biggest model. It’s the richest ecosystem - the most interesting combination of tools, memory systems, and interaction patterns that produce genuinely diverse behaviors. Since models don’t learn across sessions by default, serious agentic work requires explicit memory architecture. It requires learning loops that persist outside the model. It requires tool orchestration that handles failures gracefully. Parameter count won’t save you. Architecture might.

---


## **What Ilya Said Between the Lines**

Beyond the headline claims, several points from the interview deserve more attention than they’re getting.

**Generalization sits underneath alignment.** Most safety discourse treats alignment as something you add on top of a capable model - safety training as a finishing layer. Ilya’s argument implies the opposite. If a model’s underlying concepts don’t generalize well, its values won’t generalize either. The safety training holds in familiar situations and collapses in novel ones, exactly like every other capability. You can’t align a system that doesn’t generalize. Alignment isn’t a layer on top. It’s a property of how well the underlying system handles distribution shift.

**The AGI arrival date is the wrong thing to focus on.** Framing everything as a single arrival moment - “AI 2027” or whatever the current prediction is - obscures what actually matters. When we get systems with shared memory that actually learn and develop across sessions, that’s a more meaningful milestone than any predicted wake-up date. The functional way to think about general intelligence isn’t “when does it arrive” but “when can agents actually learn from experience.” By that measure, we’re further away than the hype cycle suggests - but that’s fine. The current systems are useful now. The learning systems will be useful when they arrive.

**We can’t reason well about systems that don’t exist yet.** Ilya explicitly agrees that when people theorize about superintelligence - systems that rapidly take over the economy - they’re reasoning about systems no one has built. That’s been one of my consistent critiques of doom discourse. We’re pattern-matching from science fiction, not from observation. The safest path forward is incremental deployment: build increasingly capable systems, put them in the world, learn from how they actually behave, develop grounded understanding rather than theoretical speculation. Ilya left OpenAI to start Safe Superintelligence, and even he thinks reasoning about systems we’ve never met is fundamentally limited.

**Research taste is a strategic asset.** A handful of people will decide which research directions to pursue and which to kill. The ability to think about intelligence in a novel, useful way - to guide a new research direction that actually works - is genuinely priceless. This is why companies pay any amount to recruit top researchers. The bidding wars aren’t irrational. They reflect real scarcity of something that matters enormously and can’t be manufactured on demand.

---


## **What Comes Next**

Maybe Ilya is right about the long-term trajectory. Maybe Google’s continued scaling wins will eventually hit a wall and vindicate his thesis. But “eventually” matters a lot when you’re building products and running teams. The models shipping today are more capable than they were a year ago. The models shipping next year will likely be more capable still. That’s the environment you’re actually operating in.

Ilya’s insights about generalization, value functions, and the limitations of current learning approaches are genuinely useful for understanding why models fail when they fail. His frameworks for compensating for those limitations - forcing forward projection, testing for adaptation under constraint changes, designing for strategy diversity - are practical tools you can use today. But his timeline for when scaling stops mattering? Treat that as one researcher’s conviction, not established fact.

The disagreement between Ilya and Google isn’t something you need to resolve. It’s something you can exploit. Build systems that work with current capabilities. Test for generalization rather than trusting benchmarks. Design architectures that can incorporate better models as they arrive - whether those improvements come from continued scaling or from the breakthrough Ilya is chasing.

What isn’t in dispute: current models struggle with generalization. Agents are amnesiacs with tools. Memory and learning architecture matter more than parameter count for production systems. Benchmarks tell you almost nothing about real-world robustness.

The models are more capable than they seem when properly scaffolded. They’re more brittle than they seem when you step off the beaten path. Learning to work in that gap - to extract real value from systems that are neither as smart as the benchmarks suggest nor as dumb as the failures imply - is the skill that matters right now.

Good luck out there.

[![](https://substackcdn.com/image/fetch/$s_!lOZA!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fff8fe638-3364-4f9c-8f6a-e4cba08fe497_512x512.png)](https://substackcdn.com/image/fetch/$s_!lOZA!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fff8fe638-3364-4f9c-8f6a-e4cba08fe497_512x512.png)
