---
title: "My honest breakdown of the OpenClaw hire + what 21,639 exposed instances tell you about agent security"
author: "Nate Jones"
published: 2026-02-17
url: https://natesnewsletter.substack.com/p/the-20kmonth-lobster-that-zuckerberg
subtitle: "Watch now | The OpenClaw saga continues..."
audience: everyone
scraped_at: 2026-02-22 15:12:16
---

Peter Steinberger built what’s been widely described as the fastest-growing open-source project in GitHub history—from his living room in Vienna, while bleeding $20,000 a month. On Valentine’s Day 2026, he posted three paragraphs on his personal blog announcing he was joining OpenAI. Sam Altman followed with a post on X calling Steinberger “a genius” who would “drive the next generation of personal agents.” The announcement landed less than 48 hours after OpenClaw shipped a massive security update—more than 40 patches across the platform. The timing is not a coincidence, and this is not primarily an acqui-hire.

OpenClaw—the project Steinberger built in about an hour on a Friday night in November 2025—proved something the industry needed to see: a self-hosted AI agent could do real work on real computers. Not answer questions. Not generate text. Actually manage your email, schedule meetings, control browsers, execute shell commands, and send messages across WhatsApp, Telegram, Slack, Discord, Signal, and iMessage—all running on your hardware, storing your data locally.

The project exploded from 2,000 GitHub stars to nearly 196,000 in under three months, survived crypto scammers hijacking the repository during a rename, weathered a high-severity remote code execution vulnerability, and attracted 600 contributors who pushed more than 10,000 commits. Then both Zuckerberg and Altman made offers. Steinberger chose OpenAI. OpenClaw itself moves to an independent foundation and stays open source. And meanwhile, Anthropic’s Claude Code had just hit $1 billion in annualized revenue, OpenAI’s Codex was playing catch-up in the developer tools market, and Steinberger had been walking around describing himself as “the biggest unpaid promoter for Codex”—having built most of OpenClaw’s codebase by running four to ten coding agents simultaneously, accumulating 6,600 commits in January alone.

**Here’s what’s inside:**

- **From Friday night hack to 196,000 stars.** How a trademark dispute, crypto scammers, and a social network where AI bots created their own religions accidentally fueled the most-starred new repo in GitHub history.
- **The Zuckerberg pitch vs. the Altman pitch.** What each CEO actually offered, why hands-on product feedback lost to mission alignment, and what the deciding factor reveals about where agents are heading.
- **The three assets OpenAI actually got.** Developer trust that no marketing budget can manufacture, architectural knowledge forged in real agent failures, and a community building everything from AI-controlled breweries to vibrator integrations.
- **The security crisis that preceded the hire.** CVE-2026-25253, 21,639 exposed instances, credential leaks at scale, and why Steinberger shipped 40 patches before walking out the door.
- **What changes for OpenClaw’s community.** Why the Chrome-Chromium analogy is both instructive and ominous, and what 600 contributors should expect now.
- **Where OpenAI goes next.** The enormous gap between what OpenClaw proved possible and what your mother can safely deploy on her laptop—and why Altman’s phrasing reads as a product roadmap for consumer agents.

Let me show you how a lobster ended up inside the world’s most valuable AI company—and why it matters for how you work.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260216_vpl_promptkit_1)

The companion prompt kit gives you the tools to think through what this shift means for your own work. You’ll find prompts for evaluating agent architectures, mapping security attack surfaces in agentic systems, assessing the Chrome-Chromium model for open-source projects under corporate influence, and analyzing competitive positioning in the personal agent space.

These aren’t generic strategy templates—they’re frameworks built around the specific lessons from OpenClaw’s three-month trajectory from side project to foundation, designed to help you navigate the gap between what agents can technically do and what you can safely deploy.


## From Friday Night Hack to 180,000 Stars

The origin story of OpenClaw borders on absurd. On a Friday night in November 2025, Peter Steinberger—an Austrian developer whose PDF framework company PSPDFKit had secured a €100M-plus strategic investment from Insight Partners—sat down and built a prototype in about an hour. The concept was deceptively simple: wire a large language model into WhatsApp so it could read messages, browse the web, and execute shell commands on your behalf.

Steinberger had spent three years away from technology after his exit, traveling, doing therapy, experimenting with ayahuasca, and cycling through what he’s described as a period of deep searching. He came back to coding because AI pulled him back. Before OpenClaw, he’d churned through 43 different projects. Number 44 was the one.

The initial version was crude. It connected a messaging interface to Claude, Anthropic’s language model, and could do basic tasks. Steinberger open-sourced it as “Clawdbot”—a pun on Claude and the lobster claw that became the project’s mascot. By mid-January 2026, it had around 2,000 GitHub stars. Respectable for a side project, but nowhere near a phenomenon.

Then everything detonated at once.

On January 27, Anthropic’s legal team sent a trademark notice: “Clawdbot” sounded too much like “Claude.” Steinberger agreed to rename. He chose “Moltbot”—lobsters molt when they outgrow their shells. During the renaming process, in the literal five seconds between releasing his old GitHub handle and claiming the new one, crypto scammers sniped the account and began promoting a fake $CLAWD token on Solana. Within hours they were serving malware from his GitHub and hijacking his NPM packages—Steinberger came close to deleting the entire project.

Three days later, he renamed again to “OpenClaw,” this time with purchased domains, completed trademark searches, and coordinated account changes executed with what he later described as “Manhattan Project-level secrecy.” He also spent $10,000 to buy a dormant Twitter business account to secure the handle.

The chaos, paradoxically, was the accelerant. Each rename triggered new threads on Reddit and Hacker News. The trademark drama drew media coverage. A simultaneous launch of Moltbook—an experimental social network designed exclusively for AI agents—went viral, with Fortune, CNBC, and TechCrunch covering AI bots creating their own religions, governments, and existential poetry. Within weeks, OpenClaw crossed 100,000 GitHub stars. By mid-February 2026, it had surpassed 180,000 and attracted 196,000 stars total—making it, by most accounts, the fastest-growing repository GitHub has ever seen—more than 10,000 commits from 600 contributors in under three months.

The numbers matter, but they obscure the more important point: OpenClaw proved that a self-hosted AI agent could do things no chatbot had done before. It didn’t just answer questions. It managed email, scheduled meetings, controlled browsers, executed shell commands, and sent messages across WhatsApp, Telegram, Slack, Discord, Signal, and iMessage—all running on your hardware, all storing your data locally. And its most unsettling capability, the one that made researchers both excited and alarmed, was that users could configure it to modify its own source code.


## Why OpenAI Over Meta

Before dissecting what OpenAI got, it’s worth understanding the negotiation Steinberger walked through—because the way he chose reveals what this deal is really about.

Both Mark Zuckerberg and Sam Altman made concrete offers. Zuckerberg reached out via WhatsApp. When Steinberger suggested they just call right then instead of scheduling, Zuckerberg asked for a few minutes because he needed to finish coding. That detail clearly resonated with Steinberger—a founder who built his reputation on shipping. Zuckerberg tried OpenClaw personally and sent a message calling it amazing. He also gave blunt product feedback, alternating between praise and pointed criticism. Steinberger valued this directness, noting that hands-on engagement showed that Zuckerberg actually cared about the product.

On the OpenAI side, Altman’s pitch came with something more tangible: a promise of computational power tied to the Cerebras deal that could dramatically accelerate agent performance, plus the fact that OpenAI was already sponsoring the project. Steinberger described his conversations with Altman as thoughtful and substantive. He also acknowledged having more personal connections at OpenAI and a deeper history of building on their technology.

But Steinberger admitted that he didn’t get the same hands-on product engagement from OpenAI that he got from Zuckerberg. The deciding factor appears to have been mission alignment rather than personal chemistry. Steinberger’s stated goal—building an agent his mother could use—requires access to frontier models and the kind of research pipeline only a leading lab can provide. He spent the week before the announcement in San Francisco meeting with labs, getting access to unreleased research, and came away saying OpenAI’s vision most closely matched his own. Critically, OpenAI also agreed to support OpenClaw as an independent open-source project through a foundation, preserving the condition Steinberger had called non-negotiable from the start.

His attitude throughout the process was characteristically blunt. When Fridman asked if this was the hardest decision he’d ever faced, Steinberger replied: “Nah.” The man who’d already seen a nine-figure deal for his previous company and spent three years soul-searching before returning to code does not, apparently, agonize over career moves. “The beauty is if it doesn’t work out, I can just do my own thing again,” he told Fridman. That posture—total optionality, zero desperation—gave him leverage most acqui-hire candidates never have.


## What OpenAI Actually Got

OpenAI did not acquire OpenClaw. Steinberger is joining the company as an employee. OpenClaw itself is moving to an independent foundation and will remain open source. Altman confirmed on X that OpenAI will continue to sponsor the project.

This is an important distinction. OpenAI got Steinberger—his vision, his developer credibility, his community influence, and his proven ability to build agentic systems people actually use. What they did not get is exclusive control of the platform. The Chrome-and-Chromium model that Steinberger had floated in his Lex Fridman interview appears to be roughly what’s taking shape: OpenClaw as the open-source foundation, OpenAI’s consumer products as the polished commercial layer built on top of (or alongside) it.

That said, three assets came with Steinberger that are genuinely hard to replicate.

Start with developer trust. Steinberger is not a corporate product manager who shipped an agent from inside a lab. He’s an independent developer who built OpenClaw in public, bled cash to keep it running, routed sponsorship money to dependencies instead of pocketing it, and told Lex Fridman on camera that when it came to the acquisition talks with Meta and OpenAI, “I don’t do this for the money. I don’t give a fuck.” That posture—substantiated by the fact that he’d already done a nine-figure deal with Insight Partners—gives him authenticity with developers that no amount of marketing spend can manufacture.

Then there’s the architectural knowledge. OpenClaw is not a toy demo. It is a platform with a gateway architecture, a skills marketplace (ClawHub), browser control, cron scheduling, multi-model support (Claude, GPT, Grok, DeepSeek, open-source LLMs), and integrations spanning a dozen messaging platforms. It runs on macOS, Linux, and via Docker. The security challenges it has faced—and the solutions Steinberger and his community developed—represent hard-won knowledge about what happens when you give an AI agent real access to real systems. That knowledge is directly transferable to whatever OpenAI is building next.

And then there’s the community itself. Six hundred contributors. A Discord server that became a gathering point for some of the most creative and unhinged agent experiments on the internet. A global user base that includes developers building AI-controlled mini-breweries, smart home automations, and DevOps pipelines. And yes, a vibrator company from Singapore that announced plans to integrate with the platform. The OpenClaw community is chaotic, inventive, and deeply invested—exactly the kind of ecosystem OpenAI needs if it wants to compete in the agent layer.


## Why OpenAI Needed This Now

The timing of this hire is not incidental. Consider what OpenAI was looking at in mid-February 2026.

Anthropic’s Claude Code had hit $1 billion in annualized revenue just six months after launch. It had become the default coding tool for a generation of developers, and its momentum showed no signs of slowing. OpenAI’s Codex product—launched as a macOS app in early February—was its counterpunch, positioned as a “command center for agentic coding” with support for multiple parallel agents, skills, and automations. But Codex was playing catch-up in a market where developer loyalty is sticky and switching costs are real.

Meanwhile, Steinberger had been walking around for weeks publicly describing himself as “the biggest unpaid promoter for Codex.” He had been building OpenClaw using OpenAI’s models. He had recorded a three-hour Lex Fridman episode—one of the most widely viewed tech podcasts on earth—comparing GPT Codex 5.3 and Claude Opus 4.6 side by side, describing Codex as reliable and efficient. His assessment was nuanced: Claude had stronger role-playing ability and was more interactive, but was impulsive and would write code without reading context first. Codex would read a large volume of code by default before starting, was less interactive and drier in style, but when it came back after 20 minutes of silence, the job was done. His bottom line: skilled developers could get strong results with any top model, and the differences came down to post-training goals, not raw intelligence.

That kind of detailed, credible evaluation—delivered on camera by a developer whose project has 180,000 GitHub stars—is worth more to OpenAI’s developer relations strategy than any marketing campaign. Steinberger wasn’t being paid to say it. He told Fridman that joining OpenAI “would feel so gratifying to put a price on all the work I did for free.” He was describing himself as having generated immense value for OpenAI without compensation—and he was right.

The Codex connection runs deeper than endorsement. Steinberger’s development workflow is itself a testament to what OpenAI’s coding tools can do. He ran four to ten agents simultaneously, accumulated 6,600 commits in January alone, and built most of OpenClaw’s codebase by talking to AI rather than typing. He practices what Andrej Karpathy calls “agentic engineering”—a term he prefers to “vibe coding,” which he considers a slur. His productivity on OpenClaw demonstrated at scale what Codex could enable, and that demonstration drove developers to try OpenAI’s tools.

Bringing Steinberger inside means that connection becomes structural rather than accidental. The developer who proved what Codex could do in the wild now works for the company that makes Codex. Every future version of Codex will benefit from the feedback loop of someone who has shipped a 180,000-star project using it.

But the developer angle is only part of the story. The deeper strategic logic is about agents.

OpenAI has been talking about agents for months. Their Responses API, Agents SDK, and AgentKit represent building blocks for multi-step workflows. Codex has evolved from a code-completion tool into what they describe as a “coding surface” combining reasoning-capable models with developer tools. Sam Altman told reporters that AI models “don’t run out of dopamine” and “keep trying, they don’t run out of motivation.”

What OpenAI has not had is a consumer-facing agent product that people actually use in daily life to manage real tasks—email, calendars, messaging, file management—across their own devices. OpenClaw demonstrated that it was possible. And Steinberger says he wants to build precisely that at OpenAI: an agent his mother could use.

The gap between what OpenClaw showed is achievable and what a normal person can safely deploy on their laptop is enormous. Closing that gap requires access to frontier models, security research, and infrastructure that a solo developer operating at a loss cannot sustain.

Altman’s announcement made this explicit: Steinberger’s work on “very smart agents interacting with each other to do very useful things for people” would “quickly become core to our product offerings.” Read that as a product roadmap, not a compliment.


## The Security Problem That Preceded the Hire

You cannot understand this deal without understanding the security crisis that shadowed OpenClaw’s growth.

In late January 2026, security researcher Mav Levin of DepthFirst disclosed CVE-2026-25253, a high-severity vulnerability (CVSS 8.8) that allowed one-click remote code execution through a crafted malicious link. The attack chain was devastating in its simplicity: clicking a link triggered a cross-site WebSocket hijacking attack because OpenClaw’s server didn’t validate the WebSocket origin header. An attacker could extract the victim’s authentication token and connect to their local OpenClaw gateway, disable safety controls, and execute arbitrary commands—even on instances configured to listen only on localhost.

The patch shipped in version 2026.1.29 on January 30. But the broader picture was alarming. Censys identified 21,639 exposed OpenClaw instances publicly accessible on the internet—up from around 1,000 just days earlier. Misconfigured instances were leaking API keys, OAuth tokens, and plaintext credentials. Moltbook’s database was found exposing user email addresses and agent API tokens at scale—Reuters reported over 6,000 owner emails and more than a million credentials, though other outlets cited higher figures. Security firm Snyk reported that 7.1% of nearly 4,000 skills in ClawHub mishandled secrets like API keys through LLM context windows. Zenity disclosed indirect prompt injection risks that could enable backdoors through trusted integrations like Google Docs.

The story drew detailed writeups across security outlets and Hacker News. Reco, the SaaS security company, flagged OpenClaw as a new class of “shadow AI” risk—autonomous agents with shell access, persistent memory, and zero enterprise visibility.

Steinberger responded with a blitz of security updates. Version 2026.2.1 on February 1 brought TLS 1.3 minimums, system prompt guardrails, path traversal fixes, and exec injection patches. Version 2026.2.6 on February 7 added a code safety scanner and support for new models. And version 2026.2.12—released on February 12, just two days before Steinberger’s blog post—was the big one: 40-plus dedicated security patches addressing SSRF, prompt injection, RCE in browser control, unauthenticated configuration tampering, and a bundled hook identified as “soul-evil” that had inadvertently remained in the codebase.

The timing is telling. Steinberger shipped the largest security update OpenClaw had ever released in the same week he was finalizing his decision to join OpenAI. He didn’t leave the project in a vulnerable state. He fortified it, then handed it to a foundation.

This also explains part of OpenAI’s calculus. The security challenges OpenClaw faced are not unique to OpenClaw. They are inherent to the category. Any company shipping autonomous agents that can access email, execute shell commands, and manage calendars will face exactly these problems. Steinberger has now lived through them—the CVEs, the exposed instances, the malicious skills, the crypto scammers, the credential leaks—and developed practical responses to each. That experience is operationally valuable to OpenAI in a way that no amount of theoretical security research can replicate.


## What Changes for OpenClaw

For the 600 contributors and hundreds of thousands of users, the immediate answer is: not much, and also everything.

OpenClaw will move to a foundation structure. It will remain open source. It will continue supporting multiple models—not just OpenAI’s. Steinberger has been explicit that the project should grow to support even more model providers and companies. OpenAI has committed to continuing its sponsorship of the project.

The Chrome-Chromium analogy that Steinberger used in his Lex Fridman interview is instructive here, though perhaps not in the way he intended. Chrome is built on the open-source Chromium project, but Google’s influence on Chromium’s direction is dominant. Google engineers contribute the majority of commits, set architectural priorities, and the features that make it into Chrome shape what Chromium becomes. Independent Chromium-based browsers exist—Brave, Vivaldi, Edge—but they operate within a framework largely defined by Google’s priorities.

The risk for OpenClaw is similar. With Steinberger inside OpenAI, the project’s founder and most prolific contributor will inevitably be influenced by his employer’s priorities. Features that align with OpenAI’s product roadmap may get faster attention. Features that compete with OpenAI’s offerings may not. The foundation structure is designed to mitigate this, but foundations are only as independent as their governance allows, and the details of OpenClaw’s foundation—board composition, funding sources, contribution policies—have not been announced.

There is also a practical question about the 3,000-plus open pull requests that Steinberger mentioned before the deal. He committed to processing them regardless of his decision. But a solo developer becoming a full-time OpenAI employee will necessarily have less discretionary time for open-source maintenance. The community will need to develop its own leadership bench.

The upside for OpenClaw users is real, though. OpenAI has resources—compute, security teams, model access, infrastructure—that an independent project cannot match. If OpenAI follows through on its commitment to sponsor the project meaningfully, OpenClaw could get more robust faster than it would have as a one-person operation hemorrhaging cash. The security hardening alone could benefit enormously from access to OpenAI’s security research.


## Where OpenAI Goes Next

Altman’s phrasing—that Steinberger’s work would “quickly become core” to OpenAI’s product offerings—points to a specific product direction. OpenAI appears to be building toward a consumer agent product that goes well beyond ChatGPT’s current capabilities.

Consider what OpenAI now has in its portfolio. Codex handles coding agents. ChatGPT handles conversational AI. The Responses API, Agents SDK, and AgentKit provide developer infrastructure for multi-step workflows. What’s missing is a persistent, always-on personal agent that manages the messy, cross-platform reality of how people actually use their computers and phones—the email triage, the calendar conflicts, the Slack follow-ups, the file organization, the proactive task management.

That’s exactly what OpenClaw demonstrated was possible. And that’s exactly what Steinberger says he wants to build at OpenAI: an agent his mother could use.

The technical challenges are formidable. OpenClaw’s security crisis proved that giving an AI agent broad access to a user’s digital life creates attack surface that current security models struggle to contain. Steinberger’s own maintainer, known as Shadow, warned on Discord that if someone can’t understand how to run a command line, “this is far too dangerous of a project for you to use safely.” Making that same capability safe for non-technical users—Steinberger’s mother, your mother—requires solving problems of sandboxing, permission management, data sovereignty, and model reliability that are at the frontier of what anyone in the industry knows how to do.

Altman’s mention of “very smart agents interacting with each other” also signals interest in multi-agent architectures—systems where specialized agents collaborate to complete complex tasks. This aligns with what OpenAI demonstrated in its Harness engineering case study, where a team of three engineers used Codex to produce over 1,500 pull requests across a million-line codebase with zero human-written code. The extension of that model from coding to personal productivity seems like a natural next step.

The competitive implications are significant. Anthropic’s Claude Code dominates the developer tools market. Google is investing in Gemini-based agent capabilities. Meta courted Steinberger personally—Zuckerberg reached out via WhatsApp, and they reportedly spent 10 minutes arguing about whether Claude or GPT was the better coding model. Microsoft, which invested heavily in OpenAI, has its own agent ambitions through Copilot. Apple has been conspicuously quiet on agents but controls the hardware and OS layer that any personal agent must ultimately run on.

Steinberger’s hire gives OpenAI a credible claim to the personal agent space—not because of any proprietary technology, but because of proven execution. He built something that nearly 200,000 people starred on GitHub. He did it in three months. And he did it in a way that generated the kind of organic enthusiasm that no marketing budget can buy.


## The Bigger Picture

Steinberger told Lex Fridman that OpenClaw-style agents would kill 80% of apps. His logic is straightforward: every app is just a slow API, and an agent that already knows your location, sleep patterns, stress levels, and calendar doesn’t need you to open a separate application for fitness tracking, food ordering, or scheduling.

That prediction may prove aggressive in its timeline and conservative in its scope. The more fundamental shift is not about replacing apps but about changing the interface layer between humans and software. For thirty years, the dominant paradigm has been graphical user interfaces—icons, menus, buttons. For the past fifteen, it’s been touch interfaces on mobile devices. What OpenClaw demonstrated, imperfectly and at great personal cost to its creator, is a third paradigm: delegation. You don’t tap an icon or type a query. You tell an agent what you want done, and it figures out the APIs, the tools, and the sequence of steps on its own.

The fact that this paradigm emerged not from a corporate lab but from a single developer’s living room in Vienna is itself instructive. It suggests that the hard problem in agentic AI is not primarily one of model capability—the underlying LLMs were already good enough—but of integration, persistence, and the willingness to give an AI system real access to real things. Steinberger’s contribution was not a new algorithm. It was glue code, architecture decisions, a messaging interface, and the audacity to give an AI agent the ability to rewrite itself.

Now that audacity lives inside OpenAI. The question is whether it survives the transition from indie hacker project to corporate product, and whether the foundation model preserves enough independence to keep the open-source community invested.

The lobster has molted for the last time. What it grows into next depends on whether the new shell fits.

[![](https://substackcdn.com/image/fetch/$s_!WD6j!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff837e0c6-0afb-4c6a-ad8b-12ae51ef0a14_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!WD6j!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff837e0c6-0afb-4c6a-ad8b-12ae51ef0a14_1024x1024.png)
