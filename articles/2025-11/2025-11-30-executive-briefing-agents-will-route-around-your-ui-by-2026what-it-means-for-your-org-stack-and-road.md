---
title: "Executive Briefing: Agents Will Route Around Your UI by 2026—What It Means for Your Org, Stack, and Roadmap"
author: "Nate Jones"
published: 2025-11-30
url: https://natesnewsletter.substack.com/p/executive-briefing-pixels-are-throwaway
audience: everyone
scraped_at: 2026-01-05 19:10:52
---

I once deleted half a production e-commerce store because of Oracle iStore.

If you’ve never used iStore, count yourself lucky. It’s a monument to an era when interfaces were so expensive to build that millions of users had to share the same terrible screens, preferences be damned. The interface was the product. You learned it, got certified in it, and lived inside it whether you liked it or not.

That economic reality just broke.

Google released Imagen 3 as an API-first service a few weeks ago. Within days, developers on X and Reddit were passing structured data to the API and getting back fully-rendered charts, dashboards, and UI components—not mockups, but functional interface elements generated on demand, displayed once, then discarded. User interfaces have become just another output modality, like text or code. Pixels are throwaway now.

This matters because software is decoupling into two layers: a substrate that needs to be stable, and pixels that matter far less than they used to. The question for every executive is simple: where does your value actually live?

Five themes emerged from working through this shift with clients:

- **Coherent interfaces were an economic necessity, not a law of nature.** Three overlapping shifts just made that constraint obsolete—and most product roadmaps haven’t caught up.
- **Value is migrating to a three-layer model.** Substrate (systems of record), intelligence (agentic orchestration), and pixels (increasingly disposable). Most executives haven’t mapped where their value actually sits across these layers.
- **Coherent interfaces still win in specific, predictable contexts.** High-stakes spatial memory work, regulated flows, team collaboration. The binary framing—”all generative” versus “all traditional”—misses the point.
- **Computer-use agents are the forcing function.** Once agents can drive any interface, your UI preferences as a vendor stop mattering. Only your substrate quality and agent-addressability matter. This makes the shift urgent rather than interesting.
- **Talent and roadmaps need to move up-stack.** Designers, PMs, and engineers must shift from “what page do we ship” to “what intents do we support, what state changes must be safe, and how do agents and generated UIs consume what we build.”

This piece walks through each theme with the framing questions and diagnostic tools I’ve been using with clients navigating these decisions.

By the end, you’ll have a lens for evaluating your software strategy—whether you’re building, buying, or leading teams that do either. You’ll have a diagnostic to run against your portfolio. And you’ll have access to a prompt pack you can use to pressure-test your product roadmap against the disposable pixel thesis.

> *This is an Executive Circle briefing, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via this 60 second video explaining what’s in each tier, and you can change your plan here.*

---


## **[Grab the Disposable Pixel Strategy Prompts](https://www.notion.so/product-templates/Disposable-Pixels-Prompts-2b95a2ccb52680588245d39eab844a73?source=copy_link)**

I’ve built a prompt pack for strategic conversations about where your organization stands on these issues. Five prompts for different roles: executive portfolio audit, product-level workflow redesign, vendor/RFP evaluation, talent and org design, and a coherent-vs-disposable decision tool for specific interfaces.

Each prompt is loaded with context from this piece—the three-layer model, the diagnostic questions, the talent implications, the implementation path—and wired to work the way a good advisor does: one question at a time, pushing toward specifics, flagging common traps.

---


## **Why Interfaces Were Expensive (And Why That Just Changed)**

The core insight is simple: for forty years, we treated user interfaces as precious because building them cost real money. Design, development, QA, localization, documentation, training—every pixel had to be hand-tooled, so every interface had to serve millions of users and last for years. That constraint shaped everything. It created Salesforce certifications, Workday training programs, and change management as a discipline. It made “opinionated interaction design” a selling point rather than a limitation.

That constraint is lifting. Three shifts happened simultaneously, and they reinforce each other.

**Generative UI technology reached production quality.** Galileo AI, Vercel’s v0, Uizard—these tools generate multi-screen interfaces from natural language. They’re backed by serious capital and integrated into major developer platforms. A startup called Wabi lets consumers make generative interfaces for personal use. The technology layer is here and spreading fast.

**Design thinking caught up.** A growing conversation has emerged around ephemeral, hyper-contextual applications—panels created and destroyed while application state persists underneath. We’re developing vocabulary for interfaces that don’t need to last, which is different from the technology that enables them. Both are advancing at once.

**Agentic software started driving other software.** Google made Imagen 3 API-first from day one, positioning it as infrastructure for agents rather than a tool for humans. Developers are already using that API to pass structured queries—”show me last week’s sales by region”—and retrieve rendered charts to display in Slack or discard after a single glance. I’m not describing theory; I’m describing what I see on X and Reddit with screenshots and videos. The visual interface has become an API call away.

The result is software generated from intent and context, private to the user in that moment, discarded when the moment passes. One instructive observation from developers who’ve built twenty or thirty “vibe-coded” apps: many were valuable for exactly one use, and that was worth it. The value was in the moment, not the artifact.

---


## **The Forcing Function: Computer-Use Agents**

This would be interesting but not urgent if it stopped at generative UI tools. It doesn’t.

Computer-use agents—software that browses interfaces the way humans do—are improving fast. Once those reach production quality, users choose their interface regardless of what you, the vendor, prefer. You can insist humans must use your monolith directly. But if an agent can have a voice conversation with the user, navigate your software, extract what’s needed, and bring it back, the user’s experience is whatever interface they choose. Your software becomes a data source accessed through their preferred channel.

The timeline isn’t distant. Advances in image generation and understanding mean a capable computer-use agent is close behind. By 2026, users could wake up, talk to an agent, and have it browse the monolith software you insist only humans can use—extracting data and bringing it back without touching your UI at all.

If agents can’t safely call your core capabilities, you’ll be bypassed or wrapped. If they can, you become infrastructure. The question isn’t whether this shift happens. The question is whether you’re positioned on the winning side when it does.

---


## **The Three-Layer Model: Substrate, Intelligence, Pixels**

Software value isn’t declining—it’s redistributing. Most executives haven’t mapped where their value actually sits across the layers that matter.

**Layer One: The Substrate.** Systems of record and decisioning. Data models, workflows, permissions, audit trails, compliance logic. Domain-specific engines for forecasting, pricing, routing. APIs and webhooks that let other systems call your capabilities.

This is what B2B SaaS was always selling underneath the interface—the hard stuff, the value-dense stuff, where moats actually live. Image generators don’t touch it. Salesforce survives because its substrate is deep: the data model, the automation rules, the permission structures, the compliance controls. The interface is increasingly a convenience layer on top of defensible infrastructure.

If your competitive advantage lives here, you’re more secure than you think. If it doesn’t, generative UI will accelerate your problem.

**Layer Two: The Agentic Intelligence Layer.** Orchestration between substrate and interface. Agents that call APIs, retrieve data, decide what to surface and when.

When a user says “show me which enterprise customers in EMEA have renewal risk this quarter, identify CSM touch gaps over 45 days, and draft outreach,” that’s a series of tasks an agent can execute against the substrate—hitting the CRM, the data warehouse, the email system, deciding what needs a UI and what should auto-execute.

This layer is where new value is being created. The companies building robust agent-to-API infrastructure are positioning for a world where humans describe outcomes and agents assemble the interfaces to achieve them. Everyone running a B2B SaaS company is working on some version of this. So are most businesses for back-office operations. This is what we always wanted software to be: personal, responsive to intent, not something we had to conform to.

**Layer Three: The Disposable Pixel Layer.** The interface itself—not hand-tooled artifacts, but compiled outputs of intent.

Only when the system needs your judgment does it compile pixels. A one-off panel with a ranked table of at-risk customers. Inline suggested outreach. A toggle for send now, schedule, or edit. A specific cohort chart for this question only. A narrow editor UI for exactly one structured decision.

Instead of building a settings page serving every user, you generate a settings view showing this user what they need now. Instead of maintaining a dashboard with twelve charts, you generate the three charts relevant to this question at this moment.

The maintenance implications alone are significant. Traffic in SaaS applications decays stochastically—top pages get most sessions, but you maintain hundreds of pages that a handful of people use. Those are at risk. Expect SaaS applications with two or three main pages and everything else generated on the fly.

---


## **Diagnostic: Mapping Your Portfolio by Layer**

The three-layer model is vocabulary. To make it actionable, you need to map your own portfolio. Three questions per layer:


### **Substrate**

**What critical business states do you own end-to-end?** Contracts, risk scores, balances, compliance records, customer lifecycle stages—places where you’re the system of record, not a viewer of someone else’s data.

**Can other systems address those states cleanly via API?** Not “do we have an API” but “can an external agent actually call our core capabilities without human navigation?” If the honest answer is “sort of, but you’d really need our UI,” that’s a warning.

**Where are you hiding important logic behind a UI click-path?** Every place requiring three screens to accomplish what should be an API call is a vulnerability.


### **Intelligence Layer**

**Do you have agentic workflows in true production?** A demo working in a conference room is worth nothing. A workflow running in production, handling edge cases, hardened against real-world messiness—that’s valuable.

**Where do you have enough data and rules to safely automate decisions?** Clear decision criteria applied inconsistently by humans are candidates for automation.

**Which decisions are you keeping human-in-the-loop, and why specifically?** The answer should be concrete, not “we’re being cautious.”


### **Pixel Layer**

**Which UI surfaces do users complain about but you maintain because you built them?** Everyone has these.

**How many pages have less than 5% of sessions but cost real engineering time?** If you can’t answer quickly, that’s itself a red flag.

**Where do people screenshot or export data to work elsewhere?** That’s a signal they want different pixels than you’re providing.

---


## **Where Coherent Interfaces Still Win**

The binary takes are wrong in both directions. Generative UI will transform enterprise software, and coherent interfaces will survive in specific contexts. The question is knowing which workflows need which approach.

**High-stakes work requiring spatial memory.** Traders, doctors, incident responders build deep mental models of their tools. The Bloomberg Terminal looks like a maze to outsiders, but experienced users navigate by muscle memory—that speed is worth the ugly interface. Bloomberg has hundreds of thousands of professional subscribers paying tens of thousands annually per seat. That stickiness isn’t about features; it’s about mental models built over years. You can’t disrupt it with a prettier interface.

This is why I’m skeptical of Perplexity’s finance play. AI-driven research against real-time market data is useful for certain workflows, but it won’t displace Bloomberg for users who’ve encoded its command language into their fingers. There’s a floor of coherence you can’t cross without hurting performance.

**Regulated flows requiring reproducibility.** “Show me exactly what the user saw when they approved this loan” is an audit requirement. Ephemeral UI makes that hard unless you capture and version the UI specification itself—possible in theory, complicated and expensive in practice. Incentives favor coherent interfaces for compliance-heavy workflows.

**Team collaboration requiring shared views.** “Look at this dashboard” and “check this queue” require everyone seeing the same thing. Different ephemeral panels for each user need explicit mechanisms for pinning, sharing, standardizing. Solvable, but adds friction.

Slack is interesting here. It benefits from generative UI not because Slack is generative (it’s very stable), but because stability makes it a natural destination for agent-generated outputs flowing back to teams. Demo videos of Imagen 3 charts always show them popping into Slack. That’s Slack’s value proposition shifting: stable team collaboration substrate in a generative UI world.


### **The Decision Framework**

**High-stakes, time-critical work** (trading, ICU, incident response): Bias toward coherent, stable UI with strong spatial consistency.

**Exploratory, analytical, one-off work** (”get me a view of X for this meeting”): Bias toward disposable, generated panels.

**Auditable flows** where regulators can demand “show me what the user saw”: Keep stable UI or invest heavily in logging and versioning generative specs.

**Collaborative work** where multiple people need the same view simultaneously: Define shared, named views with explicit pinning and sharing rules.

The mature pattern is a spectrum: standardized shells for regulated flows, shared operational views, training, and collaboration—with disposable pixels inside that shell for exploratory analysis, micro-decisions, personalized shortcuts.

---


## **Implications for Buyers**

If you’re buying software, the three-layer model changes evaluation criteria. Grade vendors on substrate quality and agent-addressability, not UI polish.

**Questions to add to RFPs:**

What core states does this product own as its system of record? How clean and well-documented are the APIs for those states? Could your own agents complete key workflows without a human touching the UI? How does the vendor log and expose system activity for audit and compliance? How hard would it be to replace their UI with your own or a generative surface?

If a vendor’s competitive response is “our interface is beautiful,” that’s a red flag. If they can articulate why their substrate is defensible and how agents can safely call their capabilities, that’s a green signal.

The deeper issue: UI is becoming a product surface you don’t fully control. Customers using generative tools on top of your APIs render their own views of your data. Your canonical UI becomes one frontend among many, competing with internal task panels, copilot-generated micro apps, third-party workspace tools. You risk disintermediation—aggregated behind someone else’s agentic interface.

SaaS wins where it becomes substrate as a service: owning canonical state for contracts, ledgers, records, risk models; embedded in domain flows tracking real value; safe and predictable for agents to call. Strong schemas, good safeguards, idempotency. Less a thing with screens, more a high-integrity service agents and generators rely on.

---


## **Talent Implications**

Job descriptions are shifting whether HR knows it or not.

**Designers** move from owning specific flows and screens to defining interface grammars: constraints, tokens, safe snap-points for generative UI. The question shifts from “What should this screen look like?” to “What rules govern how screens get generated?” Design system roles already emphasize component libraries and design tokens; that accelerates dramatically when downstream consumers include AI generators, not just human developers.

*Green signal:* Talks about constraints, tokens, composition, safe patterns for generators. *Red signal:* Portfolio is 100% static screens with no language around runtime assembly.

**Product managers** move from “What page do we build next?” to “What intents do we support? What state changes must be safe? What decisions require human judgment versus full automation?” Instead of speccing wireframes, you’re speccing intent-state-outcome loops.

*Green signal:* Specs in terms of intents, state machines, guardrails. *Red signal:* Specs are lists of pages and buttons.

**Front-end engineers** move from pixel-pushing to building stable interfaces for agents and generators: thin shells, validation logic, composability within constraints. The job becomes scaffolding that generative systems can assemble safely.

*Green signal:* Experience building shells, component APIs, validation layers. *Red signal:* Proudest work is pixel-perfect pages tightly coupled to current flows.

**The backlog changes too.** Instead of “add settings page,” you’re tracking new intents to support, new system behaviors, new constraints the generator must respect, new components it might use.

If hiring and performance reviews still reward shipping pages rather than improving substrate and intelligence, you’re misaligned with where value is moving.

---


## **Implementation: 30-Day and 90-Day Moves**


### **Next 30 Days**

**Audit your portfolio against the three-layer model.** For each major product area: where does value actually live? Substrate, intelligence, or pixel layer?

**Map substrate versus pixel features.** Identify the 20% of your interface driving 80% of user value—that’s probably substrate or intelligence work. The rest is candidate for generative approaches.

**Test agent addressability.** Can an external agent call your core functions via API? Is your schema clean enough for other software to compose with?


### **Next 90 Days**

**Identify one workflow where disposable pixels could replace coherent UI.** Best candidates: exploratory analysis, micro-decisions, personalized shortcuts. Worst candidates: regulated flows, training, shared operational views.

**Prototype the split architecture.** Thin stable shell with controls users need to stay oriented; generative or agentic UI handling content inside. See what breaks.

**Document coherence floors.** Which interfaces must stay stable, and why? Compliance, collaboration, cognitive load—make decisions explicit so teams aren’t guessing.


### **Metrics**

**Engineering time split:** substrate versus intelligence versus pixel maintenance. If most time goes to pixels, you’re investing in the wrong layer.

**API coverage:** percentage of core capabilities callable without UI automation. Should be increasing.

**Intent-to-interface latency:** median time from identifying a new intent to supporting it with some interface. Should shrink dramatically in a generative world.


### **Red Flags**

You can’t quickly answer “what are our ten least-used pages?” Your APIs mirror UI screens rather than mapping to business concepts. No one owns agent readiness as a first-class responsibility.


### **Green Signals**

Design system treats components as tokens and grammar, not just Figma artboards. At least one live workflow where screens generate per user and intent. Vendor RFPs already include questions about agentic access and schema quality.

---


## **Who Wins, Who Loses**

**Winners:**

Products that are agent-addressable—software other agents can call becomes infrastructure; software they can’t becomes friction.

Products with clean schemas that compose well—gains distribution as agents assemble workflows from multiple sources.

Teams treating UI as language and runtime, not frozen screens—iterate faster, maintain less.

Buyers insisting on substrate and agentic quality in RFPs—end up with software that ages well.

Individuals who work at substrate and intelligence layers—defining constraints, architecting workflows, building systems agents can use.

**Losers:**

Products whose only moat is beautiful interface—generative tools will commoditize pure pixel-layer value.

Vendors resisting agent calls—insisting users stay in your monolith works until computer-use agents let them route around you.

Talent stuck in coherent-pixel thinking—designers who only spec screens, PMs who only write feature requirements, engineers who only implement mockups. The job is changing faster than most realize.

---


## **The Comparison That Clarifies**

Traditional coherent interfaces versus disposable pixels, across the dimensions that matter:

**Time horizon:** Months or years versus seconds.

**Design target:** Personas, roles, generalized workflows versus agents combining user, moment, and goal.

**Mental model:** “Learn this app” versus “state your intent.”

**Cost structure:** Heavy upfront, amortized over years versus heavy model training, functionally free pixels.

**Where consistency lives:** Pixel layer (same screens for everyone) versus substrate and agent layer.

**Differentiation:** Look and feel, interaction design, UX patterns versus outcomes and speed from intent to action.

You don’t need to move entirely to the right column. You need to understand which column describes your current approach and where you’re headed.

---


## **What’s Your Read?**

Does your product portfolio look different through this lens?

Software isn’t dying. It’s decoupling. The companies that understand which layer their moat sits in—and invest accordingly—will be positioned well. The companies that keep pouring resources into pixel work while their substrate atrophies will wonder why their AI investments aren’t paying off.

I’d like to hear where you’re finding substrate strength and where you’re discovering you’ve over-invested in pixels.

[![](https://substackcdn.com/image/fetch/$s_!zKfM!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe8d36475-9a36-406d-8d7a-9696d1ac8832_512x512.png)](https://substackcdn.com/image/fetch/$s_!zKfM!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe8d36475-9a36-406d-8d7a-9696d1ac8832_512x512.png)
