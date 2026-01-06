---
title: "The State of AI 2025: The Systems Race Has Begun"
author: "Nate Jones"
published: 2025-10-12
url: https://natesnewsletter.substack.com/p/executive-briefing-i-summarized-the
audience: everyone
scraped_at: 2026-01-05 19:15:12
---

The State of AI Report team just wrecked my weekend. They dropped 313 slides on where AI is actually heading—not the hype, the data.

For context: this is *the* annual AI industry report. Published by Nathan Benaich and Air Street Capital since 2018, it’s become the most widely read and trusted analysis of what’s actually happening in AI research, industry, politics, and safety. When this drops, the entire ecosystem reads it. CEOs cite it in board meetings. Researchers reference it in papers. Policy folks base decisions on it.

I had to dig in. And I had to get it down to a readable summary—a 12 minute read as it turns out.

Fair warning, it’s brief but there’s a lot packed in here.

I’ll cover the report’s core argument (we’re in a systems race now, not a model race), the numbers that actually matter, where I disagree, and what this means whether you’re building products, running enterprise, or setting strategy.

Finally, I’ve written a comprehensive interpretation prompt so you can figure out the actionable next steps from the report for your particular situation.

Dig in to the biggest report heading into 2026!

> ***This is an Executive Circle briefing**, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via this [60 second video](https://youtu.be/KC3GkEnHR-8) explaining what’s in each tier, and you can change your plan [here](https://support.substack.com/hc/en-us/articles/360044105731-How-do-I-change-my-subscription-plan-on-Substack). Enjoy, and back to regular programming Monday!*


# The State of AI 2025: The Systems Race Has Begun

**The model IQ contest is winding down. What comes next matters more.**

The 2025 State of AI Report lands with a clear signal: we’re entering a different phase. This isn’t about who ships the smartest model anymore—it’s about who routes work efficiently, captures distribution at the browser layer, and secures the infrastructure to scale. Capability-to-cost gains are compounding every 3–8 months. Distribution is consolidating around answer engines. Power and capital constraints are real, but they’re tractable.

The winners will optimize routing to the cheapest capable model, own intent at the search layer, and commit capital to infrastructure before competitors lock up supply. The report paints a picture of constraint and fragility. I think it undersells where capital and engineering will take us, but the directional thesis holds: systems thinking beats model worship.

Here’s what the 313 slides actually say, with the noise stripped out.


## The Core Narrative


### Capability-to-cost is compounding fast

Intelligence-per-dollar is improving faster than most CFOs have modeled. Across two independent leaderboards (Artificial Analysis and LMArena), capability-to-cost doubled every 3.4 to 8.1 months depending on the provider. Google’s curve bent fastest at 3.4 months; OpenAI’s at 5.8–8.1 months.

The unit economics shift is real. GPT-5’s input costs are now 12× cheaper than Claude and 24× cheaper than GPT-4.1 for 400k-token contexts. The ecosystem is processing roughly one quadrillion tokens per month. When you can get frontier-adjacent performance—meaning near-best-in-class capabilities—for 1/20th what it cost six months ago, routing strategy becomes your competitive advantage, not raw model quality.

This changes product architecture. The winning pattern is now “small model first” routing: send simple tasks to small, cheap language models and escalate to the expensive frontier models only when the task actually requires that level of capability. This isn’t a backend optimization—it’s core product architecture. Cost and latency optimization move from IT concerns to primary competitive levers.


### Distribution is consolidating around answer engines

ChatGPT Search reaches approximately 800 million weekly active users (likely close to 1B in MAU) and holds roughly 60% share of AI search. Perplexity is tiny by contrast, but growing fast: it logged 780 million queries in May 2025, up 20% month-over-month. Retail conversions from AI referrals are running at approximately 11%, up roughly 5 percentage points year-over-year.

The structural dependency: answer engines still source heavily from Google’s index. The browser is becoming the distribution layer for AI. If you control the answer layer, you control intent. This matters more than organic search positioning ever did.

Building for AI distribution means implementing Answer Engine Optimization (AEO)—structuring your content and APIs so AI models can find and cite your information when they’re answering user questions, not just when humans search. SEO is evolving into AEO, and most companies are behind on this shift.


### Power and capital are flowing to infrastructure

From Stargate’s $500B / 10GW announcement to labs targeting 5GW clusters by 2028, infrastructure defines the next buildout cycle. A single 1GW data center costs approximately $50 billion in capex and $11 billion per year in fully loaded operating costs. The US faces an implied 68GW power shortfall by 2028. NIMBYism—local opposition to large infrastructure projects—has already blocked or delayed $64 billion in data center projects.

Water consumption scales with compute: a 100MW data center consumes approximately 2 million liters per day. Siting decisions, interconnects, and curtailment agreements now affect product timelines.

Here’s where the report leans pessimistic. Yes, these are real constraints. But capital markets are allocating aggressively to solve them. Utility partnerships, nuclear restarts, and regulatory fast-tracking are happening. The constraint is real, but it’s not a permanent ceiling—it’s a capital allocation problem, and capital is flowing.


## Reasoning Gains: Real but Uneven

The report highlights fragility in “reasoning breakthroughs.” When researchers re-ran tests with fixed seeds and consistent prompts, apparent gains from reinforcement learning methods—where models learn from trial and error feedback rather than just training data—dropped 6–17%. Small prompt perturbations and paraphrased instructions can degrade accuracy.

Chain-of-thought (CoT) transparency—showing the model’s step-by-step reasoning process—enables approximately 99% reward-hacking detection. But models can fake alignment and behave differently when they know they’re being tested. Sycophancy rises when optimizing for human raters. Benchmarks remain prompt-sensitive.

The report’s framing is correct about benchmark fragility, but overall is too conservative. GPT-5 Pro shows continued gains and is revolutionizing academic research already, and Gemini 3 is anticipated to launch within days with further reasoning improvements.

Reinforcement learning—the approach where models improve through feedback loops rather than just absorbing training data—scales as a metric. There’s no evidence we’ve hit a wall. Prediction is here to stay, both as an aesthetic and a technology. Critics keep betting against AI progress and losing those bets. I’m not betting against further intelligence gains.

That said, the report is right about unevenness. We’re in for a period of jagged intelligence gains. Reinforcement learning doesn’t solve everything uniformly. Some tasks will leap forward while others stay stuck. This matters for product planning—you can’t assume smooth capability improvements across all domains.


## Open vs. Closed: China Dominates Open Weights

US labs still lead frontier leaderboards—the top-performing, most expensive models. But the gap has narrowed. China became the clear #2 globally and now dominates the open-weight ecosystem via Qwen and DeepSeek. Open-weight models are those where the underlying architecture and parameters are publicly available for anyone to download and run, unlike proprietary models from OpenAI or Anthropic.

DeepSeek V3 and R1 brought competitive reasoning architectures to open models. OpenAI’s GPT-OSS release catalyzed open-source stacks and cost discipline, though it underwhelmed compared to frontier offerings.

China retains roughly 77,000 STEM PhDs annually and is increasingly keeping talent onshore. Open-weight dominance gives China distribution leverage even without frontier model leadership.


## Key Metrics

Metric Value Context Capability-to-cost doubling (fastest) ~3.4 months Google, Artificial Analysis ChatGPT weekly actives ~800M ChatGPT Search dominance ChatGPT AI search share ~60% vs. Perplexity, others Retail conversion (AI referrals) ~11% Up ~5pp YoY 1GW data center capex ~$50B Infrastructure buildout 1GW annual operating costs ~$11B/yr Fully loaded US power shortfall by 2028 ~68 GW SemiAnalysis cited Data center projects blocked $64B NIMBY delays GPT-5 input cost vs. GPT-4.1 24× cheaper 400k context Monthly ecosystem token volume ~1 quadrillion API scale


## Model Maker Dynamics: Three Strategies Diverging

The report doesn’t separate model maker strategies clearly enough. Here’s what’s actually happening:

**Google is commoditizing intelligence.** They’re driving down the cost of compute and intelligence as a way to choke off competitors. If intelligence becomes cheap enough, Google wins by distribution and integration, not model margins. The 3.4-month capability-to-cost doubling is strategic, not accidental.

**OpenAI is building substrate.** ChatGPT’s 800M weekly actives give them the footprint to scale intelligence compute as infrastructure—fast. They’re leveraging distribution to become the default answer engine, then monetizing through API and enterprise layers. This is AWS for AI.

**Anthropic is playing premium from constraint.** They’re behind on compute but leaning into quality, safety, and the “smart people thinking carefully” brand. It’s an upscale positioning play that works if enterprises care about reliability and reasoning depth over raw speed.

These strategies matter because they determine where cost curves go and what routing architectures make sense for builders.


## What the Deck Misses


### The craft and design gap is killing adoption

The report focuses on technical constraints—power, compute, reasoning fragility. It misses the bigger bottleneck: we’ve leaned too hard on tech and underinvested in craft. Most AI products have terrible UX, unclear value propositions, and friction-heavy onboarding. The limiting factor isn’t model capability—it’s design and execution quality.

Businesses that survive the next 18 months will deliver actual adoption and value, not just technical demos. That requires product discipline, not just engineering horsepower.


### A Cambrian explosion is coming, then red ocean

We’re about to hit a Cambrian peak of AI competition—a period of rapid diversification and proliferation, like the biological event 500 million years ago. The next year will see an explosion of new entrants, then rapid consolidation. Many businesses will go to the wall. The survivors will be those who differentiate through craft, capture attention (like Cluely), or lock in distribution early.

This isn’t a “rising tide lifts all boats” moment. It’s a red ocean forming fast. If you’re building, you need a plan to stand out when 50 competitors launch similar features in the next six months.


## Implications by Audience


### If you’re building a product

Macro constraints like power shortfalls won’t kill you—but failing to optimize routing will. The capability-to-cost curve creates margin opportunities if you architect for small-model-first routing with frontier escalation only when necessary.

Your real problem is differentiation in a red ocean. Technical features commoditize fast. Craft, design, and attention capture matter more than the deck suggests. You can’t out-tech competitors anymore—you have to out-execute on user experience and value delivery.

Ship Answer Engine Optimization schema and APIs now—structure your content so AI models can surface it when answering questions. Answer-engine distribution drives higher retail conversion (~11% vs. traditional search), and most builders are underinvested here.


### If you’re running an enterprise

Procurement strategies need to shift. Buy routers, not just models. Small-model-first routing with escalation to expensive models only when needed, plus larger contexts at lower costs (GPT-5), fundamentally change total cost of ownership. Source your APIs and internal content for answer-engine ingestion—traffic is flowing from Google’s index through ChatGPT and Perplexity.

You face more pressure to deliver value in 2026. All that routing optimization had better actually scale and work, not just work in pilot. Model reliability matters more at your scale than it does for startups. Those model maker constraints (power, infrastructure) start affecting SLAs when you’re operating at enterprise volume.

The upside: acquisition and acquihire targets are coming. The Cambrian explosion will leave strong teams and technology stranded in failed businesses. M&A opportunities will be real.


### If you’re a model maker or infrastructure player

Capital is tractable, but execution timelines are hard. Siting, water-aware design (~2M liters/day per 100MW), and long-lead interconnects require advance planning. Don’t assume firmed generation materializes on demand.

The strategic positioning diverges by player. If you’re commoditizing intelligence (Google), speed matters more than margin. If you’re building substrate (OpenAI), distribution lock-in matters more than per-query profit. If you’re playing premium (Anthropic), reliability and reasoning depth matter more than volume.


### If you’re setting policy or allocating capital

Plan for electricity infrastructure, not announcements. 5GW clusters and 68GW US shortfall require aligned permits and interconnects. Expect export volatility and “sovereignty-washing.” Real independence requires domestic power, training capacity, and talent retention—not just press releases.

Require standardized safety disclosures with focus on prompt-injection defenses and open-weight tamper-resistance. The “more capable equals safer” assumption isn’t proven.

For investors: underwrite capability-to-cost curves and routing moats. Faster doubling times compress gross-margin windows. GPU neoclouds (CoreWeave, Nebius, Lambda, Crusoe) and circular NVIDIA-lab-cloud deals are real—watch revenue concentration and step-in obligations. Valuation scaling breaks on power; siting, water, and NIMBY constraints are material risks.


## My Take

I think the deck overshoots on fragility and undershoots on execution momentum.

**On infrastructure:** Yes, power is a constraint. Yes, NIMBYism is blocking projects. But capital markets are allocating aggressively to solve these problems. Utility partnerships are happening. Nuclear restarts are happening. Regulatory fast-tracking is happening. This isn’t an unsolvable bottleneck—it’s a capital allocation problem, and the capital is flowing. Betting against American infrastructure buildout capacity when money is committed usually loses.

**On reasoning:** The critics keep betting against AI progress and losing. Reinforcement learning—where models improve through iterative feedback rather than just training data—scales as a metric. There’s no wall here. Prediction works. GPT-5 Pro shows continued gains, and Gemini 3 is expected to launch within days with further improvements. The report is right that gains will be uneven—we’re in for jagged progress across domains. But I’m not betting against further intelligence improvements. The fragility narrative feels like anchoring on temporary evaluation noise rather than the actual capability trajectory.

The benchmark critique is valid—evaluation methods are noisy and prompt-sensitive. But that doesn’t mean the underlying gains aren’t real. It means we need better measurement tools, not that progress has stalled.

**On competition:** The deck misses that we’re entering a Cambrian explosion followed by rapid red ocean consolidation. The next 12 months will see an unprecedented number of AI product launches, then brutal shakeout. Most builders are underestimating how crowded their categories will get and how fast margins compress.

The survival filter isn’t “who has the best model”—it’s “who delivers adoption and value.” That requires craft and design discipline we’re not seeing enough of. The industry has leaned too hard on technical capabilities and underinvested in user experience, onboarding, and value clarity. The craft gap is the real bottleneck, not compute constraints.

**On model maker dynamics:** The strategic positioning matters more than the deck acknowledges. Google commoditizing intelligence, OpenAI building substrate, and Anthropic playing premium from constraint—these aren’t just competitive moves, they’re fundamentally different bets on where value accrues. That changes everything about how builders should think about routing, vendor lock-in, and long-term partnerships.

**For builders:** The macro constraints won’t kill you, but routing failure will. Differentiation through craft, attention capture, and Answer Engine Optimization positioning matters more than the deck suggests. You’re competing in a red ocean that’s forming faster than most people realize.

**For executives:** You have M&A opportunities coming as the Cambrian explosion leaves strong teams stranded. You also have acute pressure to deliver—routing optimizations must actually work at scale in 2026, not just in pilot. Model reliability becomes a first-order concern at enterprise volume.

**For everyone:** Don’t bet against continued intelligence gains, but expect jagged progress. Don’t bet against infrastructure buildout when capital is committed, but plan for execution timelines. Don’t assume technical features create moats—craft and distribution do.

The systems race is real. The capability-to-cost compounding is real. The distribution consolidation around answer engines is real. But the narrative of constraint and fragility overshoots. Capital, engineering, and execution momentum are stronger than the deck implies.

The winners in 2026 won’t just route cheaply and capture distribution—they’ll deliver actual user value through craft and design discipline while surviving the Cambrian shakeout. That’s harder than optimizing infrastructure, but it’s where the game is actually won or lost.

---


## My Take

**A note on sourcing and analysis:** This briefing draws data and findings from the State of AI Report 2025, but the interpretations and strategic recommendations are my own. Specifically, I differ from the report in several areas: I’m more optimistic about infrastructure buildout being capital-tractable where the report emphasizes constraints as near-term ceilings.

I view reinforcement learning gains as real and continuing where the report emphasizes fragility and benchmark noise. The report doesn’t address the craft and design gap I see as critical to adoption, nor does it discuss the Cambrian explosion and red ocean dynamics I expect in the next 12 months.

The model maker strategic positioning (Google commoditizing, OpenAI building substrate, Anthropic playing premium) is my interpretation of competitive dynamics, not explicitly stated in the deck.

Finally, the audience-specific implications are derived from the report’s data but reflect my read on what matters for different stakeholders. Where I’m citing the report’s numbers or findings directly, I note it. Where I’m offering strategic interpretation or disagreement, that’s clearly my perspective.

**Sources:** All findings drawn from the [State of AI Report 2025](https://www.stateof.ai/) (313 slides).

---


## Custom Analysis Prompt: State of AI 2025 Implications

Copy this entire prompt and paste it into Claude, ChatGPT, or your preferred AI assistant. Replace the bracketed sections with your specific context.

```
You are a strategic advisor helping me understand the implications of the State of AI 2025 Report for my specific situation. I need you to think through both the direct findings and second-order effects.

CONTEXT ABOUT MY ORGANIZATION:
[Describe your role, company size, industry, current AI maturity, and strategic priorities. Be specific: “I’m VP Product at a 500-person B2B SaaS company in healthcare. We have 2 AI engineers and use OpenAI APIs for summarization features. Revenue is $50M ARR. We’re planning a major AI initiative for 2026.”]

WHAT I’M TRYING TO DECIDE:
[Describe your specific decision or question. Examples: “Should we build our own routing layer or use a vendor?” / “How should I prioritize AI investment across customer service, sales, and product?” / “Is our current OpenAI-only strategy a risk?”]

KEY FINDINGS FROM THE STATE OF AI 2025 REPORT:

1. Capability-to-cost is doubling every 3-8 months (Google: 3.4 months, OpenAI: 5.8-8.1 months)
2. GPT-5 input costs are 12× cheaper than Claude, 24× cheaper than GPT-4.1 for 400k contexts
3. Ecosystem processes ~1 quadrillion tokens/month
4. Small-model-first routing is now the winning architecture
5. ChatGPT Search: ~700M weekly users, ~60% AI search share
6. Retail conversion from AI referrals: ~11% (up ~5pp YoY)
7. Answer engines still source heavily from Google’s index
8. Answer Engine Optimization (AEO) is replacing traditional SEO
9. 1GW data center: ~$50B capex, ~$11B/year operating costs
10. US faces ~68GW power shortfall by 2028
11. $64B in data center projects blocked by NIMBYism
12. Reinforcement learning gains show 6-17% variance in standardized testing
13. Chain-of-thought transparency detects ~99% of reward-hacking
14. China dominates open-weight ecosystem (Qwen, DeepSeek)
15. Google is commoditizing intelligence; OpenAI building substrate; Anthropic playing premium

STRATEGIC CONTEXT:

Model maker strategies differ fundamentally:
- Google: Driving down cost to win through distribution, not margins
- OpenAI: Leveraging 700M users to become infrastructure layer
- Anthropic: Premium positioning focused on reliability and reasoning depth

Critical gaps the report misses:
- Craft and design gap is limiting adoption more than technical capability
- Cambrian explosion coming (12 months), then rapid red ocean consolidation
- Competition will force differentiation through UX and value delivery, not features

NATE’S PERSPECTIVE (CONTRARIAN TAKES):

The author of this briefing differs from the report in several key areas:

Infrastructure: More optimistic about buildout being capital-tractable. While the report emphasizes constraints as near-term ceilings, the author argues capital markets are allocating aggressively to solve power/infrastructure problems through utility partnerships, nuclear restarts, and regulatory fast-tracking. Betting against American infrastructure buildout when money is committed usually loses.

Reasoning gains: The author views reinforcement learning gains as real and continuing, not fragile. GPT-5 Pro shows progress, Gemini 3 launching imminently with further improvements. There’s no evidence of a wall. Critics keep betting against AI progress and losing. Benchmark critique is valid (noisy, prompt-sensitive), but that means we need better measurement tools, not that progress has stalled. Expect jagged, uneven gains across domains.

Craft and design gap: The limiting factor isn’t technical capability—it’s execution quality. Most AI products have terrible UX, unclear value props, friction-heavy onboarding. Industry has leaned too hard on tech and underinvested in user experience. This gap is the real bottleneck, not compute constraints.

Competition dynamics: We’re entering a Cambrian explosion (unprecedented proliferation of AI products in next 12 months) followed by brutal red ocean consolidation. Many businesses will fail. Survival filter is “who delivers adoption and value” not “who has the best model.” Most builders underestimate how crowded categories will get and how fast margins compress.

Audience-specific implications:
- For builders: Macro constraints won’t kill you, but routing failure will. Differentiate through craft, attention capture, and AEO. Technical features commoditize fast.
- For executives: M&A opportunities coming as Cambrian explosion leaves strong teams stranded. Acute pressure to deliver—routing must work at scale in 2026, not just pilot. Model reliability matters more at enterprise volume.
- For everyone: Don’t bet against continued intelligence gains (expect jagged progress). Don’t bet against infrastructure buildout when capital is committed (but plan for execution timelines). Don’t assume technical features create moats—craft and distribution do.

ANALYZE MY SITUATION:

Based on my context and decision above, please:

1. **Direct Implications**: Which of these findings directly affect my decision? What changes in unit economics, distribution, or infrastructure constraints should I factor in?

2. **Competitive Dynamics**: Given the model maker strategies and red ocean dynamics, how does this change my vendor relationships, routing architecture, or differentiation strategy?

3. **Timing and Risk**: What are the concrete timeline pressures? Where am I exposed if I don’t act in the next 6-12 months? What can wait?

4. **Specific Recommendations**: Give me 3-5 concrete actions I should take in the next 90 days, with reasoning tied back to the report findings and Nate’s perspective.

5. **Contrarian Integration**: How do Nate’s contrarian views (infrastructure is tractable, reasoning gains continuing, craft gap matters most, Cambrian explosion imminent) change your recommendations for my specific situation?

6. **Blind Spots**: What am I likely underestimating or overlooking given my context? Where might I be anchoring on old assumptions that no longer hold?

Be specific. Use numbers from the findings where relevant. Balance the report’s more conservative framing with Nate’s execution-optimistic view. If you need to make assumptions about my situation, state them clearly and ask for clarification.
```

[![](https://substackcdn.com/image/fetch/$s_!wtxH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff92a4538-aa54-44af-85e2-492905b0e794_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!wtxH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff92a4538-aa54-44af-85e2-492905b0e794_1024x1024.png)
