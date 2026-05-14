---
title: "512,000 Lines of Leaked Code Reveal the Lock-In Strategy Coming for Your AI Stack"
author: "Nate Jones"
published: 2026-04-08
url: https://natesnewsletter.substack.com/p/the-platform-play-hidden-in-512000
audience: everyone
scraped_at: 2026-05-14 14:33:58
---

Anthropic is building an always-on agent called Conway. It wasn’t announced. It was found, buried in the Claude Code source that Anthropic accidentally published last week when a packaging error pushed half a million lines of code to a public registry. While everyone focused on the source code itself (the takedown notices, the security flaws, the modified forks spreading across the internet), the more consequential discovery went largely unnoticed.

Conway is a standalone agent environment, separate from chat, with its own extension format, the ability to be woken up by outside events, browser control, and connections to your other tools. It’s not on Anthropic’s roadmap page. It’s an internal project. And when you line it up against everything else Anthropic has shipped in the last 90 days, it reveals a platform strategy that I think most people are missing.

Conway is Anthropic’s bid to become an operating system.

I spent the weekend pulling apart what was in the leak, cross-referencing it against every product move Anthropic has made this quarter, and what emerged is a pattern I’ve only seen once before in tech. It didn’t end well for the companies that weren’t paying attention.

**Here’s what’s inside:**

- **What Conway actually looks like.** A walkthrough of the always-on agent environment and what your Tuesday morning looks like six months after you set it up.
- **The five moves.** How Conway connects to Claude Code Channels, Cowork, the Marketplace, the Partner Network, and the OpenClaw ban as a single platform strategy.
- **The .cnw.zip question.** Why Conway’s proprietary extension format on top of MCP follows the Google Play Services playbook, and what it means if you’re building tools for agents.
- **The lock-in nobody’s talking about.** Why behavioral context creates switching costs deeper than anything Microsoft or Salesforce ever built.
- **What this means if you’re building.** How to think about platform risk when the agent holds your organizational memory.
- **Grab the prompts.** Three prompts to map your platform dependencies, generate enterprise contract language for portability, and choose an agent memory architecture before the defaults choose for you.

I don’t think the industry has reckoned with what an always-on agent that *learns you* means for vendor lock-in. This piece is my attempt.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260405_zxa_promptkit_1)

This week’s kit has three prompts built around the risk most teams won’t see until switching costs make it irreversible — the behavioral context an always-on agent accumulates about how you work, which has no export path and no portability standard. The first prompt maps your actual dependencies on any agent platform (data, integrations, behavioral context, billing) and produces an exit cost estimate before you’re too deep to leave cheaply. The second is for enterprise teams approaching a contract: it generates specific portability clauses to demand, a vendor questionnaire with red-flag benchmarks, and a 90-day evaluation framework so you’re not discovering the lock-in terms at renewal. The third helps developers and technical leaders choose between provider-hosted memory (fast, locked) and self-owned memory architecture (portable, harder to maintain) — with an honest decision matrix weighted to your actual constraints, not ideology. Run them before you sign, before you deploy, or before you build on top of someone else’s agent layer. You should walk away with a clear map of what you’d lose if you had to leave, the specific contract language to prevent it, and an architecture decision you made on purpose instead of by default.


## What Conway actually looks like

The implications don’t land until you picture what using this thing actually means.

Conway operates as a standalone sidebar in the Claude interface. Not a chat window, an environment. It opens a dedicated page tied to a “Conway instance” with three core areas: Search, Chat, and System.

The System section is where it gets interesting. There’s an Extensions area where you can install add-ons (custom tools, interface panels, and ways for the agent to understand new kinds of information) through .cnw.zip files. Think of it as an app store for agent capabilities. Someone builds an extension, packages it up, and Conway installs it.

There’s a Connectors and Tools section showing what other services are plugged in, including a toggle that lets Claude in Chrome connect directly to the Conway instance.

And there’s a section for automatic triggers, public web addresses that outside services can ping to wake the agent up. You can toggle which services are allowed to do this.

Now imagine what a Tuesday morning looks like six months after you set this up.

You wake up. Conway has been running overnight. It noticed three emails that match patterns it’s learned matter to you, not because you wrote rules, but because after six months of watching how you work, it knows what you prioritize. It drafted responses for two of them. The third one, from your VP, it flagged but didn’t touch. It’s learned that anything from her gets your eyes first.

It checked the Slack channels it monitors. There’s a thread in #engineering where someone asked a question about the authentication architecture. Conway pulled context from a design doc you reviewed last month and drafted a reply, sitting in your queue for approval. It noticed a competitor mentioned in #competitive-intel and cross-referenced it against the research you asked for last week, adding a paragraph to the running brief.

Your calendar has a board meeting prep session at 10am. Conway already pulled the latest numbers from the dashboards it has access to, compared them against what you presented last quarter, and highlighted the three biggest deltas with one-sentence explanations.

You haven’t typed a word yet. And about a third of what Conway did overnight will be wrong: the email draft that misreads tone, the Slack reply that’s technically accurate but misses the political context, the competitive brief that over-indexes on a press release that doesn’t actually matter. You’ll catch it in two minutes of review. The net is still massively positive. But the gap between “impressive demo” and “daily reality” is the part nobody talks about when they pitch always-on agents. I run agent workflows daily, and the honest version is: they’re transformative and they require babysitting. Both are true, and the ratio shifts toward less babysitting every month.

But an agent that knows you that well creates a dependency that goes far beyond anything a chat window ever could. More on that in a moment.


## The five moves

Conway doesn’t make sense in isolation. It makes sense as the capstone of a strategy Anthropic has been executing all quarter.

In the last 90 days, Anthropic has:

Shipped Claude Code Channels, letting you message Claude Code through Discord and Telegram and get notified when it finishes tasks. This neutralized the core appeal of OpenClaw (message your agent from anywhere) inside Anthropic’s own surface.

Launched Claude Cowork for non-technical users, targeting the 95% of enterprise employees who aren’t engineers. Cowork’s initial adoption outpaced Claude Code at the same stage, according to Anthropic’s chief commercial officer. Separately, leaked code from the same source dump shows permanent memory being built into Cowork and merged into the default Claude Desktop interface.

Opened the Claude Marketplace, an enterprise procurement layer where partner apps built on Claude (GitLab, Harvey, Snowflake, Replit, Lovable, Rogo) are purchased through Anthropic’s billing. Anthropic handles invoicing. Purchases count against existing spend commitments. No commission yet. They’re buying market share in the distribution layer.

Committed $100 million to the Claude Partner Network. Accenture training 30,000 professionals on Claude, Deloitte and Cognizant and Infosys as anchor partners, Anthropic scaling its partner-facing team fivefold. This is the system integrator lock-in that makes enterprise deals sticky.

And on Friday, began blocking third-party tools from Claude subscriptions. OpenClaw first, with Anthropic confirming the restriction will roll out to everything else in the coming weeks. If you want to use Claude through anything Anthropic didn’t build, you pay per-use rates that can run 10 to 50 times higher than what the subscription covered.

Now add Conway on top.

You’re not looking at five separate product decisions. You’re looking at a single platform strategy executed across five surfaces in a single quarter: the developer tool (Claude Code), the enterprise tool (Cowork), the always-on agent (Conway), the distribution layer (Marketplace + Partner Network), and the enforcement mechanism (the harness ban). Every piece pushes in the same direction: build inside our walls, use our surfaces, run through our billing, buy from our store.

If you’re old enough to remember the trajectory of Microsoft in the 1990s, this should feel familiar. Microsoft went from selling an operating system (DOS) to owning the desktop (Windows) to controlling the application layer (Office) to locking in the enterprise (Active Directory and Exchange). Each step was a separate product. Together they were a strategy that took Microsoft from operating system vendor to the company that owned how businesses computed. It took about fifteen years.

Anthropic is attempting the same arc, model provider to developer tool to enterprise platform to agent operating system, in about fifteen months. Conway is the Active Directory play: the piece that makes everything else in the stack sticky, because the persistent agent that knows your organization is the thing you cannot rip out without losing institutional memory.


## The .cnw.zip question

The detail in the Conway leak that I keep coming back to is the extension format, because it exposes the tension at the heart of Anthropic’s strategy.

MCP — the Model Context Protocol — is Anthropic’s own open standard. They published it. OpenAI adopted it. Google adopted it. The Linux Foundation hosts it. It’s designed to be the universal connector between AI tools and data sources. If you built Open Brain, you’re running an MCP server right now. The whole point is that any AI client can talk to any data source through one open protocol.

Conway uses MCP. But Conway’s .cnw.zip extension format sits on top of MCP and creates a proprietary layer. Extensions packaged as .cnw.zip include custom interface panels, information handlers, and tools that work specifically inside Conway’s environment. They’re not portable tools that work everywhere. They’re Conway-only tools.

This is the Google Play Services pattern. Android is built on open-source software, free for anyone to use. But the Google Play Services layer that makes Android commercially viable (Maps, payments, push notifications, the Play Store itself) is proprietary. You can technically build an Android phone without Google’s services. In practice, nobody does, because the valuable stuff lives in the proprietary layer on top of the open foundation.

MCP is the open foundation. Conway’s extension ecosystem is the proprietary layer on top. Anthropic gets the credibility of publishing an open standard and the commercial advantage of building the valuable tooling on a format that only runs in their environment.

Now think about what this means if you’re a developer building tools for agents.

You have two paths. Path one: you build a standard MCP tool. It’s portable. It works with Claude, GPT, Gemini, any MCP-compatible client. But there’s no distribution mechanism. No app store. No featured placement. You’re building a website in 2008 when everyone’s downloading iPhone apps.

Path two: you build a Conway extension. It only works inside Conway. But Conway has a built-in extensions directory. When Anthropic launches this to millions of Claude subscribers, your extension is discoverable inside the environment where people are already working. You don’t need to convince anyone to install anything. You’re in the store.

If that choice sounds familiar, it should. It’s the same choice mobile developers faced in 2009. Build for the open web, or build native for iPhone. We know how that played out. The open web was the right architectural choice. The App Store made all the money. A decade later, the web still exists and is still important, but the center of gravity in mobile software is native apps distributed through platform-controlled stores.

The developers who bet on Google Play Services-free Android learned this the hard way. Amazon tried it with the Fire Phone and Fire tablets, stock Android, no Google services, their own app store. It flopped. Not because the hardware was bad, but because the ecosystem had already organized around Google’s proprietary layer. The open kernel didn’t matter when the valuable apps needed the proprietary services to function.

I’m not saying this is evil. I’m saying it’s a pattern with a known outcome. And if you’re building on MCP because you believed it meant your tools would be portable across platforms, you should understand that Conway’s extension model creates a gravitational pull toward Anthropic specifically. The more extensions get built as .cnw.zip packages, the more Conway becomes the only place those tools actually work, regardless of what MCP enables in theory.


## What happened to OpenClaw is the template

The timeline tells the story better than any analysis could.

On January 9, Anthropic quietly blocked subscription OAuth tokens from working with third-party tools. No advance warning. When the community pushed back, the company framed it as “tightening safeguards against spoofing.” That was the first move, and it happened before anyone left.

Five weeks later, on February 14, Peter Steinberger, OpenClaw’s creator, announced he was joining OpenAI. Sam Altman called him “a genius” and said he’d “drive the next generation of personal agents.” OpenClaw moved to a foundation with OpenAI’s backing.

Within days of the hire, Anthropic revised its Terms of Service to explicitly prohibit third-party tools from using subscription credentials. Then came Friday’s enforcement, cutting off OpenClaw and everyone else.

Steinberger and investor Dave Morin tried to negotiate a softer landing. By their account, they managed to delay enforcement by a single week.

Steinberger’s own read: “First they copy some popular features into their closed harness, then they lock out open source.”

That’s the pattern I’d watch with Conway. Step one: build the first-party version of what the community built (OpenClaw → Claude Code Channels → Conway). Step two: make the first-party version free or subsidized inside the subscription. Step three: make the third-party version expensive or impossible. Step four: ship the proprietary extension format that ensures the ecosystem builds for your surface, not the open one.

We’re at step one on Conway. Steps two through four are visible in the architecture.


## The question nobody’s asking

I want to push past the strategy analysis into something I don’t think the industry has reckoned with.

Every previous form of tech platform lock-in was about stuff. Microsoft locked in your files. Salesforce locked in your customer records. Slack locked in your communication history. Stuff is painful to migrate but it’s possible. There are export tools. There are consultants who specialize in it. The switching cost is measured in months and dollars.

Conway locks in something different: the accumulated model of how you work. Not your files — the patterns the agent learned by watching you use them. Not your Slack messages — the understanding of which messages you respond to in five minutes and which ones you ignore for three days. Not your calendar — the knowledge that you always reschedule your 2pm on Thursdays and that meetings with your VP run long.

That model doesn’t export. There’s no CSV of “how this person thinks.” There’s no migration consultant for behavioral context. When you switch away from Conway after six months, you don’t just lose an agent. You lose the six months of compounding that made the agent useful. You’re back to a brilliant stranger. And the new platform’s agent starts from zero, learning you all over again, while you remember how good it was when the last one just *knew*.

This is lock-in at a layer that hasn’t existed before. It’s not about data portability — we have laws and frameworks for that. It’s about *intelligence portability*. The model of you that the agent built is the product of your data plus their compute plus six months of inference. Who owns that? Can you take it with you? In what format? These questions don’t have legal frameworks yet because the category didn’t exist until now.

Where I land: the accumulated behavioral model, the understanding of how you work that an always-on agent builds over time, should be portable. If you leave a platform, you should be able to export not just your data but the derived context in a format another system can use. This is the same principle behind data portability regulations, extended one layer deeper. And any enterprise deploying Conway for their teams should be negotiating this in the contract before deployment, not discovering it’s a problem when they want to evaluate a competitor.

Anthropic tends to be more thoughtful about these questions than the rest of the industry. I’d like to see them prove it here. The policies around behavioral context portability should ship before Conway does, not after.


## The new competitive axis

The frame I think is useful for understanding what’s actually happening in the industry right now.

The first era of AI competition was about models. 2023 through 2024. Who has the best foundation model. Benchmarks, training runs, context windows. GPT-4 vs. Claude vs. Gemini. That race isn’t over but the margins between frontier models have compressed to the point where it’s no longer the primary axis of competition.

It’s worth noting that Anthropic’s next frontier model, Mythos, is delayed in part due to security concerns and in part because serving it off the existing infrastructure would mean something like a 10x increase in compute demands. They don’t have the compute. Nobody does. We remain deeply power-constrained globally. When the bottleneck on your next model isn’t the research but the electricity, the strategic logic shifts: you stop trying to win on model releases alone and start winning on the layer that makes customers sticky regardless of which model sits underneath.

The second era was about surfaces. 2025 through early 2026. Who owns the interface where people actually work. Claude Code vs. Cursor vs. OpenClaw vs. Windsurf. The harness wars. This is the era we just watched reach its climax with the OpenClaw ban and Steinberger’s defection to OpenAI.

The third era — the one Conway signals — is about persistence. Who owns the always-on layer. The agent that doesn’t just respond when prompted but stays running, accumulates context, wakes on events, and acts autonomously. The agent that knows you not because you told it something this session, but because it’s been watching, learning, and remembering across every session.

Google is making the same move. They recently cracked down on Gemini users connecting third-party tools through their command-line interface. OpenAI hired Steinberger specifically to build their version of this. Every lab has converged on the same insight: the model is the loss leader. The persistent agent layer, the thing that holds your memory, your context, your workflows, your integrations, is the actual product.

Whoever owns that layer owns the customer. Not because the model is better. Because the switching cost of abandoning six months of accumulated agent context is prohibitive.


## What this means if you’re building

If you’re building agents, for yourself, for your team, for your clients, Conway changes the calculus.

If you’re an enterprise architecting an agent platform, the question is sharp: do you want your agent memory to live inside a single model provider’s infrastructure? Conway is convenient. It’s going to be polished. It’s going to ship with an extension ecosystem from day one. But everything your agents learn about your organization, your workflows, your decisions, your institutional knowledge, lives inside Anthropic’s systems. Switch providers and you leave the brain behind.

If you built Open Brain, you already have the alternative architecture: memory you own, exposed through an open protocol, that any model can access. Conway’s launch will be the test of whether that matters enough to justify the setup cost, or whether convenience wins, as it usually does.

I’ve written before about why I think owning your memory layer is the right architectural bet. I still believe that. But I also want to be honest about the headwinds. Conway is going to be very good. Anthropic is going to make it very easy. And for most users, “Anthropic holds my agent’s brain and it just works” will beat “I run my own database and it’s portable” every single time.

The builders reading this aren’t most users. You understand platform risk. You watched the OpenClaw community wake up on Friday with broken pipelines because a switch got flipped. You know what it looks like when a platform you built on decides your use case isn’t worth supporting anymore.


## What I’m watching

As of this writing, Conway hasn’t shipped publicly. It’s in the codebase, it’s in internal testing, and based on the maturity of what leaked, it’s a matter of months.

When it launches, I’ll be watching three things.

Does the .cnw.zip format open up or stay proprietary? This is the whole game. Open extensions mean Conway is a platform the broader ecosystem can build on. Proprietary extensions mean it’s a walled garden with an open-source foundation for credibility. The history of this pattern, Android, iOS, the web, says the proprietary layer wins the economics even when the open layer wins the argument.

Does OpenAI ship their competing always-on agent before or after Conway goes public? Steinberger is there to build exactly this. It remains to be seen whether they learned from Anthropic’s approach to the OpenClaw community and decide to play the open card.

And the one I care about most: does the enterprise world accept an always-on agent that lives inside a model provider’s infrastructure, or does the privacy and portability argument win?

Because if enterprises are comfortable letting Anthropic hold the persistent memory of how their organizations work, then Conway isn’t just a product. It’s the beginning of the deepest vendor lock-in the technology industry has ever produced, deeper than Windows, deeper than Active Directory, because those systems held your files and your login credentials.

Conway holds how your people think. The leaked source code told you how Claude Code works, but Conway tells you where the industry is going, and that’s the part worth paying attention to.

[![](https://substackcdn.com/image/fetch/$s_!-eYZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0acb3467-cafc-41f0-9fbf-11f3e9da8ba0_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!-eYZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0acb3467-cafc-41f0-9fbf-11f3e9da8ba0_1024x1024.png)
