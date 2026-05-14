---
title: "Six layers your agent has to handle. Most products have only thought about two. + a responsibility-layer audit."
author: "Nate Jones"
published: 2026-05-12
url: https://natesnewsletter.substack.com/p/agentic-commerce-protocol-war
subtitle: "Watch now | For most of the internet’s history, a purchase has been a human action that everyone in the chain could see."
audience: everyone
scraped_at: 2026-05-14 14:32:11
---

For most of the internet’s history, a purchase has been a human action that everyone in the chain could see. A person clicked a button on a merchant’s site. A payment credential moved through a processor. A network or wallet weighed the risk. The merchant took responsibility for the order. The records were imperfect, but everyone agreed on the shape of the evidence: a human was present, a page was shown, a credential was used, a final action was taken.

Agentic commerce breaks that structure.

Software is starting to hold wallets, sign authorizations, and pay merchants directly. Some of those agents are spending your money. Some are spending your company’s. Some are spending your customers’. When one of them sends money to the wrong place — and one of them will — someone is going to be left holding the bag. Protocol camps are fighting over who that someone is.

The question stops being “can the customer pay?” and becomes “how does everyone know the agent was allowed to do what it just did?” That question reaches well past checkout. It touches identity, authorization, fraud, payment credentials, settlement, refunds, liability, data rights, and the merchant’s relationship with the customer. The old purchase bundle comes apart, and the market isn’t converging on a single replacement. It’s splitting into protocol camps, each owning a different piece of what used to live behind one click.

That’s the split. A fight over where commercial trust lives, not over a single button. And it will shape who keeps the customer, who carries the loss, and who gets to write the rules of online buying for the next decade.

**Here’s what’s inside:**

- **The first round of the fight is already over.** OpenAI and Stripe shipped Instant Checkout in September. Five months later it was scaled back, while Shopify and Google’s counter-protocol gained ground.
- **Authorization is not payment.** The evidence layer agentic commerce needs, why it has to outlive the transaction, and the two routes Google and Stripe are taking to build it.
- **The stablecoin case that holds up.** Software paying software is a different business problem than a person buying shoes, and the rails should be different too.
- **Where this lands and who owns which layer.** Why AWS quietly matters most, and what every kind of builder, merchant, and operator should do now.
- **Two prompts to expose your own gaps.** A responsibility-layer audit that forces you to name who owns each piece of an agentic purchase in your product, and an authorization spec that finance and legal will actually accept.

The split started a year ago. Start with Instant Checkout: how OpenAI and Stripe launched it, and why OpenAI walked it back.


## **LINK: Grab the [prompts](https://promptkit.natebjones.com/20260508_104_promptkit_1)**

The old checkout page collapsed six commercial responsibilities into one human click. The prompts in this kit do the opposite — they pull those responsibilities apart and force you to put a name next to each one. The first prompt is a responsibility-layer audit. You describe what your agent does, who’s buying, who’s selling, and the prompt produces a populated table showing who owns each of the six layers: discovery, authorization, payment credential, settlement, merchant relationship, governance. The rows labeled “nobody owns this yet” are the ones to read first. Those are the failure modes you haven’t priced in. The second prompt is the authorization spec finance, legal, and security will demand the moment your agent goes near real money — scope, limits, evidence layer, failure handling, escalation thresholds. You will eventually be asked for this document. Better to draft it before you’re asked. If you can’t answer the questions either prompt asks, the prompt tells you so — and that answer is the artifact you actually needed.


## The checkout button was the wrong center

The most visible version of this shift arrived September 29, 2025, when OpenAI and Stripe co-launched the [Agentic Commerce Protocol](https://github.com/agentic-commerce-protocol/agentic-commerce-protocol), or ACP, alongside [Instant Checkout in ChatGPT](https://openai.com/index/buy-it-in-chatgpt/). The product was easy to grasp: ask ChatGPT about something, and for supported merchants, buy without leaving the conversation. Stripe handled payment. OpenAI ran the agent surface. The merchant stayed merchant of record — still on the hook for fulfillment, returns, and support.

Five months later, OpenAI [scaled it back](https://www.cnbc.com/2026/03/24/openai-revamps-shopping-experience-in-chatgpt-after-instant-checkout.html). Etsy reported low volume. Walmart’s head of AI told *Wired* that conversion inside the chatbot ran three times lower than the same items requiring a click-out. The infrastructure problem turned out to be harder than the demo suggested — real-time inventory sync across millions of SKUs, sales tax collection, fraud prevention, multi-item carts. OpenAI’s revised position is that ChatGPT should focus on discovery and let merchants own checkout in their own apps and sites.

The more interesting fact is what didn’t retire: ACP itself kept going. The spec is on its fifth revision, still co-maintained by OpenAI and Stripe, [PayPal joined as a payment provider](https://newsroom.paypal-corp.com/2025-10-28-PayPal-Launches-Agentic-Commerce-Services-to-Power-AI-Driven-Shopping) in October, [Salesforce](https://investor.salesforce.com/news/news-details/2025/Salesforce-Announces-Support-for-Agentic-Commerce-Protocol-in-Collaboration-with-Stripe/default.aspx) is in, Shopify supports both ACP and UCP. What got retired was a product hypothesis: that checkout itself should live inside the assistant. What survived was the protocol that defines how an agent and a merchant pass structured purchase data to each other.

The ACP/Instant Checkout story is the cleanest possible proof of what this whole article is arguing — the checkout button was never the right center. OpenAI bet that the assistant should own the moment intent becomes a completed transaction. The market said: own the moment intent forms, sure; the transaction is going somewhere else. ACP solves the data problem between agent and merchant. Whether checkout completes inside chat, inside a merchant app surfaced inside chat, or back on the merchant’s website turns out to be a product question, not a protocol question.

Stripe made it easy for software businesses to accept money from humans on web pages. ACP carries that logic into a world where software, not a human at a browser, is the source of buying intent. Stripe is making payment authority programmable enough for agents to use safely, and the protocol travels with the agent surface regardless of which checkout flow wins.

For OpenAI, the retreat is sharper. ACP still gives ChatGPT a path from recommendation to transaction. But the retreat means the assistant is back upstream of the actual economic event, sending intent and structured purchase context downstream to whoever owns conversion. A system that answers and recommends but doesn’t close the loop is in a different strategic position than one that does.

The limitation Instant Checkout ran into is the same limitation any assistant-owned checkout will run into. If checkout moves into the agent surface, the merchant risks losing parts of the customer experience that have always been central to its business. The merchant may stay merchant of record while the assistant controls discovery, ranking, comparison, bundling, substitution, and the final presentation of choices. That weakens the merchant’s ability to tell its story, gather first-party context, and shape repeat behavior.

This isn’t an abstract branding worry. It’s a control problem. If the assistant becomes where customers express intent, the merchant’s website stops being the default starting point of the relationship. The merchant still sells, but through a surface it doesn’t own.

That’s why Shopify’s response matters.


## UCP is a merchant control argument

Shopify and Google’s [Universal Commerce Protocol](https://shopify.engineering/UCP), or UCP, should be read as a merchant control argument.

UCP represents a different view of what needs to be standardized. ACP focuses tightly on the agent-to-merchant checkout flow. UCP is broader, aiming to make the full shopping journey work across AI agents, merchants, payment providers, identity systems, and commerce platforms — discovery, cart, checkout, order management, returns, customer identity, loyalty, and merchant rules.

The distinction is the whole point. A merchant doesn’t only need an agent to pay. It needs the agent to understand what the merchant actually sells and the conditions it’s willing to sell under. Real commerce involves product variants, inventory, shipping rules, promotions, loyalty accounts, return policies, subscriptions, bundles, warranties, fraud rules, taxes, support, and post-purchase communication. A checkout protocol that ignores most of that may complete a transaction, but it won’t preserve the merchant’s business.

Shopify’s incentive is straightforward. Shopify merchants need to be visible to agents without becoming anonymous inventory nodes inside someone else’s assistant. They need to keep the customer relationship, the order record, the checkout rules, and the post-purchase flow — and to know which channel created the demand and what data they get back.

The threat isn’t theoretical. I’ve largely stopped using Google to start shopping research and I rarely begin on Amazon. A sound system, a couple of bicycles — I worked through the comparison and the decision inside ChatGPT, and only went to a merchant site to finish. ChatGPT crossed [900 million weekly active users](https://techcrunch.com/2026/02/27/chatgpt-reaches-900m-weekly-active-users/) in February. Some meaningful share of those users is doing what I’m doing. A merchant that isn’t legible to that surface isn’t in the running before the surface even shows results.

That’s the tension UCP tries to manage: agents should be able to shop across merchants, but merchants shouldn’t have to surrender the structure of their business to participate. The pitch, in plain terms, is to make commerce machine-readable without reducing the merchant to a product feed and a payment endpoint.

Google’s involvement adds another layer. Google has every reason to make AI shopping work through Gemini, AI Mode, Merchant Center, and its broader advertising and commerce stack. If people start asking agents what to buy, Google needs its merchant graph to stay useful. UCP keeps merchants connected to AI discovery without forcing every purchase into a single assistant-owned checkout.

The first split, then, isn’t ACP versus UCP in a winner-takes-all sense. ACP is strongest as an agent-surface checkout standard. UCP is strongest as a merchant-system interoperability standard. ACP asks how a purchase gets completed when the buyer is inside an assistant. UCP asks how a merchant’s whole commercial system can be understood and used by agents without removing the merchant from the relationship.

Both questions are real. They just locate power in different places.


## Why AI agent authorization is different from payment

Below checkout sits a layer that’s easy to miss: authorization.

Authorization is proof that the agent was allowed to take the action. It’s not the same as payment. A payment system can move money; that doesn’t prove the money should have moved. In human commerce, authorization is usually compressed into the final click, a wallet confirmation, a card challenge, or an account login. With agents, that compression breaks down.

Suppose a person tells an agent, “Book me the best hotel near the conference under $300 a night.” The agent searches, compares, and finds a room. But the final purchase depends on taxes, fees, cancellation policy, loyalty status, distance from the venue, check-in time, and whether the rate is refundable. If the agent books a non-refundable room that technically fits the budget but violates what the user actually meant — who’s responsible?

Now run the same scenario inside a company. A procurement agent is told to find a software vendor, compare pricing, and buy access for a team. The agent has to know budget owner, vendor approval status, security policy, contract threshold, data handling requirements, renewal terms, and whether the purchase creates a long-term obligation. Being able to pay isn’t sufficient. The company needs evidence that the agent had the authority to pay.

Google’s [Agent Payments Protocol](https://cloud.google.com/blog/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol), or AP2, targets this gap. AP2 introduces the idea of a *mandate* — a structured record of what the user authorized the agent to do. In plain English, it’s a permission slip: the scope of the task, the constraints, and the proof that the user approved the agent’s action.

Agentic commerce needs a new evidence layer. The old checkout page generated evidence through a human session and a final click. An agent’s evidence may need to begin earlier, last longer, and travel across systems. The user might authorize the agent before the merchant is even known. The agent might act later. The final price might shift. The purchase might be one of several options the agent considered. If the transaction is disputed, a payment receipt isn’t enough — the system has to show what the user asked for, what the agent was permitted to do, and whether the agent stayed inside those limits.

Stripe shipped the consumer-facing version of the same idea in April. [Link’s wallet for agents](https://stripe.com/blog/giving-agents-the-ability-to-pay) lets a person grant an agent OAuth access to their Link wallet. The agent submits a spend request with context — merchant, amount, line items, purpose. The user approves on the web or in the Link app. Link returns either a one-time-use card or a Shared Payment Token, scoped to that purchase. The agent never sees the underlying card. Google designed a protocol for the authorization record; Stripe shipped a product that produces one.

Visa, Mastercard, and PayPal are moving in the same general direction, each from its own position in the payments system. [Mastercard Agent Pay](https://www.mastercard.com/news/press/2025/april/mastercard-unveils-agent-pay-pioneering-agentic-payments-technology-to-power-commerce-in-the-age-of-ai) is built around agent registration, tokenized credentials, consumer control, and continuity of fraud and dispute protections. [Visa Intelligent Commerce](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.22276.html) takes a similar approach — trusted agents, payment tokens, secure transaction rules. [PayPal’s agentic commerce services](https://newsroom.paypal-corp.com/2025-10-28-PayPal-Launches-Agentic-Commerce-Services-to-Power-AI-Driven-Shopping) try to make PayPal the wallet, trust, merchant services, and buyer protection layer across AI surfaces.

These companies aren’t trying to own the recommendation layer. They’re trying to own the trusted transaction layer. The bet is that agentic commerce won’t scale unless consumers, merchants, and businesses trust the credential, the permission record, and the dispute process.

It’s a strong bet. The more autonomous agents become, the more valuable authorization gets. Companies won’t allow software to spend meaningful money unless the system can prove who authorized the action, which policy applied, what limit existed, and what happens if the outcome is wrong.


## Stablecoins matter most when agents buy software from software

Stablecoins enter for a different reason.

A stablecoin is a digital token designed to track the value of a currency, usually the U.S. dollar — USDC is the canonical example. They can move value quickly, often across borders and outside traditional card settlement windows. They’re particularly useful when the buyer and seller are both software systems rather than a consumer and a retail merchant.

The consumer version of agentic commerce is easy to picture: a person asks an agent to buy shoes, groceries, coffee, or a flight. In those cases, cards and wallets remain useful because they already carry consumer protection, refunds, cardholder recognition, fraud monitoring, and broad merchant acceptance.

The more interesting stablecoin case is different. An agent may need to pay an API for a single data request. A coding agent may buy access to a hosted tool. A research agent may spend a few cents for a document, a model call, a browser action, or some specialized service. A SaaS service may want to charge per task instead of per month. A company may want each of its agents to have its own wallet, budget, and spending log. These payments are often too small, too frequent, or too software-native for ordinary checkout.

Coinbase’s [x402](https://docs.cdp.coinbase.com/x402/docs/welcome) matters for this reason. x402 makes payment part of the web request itself. The name refers to HTTP 402 — the long-dormant “payment required” status code that was always in the web’s design but never became a real payment layer. In an x402 flow, software requests a resource, receives payment instructions, pays, and gets access. The payment becomes part of the interaction between machines.

Stripe’s [Machine Payments Protocol](https://stripe.com/blog/machine-payments-protocol), or MPP, points the same way. MPP is built for agents and software systems paying other software systems — less about a person buying from a merchant website, more about agents paying for services, tools, API calls, data, compute, or access. Stripe’s broader stablecoin work (Bridge, Privy, and Tempo) gives it the wallet, issuance, orchestration, and settlement infrastructure to back it up.

Circle’s [Arc](https://www.circle.com/en/pressroom/circle-launches-arc-public-testnet) belongs in the same category, aimed at making USDC and related infrastructure credible for enterprise-grade stablecoin settlement. Coinbase is pushing x402 and agentic wallets. Stripe is building across cards, wallets, stablecoins, merchant infrastructure, and machine payments. None of these companies is asking, narrowly, whether consumers will pay merchants in stablecoins. They’re asking whether software will need a native way to pay other software.

That’s worth being precise about, because “stablecoins replace cards” is too broad. Stablecoins may be a better rail for some machine-to-machine payments. Cards and wallets may stay better for many consumer purchases. Both can coexist because they solve different business problems.

A card is still a strong adapter to the existing commercial web. A stablecoin wallet may be a better primitive for agents that need small, fast, programmable payments. A payment token from Stripe, Visa, Mastercard, or PayPal may be the safest credential for a consumer purchase. An x402 or MPP payment may fit best when an agent buys a digital resource from another service.

The right product question isn’t which rail is more futuristic. It’s which rail matches the responsibility, economics, and risk of the transaction.


## The hyperscalers will try to own the governance layer

The newest signal is AWS.

On May 7, AWS announced [Amazon Bedrock AgentCore Payments](https://aws.amazon.com/blogs/machine-learning/agents-that-transact-introducing-amazon-bedrock-agentcore-payments-built-with-coinbase-and-stripe/), built with Coinbase and Stripe. The announcement shows where enterprise agent payments are likely to land. If companies build agents on a cloud platform, they’ll expect the platform to help manage payment authority, wallet access, budgets, approval rules, and logs.

That’s the governance layer.

Governance is the set of controls that determine what an agent is allowed to do, what it isn’t, how much it can spend, which vendors it can pay, which human must approve which action, and what record gets kept. In normal companies, that means procurement policy, finance controls, expense rules, vendor approval, audit trails, security policy, and compliance requirements. Agentic commerce drags those controls into the agent runtime.

AWS doesn’t need to own every payment protocol to own part of this layer. It can connect to Coinbase for x402 and stablecoin wallet flows. It can connect to Stripe and Privy for wallet infrastructure. It can support more protocols over time. Its strategic position isn’t necessarily the payment rail. It’s the environment where enterprise agents run, receive tools, execute tasks, and are monitored.

That’s a powerful place to sit. The agent runtime knows the task, which tools were called, which policy was active, which budget applied, and what the agent did before and after the transaction. A payment provider sees the payment. The agent platform sees the work around the payment.

Amazon’s commerce platform shows the other side of the same story. Big platforms aren’t going to let outside agents act freely inside their systems. Amazon’s own AI shopping work and its resistance to unauthorized agentic browsing make clear that platform commerce will stay controlled. The open agentic web may grow, but powerful marketplaces will decide which agents they trust, which data they expose, and which automated purchases they allow.

So product teams shouldn’t assume agentic commerce is a march toward open interoperability. Some parts of the market will be protocol-driven. Some will stay platform-controlled. Some will open up only under strict trust, identity, and data-sharing terms.


## The real product question is where responsibility lives

The most useful way to evaluate any agentic commerce product is to ask where responsibility lives.

When the agent finds the product, who’s responsible for the recommendation? When it interprets the user’s intent, who’s responsible for the interpretation? When it requests permission, who records what the user approved? When it pays, who owns the credential and the risk? When the merchant fulfills, who owns the order? When the buyer wants a refund, who handles the return? When the payment is disputed, what evidence exists? When the agent is manipulated by a malicious site, who absorbs the loss? When the agent buys something technically allowed but commercially foolish, who’s accountable?

These questions don’t have one answer. They divide across layers.

ACP answers the agent-surface checkout question, with the merchant still as merchant of record. UCP answers the merchant-system question, preserving merchant control across the full commerce journey. AP2 answers the delegated-authorization question. Visa, Mastercard, and PayPal answer through network trust, tokenized credentials, and dispute infrastructure. Coinbase, x402, Stripe MPP, Circle, Tempo, Bridge, and Privy answer through wallet and settlement infrastructure. AWS answers through enterprise agent governance.

The market isn’t messy because too many people are inventing acronyms. It’s messy because the old purchase flow hid many responsibilities inside a single human action. Once that action is delegated to software, every hidden responsibility has to be named.

That’s uncomfortable for product teams, but it’s also useful. It forces a clarity that internet commerce mostly avoided. A company building agentic commerce has to define what it means by identity, permission, payment, settlement, merchant control, fraud, refunds, and liability. If it can’t define those terms, it isn’t ready to let agents transact.


## How to prepare your product for agentic commerce

The first decision is what kind of commerce the product actually supports.

A consumer shopping assistant is a different beast from an enterprise procurement agent. A merchant agent-readiness product is not the same as an agent wallet. A stablecoin payment tool for API calls is not a retail checkout integration. A platform that lets agents buy inside a controlled marketplace is not an open protocol for the web.

This sounds basic, but ignoring it produces bad architecture. Most agentic commerce conversations blur retail shopping, B2B procurement, machine-to-machine payments, stablecoin settlement, and consumer wallets into one bucket. They share a word; they don’t share a risk model.

Retail needs product presentation, merchant trust, returns, customer service, taxes, shipping, fraud monitoring, and familiar payment protection. Machine-to-machine API payments need pricing, access control, metering, settlement, rate limits, wallet policy, and automated reconciliation. Enterprise procurement needs vendor approval, budget, compliance, spend authority, audit logs, and approval thresholds. Marketplace purchases need platform rules, seller identity, buyer protection, dispute handling, and data controls.

Once the use case is clear, the protocol decisions get easier.

**Merchants** should focus first on becoming usable by trusted agents without giving up the business itself. That means clean product data, current inventory, accurate pricing, explicit policies, callable checkout, order status, refund handling, customer support paths, fraud signals, and clear data terms. A merchant that exposes only a product feed isn’t agent-ready. A merchant that exposes the commercial path behind the product has a real shot.

**Agent builders** should treat payment authority as part of the core product, not as a late integration. The product needs to define what the agent can buy, from whom, under what budget, with which credential, after which approval, and with what record. The user has to be able to inspect and revoke that authority. A business has to be able to set policies by role, vendor, project, department, risk level, or transaction type.

**Payment companies and wallet providers** should focus on scoped authority. A safe agent payment credential shouldn’t behave like a raw card number handed to a bot. It should have limits. It should know, where possible, the merchant, amount, currency, time window, use case, user, or policy context. It should support refunds and disputes and produce evidence other systems can read later.

**Stablecoin and machine-payment builders** should be precise about their target market. The strongest near-term use case isn’t every consumer purchase. It’s software paying software, agents buying digital resources, companies assigning budgets to agents, and services charging for work below a monthly subscription. A real market. It isn’t replacing all of checkout.

**Enterprise teams** should focus on governance. If agents are going to spend company money, finance, security, procurement, and legal need a shared model. Which agents can spend? Who approved them? Which vendors are allowed? What’s the limit? What happens above it? Can the agent hold a balance? Can it use a card token? Can it use stablecoins? How are refunds handled? How is spend reconciled? What appears in the audit trail?

These aren’t administrative details. They’re the product.


## Claims to be careful with

**One protocol won’t win in the short term.** The protocols answer different questions. A retailer may need UCP for merchant-controlled commerce, ACP for ChatGPT transactions, AP2-style authorization for delegated consent, card tokens for consumer payment protection, and stablecoin rails for software services. Layered compatibility is more likely than a single universal standard.

**Checkout inside chat won’t kill merchant checkout.** Some purchases will happen inside agent surfaces. Others will route back to merchant-controlled flows. In many categories, the merchant’s site or app will remain important because the buyer needs detail, configuration, support, or brand context. The truer claim is that checkout becomes less tied to one surface: the merchant site stays important, but it’s no longer the only place commercial intent can turn into action.

**Stablecoins won’t replace cards.** Stablecoins matter, especially for machine payments and programmable settlement. Cards, wallets, and payment networks still carry consumer trust, merchant acceptance, fraud systems, and dispute processes. The likely future is mixed: different transaction types using different rails.

**Agents won’t buy fully autonomously.** Some low-risk transactions will become automatic. Many won’t. The higher the value, risk, irreversibility, or policy sensitivity, the more the system needs explicit authorization, review, or escalation. The right framing is *graduated autonomy*: agents act freely where risk is low, ask for approval where risk is moderate, and prepare evidence for humans where risk is high.

**Open protocols don’t automatically protect merchants.** Open protocols help, but control still depends on distribution, defaults, data access, ranking, customer identity, payment credentials, and governance. A merchant can stay merchant of record on paper and still lose influence over discovery and the customer relationship. Protocol terms matter, but so do the platforms where customers begin.


## The strategic read

Agentic commerce is forcing a reallocation of commercial responsibility that the old checkout page used to hide.

The old internet assumed a seller could pull a human into a controlled environment and persuade that person to complete a purchase. The agentic internet starts with the buyer’s intent somewhere else — in a chat, a workflow, a coding environment, a procurement system, a browser agent, or an enterprise automation platform. By the time the merchant sees the request, much of the decision has already been made.

That doesn’t make merchants powerless. It makes the job different: merchants need to express their business in forms agents can read and trust. Product data, pricing, terms, policies, availability, payment methods, refunds, support. All of it has to become more explicit. The merchant’s commercial reality has to travel outside the website.

It also doesn’t turn payment companies into invisible utilities. The opposite, really. Agentic commerce makes payment infrastructure more important because the system needs safe delegation. A human clicking a button is one kind of authorization. An agent acting later, under constraints, with a scoped credential, is a much more complex one. The companies that can define, enforce, and prove that authority will matter.

The strongest companies in this market won’t be the ones that build the prettiest shopping agent. They’ll be the ones that own a necessary responsibility layer. OpenAI has the surface where intent forms. Stripe has merchant and payment infrastructure. Shopify has the merchant operating system. Google has discovery, merchant data, and protocol ambition. PayPal has wallet trust and merchant reach. Visa and Mastercard have network rules, tokenization, and dispute infrastructure. Coinbase has stablecoin wallets and x402. Circle has stablecoin settlement credibility. AWS has the enterprise agent runtime. Amazon has platform commerce control.

Different strengths, all defensible. The single-winner story is weak.

The more useful question is which part of the purchase each company makes safer, easier, or more controllable when the buyer isn’t directly clicking through the old funnel.

This is the protocol war. Not a fight over a checkout button. It’s a fight over the rules that make a purchase valid when software is acting for the buyer.

The companies that understand this early won’t just ask “how do we let agents buy?” They’ll ask the harder questions: What exactly is the agent allowed to do? What evidence proves that? Which system owns the customer relationship? Which payment credential is safe enough? Which settlement rail fits the transaction? Who handles the refund? Who takes the fraud loss? What record survives after the agent finishes?

Those aren’t footnotes. They’re the new commercial architecture.

The old checkout page hid all of them behind a familiar human click. Agentic commerce brings them back into view.

[![](https://substackcdn.com/image/fetch/$s_!HTab!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8be3b75d-6a62-4aa6-9358-df28cc3660af_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!HTab!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8be3b75d-6a62-4aa6-9358-df28cc3660af_1024x1024.png)
