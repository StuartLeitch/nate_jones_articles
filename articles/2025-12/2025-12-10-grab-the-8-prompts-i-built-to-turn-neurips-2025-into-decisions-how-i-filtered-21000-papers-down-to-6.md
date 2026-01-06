---
title: "Grab the 8 prompts I built to turn NeurIPS 2025 into decisions + how I filtered 21,000 papers down to 6 shifts"
author: "Nate Jones"
published: 2025-12-10
url: https://natesnewsletter.substack.com/p/i-filtered-21000-ai-papers-so-you
audience: everyone
scraped_at: 2026-01-05 19:10:16
---

*NeurIPS is the premier LLM academic conference.*

*Just 2-3 years ago, it used to be something few of us could pronounce and almost no one attended.*

*Well, not anymore. Now it shapes how a billion people will work and live, and we all need to know about it.*

[![](https://substackcdn.com/image/fetch/$s_!jmwU!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3de16ae5-fe61-4ca3-a6a4-01dac18b92a9_1024x547.png)](https://substackcdn.com/image/fetch/$s_!jmwU!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3de16ae5-fe61-4ca3-a6a4-01dac18b92a9_1024x547.png)

*So this is your NeurIPS cheat sheet. This is what you need to know now about what shapes your tools for next year. And I’m not kidding about that. Look at this year: if you’ve noticed AI getting better at long documents, or watched reasoning models like o1 appear seemingly out of nowhere, those capabilities started as NeurIPS papers 12-18 months earlier.*

*This year, the conference split across two cities for the first time — San Diego and Mexico City — and still couldn’t fit everyone. The main track received 21,575 submissions, up from 9,467 in 2020. Which is completely insane. And yes, lots of the papers where AI-assisted.*

*The best paper awards this year went to work that challenges assumptions many teams are still operating under — including one paper proving that the top 70+ AI models now give nearly identical answers to open-ended questions, and another showing that “reasoning” improvements from reinforcement learning may not actually expand what models can do.*

*I’m not writing this as a NeurIPS insider or academic. I’m writing as someone who advises enterprise teams on AI rollouts and has to translate research into roadmaps. I don’t care who won which workshop. I care about three things: what changes the cost curve, what changes failure modes, and what changes where AI can run.*

*So I treated the conference like a noisy dataset and filtered it down to what matters for 2026 planning.*

***Here’s what’s inside:***

***The non-technical TLDR** — I want NeurIPS to feel accessible if you’re not technical. This will shape how we ALL work, so we should all get it. I put that one right at the top, just after the prompts.*

***Six technical shifts that will quietly change how AI works next year** — drawn from this year’s best paper awards and major lab presentations. I’ll explain what actually changed, why it matters for practitioners (not just researchers), and even where I might be wrong about each one. The future is uncertain, and we’re going to lay out where NeurIPS shed light and where we still need to clear up ambiguity*

***The slop crisis and what it means for trust** — 21,575 submissions reviewed by exhausted volunteers, with AI now helping to triage AI-generated papers about AI. I’ll explain why “published at NeurIPS” no longer filters for quality, and share the framework I’m using instead.*

***Eight strategy prompts to apply this research to your specific situation** — each one embeds the full technical context so you don’t need to read the papers, and each runs as a one-question-at-a-time consultation:*

- ***Prompt 1: Model Convergence Strategy** — determine whether your multi-vendor model setup is now wasted complexity, given that frontier models are converging on similar outputs*
- ***Prompt 2: Attention Infrastructure Readiness** — identify which preprocessing and chunking pipelines will become obsolete as attention mechanisms improve*
- ***Prompt 3: Edge Deployment Economics** — calculate whether local/on-device inference now makes sense for your cost structure and privacy requirements*
- ***Prompt 4: Reasoning Telemetry Architecture** — design instrumentation for agents and multi-step AI systems so you can actually debug them when they fail*
- ***Prompt 5: Research Curation System** — build your own filter for AI research now that conference prestige no longer signals quality*
- ***Prompt 6: Automation Frontier Reassessment** — revisit workflows you previously ruled out as “too complex” given new RL scaling results*
- ***Prompt 7: Diffusion Model IP Risk Assessment** — develop the right questions to ask vendors about image generation training protocols and memorization risk*
- ***Prompt 8: 2026 AI Strategy Synthesis** — pull all six shifts together into a prioritized roadmap based on your role and industry*

*If this one sounds nerdy, it is! But everything that ends up in your tooling starts out as a nerdy NeurIPS paper. So this is the summary I wish I had, so I wrote it. I hope it helps you get a clear view of what’s coming down the tracks in 2026.*


## [GRAB THE PROMPTS](https://www.notion.so/product-templates/NeurIPS-2025-Strategy-Prompts-2c45a2ccb52680b69336cec96aedbbc7?source=copy_link)

These eight prompts walk you through the decisions that will shape your 2026 AI strategy. You’ll figure out whether using multiple AI vendors is still worth the complexity, and which parts of your current workflow AI will make obsolete in the next six months.

You’ll rethink the math on running AI locally versus in the cloud. You’ll learn how to track what your AI is actually doing so you can fix it when things go wrong. You’ll cut through the hype to find research that actually matters for your work.

You’ll revisit projects you shelved because they seemed too complicated at the time. And you’ll ask the right questions about legal risk when AI generates images.

These aren’t generic templates—they’re the same frameworks I use when advising enterprise teams on where to place their bets. I think that’s a more useful and less hype-y frame for NeurIPS, and it gives us something stable to work on.

---


## **The Non-Technical Version**

NeurIPS is where the nerds decide what your AI tools will do next year. If you’ve noticed AI getting better at long documents, or watched reasoning models appear seemingly out of nowhere—those started as NeurIPS papers 12-18 months earlier. So even if you never read a research paper, what happens here shapes your workflow.

This year’s conference was so big it had to split across two cities and still couldn’t fit everyone. Twenty-one thousand paper submissions, up from under ten thousand five years ago. The review system is buckling under the weight, which creates its own problems I’ll get to. But first: what actually matters.

**Six things that will change your tools in 2026:**

AI is about to get meaningfully better at long documents. One of the top papers found a surprisingly simple fix for why models lose track of information in the middle of long texts. This is already shipping in newer models. If you’ve built elaborate workarounds to deal with context limits—chunking documents, running multiple passes, custom retrieval systems—some of that infrastructure is about to become unnecessary overhead.

The major AI models are converging on the same answers. This one got measured rigorously: more than 70 top models now give strikingly similar responses to open-ended questions. The researchers called it the “Artificial Hivemind effect.” The practical implication is that agonizing over which frontier model to use matters less than it did. The differences that matter now are price, speed, and reliability—not capability. And if you’re running the same prompt through Claude and GPT and Gemini hoping to get diverse perspectives, you’re getting three variations on the same perspective.

The “reasoning” improvements in models like o1 might not be what we thought. This one’s a bit of a gut punch. A best paper showed that reinforcement learning for reasoning doesn’t appear to teach models genuinely new problem-solving strategies. It makes them faster at finding answers they could already produce. The improvements are real—you get better results more efficiently—but the ceiling on what models can figure out may not have moved as much as the hype suggested.

On the flip side, a different kind of AI learning is finally scaling. The “just make it bigger” approach that worked for language models is now working for AI that learns from trial and error in complex environments. This is the research that eventually enables robots, autonomous systems, and automation of tasks we previously thought were too variable or unpredictable. If you ruled out automating a workflow in 2023 because it was “too complex,” that complexity ceiling has moved.

Image generation isn’t inherently copying—but the legal questions aren’t settled. A top paper showed that diffusion models have a natural training dynamic that prevents memorization if you train them right. This shifts the IP conversation from “these tools are stealing” to “what questions should we ask about how this tool was trained?” It’s progress, but it’s not a clean answer for the lawyers.

Running AI locally is becoming practical. This wasn’t one paper—it was a theme across the whole conference. Demos of capable models running on phones, laptops, specialized chips. The quality gap between local and cloud models is shrinking. For anything high-volume, latency-sensitive, or involving data you can’t send to third parties, the economics have shifted.

**The trust problem**

Here’s the uncomfortable meta-story: NeurIPS received so many submissions that exhausted volunteers are now using AI to help triage AI-generated papers about AI. The conference is buckling. “Published at NeurIPS” used to be a quality signal. Now it means “this survived a process that couldn’t read everything deeply.”

I’ve stopped asking “where was this published?” and started asking “does this change what I would actually deploy?” That question cuts through prestige and gets to what matters.

---


## The Technical Version: Twenty-one thousand papers and no way to read them

The NeurIPS program committee released their retrospective in September. The number that jumped out: 21,575 valid submissions to the main track. That’s up from 9,467 in 2020 — more than doubled in five years.

They accepted 5,290 papers, a 24.52% acceptance rate. To review that volume, the conference recruited 20,518 reviewers, 1,663 area chairs, and 199 senior area chairs. The program chairs noted, diplomatically, that “recruiting has to happen at a larger scale, but this creates a greater possibility that papers might be reviewed and handled by less experienced reviewers.”

Here’s what that looks like in practice: approximately 400 papers that passed full review — three reviewers plus an area chair — were rejected anyway because the venues couldn’t fit them. Some researchers reported having papers with strong scores (5-4-4-4) cut at the last minute. The conference split across two cities for the first time and still ran out of space.

The community has started calling this the “slop crisis.” One researcher characterized the landscape as “LLM to the power of five” — large language models generating data, writing code, authoring papers, reviewing submissions, and serving as the research subjects themselves. The conference is now using AI tools to help triage the review process. That’s a reasonable response to an unreasonable workload, but it points to a structural problem that isn’t going away.


### How I decided what to pay attention to

I stopped treating “NeurIPS paper” as a quality signal and started treating each paper like an untrusted API call.

**What I ignored:** Benchmark improvements on datasets nobody uses in production. Pure theory with no plausible path to changing cost, reliability, or deployment. Papers that added “yet another loss term” without changing behavior in ways a user would notice. Workshop papers from labs with no track record of shipping anything.

**What I prioritized:** Architecture changes already landing in production models. Work from labs that have shipped systems, not just papers. Results that change at least one of: cost, latency, failure modes, or where the model can run.

The filter came down to three questions:

1. Does this make useful capability cheaper or faster?
2. Does this change how and when the model fails in ways a business should care about?
3. Does this move compute around — toward the edge, into the browser, into specialized hardware?

If the honest answer to all three was “not really,” I let it go. The six shifts below are what survived. Prompt 5 at the end (”Research Curation System”) is basically this process turned into a reusable script you can run on any new wave of arXiv links.

---


### Shift 1: Attention just got meaningfully better

One of the four best paper awards went to the Alibaba Qwen team for work that sounds almost too simple: add a sigmoid gate after the attention calculation.

The paper, “Gated Attention for Large Language Models: Non-linearity, Sparsity, and Attention-Sink-Free,” tested over 30 variants across 15B mixture-of-experts models and 1.7B dense models trained on 3.5 trillion tokens. The finding: applying a head-specific sigmoid gate after the scaled dot-product attention consistently improves performance, training stability, and long-context behavior.

The technical mechanism matters because it solves a known problem called “attention sink.” In standard transformers, models allocate disproportionate attention to certain tokens — often the first token in a sequence — regardless of whether those tokens are actually informative. The Qwen team’s measurements showed baseline models allocating about 46.7% of attention to the first token. With gated attention, that dropped to 4.8%.

This isn’t just an aesthetic fix. Attention sink forces models to waste capacity on uninformative positions, which degrades performance on long documents and contributes to the “lost in the middle” problem where models forget information in the center of long contexts. By giving the model the ability to output a zero vector from an attention head (which softmax normalization normally prevents), gated attention lets the model ignore positions that aren’t contributing useful information.

The practical result: better handling of long documents, more stable training with larger learning rates, and improved scaling properties. The NeurIPS selection committee noted that “the main recommendation of the paper is easily implemented, and given the extensive evidence provided... we expect this idea to be widely adopted.”

That’s already happening. The Qwen team integrated gated attention into Qwen3-Next, released in September 2025, which uses a combination of Gated DeltaNet and Gated Attention. The architecture supports context lengths up to 1 million tokens.

**Why this matters for you:** If you’ve built elaborate preprocessing pipelines to work around context limitations — chunking long documents, running multiple summarization passes, building custom retrievers — some of that infrastructure will become unnecessary overhead as these attention improvements propagate through the major model providers. The timeline is roughly 6-12 months before you’ll see meaningful improvements in the APIs you’re already using. Flag the ugliest workarounds in your stack now; they’re the first candidates for simplification.

---


### Shift 2: The models are provably converging

Another best paper, “Artificial Hivemind: The Open-Ended Homogeneity of Language Models (and Beyond),” turned an anecdote into a measurement.

The team — Liwei Jiang and colleagues from the University of Washington, Carnegie Mellon, and the Allen Institute for AI — built a dataset called Infinity-Chat: 26,000 diverse, real-world, open-ended queries paired with 31,250 human annotations. They then systematically tested output diversity across more than 70 state-of-the-art language models.

The finding: models exhibit what they call the “Artificial Hivemind effect” — pronounced homogenization both within models (the same model generates similar outputs to different prompts) and across models (different models generate strikingly similar outputs to the same prompt).

This isn’t news to anyone who’s used multiple AI assistants. But the paper quantifies it and, more importantly, identifies a mechanism. The homogenization isn’t random — it’s a predictable consequence of how models are trained. Similar training data, similar RLHF processes, and similar optimization objectives produce similar behavioral patterns. The paper explicitly challenges the assumption that adjusting temperature or using model ensembles will produce diversity. It doesn’t. The “creative” latent space of these models has been homogenized by training.

The NeurIPS committee noted the paper “reveals critical insights to guide future research for mitigating long-term AI safety risks posed by the Artificial Hivemind.” That framing — safety risk — is worth taking seriously. If all major AI systems converge on the same responses, any bias or blind spot in that consensus gets propagated everywhere simultaneously.

**Why this matters for you:** Two practical implications. First, if you’ve been agonizing over which frontier model to use, that decision matters less than it did. The capability gap between top-tier models is shrinking; the differences that matter now are pricing, latency, context window, tool integration quality, and reliability. Second, if you’re relying on AI outputs for anything that benefits from diverse perspectives — brainstorming, ideation, exploring solution spaces — you need to understand that “run it through Claude and GPT and Gemini” doesn’t give you three independent views. It gives you three variations on the same view.

---


### Shift 3: Reinforcement learning for reasoning might not do what we thought

This one stung.

A best paper runner-up, “Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?”, directly challenges the assumption behind models like OpenAI’s o1 and DeepSeek-R1. The conventional wisdom has been that Reinforcement Learning with Verifiable Rewards (RLVR) — training models by rewarding correct answers to math and coding problems — teaches models genuinely new reasoning strategies, similar to how AlphaGo discovered novel approaches through self-play.

The paper, by Yang Yue and colleagues, tested this systematically across multiple model families, RL algorithms, and benchmarks. They used a clever evaluation approach: instead of measuring average accuracy (which RLVR models clearly improve), they measured pass@k at large values of k — essentially asking “if we sample many times, what’s the maximum set of problems this model can solve?”

The finding is stark. At k=1 (single best answer), RLVR-trained models outperform their base models. But as k increases — giving the model more attempts — the base models catch up and eventually surpass the RLVR-trained versions. The reasoning paths generated by RLVR models are already present in the base model’s output distribution. RLVR isn’t teaching new strategies; it’s making the model more efficient at finding strategies it already knew.

The NeurIPS committee called this “a masterfully executed and critically important negative finding on a widely accepted, foundational assumption.”

There’s a nuance here. The paper also tested distillation — training a smaller model on traces from a better model — and found that distillation does introduce genuinely new reasoning patterns. So the conclusion isn’t “models can’t learn new reasoning.” It’s “current RLVR methods don’t appear to expand reasoning capacity beyond what’s already in the base model’s distribution.”

**Why this matters for you:** If you’ve been assuming that reasoning-focused models like o1 represent a fundamentally new capability tier — models that can solve problems their predecessors couldn’t — this paper suggests skepticism. The improvements are real, but they may be more about sampling efficiency than expanded capability. For practical purposes: RLVR models are better at finding correct answers quickly, which matters for cost and latency. But if you’re evaluating whether a model can handle a task at all, the base model’s upper bound may be the relevant ceiling.

---


### Shift 4: Deep RL is finally scaling

While the RLVR-for-reasoning story got more complicated, a different reinforcement learning result got more promising.

“1000 Layer Networks for Self-Supervised RL: Scaling Depth Can Enable New Goal-Reaching Capabilities” — another best paper — demonstrated that the “just keep scaling” approach that worked for language models can work for reinforcement learning too, under the right conditions.

The context: most RL research in recent years has used shallow networks (2-5 layers). Attempts to go deeper often failed — training instability, diminishing returns, collapse. The authors (Kevin Wang, Ishaan Javali, and colleagues) showed that with the right combination of self-supervised contrastive learning and batch size scaling, you can train RL policies up to 1,024 layers deep and get meaningful performance improvements.

The experimental setup was deliberately hard: unsupervised goal-conditioned learning with no demonstrations and no reward signals. The agent has to explore from scratch and learn how to reach specified goals. On simulated locomotion and manipulation tasks, the deep networks improved performance 2-50x compared to shallow baselines.

Two technical details matter. First, contrastive self-supervision — learning by comparing states and goals — provides a stable, dense learning signal that doesn’t collapse as networks get deeper. Second, batch size has to grow with depth; larger batches keep the contrastive updates stable.

**Why this matters for you:** The ceiling on what RL agents can learn from raw interaction just moved. This doesn’t mean household robots are arriving next year (some limited ones might though) — there’s a long path from simulated manipulation to physical deployment. But if you’re in an industry where automation has historically hit complexity walls — logistics, warehouse operations, manufacturing, anything with physical systems and adaptive decision-making — this is the foundational research that eventually enables products. The pattern is familiar: LLMs hit a scaling inflection point around 2020-2021, and capabilities that seemed decades away arrived in years. RL might be entering a similar phase. I’d revisit any workflow you ruled out as “too complex” or “too variable” for automation in 2025.

---


### Shift 5: Image generation isn’t necessarily theft (with caveats)

“Why Diffusion Models Don’t Memorize: The Role of Implicit Dynamical Regularization in Training” won a best paper award for clarifying a question at the center of ongoing legal and ethical debates about image generation.

The team (Tony Bonnaire and colleagues) showed that diffusion model training has two distinct timescales. There’s an early phase (τ\_gen) where the model learns to generate high-quality, diverse samples that aren’t copies of training data. And there’s a later phase (τ\_mem) where the model starts memorizing specific training examples.

The key finding: τ\_gen stays roughly constant regardless of dataset size, but τ\_mem increases linearly with the size of the training set. This means that with enough training data and appropriate stopping time, you can stay in the generalization regime and never enter the memorization regime.

This is a form of implicit regularization — the training dynamics themselves prevent memorization if you don’t train too long. The paper notes that “a principled early-stopping criterion — scaling with dataset size — can effectively optimize generalization while avoiding memorization.”

**Why this matters for you:** This shifts the IP conversation around image generation from “diffusion models are inherently copying training data” to “the questions are: how much data, how long did you train, and can you demonstrate you stayed in the generalization regime?”

That doesn’t make copyright concerns disappear. Sensitive content can still be reproduced under certain conditions. But it provides a framework for due diligence. If you’re evaluating image generation tools for business use, you now have better questions to ask vendors: What’s your training dataset size? What’s your training protocol? How do you validate that you’re operating in the generalization regime?

The caveat: this is about the aggregate statistical behavior of these models. A model that doesn’t memorize on average can still reproduce specific images in edge cases — and those edge cases are exactly what matters for litigation and regulation. The paper advances the science; it doesn’t settle the legal questions.

---


### Shift 6: Edge deployment is becoming practical

This one doesn’t come from a single paper but from a clear theme across the conference.

NeurIPS 2025 included an entire expo track on edge AI deployment, with demos of safety-aligned LLMs running on mobile devices, vision-language models doing path planning on Snapdragon chips, and quantized models achieving near-cloud-quality performance on laptops. Apple presented multiple papers on running efficient models locally, including demonstrations of fine-tuning 7B-parameter models on an iPhone using their MLX framework.

The technical enablers are converging: quantization techniques that reduce precision without proportional quality loss, specialized neural processing units in consumer hardware, and software frameworks optimized for edge inference. Research at NeurIPS showed that 4-bit quantized models can retain 90-95% of their full-precision accuracy while reducing memory footprint by 75-90%.

The shift in narrative from major labs is notable. The message used to be “we have the biggest model.” Now it’s “we can run strong models where your users are.” Qualcomm demonstrated 7B-parameter models running on Snapdragon with sub-second latency. Apple’s presentations emphasized on-device inference for privacy-sensitive applications.

**Why this matters for you:** Three things change when AI runs locally. Latency drops — a local model responding in 50ms beats a 2-second API round trip for anything interactive. Marginal cost drops — you’re paying for hardware, not per-token. And privacy improves — data never leaves the device.

The question isn’t whether local models are as good as cloud models. They’re usually not. The question is whether local models are good enough for specific tasks, and what you gain from running locally. For high-volume inference, latency-sensitive applications, or anything involving data you can’t send to third parties, the economics have shifted. If you’re paying significant API costs, do the math. Prompt 3 (Edge Deployment Economics) walks through the calculation.

---


### The mental model shift

If I had to distill NeurIPS 2025 into a single observation, it’s this: the questions that mattered last year are becoming the wrong questions.

[![](https://substackcdn.com/image/fetch/$s_!aeJo!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2fa069f5-5c8c-474e-bbee-4128e4d88337_1468x548.png)](https://substackcdn.com/image/fetch/$s_!aeJo!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2fa069f5-5c8c-474e-bbee-4128e4d88337_1468x548.png)

---


### The slop crisis, concretely

It helps to put a human face on the signal-to-noise problem.

The conference program chairs, in their September retrospective, described a new failure mode: “reviewers increasing their scores just to end back-and-forth discussion with the authors, but being silent or critical in private discussions with the AC.” Reviewer fatigue is breaking the feedback loop between author and evaluator.

Meanwhile, there’s an ecosystem of “mentorship businesses” whose model works like this: pay us, and we’ll help you generate a stack of conference-ready drafts with boilerplate experiments and lightly remixed ideas. The work isn’t necessarily fraudulent. It’s just not moving the frontier. But to a reviewer with 40 papers in their queue, it looks indistinguishable from the three that actually matter.

To be fair, some of this volume is just what industrialization looks like. When a field gets practical, you naturally get more incremental engineering papers and fewer fundamental breakthroughs. That’s normal. The problem is that the review system was designed for a different scale. NeurIPS in 2010 had 1/60th of this year’s submissions.

The consequence is a quiet collapse of trust. “NeurIPS paper” doesn’t mean “this is important” anymore. It means “this survived a stressed process that couldn’t read everything deeply.”

My fix has been to stop asking “where was this published?” and start asking “does this result change what I would deploy?” That question cuts through prestige. Prompt 5 at the end basically automates it.

---


### What to do now (by role)

Different seats experience these shifts differently.

**If you’re a founder or product lead:**

Treat model choice as infrastructure, not brand identity. The convergence research suggests you can simplify to one primary vendor plus a backup, and optimize for price, latency, and integration instead of capability FOMO.

Make a list of workflows where you said “too complex for automation” in 2023-24. The RL scaling results suggest the complexity ceiling has moved. At least one of those workflows probably deserves a prototype.

Flag any chunking or preprocessing subsystem that exists solely to work around context limitations. Those are the places where attention improvements will let you delete code over the next year.

**If you’re an enterprise exec:**

Update your RFPs and renewals. Stop asking “do you use the best model?” and start asking “how do you hedge across vendors, and what’s your plan when the model you’re using today degrades or changes policy?”

If you’re evaluating agent vendors, ask about reasoning telemetry. Can they show you how the system reached a decision? If not, they’re not ready for high-stakes workflows.

Ask your teams whether edge deployment would change your risk profile — especially for internal knowledge, regulated data, or latency-sensitive workflows.

**If you’re a staff+ IC or builder:**

Look at the ugliest pipeline you own — the one with the most hacks to work around context limits, weird failures, and cost. That’s your first candidate to simplify as the attention mechanism improvements land in production APIs.

Start treating local models as first-class options for prototyping and for anything you can’t send to the cloud. The quality gap is smaller than it was a year ago and shrinking.

Build yourself a small “canon” of labs and authors you trust. You don’t need to read the firehose. You need to read the 1-2% that will change how you build.

---


### Where this could be wrong

I’m reasonably confident about the direction of these shifts, but there are several ways this story could age badly.

**Homogeneity could diverge.** If non-US labs — particularly Chinese labs using different data and different RLHF priorities — develop meaningfully different behavioral patterns, we might see “AI cultures” emerge. In that world, vendor choice starts mattering again in ways that have nothing to do with capability.

**RL scaling could hit physical walls.** It’s one thing to train thousand-layer policies in simulation. It’s another to deploy them in noisy warehouses or hospitals without hitting safety, reliability, or latency problems. The gap between “works in simulation” and “works in production” has historically been larger for robotics than for language tasks.

**The diffusion IP story could crack on edge cases.** The “we don’t memorize if we stop early” finding is about aggregate behavior. It could hold on average while failing catastrophically for rare or sensitive data — exactly the cases that matter for litigation. A model that memorizes 0.01% of its training set is fine until that 0.01% includes someone’s copyrighted character.

**The RLVR findings might not generalize.** The “RL doesn’t expand reasoning” result was tested on specific benchmarks with specific algorithms. Future RLVR approaches — continual scaling, multi-turn interaction, different reward structures — might behave differently. The paper itself suggests these as directions that might “unlock the potential.”

Despite these uncertainties, I think we get a pretty clear idea of where models and tools will evolve in 2025: more focus on reasoning methodology, especially as it relates to long-running agentic tasks. More focus on quantized and edge-distributed models, and new emphasis on how to give models more sophisticated training via RL and move away from the simple reward signal.

[![](https://substackcdn.com/image/fetch/$s_!QkiW!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb8c29636-51ba-48c2-9879-c02a2fea22f9_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!QkiW!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb8c29636-51ba-48c2-9879-c02a2fea22f9_1024x1024.png)
