---
title: "Executive Briefing: The Global Inference Crisis — Why AI Compute Runs Out Before Your Roadmap Does"
author: "Nate Jones"
published: 2026-02-08
url: https://natesnewsletter.substack.com/p/executive-briefing-the-global-inference
subtitle: "Watch now | We built an economy that runs on AI. There isn’t enough compute to run it."
audience: everyone
scraped_at: 2026-02-08 12:00:17
---

Your CFO approved the AI budget six months ago. The pilots worked. The rollouts are underway. And now someone in procurement is telling you that the inference capacity you need for Q3 doesn’t exist — not at your current vendor, not at the backup, not at any price you’d previously considered reasonable.

The enterprises getting hit hardest aren’t the ones who skipped AI planning — they’re the ones who planned well and are discovering that the infrastructure they need doesn’t exist in sufficient quantities.

Over the past three years, a growing share of enterprise software, customer-facing services, and knowledge work has become dependent on AI capabilities — capabilities that run on inference compute. That compute is now physically constrained. DRAM contract prices are rising 90-95% in a single quarter. The GPUs your workloads need are sold out to hyperscalers through multi-year commitments. And the new fabrication capacity that’s supposed to fix this won’t arrive at meaningful scale until late 2027 at the earliest.

The demand side isn’t waiting. At AI-forward enterprises, consumption is approaching 10x annual growth. Agentic systems — AI calling AI in automated loops — are compounding that curve in ways most capacity plans haven’t accounted for. Google disclosed that it now processes 1.3 quadrillion tokens per month, up 33% from just months earlier. That’s your leading indicator for where enterprise consumption is heading.

The hyperscalers who sell you compute are also your competitors for it. Google needs GPUs for Gemini. Microsoft needs them for Copilot. Amazon needs them for its own AI products. When supply is scarce, they will prioritize themselves. They already are.

This briefing is about what that means for your enterprise and what to do about it in the next 6-12 months.

**This briefing covers:**

- **The demand shock.** Why enterprise AI consumption is growing by orders of magnitude — and why agentic systems break every existing capacity model.
- **The supply wall.** Memory, fabrication, and GPU constraints that won’t resolve before late 2027, and why new domestic capacity doesn’t help you now.
- **The pricing reckoning.** Why inference costs will spike 2-3x (not rise gradually), and what that does to margins across every business model.
- **The geopolitical dimension.** Concentration risk in Taiwan, South Korea, and the Netherlands — and why reshoring is a decade-long fix for a near-term crisis.
- **Why traditional planning fails.** Capex traps, depreciation illusions, and committed-use agreements that become anchors when demand is unpredictable.
- **The strategic playbook.** Six principles for securing capacity, building routing intelligence, and maintaining optionality through the crisis.
- **Scenarios and equilibrium.** What the next 36 months look like under base, severe, and optimistic cases — and what the world looks like when supply catches up.

Let me walk you through the numbers, the constraints, and what I think the playbook looks like from here.


## **The demand nobody planned for: what a billion tokens** ***actually*** **means**

Start with what’s actually being consumed, because the numbers are larger than most planning teams realize.

A knowledge worker using AI tools aggressively — code completion, document analysis, research assistance, meeting summarization, email drafting — consumes roughly one billion tokens per year. That’s the current baseline for heavy users at AI-forward enterprises.

One billion tokens sounds like a lot. It isn’t. A single complex analysis task — “review these 50 documents and synthesize the key findings” — can consume 500,000 tokens. A day of active coding with AI assistance runs 2-5 million tokens. A research session with multiple iterations and refinements might burn 10 million tokens before lunch.

And consumption is growing, not stabilizing.

Three dynamics are driving acceleration:

- **Capability unlocks usage.** As models improve, users find new applications. Features that didn’t work well enough a year ago — complex reasoning, multi-step planning, nuanced creative work — now work. Every capability improvement creates new demand.
- **Integration multiplies touchpoints.** AI is no longer a standalone tool you open when you need it. It’s embedded in email clients, document editors, development environments, CRM systems, analytics platforms. Each new integration point creates ambient, continuous consumption that most organizations aren’t tracking.
- **Agents compound everything.** The shift from human-in-the-loop to agentic systems — where AI calls AI in automated loops — represents a step change in consumption. A single agentic workflow can consume more tokens in an hour than a human user generates in a month.

Based on the growth rates I’m seeing at AI-forward enterprises, per-worker consumption could reach 10 billion tokens annually within 18 months. That’s not a ceiling prediction — it’s an extrapolation from what’s already happening in organizations that have moved aggressively on AI integration. Some are already approaching these levels in specific roles. Your mileage will vary based on how deeply AI is embedded in your workflows, but the direction is consistent across every enterprise I’m tracking.


### **The math that breaks your budget**

A 10,000-person organization at 1 billion tokens per worker consumes 10 trillion tokens annually. At blended API rates — which currently range from roughly $1 to $5 per million tokens depending on model tier, input/output mix, and how much frontier capability your workloads require — that’s somewhere between $10 million and $50 million per year. Use $2-3 per million as a planning midpoint if your workloads are a mix of frontier and mid-tier models, but the math scales linearly: plug in your actual blended rate and the picture gets precise fast.

At 10 billion tokens per worker, that same organization consumes 100 trillion tokens annually — $100 million to $500 million per year depending on blended rate. At 100 billion tokens per worker, which agentic systems could plausibly reach, the math crosses into the billions. The exact number matters less than the shape of the curve: consumption is growing by orders of magnitude, and pricing is not falling fast enough to compensate.

But these calculations assume stable pricing and available capacity. Neither assumption will hold.


### **When AI starts consuming AI**

The agentic shift deserves special attention because it changes the consumption model fundamentally.

Human users have natural rate limits. They type at a certain speed, take breaks, attend meetings, go home. A human cannot sustain more than perhaps 50-100 million tokens per day of AI interaction, even working intensively.

Agents have no such limits. An agentic system running continuously — monitoring, analyzing, responding, planning — can consume billions of tokens per day. A fleet of agents working in parallel can consume trillions.

This isn’t hypothetical. Enterprises are already deploying agentic systems for code review, security monitoring, customer service, document processing, and workflow automation. Each deployment creates sustained, 24/7 inference demand that dwarfs what human users generate.

The enterprises planning for “1 billion tokens per worker” are planning for the wrong curve. They need to plan for the workers plus the agents those workers deploy plus the agents the enterprise deploys centrally. The total consumption footprint is potentially 10-100x the per-human calculation.


### **Google’s canary**

One data point crystallizes the trajectory.

In a recent enterprise keynote, Sundar Pichai disclosed that Google now processes 1.3 quadrillion tokens per month across its services — up from 980 trillion announced just months earlier. That’s roughly a 33% increase in monthly token volume at a company already operating at a scale most enterprises can’t comprehend. Google is the world’s most sophisticated operator of AI infrastructure, with more visibility into demand patterns than anyone. Their consumption curve is your leading indicator.

If the world’s largest and most capable AI operator is adding hundreds of trillions of tokens per month to an already staggering base, enterprises planning for stable consumption are planning for a world that doesn’t exist.


## **The Wall**


### **Memory is the binding constraint**

For most large-model inference at scale, the binding constraint is memory — specifically, high-bandwidth memory (HBM) for datacenter inference and DDR5 for everything else. The size of model you can run, the speed at which you can run it, and the number of concurrent users you can serve are all gated by memory bandwidth and capacity.

I’ve been watching memory markets for the past year, and what’s happening now is unlike any cycle I’ve tracked. The memory market is broken.

Server DRAM prices rose approximately 50% through 2025, according to TrendForce’s pricing data. Their Q1 2026 forecast has since been revised sharply upward — from an already aggressive 55-60% quarter-over-quarter increase to 90-95% QoQ for conventional DRAM contracts. DRAM contract pricing is a component cost, not a total-system number, but it’s the most volatile input in the inference stack right now. By mid-2026, memory costs alone will likely be more than double what they were eighteen months prior — and they’re pulling total infrastructure costs up with them.

DDR5 64GB RDIMM modules — the workhorse of enterprise datacenter deployment — could cost twice as much by end of 2026 as they did in early 2025. Counterpoint Research projects DRAM prices overall to rise 47% in 2026 due to “significant undersupply in both traditional and legacy DRAM markets.”

This isn’t a typical cyclical shortage. Three structural factors make it different:

- **Capacity reallocation.** Samsung, SK Hynix, and Micron — who control roughly 95% of global DRAM production — are systematically reallocating manufacturing capacity from consumer and enterprise segments to AI datacenter customers. They’re not producing less memory; they’re producing different memory, and the hyperscalers are buying all of it.
- **HBM concentration.** High-bandwidth memory, essential for large model inference, is a specialized product with limited manufacturing capacity. SK Hynix dominates HBM production. Their output is allocated to NVIDIA, AMD, and the hyperscalers years in advance. Enterprise buyers cannot access HBM in meaningful volumes outside of NVIDIA systems or hyperscaler channels — it’s effectively allocated before it reaches enterprise procurement.
- **New capacity takes years.** A new DRAM fabrication facility costs $15-20 billion and takes 3-4 years to construct and ramp. Decisions being made today won’t produce chips until 2029-2030. There is no near-term supply response possible.

Wonjin Lee, president and head of global marketing at Samsung Electronics, told Bloomberg that memory chip shortages driven by AI demand and capacity shifts will affect pricing “industry-wide” in 2026. That’s the world’s largest memory manufacturer telling you, on the record, that they cannot meet demand.


### **One company, one island**

Below memory sits the semiconductor fabrication layer, which is even more constrained.

TSMC manufactures the world’s most advanced chips, including NVIDIA’s datacenter GPUs. Their advanced nodes (5nm, 4nm, 3nm) are fully allocated. NVIDIA is their largest customer. Apple is second. The hyperscalers fill out the rest.

TSMC’s capacity expansion is proceeding. Their Arizona Fab 1 is expected to begin 4nm production in the first half of 2025. Fab 2 volume production is now tracking to the second half of 2027, ahead of earlier 2028 estimates. But “production begins” and “meaningful capacity available to enterprise buyers” are different milestones — early output is limited, yields ramp slowly, and hyperscalers have first claim on allocation. New facilities in Japan and Germany are on similar multi-year timelines.

Intel’s 18A process, demonstrated at CES 2026, represents the first credible American alternative to TSMC’s leading edge. But Intel’s foundry services are unproven at scale, their capacity is limited, and their first major customers (Microsoft, among others) will absorb initial allocation.

Samsung’s foundry business has struggled with yields on advanced nodes, making them a less reliable alternative for cutting-edge AI chips.

The result: essentially all advanced AI chip production runs through a single company, TSMC, located in Taiwan. There is no surge capacity, no alternative supplier, and no short-term fix — not at any timeline that helps you this year.


### **GPUs are sold out**

NVIDIA dominates the datacenter AI accelerator market, with estimated market share above 80% of GPU shipments for training and inference workloads. Their H100 and newer Blackwell GPUs are the de facto standard.

Both are sold out.

Lead times for large GPU orders exceed six months. The hyperscalers have locked up allocation through multi-year purchase agreements worth tens of billions of dollars. Microsoft, Google, Amazon, Meta, and Oracle have collectively committed to hundreds of billions in NVIDIA purchases over the next several years.

Enterprise buyers are left with whatever allocation remains — which, increasingly, is not much.

NVIDIA’s H200 and Blackwell GPUs, which offer significant performance improvements, are even more constrained. Initial production runs are fully allocated to hyperscalers. Enterprise availability in volume is uncertain.

The alternatives are limited:

AMD’s Instinct MI300X is competitive on specs and available in somewhat larger quantities, but ROCm software ecosystem maturity lags CUDA significantly. Enterprises switching to AMD face substantial software porting costs.

Intel’s Gaudi accelerators have struggled to gain market share despite competitive pricing. Software support and ecosystem adoption remain challenges.

Custom silicon from hyperscalers — Google’s TPUs, Amazon’s Trainium and Inferentia, Microsoft’s Maia — is not available to enterprises. It’s built for internal use.

Inference-specific chips from startups like Groq, Cerebras, and SambaNova offer efficiency advantages for certain workloads, but production volumes are small and long-term viability is uncertain.

None of these alternatives changes the fundamental picture: the GPUs that enterprises need are controlled by companies that have every incentive to use them internally rather than sell them.


### **Your cloud provider is your competitor**

This is the piece that most analyses miss.

AWS, Azure, and Google Cloud are not neutral infrastructure providers. They are AI product companies that happen to also sell infrastructure. They compete directly with their enterprise customers.

Google uses its compute allocation to power Gemini, which competes with every enterprise AI deployment. Microsoft uses its allocation for Copilot, which competes with every enterprise productivity AI. Amazon uses its allocation for Alexa and AWS AI services, competing across the board.

When compute is abundant, this conflict of interest is manageable. The hyperscalers can serve their own needs and sell excess capacity to enterprises. Everyone wins.

When compute is scarce, the conflict becomes zero-sum. Every GPU allocated to an enterprise customer is a GPU not available for Gemini, Copilot, or Alexa. The hyperscalers must choose between their own products and their customers.

They will choose their own products. They already are.

The pattern is visible in how providers manage access. API pricing has fallen over the past two years, but rate limits haven’t loosened proportionally. Enterprise buyers I’ve spoken with report increasing difficulty getting firm allocation commitments for high-volume deployments. “Contact sales” has become the standard response to capacity requests above certain thresholds — which tells you something about what’s available on the shelf.

The hyperscalers are not being villains here. They’re being rational. Their AI products are strategic priorities with internal champions and executive visibility. Selling capacity to enterprises is a business, but it’s not the business their leadership is measured on.

Enterprise CTOs need to internalize this: the cloud providers are not your partners in this crisis. They are competitors who control the scarce resource you need.


## **The pricing reckoning: Why prices spike, not rise**

In theory, tightening supply produces gradual price increases until demand moderates and equilibrium returns. That’s the textbook version. What actually happens in severely constrained markets is uglier.

When supply cannot respond to demand, and demand cannot be deferred, prices spike. Buyers bid against each other, willing to pay premiums for scarce allocation. Sellers, seeing the desperation, raise prices not to equilibrium but to extraction.

We’ve seen this before. DRAM contract prices saw multiple-fold increases during the 2016-2018 shortage, with some segments more than doubling over the cycle. GPU prices doubled during the crypto mining boom and pandemic gaming surge. Memory prices are notoriously volatile because the supply side is inelastic — you cannot quickly produce more chips when demand spikes.

The current situation has all the ingredients for a severe spike:

- **Supply is inelastic.** No new fabs until 2028-2029. No capacity reallocation possible in the short term.
- **Demand isn’t going anywhere either.** Enterprises have committed to AI transformations. Turning back is not an option. They will pay whatever is necessary to continue.
- **The information gap favors sellers.** The hyperscalers know exactly how constrained supply is. Enterprises don’t. This allows sellers to extract maximum prices from buyers who don’t realize how bad the situation is.
- **And coordination is easy when there are only four players.** Three major memory suppliers and one dominant GPU supplier. Tacit pricing coordination is straightforward — no antitrust violation required, just rational profit maximization by oligopolists facing unlimited demand.


### **The numbers**

TrendForce’s February 2026 revision projects conventional DRAM contract prices rising 90-95% quarter-over-quarter in Q1 2026 — a sharp upgrade from their earlier 55-60% forecast. Server DRAM, which accounts for a disproportionate share of inference infrastructure cost, is expected to rise at least as fast. These are component costs, not total system costs — but when your largest variable input nearly doubles in a single quarter, the total follows.

If these projections hold through H1 2026, memory costs alone will have roughly doubled from early 2025 levels.

GPU pricing is harder to track because NVIDIA doesn’t publish list prices and actual transaction prices vary by customer and volume. But anecdotal evidence suggests datacenter GPU pricing has risen 20-40% over the past year, with steeper increases for priority allocation.

Inference API pricing from hyperscalers has actually fallen in nominal terms — GPT-4 class capabilities cost a fraction of what they did two years ago. But this masks several factors:

- **Quality-adjusted pricing is rising.** The frontier has moved. The cheapest models today are roughly equivalent to premium models from 18 months ago. But enterprises don’t want 18-month-old capabilities; they want frontier. Frontier pricing remains stubbornly high.
- **Rate limits constrain effective access.** You can access cheap inference — just not much of it. The enterprises that need volume are increasingly pushed toward “enterprise” tiers with higher pricing and committed volumes.
- **Hidden costs compound.** Data egress, fine-tuning, retrieval augmentation, orchestration — the per-token price is only part of the total cost. As providers optimize revenue, expect these adjacent costs to rise.

A reasonable central estimate: effective inference costs for enterprises at scale will rise 2-3x over the next 18 months. A severe scenario — sustained supply constraints combined with demand acceleration — could see 4-5x increases.


### **Every business model is exposed**

The impact of rising inference costs depends on your business model.

I want to be careful not to overstate the margin impact — it varies enormously by business model and usage pattern. But the direction is consistent across every company I’m talking to.

AI-native startups are most exposed. Notion’s CEO has publicly described AI features as “margin dilutive” — a remarkable admission from a company that built its business on SaaS gross margins north of 80%. The specific impact varies by product and usage pattern, but the dynamic is consistent across AI-native companies: every AI feature your users love is inference cost your margins absorb. If inference costs double, the business models that assumed cheap compute become structurally unsound.

Enterprise software companies building AI features face similar pressure. AI is a competitive requirement — customers expect it — but every AI feature erodes margin. Companies must choose between competitive necessity and financial sustainability.

Enterprises using AI internally have more flexibility. If AI creates value, the cost increase may be justified. But budget scrutiny will intensify. AI projects that were approved at one cost level may be canceled at twice that cost.

Hyperscalers themselves are somewhat insulated by vertical integration — they own the infrastructure that’s becoming scarce. But even they face constraints. Google, Microsoft, and Amazon are all warning investors about rising AI infrastructure costs.

The companies most at risk are those in the middle: too dependent on AI to abandon it, not large enough to secure dedicated allocation, and competing in markets where passing through cost increases is difficult.


## **The chokepoints: Four points of failure**

The global AI supply chain runs through a remarkably small number of chokepoints.

- **Taiwan:** TSMC manufactures essentially all advanced AI chips. Their fabs are located in a country that China claims as its territory, across a strait that represents one of the world’s highest-risk flashpoints for great power conflict.
- **South Korea:** Samsung and SK Hynix control approximately 70% of global DRAM production and an even higher share of HBM. Both are located within artillery range of North Korea.
- **Netherlands:** ASML is the sole manufacturer of EUV lithography equipment, without which advanced chips cannot be produced. A single fire, earthquake, or supply chain disruption could halt global semiconductor advancement.
- **United States:** NVIDIA, AMD, and Intel design the chips, but all depend on Asian manufacturing. The U.S. has no volume production capacity for leading-edge logic semiconductors.

This concentration was an acceptable risk when AI was a niche application. It is not acceptable when AI is infrastructure.


### **Reshoring won’t save you in time**

Governments have recognized the risk. The U.S. CHIPS and Science Act provides $52 billion in subsidies and incentives for domestic semiconductor manufacturing. The European Chips Act commits €43 billion. Japan, South Korea, and others have similar initiatives.

New capacity is being built:

- **TSMC Arizona:** Two fabs, $40+ billion investment. Fab 1 targeting 4nm production beginning in 1H 2025; Fab 2 volume production now expected in 2H 2027 based on current reporting, ahead of earlier 2028 targets.
- **Intel Ohio:** Two fabs, $20 billion initial investment with potential expansion to $100 billion. Expected production in 2027-2028.
- **Samsung Texas:** $17 billion fab under construction. Production expected in 2026.
- **Micron Idaho and New York:** $100+ billion committed over the next two decades for memory production.

These investments are significant, but they don’t solve the near-term problem:

- **Timelines extend beyond the acute crisis.** Most new capacity won’t be fully operational until 2027-2028. The supply crunch is happening now.
- **Ramp-up takes years.** Even after a fab opens, it takes 12-24 months to achieve full yield and volume production. Early output is limited and expensive.
- **Capacity is already allocated.** The hyperscalers that depend on these fabs are locking up output before the fabs open. Enterprise buyers will not see meaningful allocation from new domestic capacity until late in the decade.
- **Cost structures are higher.** U.S. and European manufacturing costs significantly exceed Asian costs due to labor, energy, and regulatory factors. Domestic chips will be more expensive, likely 20-40% at a minimum.

Reshoring is a strategic imperative for national security. It is not a solution to the immediate supply crisis.


### **The Taiwan question**

No analysis of AI infrastructure can ignore the Taiwan question.

A Chinese blockade or invasion of Taiwan would instantly remove the majority of the world’s advanced chip production from the market. Not gradual reduction — complete cessation.

Every AI system dependent on new GPU and accelerator production would face indefinite delays. Existing chips would continue to operate, but expansion would be impossible. Prices for available hardware would spike to multiples of current levels.

The economic consequences would dwarf any supply chain disruption in modern history. We’re not talking about a chip shortage; we’re talking about the collapse of the technology infrastructure that the global economy depends on.

Is this scenario likely? Most analysts assess it as low probability in the near term. But “low probability” is not “zero probability,” and the consequences are catastrophic. Enterprise risk planning must account for tail scenarios, not just central cases.

Practical implications for enterprises:

**Inventory buffers matter.** Enterprises with existing hardware have resilience that those dependent on just-in-time procurement do not. There’s an argument for maintaining larger-than-efficient hardware reserves as insurance.

**Geographic diversification matters.** Capacity from Intel, Samsung, and emerging foundries provides optionality that TSMC-only supply chains lack. Pay the premium for diversification.

**Model efficiency matters.** The more you can accomplish with less compute, the more resilient you are to supply disruptions. Invest in optimization and efficiency, not just capability.


## **Why your planning framework is wrong**

I keep coming back to why traditional planning fails here, and I think it’s because the failure isn’t in the math — it’s in the assumptions underneath the math.


### **The capex trap**

Enterprise IT planning evolved for a different era.

The traditional model: assess requirements, procure infrastructure, depreciate over 3-5 years, extract value, refresh. This works when demand is predictable, technology is stable, and supply is available.

None of these conditions hold for AI infrastructure.

**Demand is unpredictable.** Consumption growth of 10x annually means any forecast is obsolete within months. Planning for this year’s demand guarantees inadequacy for next year.

**Technology is unstable.** Model architectures, hardware capabilities, and efficiency improvements are advancing rapidly. Infrastructure purchased today may be architecturally obsolete within 18-24 months.

**Supply is constrained.** You cannot simply purchase more infrastructure when demand exceeds capacity. The infrastructure may not be available at any price.

The capex model worked for servers, storage, and networking because those technologies were mature, demand was predictable, and supply was elastic. AI infrastructure has none of these characteristics.

CTOs who apply traditional planning frameworks to AI infrastructure will systematically make bad decisions. They’ll over-commit to long-term purchases that become stranded assets. They’ll under-invest in flexibility and optionality. They’ll assume supply availability that doesn’t exist.


### **The depreciation illusion**

Consider a concrete example.

An enterprise purchases 1,000 AI workstations with NPU capabilities at $5,000 each — a $5 million capital investment. Finance sets a 4-year depreciation schedule. IT expects to extract $1.25 million per year in value.

By year two, these workstations cannot handle the workload. Per-worker consumption has grown 10x. The NPUs that were adequate for code completion and document summarization cannot sustain agentic workflows consuming billions of tokens. The machines aren’t broken; they’re obsolete.

You’ve got three options, and only one of them works.

- **Option A:** Continue using inadequate hardware. Workers are constrained. Productivity lags. Competitors with better infrastructure pull ahead. The “savings” from extending the depreciation schedule cost more in lost productivity than new hardware would.
- **Option B:** Purchase new hardware before depreciation completes. The enterprise takes a write-down on stranded assets. The $5 million investment yields perhaps $2 million in value. Finance is unhappy.
- **Option C:** Lease instead of buy. The enterprise pays a premium — lessors aren’t charities — but transfers depreciation risk. When workstations become obsolete, they go back to the lessor rather than sitting on the balance sheet.

Option C is the correct answer for most enterprises. But it requires abandoning capex models that finance teams have used for decades.


### **Committed-use agreements are traps**

Cloud providers offer substantial discounts for committed use agreements. Multi-year commits can reduce effective pricing by 30-50% compared to on-demand rates.

At 10x annual demand growth, these commits are traps.

- **Scenario 1: You under-commit.** You estimate 10 trillion tokens for the year, commit to that level, and get the discount. Actual consumption is 30 trillion tokens. You pay on-demand rates for the overage — exactly the expensive pricing you tried to avoid. The “discount” becomes a floor, not a ceiling.
- **Scenario 2: You over-commit.** You estimate 30 trillion tokens, commit aggressively. Actual consumption is 15 trillion — perhaps because a key project was delayed, or efficiency improvements reduced demand. You pay for 30 trillion regardless. Half your spend is waste.
- **Scenario 3: You commit accurately.** This requires predicting AI consumption, AI capability improvements, efficiency gains, business project timelines, and workforce changes — all in an environment where every variable is changing rapidly. The probability of accurate prediction is near zero.

The expected value of committed use agreements is negative when demand uncertainty is high. Enterprises are better off paying premium on-demand rates and preserving flexibility than locking in “discounts” that become anchors.


### **Lock-in is dangerous when supply is scarce**

Every AI infrastructure decision creates lock-in. The question is how much and to whom.

- **Hardware lock-in:** GPUs from different vendors require different software stacks. CUDA for NVIDIA, ROCm for AMD, OpenVINO for Intel. Models optimized for one platform don’t run efficiently on others. Switching costs are substantial.
- **Cloud lock-in:** Each hyperscaler has proprietary services, APIs, and tooling. Data gravity accumulates — once your training data, models, and workflows are in one cloud, moving them is expensive and risky.
- **Model lock-in:** Fine-tuned models, prompt libraries, and workflows are built around specific foundation models. Switching from GPT to Claude to Gemini requires rebuilding, not just reconfiguring.

In a stable supply environment, some lock-in is acceptable. You pick a vendor, build on their stack, and extract efficiency from deep integration.

In a constrained supply environment, lock-in is dangerous. If your sole vendor cannot provide capacity, you’re stuck. No amount of escalation or premium pricing will produce GPUs that don’t exist.

The enterprises that survive the inference crisis will be those with optionality: the ability to shift workloads between vendors, clouds, and hardware platforms as capacity dictates. This requires deliberate investment in portability — multi-cloud architectures, abstraction layers, vendor-agnostic tooling — that adds cost and complexity in the short term.


## **What to do about it**


### **Secure capacity before you need it**

The single highest-impact action an enterprise can take is securing inference capacity commitments now, before the crisis peaks.

“Securing capacity” does not mean signing a committed use agreement at a certain dollar level. It means obtaining contractual guarantees of throughput — specific token volumes per day/month/year, with SLAs for availability.

The conversation with vendors should shift from “what’s your price per million tokens?” to “can you contractually guarantee us 10 billion tokens per day, sustained, with 99.9% availability?” If the vendor cannot make that commitment, their pricing is irrelevant.

Tactics:

- **Audit current consumption and project forward.** Understand your actual token usage across all workloads, by business unit, by application. Project forward at 5x and 10x annual growth. Know the numbers before negotiating.
- **Engage vendors at senior levels.** Capacity allocation decisions are made at executive levels, not by sales teams. If you’re negotiating with account managers, you’re not having the real conversation.
- **Be willing to commit volume to get capacity.** Vendors will prioritize customers who commit volume. The paradox: committed use agreements are generally disadvantageous (see above), but capacity guarantees may require them. Negotiate capacity guarantees in exchange for volume commits, not discounts.
- **Diversify across providers.** No single vendor can guarantee the capacity large enterprises will need. Spread allocation across multiple hyperscalers, inference providers, and on-premises options. Accept the complexity cost for the resilience benefit.
- **Consider strategic relationships.** For enterprises with sufficient scale, direct relationships with NVIDIA, AMD, or memory suppliers may be possible. These bypass the hyperscaler intermediary and provide more control over allocation — but require volume commitments that only large enterprises can make.


### **Build the routing layer**

The most durable competitive advantage in this environment is the intelligence layer that decides where workloads run.

A sophisticated routing system can:

- **Optimize cost.** Route queries to the cheapest provider capable of handling them. Use expensive frontier models only when necessary; default to cheaper alternatives when they suffice.
- **Manage capacity.** Automatically shift workloads when one provider is capacity-constrained or experiencing latency issues. Maintain service even when individual providers fail.
- **Preserve optionality.** Abstract the underlying infrastructure so that switching providers requires configuration changes, not code rewrites.
- **Strengthen your negotiating position.** Vendors know you can shift spend to competitors. This changes the dynamic entirely.
- Building this layer requires investment:
- **Architecture.** A routing layer must sit between applications and inference providers, handling request transformation, response normalization, error handling, and retry logic. This is meaningful engineering work.
- **Model evaluation.** Intelligent routing requires knowing which models can handle which tasks adequately. This requires ongoing evaluation and benchmarking as models evolve.
- **Observability.** You need to know what you’re consuming, where, at what cost, with what latency and quality. Per-query telemetry is essential.
- **Team.** This isn’t a one-time build; it’s ongoing infrastructure that requires dedicated engineering capacity to maintain and improve.

Do not outsource this capability to a vendor. Any vendor that provides routing will use it to lock you into their stack. The routing layer is how you maintain independence; ceding it defeats the purpose.


### **Treat hardware as consumable**

Any hardware purchased for AI workloads should be mentally depreciated within 18-24 months, regardless of accounting treatment.

If the ROI calculation doesn’t work at that depreciation rate, don’t purchase.

For workstations and edge devices:

- **Lease where possible.** 24-month lease terms align with the actual useful life of AI-capable hardware. Let the lessor eat the depreciation risk.
- **If purchasing, use accelerated depreciation schedules** that reflect reality rather than accounting convention. Write off AI hardware in 2-3 years, not 4-5.
- **Plan for refresh cycles** that coincide with hardware generations. Every 18-24 months, new NPU and GPU architectures arrive with meaningful capability improvements. Plan to be on them.
- For datacenter infrastructure:
- **Prefer cloud or colo over owned datacenters.** The flexibility to scale down is as valuable as the ability to scale up when technology changes rapidly.
- **If building on-premises capacity, design for modularity.** Individual rack units should be replaceable without stranding the whole facility.
- **Consider inference-as-a-service providers** (CoreWeave, Lambda, etc.) as alternatives to owning GPUs. You pay a premium for not owning the hardware, but you also don’t get stuck with stranded assets when the next architecture arrives.


### **Efficiency is a competitive advantage**

In a supply-constrained environment, efficiency is a competitive advantage.

Every token you don’t consume is capacity available for additional workloads. The enterprise that can accomplish the same tasks with 50% fewer tokens has twice the effective capacity of one that can’t.

- **Model selection:** Use the smallest model capable of each task. Frontier models are necessary for some workloads; they’re wasteful for others. Systematic model selection based on task complexity can reduce consumption by 50-80% without quality degradation.
- **Prompt engineering:** Well-designed prompts produce results in fewer tokens. Poorly designed prompts waste tokens on irrelevant output, clarifying questions, and retries. Invest in prompt optimization as an engineering discipline.
- **Caching:** Many inference requests are similar or identical. Caching responses to repeated queries can eliminate 20-40% of inference demand with no quality impact.
- **Retrieval augmentation:** Embedding-based retrieval is orders of magnitude cheaper than inference. Architectures that use retrieval to reduce context length and inference demands can achieve dramatic cost savings.
- **Quantization and distillation:** Smaller, quantized models can match larger model performance on specific tasks at a fraction of the compute cost. Invest in model optimization for your specific workloads.

These efficiency investments have traditionally been lower priority than capability investments. In a constrained environment, they become critical. The enterprise that achieves 10x efficiency improvement has, effectively, secured 10x more capacity.


### **Diversify everything**

Concentration is risk. Diversify along every axis.

- **Cloud providers:** Spread workloads across AWS, Azure, and Google Cloud. Add secondary providers (Oracle, IBM, specialized inference providers) for additional optionality. Accept the management overhead as the cost of resilience.
- **Hardware platforms:** Qualify workloads on NVIDIA, AMD, and Intel hardware where possible. The software porting cost is real, but so is the risk of being locked to a single supplier’s allocation constraints.
- **Chip architectures:** x86 is not the only option. Arm-based inference (AWS Graviton, Apple Silicon, Qualcomm) may offer availability when x86 allocation is constrained. Specialized inference chips (Groq, Cerebras) offer efficiency advantages for specific workloads.
- **Geography:** Ensure capacity in multiple regions. U.S., European, and Asian availability provides resilience against regional disruptions, regulatory changes, or geopolitical events.
- **Model providers:** Qualify workloads on OpenAI, Anthropic, Google, and open-source models. When one provider faces capacity constraints or changes terms, you need alternatives.

This diversification is expensive. Multi-cloud architectures cost more to build and operate than single-cloud. Multi-platform software requires more engineering investment. Multi-region deployment adds latency and complexity.

The expense is insurance. When the crisis hits — and it will — the enterprises with optionality will be able to continue operating. Those without it will be hostage to whatever capacity their single vendor can provide.


### **Make sure your leadership understands**

None of the playbook above works if your CFO thinks AI costs are stable and your board thinks this is an IT problem.

**For the CFO:**

*The mental model shift:* AI infrastructure is a utility, not an asset class. You don’t buy it; you buy capacity. The cost scales with consumption. Traditional capex planning doesn’t apply.

*The budget reality:* AI infrastructure costs will not be stable. Plan for 2-3x increases over the next 18 months as supply constraints bite. Build contingency into budgets.

*The investment case:* Securing capacity now, even at premium prices, may be cheaper than trying to acquire it later when supply is even more constrained. Early investment has option value.

**For the CEO and board:**

*The competitive stakes:* Enterprises with AI capacity will be able to operate and innovate. Those without it will fall behind. This is not an IT decision; it’s a strategic decision about the company’s ability to compete.

*The timeline:* The window to secure capacity is closing. Decisions made in the next 6-12 months will determine the enterprise’s AI capabilities for the next 3-5 years.

*The uncertainty:* No one can plan this perfectly. The environment is changing too fast. What you can do is preserve flexibility, diversify risk, and position to adapt. That requires accepting uncertainty rather than demanding false precision in forecasts.

**For business units:**

*The consumption accountability:* Per-workload consumption will need to be tracked and budgeted. “AI costs” can no longer be an abstract overhead; they need to be attributed to the workloads that incur them.

*The efficiency imperative:* Wasteful AI usage has real costs. Efficiency improvements have real value. Building efficiency into workflows is not optional overhead; it’s competitive necessity.

*The prioritization reality:* Not all AI use cases can be funded at any price. Enterprises will need to prioritize high-value applications over nice-to-haves. Be prepared to justify consumption against business value.


## **Three scenarios and a black swan**

I’m going to lay out three scenarios and a tail risk. I think the base case is most likely, but I’m genuinely uncertain about timing — the variables are moving faster than my ability to model them.


### **Base case: constrained through 2027**

The most likely scenario: supply remains significantly constrained through 2027, with gradual improvement thereafter as new capacity comes online.

**2026:** Memory prices peak in Q2-Q3 at roughly 2x late-2024 levels. Effective inference costs rise 50-100% from current levels. Capacity allocation becomes more difficult. Enterprises face tough choices about which AI initiatives to fund.

**2027:** New fab capacity begins producing meaningful volume. Memory prices stabilize but remain elevated. Inference costs plateau. Enterprises that secured capacity in 2025-2026 have significant advantage over those scrambling to acquire it.

**2028:** Supply begins to catch up with demand. Prices moderate. The crisis transitions from acute to chronic. New challenges emerge around managing the installed base of AI infrastructure.


### **Severe case: shortage through 2028**

In this scenario, demand growth exceeds supply growth through 2028, sustaining crisis conditions for 3+ years.

**Triggers:** Faster-than-expected agentic adoption accelerates demand. Fab construction delays push new capacity to 2029-2030. Geopolitical disruption constrains key suppliers.

**Implications:** Memory prices could triple from current levels. Effective inference costs could rise 3-5x. Many AI-native business models become unviable. Enterprise AI adoption slows as costs exceed budgets. Market consolidation accelerates as only well-capitalized players can afford to operate.


### **Optimistic case: resolved by late 2026**

In this scenario, supply catches up faster than expected, and the crisis resolves by late 2026.

**Triggers:** Inference efficiency improves faster than expected (new architectures, quantization breakthroughs). Demand growth moderates as initial AI deployments mature. New suppliers enter the market faster than projected.

**Implications:** Price spikes are shorter and less severe. Enterprises that over-prepared may have stranded capacity, but the cost of over-preparation is modest. The competitive scramble for capacity diminishes.


### **Black swan: Taiwan**

The tail risk that transforms the crisis into catastrophe.

**Trigger:** Chinese military action against Taiwan — blockade, invasion, or coercive measures short of war — disrupts TSMC operations.

**Implications:** Global advanced chip supply falls 60%+ overnight. AI development effectively freezes — no new training runs, no new model development, inference capacity fixed at installed base. Existing chips become critical strategic assets. Prices spike to multiples of current levels. Economic disruption extends far beyond tech sector.

**Probability:** Low in any given year. Not zero. The consequences are severe enough to warrant contingency planning even at low probability.


## **What the other side looks like**

The crisis will eventually resolve. What does the world look like when it does?


### **Costs settle higher**

Inference costs will settle at higher levels than the 2023-2024 lows. Several structural factors sustain elevated pricing:

**Memory capacity remains constrained.** Even with new fabs, HBM and high-density DRAM will remain specialized products with concentrated supply. Prices will reflect scarcity value.

**Power constraints emerge.** AI datacenters consume enormous electricity — a single large training run can use more power than a small city. Grid capacity becomes a new bottleneck.

**Margin expectations reset.** Memory and chip suppliers have enjoyed exceptional margins during the shortage. They will resist returning to commodity pricing.

Reasonable expectation: equilibrium inference costs will be 30-50% higher than 2024 levels, even after supply catches up. Budget accordingly.


### **Supply chains restructure permanently**

The crisis will accelerate reshoring and diversification:

**More geographic distribution.** The concentration risk exposed by Taiwan dependence will drive investment in alternative manufacturing locations. By 2030, meaningful advanced chip capacity will exist in the U.S., Japan, and Europe.

**More vertical integration.** Hyperscalers are already designing custom silicon. The crisis will push more enterprises toward similar strategies, reducing dependence on merchant suppliers.

**More strategic stockpiling.** Just-in-time procurement will give way to buffer inventories. Enterprises will hold more hardware than immediate needs dictate as insurance against supply disruption.


### **Who wins and who doesn’t**

The enterprises that emerge strongest will be those that:

**Secured capacity early.** First-mover advantage in locking up allocation translates to operational advantage through the crisis.

**Built efficiency advantages.** The enterprises that learned to do more with less compute have durable competitive advantages even when supply loosens.

**Maintained flexibility.** Multi-vendor, multi-cloud, multi-architecture strategies position enterprises to exploit whatever capacity is available.

On the other side of that line: enterprises that assumed supply would be available when they needed it, that locked into single vendors when it felt efficient, that treated AI as a departmental experiment rather than infrastructure. The crisis will widen the gap between these groups in ways that don’t close easily once supply normalizes.


## **The moment to move**

I want to be honest about the limits of what I can predict here. The timing is uncertain, the severity is uncertain, and there are scenarios where efficiency breakthroughs or demand moderation ease the pressure faster than I expect. But the structural dynamics — exponential demand, flat supply, widening gap through at least 2027 — are not uncertain. They’re already visible in the data.

The playbook in this briefing comes down to six moves: secure capacity before the crisis peaks, build the routing layer that gives you portability, treat hardware as consumable, invest in efficiency as a competitive weapon, diversify across every axis you can, and make sure your leadership understands the environment well enough to fund what needs funding.

The enterprises that act on this will be positioned to operate through the crisis and compete effectively on the other side. Those that don’t will discover the cost of inaction when it’s too late to change course.

I’d start with one thing: audit your actual token consumption this week, by workload and by provider, and project it forward at 5x and 10x. If the numbers surprise you — and they will — that’s your signal that the rest of this briefing applies to your organization. Everything else follows from knowing where you actually stand.

The window is still open, but it’s closing faster than most planning cycles can accommodate. If your organization is going to act, the next two quarters are when it happens.


## [Grab the prompts](https://www.notion.so/product-templates/The-Global-Inference-Crisis-Companion-Prompts-2ff5a2ccb5268076b0bbf053eabe15a8?source=copy_link)

These five prompts force the specific decisions this briefing calls for: what you’re actually consuming, what throughput guarantees to demand, where tokens are bleeding, how to brief your CFO in language that moves budget, and what three different supply scenarios mean for your specific infrastructure. The Inference Capacity Auditor in particular exists because I’ve watched too many procurement conversations collapse when the enterprise couldn’t produce its own consumption numbers — the vendor sets the terms because you showed up without data. If you can’t fill in the blanks these prompts ask for, you’re not ready to negotiate. That’s the point.

[![](https://substackcdn.com/image/fetch/$s_!o-K7!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7655f9ff-2b90-497d-8461-6424dd67e3c6_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!o-K7!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7655f9ff-2b90-497d-8461-6424dd67e3c6_1024x1024.png)
