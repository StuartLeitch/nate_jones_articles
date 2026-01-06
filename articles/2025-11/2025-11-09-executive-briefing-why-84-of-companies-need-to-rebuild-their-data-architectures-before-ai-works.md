---
title: "Executive Briefing: Why 84% of Companies Need to Rebuild Their Data Architectures Before AI Works"
author: "Nate Jones"
published: 2025-11-09
url: https://natesnewsletter.substack.com/p/executive-briefing-why-84-of-companies
audience: everyone
scraped_at: 2026-01-05 19:12:14
---

Your company is probably not as data-driven as you think it is.

I know this because Salesforce just surveyed 6,000 enterprise data leaders and found something remarkable: 84% say their data strategies need complete overhaul before AI works. That means only 16% of data leaders think their organizations are actually ready.

Meanwhile, 63% of C-suite are overly optimistic: they believe their companies are already data-driven and are ready for a bold new AI future!

That’s a 47-point gap between what data leaders see (16% ready) and what executives believe (63% ready)—and it’s killing AI transformation. C-suite is not talking to (or listening to) data leadership, and it’s killing AI transformation.

This explains a lot.

Maybe you’re running pilots. Maybe dozens of them. Vendors are promising six-month transformations. Leadership is asking why AI isn’t showing up in business metrics yet.

And all along the answer is probably hiding in your data architecture.

I keep underlining that the difference between companies that scale AI and companies stuck in pilot purgatory isn’t about prompting techniques or model selection. It’s about whether their data infrastructure can actually support what agentic systems demand. The 16% who are succeeding fixed their data first. They did the boring work.

I admit seeing the numbers and seeing the communication gaps here is not too surprising for me.

I’ve spent the last year working with Fortune 500 companies on AI transformation, and I keep seeing the same pattern.

I keep seeing optimistic CEOs walk into conversations assuming they’re data-driven—they have dashboards, they have reports, they have data teams. Then they set a mandate to deploy agents and discover their data can’t answer simple questions when queried agentically, can’t assemble complete customer views without missing records, can’t support real-time retrieval that agentic workflows require.

What I’ve found is that the infrastructure gap is both bigger and more specific than most C-suite executives realize.

After working through this with data leaders across financial services, retail, manufacturing, and healthcare, I’ve identified seven team and architectural principles that separate the 16% who scale from the 84% who don’t:

1. Diagnose before you deploy—latency versus integrity tradeoffs matter more than you think
2. Zero-copy architecture is a philosophy, not a mandate
3. Context matters more than volume—semantic accuracy outranks raw data
4. Governance enables speed when designed right
5. Set an honest timeline
6. Close the perception gap between business and technical leaders
7. The strategic choice is time-bound—infrastructure investments compound

You notice none of these are about buying the right vendor platform or running better pilots. That’s not what gets successful organizations to scale.

Data is. And taken together, these principles are about making explicit tradeoffs that match your organization’s constraints, risk tolerance, and competitive position.

Whether you’re a data leader trying to educate executives on infrastructure realities, a business leader trying to understand why AI initiatives keep stalling, or even an individual contributor or team lead looking to explain to leadership who will NOT listen that the data structures matter—this one’s for you.

This piece walks through the seven architectural principles, explains the specific tradeoffs each one presents, and gives you the framing questions to assess where your organization actually stands versus where you think you stand.

And yes, there’s a diagnostic prompt that helps you figure out which architectural decisions matter most for your specific situation, and that helps you navigate the tradeoffs for your specific organization.

My goal is simple: I want to kill the false optimism that’s so prevalent around AI to make room for useful projects, useful work, useful AI transformation. And time after time after time, that starts with data. How can it start anywhere else? Data is what AI eats for breakfast.

So let’s get our data right!

> ***This is an Executive Circle briefing**, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via this [60 second video](https://youtu.be/KC3GkEnHR-8) explaining what’s in each tier, and you can change your plan [here](https://support.substack.com/hc/en-us/articles/360044105731-How-do-I-change-my-subscription-plan-on-Substack). Enjoy, and back to regular programming Monday!*


## [Grab the Conversational AI Data Stack Prompt](https://www.notion.so/product-templates/Executive-Briefing-Prompt-Data-Architectures-2a65a2ccb526807bab07d8c8a7948a6c?source=copy_link)

This prompt gives you a conversational advisor that helps you figure out where your data infrastructure actually stands versus where you think it stands. That perception gap is what kills most AI initiatives. Instead of generic best practices, it walks you through the specific tradeoffs you’re facing.

Should you build foundation first or run pilots concurrently? Where does zero-copy architecture make sense versus centralized data? How much governance overhead do different use cases justify? What timeline is actually realistic given your constraints?

The value is that it forces concrete diagnostic questions—can you answer simple queries in under five seconds?—rather than letting you self-assess as “data-driven.” Then it helps you think through decisions in terms of real consequences: stakeholder patience, error costs, competitive position, regulatory exposure.

By the end of the conversation, you’ll know which 2-3 architectural decisions matter most for your situation and what accepting each tradeoff actually means for your organization.

---


# **Executive Briefing: Why 84% of Companies Need to Rebuild Their Data Architectures Before AI Works**

Salesforce just published survey data from 6,000 enterprise data leaders that explains why most AI initiatives are failing. The headline finding: **84% of organizations say their data strategies need complete overhaul before AI works.** At the same time, 63% of executives believe their companies are already data-driven.

That perception gap is killing AI transformation. Leaders walk into AI conversations assuming they’re data-driven, then discover their data can’t support the demands of agentic systems. The result is pilot purgatory, vendor disappointment, and quiet retreat from transformation ambitions.

The good news: the 16% successfully scaling AI aren’t smarter about prompting or model selection. They fixed their data infrastructure first. They did the boring work. Here’s what separates them from everyone else.


## **Diagnose Before You Deploy**

The principle here is straightforward: diagnostics reveal the latency versus integrity tradeoffs in your data architecture. Before you run AI initiatives, you need to understand whether your infrastructure can deliver data quickly enough for agentic workflows, and whether that data is trustworthy enough for autonomous decision-making.

Two tests matter most. First, can your system answer factual questions about your data in less than five seconds without human intervention? I’m talking simple queries like “What’s our inventory for Product X in warehouse three right now?” If you can’t get performant query results that quickly, you’re not ready for anything more sophisticated.

Second, can you assemble a complete customer view across sales, support, billing, and shipping with no missing data in a similar time envelope? If these tests fail, what you’re finding is that your data sets were designed for slow retrieval—the kind that takes thirty minutes and produces one row in a quarterly report. They weren’t designed for agentic retrieval that happens on the fly.

Here’s where executive judgment matters. When diagnostics reveal gaps, you face a choice: accept a slower AI rollout while you fund infrastructure upgrades, or proceed with limited deployments in data-ready domains while building foundation elsewhere. The first path delays visible wins but reduces rework. The second maintains momentum and satisfies stakeholder pressure for progress, but you’ll hit scaling walls quickly and may need to rebuild pilots later.

Consider what happened at a financial services client. Their diagnostics showed that customer data queries took eighteen seconds on average. They had two options: spend nine months rebuilding their customer data platform to hit sub-second queries, or deploy AI agents only for back-office functions where twelve-hour data latency was acceptable. They chose the latter, got early wins that funded the infrastructure work, then expanded to customer-facing agents eighteen months later. The tradeoff was conscious: accept narrow initial scope to maintain organizational momentum.

The alternative approach works too. A retail client discovered similar latency issues but chose to pause all AI deployments for fourteen months while they rebuilt core data infrastructure. When they resumed, they scaled agents across merchandising, supply chain, and customer service simultaneously because the foundation supported it. The tradeoff: they absorbed opportunity cost and stakeholder frustration during the build, but avoided the technical debt of premature deployments.

Neither approach is universally correct. The choice depends on your organization’s tolerance for delayed gratification versus its need for visible progress. What doesn’t work is pretending the diagnostic findings don’t matter or assuming vendor solutions will paper over infrastructure gaps. They won’t.


## **Zero-Copy Architecture Is a Philosophy, Not Tooling**

Zero-copy architecture is an architectural principle, not a mandate. The core insight is that copying data to central locations introduces latency, staleness, and transformation errors. By querying data where it lives, you can achieve real-time accuracy and reduce the surface area for data quality issues.

But zero-copy comes with tradeoffs. Governance complexity increases because you’re managing access controls across distributed systems rather than at a single warehouse perimeter. Integration costs rise because you need high-performance connectors to every source system. And you introduce vendor reliance on data virtualization or federation layers that become critical dependencies.

The Salesforce survey found that companies using zero-copy approaches were **34% more likely to succeed with AI**. That’s compelling. But it doesn’t mean centralized copies are obsolete. There are scenarios where centralizing data still makes sense.

Compliance requirements sometimes demand it. If regulatory audits require point-in-time snapshots with tamper-proof lineage, a data warehouse provides clearer audit trails than distributed queries. Performance hotspots justify it too. If your AI agents repeatedly query the same high-volume data sets, caching centrally can be more efficient than hammering source systems with redundant queries.

The principle to apply is this: default to zero-copy for agility and real-time accuracy, but make conscious exceptions where compliance, performance, or cost considerations justify centralization. A manufacturing client implemented zero-copy for production line sensors and inventory systems where real-time data drove operational decisions. But they maintained a centralized copy of financial transaction data because their audit requirements demanded immutable historical records and their quarterly reporting queries would have overwhelmed source systems.

The architectural decision isn’t binary. Most organizations end up with hybrid models—zero-copy for operational data, selective centralization for analytical workloads and compliance domains. The mistake is treating this as a religious debate rather than an engineering tradeoff. Ask yourself: where does real-time access unlock enough value to justify the governance complexity? Where does centralization provide enough performance or compliance benefit to accept staleness?

The organizations that succeed with zero-copy are typically those investing in internal architectural capacity. Your data configuration is unique enough that vendor solutions alone won’t solve it. You need people who can design federation layers, optimize distributed queries, and build governance frameworks that work across boundaries. If you’re not prepared to build that capacity, a more centralized approach may be pragmatic even if it’s less theoretically pure.


## **Context Matters More Than Volume**

The governing principle: semantic accuracy outranks raw volume. The Salesforce survey found that **49% of organizations draw incorrect conclusions because their data lacks business context**. More data without context just means more confidently wrong answers.

Here’s what that looks like in practice: the data says revenue is $2 million, the customer is Acme Corp, it’s third quarter revenue. But that particular database row doesn’t specify that the $2 million was a one-time contract, not recurring revenue. Now your agents are inappropriately adding $2 million in ARR to your reporting. This is not uncommon.

The solution is semantic layers—metadata frameworks that encode business definitions, relationships, and logic so that agents understand what data means, not just what it says. Agents should know the difference between booking and revenue, between gross and net, between active and total customers, all from universal single-source definitions.

But implementing semantic layers has costs. You’re adding an abstraction layer that needs maintenance. Business definitions change, and your semantic layer becomes another thing that can fall out of sync with reality. Development velocity can slow while data teams debate canonical definitions. And if your semantic layer is wrong, you’ve systematically encoded incorrect business logic across all AI interactions.

The tradeoff is between investing in semantic layers versus accepting model hallucinations. Without semantic layers, your AI agents will make reasonable-sounding but substantively wrong interpretations of ambiguous data. With semantic layers, you trade development speed and flexibility for correctness and consistency.

Consider when context work is overkill. If you’re building AI agents for low-stakes internal tools—say, a chatbot that helps employees find HR policies—the risk of misinterpreting data fields is low and the cost of errors is minimal. Investing heavily in semantic layers may not be justified. But if you’re building agents that generate financial reports, interact with customers, or make operational decisions, semantic accuracy becomes critical.

On the other hand, imagine deploying AI agents in a healthcare scenario. Would you tolerate agents that might confuse “prescribed medication” with “administered medication” or “scheduled appointment” with “completed visit?” No. In these situations the semantic layer can become a competitive advantage because the system’s AI outputs are trustworthy enough to inform clinical decisions.

The calibration question for executives: where does semantic precision justify the investment in governance overhead? Where can you tolerate ambiguity in exchange for speed? The answer depends on error consequences, regulatory exposure, and competitive dynamics in your specific context.


## **Governance Enables Speed, It Doesn’t Slow You Down**

Governance is a design philosophy, not a compliance checkbox. The principle is that well-designed governance creates shared understanding of data quality, clear ownership of remediation, and automated enforcement of standards. Poor governance is what slows you down—when nobody knows who owns data quality, when issues get debated in endless meetings, when enforcement is manual and inconsistent.

The design choice is between automation and manual oversight. Automated governance means you encode quality rules, lineage tracking, and access controls in systems that flag issues in real-time and route them to owners based on severity. Manual governance means quality councils, review boards, and approval workflows. The tradeoff is between upfront investment in automation versus ongoing labor costs of human review.

There’s a second dimension: tolerance for false positives versus risk exposure. Strict governance catches more data quality issues but generates false alarms that teams must investigate. Loose governance reduces noise but lets more errors through to production. The right balance depends on your risk appetite.

The 16% successfully scaling in the Salesforce survey are doing so with strong governance practices, but what “strong” means varies. Healthcare again: a pharmaceutical company building AI for clinical trial analysis should likely use heavy governance—every data transformation requires documentation, every quality rule needs human review, every alert triggers investigation. The false positive rate may be high, but the consequences of data errors in drug development justify extreme caution. The governance model prioritizes safety over speed.

A media company might take the opposite approach. Lightweight governance would work, because it enables more rapid progress. Self-service data access gives the team advantages here, and automated QA is good enough.

Both models work. The pharmaceutical company moves slowly but builds unimpeachable data foundations. The media company moves quickly but occasionally ships buggy recommendations. Neither is wrong. They’re matching governance posture to their risk context.

The question for your board: what’s the cost of a data error in your AI deployments? If errors create regulatory exposure, customer harm, or financial materiality, invest in heavier governance even though it slows initial development. If errors are mostly inconvenience or minor user friction, optimize for lightweight governance that maintains velocity.

The organizations that struggle are those with heavy governance inherited from legacy compliance requirements applied to low-stakes AI experiments. You end up with the worst of both worlds—slow development without proportional risk reduction. Governance should be right-sized to actual risk, not historical precedent.


## **The Honest Timeline Is 18 to 36 Months**

> *I am implicitly assuming here you are starting at a standing start, and have relatively big data. If you’re already partway on a data transformation journey, or if you’re operating on a smaller data footprint, you may get away with moving faster!*

The principle here is about sequencing: do you invest in infrastructure first to reduce rework, or run concurrent pilots to maintain momentum? Each approach has tradeoffs.

The infrastructure-first path means spending twelve to eighteen months fixing data pipelines, implementing zero-copy architecture, and building semantic layers before deploying agents at scale. The advantage is that when you do deploy, you can scale quickly across multiple use cases because the foundation supports it. You avoid the rework of rebuilding pilots that were built on inadequate infrastructure. The disadvantage is that you delay visible wins, test stakeholder patience, and risk losing organizational momentum.

The concurrent path means running AI pilots in data-ready domains while building infrastructure in parallel. You get early wins that demonstrate value and fund further investment. You maintain organizational energy and executive support. But you accept that some pilots will need to be rebuilt when infrastructure catches up, and you’re managing the complexity of production deployments while simultaneously doing foundation work.

Most organizations end up somewhere in between. Year one, you’re fixing critical pipelines, implementing zero-copy architecture for your top domains, and piloting agents where data is trustworthy. Year two, you’re expanding toward real-time capabilities and automating governance. Year three, you’re scaling agents across the organization.

This feels slow. Vendors will promise six-month transformations. Those timelines assume your infrastructure is already ready—which is exactly what Salesforce is calling out. For 84% of organizations, it’s not.

The choice depends on your competitive position, stakeholder patience, and access to capital. If you’re in a land-grab market where first-mover advantage matters, concurrent pilots may be rational despite rework costs. If you’re in a stable market where operational excellence compounds over time, infrastructure-first may be the better bet.

What doesn’t work is pretending you can skip the infrastructure work entirely. You can defer it, but you can’t avoid it. Organizations that keep launching pilots on inadequate foundations eventually hit a wall where nothing scales and leadership loses faith in AI altogether. Better to be honest about the timeline upfront.


## **Close the Perception Gap Between Business and Technical Leaders**

The governing principle is shared situational awareness. The fact that 63% of executives think they’re data-driven while 84% need complete overhauls reveals a fundamental communication breakdown. Business and technical leaders are operating with different mental models of organizational readiness.

There are multiple mechanisms to close this gap, each with tradeoffs.

But honestly, start with listening. It doesn’t need to be that fancy.

You might start with a standing conversation with data and technical leaders, but meetings don’t fix the gap by themselves.

It’s a mindset shift. Senior business leaders need to commit to learning more of the details of the technical stack than they normally would. Without that technical fluency, most C-suite will be over-optimistic on AI.

And this is not a time for magic box thinking.

Remember, the perception gap exists because business leaders genuinely don’t understand what “data-driven” means in the context of agentic AI. They think it means having dashboards and reports. It actually means having agentic query performance, complete data lineage, automated quality monitoring, and semantic layers that encode business logic. Technical leaders need to educate executives not just on what’s broken, but on what success looks like and why it’s different from what exists today.

This requires technical leaders to step up. Make infrastructure work visible rather than hiding it beneath the technical organization. Frame data investments in business terms—not “we need to implement a data virtualization layer” but “we can’t deploy customer service agents until we can assemble complete customer views in under one second, which requires six months of data pipeline work.” That framing has teeth.

A cultural choice to pay attention to in all this: do you want a collaborative model where business and technical leaders share accountability for data readiness, or a model where technical leaders have authority to block AI initiatives until infrastructure is ready? The first builds alignment but requires maturity on both sides. The second provides clarity but risks business leaders feeling frustrated by technical gatekeeping. Choose the model that fits your culture, but choose explicitly.


## **The Strategic Choice Is Time-Bound**

The time-value principle is simple: investments in data infrastructure compound over time. Organizations that start building integrated data systems today will find each component easier to implement, each success easier to achieve, each new use case faster to deploy. Organizations that wait will discover that catching up isn’t about working harder—it’s about having started sooner.

This creates a tradeoff between the compounding benefits of early infrastructure investment versus the option value of waiting for clearer technology maturity. Start now and you’re making bets on architectural approaches—zero-copy versus centralized, semantic layers versus model fine-tuning, build versus buy—before best practices have fully crystallized. Wait and you benefit from lessons learned by early movers, but you fall farther behind while competitors accumulate advantages.

Consider the opportunity cost scenarios. If you invest $10 million in data infrastructure today and deploy agents that generate $5 million in annual value, you’ve broken even in two years and generated returns indefinitely after. But if you wait two years to start, your competitors have four years of data infrastructure maturity by the time you break even, and they’re deploying agents you can’t match because your foundation isn’t ready.

The math gets worse when you factor in exponential AI capability growth. If AI models double in capability every eighteen months—a reasonable assumption given recent trends—then infrastructure you build today unlocks not just current model capabilities but every future improvement. Infrastructure you defer means you’re locked out of capability gains until you catch up.

The counterargument: what if you invest in the wrong approach? What if zero-copy architecture proves to be a dead end, or semantic layers become obsolete when models get smart enough to infer context? These are real risks. But the cost of building the wrong infrastructure is bounded—you might spend $10 million on a suboptimal approach and need to rebuild. The cost of not building infrastructure is unbounded—you’re locked out of the entire AI revolution until you catch up, and the gap keeps widening.

The strategic bet is not whether AI matters. Every executive understands that it does. The bet is whether your organization can afford to wait for clarity or needs to move with imperfect information. In stable markets with long planning cycles, waiting has merit. In dynamic markets with increasing returns to scale, waiting is fatal.


## **What This Means for You**

The organizations successfully scaling AI fixed their data infrastructure. They ran diagnostics, accepted honest timelines, did the work. That’s how you close the gap between “we’re data-driven” and “our data can’t support AI.”

The guidance can’t be prescriptive because your context differs. Ask yourself:

Do we accept twelve to eighteen month payback periods, or need faster returns? Can we invest in internal architectural capacity, or need vendor solutions? Do we have patience for eighteen to thirty-six month timelines, or will stakeholders demand quarterly wins?

What’s the actual cost of a data error—regulatory exposure, customer harm, revenue impact? Where do we tolerate siloed data versus demand integrated views? Where does semantic precision justify governance overhead versus where can we tolerate ambiguity?

These require honest assessment of your constraints, capabilities, and competitive context. The answers determine which architectural principles to prioritize, which tradeoffs to accept, which timelines to commit to.

The difference between the 16% who succeed and the 84% who fail isn’t technology or budget. It’s confronting these questions honestly rather than assuming readiness, making explicit tradeoffs rather than hoping they’ll resolve, and accepting that the boring work of data infrastructure unlocks transformation.

Start now with imperfect information, or wait for clarity and accept the gap will be harder to close later.

---

> *I occasionally recommend newsletters that I think my readers will enjoy. Just be clear: these are not sponsored, and no money ever changes hands here. I personally like Semafor because of their hard-headed analysis, and I think their own self-description puts it well:*

***As AI accelerates change across industries, understanding the scale of its impact has never been more vital.** [Semafor Technology](https://www.semafor.com/newsletters/tech?utm_medium=swaps&utm_source=swaps&utm_campaign=natesnewsletter1125) is a twice-weekly email briefing that does exactly that. Written by Reed Albergotti, each issue examines the people, ideas, and companies driving the AI transformation. [Subscribe for free.](https://www.semafor.com/newsletters/tech?utm_medium=swaps&utm_source=swaps&utm_campaign=natesnewsletter1125)*

---

[![](https://substackcdn.com/image/fetch/$s_!tc0k!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2d095315-2ed7-4127-9aaa-3ec510cba6ff_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!tc0k!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2d095315-2ed7-4127-9aaa-3ec510cba6ff_1024x1024.png)
