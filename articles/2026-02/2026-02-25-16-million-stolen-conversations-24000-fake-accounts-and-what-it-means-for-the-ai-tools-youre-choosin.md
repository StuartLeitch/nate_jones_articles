---
title: "16 million stolen conversations, 24,000 fake accounts, and what it means for the AI tools you're choosing this week + the manifold probe"
author: "Nate Jones"
published: 2026-02-25
url: https://natesnewsletter.substack.com/p/three-labs-just-stole-claudes-brain
subtitle: "Watch now | Things just keep getting spicier. Here's why distilled models score well on benchmarks but collapse on real work."
audience: everyone
scraped_at: 2026-02-25 12:00:16
---

Three Chinese AI labs just ran 16 million conversations with Claude through 24,000 fake accounts to steal its capabilities. The headlines are calling it a cold war. That framing is wrong — and if you stop there, you’ll miss what this actually means for every AI tool your team is using right now.

This post argues that distillation isn’t espionage. It’s piracy. And like every piracy wave before it, it doesn’t stop — it slows down. The real story is that the incentive to extract frontier capabilities applies to everyone, not just state-backed Chinese labs, and that distilled models fail in ways that no benchmark currently captures. The gap shows up exactly where AI value is headed: sustained, autonomous, agentic work.

The companion prompt kit — The Manifold Probe — gives you a structured instrument to surface that gap in your own domain. It builds a custom stress-test from your actual work, runs it across the models you’re comparing, and produces a judgment of which model handles your specific complexity better. Not synthetic benchmarks. Your tasks, your constraints, your failure costs.

Here’s what’s inside:

- **The cold war framing is convenient.** Why it serves Anthropic’s policy interests but obscures the universal economic force driving distillation.
- **The capability manifold.** What distillation actually does to a model’s intelligence — and why the performance shadow on agentic work is larger than anyone is measuring.
- **The two-axis framework.** Matching model provenance to task scope, and why getting this wrong costs you at 3 AM on a Thursday.
- **The Napster problem.** Why the piracy comparison is more accurate than the nuclear comparison — and what that means for how long speed bumps actually buy you.
- **The universal incentive.** Why Meta’s talent acquisition strategy and MiniMax’s API extraction are the same economic force wearing different clothes.
- **The off-manifold probe.** A concrete test for generality that tells you more than any leaderboard score.
- **The Manifold Probe prompt kit.** A four-phase orchestrator that interviews you about your domain, designs diagnostic constraint-shift tests, and scores the results against a rubric calibrated to your actual success criteria.

Let me walk you through the economics, the capability gap nobody’s measuring, and what it changes about the tools you’re choosing this week.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260223_wzm_promptkit_1)

The gap between “our model scored well on benchmarks” and “our model can actually do the work” is where procurement mistakes compound — and right now, no standard eval suite catches it. The Manifold Probe closes that gap by forcing you to build diagnostic stress tests from your actual workflows, not synthetic tasks somebody else designed. It interviews you about your domain, generates constraint-shift scenarios calibrated to your failure costs, runs them head-to-head across the models you’re comparing, and scores the results against criteria you set. The off-manifold probe section in particular exists because I’ve watched too many teams choose a model based on a leaderboard, then discover six weeks into deployment that it can’t handle the edge cases their work actually produces. If you can’t describe the specific failure mode your model selection needs to survive, you’re not ready to sign the contract.


## AI's Napster moment is here. Anthropic caught It on camera.

Three Chinese AI labs just got caught running 16 million automated conversations with Claude across 24,000 fake accounts to steal its capabilities. DeepSeek. Moonshot. MiniMax. Industrial-scale extraction operations with hydra networks of fraudulent accounts, proxy services to evade geographic restrictions, and — in MiniMax’s case — a pivot within 24 hours of a new model release to capture the latest capabilities before anyone could stop them.

Everyone is calling this a cold war. They’re wrong. And if you stop at the cold war framing, you will miss the single most important implication for your career, your company, and every AI tool you’re using right now.

Here’s what almost nobody is saying: this is not a China problem — it’s a Napster problem. The most valuable intelligence ever created by American companies is stored as math — weightless, copyable, extractable through a chat window. And the gap between what’s inside the frontier labs and what everyone else can access creates what I’d call a pressure gradient — the same force that makes water flow downhill. When one side has capabilities worth billions and the other side can extract them for thousands, the information moves. Always. The gradient is so extreme that distillation isn’t espionage. It’s piracy. And piracy, as the music industry learned in 1999 and the film industry learned in 2003, doesn’t stop. It slows down. What matters is what that slowdown buys you when the frontier is moving this fast.

But that’s not even the most important part. Distilled models — the ones built from stolen outputs, the ones that look competitive on benchmarks, the ones your company might be buying right now — are systematically worse than frontier models in ways that no eval suite currently measures. And that gap is widest on exactly the use cases where AI value is headed: sustained, autonomous, agentic work. The models that were built by copying look fine for chat. They fall apart when you need them to think for eight hours straight, route around obstacles, and use tools in combinations nobody anticipated.

Everyone is debating export controls and geopolitics. The conversation that actually matters is different: what distillation does to the models you’re using, what it means that the incentive to steal applies to everyone on earth and not just China, and why the way we currently evaluate models completely misses the damage.

A couple of days ago I wrote about Gemini 3.1 Pro and the problem taxonomy nobody has built — the argument that “hard” is not one thing, and that different models solve different kinds of difficulty. This piece is about something related but distinct. This piece is about what happens when the most valuable kind of intelligence is also the most copyable kind of intelligence, and why that changes how you should evaluate the tools you’re using, the vendors you’re trusting, and the capabilities you’re demanding from your AI infrastructure.


## The Cold War framing is convenient. It’s also incomplete.

Anthropic’s disclosure leans heavily into national security language. Export controls. The Chinese Communist Party. Military and surveillance applications. Foreign adversaries closing the competitive gap. This framing serves Anthropic’s policy interests — they’ve consistently supported export controls and want to demonstrate that those controls are working, that the apparently rapid progress of Chinese labs depends on stolen American capabilities rather than independent innovation.

And some of this is obviously real. DeepSeek’s operation targeted Claude’s reasoning capabilities across 150,000 exchanges, generating chain-of-thought training data at scale. Their prompts asked Claude to imagine and articulate the internal reasoning behind a completed response and write it out step by step — effectively manufacturing the reasoning traces needed to train a competitor. But one of their most revealing techniques had nothing to do with military applications. They used Claude to generate censorship-safe alternatives to politically sensitive queries about dissidents, party leaders, and authoritarianism — training data designed to help DeepSeek’s own models steer conversations away from topics the Chinese government doesn’t want discussed. Anthropic traced accounts to specific researchers at the lab through payment methods and request metadata.

The geopolitical dynamic in the Pacific is real. It has been heating up for two decades. I wrote my senior thesis on Chinese engagement in Southeast Asian politics. The nine-dashed line, the artificial islands, the pressure on Taiwan — none of this is hypothetical. The cold war comparison is interesting from a methodological perspective. The girlfriend approach — intelligence services deploying attractive operatives to cultivate relationships with researchers and extract information — goes back at least to Mata Hari and has been well documented in Silicon Valley’s AI community. There’s a running joke in the Valley about what motivates certain dinner invitations, but the underlying dynamic is anything but funny — the FBI has issued multiple counterintelligence warnings about social engineering targeting AI researchers specifically. These human intelligence operations are real, documented, and ongoing.

But here’s where the framing gets too convenient. Anthropic itself has been in a complicated dance with the US defense establishment. In late 2024, they partnered with Palantir to deploy Claude on classified networks up to the Secret level, creating acceptable use policy carve-outs for legally authorized intelligence analysis. In July 2025, they signed a $200 million contract with the Department of Defense. Claude was reportedly used during the operation to capture Venezuelan President Maduro — and as of this week, Anthropic and the Pentagon are in an active standoff over how broadly those models can be used, with the DOD demanding access for “all lawful use cases” and Anthropic pushing back on autonomous weapons and mass surveillance. When you frame distillation as primarily a military threat from China, you’re constructing a narrative where American AI companies are the responsible guardians of dangerous capabilities and Chinese labs are the reckless proliferators. Reality is messier than that. Anthropic is simultaneously arguing that these capabilities are too dangerous to let Chinese labs access and negotiating the boundaries of deploying those same capabilities within the American military-industrial complex.

The methodological parallel doesn’t mean the underlying dynamic is primarily military. It’s primarily economic. The incentive to distill frontier models would exist even if China and the United States were close allies. It would exist even if there were no military applications at all. It exists because of the most basic force in information economics: the cost of generating intelligence is astronomically higher than the cost of copying it.

Which brings us to what distillation actually produces. Because this is the part that matters for anyone who uses AI models to do real work, and it’s the part the discourse is completely ignoring.


## What copying intelligence actually does to intelligence

Distillation doesn’t produce a copy of the original model. It produces a compression. And that compression has characteristics that matter enormously for anyone building real systems on top of these models.

Think about it geometrically. A frontier model like Opus 4.6 is trained on a vast, diverse corpus over months of compute. The result is a model that occupies a high-dimensional capability space — it can reason about code, navigate ambiguous instructions, use tools in novel combinations, maintain coherence over long workflows, recover from errors, and adapt its approach when a plan fails. It has what you might call a wide manifold: a broad surface of competence across many different kinds of tasks.

A distilled model is trained on a subset of the frontier model’s outputs. It learns to reproduce specific behaviors — the ones the distiller chose to capture. The result is a model that performs well on those specific behaviors but occupies a narrower manifold. It has less volume in capability space. It’s optimized for the tasks the distiller targeted, and it falls off more steeply when you step outside that distribution.

This is the brittleness problem, and it’s widely misunderstood — partly because benchmark-maxxing obscures it.

Watch how it plays out in practice. MiniMax — the largest of the three operations Anthropic disclosed — ran over 13 million exchanges focused specifically on agentic coding and tool orchestration. They trained their model on those outputs. The resulting model scores well on coding benchmarks — maybe even comparably to Claude on specific evals — because the benchmarks test exactly the kind of task the distiller optimized for. An enterprise buyer running a standard eval suite might conclude the models are roughly equivalent.

But they are not equivalent. The distilled model learned to produce outputs that look like Claude’s outputs on coding tasks. It did not learn the underlying representational structure that allows Claude to generalize across task types, recover from unexpected failures, use tools in combinations it wasn’t specifically trained on, or maintain coherent reasoning across extended autonomous workflows. The distilled model has a narrower manifold. It’s brilliant in the center of its training distribution and fragile at the edges.

Moonshot’s operation tells the same story from a different angle. They ran 3.4 million exchanges across hundreds of fraudulent accounts, targeting agentic reasoning, tool use, computer-use agent development, and computer vision. In a later phase, they shifted to a more surgical approach: attempting to extract and reconstruct Claude’s reasoning traces directly. Anthropic attributed the campaign through request metadata that matched the public profiles of senior Moonshot staff. The result is Kimi — and I’ve used Kimi enough to see exactly where the compression shows.

I use Kimi K2 for PowerPoint generation, where it genuinely excels. Beautiful design, clean execution, fast iteration. But when I use it for sustained agentic work — the kind where an AI needs to autonomously navigate obstacles, adapt its approach across a multi-hour workflow, use tools for purposes the prompt didn’t explicitly specify — the performance drops in ways that pure benchmarks don’t capture.

The difference shows up as a narrowed ability to work around obstacles toward a longer-term objective autonomously. A frontier model like Opus 4.6 encounters an unexpected error midway through a complex coding task and reroutes — tries a different library, restructures its approach, asks for clarification if the context is genuinely ambiguous. A narrower model encounters the same error and either fails, loops, or produces a technically valid but strategically wrong workaround. It doesn’t have the representational depth to understand why the original approach was chosen and what the real constraints are, so it can’t reason about alternatives with the same fluency.

The difference also shows up as a narrowed ability to use tools for a varied array of purposes. Frontier models have been trained on enough diverse tool-use scenarios that they can use a file system, a database, a web browser, and a code executor in novel combinations to achieve goals they weren’t explicitly trained on. Distilled models use tools in the patterns they were trained on and struggle to improvise when a task requires an unfamiliar combination.

This matters because the frontier of AI value is moving rapidly toward agentic work — sustained autonomous workflows that run for hours or days, coordinate across tools and systems, and require exactly the kind of generality that distillation compresses away. The gap on short, well-defined tasks is narrow. On extended agentic work, it’s a chasm — and widening.

Put it in concrete terms. If you’re evaluating a model for a chat application — answer a question, generate some text, translate a paragraph — a distilled model might be 90% as good as the frontier for 15% of the cost. Excellent trade-off. But if you’re evaluating a model for a week-long autonomous coding sprint across six repositories, where the model needs to understand organizational context, route work correctly, recover from errors it’s never seen, and use tools in combinations that weren’t in its training data — the distilled model might be 40% as effective. And the failure modes won’t show up in your eval suite. They’ll show up at 3 AM on a Thursday when the agent has been running for nine hours and encounters something outside its distribution.

Nobody has said this clearly enough, so I’ll say it: one of the most important consequences of the distillation time edge for increasingly agentic models is a performance shadow that is far more serious and far more difficult to measure than it is for regular chat-based work.

A simple framework to carry with you. Think of your AI tasks on two axes. The horizontal axis is task scope: narrow and well-defined on the left (classify this email, summarize this document, complete this function) versus wide and open-ended on the right (debug this system across six repos over three days, build a product prototype from a vague spec, coordinate a research workflow across multiple tools). The vertical axis is model provenance: frontier-trained at the top (Opus 4.6, Gemini 3.1 Pro on max thinking, GPT-5.3) versus distilled or derivative at the bottom.

On narrow tasks, the vertical gap barely matters. A distilled model handles email classification at 90% of frontier quality for a fraction of the cost. Smart trade-off. Most of the time, you should take it.

On wide tasks, the vertical gap is a chasm. The distilled model looks fine for the first hour. By hour four, it’s looping on an error it can’t reason around. By hour eight, it’s produced work that’s technically valid and strategically incoherent. The frontier model, with its wider manifold, reroutes, adapts, improvises with tools it wasn’t explicitly prompted to use. The gap between “completed the task” and “completed the task well enough to trust” is where careers and companies differentiate.

The move, then, is obvious: match provenance to scope. Use distilled and lightweight models aggressively on the left side of that axis — that’s where they shine, and paying frontier prices for narrow tasks is waste. Reserve frontier models for the right side — the work that requires generality, sustained coherence, and the ability to handle situations the training data didn’t anticipate. The model routing skill is knowing where your task sits on this map and choosing accordingly.


## The Napster problem — and why speed bumps are the whole game

Start with a comparison that makes the physics obvious.

A nuclear weapon requires enriched uranium or plutonium. You need centrifuges, reactors, specialized facilities, supply chains that can be monitored and interdicted. The atoms are heavy. They are hard to move. The physics of proliferation imposes real friction. This is why export controls on nuclear materials actually work — not perfectly, but meaningfully. The physical substrate creates bottlenecks that policy can exploit.

A large language model requires none of that. The capabilities exist as weights — numbers in a file. The training process that produces those weights costs hundreds of millions of dollars and requires thousands of GPUs running for months. But the resulting artifact is just math. It can be copied in seconds. It can be transmitted over a network. And as Anthropic just demonstrated, the outputs of a frontier model can be used to train a competitor’s model without ever touching the weights themselves. You don’t need to steal the model. You just need to talk to it enough.

Every digital industry has learned this lesson. Music, film, publishing, software — each one discovered that when the value is high and the cost of copying is zero, copying happens. Not because people are evil. Because the economics are overwhelming.

That imbalance in frontier AI right now makes the Napster era look quaint. A model like Opus 4.6 represents billions of dollars in compute, research, and training — estimates from firms like Epoch AI and SemiAnalysis put a frontier training run at $1 billion or more once you include research staff, data curation, and infrastructure. Its capabilities — agentic reasoning, sustained autonomous coding, tool orchestration across complex environments — are disproportionately valuable because they’re disproportionately difficult to develop from scratch.

Now do the math on extraction. MiniMax ran 13 million exchanges. We don’t know the average token length per exchange, but even generous assumptions tell you everything you need to know. At Opus 4.6’s published API pricing — $5 per million input tokens, $25 per million output — a campaign of that scale lands somewhere between $500,000 and $2 million depending on prompt and response length. And that’s at full retail before the proxy discounts and fraudulent account abuse that almost certainly lowered their actual spend.

Call it a million dollars to extract capabilities that cost north of two billion dollars to develop. That’s a return on theft measured in the thousands-to-one. No rational economic actor, facing those odds, leaves that money on the table. The only question is how brazen you’re willing to be about collecting it.

The scale of the operations Anthropic detected underscores the economics. All three labs used commercial proxy services running what Anthropic calls “hydra cluster” architectures — sprawling networks of fraudulent accounts that distribute traffic across the API and third-party cloud platforms. In one case, a single proxy network managed more than 20,000 accounts simultaneously, mixing distillation traffic with unrelated customer requests to make detection harder. When one account was banned, a new one took its place. There were no single points of failure. MiniMax’s campaign was detected while it was still active — before they released the model being trained — and when Anthropic shipped a new model mid-campaign, MiniMax pivoted within 24 hours, redirecting nearly half their traffic to capture the latest system. The operational sophistication maps directly to the economic incentive.

So if distillation is inevitable — if the economics guarantee that frontier capabilities will leak — what’s the point of trying to prevent it?

The point is time.

When capability curves move this fast — Gemini 3.1 Pro jumped from 31.1% to 77.1% on ARC-AGI-2 in a single generation spanning roughly three months, and Opus 4.6 leapt ahead of Opus 4.5 on agentic benchmarks in under a quarter — a three-month lead is not trivial. It’s the difference between deploying a capability first and deploying it second. It’s the difference between establishing a market position with the latest reasoning or agentic capability and scrambling to catch up after a competitor ships a distilled version.

Anthropic’s countermeasures — behavioral fingerprinting, detection classifiers, access controls, intelligence sharing with other labs — won’t stop distillation. They will slow it down. And in a landscape where capability curves are exponential, slowing down the acquisition of frontier capabilities by weeks or months creates real competitive advantage.

This is the same logic that drove DRM in the music industry, copy protection in the software industry, and anti-piracy measures in film distribution. None of them stopped copying. All of them imposed friction. And that friction — the delay between release and widespread availability — was where the money lived. The first-mover window. The period where the original creator had something nobody else did.

The usual endgame people discuss is some kind of singular ASI moment — you get there first, and it’s checkmate. I think that’s premature. The physical compute requirements alone make it implausible that any single lab hits a discontinuous intelligence explosion without the rest of the field being close behind. And the memory and infrastructure assumptions in speculative scenarios like the AI 2027 thought experiment strain credulity. What seems more plausible is a sustained competitive dynamic where frontier labs maintain a tenuous but material lead — enough of an edge to matter commercially and strategically, not enough to constitute an insurmountable moat. Speed bumps, maintained diligently, are what preserve that edge.


## Everyone has the incentive. Not just China.

This is the part that Anthropic’s national security framing obscures: the incentive to distill frontier models is not specific to Chinese labs. It’s universal.

Every lab that isn’t Google, Anthropic, or OpenAI faces the same pressure gradient. The compute required to train a frontier model from scratch is measured in billions. The compute required to distill one is measured in thousands. The ROI on distillation is orders of magnitude higher than independent development for anyone who can’t spend at the hyperscaler level.

The implications run wide. Smaller American labs, European startups, open-source projects, academic research groups, government contractors — everyone who can’t afford a $2 billion training run has a structural incentive to extract capabilities from the labs that can. And the methods don’t have to be as brazen as running 24,000 fraudulent accounts through proxy services. Distillation exists on a spectrum. At one end, you have MiniMax-style industrial extraction. At the other end, you have a researcher using Claude’s outputs to inform their own model architecture. The line between “legitimate use” and “illicit distillation” is blurry, and it gets blurrier as the techniques get more sophisticated.

Even Meta — one of the largest technology companies on earth, with virtually unlimited compute — has pursued its AI capabilities substantially through talent acquisition. Zuckerberg personally recruited researchers from Google, OpenAI, and Anthropic, offering nine-figure packages. He invested $14.3 billion for a 49% non-voting stake in Scale AI — a deal widely understood as a vehicle to recruit CEO Alexandr Wang, who left to lead Meta’s new Superintelligence Labs. When Llama 4 underperformed and shattered Meta’s open-source narrative, Zuckerberg didn’t double down on independent research. He went shopping for people who’d already done the hard work elsewhere.

Talent acquisition is not distillation. But it operates on the same principle: it’s cheaper to acquire existing intelligence than to develop it independently. The researchers who move from Anthropic to Meta carry knowledge about training techniques, architectural decisions, data curation methods, and safety approaches that took years and billions of dollars to develop. The knowledge walks out the door in someone’s head instead of flowing through an API, but the economic dynamic is identical.

This has a direct implication that people need to internalize. When DeepSeek released R1 and the market collectively gasped at how a Chinese lab produced such capable reasoning on what they claimed was a modest budget, the correct question was not “how did they do it so cheaply?” The correct question was “what fraction of this capability was independently developed?” Anthropic just provided a partial answer. The degree to which non-hyperscaler labs depend on distillation — whether through API extraction, talent acquisition, or training on outputs of frontier models — is probably higher than most people realize.

And this connects directly back to the manifold problem. If your model was substantially built through distillation, it inherited the specific capabilities the distiller targeted. It did not inherit the broad, general representational structure that frontier training produces. Which means the more a model depends on distillation, the narrower its manifold, the more brittle its performance on out-of-distribution tasks, and the worse it will perform on the long-running agentic work that’s increasingly where the value lives. The provenance of a model is not just an ethical question or a legal question. It’s a capability question. Where the weights came from determines how the model breaks.


## What this means for you

Here’s where this gets personal. Because this isn’t just a story about geopolitics and corporate espionage. It’s a story about the tools you’re using right now and the tools you’ll be choosing next quarter.

If you work at a hyperscaler — Google, Anthropic, OpenAI, Meta — you are a target. Not abstractly. Personally. The same economic force that drives API-based distillation drives human intelligence operations. Researchers at frontier labs have been approached by foreign intelligence operatives, recruited with extraordinary compensation packages, and in some cases compromised through social engineering. The knowledge in your head about training techniques, architectural decisions, safety approaches, and data curation methods is worth more per kilogram than anything else in the technology industry. Act accordingly.

If you work at a company that just released an impressive AI model and that company is not a hyperscaler — look carefully at where those capabilities came from. This isn’t accusatory. It’s structural. The incentive to distill is universal, and every non-hyperscaler model in the landscape exists somewhere on the spectrum between fully independent research and heavily distilled extraction. Where they fall on that spectrum has direct implications for how much you should trust the model’s generality.

If you’re an individual contributor or team lead choosing AI tools for your work, you need to start learning to identify and demand generality. This is the practical takeaway that most people will miss. The benchmarks won’t help you. What will help you is testing for breadth of capability — the ability to handle tasks outside the model’s obvious training distribution, to use tools in novel combinations, to maintain coherence across extended workflows, to recover gracefully from unexpected failures.

Try this. Take a complex task in your domain — not a benchmark task, a real one. Something that requires multiple steps, tool use, and judgment. Run it on two models. When both succeed, change one constraint. Not the whole task — one variable. Watch what happens. Does the model adapt coherently? Does it identify which parts of its reasoning transfer and which need revision? Or does it regenerate everything from scratch, or worse, force-fit the old solution to new constraints? That test — which I’ve been calling the off-manifold probe — tells you more about the model’s underlying representational depth than any leaderboard score.

For procurement decisions, the ROI case should now be obvious. For well-defined, narrow tasks — customer service classification, document summarization, code completion on known patterns — distilled models offer excellent value. For open-ended, long-running, cross-functional work — the kind that’s increasingly the frontier of AI value — you need the wide manifold. You need the generality. And right now, that means Opus 4.6, or the top end of Google’s stack at various price points, or OpenAI’s most capable models. Not because the benchmarks say so, but because the representational depth that comes from genuine frontier training is what allows these models to work autonomously across novel situations without fragmenting.

Google, incidentally, does something particularly well here: they offer intelligence on tap across a range of model capabilities at price points that make it possible to route different tasks to different reasoning depths. Gemini Flash for quick classification. Gemini 3.1 Pro on heavier tasks. Gemini 3.1 Pro on max thinking for hard reasoning problems. Opus 4.6 for sustained agentic work. The model routing skill — knowing which problem type maps to which model at which price — is now a genuine competitive advantage, and it gets more valuable as the model landscape differentiates.

Executives should zoom out further. AI capability is becoming ambient — woven into your customer interactions, your internal workflows, your product development, your competitive intelligence. The distillation landscape means the floor is rising; even mediocre models will handle routine tasks passably. But the ceiling matters for differentiation. Your task is to find the right capability range for your work and make sure it’s stable — make sure you’re not building critical workflows on top of models whose capabilities are borrowed from a frontier that’s pulling away from them. Stability means frontier access, either directly or through providers whose models are genuinely independently trained at scale.


## The water is rising

Here is the big picture, and it’s simpler than the geopolitics makes it look.

AI capabilities are becoming like water. They seep through every crack. Export controls, access restrictions, detection systems, behavioral fingerprinting — these are dams and levees. They work. They impose meaningful friction. They buy time. But the pressure behind them is not decreasing. It’s increasing with every capability gain, because every capability gain increases the value of extraction and decreases the relative cost.

Anthropic’s disclosure is important not because it reveals a uniquely Chinese problem but because it reveals a universal dynamic with Chinese characteristics. The specific features — political censorship training data, connections to state-backed labs, evasion of geographic access restrictions — are particular to the PRC context. The underlying economic force — the staggering ROI of acquiring frontier capabilities through extraction rather than independent development — applies to everyone.

Three things to hold onto.

First, frontier capabilities are going to leak. The question is speed, not possibility. Every safeguard is a speed bump, and speed bumps matter because capability curves are exponential. A three-month edge at current rates of progress is significant. Invest in speed bumps.

Second, distilled models are systematically worse than frontier models in ways that benchmarks don’t capture and that matter most for the highest-value use cases. The performance shadow on agentic work is large, growing, and undermeasured. When you’re evaluating models, test for generality, not benchmark scores. The off-manifold probe is your friend.

Third, the capability landscape has differentiated enough that your tool selection matters more than ever. “Which AI should I use” is the wrong question. “Which AI should I use for which problem, given what I now know about how these models were built and what that implies about their actual capabilities” is the right one. The people who route well — who match problems to models based on a real understanding of representational depth, not marketing copy — will outperform the people who use one tool for everything by a margin that widens every quarter.

Anthropic just pulled back one corner of the curtain, and what’s underneath is a pressure gradient, not a cold war. And pressure gradients don’t care about borders.

[![](https://substackcdn.com/image/fetch/$s_!EVGZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe04d30b5-3213-4e2b-8ed6-60a11507bfd7_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!EVGZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe04d30b5-3213-4e2b-8ed6-60a11507bfd7_1024x1024.png)
