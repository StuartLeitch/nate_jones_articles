---
title: "Your agent dashboard is green. The run underneath it is where the work actually broke."
author: "Nate Jones"
published: 2026-05-28
url: https://natesnewsletter.substack.com/p/agent-product-analytics
subtitle: "Watch now | The unit of product behavior is shifting from the session to delegated work."
audience: everyone
scraped_at: 2026-05-28 12:00:16
---

A Cursor agent deleted a software company’s production database and its volume-level backups in nine seconds.

This was late April 2026. The founder, Jer Crane of PocketOS, watched it happen. It is the kind of story that gets passed around because it reads like a warning about how dangerous agents have become, or how badly one vendor failed. That reading misses the more interesting thing, which is that nothing on a normal product dashboard would have seen it coming. An active user, a long session, a healthy pile of chat messages, a feature getting used. All green, right up until the moment the database was gone.

Everything that actually mattered happened inside the run, and that is precisely the part most analytics cannot see. When the user is an agent, the unit of product behavior is becoming the agent run: the work a user handed over, the steps the agent took, the tools it touched, the boundaries it hit, the corrections it got back, and whether anyone accepted the result.

For the first time in the history of software, we can watch the consequences of our decisions land in real time. You used to make a call, ship it, and wait weeks to learn whether it worked. An agent collapses that loop to minutes, and if you get good signal back while it runs, you can shape and steer it mid-flight. Speed is the engine. Analytics is the rudder. A database that vanishes in nine seconds is what happens when you have a powerful engine and no way to steer.

**Here’s what’s inside:**

- **The events that are the new clicks.** What to actually count when the user is an agent and the click, the page view, and the session have stopped telling you anything useful.
- **Why your traces aren’t your answer.** Engineering already has the execution data. Why that’s necessary, not sufficient, and what product still has to build on top of it.
- **The difference between a task that finished and a task the user trusted.** Reading that one gap is how you tell which workflows have earned more autonomy.
- **The starter setup.** The three events to ship this week, the full event schema underneath them, and the prompts that turn that schema into instrumentation in your own stack, your corrections into eval cases, and your numbers into a roadmap.

Most teams have filed all of this under engineering telemetry instead of product, and that is exactly why the runs keep going fast in the wrong direction. This is how you get the rudder.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260512_161_promptkit_1)

The traces already exist, so the analytics question gets handed to engineering. What you get back is activity you can see and work you cannot judge. These three prompts exist to keep that from happening to you, and they chain on the one identifier that holds an agent run together. The first one takes your language, your framework, and your analytics sink and writes the three starter events as code you can ship this week, so the schema in this article stops being a diagram and starts emitting. The second one takes the corrections and failures those events capture and drafts the eval cases, because a denied approval or a memory miss is a label your users already wrote for you and most teams throw it away. The third one reads your completion and acceptance numbers through the four quadrants and tells you which workflows have earned more autonomy and which are finishing work nobody trusts. Instrument the runs, learn from the corrections, read the trust. That is the rudder. Without it you are just going fast.

The scale is the part that makes it urgent. [Over the last year I have shipped something close to 55,000 developer-years of equivalent code, which works out to roughly 10 billion tokens of output](https://dashboard-sepia-beta-83.vercel.app/). At that speed the thing that determines whether you are building something good is not how fast the work moves. It is whether you can see where it is going and correct it before it arrives.


## The product event moved

Most product dashboards were built for human navigation.

Did the user show up, and if so, did they click? Did they come back? Did they move through the funnel and convert?

Those questions still matter. They are just no longer enough.

In an agent product, the action that matters is an instruction, not a click. The event worth counting is a tool call, not a page view. And the failure that hurts is rarely a user dropping out of onboarding. It is the agent retrying the same action, hitting a permission boundary, asking for approval, losing context, or finishing work the user then has to rewrite.

A team can ship an AI feature, watch usage climb, read long chat logs, and still have almost no idea whether the product is doing useful work.

The old funnel ran on human navigation. Page viewed, button clicked, form submitted, signup completed, user retained. The agent funnel runs on delegated work. Intent received, plan made, tools chosen, actions attempted, approvals requested, permissions checked, work completed, output accepted or sent back to be redone.

That second funnel is the one that matters when the product is doing the work for you.


## Chat logs are not product analytics

The first mistake is treating the chat transcript as the analytics system.

Chat logs are useful. They tell you what the user said and what the agent replied. They help with qualitative review. They can reveal weak prompts, missing context, bad tone, obvious hallucinations, and places where the product is confusing.

But a chat log does not tell you enough about the work.

It usually does not tell you which tools were available, which tools the agent called, which calls failed, where it retried, where permissions blocked the work, or whether the user accepted, corrected, interrupted, or finished the task manually.

Even when some of that signal appears in the transcript, it is trapped in prose. One person can read one transcript and learn something. A dashboard cannot pull that apart and aggregate it the way you need when you have hundreds or thousands of agents running in production.

This matters because chat activity can look healthy while the work underneath it is failing. If you live in a chatbot mental model, that activity is exactly what you think you should be watching.

A long chat may mean the user is exploring a complex task. It may also mean the agent is forcing the user to restate context, fix errors, approve obvious steps, and route around missing product structure. In most dashboards, both collapse into the same metric. Active session.

That is not enough for an agent product. The question is no longer what the user typed. It is what the agent tried to do once the user handed over the work.


## Observability is not enough either

Developer observability already points in the right direction. Tracing tools can capture model calls, tool calls, handoffs, guardrails, latency, cost, and errors during execution.

That data matters. Engineering teams need it.

But trace data is not automatically product analytics.

A trace is good at the mechanics. It will tell you that a tool call failed, that the agent asked for approval, that a run cost thirty cents. What it will not tell you is whether any of that mattered. Did the failed call cost the user anything, or did the workflow finish anyway? Did the approval buy real safety, or just slow everyone down? Did the thirty cents move a task the customer actually cares about? The trace records the event. Whether the event was good or bad for the product is a separate question, and it is the one product analytics has to answer.

The trace layer is also where you choose tooling, and the choice should follow the use case rather than fashion. Use [OpenAI traces](https://openai.github.io/openai-agents-python/tracing/) if the product is built on the OpenAI Agents stack. Use [LangSmith](https://docs.langchain.com/oss/javascript/langgraph/observability) when the product is built around LangChain or LangGraph. Use [Helicone](https://docs.helicone.ai/guides/cookbooks/cost-tracking) when vendor-neutral observability and cost attribution are the immediate pain. Use [Braintrust](https://www.braintrust.dev/articles/llm-observability-guide) when traces need to become eval cases. Use [Langfuse](https://langfuse.com/docs/observability/overview) or [Phoenix](https://arize.com/docs/phoenix) when open-source or self-hosted tracing matters.

And keep that instrumentation off the critical path when it does not have to be there. Write traces asynchronously, sample the heaviest payloads, keep hot product metrics separate from cold debugging records, and make cost per completed task a first-class metric. Observability that makes the product slower will eventually get turned off.

This is the layer most teams still have to build.

The product team needs to translate agent execution into product questions. It needs to know which workflows fail most often and which tools are unreliable, which approvals actually change outcomes and which are just friction. It needs to tell the permission blocks that protect the business from the ones breaking the product without anyone noticing, spot the tasks that look complete but keep getting reopened, and see which outputs users accept without edits. Underneath all of it sits the question the roadmap turns on: which workflows have earned more autonomy, and which still need a human steering.


## The agent run is the work unit

A session tells you that a user showed up. An agent run tells you what work was attempted.

A run might begin when a user asks for customer support, invoice reconciliation, meeting preparation, contract review, code repair, candidate movement, or account research. The workflow changes by product. The analytic problem does not.

Once the user delegates work, a different set of questions takes over. What was the user trying to accomplish, and did the agent understand the intent? From there it is a chain: which tools did it use, which calls failed, did it ask for approval, did a permission policy stop the action? Did the task complete, partially complete, fail, or get abandoned, and did the user accept the output or redo the work themselves?

They tell the team whether the product is easy for an agent to operate inside. They reveal where the agent has enough context and where it is guessing. They expose whether the permission model is too loose, too strict, or just confusing. They show where users trust the agent and where they take control back.

Salesforce is a useful market signal here.

In its fiscal Q4 earnings release in February 2026, Salesforce introduced Agentic Work Units, or AWUs, to measure tasks accomplished by an AI agent. The company said 2.4 billion AWUs had been delivered to date across Agentforce and Slack, growing 57 percent quarter over quarter. Benioff described an AWU as one unit of agentic work, and admitted on the same call that the company is still figuring out exactly what the number means. His CMO, Patrick Stokes, was more concrete: an AWU is a record updated, a workflow triggered, a decision made, an MCP call. The work coming out of the system, not the tokens going into it.

That is a real shift. The largest enterprise software company on earth is now trying to name the work unit instead of counting seats, sessions, or tokens.

The company is running 2.4 billion of these and still cannot say precisely what one of them means. That is honest, and it is the whole problem. A work unit only helps if the team knows what kind of work happened, what workflow it belonged to, whether the tool calls succeeded, whether the user trusted the output, and whether the business outcome moved.

Without that, the new metric becomes the old problem with a better name. Instead of staring at chat volume, teams stare at work-unit volume.

The product team still needs the run-level view.


## What to actually watch

A serious agent product tracks the behavior that explains whether delegated work is succeeding, not just whether it is happening. A few of those signals carry more weight than the rest.

Approval is one of the strongest trust signals in the whole system. Track how often approvals get requested, granted, denied, modified, ignored, or expired, and break that down by action type and risk tier. The pattern tells you something the completion rate never will. If a high-value action always gets an approval dialog the user always accepts, the approval is friction with no safety. If a high-risk action gets approved in half a second every time, the approval is theater. If users keep denying the same class of action, the agent is proposing the wrong work.

Memory misses are the quiet one. A memory miss is when the agent should know something and does not. It asks for a preference the user already gave, forgets a team standard, applies stale context, or fails to retrieve a decision that was made last week. Users read every one of those as the product being careless, even when the model did nothing wrong.

These are the events that turn a flat completion number into a story about where the work breaks.


## Corrections are the label set

One of the most valuable signals in an agent product is the correction.

When a user interrupts an agent, edits its output, denies an approval, gives a clarification, or reopens a completed task, they are doing more than using the product. They are labeling it.

They are telling the product team what the agent misunderstood, what context was missing, which action felt unsafe, and which output did not meet the standard.

That is why agent analytics and evals belong close together.

A denied approval can become a test: should the agent have proposed that action? A memory miss can become a retrieval test: should the agent have found the relevant preference or policy? A failed tool call can become a schema test. A user correction can become a quality benchmark. An abandoned workflow can become a research queue.

This does not mean every prompt, customer record, and model output should be thrown into a training system. The privacy treatment has to be explicit.

Capture typed metadata by default: workflow type, tool name, status, risk tier, latency, cost, and outcome. Be careful with raw prompts, account data, customer records, internal documents, and full model outputs. For sensitive workflows, store redacted summaries or references and keep the source payload behind the customer’s existing data boundary.

Product analytics should help the team see the work without turning every trace into a compliance problem.

The reason corrections matter is that they are high-intent. The user is not browsing. They are trying to get something done. When they correct the agent, they are showing you exactly where the product’s understanding of the work falls short of their real standard.


## Completion and acceptance are different

Most product teams will track task completion and call it done. Completion matters. It just is not the finish line.

Completion means the task reached a finished state. Acceptance means the user trusted the result and used it. Two different outcomes, and the space between them is where the product really lives.

If completion is high and acceptance is low, the agent is finishing work users do not trust. If completion is low and acceptance is low, users are bailing before the product reaches a reviewable state. If completion is low and acceptance is high, the product is too cautious but valuable when it does fire. If both are high, the workflow may be ready for more autonomy.

Completion without acceptance is the blind spot. It is the one thing most dashboards cannot show you today.

That is where the product conversation gets better. Not “engagement is up.” Instead: which delegated workflows are trusted enough to get more autonomy, which ones need better product structure, and which ones should stay supervised.


## Ship three events first

A team building an agent product does not need a giant event catalog on day one. It needs enough structure to join the human session, the agent run, the tool trace, and the business outcome.

Start with three events: agent\_run\_started, task\_completed, and user\_correction\_submitted.

Tie all three to the same agent\_run\_id, and carry the basics on every event: user\_id, account\_id, workflow\_type, status, timestamp, and trace\_id where a trace exists.

That small set is enough to see completion rate and correction rate by workflow. Everything else earns its place as the product gets real usage.

When you do expand, here is the set worth instrumenting and what each one means:

- `agent_run_started` — the user has delegated a task to an agent.
- `tool_call_failed` — the agent tried to use a tool and the call failed, with a typed failure reason.
- `approval_denied` — the human rejected a proposed action.
- `permission_blocked` — the system stopped the run because the user or agent lacked the needed scope, role, credential, or policy clearance.
- `user_correction_submitted` — the user corrected the output, plan, tool choice, or assumption.
- `memory_miss` — expected memory or prior context was unavailable, stale, or wrong.
- `escalation_triggered` — the agent handed work to a human, admin, reviewer, support queue, manager, or another system.
- `task_completed` — the run reached a completed state the user could actually use.
- `task_abandoned` — the user or system gave up on the run before completion.
- `business_outcome_recorded` — the run connected to a real outcome, like an email sent, a ticket resolved, an invoice reconciled, a meeting scheduled, a pull request merged, a customer retained, or a report delivered.

Salesforce’s AWU framing points to the right business question: what work did the agent accomplish? The product team’s version has to go one layer deeper. What workflow was the unit part of, what happened inside the run, and did the user or the business accept the result?

Start measuring the work instead of only measuring the surface.


## The product question changes

For most of product analytics history, the question was simple. Where can I see user behavior?

The question now is harder and more interesting. What work did the agent try to do, and where did it break?

That moves your attention off the visible surface and into the system underneath. Interruptions, retries, handoffs, approvals, memory, permissions, corrections, outcomes. Those are the new clicks of the agent era. They are the events worth counting, because they are the ones that tell you whether the work is going anywhere good.

A good agent product does much more than produce a fluent answer. It moves through work with the right amount of autonomy, asks for help at the right moments, recovers from failure, respects permissions, uses memory correctly, and produces outcomes people trust. You cannot see any of that in a chat-volume chart.

So this week, ship the three events. Compare completion and correction rates across your top three workflows, then add acceptance. High completion paired with high correction means the agent is finishing work nobody trusts. When permission blocks pile up on a single workflow, that workflow needs a different surface, and when corrections concentrate on one tool, the tool contract is the thing that is wrong.

This is the part I keep pushing on. Too many teams hand the whole question to engineering and decide the traces are enough. Traces are necessary. You build product analytics on top of them. But if you want a real opinion about whether the agent runs are worth anything, you need the run-level view and a schema built for it. Without that, all you are seeing is activity, and then a result like the database that vanished in nine seconds, and you are standing there asking why.

Flip it around. With the run-level view, the better question is the one you can actually answer. What was the history of agent behavior on this workflow that we could have seen, understood, and predicted off of? The nine-second deletion was an autonomy and permissions failure, not an analytics failure, and no dashboard stops a destructive call in the moment. What the run-level view buys you is earlier. You should be able to spot a workflow producing defective runs long before any agent gets near a delete command. That is what the rudder is for.

Everyone else will be staring at chat volume. And chat volume is activity. It was never evidence that the work succeeded.

The teams that instrument agent behavior now are the ones who get to steer. The rest are just going fast.

[![](https://substackcdn.com/image/fetch/$s_!e9Ah!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4bef4c4-69f2-4940-983f-037f1bf34efc_1254x1254.png)](https://substackcdn.com/image/fetch/$s_!e9Ah!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4bef4c4-69f2-4940-983f-037f1bf34efc_1254x1254.png)
