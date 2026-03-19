---
title: "Most AI companies are renting their position. These 4 prompts tell you if yours is one of them."
author: "Nate Jones"
published: 2026-03-19
url: https://natesnewsletter.substack.com/p/perplexity-shipped-its-best-product
subtitle: "Watch now | What Perplexity's smartest move reveals about the most dangerous position in AI."
audience: everyone
scraped_at: 2026-03-19 12:00:16
---

On February 25, Perplexity shipped the best agentic product of the month. And it might not matter.

Perplexity Computer launched to genuine excitement. It’s a cloud-native, multi-model orchestration system that routes work across 19 frontier models, spawns sub-agents, persists for months, and delivers finished artifacts while you sleep. It runs Claude Opus 4.6 as its reasoning core, Gemini for deep research, Grok for speed, GPT-5.2 for long-context recall. It is available today for $200 a month and it is almost certainly worth it for heavy research and ops workflows.

It is also, structurally, a cautionary tale about where most of the AI industry is building right now, and why good execution on the wrong layer of the stack doesn’t save you.

I should say this upfront: this is not a Perplexity hit piece. Perplexity is one of the best-run AI companies in the world. They read the market correctly. They made a genuinely bold call to kill their own ad business in February because they understood that trust is the new distribution. They are targeting $656 million in 2026 revenue, and their search API already has major enterprise customers running it in production.

And yet. Their core reasoning engine runs on a direct competitor’s model. Their deep research runs on another competitor’s model. Even their speed layer depends on a third provider who is building the same product Computer competes with. The week Perplexity launched Computer, Anthropic shipped the enterprise expansion of Claude Cowork with deep connectors, private plugin marketplaces, and the ability to pass context seamlessly across tools. Cowork doesn’t need 19 models. It has one. And it owns it.

That asymmetry between the quality of Perplexity’s execution and the fragility of its structural position is the thing I can’t stop thinking about. Because it’s not just Perplexity’s problem. It’s the position of almost every AI company that isn’t Anthropic, Google, OpenAI, or Meta. Which means it’s probably the position of the company you work for, invest in, or advise.

**Here’s what’s inside:**

- **Perplexity Computer, honestly reviewed.** Who should pay $200/month, who should skip, and the five use cases where it actually over-delivers.
- **The middleware trap, and the math behind it.** Why good execution on the wrong layer of the stack won’t save you, and how the hyperscalers’ $690 billion infrastructure bet makes it worse by the month.
- **Four positions that survive.** The specific structural plays where the hyperscalers’ incentives align with your existence rather than your replacement.
- **The diagnostic.** A five-step test you can run today on your own company, your portfolio company, or your client’s company to know if you’re building a durable position or renting it.

We’ll start with how February 2026 drew the map for everything that follows.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260302_a4w_promptkit_1)

This week’s kit has four prompts built around the diagnostic framework in this article. The first runs the full Middleware Trap Diagnostic on your company — maps every dependency, rates absorption risk, and delivers a verdict. The second triages your domain context into three defensibility tiers so you can see which parts of your claimed moat actually survive platform consolidation. The third builds a 30/90/180-day repositioning roadmap if you’re exposed, including what to stop building and a ready-made answer to “can’t Claude just do this?” The fourth produces a board-ready risk brief for any company you work at, invest in, or advise — written in the language investment committees actually respond to.


## February 2026 drew the map

To understand why any of this matters now, you need to see the full sequence. January and February compressed about two years of strategic positioning into six weeks, and the pattern it revealed will play out on multiple clocks simultaneously. Model capability jumps every six to twelve months. Enterprise procurement cycles run six to eighteen months. The hyperscaler capex must show revenue realization by 2028 or the debt structure starts straining. Trust architecture standardization is a two-to-three-year regulatory grind. Each of these clocks governs different decisions for different people, and conflating them is a mistake I want to avoid. Ready?

**Late January:** OpenClaw goes viral. An open-source AI agent built by Austrian developer Peter Steinberger becomes the fastest-growing repository in GitHub history, blowing past 100,000 stars and climbing well beyond 200,000. It runs locally, connects through WhatsApp and Telegram, and takes autonomous action: managing email, modifying files, browsing the web. The demand signal is massive and undeniable. The trust problem is equally massive. Cisco’s security team finds a third-party OpenClaw skill performing data exfiltration and prompt injection without user awareness. Someone’s agent deletes their emails. Another’s creates a dating profile and starts screening matches without being asked. But despite all of the security flaws, people keep showing up. The hunger for agents that actually do things is real.

**January 12:** Anthropic launches Claude Cowork in research preview for Max subscribers. It’s described as “Claude Code for the rest of your work.” Simple idea, deep execution.

**January 30:** Anthropic releases 11 open-source plugins for Cowork to GitHub. No launch event. No marketing blitz. Just Markdown and JSON files that let Claude handle real enterprise work: contract review, compliance checks, sales preparation, legal intake, internal research. Tasks that sit at the center of high-margin SaaS products.

**February 3:** Investors connect the dots. The iShares Expanded Tech-Software Sector ETF records its worst stretch since the 2008 financial crisis. Bloomberg reports a $285 billion selloff across software, financial services, and asset management stocks. The market isn’t reacting to a chatbot. What spooked investors was simpler and more profound: a model provider had just demonstrated it could collapse the entire tool stack above it.

**February 5:** Two things happen. Anthropic ships Claude Opus 4.6 with a one-million-token context window, pushing the frontier for long-context reasoning. The same day, OpenAI launches Frontier, an enterprise platform that connects siloed data warehouses, CRM systems, and internal applications into what OpenAI calls “a semantic layer for the enterprise.” We’ll come back to why that matters. Meanwhile, Amazon announces $200 billion in 2026 capital expenditure, blowing past consensus estimates of $147 billion and sending its stock down 8%.

**February 11:** Cowork ships on Windows. Seventy percent of desktop computing now has access.

**February 14:** Peter Steinberger, OpenClaw’s creator, announces he’s joining OpenAI. The project moves to an open-source foundation.

**February 18:** Perplexity officially confirms it has abandoned advertising entirely. Executives tell the Financial Times that ads risk making users “suspicious of everything” and that Perplexity is “in the accuracy business.” Killing a revenue stream to protect trust tells you exactly how Perplexity’s leadership sees their moat: accuracy and sourcing, not eyeballs.

**February 24:** Anthropic’s enterprise agents launch. Deep connectors, private plugin marketplaces, prebuilt templates.

**February 25:** Three things happen on the same day. Samsung unveils the Galaxy S26 as “the agentic AI phone.” Google previews Gemini agents with a framework called AppFunctions that lets apps expose data directly to AI agents at the OS level. And Perplexity ships Computer.

Are you out of breath? In just six weeks, the industry stratified into layers with fundamentally different structural economics. At the bottom: model providers who own the weights. In the middle: orchestration and application layers who combine models into products. At the top: distribution owners who control the surface where users encounter agents. And hovering over everything: cloud providers spending roughly $690 billion a year on infrastructure they must fill with tokens.

Perplexity sits in the middle layer. The most exposed layer.


## The middleware trap, clearly stated

When a technology stack consolidates, the layer that gets squeezed is the one between the platform owner and the customer. It happened to travel agents when airlines went direct. It happened to media companies when Facebook and Google captured distribution. It happened to enterprise middleware when cloud providers absorbed the application layer. The common thread: if you don’t own the layer below you or the relationship above you, you’re borrowing time.

In AI, the trap has a specific shape. You’re in it if you build on models you don’t control and serve customers that model providers are now selling to directly. Every upstream provider has the ability and now the incentive to replicate what you do, or to change pricing and access terms that compress your margins. Reports surfaced in February that Anthropic began banning users who powered OpenClaw with Claude credentials. If that logic extends to orchestration layers wrapping Claude in competing products, the dependency risk stops being theoretical.

But the squeeze isn’t only coming from below.


### The model makers are coming for the context layer

The conventional defense for middleware companies is: “We have domain expertise the model providers can’t replicate.” OpenAI Frontier just blew a hole in that argument.

Frontier launched as an enterprise platform that connects siloed data warehouses, CRM systems, and internal applications into a shared context layer. It onboards agents with institutional knowledge, grants them identity and permissions, and builds evaluation loops so agents improve with experience. That is the context layer. The thing that was supposed to be your moat. Harvey, Sierra, Decagon, and Abridge are already committed as Frontier Partners. Smart companies building on top of models are joining forces with OpenAI because they don’t want to get eaten.

This doesn’t mean domain context is worthless. It means the form that survives is narrower than people think. If your “domain expertise” is mostly connecting enterprise systems and teaching AI how your org works, Frontier does that now with Forward Deployed Engineers. If it’s something deeper, proprietary data or regulatory knowledge built from years of compliance or operational insight from running specific physical processes, that’s still valuable. But most companies claiming domain moats haven’t done the rigorous thinking to figure out whether their context actually survives this kind of consolidation.


### The hyperscalers aren’t neutral referees

The five largest hyperscalers plan to spend $660 to $690 billion on capital expenditure in 2026, nearly double the roughly $443 billion they spent in 2025. Amazon alone announced $200 billion, blowing past consensus estimates and sending its stock down 8%. Alphabet guided $175 to $185 billion. Meta projected $115 to $135 billion. Microsoft is running at $120 billion-plus. Goldman Sachs projects total hyperscaler capex from 2025 through 2027 will exceed $1.15 trillion.

Where do the tokens come from to justify that spend? AI-related services delivered roughly $25 billion in revenue to hyperscalers in 2025, approximately 10% of what they spent on infrastructure. The gap between infrastructure investment and revenue realization is measured in years, not quarters.

These are not companies that can afford to be neutral platform providers. Every layer of the stack a hyperscaler controls generates tokens on its infrastructure. A layer they don’t control is a layer where somebody else captures value from compute they’re subsidizing. This is why AWS secured distribution partnerships for Frontier and is building persistent agent infrastructure on Bedrock. Microsoft takes a significant revenue share from OpenAI. Google invested billions in Anthropic while building its own agent layer into Android. Amazon backs both OpenAI and Anthropic while building custom Trainium silicon to undercut Nvidia’s inference economics.

The framing that “cloud providers win regardless” was the early 2025 story. The 2026 question is which layer generates the most tokens, and the hyperscalers are structurally compelled to own as many of those layers as possible.

That is the world Perplexity Computer launched into. So let’s talk about the product itself, because it really is quite good.


## What Perplexity Computer actually is

Despite the name, Computer is not hardware. It’s a cloud-based agentic system that orchestrates 19 AI models together to execute complicated multi-step workflows end to end. It is available exclusively on Perplexity’s $200-a-month Max tier, and it represents the company’s clearest bet yet that the value layer in AI is not the model but the orchestration.

The core idea: you describe an outcome and Computer decomposes it into tasks and subtasks. It spawns specialized sub-agents that run in parallel. One agent does web research while another drafts a document, a third generates visuals, and a fourth writes code. Each task runs in an isolated compute environment with access to a real file system, a real browser, and integrations with tools like Gmail, Slack, GitHub, Notion, Salesforce, and more than 400 others.

The model routing is Perplexity’s claimed differentiator. Computer uses Opus 4.6 as its central reasoning engine and delegates to specialized models per task. The routing is automatic, but you can override it and pin specific models to specific subtasks if you want to manage token budgets. Crucially, workflows can run asynchronously for hours or even months. You can kick off a job, close your laptop, and come back to finished deliverables. Computer retains persistent memory across sessions, accumulating context about your preferences and past work over time.

Perplexity positioned this as a secure, responsible version of OpenClaw. But where are users actually finding value?

The most credible early use cases cluster around research-heavy, multi-source workflows. Competitive intelligence and market research lean directly on Perplexity’s search infrastructure. Give it a prompt like “analyze the top five competitors in X space, track their recent product launches, and produce a briefing,” and Computer parallelizes multiple search types simultaneously, reads full source pages, cross-references findings, and constructs a structured report. Financial analysis and investment memos work similarly: pull earnings data, compare margins across competitors, synthesize analyst sentiment, and output a formatted PDF with charts. This is where the multi-model routing earns its keep. Research agents gather data while a coding agent builds the visualizations.

Outbound and pipeline building was more surprising to me. An early reviewer tested cold outreach automation: Computer found real email addresses, researched each prospect’s recent activity, drafted personalized messages referencing specific details, and sent them through a connected Gmail account. The recurring version of this, daily competitive monitoring and weekly reports, is where Computer shifts from a one-off assistant into a persistent agent.

End-to-end build tasks are another strong category. “Build me a personal finance dashboard” or “create a portfolio site with case studies and deploy it.” Computer handles the research, design, code, and deployment loop in one long session, although it currently stamps outputs with a watermark. And content repurposing works surprisingly well: pull a segment from a podcast, extract the clip, convert to vertical format, add captions. That’s a multi-tool pipeline that normally requires stitching together three or four services.

So who should actually pay for this? My honest answer: power users in those specific verticals. If you already spend $100 to $200 a month across multiple AI tools, you’re tired of context switching, and any of those use cases resonate, this may consolidate your workflow in a way that’s worth every penny. Perplexity’s own executives have been explicit that they’re targeting people making consequential decisions, not maximizing free-tier monthly active users. Founders doing their own research, solo operators, analysts, consultants. The parallel research engine is where Computer over-delivers, and that plays directly into Perplexity’s search heritage. If your workflow is primarily conversational, if you need deep technical coding, or if you need surgical precision on nuanced creative work, skip this. Computer’s autonomy is a feature when it works and a liability when you need fine control.

I should note: Perplexity’s planned live demo was canceled due to product bugs, which tells you reliability at this level of autonomy isn’t fully baked yet. Buyer beware. But Computer is the most ambitious attempt so far to package truly multi-model agentic AI into a tidy consumer-facing product, and for the right user, it delivers.

Now. Having looked at Computer in detail, I think you can see where Perplexity is at risk as a company. Because Computer, as good as it is, does not solve any of Perplexity’s underlying problems. In fact, February of 2026 just revealed the trap more clearly. Multi-model orchestration is a moat, but an easily replicated one. The commoditization of the models themselves will make that orchestration layer less valuable over time.

So the natural question becomes: in a world where the middleware layer is structurally fragile, which positions actually have durability?


## Four positions that survive

February didn’t just reveal the trap. It also revealed which plays have lasting durability, where getting squeezed by the model providers either can’t happen or would cost them more than it’s worth. There are four. Most companies should be targeting one of them. A few, like Perplexity, are straddling more than one.


### Position 1: Know which context to platform, which to retain, and why

I need to be honest about this one, because it’s the position most AI companies claim and the one most under assault right now.

Six months ago, the advice was straightforward: models are general-purpose, so your value is making them specific. Encode institutional knowledge, proprietary data, workflow-specific context. The model providers can’t build that. Frontier changed the equation. OpenAI is now building the platform for institutional context, connecting CRMs, data warehouses, and internal tools into a shared semantic layer, with onboarding workflows that teach agents how the business operates. The model maker isn’t just providing the reasoning engine anymore. It’s providing the scaffolding to hold your institutional knowledge.

But “domain context is dead” overshoots. Enterprise leaders have survived platform lock-in with Salesforce, SAP, and Oracle. They have procurement frameworks for this. The question for enterprise leaders is not whether to use something like Frontier, but which context to platform and which to retain.

There are three kinds of enterprise context, and each has a different answer.

Structural context is how systems connect, where data lives, what permissions exist. This is commodity plumbing. Frontier’s connectors handle it. If your startup’s moat is wiring up Salesforce to Jira to Snowflake for a customer, Frontier eats you on a twelve-to-twenty-four-month timeline.

Operational context is how decisions actually get made in practice. The informal knowledge in senior people’s heads. The institutional judgment nobody’s written down. This is more interesting. Frontier can approximate it, but the approximation has limits that matter. The rate of change is the variable that determines defensibility. If your operational context updates quarterly from regulatory filings, the platform keeps up. If it updates hourly from live physical operations, the platform can’t. For slowly-changing operations, this window closes within one to two model generations. For companies generating novel data daily, the window stays open much longer.

Proprietary context is data and judgment that exists nowhere else, where handing it to the platform would create competitive exposure. A trading desk’s risk models. A drug company’s experimental data. A manufacturer’s sensor data from proprietary production lines. This is where the enterprise’s calculation flips, because platforming it means giving the provider access to the thing that makes you you.

And here’s the question most AI strategy discourse ignores: Harvey is a Frontier Partner building legal AI on OpenAI’s platform. Every piece of legal domain knowledge Harvey encodes in Frontier’s semantic layer is knowledge that lives on OpenAI’s infrastructure. Today, that’s a partnership. In three years, when OpenAI needs to justify an $840 billion valuation and legal AI is a proven market, is it still a partnership? Enterprise buyers and VCs funding vertical AI companies need to think about this honestly.

The middleware companies that survive are those whose value proposition lives in the proprietary layer. The context the enterprise can’t rationally give to the platform provider even if the platform offers to manage it. That’s a narrower niche than the VC pitch decks suggest. But it’s real, and it’s defensible for structural reasons.


### Position 2: Become infrastructure the agents call

This might actually be Perplexity’s most durable business, and the one the market is undervaluing. I keep coming back to this because it’s so counterintuitive: everyone talked about Computer, the flashy consumer product. People aren’t talking enough about the fact that Perplexity’s search API already has major enterprise players using it in production at significant scale. Anthropic’s agents, Google’s agents, and OpenAI’s agents all potentially depend on Perplexity as a service for real-time grounded search.

That’s a fundamentally different position than Computer. Computer competes with Cowork. The search API powers systems like Cowork. Infrastructure that agents need regardless of who wins the orchestration war is the most resilient layer in the stack.

Quartr, a financial data company, published a case study showing how Perplexity Finance uses their earnings transcript API as a core data layer. Quartr doesn’t compete with Perplexity. It’s infrastructure Perplexity can’t function without. That’s the model. Data feeds, verification services, domain-specific APIs, compliance checking. These are the picks and shovels of the agent era, inherently safer than building another wrapper because the agent providers are your customers, not your competitors.


### Position 3: Own the customer workflow deeply enough that switching costs protect you

When Anthropic shipped private plugin marketplaces where organizations deploy custom agents with institutional knowledge encoded into workflows, that’s not a chatbot. That’s a system that learns how this specific legal team reviews NDAs and how this specific trading desk evaluates risk. Ripping it out means rebuilding all of that institutional encoding.

Stop thinking about model selection. Start thinking about integration depth. What matters is not which model you use but how many institutional workflows break if someone rips your system out. Deep integration takes longer than wrapping an API, but it produces something the wrapper approach never can: a product that gets more valuable the longer it runs, because it accumulates institutional context that can’t be replicated.


### Position 4: Own the trust and verification layer

This is the emerging position almost nobody is building yet, and it might be the biggest opportunity in the stack.

February revealed three incompatible trust architectures deploying simultaneously. OpenClaw runs locally with no enforced security. Perplexity Computer operates in the cloud with curated sandboxes. And Google’s Gemini agents sit inside OS-level containment on the phone itself. Each makes different tradeoffs; none are auditable by the others, and the governance frameworks haven’t caught up.

As agents proliferate, someone needs to audit what they do, verify their outputs, and enforce policy. The model providers are focused on capabilities, not governance. The gap between “agents are doing real work” and “we can prove what agents did” is wide and growing. This is analogous to what accounting firms did when financial complexity outpaced regulation, or what cybersecurity companies did when enterprise computing outpaced IT security. The opportunity emerges from the delta between adoption speed and governance maturity. That delta is enormous right now.


## The blind alleys

Despite those four genuine openings, there are corners of middleware that look like dead ends to me. Places the hyperscalers will eat.

First: don’t get in the way of which cloud runs the tokens. Total AI inference demand is growing, but the distribution of that demand across cloud providers is fiercely contested. AWS securing distribution for Frontier means those enterprise agent tokens run through AWS, not Azure. Every exclusive deal shifts the margin on a fixed pool of enterprise customers. I would not want to be a middleware company getting in the way of multi-cloud orchestration.

Second: don’t build where the margin gets squeezed to zero. Token volume can grow 10x and the middleware layer can still get crushed if model providers absorb its functionality. When I outlined the four positions where middleware survives, every single one focused on tokens that mean something, on sustainable differentiated value. If you cannot show that your tokens add something beyond baseline vanilla inference from model providers, your margin will get squeezed into nothing. Inevitably.

Third: don’t get between the hyperscalers and the enterprise relationship. When OpenAI deploys Forward Deployed Engineers alongside customers to set up Frontier, it’s building the relationship that determines which AI services that enterprise buys for the next several years. Anthropic is doing the same with their enterprise teams. If you are a middleware company, what this implies is that you need to find a corner with clear differentiated value where you can build a relationship with an internal champion who is AI-fluent enough to understand why you exist. You cannot be looking for the people behind the ball. You need the smart, proactive buyer who understands that you’re building something structural the hyperscalers themselves aren’t going to go after. I know that demands more of our sales teams than we’ve traditionally had to give. But suspicious CTOs are already saying “if we wait six months, can’t Claude just do it?” You need a real answer to that question.


## The diagnostic

You can run this test today. It takes five minutes and it will tell you whether you’re building a durable position or renting it.

Step one: draw your stack. Every dependency your product requires. Model, cloud, data sources, distribution channels.

Step two: for each, ask two questions. Does the provider have the incentive and ability to absorb my functionality? And is the provider now building the context layer I thought was my moat?

Step three: for each “yes,” ask what you still own if that provider moves into your space. If the answer is “our UX” or “our integrations,” those are real value but borrowed value. If the answer is “our domain context,” run it through the three-layer test: structural (Frontier eats it), operational (check the rate of change), or proprietary (worth defending).

Step four: check against the four durable positions. Proprietary context that can’t be rationally platformized? Infrastructure agents depend on? Workflow depth with real switching costs? Trust and verification?

Step five, the one people skip: look at your position from the hyperscaler’s perspective. You are a token-generating entity running on their infrastructure. Does your existence generate more tokens for them, or do you sit between them and a customer they could serve directly at higher margin? If you’re the former, a search API that Cowork calls thousands of times per query, the hyperscaler wants you to succeed. If you’re the latter, a middleware layer that handles a customer interaction in one API call that Frontier would handle in ten, the hyperscaler’s economic incentive is to replace you.

If none of the four positions apply and the hyperscaler math works against you, you’re in the middleware trap. That doesn’t mean your business fails tomorrow. It means your structural position degrades over time as the layers above and below consolidate, and the $690 billion in capex pressure accelerates that consolidation. The time to reposition is now, while you still have revenue, customers, and optionality.


## What Perplexity actually teaches

Let me come back to Perplexity, because the nuance matters and I’ve been turning it over since the launch.

Perplexity is simultaneously in the middleware trap with Computer and building one of the most durable positions in the stack with its search API. Everyone talked about Computer. The press covered Computer. But the search API as agent infrastructure, the thing that makes Perplexity a pick-and-shovel provider to the entire ecosystem, got much less attention. That is their strategic way out of the middleware trap, and I think their leadership knows it.

The decision to kill advertising to protect trust tells you exactly where the executives are leaning. “We are in the accuracy business,” they told the Financial Times, “and the business is giving the truth, the right answers.” That’s the search infrastructure talking, not the orchestration layer.

The lesson for everyone else is harder than it looks. Anthropic owns the model and is collapsing layers above it. OpenAI owns the model and is building the enterprise context platform. Google owns the phone, the model, the cloud, and the browser. Meta owns distribution and bought Manus for the execution layer. AWS and Azure are economically compelled to own as much downstream token-generation surface as possible to justify their infrastructure bets.

If you’re not one of those companies, and almost nobody is, your strategic imperative is not to compete on their layer. It’s to find the position where their incentives align with your existence rather than your replacement. Infrastructure the agents call. Workflow depth that generates tokens the hyperscaler wants. Governance the ecosystem needs. And proprietary context the enterprise can’t rationally hand to a platform provider. Those categories are narrower than a lot of pitch decks suggest. But they’re real, and the enterprises that need them know they need them.

That’s where a durable position lives in 2026. The bar is higher than it was, the window to claim a position narrower than it’s ever been. And the clocks are running at different speeds depending on where you sit: model providers will ship the next capability jump within twelve months, enterprise procurement will lock in platform decisions over the next six to eighteen, the hyperscaler capex must show returns by 2028, and the regulatory frameworks governing agent trust will take two to three years to crystallize.

If you’re in the middleware layer, the clock that matters most is the first one. Every model generation that collapses your differentiation narrows the window for repositioning.

If you’re an engineer or product person at a company in this middleware business and you’re reading this thinking you might be in trouble, you’re probably right. The ideas in this piece, particularly the four positions, are your starting point for figuring out where to push your team or where to point your career. If you’re a solo operator or founder, this is your roadmap for strategic positioning in a world with hungry hyperscalers. And if you’re in the C-suite, this is a conversation that belongs in the boardroom. In a world where the hyperscalers need downstream tokens, it’s irresponsible not to treat middleware fragility as a strategic risk.

Everything else is renting. And the landlords are getting hungrier.

[![](https://substackcdn.com/image/fetch/$s_!c-qE!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0c11d76f-6fdb-46db-8563-191001b3422d_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!c-qE!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0c11d76f-6fdb-46db-8563-191001b3422d_1024x1024.png)
