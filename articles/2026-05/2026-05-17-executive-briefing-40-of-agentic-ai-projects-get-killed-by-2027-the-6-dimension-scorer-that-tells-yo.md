---
title: "Executive Briefing: 40% of agentic AI projects get killed by 2027. The 6-dimension scorer that tells you which side you're on."
author: "Nate Jones"
published: 2026-05-17
url: https://natesnewsletter.substack.com/p/build-buy-hire-wait-ai-matrix
subtitle: "Watch now | Every serious AI conversation eventually turns into the same practical question."
audience: everyone
scraped_at: 2026-05-17 12:00:16
---

Every serious AI conversation eventually turns into the same practical question. Should we hire someone for this? Should we automate it? Should we buy a tool? Should we build the workflow ourselves? Or should we wait because the models are changing so fast that anything we build today may be obsolete in six months?

Most teams treat this as an AI question. That ends up costing time, money, and the work itself. It is a work-shape question. The right answer depends less on how impressive the model demo looked and more on the structure of the work in front of you: how often it repeats, how costly a mistake is, how much judgment it needs, and whether near-term model improvement is about to collapse what you are about to build.

Shopify gave the market one version of this question when Tobi Lütke told teams they had to show why they could not get something done with AI before asking for more headcount. It stopped hiring from being the default answer to every capacity problem. But “can AI do this?” is the wrong question to stop at.

Executives are running a capital allocation problem, not a technology question. How you allocate capital has always defined what a firm can accomplish, and the upside variance on AI investment right now is wider than most leaders have ever priced for. Pick the wrong motion for a workflow and the cost is not only the wasted spend. It is also the upside you never captured because the capital landed in the wrong place.

The wrong answer is expensive in both directions. If you hire against work that AI can already handle, you build a cost structure around disappearing scarcity. If you automate work that depends on trust and judgment, you break the business process at the point where the human mattered most. If you buy a generic tool for company-specific work, you spend months fighting the product. If you custom-build something the market has already solved, you burn scarce builders on infrastructure that should have been a line item. If you wait on a workflow that is already stable and costly, you let delay masquerade as prudence.

Gartner has put a number on it: more than 40% of agentic AI projects are forecast to be canceled by the end of 2027 because of cost, unclear business value, or inadequate risk controls. Classify the work before the spending starts.

**This briefing covers:**

- **The decision starts with the work.** A six-dimension scoring framework that routes each workflow to the right investment motion.
- **When to automate, build, buy, hire, or wait.** Real company examples (IBM, Klarna, Stripe) showing how the shape of the work determines the answer.
- **The matrix.** A two-axis visual that maps market maturity against company specificity, with named examples in every cell.
- **The executive job is changing.** Why routing logic is the new leadership skill, and what happens when executives and builders have the conversation together.
- **Four prompts that route AI investment.** A decomposer that turns a function into scoreable workflows, a scorer that writes the budget memo, a pressure test that forces three counter-arguments before capital commits, and a describability gate that holds automation projects until eight fields are filled.

Classify the work first. The investment motion follows.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

A read-only MCP server that gives your AI direct access to my entire published content library. You connect once, and then the archive just shows up inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Setup takes about ninety seconds.

- Register once at **[promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)**
- Enter your access code (executive\_circle) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

Your subscription now works inside your AI. Have fun!


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260512_399_promptkit_1)

Capital allocation mistakes in AI happen before the model ever enters the room. The team buys before they define the work, builds before they know if it’s differentiating, hires before they redesign the job, or automates a workflow they cannot describe in plain English. These four prompts close the gap between “we have an AI budget” and “we know where it should land.” The Workflow Decomposer breaks a function into scoreable units of work. The Six-Dimension Scorer produces a budget-memo paragraph an executive can paste into a planning doc. The Build-vs-Buy Pressure Test forces the three strongest objections to your team’s preferred motion before the money commits. The Describability Test refuses to let an automation project start until the workflow can survive eight specific fields. Run them in order. If a workflow cannot pass the Describability Test, the next investment is process discovery, not software.


## The decision starts with the work

Before you decide whether to hire, automate, buy, build, or wait, describe the work.

Not the department. Not the role. Not the software category. The work.

An accounts receivable team does not have one AI problem. It has collections prioritization, invoice matching, customer follow-up, exception handling, cash application, dispute resolution, reporting, and escalation. Those are different shapes of work.

A product team does not have one AI problem. It has user research synthesis, spec drafting, backlog grooming, design review, experiment analysis, roadmap judgment, launch coordination, and customer escalation. Those are different shapes of work.

A healthcare company does not have one AI problem. It has high-volume administrative transactions, clinical documentation, coding, prior authorization, audit workflows, clinician trust-building, regulatory interpretation, and evaluation design. Again, different shapes of work.

The unit of decision is not the job title. It is the workflow.

Once you get down to that level, the question becomes much easier. Every workflow can be scored across six dimensions: repetition, risk, judgment, company specificity, market maturity, and model-improvement risk.

Those six dimensions do more than help you think. They route the investment.


## When to automate work with AI

Automation is the right answer when the work repeats often, follows a clear pattern, has recognizable exceptions, and can be checked cheaply.

This is the part of AI adoption most people understand first, because the examples are obvious. [IBM’s internal AskHR system](https://www.ibm.com/case-studies/ibm-askhr) is a clean public case. IBM says AskHR handles routine HR inquiries and tasks across areas like payroll access, vacation requests, employee letters, and manager workflows, while human advisors handle more complex needs. IBM reports a 94% containment rate for common questions and a major reduction in support tickets. That is the right shape for automation: high-volume, recurring, policy-bound work where the system can answer routine cases and escalate the rest.

Klarna’s customer-service assistant is the more complicated version of the same lesson. In 2024, [Klarna said](https://www.klarna.com/international/press/klarna-ai-assistant-handles-two-thirds-of-customer-service-chats-in-its-first-month/) its OpenAI-powered assistant handled 2.3 million conversations in its first month, about two-thirds of its customer-service chats, and did the equivalent work of 700 full-time agents. That is a real automation result. But by 2025, [Klarna’s CEO was also talking publicly](https://techcrunch.com/2025/06/04/klarna-ceo-says-company-will-use-humans-to-offer-vip-customer-service/) about bringing humans back into customer service because two things can be true at the same time: AI can reduce costs and handle routine work, while customers still need human support in higher-trust moments.

Automation works best as a routing layer, not a religion.

If a customer asks where an order is, an AI system should probably answer. If a customer is angry, confused, high-value, dealing with a complicated refund, or stuck in a situation where policy and trust collide, the goal is not to prove the AI can handle it. The goal is to get the right kind of attention to the case.

The first rule: automate when the routine cases dominate and the exceptions are visible. Do not automate when the exception is the work.

Most bad enterprise AI demos fail at exactly this line. The vendor shows the routine case in the pitch deck and the buyer signs because the routine case looks impressive. Production traffic turns out to be mostly exceptions. Six months later the executive team is staring at an accuracy number nobody can defend and asking how the demo and the deployment ended up so far apart. Nobody was lied to. The buyer bought the wrong shape of work.


## When to build AI workflows in-house

The next category is the one most executives miss.

Some work should not be bought as a generic tool, and it should not be handed to a single human forever. It should become an internal workflow.

The work repeats in this zone, but the quality depends on company-specific context. It needs your data, your standards, your approval gates, your examples, your customer language, your risk thresholds, your source hierarchy, your team’s way of doing the job. It may still need humans, but the humans should not have to reconstruct the workflow every time.

This is where skills, agents, plugins, internal copilots, workflow builders, and MCP-connected systems matter. OpenAI’s Codex uses [skills](https://openai.com/academy/codex-plugins-and-skills/) — reusable instructions that teach the system how a person, team, or company does a task. Anthropic describes [Claude plugins](https://docs.claude.com/en/docs/claude-code/plugins) as reusable packages that can bundle skills, MCP connectors, commands, and sub-agents. The technical details vary. The pattern is the same: repeated work can be packaged.

A code review workflow is not just read the diff. It is a standard for what counts as a serious bug, where to look for risk, which tests matter, what comments deserve review capital, and how the team wants findings written.

A customer research workflow goes beyond summarizing transcripts. It is a standard for source coverage, uncertainty, customer evidence, product implications, and what not to include.

A board-reporting workflow goes beyond making slides. It is a standard for which metrics matter, how assumptions are handled, what decisions need to be surfaced, what confidence level is acceptable, and which claims require backup.

You buy generic software when the market has solved the problem. You build workflows when the problem is yours in a way that matters.

If you commission a build, your team will be motivated to come back and tell you it works. That opens up the harder questions. Do you know whether it works? Can you sit as the honest third party and say this is up to the standard, or this is unacceptable and needs another pass, or this was the wrong specification and we need to redefine what we are asking for? That level of clarity around what good output looks like is missing from most build conversations. The agentic capability has improved sharply over the last several months. The executive conversation around what counts as good has not kept up, and the gap is where most build budgets go to waste.

In a recent finance-operations conversation, the orders-to-cash question had this shape. The company did not need to hire a large team or build a giant custom platform first. A large part of that workflow was high-volume, low-complexity transaction handling. It had jargon, but the underlying shape was not mysterious. The better first move was to map the process, separate routine cases from exceptions, and build or buy a workflow that routed the routine work through AI-assisted automation while preserving human review for disputes, unusual customers, and policy-sensitive cases.

In a recent healthcare AI conversation, clinical evaluation had a different shape. If the work requires sitting next to clinicians, understanding how they reason from clinical data, building trust, and translating that into ground truth and eval frameworks, you are no longer dealing with routine automation. You are dealing with a workflow that has to encode expert judgment. That may deserve tooling, but the first investment is the human system that can define what the tool should measure.

The build-or-buy line lives here. If the standard is yours, you have to package it. If it is not, do not pretend it is.


## When to buy AI tools vs building

Buying is underrated in AI because everyone wants the custom thing.

That instinct is often wrong. If the problem is common, mature, non-differentiating, and already handled well by the market, you should buy it. Your internal builders should not spend their best hours recreating solved infrastructure.

This is especially true when the vendor owns a domain primitive that would be hard or risky to recreate. Payments are the clean example. Stripe’s [agentic commerce documentation](https://docs.stripe.com/agentic-commerce) describes shared payment tokens that let AI platforms pass scoped payment credentials and risk signals to businesses without exposing the underlying credentials. That amounts to a structured transaction primitive, not a feature. If you are building an agentic commerce workflow, you should be very careful before deciding that your differentiated work is rebuilding payment semantics, credential scoping, merchant risk, and settlement logic yourself.

You probably should not build your own commodity payroll system, basic identity system, or generic helpdesk when the work is standard. You probably should not build your own scheduling infrastructure unless scheduling is core to your product, or your own security scanner when mature tools already exist.

The strategic question is whether the layer is differentiating.

If the work is common and the market has a mature solution, buy it. If the work is common but the vendor category is still thin, buy carefully and avoid long lock-ins. If the work is company-specific and central to how you operate, buying may still be useful, but only as part of a workflow you own.


## When to hire for AI vs automate

Hiring is still the right answer more often than AI maximalists want to admit.

The mistake is hiring people to do routine work that should become a system. But the opposite mistake is just as dangerous: refusing to hire the person who can define, govern, and improve the system.

A lot of companies are now trying to find a single impossible hire: domain expert, AI builder, systems architect, operator, change leader, security thinker, product person, and executive translator. Sometimes that person exists. Usually the market clears more slowly than the business wants.

The better question is what kind of human capability the workflow actually needs.

If the missing piece is domain trust, workflow engineering, evaluation design, or executive ownership — hire for that. If the missing piece is a person who can sit between clinicians, engineers, compliance, and customers and make the work legible to all four groups, do not pretend a tool will solve that.

This came up clearly in a healthcare talent conversation I had recently. Some requirements were teachable. Industry codes, payer-provider mechanics, internal jargon. A strong AI-native operator could ramp quickly on a lot of that, especially with the right support. But other requirements went deeper than knowledge. Building trust with clinicians, understanding how clinical ground truth is created, and designing evals that clinicians will actually respect required prior exposure. Not because healthcare is magic. Because trust was part of the work.

That distinction matters for every industry.

If the work requires credibility in front of customers, regulators, clinicians, enterprise buyers, auditors, or a skeptical internal team, the human is not incidental. The human is part of the production system.

Shopify’s headcount rule is useful as pressure, but it should not become a blunt instrument. Can AI do this? is not enough. The better version is: what part of this role is routine execution, what part is judgment, what part is trust, what part is workflow ownership, and what part will disappear as tools mature?

Sometimes the answer is a split. Pair a domain expert with an AI-native builder. Pair an operator who understands the process with a workflow engineer who can package it. Pair a senior judgment owner with agents that remove the coordination work around them.

In practice, build and hire often happen in sequence rather than as competing choices. Hire the operator who can define the standard, then build the workflow around that standard, then automate the repeated parts. If you automate before the standard exists, the system simply scales confusion.


## When to wait

Waiting is not the same as doing nothing.

Waiting is the right answer when the tool category is immature, the workflow is not yet stable, the risk controls are not ready, or near-term model improvement is likely to commoditize the thing you are about to build.

This is especially true in agentic AI. [Gartner has warned](https://www.gartner.com/en/newsroom/press-releases/2025-06-25-gartner-predicts-over-40-percent-of-agentic-ai-projects-will-be-canceled-by-end-of-2027) that more than 40% of agentic AI projects may be canceled by the end of 2027 because of cost, unclear business value, or inadequate risk controls. Gartner’s [agentic AI hype cycle](https://www.gartner.com/en/articles/hype-cycle-for-agentic-ai) reinforces the maturity problem: most deployments remain narrowly scoped, and the supporting practices for governance, security, and cost management lag behind the enthusiasm.

That does not mean avoid agents. It means be precise.

If the workflow is routine, valuable, and measurable, move. If the workflow is vague, high-risk, and sold under a label that vendors themselves cannot define consistently, wait or run a narrow experiment. If the technology is changing monthly and the cost of being wrong is high, do not build a giant internal platform. Build the smallest learning loop that tells you when the category crosses your threshold.

Waiting is also right when the model is about to absorb the custom work. A year ago, a team might have built a custom summarization pipeline for internal documents. Today, much of that may be handled by stronger models with connectors, retrieval, and workspace context. A year from now, more of it will be native inside the tools people already use. If the work is generic and the models are rapidly improving into it, the right move may be to wait, prototype lightly, and avoid hardening a system whose main advantage is about to vanish.

But waiting becomes cowardice when the workflow is already stable and expensive. If a team spends five hours every week producing the same report from the same systems for the same audience, you do not need three more quarters of model progress to act. You need to describe the workflow.

The speed objection is legitimate. In a competitive market, being late can be more expensive than being wrong. But urgency is not the same as clarity. If the cost of delay exceeds the cost of a bad first version, move with a narrow learning loop. If the pressure is only that competitors are announcing things, the matrix is doing its job when it tells you to wait.


## Do not automate what you cannot describe

One line should sit above every AI investment review.

Do not automate what you cannot describe.

If you cannot describe the inputs, the output, the standard, the source of truth, the exception path, the error cost, the owner, and the review gate, then automation is premature.

Many AI projects fail at this point before the model ever enters the room. The team says it wants to automate customer onboarding, finance operations, research, compliance, sales follow-up, or reporting. But those words are too broad. They hide twenty workflows with different risk profiles.

A good automation candidate can be described in plain English.

Every Monday morning, read the last week of customer support tickets, group them by product area, deduplicate repeated issues, flag anything tied to a top account, and post a summary with links in the customer-success channel.

Describable.

For every incoming invoice from an approved vendor under a certain dollar threshold, match it against the purchase order and receipt, flag mismatches, and route clean cases for approval.

Describable.

Review all clinical notes for potential coding gaps, but only produce suggestions with evidence links and route anything uncertain to a qualified reviewer.

That is describable, though higher risk.

Make our back office AI-native is not describable. Automate finance is not describable. Replace customer support with agents is not describable.

If the workflow cannot be described, the next investment is process discovery, not automation.

Process discovery should be treated as its own investment, not as a failure to automate. Some work starts genuinely undescribed. In that case, the sequence is discover, then describe, then automate. Fund the discovery sprint, name the owner, map the exceptions, and decide what evidence would make the work describable enough for software.

The matrix is the artifact that keeps this from turning into taste or FOMO. The horizontal axis is how specific the work is to your company. The vertical axis is how mature the market solution is. The investment motion changes by cell.


## AI build vs buy decision matrix

[![A two-by-three decision matrix routing AI work by market maturity and company specificity.](https://substackcdn.com/image/fetch/$s_!Xlo8!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F08980800-0c3f-407a-9ac9-446e12b8421a_2048x1451.png "Build, Buy, Hire, or Wait Matrix")](https://substackcdn.com/image/fetch/$s_!Xlo8!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F08980800-0c3f-407a-9ac9-446e12b8421a_2048x1451.png)

The visual version is the whole point. It puts six common investment motions in one place: buy mature commodity work, buy primitives while owning company-specific workflow, prototype or wait where common categories are immature, build workflow where your standards are the product, wait where generic work is likely to be absorbed by base tools, and hire first where judgment or trust has to be defined before software can help.

Read the matrix this way. If the work is common and the market is mature, buy. If the work is common and the market is immature, prototype narrowly or wait. If the work is company-specific but the market has useful primitives, buy the primitives and own the workflow. If the work is company-specific and the market is thin, build the workflow. If the bottleneck is judgment, credibility, or trust, hire the person who can define the standard before you automate around it.

Hiring cuts across the grid. If the work resists framing, requires trust, or needs someone to define the standard before software can help, the next investment may be a person. If the work is already described and repeated, the next investment is usually a workflow, a vendor, or automation.

The named examples matter because they keep the cells honest. Buy looks like IBM AskHR for routine HR service or Stripe’s payment primitive for agentic commerce. Build-workflow looks like turning code review, customer research synthesis, or board reporting into a reusable internal playbook rather than asking a human to reinvent it each time. Hire looks like the healthcare evaluation case above, where the missing capability was not another tool but a person who could earn clinician trust and define ground truth. Wait looks like broad custom RAG pipelines or generic code-review-as-a-service tools when the base workspace products are rapidly absorbing the workflow.

For finance, ask which workflows are deterministic matching, which require exception handling, which require auditability, and which require a finance leader’s judgment.

For product management, ask which parts of the job are synthesis, coordination, customer interpretation, roadmap judgment, and organizational trust.

A much more useful conversation.


## The executive job is changing

The executive job in this world is to own the routing logic — not to personally evaluate every model and tool.

This cannot be delegated to any single function. IT alone misses the business judgment. The business alone misses the implementation path. Procurement alone cannot keep pace with the category. Developers alone miss the customer trust and organizational risk.

The right conversation has both sides at the table.

Executives need to define what outcomes matter, where human judgment must remain, which risks are acceptable, and where capital should go. Builders need to say what is actually buildable, what can be bought, what should be packaged as workflow infrastructure, what is too immature, and what will be easy in six months if the company does not panic-build today.

The worst AI strategies separate those conversations. The executive team buys the vision. The builders inherit the mess. Or the builders experiment locally. The executive team never changes the operating model. Both fail in different ways.

The companies that do this well will create a new habit: before money or headcount gets committed, the team classifies the work.

What repeats? What is risky? What requires judgment? What has the market already solved?

Then they choose the investment motion.

Use it in the next budget meeting. List the top five AI investments planned for the next two quarters. For each one, write one sentence describing the actual workflow, not the department and not the tool category. Score the workflow on the two axes: how specific is this work to us, and how mature is the market solution?

Then plot each investment on the matrix. Any investment that lands in a different cell than its proposed motion gets a hard re-examination before the budget closes. A custom build proposed for a commodity-mature problem should be challenged. A generic vendor proposed for a company-specific judgment workflow should be challenged. A hire proposed for routine repeated work should be challenged unless that person is there to define the system.


## The human work does not disappear

The cheap version of this conversation turns into AI versus people.

That is not the serious version.

The serious version says that people should stop spending their time on work that no longer needs human attention, and companies should stop pretending every human task has the same shape.

Some work should become software. Some should become an internal workflow. Some should become a vendor contract. Some should remain a human responsibility. Some should wait.

The human work that remains gets more important, not less. Someone has to define the standard and know when the output is wrong. Someone has to build trust with the customer, clinician, regulator, partner, or employee. Someone has to decide which risks are worth taking, maintain the workflow as the business changes, and notice when the agent is optimizing for the wrong thing. Someone has to decide what the company is trying to become.

The firm is being forced to admit which work actually needed people in the first place.

A lot of companies will get this wrong. They will cut before they understand. They will buy before they define. They will hire before they redesign the work. They will automate what they cannot describe.

The better companies will be more specific.

They will look at the work directly and route it. They will keep humans where humans are load-bearing and use AI where repetition, scale, and consistency matter. They will buy solved primitives, build workflows around their own context, and wait where the market is still lying to itself.

That is the practical AI strategy most teams need.

Not a grand theory of the future of work. A matrix for the decision in front of them.

[![](https://substackcdn.com/image/fetch/$s_!xQuX!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5ba3d118-fa6a-4f02-800c-7e535d181ee8_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!xQuX!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5ba3d118-fa6a-4f02-800c-7e535d181ee8_1024x1024.png)
