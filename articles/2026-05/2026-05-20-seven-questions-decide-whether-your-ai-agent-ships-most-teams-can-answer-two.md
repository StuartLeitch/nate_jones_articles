---
title: "Seven questions decide whether your AI agent ships. Most teams can answer two."
author: "Nate Jones"
published: 2026-05-20
url: https://natesnewsletter.substack.com/p/agent-infrastructure-control-layer
subtitle: "Watch now | The model is one piece of the agent economy. The control layer is the other, and most proposals on a CIO's desk have no answer for it."
audience: everyone
scraped_at: 2026-05-20 12:00:20
---

A new class of company has taken up position around the agent economy, and they are the ones who decide whether your agent gets to ship. They do not build models. They are not on most teams’ AI stack roadmap. But every serious production agent has to pass through them, and most agent proposals on a CIO’s desk right now have no answer for what those companies are about to ask.

The model is one piece of the agent economy. The control layer is the other.

The control layer is the set of infrastructure decisions that determine whether a model’s output is allowed to act in the world. Where does the agent live. What state does it remember. Who is it acting for. When does it need approval. What can it spend. Who can stop it. None of those questions get answered by a model. They get answered by the companies sitting between the model and your production system, and the last six weeks have made it obvious who they are. Cloudflare ran Agents Week. Stripe expanded its Agentic Commerce Suite. Okta launched Okta for AI Agents and expanded it again this month. Auth0 has been publishing AI Agents docs. Datadog has been turning LLM observability into something that looks a lot more like an agent control plane than a logging product.

I’ve covered the protocol stack already — [the six protocols that emerged and the three that decide which agents survive](https://natesnewsletter.substack.com/p/agent-protocol-stack-mcp-a2a). This piece is about the operators sitting above the protocols. The companies turning agentic behavior into controlled, permissioned, auditable infrastructure. The companies your security review is about to discover the hard way.

**Here’s what’s inside:**

- **The seven-row control map** I would put in front of any agent proposal before it touches a production system, and the one question per row that flushes out the gap.
- **Why Cloudflare, Auth0, Snowflake, Stripe, and Datadog** are becoming the operating system of the agent economy, and what each one is actually trying to own.
- **The kill switch most teams do not actually have**, even though they think they do — and the five layers it has to be implemented at to be real.
- **A real data leader’s failure mode**, live this quarter: her agents are routing around the human permission structure, and she now owns three questions she did not yet know how to answer.
- **The three prompts paid subscribers get this week.** A control-map fill-in for the agent your team is most likely to ship this quarter, a pressure-test for the next vendor pitch on your desk, and a five-layer kill-switch audit for the agent that actually scared you.

The boring layer is where the power is moving. Let me walk you through the map.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260512_v6e_promptkit_1)

The seven rows of the control map are not theoretical. They are the questions your security review, your CFO, your data leader, and your incident postmortem will eventually ask. These three prompts close the distance between an agent proposal that demos well and an agent that survives a real production rollout. The first walks one of your actual workflows through all seven rows and tells you which row will fail first. The second runs a vendor pitch or internal proposal through the same lens — what the pitch answers, what it dodges, and what each dodge will cost. The third is for the moment in the kill-switch section where you noticed your current stop button only works if the agent agrees to stop. None of these are generic strategy prompts. Each one ends with a filled-in artifact you can hand to a specific owner and act on this week.


## Compute is not control

Compute is necessary. It is not sufficient.

A model can generate a plan. It cannot, by itself, decide whether the plan is allowed. It can infer what a user might want. It cannot prove that the user authorized a purchase. It can ask to query a database. It cannot know which rows the user is entitled to see. It can draft an email, but whether sending that email creates a legal or customer obligation is not a question the model is positioned to answer.

The gap is between intelligence and work.

The first phase of the AI boom rewarded model access. Who had the best model? Who had the cheapest inference? Who had the context window, the multimodality, the reasoning score, the coding benchmark, the agent demo?

The next phase rewards controlled agency.

Controlled agency is the ability to let software act in the world without turning every action into a human supervision tax. It requires a runtime with state, governed data, identity and delegated authorization, commercial authority if money is involved, and observability with a real kill switch.

That is the control layer.

The infrastructure story is changing. The hyperscaler may provide the raw compute. The model lab may provide the reasoning engine. But the company that owns the control layer can decide whether the agent is usable in production.


## The runtime control point: Cloudflare

Cloudflare is interesting because it is not trying to win the model war in the obvious way. It is trying to become a place where agents can run.

Cloudflare’s [Agents SDK documentation](https://developers.cloudflare.com/agents/) is unusually revealing. It says real agents need to remember conversations, act on schedules, call tools, coordinate with other agents, and stay connected to users in real time. Each agent runs on a Durable Object: a stateful micro-server with its own SQL database, WebSocket connections, and scheduling. The agent can use tools, serve tools through MCP, schedule tasks, run workflows, coordinate with sub-agents, browse the web, talk to users, and react to events.

Hosting with memory, execution, and coordination built in. An agent runtime.

The control point is state plus execution. If agents are long-running workers rather than stateless chat completions, then the runtime matters much more than it did for ordinary web apps. An agent needs to wake up later, remember what happened, continue a stream after disconnect, accept a human approval, run a scheduled task, call a tool, retry a workflow, or stop when a policy says stop.

Cloudflare sits in a strategically useful place for that. It already lives close to traffic. It sells global infrastructure, security, workers, stateful objects, gateways, and edge execution. Agent workloads need exactly the kind of infrastructure that makes “where does this run?” less separate from “how is this controlled?”

Cloudflare is not the only company trying to occupy that runtime position. AWS has made the same control-layer claim inside its own cloud with [Amazon Bedrock AgentCore](https://aws.amazon.com/blogs/aws/introducing-amazon-bedrock-agentcore-securely-deploy-and-operate-ai-agents-at-any-scale/), which packages runtime, memory, identity, gateway, browser, code interpreter, and observability services. Vercel is coming from another angle with [AI Gateway](https://vercel.com/docs/ai-gateway/), where the control point is model routing, budgets, monitoring, load balancing, and fallback across providers. Runtime control is splitting into several operator jobs: where the agent runs, how state persists, how tools are mediated, and how failures are observed.

The x402 work makes the point even clearer. Cloudflare’s [x402 docs](https://developers.cloudflare.com/agents/agentic-payments/x402/) describe a flow where a service can respond with 402 Payment Required, the client signs a payment payload, the server verifies or settles the transaction, and the resource is returned. The same docs describe charging for HTTP content and MCP tools. That is a runtime company moving into machine-native economic coordination.

Control surfaces compound. If Cloudflare runs the agent, mediates the connection, exposes or protects the tool, observes the request, and helps charge for the resource, it moves from infrastructure beneath the product into the product’s operating system.

The practical implication for builders is that agent runtime should not be an afterthought. If your agent has durable work, deadlines, callbacks, streaming UI, tools, approvals, payments, or state, the runtime is a strategic choice. A stateless API wrapper is not an agent platform. It is a demo path.


## The identity control point: Auth0 and Okta

Identity becomes much harder when software acts on behalf of people.

In the ordinary SaaS world, identity mostly meant authenticating a human user and authorizing that user against application resources. In the agent world, that is not enough. The agent may be acting for a user, for a team, for a company, or for another agent. It may need to call Google, Slack, GitHub, Salesforce, or internal APIs. It may need to request approval while the user is away. It may need to retrieve documents for a RAG pipeline but only those the user is allowed to see.

Auth0’s [AI Agents documentation](https://auth0.com/ai/docs/intro/overview) is worth reading as strategy rather than product docs alone. Auth0 is explicitly packaging user authentication, OAuth-based API access, Token Vault, asynchronous authorization, and fine-grained authorization for RAG. The key phrase is not “login for agents.” The key idea is delegated authority with constraints.

An agent should not get a broad, permanent credential because a user once signed in. It should call APIs on behalf of a user, however token storage should be opaque to the agent itself. Consent should be required for sensitive or long-running operations, and document retrieval should respect what the user is allowed to see.

That becomes a control layer because enterprises will not deploy serious agents without it.

The most dangerous agent in a company is not necessarily the most capable one. It is the one with fuzzy authority. It has access to a user’s calendar, email, files, CRM, source code, and internal documents, but nobody can clearly say whether it is acting as the user, as the company, as an application, or as itself. The persistence of that permission is unclear. So is whether the approval covers this action or a broader class of actions, and whether the agent can pass data to another agent.

That ambiguity is manageable when agents draft text. It is not manageable when agents transact, deploy, refund, schedule, provision, or make commitments.

Okta’s broader enterprise agent-security push points in the same direction. So does WorkOS, which has been explicit about giving [AI agents their own scoped credentials](https://workos.com/blog/ai-agent-credentials) and about its partnership around [Microsoft Entra Agent ID](https://workos.com/blog/workos-partners-with-entra-agent-id). AWS is making the same move inside AgentCore Identity. The identity providers understand that AI agents are becoming identity-bearing actors. The company that can register them, scope them, authorize them, revoke them, and audit them has a real control position.

The builder implication is blunt: every serious agent product needs an authority model. A login is only one piece of that model. Who is the principal, what can be delegated, what can be revoked, and what does the audit log show. If those questions are not answered, the agent will hit a ceiling in any enterprise environment that actually reviews what it deploys.


## The data control point: Snowflake

Agents are only as useful as the data they can safely interpret.

Snowflake’s agent strategy becomes more than “AI on data” at this point. Snowflake’s [Cortex Agents documentation](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents) describes agents that orchestrate across structured and unstructured data, plan tasks, use Cortex Analyst for structured data, use Cortex Search for unstructured data, and select the right tool to ensure governed access and compliance with enterprise policies.

That is a mouthful, but the strategic point is simple: the agent needs more than data access. It needs governed meaning.

Data warehouses and data clouds became important because they became places where organizations tried to create a reliable version of business truth. Revenue. Customers. Inventory. Usage. Churn. Margin. Forecast. Territory. Support volume. Claims. Risk. Supply. The numbers matter because decisions move around them.

Agents make that semantic layer more important, not less.

A generic agent can query data badly. It can join the wrong tables, trust the wrong column, misunderstand a metric, retrieve stale documents, answer confidently from ungoverned context, or present an assumption as a fact. That is not a model problem alone. It is a data control problem.

Snowflake’s position is that the agent should operate inside the governed perimeter of enterprise data — routing between structured and unstructured sources through tools that understand the environment, using semantic models, semantic views, Cortex Search, Cortex Analyst, and custom tools, and respecting the roles, policies, and existing governance the company already enforces.

That makes Snowflake a control-layer company because it can answer a question model providers cannot answer from the outside: what does this business object mean inside this company?

Databricks is making the parallel argument from the lakehouse side. Its [Mosaic AI Agent Framework](https://www.databricks.com/product/artificial-intelligence/mosaic-ai-agent-framework) is about building, deploying, evaluating, and monitoring agents inside the same governed environment where enterprise data and ML workflows already live. BigQuery and Gemini represent the hyperscaler-native version of the same move. These companies are doing more than adding chat to databases. They are trying to make the governed data platform the place where agents are allowed to reason and act.

What is ARR? Which customer hierarchy is authoritative? Which data is restricted? Which answer can be trusted?

In the agent economy, the semantic layer is not reporting infrastructure. It is action infrastructure. An agent that cannot tell current revenue from forecast revenue should not be allowed to draft the board narrative. An agent that cannot distinguish an approved supplier from a prospect should not be allowed to place an order. An agent that cannot tell public documentation from confidential customer commitments should not answer support questions directly.

The data platform that owns the governed meaning of the business owns a large part of the agent’s operating boundary.


## The payment control point: Stripe and the networks

The moment an agent touches money, the control problem becomes unavoidable.

Stripe’s agentic commerce work is strategically deeper than “agents can buy things.” Stripe’s [agentic commerce documentation](https://docs.stripe.com/agentic-commerce) separates seller flows, agent flows, product catalogs, shared payment credentials, and machine payments. It also distinguishes commerce protocols such as UCP or ACP from machine-payment protocols such as MPP or x402.

That separation matters because agent payments are not one job. A human may want an agent to buy from a merchant. A machine may want to pay for an API, data source, or tool call. A seller may need fraud protection because a bot and a legitimate buyer’s agent can look similar. A wallet may need to pass payment credentials without exposing raw credentials to the agent.

Stripe already lives at the intersection of payment credentials, merchant onboarding, fraud, billing, subscriptions, issuing, treasury, disputes, risk, and developer APIs. Agents make that intersection more valuable.

But Stripe is not alone. The card networks are moving because they understand the same control point.

Mastercard’s [Agent Pay announcement](https://www.mastercard.com/us/en/news-and-trends/press/2025/april/mastercard-unveils-agent-pay-pioneering-agentic-payments-technology-to-power-commerce-in-the-age-of-ai.html) introduced Mastercard Agentic Tokens, building on tokenization systems already used in mobile contactless payments, card-on-file, Payment Passkeys, recurring expenses, and subscriptions. The strategic phrase is that agentic transactions need trust, security, and control.

Visa says its [Intelligent Commerce](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.21961.html) work has already produced controlled, real-world agent-initiated transactions with partners, including consumer and B2B pilots. American Express describes its [Agentic Commerce Experiences developer kit](https://www.americanexpress.com/en-us/company/agentic-commerce/) as a suite of services for agent registration, account enablement, intent intelligence, payment credentials, and cart context.

Adyen, PayPal, Worldpay, Coinbase, and others show up in Google’s AP2 partner list for the same reason. Payment processors, wallets, risk systems, networks, and merchant infrastructure companies all see the same bottleneck: the agent can only spend at scale if the system can prove intent, preserve credentials, route payment, manage fraud, and resolve disputes.

Those are payment features, but more importantly, they are control claims.

The networks are saying: if agents are going to spend money, the payments ecosystem has to recognize legitimate agents, validate intent, protect credentials, preserve dispute rights, manage fraud, and keep issuers, merchants, and consumers inside a trusted system.

That is the right instinct. Agentic commerce will not scale because a model learns to click checkout. It will scale when the payment ecosystem can tell the difference between an authorized agent, a malicious bot, a mistaken purchase, a changed cart, a delegated budget, a merchant-specific token, and a disputed transaction.

Payment moves money, but its strategic role is institutional trust.

The company that owns that trust owns one of the most important control points in the agent economy.


## The hidden control layer is observation

Runtime, identity, data, and payment are the obvious control surfaces. The hidden one is observation.

Agents will fail differently from ordinary software. They may call the wrong tool with valid syntax, ask the right agent the wrong question, or retrieve authorized data and still draw the wrong conclusion. A run may complete the task technically while violating the user’s intent, stay inside permission boundaries while creating an expensive loop, keep retrying when it should escalate, or escalate too late when it should have stopped. Most dangerously, an agent can succeed in the tool layer and fail in the business layer — every API call green, every outcome wrong.

That means logs are not enough.

Companies need to observe agent runs as work rather than plain API traffic. What was the goal? Which tools were called? Who authorized the action? Which data sources were used? Which policy blocked the action? Which cost was incurred? Did a human accept the result?

This is where infrastructure companies can quietly gain power. Datadog’s [LLM Observability](https://www.datadoghq.com/product/ai/llm-observability/) is built around tracing prompts, responses, retrieval steps, and tool calls, then correlating that behavior with backend services, infrastructure, and user sessions. LangSmith’s [observability and evals platform](https://www.langchain.com/langsmith-platform) is closer to the developer and agent-framework layer, with traces and evaluations tied to LangChain and LangGraph workflows. [Braintrust](https://www.braintrust.dev/) and [Langfuse](https://langfuse.com/docs/) make different operator bets: evals-first quality control in one case, open-source tracing, prompt management, and evaluations in the other.

AWS is also making the integration point explicit. AgentCore Observability supports OpenTelemetry and can send agent telemetry into CloudWatch, Datadog, LangSmith, and Langfuse. That is the shape of the market: agent observability will not be one dashboard. It will be a control plane that connects traces, cost, tool calls, evals, security events, and business outcomes.

A gateway that sees model calls, routes providers, applies rate limits, caches responses, logs usage, and enforces policies becomes the place where agent behavior is made legible. Cost savings are a side effect. Control is the product. A payment processor that sees fraud and transaction patterns across merchants can distinguish good agents from bad automation. An identity provider that sees delegated authorization flows can govern who can act through whom.

The agent economy needs dashboards, but not in the shallow sense. It needs control surfaces that answer operational questions: where the agents are, what they have access to, what they cost, which actions are blocked, and which ones should be shut off.

That last question is underrated. The kill switch belongs in the product spec, not the principles deck.

It should be implemented at more than one layer. A runtime can cancel or pause the run. An identity system can revoke the credential. A gateway can block the tool call. A payment system can freeze the instrument or spending limit. A graph-based agent framework such as LangGraph can interrupt a workflow before a sensitive node. If the only kill switch is “tell the model to stop,” the kill switch is not real.


## The strongest objection

The strongest objection to this argument is that hyperscalers still own the real advantage.

They own the clouds. They own the model distribution. They own developer platforms. They own data centers. They own the enterprise contracts. They are integrating agents directly into productivity suites, cloud consoles, databases, security products, and app platforms.

That is true.

The harder version of the objection is that hyperscalers already own their own control layers. Microsoft has Entra, Azure, GitHub, Teams, Copilot, and security telemetry. AWS has IAM, Bedrock, AgentCore, CloudWatch, and the customer workloads themselves. Google has Cloud IAM, BigQuery, Gemini, Workspace, Chrome, A2A, A2UI, and AP2. If the control layer is runtime, identity, data, payment, and observability, the hyperscalers are rebuilding it inside their own clouds.

But it does not eliminate the control-layer thesis. It makes it more important.

Hyperscalers will own a lot of the agent economy because they own a lot of the existing enterprise environment. Microsoft can push agents through Office, Azure, GitHub, Teams, Copilot, and Entra. Google can push through Gemini, Workspace, Cloud, Android, Chrome, A2A, A2UI, and AP2. Amazon can push through AWS, Bedrock, marketplaces, fulfillment, and the operational backbone of the internet economy.

But agents do not live inside one vendor’s boundary forever. The more useful the agent, the more tools, clouds, apps, merchants, APIs, documents, databases, and payment systems it crosses. A company may run workloads on AWS, sell through Shopify, bill through Stripe, store customer data in Snowflake, authenticate through Okta, observe production in Datadog, and let employees use ChatGPT, Claude, Gemini, and Copilot. A control layer that only works inside one hyperscaler is powerful, but incomplete.

There is a second objection: the model labs are moving down the stack too. OpenAI’s [Responses API](https://platform.openai.com/docs/guides/responses-vs-chat-completions?api-mode=responses.html) is agentic by default, with hosted tools and remote MCP support. Anthropic has pushed Claude toward [skills, computer use, Cowork, Claude Code, and MCP support](https://support.claude.com/en/articles/12138966-release-notes). The model provider wants to become the runtime because it can make the model feel more capable when the surrounding tools, state, and workflows are native. That is the most predictable move in the market.

It still does not erase the infrastructure layer. It makes the buying question sharper. Use the model-native runtime when speed, model fit, and product simplicity matter most. Use cross-model, cross-cloud infrastructure when portability, governance, procurement, security review, or vendor risk matter more. Most serious companies will end up with both.

The last objection is lock-in. If Cloudflare runs the agent, Datadog is the only place where behavior is legible, or Stripe becomes the default commerce authority, each control layer becomes a new dependency. The mitigation is architectural: keep the runtime portable where possible, bring your own identity provider, export telemetry to a second sink, separate payment intent from payment rail, and keep audit logs in a system the business controls.

Who authenticates?

Who authorizes?

Who carries the token?

Who validates the payment?

Who observes the run?

Who can stop the agent?

Those questions create openings for infrastructure companies outside the model race. Not because they beat the hyperscalers at compute, but because they sit at unavoidable points of institutional trust.

The model produces intelligence. The control layer turns intelligence into allowed work.

Here is what that looks like in a concrete stack.

Imagine a renewal-quote agent at a regulated B2B software company. The runtime is Cloudflare Workers with Durable Objects for state, or Bedrock AgentCore if the company is standardized on AWS. Auth0, Okta, Entra, or WorkOS handles delegated identity. Snowflake or Databricks owns the governed customer-data layer. Stripe or Adyen handles quote-attached payment credentials and billing events. Datadog, LangSmith, Braintrust, or Langfuse observes the run. A production agent quickly becomes a map of control responsibilities across multiple operators.

That is why the vendor distinction matters. Cloudflare is a runtime and network-control operator. AWS is the hyperscaler-native runtime operator. Auth0, Okta, Entra, and WorkOS are authority operators. Snowflake and Databricks are governed-data operators. Stripe, Adyen, PayPal, Visa, Mastercard, and American Express are economic-trust operators. Datadog, LangSmith, Braintrust, and Langfuse are observability and evaluation operators. The model lab is one operator in that map. It is not the whole map.


## The agent control layer map

Use this table before approving an agent deployment with any AI product, vendor, or internal agent proposal.

[![](https://substackcdn.com/image/fetch/$s_!-xKE!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F857e97a5-660d-4b89-92a5-f62f83a35f7e_1168x732.png)](https://substackcdn.com/image/fetch/$s_!-xKE!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F857e97a5-660d-4b89-92a5-f62f83a35f7e_1168x732.png)

Most agent proposals are over-specified on model and under-specified on control. They will tell you which model they use, how many tools they can call, and how impressive the demo looks. They will not tell you who owns the approval path, where the agent’s authority expires, whether the payment credential is scoped, whether the data retrieval respects row-level access, whether the workflow can be paused, or who can reconstruct the run after something goes wrong.

That is backwards.

For a toy agent, model quality is the question. For a production agent, control architecture is the question.


## What to do this week

Block 60 minutes this week and pick one agent workflow your team is actually likely to ship this quarter. Not your entire AI strategy. One workflow.

For example: a sales agent preparing renewal recommendations, a finance agent analyzing monthly variance, a procurement agent comparing suppliers, a support agent drafting refunds, a coding agent provisioning infrastructure, or a marketing agent buying data and producing a brief.

Fill out the seven rows of the control map for that one workflow. Keep the exercise concrete:

- Where does the agent run?
- Which data is governed?
- Who is the principal?
- Which actions are read-only, draft-only, approval-required, or autonomous?
- What can it spend?
- Which events are logged?
- Who can shut it off?

If any row says “TBD” or “we will figure it out later,” that is the row where the agent will fail in production.

The next step is not necessarily to buy more tools. It is to assign ownership. Take the weakest row to its owner. Runtime to the platform or infrastructure leader. Identity to security. Data governance to the data leader. Payments to finance or the payments owner. Observability to engineering and operations. The question is simple: who owns this Monday morning?

Many companies will stumble here. They will treat agents as a product or productivity initiative and discover too late that agents are a cross-functional infrastructure problem. The CIO, CISO, CFO, data leader, product leader, and business owner all have part of the control surface.

Agents do not respect org charts. Your governance model has to compensate.

I was talking recently with a data leader who told me her agents had started routing around her existing permission structure, which had been designed for humans. A run would complete successfully, and she would be left with three questions she did not yet know how to answer. Was the agent allowed to work around the permission layer to get the job done? Did the human end up seeing data they should not have? Was the original permission structure simply wrong for this kind of work in the first place? There is no neutral answer to any of those. Each one is a decision someone has to own. That is the shape of the control problem when it actually shows up: not at the demo, at the post-mortem.


## Where control concentrates

Cloudflare, AWS, and Vercel are turning runtime, state, gateways, model routing, and machine payments into agent platform infrastructure. Auth0, Okta, Entra, and WorkOS are turning delegated identity and authorization into an agent safety layer. Snowflake and Databricks are turning governed enterprise data and semantic models into an agent action layer. Stripe, Adyen, PayPal, and the payment networks are turning payment credentials, fraud, mandates, tokenization, and settlement into agentic commerce infrastructure. Datadog, LangSmith, Braintrust, and Langfuse are turning traces, evals, cost, and tool behavior into the observation layer production agents require.

These companies may not all win equally. Some products will be early. Some standards will be replaced. Some protocols will fragment. Some demos will be ahead of customer readiness. That is normal.

The direction is what matters.

The model is not the whole product. The browser is not the whole product. The chatbot is not the whole product. The real product is the system that lets intelligence act inside boundaries a company can trust.

That system needs somewhere to run, something true to know, someone to act for, authority to touch the world, and a record of what happened.

That is infrastructure.

And in the agent economy, infrastructure is the control layer.

[![](https://substackcdn.com/image/fetch/$s_!W9oW!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8db0e815-0c67-48b0-abee-0f9811dffa6c_1254x1254.png)](https://substackcdn.com/image/fetch/$s_!W9oW!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8db0e815-0c67-48b0-abee-0f9811dffa6c_1254x1254.png)
