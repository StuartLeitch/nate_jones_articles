---
title: "Why CES 2026 marks a turning point + the constraint map behind the headlines (and yes, there are prompts)"
author: "Nate Jones"
published: 2026-01-08
url: https://natesnewsletter.substack.com/p/my-honest-field-notes-from-ces-2026
subtitle: "CES 2026 wasn't about chips--it was about who gets to ship. The allocation era has arrived and now factory economics decide who wins."
audience: everyone
scraped_at: 2026-01-08 12:00:16
---

CES is usually treated as a consumer electronics spectacle. But every few years, it becomes something else: the coordination event for the next industrial cycle. This is one of those years.

In the first AI era, capability was the bottleneck—you competed on model quality. In the next era, allocation is the bottleneck. You compete on supply position: who can actually deliver intelligence at scale, continuously, at a price that works.

CES 2026 marks the transition. Not because of any single announcement, but because of what the announcements reveal together: the industry is now optimizing for factory economics, not research milestones.

The teams that understood this shift a year ago locked capacity. The teams that didn’t are now waiting in queues, paying spot prices, or discovering their vendor can’t deliver what they promised. The gap between “has a strategy” and “has allocation” is about to become very visible.

Here’s what I’ll cover:

- The 5 signals from CES 2026 that reveal the shift to factory economics
- Why “bubbles don’t pre-buy bottlenecks” — and what OpenAI’s $38B in deals tells us
- The factory curve: why supply can’t catch demand, and why waiting doesn’t work
- State is the new scarcity: what breaks when your AI forgets mid-task
- What 10× cheaper inference actually unlocks (and why it leads to ambient AI)
- What this means if you build product, buy AI, or work in the system


## **[Grab the prompts](https://www.notion.so/product-templates/The-Factory-Era-Prompt-Pack-2e25a2ccb5268009b2f0e18d9dbf341a?source=copy_link)**

The factory era creates specific failure modes—your vendor gets allocation-constrained and your product becomes a queue, your context window fills and your agent forgets mid-task, your contract says “scale” but the reality is “wait.” Generic AI advice won’t help you here. I built three prompt frameworks tied directly to this analysis: one for builders (stress-test your degradation plan, state strategy, and routing), one for leaders and buyers (the vendor questions and contract clauses that reveal factory-era risk before you’re locked in), and one for anyone figuring out what this shift means for their career (where you get queued vs. where you become the operator). Each has a 30-second quick version and a deep version when you’re ready. They’re designed to produce artifacts you can actually use—not conversations that feel productive but go nowhere.


## **The Signals From This Week**

Five signals from CES 2026 tell the factory story.

**1. NVIDIA led with inference economics, not training capability.**

The Rubin NVL72 announcement centered on a claim: one-tenth the cost per million tokens versus Blackwell. That’s a serving metric, not a training metric. When the dominant platform vendor leads with unit economics, the customer pain point has shifted from “can we train it?” to “can we afford to run it?”

**2. NVIDIA productized state management.**

The Inference Context Memory Storage Platform treats KV cache—the working memory a model maintains during generation—as managed infrastructure. This is worth pausing on. Context has become a managed resource, like a cache tier or database in a classic web stack. When the platform vendor makes that a product, they’re telling you where the constraint moved.

Notice what’s happening: two announcements in, and we haven’t talked about model quality once.

**3. Rack-scale systems, not chips.**

Vera Rubin was introduced as a rack-scale platform—a 72-GPU configuration with integrated networking. NVIDIA isn’t selling components anymore. They’re selling factory modules. The unit of competition is the integrated system, not the chip.

**4. OEM integration signals ambient readiness.**

The Mercedes-Benz CLA demo featured NVIDIA’s platform embedded in what was presented as a production-intent vehicle. This signals OEM willingness to commit to continuous inference in shipping products—a bet on ambient AI, not a pilot that might scale later.

**5. Memory suppliers visible in the ecosystem.**

In the months leading to CES, Samsung and SK hynix announced involvement in projects like Stargate, engaging at the wafer level with AI infrastructure builders. CES is where the broader ecosystem reads these upstream moves as signal. Memory has become strategic enough that supply relationships are now part of the public positioning.

Each signal points the same direction: the competition has moved from “who has the best model” to “who can run the factory.”

But these signals don’t cluster in January randomly. CES is where the supply chain synchronizes.


## **What CES Coordinates**

Every January, the largest buyers lock design wins, supplier allocation, and datacenter timelines into the same calendar window. The announcements aren’t the decisions—they’re the public signal of commitments already taken.

**Memory allocation.** HBM is produced by a small handful of suppliers—SK hynix, Samsung, and Micron. Allocation decisions often shape what ships two to three quarters later.

**Packaging capacity.** Advanced packaging like TSMC’s CoWoS (which integrates HBM onto GPU packages) is widely reported as constrained. Slots are typically committed quarters in advance.

**Power.** Large AI deployments require hundreds of megawatts to gigawatts. Power agreements take years to execute.

The lead times span one to three years. The signals sent this week shape the capacity reality for 2027.

This creates a tension in how the industry gets interpreted.


## **Two Stories About AI Right Now**

If you follow AI from the financial press, you’re hearing one story. If you follow it from the infrastructure side, you’re hearing another.

**The finance story:** AI is a bubble. Valuations are disconnected from reality. Companies are overbuilding. The hype cycle will correct.

**The factory story:** AI is entering an industrial phase. Demand is real and growing faster than supply. The constraint isn’t capital—it’s physical: memory allocation, packaging throughput, power availability, lead times.

These stories can coexist in parts—real demand doesn’t preclude frothy valuations in some corners. But they can’t both be right about the core question: is the buildout justified by actual usage, or is it speculation waiting to correct?


## **How to Tell Which Story Is True**

Bubbles don’t pre-buy bottlenecks.

I was working in tech in 2000. The problem then wasn’t that we had too much traffic on the internet—it was that we had too little. Companies were building for demand that hadn’t materialized. The correction was inevitable because the usage wasn’t there.

That’s not the picture now. ChatGPT passed 800 million weekly active users last fall. The serving load dwarfs the cost of any single training run. When Sam Altman says he needs trillion-token packages to sell to enterprises—and that he’ll need 10 trillion, then 100 trillion—he’s describing a demand curve, not a marketing pitch.

In a bubble, companies buy options. They sign marketing partnerships that can be unwound. They rent short-term cloud capacity with flexible terms. They spend on downstream inputs—the stuff that’s easy to procure, easy to cancel.

In a real shortage, companies buy upstream inputs. They lock memory at the wafer level. They pre-commit to packaging capacity that takes years to build. They sign power agreements measured in gigawatts over long terms.

[![](https://substackcdn.com/image/fetch/$s_!frXe!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8ca6af9-7683-4cab-85bf-58e34facc574_1370x346.png)](https://substackcdn.com/image/fetch/$s_!frXe!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8ca6af9-7683-4cab-85bf-58e34facc574_1370x346.png)

Look at what companies with actual usage data are doing.

One company’s behavior reveals which story is true.


## **OpenAI and the Factory Curve**

The “factory curve” is the gap between demand growth and capacity buildout. The gap persists for structural reasons.

**Supply ramps slowly.** Building memory fabrication takes years. Packaging capacity additions take 18–24 months. Datacenter power requires utility agreements, grid connections, cooling infrastructure. You can’t accelerate these with capital alone—they’re gated by physics and permitting.

This isn’t like software, where you can scale by spinning up more instances. Every additional unit of AI capacity requires physical inputs with their own supply chains, their own lead times, their own constraints. When demand spikes, you can’t just “order more.” You wait in line behind everyone else trying to order more.

**Demand compounds with state.** Traditional compute demand is roughly linear: more users, more requests. But stateful AI—agents, long-context applications, continuous systems—compounds differently. Each session accumulates working memory. Each agent maintains context across steps. The memory footprint grows faster than the request count.

The math: going from 10,000-token average context to 100,000-token context means per-session memory goes up 10×. Add agents that persist across sessions, and you’re not just serving requests—you’re maintaining entities. You’re no longer asking “how many requests per second?” You’re asking “how many concurrent stateful entities can we sustain?”

**“Catch up later” doesn’t work.** If you’re behind the curve, you don’t gradually close the gap. You pay spot prices (when available), queue for allocation, or ration what you can serve.

Here’s what that looks like operationally. A company waits to lock capacity, assuming supply will catch up. Six months later, they’re ready to scale—but their vendor is allocation-constrained. Latency that was 200ms is now 2 seconds. Requests that processed instantly are queuing. Their product feels broken to users. They try to route traffic to a backup, but they never built the routing layer. They try to port the workload, but their integration is too tightly coupled. They’re stuck—and their competitor, who locked capacity early, is shipping what they can’t.

I’ve watched companies discover this the hard way. The contract said “scale.” The reality was “queue.”

This is why OpenAI’s behavior matters as signal. They have more usage data than almost anyone. If they believed supply would catch up to demand, they’d wait and negotiate from strength later. Instead, they’re locking inputs years in advance at massive scale.


## **OpenAI’s Four-Lane Strategy**

OpenAI’s 2025 procurement isn’t a collection of deals. It’s a portfolio strategy for staying ahead of the factory curve—four lanes, each solving a different constraint.

**Lane 1: Bridge capacity (solves the time constraint).** You can’t serve users with datacenters you haven’t built yet. OpenAI and AWS announced a $38 billion, seven-year agreement giving OpenAI access to hundreds of thousands of NVIDIA GPUs, with capacity deploying through 2026 and options into 2027. This is rental at scale—a way to keep the factory running while longer-term infrastructure comes online.

**Lane 2: Second-source compute (solves the supply risk constraint).** When demand exceeds any single vendor’s output, single-sourcing becomes a chokepoint. OpenAI structured partnerships with AMD (a second GPU ecosystem) and committed capacity with CoreWeave (specialized infrastructure outside the hyperscalers).

**Lane 3: Custom silicon (solves the unit economics constraint).** For predictable, high-volume inference workloads, general-purpose GPUs aren’t optimal. OpenAI’s Broadcom collaboration targets purpose-built accelerators for inference.

**Lane 4: Memory supply (solves the binding physical constraint).** Samsung and SK hynix are set to supply memory chips to OpenAI’s Stargate project. A model company engaging memory suppliers at the wafer level—that’s treating memory as a strategic input, not a commodity purchase.

Each lane maps to a factory bottleneck. Together, they form a doctrine: stay ahead of the curve by locking every input that could become a chokepoint.

Notice something else. OpenAI is building a multi-vendor supply chain—NVIDIA, AMD, Broadcom, multiple memory suppliers, multiple cloud partners. This looks less like picking a winner and more like the early days of multi-cloud, when enterprises realized that depending on a single provider was itself a risk. Some customers went all-in on one cloud; others diversified. But each major cloud continued to grow even as relative share shifted. NVIDIA’s position may evolve the same way: dominant, but no longer singular.

OpenAI has secured the physical inputs. But there’s another input the whole industry is about to discover it can’t ignore.


## **State Is the New Scarcity**

In the old world, compute was the thing you ran out of. You had a budget of GPU hours. You optimized to use fewer of them.

In the new world, state is the thing you run out of.

When a model generates a response, it doesn’t start from scratch each token—it carries working memory forward, the KV cache that holds everything the conversation has established so far. That’s state. The longer the session, the more state. The more concurrent users, the more state. The more agentic the workflow, the more state.

And state scales dangerously. A 10,000-token conversation needs a certain amount of working memory. A 100,000-token conversation needs ten times more. Multiply by a million concurrent sessions. Add agents that persist across hours or days. You’re not just serving requests anymore—you’re maintaining entities.

Each agent, each long-context application, each always-on system adds persistent memory load. It’s not a spike you provision for and scale down. It’s a footprint that accumulates.

The failure mode isn’t “AI gives a wrong answer.” It’s “AI forgets what it was doing.”

A customer support agent is handling a billing dispute. The customer has explained the problem, provided account details, described three prior calls where they were promised a refund. The agent is mid-resolution.

Then the context window fills. The session times out. The state fails to persist.

Now the agent asks for the account number again. It doesn’t remember the promise. It contradicts what it said ten minutes ago. Or worse: it takes an action that contradicts the resolution it was working toward.

State reset doesn’t mean “start over.” It means broken promises, contradicted commitments, trust collapse.

“Can it answer well?” becomes the wrong question. The right question: “Can it maintain coherent behavior over time, at scale, without losing track of what it’s doing?”

So the question becomes: who builds the infrastructure that makes state manageable at scale?


## **Rubin Is the Bridge**

NVIDIA’s Rubin announcement is the answer.

It’s not just “cheaper tokens.” It’s the bridge between factory economics and ambient deployment.

Even if real-world gains are smaller or uneven across workloads, directionally the curve is the story. When inference costs drop by an order of magnitude, behaviors that were economically irrational become viable.

*Continuous inference.* Instead of invoking AI for discrete requests, you can afford to keep it running—monitoring, maintaining awareness, anticipating.

*Longer context.* Context windows that were prohibitively expensive become affordable. A support agent can maintain the full history of a customer relationship. A coding assistant can hold an entire codebase in working memory.

*Agent loops.* Multi-step reasoning with tool use and state persistence becomes economically viable at scale.

NVIDIA didn’t just announce cheaper chips. They announced Inference Context Memory Storage—infrastructure for treating KV cache as managed state across the system, storing and moving it efficiently rather than recomputing it.

When the platform vendor productizes state management, they’re telling you where the constraint moved. Compute is becoming abundant. State is becoming the bottleneck.

Cheaper inference plus managed state means continuous AI becomes viable. That’s the foundation for ambient systems—AI that’s always present, embedded in devices and environments, maintaining context across interactions.

Rubin isn’t just a faster chip. It’s the economics that make ambient possible and the infrastructure that makes it tractable.


## **The Abundance Cascade**

When the factory works, a cascade follows.

First, the cost drop unlocks usage expansion. When tokens are expensive, you ration them. When they get 10× cheaper, you stop rationing. Usage expands to fill the new cost envelope.

Then usage expansion enables continuous systems. When inference is cheap enough, “always on” becomes viable. You’re not making discrete requests anymore. You’re running systems that persist.

And once systems run continuously, the human role shifts. You’re not prompting AI. You’re supervising it. The job becomes: set the rules, define the boundaries, monitor the behavior, handle the exceptions.

This is the moment AI stops being software and starts being infrastructure.


## **Ambient AI and What Breaks**

Once inference runs continuously, the failure mode changes. It’s not “the AI gave a bad answer.” It’s “the AI wasn’t there when it was supposed to be.”

A hospital network runs continuous AI monitoring for early sepsis detection. The system watches vitals, flags anomalies, escalates to nursing staff.

One night, inference latency spikes—the vendor is allocation-constrained, requests are queuing. The monitoring AI slows down. Alerts that should fire in seconds take minutes. Some fall below confidence thresholds because the model runs a degraded fallback.

A patient’s vitals cross the sepsis threshold. The alert doesn’t fire in time. By the time a nurse notices manually, the window for early intervention has narrowed.

One incident becomes a pattern. The hospital investigates. They discover their “AI monitoring” was silently degraded for hours. Liability questions surface. The system gets suspended pending review. Other hospitals hear about it. Deployments pause across the network.

This isn’t apocalypse. It’s the ordinary cascade when ambient systems fail: degradation → missed signal → harm → investigation → liability → pullback. The system wasn’t supplemental. It was the substrate. When it failed, there was no overflow to absorb.

Or take payments. A fintech runs continuous fraud detection—every transaction scored in real time, suspicious patterns auto-blocked. One afternoon, their inference provider hits capacity limits. Fraud scoring slows from 50ms to 800ms. To keep checkout flowing, the system loosens thresholds. For three hours, fraud that would have been caught slips through. The losses are seven figures. The post-mortem reveals: no one knew the model had degraded. The dashboard showed “system operational.” The SLA covered uptime, not inference quality.

Ambient changes the failure profile.

*Reliability becomes existential.* If it’s always on, it can’t be “mostly right.” Failure modes tolerable in occasional-use systems become unacceptable.

*Governance becomes operational.* The question isn’t “did we check the compliance box?” It’s “can we explain what it did and why, in real time, at scale?”

*Downtime becomes political.* When people depend on inference being there, outages stop being technical incidents.


## **What This Means For You**

**If you build product:**

Model capability is commoditizing. Multiple providers offer frontier-class models, and the gap narrows every few months. What’s not commoditized: reliability at scale, state management, integration depth.

Your moat is shifting to the stack above the model: how you manage context, how you handle failure, how you maintain coherence over time. Product roadmaps need a state strategy—not “what model do we use?” but “how do we persist, version, recover, and audit the working memory our system accumulates?”

**If you buy AI:**

Vendor evaluation changes. Model benchmarks matter less than: What are the contract terms? What’s the SLA? What happens when they’re capacity-constrained—do you get allocation, or do you get queued?

If your vendor gets allocation-constrained, your product becomes a queue. You discover too late whether you have routing flexibility or exit terms. (This is the scenario we walked through earlier—and it’s already happening.)

The questions that matter: Can you port workloads to a second source without rebuilding? What’s your fallback when your primary vendor is tight? Do you have the contract leverage to get priority allocation, or are you just another customer in the queue?

**If you work in the system:**

Your job is changing shape. If AI becomes continuous, someone has to supervise it.

A fraud detection system runs continuously, scanning transactions, flagging anomalies, auto-blocking suspicious patterns. The human role isn’t “review every transaction.” It’s: set the policy thresholds, monitor the behavior dashboards, handle exceptions, review incident logs, adjust and retrain.

The org artifact isn’t just “system uptime.” It’s an incident log for AI behavior—a record of what the system did, why, and what humans did in response.

This isn’t “prompt engineering.” It’s operations. The skill set is policy design, anomaly detection, rollback procedures, audit review. If you’re building a career, the durable skill isn’t “talk to AI better.” It’s “keep AI systems running safely at scale.”


## **The Constraints That Gate the Factory**

Memory gates compute. Packaging gates assembly. Power gates buildout. State gates efficiency.

These constraints don’t disappear when the cost curve drops. They shift. The factory gets more efficient. The inputs remain scarce.


## **The Posture Shift**

A faster chip you can’t get enough of loses to a slower chip you can actually deploy.

The gating factor for “AI everywhere” isn’t better demos. It’s factory buildout.

The gut check:

If your plan assumes GPUs are the constraint, name your HBM lane.

If your plan assumes cloud supply is elastic, name your contract duration and exit terms.

If your plan assumes context is free, show where state lives at 10× your current traffic.

If you can’t answer those questions, the plan isn’t ready.

The teams that understood this shift a year ago locked capacity. The teams that didn’t are now waiting in queues—or discovering that their vendor can’t deliver what they promised. The gap between “has a strategy” and “has allocation” is about to become very visible.

Sources: <https://www.perplexity.ai/search/build-me-a-complete-report-tha-CM.g2MUeQZOJ0O0tiTW1Tw?sm=r#0>

[![](https://substackcdn.com/image/fetch/$s_!4PZE!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6c3e5e54-a1c3-45c8-a9cd-4193dcd69607_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!4PZE!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6c3e5e54-a1c3-45c8-a9cd-4193dcd69607_1024x1024.png)
