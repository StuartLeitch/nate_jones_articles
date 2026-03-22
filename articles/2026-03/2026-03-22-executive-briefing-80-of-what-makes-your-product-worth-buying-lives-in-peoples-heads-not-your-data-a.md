---
title: "Executive Briefing: 80% of what makes your product worth buying lives in people's heads, not your data. Agents can't read it. Here's what to do about it + 4 prompts to start this week"
author: "Nate Jones"
published: 2026-03-22
url: https://natesnewsletter.substack.com/p/executive-briefing-your-systems-are
subtitle: "Watch now | What OpenClaw actually revealed, and why the strategic lesson has nothing to do with OpenClaw."
audience: everyone
scraped_at: 2026-03-22 15:00:20
---

The fences we spent a decade building to keep bots out are now keeping our most valuable customers from getting in.

OpenClaw went from a weekend project to over 250,000 GitHub stars in weeks. Jensen Huang called it the operating system for personal AI at GTC. NVIDIA built an enterprise platform on top of it. Everyone wants their OpenClaw moment.

Almost nobody is talking about the structural precondition that determines whether any of this works: whether your systems are agent readable and agent writable. Not your chatbot. Not your AI features. The actual transactional infrastructure — the systems that let someone discover, evaluate, and buy what you sell. And making that infrastructure agent-ready is significantly harder than the current conversation acknowledges.

**Here’s what’s inside:**

- **The Napster moment hiding inside OpenClaw.** The demand signal is real and irreversible. Apple, Google, and Meta are responding the way the music industry responded to file sharing, and will lose for the same reasons.
- **Why agent readability is a data quality problem, not an API problem.** Making your systems agent-readable forces a cleanness of data architecture down the entire stack. That forcing function is the real story.
- **Four misconceptions leading executives to prepare for the wrong thing.** Each sounds reasonable. Each is strategically dangerous.
- **The vagueness problem nobody is working on.** The highest-leverage insight in this argument, and it applies to B2B SaaS as much as retail.
- **Five diagnostic exercises that will tell you exactly how exposed you are.** They are designed to be uncomfortable. Run them this week.
- **Four prompts to diagnose your exposure and build the plan.** An agent readiness diagnostic that maps where your transactional flows break, a tribal knowledge audit that quantifies the 80% of product meaning living outside your databases, a competitive simulation you can run in thirty minutes, and a transformation roadmap your CTO and CFO can align on.

The companies that move on this first will build a structural advantage that compounds every quarter. Let me show you why.


## **LINK: [Grab the prompts](https://promptkit.natebjones.com/20260320_p34_promptkit_1)**

The five exercises later in this briefing will tell you where you’re exposed. These four prompts turn that exposure into working sessions you can run this week. The Agent Readiness Diagnostic walks your highest-revenue transactional flow and maps exactly where it breaks for programmatic access — discovery, evaluation, or transaction — then produces a board-ready assessment with severity ratings your leadership team can act on. The Tribal Knowledge Audit tackles the vagueness problem directly: it interviews you about your top products, maps what percentage of decision-relevant knowledge actually lives in structured data versus people’s heads, and extracts the decision trees your best salespeople use so you can see what needs encoding first. The Competitive Agent Simulation guides you through querying Claude, ChatGPT, and Gemini with realistic customer prompts to see whether your company even shows up in the agent’s consideration set — and what your competitors’ data looks like compared to yours. And the Transformation Roadmap takes everything you’ve found and produces a phased, resourced plan sequenced correctly: data foundation first, protocol layer second, because wrapping an MCP server around inconsistent data is buying trucks before paving roads. Start with the Competitive Simulation. It takes thirty minutes and it will reframe every conversation you have about this afterward.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

I’ve built something for Executive Circle subscribers. It’s a read-only MCP server that gives your AI — Claude, ChatGPT, whatever you use — direct access to my entire published content library. Every post across both newsletters (400+ and counting), every prompt kit I’ve ever shipped. You connect once, and then the archive just *shows up* inside your normal AI conversations. No bookmarks, no digging through email, no “I know Nate wrote about this somewhere” moments. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Think of it as a research assistant that’s already read every word we’ve put out — and it’s sitting inside the tool you’re already using. “Search for posts about AI agents and summarize the key themes.” “Find prompt kits for content creation workflows.” “What have we published about prompt engineering in the last three months?” You can even paste in something you’re working on and ask it to surface the most relevant posts. It’s six read-only tools — search posts, read full posts, browse recent content, search prompt kits, read full kits, browse all kits. No write access, no drafts, no behind-the-scenes material. Just the published, finished work, available the moment you need it.

Setup takes about ninety seconds.

- Register once at [promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)
- Enter your access code (**executive\_circle**) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

This is, as far as I know, one of the first newsletters offering native AI integration as a subscriber benefit. Your subscription doesn’t just give you content anymore — it gives you that content embedded in your AI workflow, available the moment a question comes up. The way I think about it: your subscription now works inside your AI. Have fun!


## The Napster moment

The mainstream read on OpenClaw is that it’s the consumer AI agent breakthrough: your personal Jarvis, running locally, doing things instead of just talking about them. That read is pointing at the wrong thing.

Daniel Jeffries nailed the better frame. OpenClaw is not a DeepSeek moment for agents. It is a Napster moment. When Napster launched, the music industry heard a demand signal it didn’t want to hear: people wanted digital access to everything, and if the industry wouldn’t provide it, they would take it. Napster itself got hammered with lawsuits. But the model it proved — ubiquitous, frictionless access to a unified catalog — survived and eventually became iTunes, then Spotify. The demand was never the question. Whether incumbents would restructure to meet it was.

The irony is that Apple profited enormously from that restructuring. iTunes and the iPod ecosystem were built on the same demand signal Napster exposed. Now Apple is facing its own version of that moment and responding like the old guard. Apple has blocked App Store updates for vibe coding apps, including Replit, citing longstanding rules against apps that execute code altering their own functionality (Guideline 2.5.2). Google banned hundreds of OpenClaw users from its Antigravity platform after their agent traffic overwhelmed the backend, locking some developers out of their entire Google accounts without warning. Meta is banning OpenClaw instances on WhatsApp.

These companies have every incentive to keep their walls up. But the demand signal is overwhelming. What OpenClaw demonstrated is that people want a unified agent that can act on their behalf across every service they use. Peter Steinberger built it by hacking around every wall — command-line-first, reverse-engineered libraries, proxied human interface layers. Vendors don’t want this. They wouldn’t be under pressure to deliver it if someone hadn’t insisted on building it anyway.

The strategic lesson is not “build a cool personal agent.” The strategic lesson is that your systems will be agent readable and agent writable, or they will be routed around. That shift is deeper, harder, and more urgent than the OpenClaw conversation suggests.


## Why the walls no longer hold

For fifteen years, the industry engineered its technology stacks around a single assumption: automated access is hostile. Bots meant spam. Scrapers meant theft. WhatsApp built explicit anti-bot policies. Google Ads requires a special manager account, an enterprise key, and bureaucratic approval before anything programmatic can touch it. Most SaaS platforms gate their APIs behind enterprise contracts and multi-week onboarding. The walls made sense in 2015.

They do not make sense when the machine trying to get in is a paying customer’s AI agent, acting on their behalf, with their credit card, trying to give you money.

Andrej Karpathy framed the shift in March 2025: 99.9% of attention is about to be LLM attention, not human attention. His example was documentation — library docs rendering to pretty HTML pages for humans when they should be a single markdown file optimized for a context window. Twelve months later, the scope has expanded far beyond docs. It’s agent attention specifically, and agents need to do something with that attention, not just read.

Cloudflare saw this early. In February 2026, they shipped Markdown for Agents, automatic markdown conversion when an AI agent requests a page via standard HTTP content negotiation. A page that consumed 16,180 tokens as HTML required only 3,150 as markdown. An 80% reduction. Cloudflare powers roughly 20% of the web. That they built this feature tells you where traffic is heading. That most sites haven’t enabled it tells you how wide the gap remains.

But markdown conversion is the surface layer. The hard part begins when agents don’t just want to read your content. They want to transact.


## Commerce is the canary

McKinsey projects that by 2030, the U.S. B2C retail market alone could see up to a trillion dollars in agent-orchestrated revenue, with global projections reaching $3 to $5 trillion. Google launched the Universal Commerce Protocol at NRF to let agents discover products, build carts, and complete checkout. Shopify’s president called agentic shopping the transformation of a lifetime. Over a million Shopify merchants are coming online for agent-mediated transactions.

What this means concretely: a customer types “find me running shoes under $120, size 10, that ship before Thursday, from a brand with flexible returns.” That prompt activates a chain of API calls against product catalogs, pricing services, availability feeds, and shipping estimators. The agent evaluates options programmatically, not visually. If your product data is unstructured, delayed, or inconsistent — if your shipping terms are buried in a FAQ page that requires JavaScript to render — the agent cannot include you in the candidate set. Your storefront exists. It is invisible to the layer that increasingly mediates demand.

nShift’s research puts it bluntly: if delivery windows, shipping costs, and return terms are unclear, the agent skips the offer without a human ever seeing it. They call it agent legibility. You might have the best product in the world. If it’s not agent-legible, it doesn’t exist in the transaction.

The principle extends well beyond retail. Customer support, procurement, insurance quoting, travel booking, financial services — every transactional surface in your business was designed for humans with browsers. And if you’re reading this as a B2B SaaS company thinking it doesn’t apply to you, I’d push back. The consideration funnel is moving into agent world. Buyers are going to ask, increasingly explicitly: can my agent read and interact with your application? That question will become a purchasing criterion.


## The insight nobody recognizes

Everyone who talks about making systems agent-friendly treats it as an interface problem. Add some APIs, publish an MCP server, convert your docs to markdown. Necessary, but insufficient.

The deeper insight: re-architecting your surfaces to be agent readable and writable forces a cleanness of data architecture down the entire stack, or it simply won’t work.

I learned this at Prime Video, where we spent years figuring out how to use data to personalize content experiences. What we discovered is that if your underlying data isn’t clean all the way down, the end experience is terrible. You cannot provide useful customized experiences without it. That was pre-agent — just learning how much data coherence matters. Now consider what happens when agents consume that data at scale, with zero tolerance for ambiguity.

A human looking at your website can infer that “ships in 2-3 business days” probably means weekdays, probably excludes holidays, probably starts from order confirmation. An agent takes whatever you give it literally. If your product catalog says one thing, your fulfillment system says another, and your FAQ says a third, the agent will either surface the contradiction or skip you for a competitor whose data is internally consistent.

Think about Amazon’s shipping promise. That delivery date you see on a product page is a specific promise for you, for that product, based on your geography, based on hundreds of internal factors that all have to agree. Without that internal coherence, you can’t make the promise. Now think about what it would take to make that promise agent-readable — so that a customer could say “show me only the running shoes that arrive today, in my size, from Nike or New Balance, with good arch support” and get an accurate answer. Amazon has the internal data for this. They’ve been reluctant to expose it because they’re afraid of losing the customer relationship. The customer stops visiting Amazon and starts just talking to Claude. That fear is real, and it’s shared by every major merchant. But the demand doesn’t care about their fear.

This is why the work of becoming agent readable is not primarily an API project. It is a data quality project, a systems integration project. It requires reconciling systems that have drifted apart for years because the human interface layer was papering over the inconsistencies. I would go further: a significant portion of marketing exists to paper over exactly those inconsistencies. When a marketer is selling a product with genuine product-market fit, everything works. When they’re selling a product without it, they’re running uphill. The idea that you need something extra to cover deficiencies in the product or vagueness in the data — that function erodes when the customer’s agent reads your data directly and makes its own judgment.

WunderGraph crystallized the technical dimension well. MCP, the Model Context Protocol now governed by the Linux Foundation, solves the transport layer. It standardizes how agents invoke tools and access data. It does not solve the data layer: which fields are exposed, which relationships are modeled, which constraints are enforced. A protocol cannot compensate for poorly modeled data. Investing in the coordination plane before structuring the data plane is like buying a fleet of trucks before paving the roads.

If there is one line in this briefing worth remembering: making your systems agent-readable will be the most effective forcing function for data quality your organization has ever experienced. Not because you chose to clean your data. Because you had to.


## Two examples that bracket the problem

Stripe is probably the company most people would point to as getting this right. They shipped a well-designed MCP server; an agent can look up customers, process refunds, manage subscriptions. If your mental model of agent readability is “ship an MCP server,” Stripe looks like the finish line.

It isn’t. Stripe also has Sigma, their analytics layer — SQL access to your full transactional dataset. Revenue trends, churn analysis, cross-product reporting. That’s where strategic questions live. Sigma is not exposed through MCP, and it can’t be, at least not trivially, because the result sets are too large for a context window. What you need is an intermediary: a database layer where data lands in a table structure and can be queried by an agent in manageable slices with proper authentication. At Stripe’s scale and with the sensitivity of their data, that requires thinking carefully about which views go in which secure stores, how authentication scopes to the agent’s context, and how to allow the agent to pull slices without exposing the whole dataset. Even for one of the best engineering organizations in the world, shipping one MCP server is step one of a much deeper build.

SAP sits on the other end of the spectrum. Their ERP systems run the operational backbone of a huge share of the Fortune 500, relying on proprietary interfaces — BAPIs, Remote Function Calls — that predate modern API standards by decades. Data models are deeply customized per installation and often poorly documented. SAP announced an MCP server for Commerce Cloud, but the gap between one slice of the portfolio having AI features and SAP installations being agent-readable by default is vast. For most SAP deployments in the wild, this is a multi-quarter architectural reconciliation.

I’ll be watching closely over the next six to eight months to see how many companies look down their stack and start having honest conversations with their vendors about whether their data is in a format agents can read and write against. That collective pressure may become one of the most important dynamics of 2026.


## Four misconceptions

**“We’ll optimize for agent discovery the way we optimized for search.”** A search engine returns a ranked list and the human chooses, influenced by positioning, brand recognition, ad creative. An agent doesn’t browse a list. It evaluates structured data against explicit constraints and returns a result. There is no “above the fold” in an agent’s reasoning. No brand halo effect. The companies that win will not have the biggest ad budgets. They will have the cleanest schemas and the lowest-friction data endpoints.

**“Structured schemas only work for simple products. Our business is too complex.”** I hear this from luxury brands, professional services firms, anyone who believes their product requires nuance to sell. It reveals a misunderstanding. The more complex your business, the more you benefit from agent readability, because that complexity is exactly what prevents customers from optimizing their own purchases today. They settle for good enough because the evaluation is too hard. Give an agent structured access and it can find the genuinely optimal answer.

I’m a coffee person. Authenticity in coffee means knowing which farm, how it was sourced, how it was processed, how it was roasted. Those are all schemas an agent can read from. A honey processed Ethiopian Yirgacheffe has dozens of meaningful attributes. You can tell me authenticity is a vague human quality, but at the bottom of what authenticity actually means, it’s a series of data reads. Anything you can represent on a screen is something an agent should be able to read and write against.

**“Consumers won’t trust agents to transact.”** Look at what’s actually happening, not what people say in surveys. Agent commerce doesn’t begin with “let the AI buy whatever it wants.” It starts with long-horizon intent delegation. I’m considering multiple sound systems. Here’s my room configuration, my budget, what my old system did well, the kind of lossless audio I want. I’m not delegating the purchase. I’m asking the agent to help me think through what the right call is.

Trust is a spectrum that starts narrow and widens as the agent proves reliable. This is how every trust system works. Nobody handed Uber their credit card on blind faith the first time. You took a short ride. It worked. You expanded from there. The protocols being built — Google’s UCP with consent frameworks, the Agent Payments Protocol with scoped spending limits — are designed for exactly this kind of graduated trust.

**“We need to wait and see.”** The work of cleaning your data architecture takes months, sometimes quarters. Even companies that are leaning in don’t have it figured out yet. If you are waiting for the ecosystem to stabilize before starting, you will find that early movers have already done the hard architectural work by the time you begin. 250,000 GitHub stars happened in a few weeks. The window for getting ahead of this is not as long as it feels.


## The vagueness problem

I’ve been thinking about an aspect of agent readability that may be the single highest-leverage opportunity, and that almost nobody is working on yet.

It’s straightforward to make basic product attributes agent-readable. This is a basketball. It weighs this much. This is the color. This is the logo. Done. What is hard is making higher-order attributes readable. Imagine a customer watching March Madness who says to their agent: “I want the basketball that’s on the court right now.” The agent needs to take that vague intent and find a real product. If your data can’t express “this is the same ball used in the 2026 March Madness tournament,” you miss the sale, because that is what the human will ask for.

Now translate that to B2B SaaS. A buyer says: “I want a product that’s proven to scale to 10,000 customers.” That has to be a data attribute the agent can read and trust, backed by credible sources — not a single case study on a blog. The agents we’re building are going to be sophisticated enough to take a vague human question and probe for the reality underneath.

The challenge is that so much of this is tribal knowledge. For most companies, something like 20% of the meaning around a product lives in structured data. The other 80% — the fact that this coffee was processed by a small farmer supporting a local school in Ethiopia, the reasons one model is better for marathon training than another, the compatibility nuances your best salesperson navigates intuitively — all of that lives in marketing copy, packaging, or someone’s head. When a customer tells their agent “I want to make sure my coffee supports important work like building schools,” the agent will look. Your product is either there, in a format the agent can evaluate, or it isn’t.

Think about what happens when a customer arrives with a vague request. “What’s the best option for me?” “I need help with my order.” Your best service rep asks clarifying questions, pulls up account history, follows a decision tree that converts ambiguity into a resolved transaction. That decision tree is the exact workflow an agent needs to replicate. And in most companies, that resolution logic lives nowhere except the institutional memory of veteran employees. If the resolution data is structured — a recommendation engine, a compatibility matrix, a diagnostic questionnaire — the agent can run the same process automatically. If it’s not, the transaction goes to whoever structured it first.


## The primitives are arriving

The infrastructure for an agent-readable world is assembling quickly.

MCP has gone from Anthropic’s internal tool to the industry standard in roughly eighteen months. SDK downloads have grown from 100,000 at launch to over 97 million per month across Python and TypeScript. It’s now governed by the Agentic AI Foundation under the Linux Foundation, co-founded by Anthropic, Block, and OpenAI, with support from Google, Microsoft, AWS, and Cloudflare. Gartner projects that a significant majority of API gateway vendors will have MCP features by end of 2026.

Agent authentication remains the missing layer. Today’s security model was designed for humans and workloads. Agents are neither — they reason across many possible paths, operate with evolving context, and run on non-deterministic models. Gravitee’s State of AI Agent Security 2026 report, surveying over 900 executives and practitioners, found that 88% of organizations have experienced confirmed or suspected AI agent security incidents, while only 14.4% reported agents going live with full security and IT approval. Adoption has massively outpaced governance.

Commerce protocols — Google’s UCP, OpenAI’s Agentic Commerce Protocol, the Agent Payments Protocol — are defining how agents discover, negotiate, and transact. Content negotiation standards like Cloudflare’s markdown headers are making web content agent-consumable. These are being built now.

I want to be careful not to overstate how mature this ecosystem is. But I also want to be clear about the timing risk: the companies that started making their systems agent-readable before the standards were finalized are the ones that will be ready when the standards lock. The hard part was never the protocol integration. The hard part was cleaning the data underneath. That work doesn’t compress.


## Software is becoming primitives

There is a broader shift worth naming. Software is increasingly going to be a set of primitives callable from any surface, not applications with interfaces.

Paper.design launched with native MCP integration — 24 tools, full bidirectional access. An agent running in Claude Code can inspect a design file, modify it, export production-ready React components, and push them to a codebase, all through a standardized protocol. The design tool isn’t an application you open in a browser. It’s a set of capabilities any agent can invoke from any context. Figma launched their own MCP server, though read-only — which tells you something about how far even forward-looking companies have to go. Read-only is observation. Read-write is participation.

Every team building a new feature should be asking three questions. Can an agent invoke this? Can an agent read the output? Can an agent write the input? If any answer is no, the feature is built for the past.


## Five exercises that will tell you where you stand

**The Agent Walkthrough.** Pick your single highest-revenue transactional flow. Assign an engineer who understands both your systems and what agents can do. Give them a week to complete the entire transaction programmatically — no browser, no JavaScript rendering, no UI wizard. Pure API calls against structured data. They will hit a wall. If they stall at discovery, your catalog is invisible to agents. If they stall at evaluation, your data exists but is scattered across systems and only reconciled at the UI layer. If they stall at transaction, your checkout requires rethinking as API primitives. Document where the wall is. That document is your agent readability roadmap.

**The Schema Completeness Test.** Take your top twenty products. For each, write down every piece of information a customer needs for a fully informed decision — not just price and availability, but decision-support data: who is this for, what problem does it solve, how does it compare, what are the tradeoffs. Check how much of that exists as structured, machine-readable data in any system you operate. Not marketing copy. Not a PDF. Fields in a database. For most companies, the answer is 15-30%. The exercise tells you which data to encode first. It requires someone sitting down with your best salespeople and asking: walk me through how you sell this to someone who doesn’t know what they need.

**The Vagueness Resolution Audit.** Pull the last hundred inbound inquiries where the customer’s initial question was vague. Examine how each was resolved. What clarifying questions did the rep ask? What information did they access? What decision tree converted ambiguity into a specific outcome? If that resolution logic is locked in a customer service platform, an internal wiki, or someone’s head, no agent can replicate it. If it’s expressed as structured data, the agent can run it automatically.

**The MCP Smoke Test.** Pick one internal system. Build or configure an MCP server that exposes it — it doesn’t need to be production-grade. Point an agent at it and ask it to do something useful. Watch what happens. Every failure mode is a data quality issue surfaced in minutes instead of months. I have watched this exercise reveal integration problems companies lived with for years because the UI was silently papering over them.

**The Competitive Simulation.** Identify your top three competitors. Open Claude, ChatGPT, or Gemini. Give it a realistic purchase prompt — the kind of thing a real customer would ask. Don’t mention any company by name. Let the agent discover, evaluate, and recommend. See who it recommends. See whether your company appears in the consideration set. See how it describes your offering versus theirs, whether it’s working with accurate data or hallucinating from a 2024 blog post. This takes thirty minutes and tells you more about your competitive position in the agent era than any strategy deck. Do it again next month. The gap between companies publishing structured data and those that aren’t will widen every cycle.


## The core thesis

The 2010s software stack was built to keep agents out. CAPTCHAs, bot detection, gated APIs, JavaScript-heavy interfaces — all designed around the assumption that automated access is adversarial. That assumption is now wrong, and for a growing number of businesses it is becoming existentially wrong.

The most valuable traffic your business receives in the next three years will be agent traffic. The companies that make their systems readable and writable will capture that demand. The companies that don’t will be routed around — silently, by agents that find the competitor whose data is cleaner and whose interfaces don’t require a human in the loop.

But the real value of this work extends beyond capturing agent traffic. All of that tribal knowledge that used to live in marketing copy and institutional memory, once it’s encoded as structured data, becomes remarkably easy to build great human experiences around too. You could build a personalized landing page about that farmer and that school in Ethiopia for your specialty coffee, and the agent could suggest taking the customer there. That is easy to do when your data is correct.

Build for agents first. The humans will follow.


## **LINK: [Executive Circle WhatsApp group](https://chat.whatsapp.com/LqpF3i5wDYv1EdraJYKplL?mode=gi_c)**

We launched an Executive Circle WhatsApp group a few weeks ago, and it’s already one of my favorite places to spend time. These are senior leaders working through the same strategic decisions we cover here, sharing what’s actually working and what isn’t. No fluff, no LinkedIn energy. If you’re an Executive Circle member, come join the conversation.

[![](https://substackcdn.com/image/fetch/$s_!iWu3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9ed4069d-61da-4c67-940d-eabe1adf9df6_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!iWu3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9ed4069d-61da-4c67-940d-eabe1adf9df6_1024x1024.png)
