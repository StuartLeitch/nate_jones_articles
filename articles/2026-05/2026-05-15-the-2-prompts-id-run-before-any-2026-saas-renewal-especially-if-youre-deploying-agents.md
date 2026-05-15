---
title: "The 2 prompts I'd run before any 2026 SaaS renewal (especially if you're deploying agents)"
author: "Nate Jones"
published: 2026-05-15
url: https://natesnewsletter.substack.com/p/saas-agent-license-renewal
subtitle: "Watch now | The seat is not dead. It is being wrapped in a meter for delegated work."
audience: everyone
scraped_at: 2026-05-15 12:00:17
---

For two decades, SaaS pricing pulled off a beautiful trick: it turned work into seats. Ten reps in the CRM meant ten seats. Fifty reps in the help desk meant fifty seats. The model was legible because the human was the unit of software value. A person logged in, clicked, updated records, sent messages, and the vendor charged for that person.

That model just cracked.

Salesforce booked $800 million in agent revenue last quarter, up from $540 million the quarter before. Its CRO Miguel Milano told analysts, “We have found the formula to monetize AI.” Microsoft added a separate $15-per-user license for agent governance, sitting alongside the $30 Copilot seat. SAP put hard limits on which agents are even allowed to call its APIs. ServiceNow, Workday, Zendesk, HubSpot, and Atlassian each added their own meter under their own name.

Your next SaaS renewal will price two things: who logs in, and what work moves through the system. If you walk in counting seats, you’ll sign for the headcount you already have and pay for the agent work on top. Once usage is embedded in customer workflows, support deflection numbers, and the finance close, the negotiating position flips. The vendor knows the work has moved. You know turning it off would hurt.

**Here’s what’s inside:**

- **The eight-vendor pattern.** What each one calls its agent meter, and which one your renewal will hit first.
- **The hybrid model most companies will land on.** Why Microsoft’s three-layer stack is probably the template.
- **Fair license vs. rent-seeking.** Nine traits that separate a defensible meter from a vendor capturing the AI efficiency.
- **The negotiation list.** What to ask at renewal, and the one question most vendors will try to dodge.
- **Two prompts to run before you renew.** A system touch map for builders before procurement reviews it for them, and a vendor-specific question sequence for CFOs walking into renewal.

But first, the seat stays — even as the meter changes. Then we’ll look at how each vendor is pricing the work, and what to ask before you sign.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260508_262_promptkit_1)

Most companies walk into 2026 renewals with the wrong artifact in hand. Procurement brings a seat-count spreadsheet. The builder brings an architecture diagram nobody outside engineering can read. Neither survives contact with a Salesforce AE who already knows their Flex Credit numbers cold, or with a security review that wants to know which SAP APIs the agent is hitting and under what identity. These two prompts came out of that exact mismatch: one maps every system your agent touches and flags the governed-path risks before the vendor flags them for you, the other generates a vendor-specific question sequence with the one question each vendor will try hardest to dodge.


## **Where the work moves**

The seat isn’t dying. People still need seats for dashboards, approvals, interfaces, records, workflow surfaces, analytics, exception handling, permissions, and admin control. The human doesn’t vanish from enterprise software just because an agent can fill out a form.

What changes is that an agent can use software without sitting in the software. The CRM gets read. A HubSpot lead gets enriched. A ServiceNow workflow gets triggered. An SAP API gets called. None of it requires a human spending the day inside that application — and the access can come through an API, a service account, a delegated user identity, or the vendor’s own agent framework.

The work still happens, but the old sentence — *this human uses this software* — no longer captures the value exchange.


## **How SaaS vendors price AI agent work**

It probably won’t be called an agent license. Salesforce calls them Flex Credits. Microsoft calls them Copilot Credits. Zendesk and HubSpot frame it as outcomes — automated resolutions, completed prospecting tasks. ServiceNow runs Assist currency and Action Fabric consumption side by side. Workday wraps Flex Credits and agent management into one story. SAP expresses control through API policy rather than credits. And Atlassian bundles Rovo credits into cloud subscriptions today, with overage billing waiting in the wings.

The names differ because every vendor wants the meter to sound native to its platform. The underlying move is identical: each one is establishing a commercial control point around non-human work.

The next renewal fight is no longer *how many people need seats?* It’s *who or what is allowed to act through this system, how often, under which identity, under which controls, and at what price?* That sounds like a licensing detail. It’s the SaaS business model adjusting to the fact that work no longer attaches cleanly to a human sitting in a product all day.

I’ve written before that AI isn’t killing SaaS so much as changing the way SaaS *tastes* financially. The old subscription model was predictable because usage was attached to employees and departments. AI scrambles that. Some work moves into custom internal tools. Other work becomes outcome-based. Some gets metered or bundled into subscriptions but capped by credits. The rest gets cheaper for the buyer and more expensive for the vendor to support. The agent license is where that pressure shows up in the contract.

A seat prices access to software. An agent license prices delegated work. Once you internalize that distinction, current vendor behavior makes sense.


## **Salesforce Agentforce pricing explained**

Salesforce is the cleanest example because it isn’t hiding the shift. The [Agentforce pricing page](https://www.salesforce.com/agentforce/pricing/) lists Flex Credits, conversation pricing, per-user Agentforce licensing, and action-based examples. The exact numbers matter at renewal, but the unit matters more. Salesforce is pricing agent work through credits and actions — updating a record, summarizing a case, answering an inquiry, executing a prompt, running a flow — and pulling that consumption into the usage meter.

The numbers behind that pricing model are no longer roadmap material. Agentforce hit $800 million in ARR in Salesforce’s most recent quarter — up 169% year over year and up from $540 million only one quarter earlier. The platform closed 29,000 deals since launch in September 2024. AI agents on Salesforce have delivered 2.4 billion Agentic Work Units to date — a metric Salesforce invented and defines as “one unit of AI work: a record updated, workflow triggered, decision made.” Roughly half of last quarter’s Agentforce bookings came from Flex Credits and half from higher-tier seat SKUs. Milano told analysts, “We have found the formula to monetize AI.” That sentence is the whole point. Salesforce is no longer experimenting with how to charge for agent work. It is reporting earnings on it.

In the old model, the service rep had a seat. In the new model, the rep may still have a seat, but the agent that identifies the customer, retrieves prior cases, drafts the response, updates the record, and triggers the next workflow also burns credits — at different rates depending on whether it’s a conversation, a voice interaction, or a custom action. The seat is still there. It just isn’t the whole bill anymore.

Buyers are now paying for people *and* for work moving through the system.


## **ServiceNow Action Fabric and agent pricing**

ServiceNow comes at the same problem from the other side. Where Salesforce makes the credit meter visible, ServiceNow makes the *governed action layer* visible. Its [Action Fabric announcement](https://newsroom.servicenow.com/press-releases/details/2026/ServiceNow-opens-its-full-system-of-action-to-every-AI-Agent-in-the-enterprise/default.aspx) reframes ServiceNow from a place where employees click around into a system where agents trigger real operational work.

ServiceNow’s claim goes further than passive reads. Agents can use the system of action through governed pathways — including its MCP Server — with identity, permissions, audit, and consumption metering attached. That positioning matters because ServiceNow sits in the part of the enterprise where actions have consequences: provisioning access, escalating an incident, kicking off onboarding, opening a change request, routing approvals, resolving a service issue, executing a playbook.

Each one is a unit of operational work doing the job a person used to do. If an agent does that work through ServiceNow, ServiceNow has a defensible claim that it provides more than storage or interface. It provides the workflow substrate, the rules, the audit trail, the permission model, the routing, and the operational reliability around the action. That’s a reasonable thing to price, if the meter is honest.

ServiceNow probably deserves to charge for agentic work. What matters is whether the charge is clear, measurable, controllable, and connected to value.


## **SAP API policy and AI agent access**

SAP is the most explicit warning that this game is about *control*, not just price. SAP’s 2026 [API Policy](https://help.sap.com/doc/sap-api-policy/latest/en-US/API_Policy_latest.pdf) draws a hard line around how customers and third-party systems can use SAP APIs, including restrictions on semi-autonomous and generative AI systems that plan, select, or execute sequences of API calls outside SAP-endorsed architectures or service-specific pathways.

You can read that generously. SAP runs finance, supply chain, HR, manufacturing, and procurement — places where careless automation creates real damage. SAP has legitimate concerns about performance, security, stability, support load, and whether a third-party agent is using published interfaces or quietly scraping its way around the product.

But the policy is also commercial. SAP is saying that agent access to SAP systems isn’t an open-ended customer right — it has to happen through sanctioned paths. That creates a new negotiation surface. If a customer wants an outside agent, an internal agent, or another vendor’s assistant to act across SAP data and SAP workflows, the first question may not be technical. It may be contractual: *is this allowed, through what interface, under whose architecture, and under what terms?*

That’s the agent license in its harder form. Not a friendly credit wallet. A boundary around who gets to automate the system of record.


## **Workday: managing the digital workforce**

Workday is giving us another version of the same future, in more organizational language. Its [Agent System of Record](https://blog.workday.com/en-us/managing-ai-powered-future-of-work.html) starts from a simple premise: if agents are going to become part of the workforce, companies need a way to manage them. Not as science projects. As operational actors. Who owns it? What systems can it access? What is it costing? Is it duplicating another agent? Is it still needed?

That framing is easy to underestimate. Workday isn’t bolting an AI feature onto HR and finance software. It’s trying to define the *management layer* for digital labor. If agents are workers, someone has to manage the org chart, cost, access, performance, and lifecycle of those workers. That won’t stay philosophical for long. It will become a budget line.

Workday has paired the management story with [Flex Credits](https://investor.workday.com/news-and-events/press-releases/news-details/2025/Workday-Illuminate-Expands-with-New-AI-Agents-for-HR-Finance-and-Industry-09-16-2025/default.aspx), included in subscriptions, expandable as customers use more agents and platform innovations. That is the enterprise AI adoption playbook in one move: include enough capacity to make the feature feel real, create a usage currency that spans multiple agentic products, then let spend grow as workflows move from experiment to operations.


## **Microsoft Copilot Credits and agent pricing**

Microsoft is the hybrid model at huge scale, and the hybrid has three layers. Microsoft 365 Copilot is the familiar seat at $30 per user per month — the worker gets a license. Sitting alongside it, [Agent 365](https://learn.microsoft.com/en-us/microsoft-agent-365/overview) is a separate per-user license at $15 per user per month, bundled into the new Microsoft 365 E7 “Frontier Suite” at $99. Agent 365 doesn’t build agents or run them. It governs the ones acting on behalf of licensed users — identity, observability, data loss prevention, Defender controls. Underneath both seats, [Copilot Studio pricing](https://www.microsoft.com/en-us/microsoft-365-copilot/pricing/copilot-studio) and Microsoft’s [billing documentation](https://learn.microsoft.com/en-us/microsoft-copilot-studio/requirements-messages-management) make the consumption meter explicit. Copilot Credits measure what an agent actually does — answers, generative answers, agent actions, Microsoft Graph grounding, flow actions, premium reasoning — at different rates per feature.

This is probably where most of the market lands. The human gets a seat. The organization gets a separate license to govern the agents acting on the human’s behalf. Custom agents, advanced actions, grounded reasoning, and high-volume workflows draw down credits underneath. It isn’t a clean replacement of seat pricing. Seats remain, governance gets its own line, and the credits run underneath. That stack is the whole story.


## **Zendesk and HubSpot: outcome pricing**

Zendesk and HubSpot represent the outcome-pricing version. Zendesk’s [automated resolutions](https://support.zendesk.com/hc/en-us/articles/5352026794010-About-automated-resolutions-for-AI-agents) charge around customer issues that AI agents resolve without human intervention, with verification rather than counting every bot interaction as value. HubSpot’s Breeze Customer Agent and Prospecting Agent moved to [outcome-based pricing](https://www.hubspot.com/company-news/hubspots-customer-agent-and-prospecting-agent-now-you-pay-when-the-task-is-complete) tied to resolved conversations and recommended leads.

This is the cleanest buyer-friendly version when it works. Don’t charge me because an agent talked. Charge me because the agent completed work I would have paid a person or process to complete. A resolved support conversation is easier to defend than a mysterious pile of AI credits. A qualified lead is easier to defend than a vague “agent session.”

The hard part is defining the outcome honestly. If the vendor controls the definition of *resolved*, the buyer needs to understand exactly how that outcome is measured, disputed, audited, and capped.


## **Atlassian: the soft launch**

Atlassian shows the soft-launch pattern. Rovo is included in paid cloud subscriptions, but [Rovo usage is metered](https://support.atlassian.com/rovo/docs/rovo-usage-limits/) in credits. Rovo Chat, Rovo Agents, and Deep Research all draw from allowances. Atlassian says it isn’t currently charging overages and would provide notice and opt-in before doing so.

That’s a reasonable adoption posture. It’s also how meters enter the building. The feature ships included, usage gets tracked quietly, teams build dependencies, and one renewal later the credit conversation arrives.


## **Software economics are catching up**

The old SaaS bargain worked because more value usually meant more seats. More employees in the product meant more revenue, more departments meant expansion, more workflows meant stickiness. AI agents complicate that equation. They can increase the work moving through the platform while *decreasing* the number of humans who need to touch the interface.

A support org resolves more issues with fewer human agents. Finance reconciles more exceptions without adding analysts. A recruiting team moves more candidates through the funnel without every recruiter living in every tool.

Vendors pricing only seats lose revenue. Buyers thinking only in seats blow their budgets. Builders ignoring the meter ship architectures that collapse at the first procurement review. Renewal is where all three failures meet.

The vendor’s argument: our system still does the work. It stores the data, enforces permissions, runs the workflow, logs the audit trail, supports the integration, absorbs the compute, and carries the risk when agents act at scale. We can’t give unlimited machine work away just because fewer humans are clicking.

The buyer’s argument: we bought AI to reduce the cost of work. If we keep paying for every human seat *and* pay again for every agent action, credit, resolution, API path, and workflow run, the vendor captures all the efficiency. We need a model where our cost goes down when the work gets cheaper.

Both sides are right. That’s why this is a real negotiation, not a simple anti-vendor story.


## **What a fair SaaS agent license looks like**

Vendors should charge for real infrastructure, risk, and value. Agents are not normal users. They run constantly, they retry, and they generate bursty API usage. They trigger workflows at machine speed and cause expensive support problems when permissions are wrong. They surface audit and compliance issues, and expose sloppy data governance that human pacing used to hide. A serious enterprise vendor cannot let every model, bot, and workflow runner hammer the system without rules.

But buyers shouldn’t accept agent pricing that’s just seat protection in a new costume.

A fair agent license has nine traits in common. The meter is visible and the unit makes sense. The customer can forecast usage. Failed or low-value work isn’t billed identically to completed work. Third-party agents get a governed path rather than a blocked one. The vendor distinguishes reading, drafting, recommending, writing, approving, and executing. The buyer can set caps. Usage data exports cleanly. The rate card holds for the term without quiet changes after adoption. And the model aligns with the value created.

A rent-seeking agent license looks different. It charges for vague AI access without explaining what is consumed. The vendor’s own agent becomes the only practical route while outside agents are treated as hostile. Customers get charged to use their own data in their own workflows. Failed work counts as billable. The meter stays hidden until renewal. Credits expire unused while overages bill immediately. And commercial lock-in arrives dressed in security language with no reasonable governed alternative.

That distinction matters because most companies are about to discover they don’t have an agent access strategy. They have seat counts, API clauses, bot policies, service accounts, automation scripts, integration licenses, and a pile of AI pilots scattered across departments. Demos can survive that mess. Production workflows can’t.


## **The CFO question is changing**

The old model was base subscription + seats + support + implementation. The new model is base subscription, seats, AI entitlement, agent access, credits, actions, conversations, resolutions, workflow runs, API usage, governance, monitoring, overages, and internal support. That sounds messy because it is. The clean ARR world was easier to buy, sell, value, and explain to a board. AI makes the software bill behave more like a labor bill mixed with a cloud bill.

CFOs have to stop asking only *how many licenses do we need?* and start asking *what work is moving through this platform, and what is the cost per completed unit of work?*

In customer support, the unit might be cost per resolved case. In sales, cost per qualified lead or correctly updated opportunity. In finance, cost per reconciled account, closed exception, or completed audit package. In HR, cost per employee request handled. In IT, cost per access request, incident, change, or onboarding workflow. The point isn’t to obsess over every micro-action but to keep the AI bill tied to business value rather than software theater.

If an AI agent resolves 30,000 support conversations a human team would otherwise handle, paying per resolution may be a great deal. If an agent saves five minutes for a highly paid salesperson but burns credits across ten background actions every time, the math may still work. If an agent mostly summarizes information employees could already find, but requires an expensive add-on for every worker, the economics fail. If an agent reduces headcount pressure but the vendor replaces every saved seat with higher usage charges, the buyer needs to negotiate hard.


## **Builders: licensing is part of the architecture**

A good enterprise agent doesn’t stop at accuracy. It is cost-aware. It knows which tools are expensive, which actions are reversible, and when to read, draft, ask, or execute. Every action gets logged with a recommendation-versus-write distinction. Retry loops get killed, sanctioned APIs get used, and nothing sneaks through the browser because the official path is inconvenient. The agent surfaces cost per task and lets the customer cap usage before it becomes a budget incident.

This is where a lot of agent builders will get surprised. The prototype works because the developer has access. The demo works because volumes are tiny. The first customer pilot works because nobody has audited the contract yet. Then procurement asks whether the agent is a user. Security wants to know whether the agent is allowed to access the data. Legal pulls the API policy and asks whether autonomous execution is permitted. The CFO asks why the forecasted credit consumption is a guess. And the platform vendor asks whether the agent is using an endorsed path.

That’s when the architecture either holds or collapses.

The best builders design for this from day one. The first move is mapping every SaaS system the agent touches, then classifying each operation: read, search, summarize, draft, recommend, write, approve, execute, delete. Each operation gets an identity model. Vendor meters get tracked. Costs surface on a dashboard. Customers get budget caps and configure which actions require human approval. And the audit history is rich enough that a business owner can understand what happened without reading raw logs.

That’s what gets agents into production, not bureaucracy.


## **Pricing follows platform control**

The larger fight is the one I wrote about in [Whoever Defines the Work Primitive Wins](https://natesnewsletter.substack.com/p/ai-work-primitives-access-vs-meaning). Access isn’t meaning. An agent that can click the refund button is doing something quite different from a system that understands the refund as a scoped, permissioned, auditable business action. The durable platform isn’t the one that can reach the most tools. It’s the one that defines the meaningful unit of work.

The agent license is the commercial expression of that same fight. If a vendor defines the object, the action, the permission, the validation, the audit trail, and the outcome, it will also define the meter.

Salesforce meters agent actions because it defines the actions inside the customer relationship workflow. ServiceNow does the same with operational actions across the enterprise action layer. Workday is moving toward managing agents because it already runs the employee system of record. Microsoft uses Copilot Credits because its surface — productivity graph, apps, agent studio — runs everywhere. And SAP is gating its APIs because uncontrolled agent execution at the system of record isn’t just a product concern. It’s an operational risk.

Pricing follows control. The vendor that defines the work primitive earns the right to argue it should price the work.

Buyers need to understand that before they walk into renewal season.


## **How to negotiate SaaS renewals with AI agent pricing**

The worst move is waiting until usage is already embedded. By then employees use the agent every day, customer workflows depend on it, and the finance close runs through it. The negotiating position has flipped. The vendor knows the work has moved. You know turning it off would hurt. Credit models, action tiers, and agent SKUs become much harder to challenge once that’s true.

The better move is to negotiate agent access *before* agent usage becomes mission-critical.

Three buckets of questions earn their place before you sign.

**What’s covered under current seats.** Are agents acting on behalf of licensed users included, or do they require their own entitlement? Can a third-party agent use the same governed path as the vendor’s own agent? Is API access for autonomous systems allowed at all?

**How the meter actually works.** Which actions consume credits, and do failed actions count the same as completed ones? Are reads, searches, summaries, drafts, writes, approvals, and downstream workflows priced differently, or rolled into one rate? Do overages auto-bill or pause? Is the rate card fixed for the term, and can caps be set by department, workflow, environment, or agent?

**What changes when the agent replaces human work.** This is the question vendors will try hardest to avoid. If an AI agent resolves a large share of support volume, can you reduce support seats? If a sales agent keeps records updated, can occasional CRM users move to lighter access? If an HR agent handles routine questions, does every employee still need the same tier?

Sometimes the answer is no for good reasons. Compliance requires named users, oversight requires seats, approvals require human licenses. But the question has to be asked. Otherwise the buyer ends up with the worst possible hybrid: old seat counts plus new agent consumption.

This is the practical CFO risk. AI can make work cheaper while making software bills more complicated. If finance doesn’t model the work, it will only see the line items. The vendor will show productivity. The business owner will show adoption. Procurement will see credits. The budget owner will see overages. Nobody will know whether the company is actually paying less per unit of work.

A workable model isn’t perfect, but it’s simple enough to start. For every agentic workflow, estimate the baseline human cost. Then estimate the software cost of the agent workflow: base seats, AI add-ons, credits, actions, resolutions, API access, model calls, implementation, governance, monitoring, and support. Compare on output quality, speed, risk, and volume. Three outcomes are likely. The agent reduces cost per completed task while keeping quality acceptable — scale it. The cost merely shifts from labor to a less predictable vendor meter — slow down and renegotiate. The speed or quality gain justifies higher software cost — say so honestly and budget it as a premium workflow rather than savings.

That’s how buyers separate real AI savings from vendor packaging.


## **Be anti-opaque, not anti-vendor**

The best vendors will help customers run that math. They’ll provide dashboards that show usage and outcomes together, make credit burn understandable, and offer caps and alerts. They’ll distinguish high-value actions from low-value chatter. They’ll support third-party agents through secure interfaces rather than treating every outside agent as a threat. They’ll connect spend to work completed.

The weaker vendors will hide behind complexity: broad bundles, vague AI access, expiring credits, unclear overage rules, platform restrictions dressed up as safety. They’ll claim every agentic path must run through their own product while offering no serious alternative for customer-built agents. They’ll make it impossible to know whether the AI bill reflects value or just activity.

Buyers shouldn’t be anti-vendor. They should be anti-opaque.

There’s a good version of the agent license. We probably need one. Enterprise agents can’t become serious if vendors pretend machine work is just another human seat, or if customers expect unlimited agent execution for the price of yesterday’s UI access. A world where agents safely run business processes needs pricing, governance, audit, and support.

But that pricing has to be honest about what changed. The old SaaS unit was the user. The new AI unit is the work. Not every kind of work, not magically, not all at once — but the direction is clear. As software becomes substrate for agents, pricing shifts from *who can log in?* to *what work can be delegated?*

That’s the line buyers should take into 2026 renewals. Don’t ask only for an AI discount. Ask for the agent access map, the sanctioned interfaces, the action taxonomy, and the credit rate card. Ask for the outcome definition, the overage behavior, the third-party agent policy, and the seat-reduction logic. Ask for usage logs, and ask for the right to cap, pause, export, audit, and renegotiate as workflows move from pilot to production.

If you’re building agents, don’t wait for procurement to discover this for you. Build as if every action has a cost, every system has a policy, every workflow needs an owner, and every agent will eventually have to justify its bill.

The companies that understand this distinction will negotiate better, build better, and avoid the trap of treating AI as either free magic or vendor tax.

Your next SaaS renewal won’t just ask how many employees use the product. It will ask how much work you’re willing to let machines do inside it.

That’s the moment the real AI software bill begins.

[![](https://substackcdn.com/image/fetch/$s_!Wycm!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff495bcae-894d-4d1c-a65d-70166b77333e_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Wycm!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff495bcae-894d-4d1c-a65d-70166b77333e_1024x1024.png)
