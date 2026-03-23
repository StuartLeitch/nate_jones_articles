---
title: "5 AI agents, 5 contradictory bets, 3 questions that tell you which one fits — and the prompts to pressure-test your answer"
author: "Nate Jones"
published: 2026-03-23
url: https://natesnewsletter.substack.com/p/5-ai-agents-5-contradictory-bets
subtitle: "Watch now | The AI agent wars are a product strategy case study. Here's the framework."
audience: everyone
scraped_at: 2026-03-23 12:00:16
---

OpenClaw is the most consequential provocation in AI since ChatGPT. And the coverage — both the “who’s winning” horse race and the “oh God the security” dumpster fire — is hiding the actual story.

Every major company responding to OpenClaw made a fundamentally different bet on the same set of tradeoffs. Nvidia compared it to Linux. OpenAI brought the creator on board. Meta spent $2 billion on Manus. Perplexity shipped a $200/month cloud agent, then two weeks later shipped a *second* product (a local agent on a dedicated Mac) because cloud alone wasn’t close enough. Anthropic shipped Dispatch. Shenzhen’s government started subsidizing companies that build on it. A thousand people lined up outside Tencent’s headquarters to get the software installed on their laptops, and the same Chinese users who paid 599 yuan for installation are now paying 299 yuan for removal. “This isn’t embracing AI,” one RedNote user wrote. “It’s paying the stupidity tax twice.” An installer’s listing offered one free cooking service alongside the deployment.

And Lovable, the most copied AI product of 2025, $400 million ARR and $6.6 billion valuation, just announced it’s expanding beyond app building into general-purpose agent tasks. The product everyone was copying is now responding to the same gravitational force as everyone else. All of this in under four months from a hobby project with a lobster emoji.

Everyone is responding. But nobody is responding the same way, and that divergence is the real story.

**Here’s what’s inside:**

- **The three-axis framework.** Where the agent runs, who picks the model, and what the interface assumes about you: the evaluation lens that holds for every agent product launching this year.
- **Five strategic plays dissected.** OpenClaw’s sovereignty bet, Perplexity’s delegation play, Meta’s distribution move, Anthropic’s safety positioning, and why Lovable’s expansion is the subplot that should be taught in business schools.
- **The map.** A product strategy landscape showing exactly where each agent sits and what it means for developers, knowledge workers, enterprise buyers, and product builders.
- **How to evaluate the next one.** Three questions to ask about any new agent product, and why the floor matters more than the ceiling.
- **The prompts.** An agent selection advisor that won’t let you pick based on hype, a compression stress-test for product builders, and a reusable three-axis evaluator you can run on every agent launch from here forward.

Let’s break it apart.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260320_426_promptkit_1)

Most people will pick an AI agent the same way they pick a restaurant in a foreign city — whatever has the most reviews, or whatever their friend mentioned last. That’s how you end up with a tool that doesn’t match your data governance reality, your technical floor, or your actual workflow. These three prompts prevent that. The **Agent Selection Advisor** interrogates your real constraints before recommending anything. The **Compression Stress-Test** forces product builders to answer whether a general-purpose agent can already do their core task at 70% quality. The **Three-Axis Evaluator** is the one you’ll reuse — paste it in every time a new agent launches and let the framework do the sorting.


## The gravitational pull of the lobster

The scale of the response is worth dwelling on because it’s not just big companies reacting. The open-source ecosystem fractured into over a dozen serious forks within six weeks. NanoClaw (700 lines of TypeScript, built the day after OpenClaw’s rebrand) exists because the original’s 430,000 lines of code are too large for any human to audit. ZeroClaw rewrote the whole thing in Rust. Moltis targeted enterprise Rust deployments. OpenFang pitched itself as an “agent operating system.” Nanobot out of Hong Kong stripped it down to 4,000 lines of Python. Each fork attacked a specific weakness of the original: security, performance, auditability, resource footprint. Each one gathered thousands of stars.

This is what happens when a product defines a category so clearly that every weakness becomes a startup thesis. Linux had the same dynamic. So did Android. The original is messy and powerful and dangerous and wildly adopted, and the entire ecosystem that forms around it is a series of responses to the question: “What if we did that, but with this one thing fixed?”

The problem is that when every product, open-source fork or billion-dollar corporate launch, gets measured against the same reference point, they all blur together. Different flavors of “AI agent that does stuff for you.” The temptation for users, enterprise buyers, and tech journalists is to flatten them into a feature comparison table and pick the one with the most checkboxes.

That’s a mistake. These products are making categorically different bets. The differences run along three axes, not one, and getting the axes right is the difference between adopting the right tool and spending three months with the wrong one.


## Three axes, not one

The media narrative frames this as a spectrum of control. OpenClaw gives you the most. Perplexity gives you the least. Everything else lands somewhere in between. That framing isn’t wrong, but it’s incomplete in a way that leads to bad decisions.

The three axes that actually matter are:

**Where does the agent run?** Local (your machine), cloud (their servers), or hybrid. This determines your data privacy posture, your security surface area, and who’s responsible when the agent deletes your email inbox.

**Who orchestrates the intelligence?** Single-model (one LLM does everything), multi-model (a harness routes tasks to specialized models), or model-agnostic (bring your own). This determines cost, quality ceiling, and vendor lock-in.

**What’s the interface contract?** Do you interact through a messaging app you already use, a dedicated desktop app, a phone, or a web dashboard? This determines who can actually use the product, which is a more important question than it sounds.

Plot each product on these three axes and the strategic logic snaps into focus.


## OpenClaw: The sovereignty play

OpenClaw runs locally. Your machine, your API keys, your data. The agent connects to any LLM — Claude, GPT, DeepSeek, Gemini, local models through Ollama. The interface is whatever messaging app you already live in: WhatsApp, Telegram, Discord, Signal, iMessage, Slack.

This combination (local runtime, model-agnostic intelligence, messaging-native interface) isn’t a product decision. It’s a political statement. OpenClaw’s thesis is that the agent should belong to the user, full stop. No platform mediating the relationship. No subscription extracting rent. No corporate policy deciding what the agent can and can’t do.

The strategic advantage is real. You control your data completely. You can run the cheapest model for 80 percent of tasks and route the remaining 20 percent to frontier models. Developers with infrastructure skills pay essentially nothing beyond inference costs. The 100-plus skill system means the community extends capability faster than any single company can.

The strategic cost is also real. The security surface area is enormous. CVE-2026-25253 was a critical remote code execution flaw. Researchers found over 40,000 publicly exposed instances within weeks of the viral surge, most with weak or missing authentication. The skills registry got hit with a supply chain attack: over 800 compromised skills, roughly 20 percent of the registry, including hundreds that deployed. Palo Alto Networks called it a “lethal trifecta” of risks. Gartner called the design “insecure by default.” A Meta AI security researcher asked her OpenClaw to triage her overflowing inbox; it started deleting everything at speed and couldn’t be stopped. One of OpenClaw’s own maintainers said publicly: “if you can’t understand how to run a command line, this is far too dangerous of a project for you to use safely.”

Who this is actually for: Developers and technical power users who want maximum control, who are comfortable configuring and securing their own infrastructure, who want model flexibility, and who are willing to trade safety guardrails for sovereignty. If your threat model is “I don’t trust anyone else with my data,” OpenClaw is the only honest answer.

Who should not use this: Non-technical users. Enterprise teams without dedicated security staff. Anyone whose risk tolerance doesn’t extend to a community-maintained skills registry with a history of supply chain attacks.


## Perplexity Computer: The delegation play

Perplexity Computer runs entirely in the cloud. You describe an outcome. The system decomposes it into subtasks, assigns each to purpose-built sub-agents, selects the optimal model from a pool of 19, and executes the workflow in a sandboxed environment. It can run for hours, days, or (per Perplexity’s claims) months. You get interrupted only when the system hits a genuine blockade requiring a human decision. Everything else, it handles.

The strategic bet here is the opposite of OpenClaw’s. Where OpenClaw says “your machine, your risk,” Perplexity says “our infrastructure, our guardrails, your outcome.” The sandbox means failures stay contained. The agent can’t reach your local files or your network. The multi-model routing means Perplexity optimizes for quality per task (coding goes to one model, writing to another, image generation to a third) without the user needing to know or care which model is running.

At $200 a month for the Max subscription, the pricing is aggressive but pointed: Perplexity is betting that knowledge workers will pay a premium for the delegation contract. Not “help me do this.” “Do this for me, and hand me the finished deliverable.”

And the enterprise play is already live. Perplexity launched Computer for Enterprise at its Ask 2026 conference, barely two weeks after the consumer debut, with Slack integration, Snowflake connectors, and SSO. They claim over 100 enterprise customers messaged them in a single weekend demanding access. The enterprise tier reportedly runs $325 per seat per month.

But here’s the detail that reveals how strong the OpenClaw gravitational pull is: at that same conference, Perplexity announced a second product, “Personal Computer,” that runs locally on a dedicated device like a Mac mini, with full local file access. The company that bet on cloud-managed delegation felt the need to ship a local agent too, because OpenClaw had redefined what users expect. Perplexity explicitly positioned it as more secure than OpenClaw — requiring user confirmation for all actions, with a built-in audit trail. They also rushed Computer onto iOS and Android by mid-March and embedded it in their Comet browser. Web launch to five surfaces in three weeks. The speed tells the story more than any product spec could.

The honest limitation: Perplexity canceled a press demo hours before it was scheduled due to product flaws discovered at the last minute. Generated applications ship with a “Created with Perplexity Computer” watermark. And the fundamental question Perplexity hasn’t answered is whether model routing becomes commoditized. If every orchestration layer can route to the same set of frontier models, what’s Perplexity’s moat? The harness? Search infrastructure? Brand? The speed of their surface expansion, web to iOS to Android to Comet browser to local Mac mini in under three weeks, suggests they know the window for establishing that moat is short.

Who this is actually for: Knowledge workers and enterprise teams who want outcome-level delegation without infrastructure management. Finance analysts running overnight due diligence. Marketing teams generating competitive intelligence briefs. Anyone whose workflow looks like “I describe what I need, I go home, I come back to a finished deliverable.” The cloud sandbox is a feature, not a limitation, for these users. It means they don’t have to think about security at all.

Who should not use this: Developers who want to tinker with the underlying models. Teams whose data governance requirements prohibit third-party cloud processing (though Personal Computer on a dedicated Mac partially addresses this). Anyone who needs the kind of deep system access and customization that OpenClaw provides.


## Manus (Meta): The distribution play

Meta acquired Manus for over $2 billion in late December 2025. Manus was already doing $100 million in annual recurring revenue, the fastest zero-to-$100M run anyone had documented at the time. And this week, Manus launched a desktop application that brings its cloud-based agent onto local machines.

The strategic logic here is distribution. Meta doesn’t need the best agent. Meta needs an agent that reaches 3 billion people. Manus’s original interface ran through a web UI. The desktop app with “My Computer” capability (reading, editing, and launching local files and applications) aligns Manus with OpenClaw’s local-execution model while maintaining the managed, permission-gated approach of a commercial product. Unlike OpenClaw, every action requires explicit user approval: “Allow Once” or “Always Allow.”

This is the consumer-safety bet. Not the developer’s “give me root access” philosophy. Not the enterprise’s “route everything through compliance.” The consumer’s “I want this to be useful, I don’t want it to be scary, and I don’t want to configure anything.”

Where Perplexity routes across 19 models, Manus is an execution layer on top of whatever models Meta is running, currently a mix of internal models and external APIs. Manus claimed the platform had processed over 147 trillion tokens and powered 80 million virtual computers before the acquisition. That scale is Meta’s real asset: battle-tested orchestration at consumer volumes.

The strategic tension: Manus was founded in China, relocated to Singapore, and Meta explicitly stipulated no continuing Chinese ownership interests. China’s Ministry of Commerce opened an investigation into potential export control violations. This geopolitical overhang isn’t just a risk factor; it shapes the product roadmap. Every feature decision at Manus now runs through Meta’s regulatory and reputational calculus, which means the speed-to-market advantage that made Manus viral in the first place may slow under the weight of a $2 trillion parent company’s compliance apparatus.

Who this is actually for: Consumers and small businesses who want AI agent capability through familiar interfaces without terminal commands or infrastructure management. The person who heard about OpenClaw, got excited, tried to install it, and gave up after forty-five minutes. The small business owner who wants to automate file organization and scheduling without hiring a developer.

Who should not use this: Developers who want model flexibility. Enterprise teams that need SSO and compliance certifications. Anyone philosophically opposed to giving Meta more data surface area.


## Anthropic Dispatch: The safety play

Anthropic launched Dispatch as a research preview on March 17 — the day before Manus Desktop launched. Coincidence in timing, but not in strategy.

Dispatch lets you control your Claude Cowork agent from your phone. One persistent conversation. Your phone issues commands, your desktop executes them. Claude accesses local files, connected applications, and plugins. Code runs in a sandbox. Everything stays on your machine.

The strategic positioning is precise: Dispatch is OpenClaw’s capability with Anthropic’s safety posture. Local execution (like OpenClaw), but gated by a controlled client (unlike OpenClaw). Phone-based remote control (like Manus’s multi-device approach), but single-model and sandbox-first (unlike Manus). Persistent conversation (like Perplexity’s long-running workflows), but your data never leaves your computer (unlike Perplexity).

This is the “we’ll do the same thing, but properly” play. Multiple outlets framed it exactly that way. The implicit pitch: OpenClaw showed what people want. Dispatch gives it to them without the security nightmares.

The honest limitation: Early testing by MacStories found roughly 50 percent reliability on complex tasks. The desktop must remain awake and connected; there’s no background service. No notifications when tasks complete. Single thread only. It’s a research preview, and it feels like one.

But the strategic bet isn’t about the current feature set. It’s about the trust gradient. Anthropic is betting that the agent market will bifurcate into a developer tier (OpenClaw, Claude Code) and a professional tier (Dispatch, Cowork), and that the professional tier will be won by whichever company establishes the strongest safety reputation. The $20/month Pro plan and $100/month Max plan price Dispatch as an affordable professional tool, not an enterprise platform.

Who this is actually for: Non-technical professionals who want agent capability on their existing files and apps, who care about data privacy, and who are willing to accept a managed, single-model experience in exchange for a product they don’t have to configure. The marketing manager. The financial analyst. The operations lead who needs reports compiled from five different sources.

Who should not use this: Anyone who needs multi-model routing. Developers who want programmatic access. Teams that need always-on execution without a desktop staying awake.


## The irony of Lovable

This is the subplot that should be taught in business schools.

Through 2025, Lovable was arguably the most imitated product in AI. The vibe-coding tool that turned natural language into working apps. Every competitor wanted to be “the Lovable of X.” It hit $400 million in ARR. $6.6 billion valuation. 8 million users. It was the category definer, the product everyone was copying.

And on March 19, 2026, the day after Manus Desktop launched and two days after Anthropic shipped Dispatch, Lovable announced it was expanding beyond app building into general-purpose task execution: data analysis, document generation, image and video creation, file processing. The company that everyone copied is now reshaping its own product in response to the agent wave that a lobster-themed hobby project kicked off four months ago.

Life comes at you fast in AI. But there’s a deeper structural lesson underneath the irony, and it’s the most important point in this entire piece. Lovable’s expansion isn’t copying for its own sake. It’s a response to a gravitational force that OpenClaw revealed: users don’t want a tool that does one thing well. They want an agent that does whatever they need. The expectation boundary shifted. When your customers have seen an agent that manages email, writes code, organizes files, analyzes data, and books flights, all from a single WhatsApp thread, “we build apps from natural language” sounds narrow, no matter how good you are at it.

This is the relentless simplification thesis. Agents compress the interface layer. Every vertical tool (the app builder, the analytics platform, the document generator, the project management dashboard) is under pressure to collapse into a single conversational agent that handles all of it. The products that survive this compression are the ones that either go deep enough on a specific capability to justify dedicated tooling (Lovable’s code generation is better than any agent’s), or go wide enough on general execution to become the default delegation layer (OpenClaw, Perplexity Computer).

The middle, vertical tools that are good but not best-in-class and not general enough to be the everything-agent, is where products go to die in 2026.


## How to evaluate the next one

Here’s the version you can actually use. When a new agent product launches (and there will be a dozen more before summer), evaluate it on three questions:

**First: Where does it run?** Local means your data stays yours, but you own the security. Cloud means someone else handles infrastructure, but you trust them with everything the agent sees. Hybrid means you get convenience with complexity. There is no free lunch. If someone tells you they have a cloud agent that’s as private as a local one, they’re selling you something.

**Second: Who picks the model?** Single-model products (Dispatch) give you consistency and simplicity at the cost of flexibility. Multi-model products (Perplexity Computer) give you optimized task routing at the cost of vendor dependency and opacity. Model-agnostic products (OpenClaw) give you maximum flexibility at the cost of configuration burden. Your answer depends entirely on whether you have the technical chops to evaluate and select models yourself.

**Third: What does the interface assume about you?** Messaging-native (OpenClaw) assumes you’re technical enough to configure a gateway and comfortable enough with the command line to troubleshoot. Phone-to-desktop (Dispatch) assumes you’re a professional who wants to delegate but not tinker. Web dashboard (Perplexity) assumes you want to describe an outcome and walk away. Desktop app (Manus) assumes you want something that looks like software you already know.

The interface isn’t cosmetic. It determines the floor of who can use the product. And in a market where the capability ceiling is rising for everyone simultaneously, where every agent is getting better at every task every month, the floor matters more than the ceiling. The product that wins isn’t the one that can do the most. It’s the one that the most people can actually use.


## The map

[![](https://substackcdn.com/image/fetch/$s_!4w39!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F314ea4e2-3d43-4721-8326-334b5c43d820_1522x1028.png)](https://substackcdn.com/image/fetch/$s_!4w39!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F314ea4e2-3d43-4721-8326-334b5c43d820_1522x1028.png)

Plot it out and the landscape becomes clear:

OpenClaw owns the top-right: maximum control, maximum risk, maximum flexibility, technical users only. It’s Linux in 1995. The people who get it, love it. The people who don’t get it will never install it. And the enterprise wrappers (NemoClaw, Perplexity’s “Personal Computer” on a dedicated Mac) are the Red Hat play — taking the raw capability and making it palatable for organizations.

Perplexity owns the bottom-left: minimum control, minimum risk, maximum delegation, knowledge workers and enterprise. It’s the SaaS bet. You pay a subscription, you get outcomes, you never see the infrastructure.

Manus owns the consumer center: enough capability to be useful, enough guardrails to be safe, distributed through the largest social platform on Earth. It’s the iPhone play; not the most powerful device, but the one in everyone’s pocket.

Dispatch owns the professional middle: local execution with managed safety, single-model simplicity, phone-based delegation. It’s the professional-tier bet, not trying to win developers (Claude Code already has them) or enterprise (that’s a different sales motion), but the growing class of knowledge workers who want agent capability without agent complexity.

And Lovable represents the first wave of category-adjacent products being pulled into the agent gravity well, vertical tools that have to decide whether to go deeper on their specialty or wider toward general execution.


## What this means for you

**If you’re a developer:** you probably already have an OpenClaw instance running. The real issue isn’t adoption. It’s whether you’ve hardened it — least privilege, network isolation, skill vetting, no exposed ports. The supply chain attack on ClawHub wasn’t the last one. Treat your agent instance like a production server, because that’s what it is.

**If you’re a knowledge worker who doesn’t code:** start with Dispatch at $20/month or Perplexity Computer at $200/month, depending on whether your work is file-centric (Dispatch) or project-centric (Computer). The gap between these tools and OpenClaw on core productivity tasks is smaller than the gap in security risk.

**If you’re evaluating for an enterprise team:** the differentiator isn’t which agent is smartest. They’re all smart enough. What matters is which deployment model fits your data governance posture. Local-only? Dispatch or NemoClaw. Cloud-managed? Perplexity Computer for Enterprise. Consumer-distributed across a workforce? Manus will likely be bundled into Meta’s enterprise offering within six months.

**If you’re building a product:** the lesson from Lovable is that every vertical tool is now under agent-compression pressure. Your moat isn’t features. It’s either depth of specialization that no general agent can match, or breadth of execution that makes you the default delegation layer. The middle ground is shrinking by the week.


## The deeper pattern

The reason this product strategy case study matters beyond this particular week, is that OpenClaw didn’t just launch a product. It established a new expectation baseline. The expectation that your AI agent runs locally, is always on, connects to everything, and works through the messaging app you already use.

Every subsequent agent product is now either meeting that expectation or explaining why their alternative is better. Perplexity explains that cloud is safer. Anthropic explains that managed is more reliable. Meta explains that consumer-friendly is more accessible. Nvidia — and this might be the most telling response of all — built an entire enterprise platform, NemoClaw, that wraps OpenClaw in security guardrails rather than trying to replace it. Jensen Huang compared the move to how Red Hat made Linux enterprise-ready. The subtext is explicit: OpenClaw has become infrastructure, not just a product, and the money is in making that infrastructure safe enough for organizations to adopt.

CIO Magazine captured the strategic shift cleanly: until recently, the assumption was that 2026’s agents would be chatbot front ends connecting to cloud platforms like Microsoft AutoGen, Google Vertex AI, or OpenAI’s Assistants API. OpenClaw showed that local, edge-based agentic processing is the alternative model, and now the entire industry is scrambling to decide which side of that line to stand on, or whether to straddle it.

That’s the strategic lesson. In a market moving this fast, the product that defines the expectation, not the product with the most features or the best benchmarks or the largest balance sheet, is the one everyone else has to respond to. OpenClaw is a hobby project running under an MIT license with serious security problems and a creator who left for a competitor. And it’s still the gravitational center of the entire agent ecosystem.

The reason is simple and structural: OpenClaw demonstrated the simplest possible version of what agents can be: local, always-on, conversational, and capable. That simplicity is what every other product is now trying to match, improve on, or explain away. And in technology, the product that establishes the simplest viable form of a new category usually sets the terms of competition for everyone who follows.

Watch the next agent product launch. Evaluate it on the three axes. Check whether it moves the expectation or merely responds to it. This lens holds.

[![](https://substackcdn.com/image/fetch/$s_!Ug77!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa13c77cd-200b-49f3-9e47-e2ecd113a341_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Ug77!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa13c77cd-200b-49f3-9e47-e2ecd113a341_1024x1024.png)
