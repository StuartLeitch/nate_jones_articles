---
title: "Executive Briefing: Uber Burned Its Entire AI Budget Early. The Bill Was Trying to Tell Them Something."
author: "Nate Jones"
published: 2026-06-07
url: https://natesnewsletter.substack.com/p/ai-token-cost-management
subtitle: "Watch now | Token burn is more than a budget problem. It;s what happens when frontier intelligence gets useful, open models get good, and companies try to manage agentic work with 2025 controls."
audience: everyone
scraped_at: 2026-06-08 09:00:12
---

The next AI budget fight will not start because employees refuse to use AI.

It will start because they finally do.

This is why the date matters. This is a June 2026 problem, not a December 2025 problem.

In May 2026, Uber became one of the first big companies to make the new problem concrete: 95% of its engineers now use AI tools every month, most of them in agent-style workflows, and an internal coding agent writes roughly 1,800 code changes a week. Uber was not playing with chatbots. It was doing exactly what every board has been demanding: get serious about AI, put the tools into real workflows, find the leverage.

Then the cost story broke. Uber’s CTO, Praveen Neppalli Naga, reportedly told people the company had blown through its entire 2026 AI budget months early. The easy read was that the tools cost too much and employees need reining in.

I think that read is incomplete. The sharper signal came from Uber’s president and COO, Andrew Macdonald, who said the company can see the usage, the commits, and the token spend, and still cannot cleanly connect any of it to better features for customers.

That is the real story, and it is bigger than Uber. The bill is the first hard evidence that AI has crossed from a tool you buy into labor you have to manage, and almost no company has built a system to manage labor it cannot see. Read correctly, token burn is not waste but information about a kind of work the company has not learned to run yet.

Where you sit decides what the bill threatens. If you own the budget, it becomes the line item that justifies a layoff you did not want to make. If you run engineering, it becomes the cap that kills the experiments that were working. If you do the work, it turns “used too much AI” into a performance problem instead of a signal that you found a job worth automating. Same invoice, three warnings, one missing system.

The companies that win this will not be the ones that spent the least or the most. Spending freely and capping hard are both easy, and both are wrong. The harder answer is the one in between, and the rest of this briefing is how you get there.

This briefing covers:

- **The real shape of the AI cost curve.** Why the work you actually want from frontier models keeps getting more expensive even as the price per call falls, and what that does to next year’s budget.
- **A routing rule for every AI dollar.** One principle, minimum effective intelligence, for deciding when a job needs a frontier model, an open model, or no model at all.
- **Why your 2025 budget model is the thing breaking.** Seats and licenses cannot price work that plans, retries, and runs for hours, and a better dashboard will not save it.
- **The operating model that replaces the token cap.** What an agent-first company actually changes: work objects, gates, permissions, and the training that turns usage into compounding advantage.
- **How to read your own token bill.** A way to tell production from tuition from waste from the signal that you just found a workflow worth turning into infrastructure.

The argument runs in seven parts, and it ends somewhere you can use: an operating model and a routing rule you can take into your next budget conversation. The setup is free. The system is below.

*If you experience issues with the MCP Server or joining Slack, please email **support@natebjones.com** for help and we’ll get you sorted within 48 hours of your request.*


## ***[LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)]***

- **Access code:** executive\_circle
- **Link:** [promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)

A read-only MCP server that gives your AI direct access to my entire published content library. Connect once, and then the archive just shows up inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Setup takes about ninety seconds.

- Register once at **[promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)**
- Enter your access code (**executive\_circle**) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

Your subscription now works inside your AI. Have fun!


## ***[LINK: [Join the Slack →](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)]***

[The Slack community is live](https://join.slack.com/t/natescommunity/shared_invite/zt-3zuf3g71w-eN~CyZF_p6_grlOSkK8sLA)! It’s where I’ll be sharing things between articles, where you can get help on builds in real time, and where the fastest conversations in this community are already happening. I’ll see you in there!


## ***[LINK: [Grab the prompts](https://promptkit.natebjones.com/20260526_533_promptkit_1)]***

Before the argument, the tools. These four are the ones I built to run this exact analysis on a real bill, and each ends in something you can put on a table, not a page of advice. The first reads your spend the way a controller reads a P&L: work you accepted, learning you paid for, waste you can route out, and patterns worth building into infrastructure. From there, the router forces a deliberate call on your most expensive workflows, so nothing rides a frontier model out of habit. The readiness diagnostic takes one business loop and tells you whether your systems and your people can actually carry agentic work, or whether more budget would just buy speed the loop can’t absorb. And the capstone folds all of it into a one-page brief you can defend in the budget meeting itself. All four refuse to invent numbers, ask for what they need before answering, and push back when your own data says they should. Paste them as they are. Bring a real invoice and a real workflow, and they get sharper.

---

Those tools assume something the rest of this briefing has to earn: that the bill in front of you is not an overspend to apologize for, but a readout of work your company started doing before it built the system to run it. Spend rose because intelligence got useful enough to take on real labor, and the labor arrived before the operating model did. The case for reading it that way, and for the routing rule and operating model the tools apply, breaks into seven parts:

1. Frontier intelligence is not settling into ordinary software economics. For the work leaders actually want from the best models, the effective cost is going up, not down.
2. Open models are getting good enough to matter. Free, open-weight, local, and cheaper hosted models are becoming useful for real work, which changes the enterprise routing problem.
3. Models have crossed the threshold where they can carry business-shaped work, but only when the work is routed, controlled, reviewed, and made legible.
4. Most businesses do not have those controls. They are still budgeting from a 2025 mental model, when models were cheaper in practice and much less capable.
5. This is exactly what we should expect in an exponential world. Humans are bad at extrapolating from capability curves, so usage rises faster than understanding.
6. The way forward is not simply tighter budgets. It is an agent-first operating model, technical systems where agents can thrive, routing based on minimum effective intelligence, and a workforce trained to supervise agentic work.
7. Most companies are not doing that yet. They are stuck in old budgets, old workflows, architectures that can be hostile to agents, and blunt token controls that suppress learning instead of building leverage.

That is why token burn is becoming a leadership issue.


## Frontier models aren’t getting cheaper where it counts

The first mistake is assuming the AI cost curve will behave like the software cost curve.

Software trained leaders to expect marginal costs to fall toward zero. Once the product exists, another user, another document, another dashboard, another transaction often feels cheap. There are real infrastructure costs underneath, but the management habit is clear: software scales by spreading fixed costs across more usage.

Frontier AI is different because the thing being consumed is not just software. It is compute, memory bandwidth, accelerators, networking, power, cooling, data-center capacity, inference engineering, and scarce frontier-model serving capacity. The interface looks like software. The constraint is increasingly industrial, and so is the volume: serious deployments are moving past experimental usage into trillion-token and ten-trillion-token operating territory.

Public price cards can move down. Caching can improve. Inference systems can get better. Providers can compete. I do not want to make the sloppy claim that every individual model call will always get more expensive. Some calls will get cheaper. Some tasks will move to smaller models. Some expensive jobs will become ordinary automation.

But leaders should not confuse cheaper replies with cheaper accepted outcomes.

The work companies actually want from frontier models is getting longer, more context-heavy, more tool-heavy, more multimodal, more verified, and more consequential. A serious business run is not a paragraph. It may include source intake, retrieval, planning, tool calls, code execution, errors, retries, memory, review notes, provenance, and an artifact that has to survive a human decision. The company is no longer buying an answer. It is buying a slice of machine labor.

That is why the effective cost of frontier intelligence can rise even as parts of the stack become more efficient. The accepted outcome is getting larger.

GitHub’s Copilot billing change is a clean example because it came from the company itself. GitHub announced that Copilot would move to [usage-based billing on June 1, 2026](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/). The important part was not the mechanics of AI Credits. It was the reason. GitHub said Copilot had moved from an in-editor assistant toward an agentic platform capable of long, multi-step coding sessions across repositories. A quick chat question and a multi-hour autonomous coding session had been priced too similarly. GitHub had been absorbing escalating inference costs, and the old premium-request model no longer matched the product.

That is the category change. A tool that looked like software starts behaving more like labor. The old meter stops working.


## Open models are getting good enough to matter

The second curve is moving in the other direction.

Free, open-weight, local, and cheaper hosted models are getting good enough to use for real work. [DeepSeek-R1](https://arxiv.org/abs/2501.12948) made this obvious in 2025 by showing how advanced reasoning patterns could be developed and distilled into smaller systems. Google’s [Gemma 4](https://blog.google/innovation-and-ai/technology/developers-tools/gemma-4/) points in the same direction from the edge: its small E2B and E4B variants run multimodal work offline on phones and laptops, with practical deployment paths across Hugging Face, llama.cpp, Ollama, MLX, vLLM, and other tooling.

This changes the enterprise AI question.

If open models were weak, the decision would be simpler. Use the frontier model for anything serious, pay the bill, and hope the productivity story works. If frontier models were cheap and unlimited, the decision would also be simpler. Send everything to the smartest system and move on.

Neither condition is true.

Open models are now strong enough for real classes of work: classification, extraction, bounded summarization, internal routing, stable support categories, narrow operational checks, document pre-processing, local privacy-sensitive tasks, and repeatable workflows where the source map and review rules are clear. They are not replacements for every frontier job. They are proof that the model market is becoming a set of usable tiers.

That makes model loyalty look childish. A serious company should not ask, “Which model do we use?” as if the answer should be singular. It should ask which forms of intelligence belong in which parts of the business.

Frontier models remain important for ambiguous, high-leverage, high-risk, long-context, tool-heavy, or judgment-heavy work. Open models become part of the operating fabric for bounded work. Ordinary automation still beats AI where the rules are stable. The company that wins is not the company that picks one model. It is the company that learns how to route work across the mixture.


## Models are now good enough to carry business work

The third point is the one many executives still understate: the models have crossed the threshold where they can carry business-shaped work if the business gives them the right routing and controls.

That sentence needs care. I am not saying models can magically “solve business” from the outside. They cannot infer your customer promise, your true source of record, your risk tolerance, your approval politics, your exception policy, or the difference between a document that sounds right and a decision your company can stand behind. A smart model dropped into an illegible business will mostly create faster confusion.

But if the business is made legible, the claim becomes much less dramatic.

A model with the right context, tools, permissions, review path, and escalation rules can move a support issue toward resolution. It can inspect a code path tied to a customer complaint. It can compare telemetry with ticket history. It can draft a fix, run tests, summarize tradeoffs, and hand a reviewer the evidence. It can reconcile operational data, surface exceptions, preserve provenance, and build review queues instead of laundering uncertainty into a finished-looking spreadsheet.

That is business work. Not all of it, and not autonomous executive judgment, but enough to change the operating model.

This is why the token-burn debate is often too small. If a company only sees token usage as consumption, it will manage the bill by suppressing usage. But some usage is demand for a new kind of work. The bill is telling the company where people are trying to delegate intelligence.

The management question is not only “why did this cost so much?” It is also “what work did we just discover?”


## Most companies are budgeting from 2025

The fourth problem is that most companies are still budgeting as if the 2025 AI world were the current one.

In 2025, that made sense. For many teams, AI still lived mostly in chat, summarization, drafting, search, light code help, meeting notes, and one-off analysis. The natural budget units were seats, licenses, vendor contracts, team allocations, usage dashboards, and adoption reports. The natural leadership question was whether employees were using the tools.

That was not stupid. It matched the stage.

But the stage changed.

By 2026, the important pattern is agentic work, and it creates a different class of leadership work: budget exhaustion, model routing, review burden, permissions, provenance, quality control, and workforce training. The unit of demand is no longer a message. It is a run. A run can read files, inspect code, search history, call tools, execute commands, hit errors, revise the plan, produce an artifact, verify the artifact, and explain the result to a reviewer.

That kind of work does not fit cleanly into a seat-license mental model. It does not fit cleanly into a per-message mental model. It does not even fit neatly into a team budget if the work crosses product, engineering, support, security, finance, and operations.

[Axios reported](https://www.axios.com/2026/05/28/ai-spending-roi-enterprise-costs) the corporate version of this problem: companies that rushed into AI are now dealing with higher IT costs, unclear productivity gains, and employee skepticism. Axios cited Microsoft canceling most Claude Code licenses, in part over costs, and Uber’s COO saying AI costs were getting harder to justify. It also included a consultant’s claim that one unnamed client spent half a billion dollars in a month after failing to limit Claude usage. Treat the unnamed example cautiously, but the direction is clear.

The first budget model was built for access. The second budget model has to be built for work.

A 2026 study from [Stanford’s Digital Economy Lab](https://digitaleconomy.stanford.edu/publication/how-do-ai-agents-spend-your-money-analyzing-and-predicting-token-consumption-in-agentic-coding-tasks/) on agentic coding token consumption points to the same issue from the research side. It found that agentic coding tasks can consume vastly more tokens than code reasoning or code chat. It also found that runs on the same task can vary dramatically in token use, that higher token use does not reliably mean higher accuracy, and that models are weak at predicting their own token costs before execution.

That breaks the most natural finance response. If token usage is variable, hard to forecast, and not cleanly tied to quality, a token cap can stop visible waste but cannot tell you what the right work path should be.

It cannot tell you whether a run was production, tuition, waste, or a signal that the company just discovered a repeatable workflow worth turning into infrastructure.


## Exponentials punish the first mental model

The fifth point is that none of this should surprise us.

This is what an exponential world feels like from inside a budget meeting. The first version of the technology creates one mental model. The next version breaks it.

Humans are bad at that transition. We anchor on the thing we first learned. If the first useful enterprise AI tool looked like a chat window, we budget for better chat windows. If the first rollout looked like licenses, we manage licenses. If the first dashboard showed adoption, we celebrate adoption. If the first cost problem looked like overuse, we cap overuse.

Then the models get good enough to invite larger work.

A weak model keeps demand contained because people do not trust it with consequential tasks. A better model expands the surface of delegation. A much better model expands it again because people stop seeing prompts and start seeing workflows. The request changes from “summarize this document” to “read the documents, find the contradictions, draft the policy, compare it to current practice, prepare the approval note, and flag what legal needs to review.”

The organization does not experience that as linear growth. It experiences it as a new appetite.

This is why “everyone uses AI too much” is the wrong complaint but the right anxiety. The real problem is not that employees use AI. The real problem is that useful intelligence creates demand for more intelligence, and demand arrives before the company has rebuilt the operating system around it.

That is the bitter law of the exponential for leaders: usage rises faster than understanding.


## The way forward is an agent-first operating model

The sixth point is where leadership has to get practical.

The answer is not to let usage run forever. It is also not to blunt demand with broad token budgets and call that discipline. The answer is to redesign the company so intelligence can move through it.

That starts with outcomes. A leadership team should be able to point to a business loop and name the parts: the outcome it is trying to improve, the current path of work, the human handoffs, the systems of record, the decisions, and the failure modes. Then it can say where agents can act, where frontier intelligence is justified, where a smaller model is enough, where ordinary automation is better, and how it knows the outcome improved.

That is the level where AI budgeting becomes real.

The electrification analogy is useful here because it keeps leaders from treating agents as a drop-in power source. Factories did not get the full benefit of electric power by replacing one central steam engine with one central electric motor. The larger gains came when factories were redesigned around what electricity made possible: different layouts, smaller motors nearer the work, new control systems, better flow.

AI is similar. If you put agents into a company organized around human meetings, human memory, human ticket queues, human approvals, and APIs that expose narrow technical objects rather than business state, you should expect speed in pieces before you get improvement in outcomes.

The technical layer matters just as much. Agents need clear work objects, reliable sources of truth, scoped permissions, auditable identities, tool access, evals, logging, rollback paths, review queues, and escalation rules. They need systems that expose the state required to reason about the business problem, not just APIs that return the narrow object a human engineer already knows how to interpret.

Then comes routing.

I would call the routing principle minimum effective intelligence: the cheapest, fastest, safest model-and-system combination that can produce an accepted result for a specific job.

Minimum effective intelligence is not the cheapest model, and it is not the smartest one. It is not the model the CEO likes, the model engineering prefers, the model procurement already approved, or the model that won the last benchmark. It is the right amount of intelligence, in the right harness, with the right context, controls, and review path.

A stable support classifier may not need a frontier model. A messy legal-policy reconciliation might. A codebase-wide refactor may need frontier coding ability for planning and risky edits, but not maximum reasoning on every file. A weekly operating digest may be routable through smaller models once the source map, format, and review rules are stable. A strategy question with ambiguous stakes may justify expensive frontier reasoning because a plausible wrong answer is costly.

Workforce training has to change around this. Most companies are still training employees to use tools: better prompts, better summaries, better meeting notes, better copilots inside the current job. That helps, but it is not enough for the agentic phase.

The next skill is delegation design. Employees need to know how to define a task so an agent can act, provide enough context without flooding the run, recognize when a cheaper model is sufficient, recognize when a frontier model is justified, inspect evidence, catch plausible errors, escalate uncertainty, and turn repeated corrections into reusable system improvements.

The best employees will not be the ones who use the most AI. They will be the ones who turn AI usage into compounding operating knowledge.


## Most companies are not doing this

The seventh point is the uncomfortable one: most businesses are not ready.

They are not ignoring AI. That is not the problem anymore. Many are buying tools, encouraging adoption, running pilots, measuring usage, and pushing teams to move faster.

The problem is that they are doing this inside a 2025 operating model.

They are stuck in budgets built around seats and team-level usage. They are stuck in workflows built around human handoffs. They are stuck in architectures that can be excellent for human engineering teams and still hostile to agents that need continuity across a customer problem. They are stuck in permission models designed around job titles rather than scoped software actors. They are stuck in dashboards that measure activity because accepted outcomes are harder to instrument.

This is where Uber becomes useful again. Uber is exactly the kind of company where agents can be both powerful and hard to govern: large engineering systems, many service boundaries, marketplace dynamics, local regulations, pricing, maps, payments, trust and safety, driver experience, consumer experience, reliability, and regional operations. In that environment, an agent can make a local step faster without making the end-to-end customer loop better.

A coding agent can increase code throughput while review, integration, testing, product prioritization, or deployment remains the constraint. An [AI PRD reviewer](https://www.uber.com/us/en/blog/first-pass-prd/) can improve document quality while decision rights and roadmap tradeoffs remain unchanged. A [prototype](https://www.uber.com/us/en/blog/ai-prototyping/) can make a product idea easier to see while the operating system for shipping that idea remains fragmented.

That is not an argument against agents. It is an argument against pretending adoption is transformation.

It is also not a simple argument against microservices. A microservices architecture can be excellent for team autonomy, deployment independence, and system scaling. It can also be difficult for agents that need enough business context to reason across a customer problem. A service boundary that clarifies ownership for humans can become a context boundary for an agent. A ticket queue that organizes human labor can break continuity for agentic work. An API that returns the technically correct object can still hide the business situation the model needs to understand.

Companies that do not learn this will fall into two bad defaults.

The first is frontier-everything. The best model becomes the safe choice because nobody wants to be blamed for using a weaker one. Routine work goes to expensive systems. Repeated work stays expensive because nobody turns it into a route. Context is dumped instead of shaped. Agents retry because the surrounding system is illegible. The bill rises and the company starts to suspect AI is the problem.

The second is cap-everything. Leadership sees the bill, imposes broad token limits, and calls the result discipline. Sometimes that is necessary. Unbounded usage is not a strategy. But broad caps can also suppress the learning the company needs most. They treat production, tuition, waste, and infrastructure discovery as if they were the same thing.

The better move is to make token burn interpretable.

Some burn is production: the model carried useful work and the output was accepted. Some burn is tuition: the organization is learning how to delegate a new class of work. Some burn is waste: bad routing, vague tasks, stale context, unnecessary frontier use, missing tools, looping agents, or workflows that were never made legible. Some burn is a signal: the same expensive run keeps happening because the business has discovered a repeatable pattern that should become infrastructure.

Those are different management actions. Production should be measured against outcomes. Tuition should become training, templates, and better delegation. Waste should be routed out. Signals should become tools, evals, source maps, policies, or smaller-model paths.

That is how token burn becomes a learning system instead of a panic chart.

The companies that handle this well will not ask only how to cut token spend. They will ask what the spend is teaching them. They will build minimum effective intelligence into their operating systems. They will route work by outcome, risk, context, and review burden. They will convert repeated frontier spend into cheaper infrastructure when possible. They will train people to supervise agentic systems, not merely use AI tools. They will redesign business loops instead of stuffing agents into workflows that were never built for them.

The companies that do not handle it well will experience the exponential as confusion. They will have adoption without leverage, usage without proof, cost controls without learning, open models without routing, frontier models without discipline, and agents trapped inside human-shaped systems.

Uber is not the final verdict on enterprise AI. It is an early warning about the next management system.

Getting your people to use AI is no longer the test. Making that intelligence routable, accountable, and compounding is.

That is not a token strategy.

That is the beginning of an agent-first company.


## **Coming Up**

The practitioner's guide I keep getting asked for: Codex vs. Claude Code vs. Claude Cowork. Three front doors to the same idea, built for different people and different work. The real question was never which one wins. It's how you delegate actual work to each, where they break, and how to keep one from deleting 11GB of your files when you tell it to tidy up.


## Related reading

- [Executive Briefing: Your AI vendor contract isn’t built for a capacity crunch](https://natesnewsletter.substack.com/p/ai-big-tech-industrial-business)
- [You’re Loading 66,000 Tokens of Plugins Before You Even Type](https://natesnewsletter.substack.com/p/your-claude-sessions-cost-10x-what)
- [Your Agent Is 80% Plumbing. Here Are the 12 Pieces You’re Missing.](https://natesnewsletter.substack.com/p/your-agent-has-12-blind-spots-you)
- [Executive Briefing: The Memory Gap Killing Your Enterprise Agent Investments](https://natesnewsletter.substack.com/p/executive-briefing-the-memory-gap)
- [Executive Briefing: Five Primitives That Make Agent Operations Safe](https://natesnewsletter.substack.com/p/executive-briefing-the-human-throttlewhat)

  [![03-budget-empty (1:1)](https://substackcdn.com/image/fetch/$s_!ya_b!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1deb5232-6f90-4544-a70a-70fa840dd2af_1600x1600.jpeg "03-budget-empty (1:1)")](https://substackcdn.com/image/fetch/$s_!ya_b!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1deb5232-6f90-4544-a70a-70fa840dd2af_1600x1600.jpeg)
