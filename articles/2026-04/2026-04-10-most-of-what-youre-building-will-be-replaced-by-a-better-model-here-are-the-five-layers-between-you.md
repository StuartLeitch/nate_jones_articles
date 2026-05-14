---
title: "Most of What You're Building Will Be Replaced by a Better Model. Here Are the Five Layers Between You and Irrelevance."
author: "Nate Jones"
published: 2026-04-10
url: https://natesnewsletter.substack.com/p/most-of-what-youre-building-will
audience: everyone
scraped_at: 2026-05-14 14:33:50
---

If your name isn’t Anthropic or OpenAI or Google, you have a problem. You need to find a space to build in where a better model won’t just erase everything you’ve made. That problem isn’t hypothetical. It’s happening right now to a dozen companies worth billions of dollars.

The AI app builder category looked like one of the safest bets in tech as recently as last year. Lovable just raised $330M at a $6.6 billion valuation. They crossed $400M in annual recurring revenue in February, up from $100M just eight months earlier. 100,000 new projects a day. And the space is still collapsing in on itself, because most of these companies — Lovable, Bolt, Replit, Shipper, and a long tail of smaller players — are thin wrappers around the same foundation models, and their moat is about a week deep.

What’s interesting isn’t who dies. It’s what the survivors tell us about where durable value actually lives on the web. There are exactly five things AI cannot replace, and they’re going to organize the entire future of the internet.

**Here’s what’s inside:**

- **The collapse of the build layer.** Why a dozen companies racing to be your AI app builder are mostly trapped.
- **The escape hatch.** What separates Replit, Vercel, and Notion from the wrapper companies that will die.
- **The five durable verticals.** Trust, context, distribution, taste, and liability: the things AI structurally cannot provide on its own.
- **The real map.** How the future web organizes around these five layers, and what it means if you’re building something.
- **Your positioning audit and agent-readiness stress test.** Two prompts that tell you which vertical you should be building in and whether an AI agent can actually use what you’ve built.

Let me show you how the pieces fit together.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260331_oom_promptkit_1)

The framework is easy to agree with in the abstract. Holding your specific product against it is where it gets uncomfortable. These two prompts do that work. The positioning audit scores your company across all five verticals, identifies which one you should be concentrating on, and tells you plainly whether a better model makes you redundant or more valuable. The agent-readiness stress test goes somewhere most strategy pieces won’t: it simulates an AI agent trying to discover, evaluate, transact with, and verify your service end to end, then hands you a prioritized list of what’s broken. If the agentic economy is real, and it is, most businesses will fail the second prompt completely. Better to find out now.


## The collapse of the build layer

The scale of the land grab is staggering. Vercel’s v0 has 4 million users. Replit has more than 40 million developers on their platform. Base44 and a second wave of smaller players are launching every month with essentially the same pitch: tell AI what you want, and it builds it for you.

And they’re all screaming down the same lane. Most of them are thin wrappers around the same foundation models: Claude, GPT-4, Gemini. They differentiate on UI, on pricing, on marketing copy. One has an “AI Advisor.” Another has a “Visual Editor.” A third has a slightly different template library. The core technology is identical: send a prompt to someone else’s model, render the output, host the result.

This is the middleware trap in real time. When your product is a UI layer on top of someone else’s intelligence, your moat is exactly as deep as the time it takes a competitor to build a similar UI. Which, in the age of AI-assisted development, is about a week.

But here’s what’s interesting: a few companies in this space are *not* trapped. And the reason they’re not trapped tells you everything about where value creation is heading.


## The escape hatch isn’t what you think

The conventional wisdom is that to escape the middleware trap, you need to train your own model. Build your own intelligence layer. Get off the API dependency.

Replit is actually doing this. They trained their own code completion models (using MosaicML, now part of Databricks), released open-source versions on Hugging Face, and use them for inline suggestions where cost efficiency matters. Lovable, at $400M+ ARR, certainly has the cash to try. Vercel trained a custom “AutoFix” model with Fireworks AI that catches code generation errors during streaming, and they just updated their terms of service to start using customer code for model training.

But training your own model isn’t actually what separates the survivors from the casualties. The companies that are going to make it through the middleware squeeze share a different trait: **they own something structural that the model providers can’t replicate.**

Replit doesn’t escape because they out-train Anthropic. They escape because Claude can’t *execute* your code. Replit owns the runtime, the actual compute environment where your application lives and breathes. That’s a fundamentally different value proposition than “we call an API and show you the output.”

Vercel doesn’t escape because v0 uses a slightly better prompt. They escape because nobody else has the deployment infrastructure that already hosts production applications for OpenAI, Anthropic, Nike, and PayPal. Next.js gets more than 25 million downloads per week. They’re not an AI wrapper with hosting. They’re an infrastructure company with an AI front door.

Notion doesn’t even pretend to be training its own model. They offer a model *picker* (GPT-5, Claude, Gemini, take your choice). Their bet is completely different. They’re saying: we don’t care which model wins. We care that 100 million users have built one of the largest structured knowledge graphs of organizational information on the planet, and every model needs to come through us to access it.

The pattern: **AI commoditizes production. The companies that survive are the ones building on layers that production can’t replace.**

Which raises the bigger question: if building things becomes essentially free, what’s actually worth building a company around?


## The five durable verticals of value

I think the web of the future organizes around five things that AI structurally cannot provide on its own. These aren’t product categories. They’re layers of value that persist regardless of how good the models get. And the agentic economy that’s emerging will make each of them more important, not less.


### Trust

The web is about to be flooded. We’re heading toward a world where millions of AI-generated apps, services, storefronts, and content streams are created every day. Most of them will be indistinguishable from each other. Many will be garbage. Some will be actively malicious.

When anyone can generate a professional-looking checkout page in thirty seconds, “looks legitimate” stops being a signal. The companies that become the *verification layer*, the ones who tell you this app won’t steal your credit card, this service actually does what it claims, this content was produced by someone accountable, capture enormous value.

This is why Stripe’s position gets stronger, not weaker, in an AI-saturated web. “Powered by Stripe” isn’t a technical feature. It’s a trust signal. Same for Shopify, same for Apple’s App Store review process, same for Vercel’s deployment infrastructure with SSL and CI/CD baked in.

In the agentic economy, trust becomes even more critical. When your AI agent is autonomously transacting on your behalf (booking flights, signing up for services, making purchases), the trust layer is the thing standing between you and a universe of AI-generated scam apps that look pixel-perfect. The agents themselves will need trust signals to operate. Which payments are safe? Which services are verified? Which APIs won’t exfiltrate your data?

The trust providers become the routing layer of the agentic web. If an agent can’t verify a service, it can’t use it. If it *can* verify it, through Stripe’s payment infrastructure, through a verified deployment platform, through a reputation system, then that service gets traffic. Trust becomes the new SEO.

**Players building here:** Stripe (payments trust), Shopify (commerce trust), Vercel (deployment trust), Apple/Google (distribution gatekeeping), and potentially whoever builds the agent-native verification protocol that doesn’t exist yet.


### Context

The most valuable thing on the internet isn’t compute or content. It’s *your specific situation*. Your company’s data. Your customer relationships. Your project history. Your medical records. Your org chart. Your meeting notes from last Tuesday.

AI is general. Value is specific.

The companies that become the authoritative store of context, and the permissioning layer that governs who and what gets access to it, own the chokepoint. Every agent, every model, every workflow has to come through you to be useful.

Notion gets this at a deep level. They’ve built Custom Agents (21,000+ created by early testers) that run autonomously across your workspace, triaging Slack messages, drafting email responses, managing project workflows. But the agents are only as good as the context they have access to, and that context lives in Notion. The model is replaceable. The accumulated knowledge graph of your organization is not.

This is the same structural play that makes Salesforce durable (your CRM data), Epic durable (your health records), and Palantir durable (your operational data). When AI agents become the primary way work gets done, the context stores become the power brokers. An agent without context is just a chatbot. An agent with deep context about your business, your customers, and your history is a genuinely useful employee.

The agentic economy runs on context. And context has a permission layer. The companies that control that permission layer, who gets to know what about you, become the identity infrastructure of the AI web.

Google is worth watching closely in the context space. They recently launched what amounts to a context layer for Maps, and it highlights how many surfaces Google actually controls. They’re a model provider, a TPU manufacturer, an ecosystem player through Android and Chrome, and increasingly a context player through products that already hold enormous amounts of user-specific information. They have more ways to win this board than any single competitor, and the context vertical may be the least obvious one.

**Players building here:** Notion (organizational knowledge), Salesforce (customer relationships), Epic (health data), Palantir (operational intelligence), Snowflake/Databricks (enterprise data), and potentially the browser/OS layer (Apple, Google) if they nail local AI with personal context.


### Distribution

You can generate an app in five minutes. Who sees it?

There’s a persistent fantasy in tech that resembles the premise of *Field of Dreams*: build it and they will come. It has never once been true. Second-time founders know this instinctively. The bottleneck was never building the thing. It was always getting it in front of the right people at the right moment and learning whether they’d pay for it. When supply was constrained, when building an app took months and thousands of dollars, distribution and production were roughly balanced in importance. A great product could find an audience because there weren’t that many products competing.

We’re about to break that balance completely. When anyone can make anything, the supply side goes infinite. And when supply is infinite, **curation becomes the scarcest resource.**

Google, Apple’s App Store, TikTok, YouTube: these are distribution monopolies, and AI makes them *more* powerful, not less. The gatekeepers get stronger when the flood gets bigger.

For the agentic economy, this means something specific: agent *discovery* becomes a massive problem. If every business has AI agents, and those agents need to interact with other agents and services, who decides which agents get routed to? There’s a new distribution layer emerging that’s distinct from human-facing distribution. It’s the question of how agents find, evaluate, and select services on behalf of their users.

And this is one of the most underdeveloped problems in the entire AI economy. It’s not enough to expose an MCP server and call yourself agent-ready. An agent evaluating your service needs to understand what you offer quickly, execute a transaction without friction, and receive confirmation in a format it can act on immediately. The entire mechanism for commerce has to be rethought with agents as the primary customer, not just the human behind them. Almost no businesses are doing that work yet.

This is actually bullish for people who’ve already built audiences. If you own an audience, as a creator, a media company, a community leader, your distribution is worth *more* when production costs collapse. You’re the curator in a world drowning in AI-generated options. Your recommendation, your endorsement, your editorial judgment about what’s good is the signal that cuts through infinite noise.

The entrepreneur of the future doesn’t necessarily build the product. They might just be the one who finds it, validates it, and tells the right people about it.

**Players building here:** Google (search/discovery), Apple/Google (app stores), TikTok/YouTube/Substack (audience-owned distribution), Amazon (commerce distribution), and whoever builds the “agent app store,” the marketplace where AI agents discover and transact with services.


### Taste

When production is free, *what to produce* becomes the entire game.

The product decisions. The design sensibility. The editorial judgment about what’s worth building and what isn’t. The ability to look at what the AI generated and know what’s right, what’s wrong, and what’s missing.

This is a human skill that AI can assist but cannot replace, because it requires a point of view. A conviction about what should exist in the world that isn’t derivable from training data.

The best analogy is music production after GarageBand went mainstream. The tools got cheap. Everyone could make a track. The flood of music was enormous. Now Suno lets you generate an entire produced track from a text prompt in seconds, and the dynamic has only intensified. The producers and artists who thrive aren’t the ones with the most expensive studio. They’re the ones with taste, an ear for what connects, a vision for something the audience didn’t know it wanted yet.

The same thing is about to happen to software, content, and services. The vibe coder who ships an app in thirty minutes hasn’t done the hard part. The hard part is knowing which app to build, for whom, and why, and having the judgment to iterate on it until it’s actually good, not just functional.

In the agentic economy, taste manifests as *orchestration quality*. The winning agent systems won’t be the ones with the best underlying model. They’ll be the ones where a human with deep domain expertise has carefully tuned the prompts, designed the workflows, chosen the right tools, and made a thousand small editorial decisions about how the agent should behave. The model provides capability. Taste provides direction.

I want to be careful not to overstate the permanence of this. Karpathy’s auto-research work and tools like it point toward a future where agents begin to self-evolve, where optimization loops run without a human tuning every prompt. That future may arrive faster than most people expect. But even when the human sits further above the loop, the responsibility doesn’t evaporate. Someone still decides what good looks like. Someone still sets the goal, evaluates whether the agent’s behavior serves the user, and redirects when it doesn’t. The tools for expressing taste will change. The need for it won’t.

This is why I think the “solo founder with AI” story is actually a *taste* story, not a technology story. The founders winning with AI tools are the ones who already had strong product intuition. The AI just removed the bottleneck that was keeping them from expressing it.

**Who wins here:** Individual operators and small teams with strong domain expertise and product vision. This isn’t a platform play. It’s a people play. The designers, product thinkers, and domain experts who can direct AI toward outcomes that matter.


### Liability

Someone has to be on the hook. This is the most underrated vertical of value in the entire AI economy.

When an AI-generated financial plan loses your money, when an AI-built medical app gives bad advice, when an AI-generated contract has a flaw, someone needs to be legally and financially accountable. And “the AI did it” is not an answer that any regulator, court, or customer is going to accept.

Regulated industries (healthcare, finance, legal, insurance, education) won’t automate away the human in the loop, because the human in the loop is the one holding the liability. The doctor who signs off on the AI-assisted diagnosis. The financial advisor who reviews the AI-generated plan. The lawyer who reads the AI-drafted contract. The auditor who verifies the AI-produced analysis.

These professionals are selling something AI literally cannot provide: **accountability**. The willingness to say “I stake my license, my reputation, and my capital on this being correct.”

And here’s the counterintuitive dynamic: the *better* AI gets at generating plausible output, the *more* valuable human accountability becomes. Because the cost of generating confident-sounding but subtly wrong output just dropped to zero. Someone has to catch the errors. Someone has to stand behind the result. That someone commands a premium.

In the agentic economy, the liability layer becomes the governance layer. When AI agents are autonomously executing complex workflows (filing documents, moving money, making commitments), someone needs to define the boundaries, audit the actions, and take responsibility when things go wrong. This isn’t a bottleneck to be automated away. It’s a feature of a functioning system.

The companies and professionals who position themselves as the accountability layer for AI-powered workflows will command pricing power that only grows as automation expands.

**Players building here:** Professional services firms (Deloitte, McKinsey, who are repositioning as AI assurance providers), regulated SaaS platforms (Veeva, nCino, Elation), and every licensed professional who adds “AI-verified” to their practice.


## The real map of the future web

Here’s what the web looks like when you put these five layers together:

The **model providers** (Anthropic, OpenAI, Google) own the capability layer. They’re enormously valuable but increasingly commoditized relative to each other.

The **wrapper companies** (Lovable, Bolt, Shipper, and dozens of others) own nothing durable. Some will get acquired. Most will die. A few, the ones that manage to accumulate enough users and data to become platforms, might transition. Lovable, at $6.6B and $400M+ ARR, has the best shot. But the shot is at becoming a *platform*, not at staying a wrapper.

The **infrastructure players** (Vercel, Replit, Stripe, Shopify) own the trust and execution layers. AI makes them more valuable, because more things being built means more things being deployed, hosted, paid for, and verified. They’re the picks-and-shovels of the AI gold rush, and their position is durable.

The **context owners** (Notion, Salesforce, Snowflake, Databricks, Epic) own the data gravity. AI agents need context to be useful, and context is locked inside these platforms. They become the permissioning layer of the agentic economy.

The **distribution gatekeepers** (Google, Apple, Amazon, TikTok, YouTube) own attention. When supply is infinite, the curator wins. Their power increases as production costs decrease.

And the **humans in the loop**, the operators, founders, professionals, and creators who provide taste, judgment, and accountability, are the connective tissue that makes all of it work. AI doesn’t replace them. It makes them more powerful.


## What this means if you’re building something

If you’re an entrepreneur looking at this landscape, the decision framework is simple:

**Ask yourself: what do I own that still matters when the model gets 10x better for free?**

If the answer is nothing, if a better model just makes your product redundant rather than more useful, you’re in the middleware trap. Get out, get acquired, or pivot to owning something structural.

If a better model makes your product *more* valuable, because you’re the trust layer it routes through, the context store it queries, the distribution channel it needs, the taste that directs it, or the accountability that governs it, you’re on the right side of the transition.

The vibe coder shipping an MVP on Lovable in a day? That’s real, that’s great, and it’s empowering. But the MVP isn’t the business. The business is the trust you build with customers, the context you accumulate, the distribution you earn, the taste you exercise in deciding what to build and how, and your willingness to stand behind the result.

One thing troubles me about the current moment, though. The energy and excitement that tools like Lovable and Replit have generated around creation is extraordinary, but almost none of it is flowing into distribution. I see hundreds of thousands of apps blooming every week, and most will never be discovered because nobody stopped to ask whether a real person actually wants this product. That’s not an AI problem. It’s the oldest problem in business, and no model update fixes it. If you build an MVP in a day, your real job starts the next morning: putting it in front of customers, learning what they actually need, and deciding whether you’re building something worth standing behind.

None of that changed. It just matters more now.

[![](https://substackcdn.com/image/fetch/$s_!EfQF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7f83a3f6-9c8f-4996-8b0d-2c4da4727f14_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!EfQF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7f83a3f6-9c8f-4996-8b0d-2c4da4727f14_1024x1024.png)
