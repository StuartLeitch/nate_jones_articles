---
title: "The 5-question filter I run every agent launch through (so you can stop reading release notes)"
author: "Nate Jones"
published: 2026-04-29
url: https://natesnewsletter.substack.com/p/the-5-question-filter-i-run-every
subtitle: "Watch now | Six weeks of agent launches, run through the filter that separates infrastructure from features."
audience: everyone
scraped_at: 2026-05-14 14:32:50
---

“I am exhausted. Every week another agent launches. Everyone is telling me I should care. How do I know which ones actually matter?”

That is the most common thing I’m hearing from team leads and executives right now. Some version of that question, every week, from people who are good at their jobs and tired of pretending they have read every release note.

The agent conversation stopped being about models two quarters ago. It is about infrastructure now. What wins enterprise adoption this quarter is not which lab has the best frontier model. It is which products let you reach the data, run the workflows, and stack the agents your team already uses.

Teams still benchmarking model quality are losing the year to teams that picked the right data fabric. License spend is getting wasted on products that win demos and don’t survive real work. Buyers are asking “which agent is best” when the question is “which agent fits the work my team actually does.” The teams that figure this out before their competitors are pulling ahead in compounding ways, and the gap is widening, not closing.

There are four launches from the last six weeks that pass the filter I use, and most of the coverage you have read missed three of them. ChatGPT Workspace Agents, which I covered earlier this week, is one. The other three are getting less attention and matter at least as much. In some cases more.

**Here’s what’s inside:**

- **The five-question filter.** What I run every agent launch through before deciding whether to pay attention — reusable on the next four launches, and the four after those.
- **Why Salesforce Headless 360 is the most important launch of the month.** The cleanest infrastructure play any major enterprise vendor has made this year, and why most coverage missed it.
- **A practical routing guide for Copilot, Perplexity, Claude direct, and Salesforce.** Stop forcing one product to do every job — match the work to the tool.
- **The “should I switch” question is framed wrong.** Why this is a layering decision, not a switching one, and the three sub-questions that replace it.
- **Three prompts you can use today.** A reusable launch filter for every announcement that lands in your feed, a license spend audit for your current AI tools, and a layering map you can share with your team.

The filter comes first because it is reusable.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260423_988_promptkit_1)

Three prompts, built from the frameworks in this piece, designed to run in any thinking-capable model. The Launch Filter applies the five-question test to any announcement you paste in and gives you a scored verdict tailored to your stack and role — reusable on every launch that lands in your feed for the rest of 2026. The License Spend Audit takes your current AI tools and your team’s actual work and produces a one-page memo showing where you’re paying for capability that doesn’t fit the work, and where you have a gap. The Layering Audit takes your default tool and your three to five most common work types and produces a routing decision tree, plus a five-line share-ready version for Slack or Notion. These prompts exist because most agent decisions get made on the wrong axis. Each prompt forces a decision the article asks you to make. If you cannot fill in the blanks the prompts ask for, that is the answer — you are not ready to commit yet, and that is useful information.


## The filter

Five questions, in this order. I run every agent launch through these before deciding whether to pay attention.

Does it plug into tools my team already uses, or does it expect me to migrate my work into its environment? The best agent news is infrastructure news: a new way for my existing agents to reach the tools where my work already lives. The worst is a new destination I am supposed to move to. A decade of SaaS already proved that migration is the single most expensive thing you can ask a team to do, and it rarely survives first contact with the work.

Does it let other agents build on top, or is it a closed product? If I can point my coding agent, my research workflow, or my custom automation at it, that is infrastructure. If it only works standalone, that is a feature. Features commoditize. Infrastructure compounds.

Does it own or access data I care about? Agent quality is downstream of data access, full stop. A mediocre agent looking at your full customer history beats a great agent looking at nothing. This is the axis on which Copilot beats ChatGPT inside M365 shops and Agentforce beats everyone inside Salesforce shops, even when the underlying reasoning is weaker.

Is there an ecosystem forming around it? One-off launches fade. Ecosystems compound. Marketplaces, SDKs, partner programs, ship-cadence consistency — those are the signals that tell you whether the thing will still matter in six months. A product with a marketplace growing weekly is different from a product with a press release.

Can I stack agents on top? A launch that lets me compose is more valuable than one that adds a tool I evaluate against the others. The first multiplies. The second adds. This is the axis people most often forget, and it is the one that matters most for the durability of the purchase decision.

Run any launch through those five and a surprisingly clean signal emerges from the noise. Most launches fail the filter. The ones that pass are worth an afternoon of attention from your team. The rest are not.


## Salesforce Headless 360 is the most important launch of the month

A week before OpenAI shipped Workspace Agents, at Salesforce’s TDX developer conference, the company announced what it calls Headless 360. The name obscures the significance. What happened is this: every capability across the entire Salesforce platform, every object, every workflow, every piece of business logic, every piece of CRM data, is now exposed as an API, an MCP tool, or a CLI command. Parker Harris, the Salesforce co-founder, asked the question out loud in late March: “Why should you ever log into Salesforce again?” Headless 360 is the answer. The browser UI is now optional, and every agent on the market can reach into Salesforce with full live data access and inherited enterprise permissions.

The numbers are the story. Sixty new MCP tools. Thirty preconfigured coding skills. Native support for Claude Code, Cursor, Codex, and Windsurf. An Experience Layer that separates what an agent does from how its output renders, so a single agent can surface in Slack, Microsoft Teams, Mobile, ChatGPT, Claude, Gemini, or any MCP-compatible client from the same underlying logic. AgentExchange, a new unified marketplace, consolidates 10,000 Salesforce apps, 2,600 Slack apps, and 1,000 Agentforce agents behind a $50 million Builders Fund. And Agent Script, the language for defining agent behavior, has been open-sourced.

The reason this matters more than it reads is that Salesforce has positioned itself as infrastructure under the agent economy rather than a product competing inside it. If your company runs revenue operations on Salesforce, the question is no longer “should we use Agentforce or Workspace Agents for our CRM work.” It is “which of the agents we already use can now do CRM work because Salesforce finally let them.” The answer is all of them. A Claude Code agent can now build Salesforce apps with live data awareness. A ChatGPT Workspace Agent can now update opportunities. A custom Perplexity workflow can now pull pipeline data. An internal Cursor-based tool can now trigger Flows.

Run Headless 360 through the filter and it passes every axis. Deepest connector story. Explicit openness to every agent framework. Owns the data enterprise revenue teams run on. Most energetic new ecosystem of the month with AgentExchange and the Builders Fund. Designed from the ground up for other agents to stack on top of it. This is the cleanest infrastructure play any major enterprise vendor has made this year, and most of the coverage completely missed it because Salesforce’s developer conference does not produce the kind of headline the AI press orients around.

The sleeper data point inside all of it is worth calling out. Agentforce Vibes 2.0, the build-inside-Salesforce development tool, ships with Claude Sonnet 4.5 as its default model. GPT-5 is available as an option through a multi-model switcher, but the default is Claude. This is the third major enterprise infrastructure product this year to put Claude at the center by default. Microsoft Copilot Cowork is built on Anthropic’s Claude agent technology through an explicit partnership. Perplexity Computer’s default orchestrator is Claude Opus 4.7. Salesforce’s flagship agent development tool defaults to Claude. Anthropic’s enterprise strategy has increasingly become “be the agent layer inside other people’s products” rather than “build a standalone product that competes with them,” and the enterprise market is rewarding that choice clearly.


## Copilot Wave 3 is undercovered

Microsoft’s Copilot Wave 3 release predates this month’s news but has been undercovered for the same reason Salesforce Headless 360 is: it came wrapped in the language of enterprise IT rather than the language of AI, and the tech press pays less attention to IT releases than it should.

Two features matter. Copilot Cowork, which brings long-running multi-step agent execution into the M365 surface, built on Anthropic’s Claude. And Work IQ, which gives Copilot native access to your organization’s full context: every email, every meeting, every chat, every file, every SharePoint page, with identity and permission inheritance from your Entra directory.

The data access story is the moat. A ChatGPT Workspace Agent reaching into SharePoint through a connector can do work. Copilot Cowork sitting natively inside SharePoint with Work IQ does work with the full organizational memory behind it. For Microsoft-native enterprises, this is not a close comparison. Copilot runs the same kind of multi-step autonomous work Workspace Agents runs, but with an orders-of-magnitude better sense of what your organization actually is.

Where Copilot loses: agent composability is harder because it is more difficult to point external agents at it, and ecosystem energy is weaker because the Copilot Studio developer community is less active than OpenAI’s or Salesforce’s. Coding tasks also go decisively to Claude or GPT-5 via other tools — which is a big part of why, from what I hear, Google engineers ask for Claude internally, and I suspect a lot of Microsoft engineers do too. If your team’s work is mostly inside M365 and mostly not coding, Copilot Cowork is probably your right answer. If your team’s work crosses ecosystems or leans heavily on coding, the native data advantage matters less and the composability gap hurts more.

Against the filter, Copilot Wave 3 scores high on data access and connectivity for M365 shops specifically, moderate on ecosystem, low on openness to external agents. It passes the filter for a specific audience and fails it for others. That is the cleanest way to think about it.


## Kimi K2.6 matters less than it reads

Moonshot released Kimi K2.6 as open weights under a Modified MIT license on April 20th. The technical leap is real: 300 parallel sub-agents coordinating across 4,000 steps, up from K2.5’s 100 sub-agents and 1,500 steps; twelve-hour autonomous runs; benchmark scores that beat GPT-5.4 on SWE-Bench Pro and lead the field on Humanity’s Last Exam with tools. Moonshot’s own RL infrastructure team ran a K2.6 agent autonomously for five days doing production monitoring and incident response, which is the strongest dog-fooding signal any lab has put forward this year.

And yet, through the filter, Kimi matters less for enterprise buyers than Salesforce, Workspace Agents, or Copilot. The model quality is excellent. The consumer-facing UI at kimi.com is more approachable than people realize; anyone can type a prompt and click “Agent Swarm” to run the full 300-agent architecture. But the ecosystem, connector story, and Western enterprise data access are all thin. It does not plug into the tools your team already uses. It does not own a graph. And it is a Chinese-market-first product, which for many Western companies raises legitimate questions about where data travels during a long autonomous run.

Kimi is one of the strongest open-weights agent models on the market right now, and the distinction that matters is who is buying. For dev teams building their own agent infrastructure, Kimi is a legitimate answer. Open weights under a Modified MIT license means you can self-host, run it on your own hardware, inspect the model directly, fine-tune on your own data, and avoid vendor lock-in. The 300-agent swarm architecture and the twelve-hour autonomous run demonstrations are real capabilities you can deploy without sending a single byte to Moonshot’s infrastructure. For a company that has the engineering depth to run a trillion-parameter MoE and wants frontier-class agent capability without a closed-lab dependency, K2.6 is the serious open-weights answer. Qwen 3.6 is the other one, and teams in this bucket should evaluate both.

For the Western prosumer or team asking “should I use the hosted kimi.com product for real work,” the answer is almost always no. The Chinese infrastructure question cannot be sidestepped with “just don’t put sensitive data in,” because the discipline of carving that line cleanly per prompt is higher-effort than anyone will sustain. The two cases are materially different. The dev team running K2.6 on its own hardware is not sending data to anyone. The prosumer typing into kimi.com is. Conflating them is the mistake most of the coverage is making.

Kimi matters strategically as a signal about open-weights trajectory and about how fast agent architecture is advancing outside the Western labs. For dev teams with the capacity to self-host, it is an actual purchase decision this month. For the hosted consumer product, it is not a purchase decision for the audience this piece is written for.


## Perplexity Computer closed the local gap

Perplexity Computer has existed since February, but the April rollout of the Mac Personal Computer app added local file editing, local browsing through Comet, and voice orchestration. That closes the “it is a cloud toy that cannot see my stuff” criticism that kept Computer feeling abstract for its first two months. Windows is coming. Claude Opus 4.7 is now the default orchestrator model. With these changes, Perplexity Computer is an end-to-end digital worker, not a cloud research assistant.

Run Perplexity Computer through the filter: high on connectivity thanks to 400+ connectors, moderate on everything else. It passes for research-heavy work that produces a deliverable inside a Western SaaS stack. It fails for team-shared recurring workflows, where Workspace Agents wins; for M365-native work, where Copilot wins; and for revenue operations on Salesforce, where Headless 360 wins. Do not try to force one product to do every job. Assign the work to the tool.


## What to use each one for

This is the part most teams skip, and it is where most of the wasted license spend happens. Someone bought the license and then tried to force one product to cover every job class because the cost of adopting a second tool felt higher than it is.

**Perplexity Computer.** Best for research-heavy work that produces a deliverable, inside a Western SaaS stack. Competitive intelligence reports. Market research with charts and dashboards. Sales prospecting synthesizing LinkedIn, press releases, and product announcements into personalized outreach. Financial and investment research comparing multiple companies with sentiment and DCF frames. Document review and verification workflows for contracts or proposals. Weekly ops reports that read Slack, check calendars, pull from sheets, and draft the narrative. Anything where the deliverable is a polished artifact and you want a specialist.

**Microsoft Copilot Cowork with Work IQ.** Best if your team lives in M365. Excel Agent Mode for autonomous dataset cleaning, anomaly detection, and multi-page reporting. PowerPoint generation from company files and references. Outlook Voice Catch-Up for inbox triage. SharePoint site building by natural language. Teams Facilitator for meeting notes and action tracking. Monthly accounting close when the accounting data lives in M365. Anything that benefits from native permissions inheritance and the full organizational graph.

**Claude directly.** Best for coding (Claude Code remains the stronger choice over most alternatives for the engineering teams I talk to), long-running reasoning tasks without native SaaS integration through Claude Cowork directly, reusable skill development, and screen-based task automation where no clean API exists via Computer Use. Also worth knowing: you will meet Claude twice whether or not you pay Anthropic directly. Once as the model your coding agent runs. Once as the engine inside the enterprise agent vendor you already bought, whether that is Microsoft, Perplexity, Salesforce, or someone else.

**Salesforce Headless 360 integration patterns.** Point your existing coding agent (Claude Code, Cursor, Codex, Windsurf) at Salesforce to build apps with live data access and full org awareness. Build a custom agent in ChatGPT, Claude, or a bespoke stack that takes CRM actions via MCP tools. Use the Experience Layer to render your CRM-backed agent natively across Slack, Teams, ChatGPT, Claude, or Gemini from the same underlying logic. Deploy Slack-native Salesforce agents via the new Slack Agent Kit. For revenue operations teams running on Salesforce, the cheapest high-value move of the month is spending an afternoon in Agentforce Vibes 2.0 with Claude Sonnet 4.5 and seeing what is now possible that was not possible two weeks ago.


## When do you switch?

The most common question I get underneath all of this is some version of “when should I switch from Claude?” I get the ChatGPT version of the same question, the Copilot version, and increasingly the Perplexity version. They are all framed the same way and they are all framed wrong.

The Claude-specific version has a wrinkle worth naming first because it is the most common and the most misleading. You are probably already using Claude without switching anything. If your company runs Microsoft Copilot Cowork, you are using Claude underneath. If you run Perplexity Computer, your default orchestrator is Claude Opus 4.7. If your Salesforce team uses Agentforce Vibes 2.0, the default coding model is Claude Sonnet 4.5. Anthropic’s enterprise strategy this year has been to sit at the center of other companies’ agent stacks rather than compete at the product layer, and for a lot of workflows the right question is not “switch from Claude” but “which wrapper around Claude fits this specific job.” That wrinkle does not exist for ChatGPT or Gemini users in the same way, because OpenAI and Google are still playing a product-layer game, not an infrastructure-layer one.

But the framework is the same whether your default is Claude, ChatGPT, Copilot, Gemini, or something else. The real question is three questions, not one.

When should you stay in your default agent’s direct product? When the model is the center of the work and the surrounding tools are secondary. Coding, for most teams. Long-context reasoning where you want direct model-level control. Novel research where the value is in the quality of the reasoning rather than in integration with a SaaS graph. Custom agents you are building with your own skills and your own workflow logic. If you are a Claude user, Claude Code is the stronger choice over Gemini and competitive with Cursor and Codex on production engineering work, and direct Claude is the right home for most model-centered work. If you are a ChatGPT user, direct ChatGPT is the right home for novel reasoning tasks that do not fit the Workspace Agents recurring-pattern shape. If you are a Copilot user, this is actually the weakest bucket for you — Copilot’s value is in its integrations, not its raw reasoning, so this is the bucket where Copilot users should most often look outside their default.

When should you use a different product that happens to run the same underlying model? When the wrapper delivers data access or integration you cannot replicate by pointing the direct product at the same tools via connectors. This is the bucket where the Claude-is-inside-everything observation really matters. Copilot Cowork with Work IQ gives Claude native access to your entire M365 graph in a way you cannot replicate by pointing direct Claude at SharePoint via a connector. Perplexity Computer bundles 400+ OAuth connectors and a 19-model orchestration layer on top of Claude’s reasoning. Salesforce Agentforce with Claude inside it inherits permissions from the Salesforce trust layer in a way a direct Claude agent cannot. In these cases you are not switching from your default. You are switching from “your default talking to tools via your configuration” to “your default talking to tools through a vendor’s native integration,” and the vendor’s native integration is often materially better than what you would build yourself. It comes down to whether you need that specific data fabric badly enough to pay for the wrapper.

When should you use a product that runs a different underlying model entirely? When the underlying model matters less for the specific job than the surrounding product does. ChatGPT Workspace Agents on Codex fits best for the Slack-native, team-recurring, conversational-builder pattern OpenAI has extensive tooling around, regardless of whether Claude or Gemini would produce a marginally better individual response. Google Gemini in Workspace wins for teams that live in Google, because it inherits the graph the same way Copilot does for M365. Self-hosted Kimi K2.6 is the answer for dev teams that want frontier-class agent capability on open weights without a closed-lab dependency. The deciding factor in this bucket is never which model is marginally better. It is always which surrounding product fits the work.

The switching costs across all three buckets are real and underrated. Prompts do not transfer cleanly; a prompt tuned for one model often underperforms with another because the response patterns and the way each handles ambiguity are different. Memory and context do not port across products. Skills are more portable than they used to be thanks to the open-source agent skills standard, but they are not plug-and-play across every product yet. Team habits matter more than most people admit: if your team has spent six months learning how to specify work to any specific model, moving them to a different product restarts some of that learning.


### What this judgment actually is

The agentic frameworks reward different human skills, and this is the part that takes practice. Direct Claude chat rewards iterative conversation and prompting discipline. Claude Code rewards review-and-intervene judgment on agent runs. Workspace Agents rewards decomposition of recurring work into steps a conversational builder can wire up. Copilot in M365 rewards knowing what Work IQ can see and how to route across apps. Perplexity rewards query framing and credit-budget awareness. Using any single product exclusively flattens your workflow to whatever that product does best. Using multiple products well means building the judgment about which shape of problem matches which shape of tool, and that judgment is the actual new literacy of the agent era. It takes months to develop and it is the thing separating people who get compounding returns from these products from people who churn off them in disappointment.

The meta-answer, and the version I would give most readers, is that this is not a switching question. It is a layering question. You keep your default for what it is best at, you add specialists for the jobs where the specialist wins, and over time you develop the judgment to route work among them. “When should I switch” framed as a binary is almost always the wrong question. “What should I add, and what should stay in the default” is the better one.


## The rest of 2026

The agent layer is not one product category and the launches are not all equal. Filter for infrastructure over features, ecosystems over single launches, stackability over walled gardens, and data access over model quality. Use the launches that pass for the specific jobs they are good at. Match the shape of the work to the shape of the tool. That is the game for the rest of 2026, and the teams that internalize the filter first are going to pull ahead of the teams that keep chasing model benchmarks.

[![](https://substackcdn.com/image/fetch/$s_!8bmU!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9af204fb-772e-4ad9-a945-c5c247f963cb_1254x1254.png)](https://substackcdn.com/image/fetch/$s_!8bmU!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9af204fb-772e-4ad9-a945-c5c247f963cb_1254x1254.png)
