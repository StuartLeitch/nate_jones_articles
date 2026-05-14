---
title: "Your automation strategy has a blind spot the size of your entire legacy stack. Codex just filled it."
author: "Nate Jones"
published: 2026-04-23
url: https://natesnewsletter.substack.com/p/grab-the-workflow-audit-that-tells
audience: everyone
scraped_at: 2026-05-14 14:33:08
---

The conventional read on the April 16 Codex release is that OpenAI added computer use, an in-app browser, and a bunch of plugins. That’s the feature list. The feature list isn’t the story.

The story is that OpenAI now has a credible path into every piece of software with a graphical interface, and they got there without needing a single vendor to cooperate. The agent just drives the interface you already drive.

Think about what that changes. Six months ago, any software that didn’t have an API was outside the automation conversation entirely. Internal dashboards, legacy vendor portals, the app your company built in 2019 and never maintained. That software just came back inside the conversation, through a door that doesn’t require anyone’s permission to open.

Anthropic made the same bet on getting agents out of the coding box, but through structured interfaces that depend on the ecosystem building for agents first. Both labs are headed to the same destination. The paths they chose are fundamentally different, and the difference determines which software your agents can actually reach today.

**Here’s what’s inside:**

- **The mechanism nobody’s framing right.** Why computer use changes what’s automatable and why structured integrations carry a dependency most people are underweighting.
- **Who actually built this.** The twelve-person team whose line from Apple Shortcuts to Codex explains why this works when prior computer-use demos didn’t.
- **Two theories of where agents are going.** Chronicle vs. Conway, ambient context vs. event-driven agents, and what each tells you about the next eighteen months.
- **When to use which.** The specific capability where the gap is wide enough to change your stack, and the capabilities where Claude still wins.
- **What to watch.** Two signals that will tell you which path is paying off before consensus catches up.
- **Three prompts to act on this.** A workflow audit that maps where to deploy each agent, a dependency assessment for your automation stack, and an acquisition signal tracker you’ll reuse every time a deal drops.

I’ve been testing both side by side for weeks. The gap on computer use is bigger than I expected.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260421_ozj_promptkit_1)

Most people will read this piece and walk away with a better mental model. That’s fine. But the model doesn’t become useful until you apply it to your own stack. The workflow audit prompt forces you to inventory every piece of software you actually touch in a week, classify it by interface type, and output a triage map that tells you where to deploy Codex, where to deploy Claude, and what to leave alone. The dependency assessment does something different: it maps the fragility in your current or planned automations, finds the single points of failure, and shows you whether you’re over-indexed on connectors that could break or GUIs that could change. The acquisition tracker is the one you’ll keep coming back to. Every time a lab acquisition crosses your feed, run it through the framework and update your read on where the competition is actually headed. [LINK: placeholder]


## Both labs got out of the coding box

For most of 2025, the agent story was about code. Claude Code and Codex CLI were the leading products, the benchmark fights were about SWE-Bench and Terminal-Bench, and the interesting questions were about developer productivity. That’s not the story anymore, and both labs pivoted within a few months of each other.

Anthropic moved first. Cowork shipped as a research preview in January 2026, inside the existing Claude desktop app. The framing was explicit: Claude Code for people who don’t write code. Point the agent at a folder, describe an outcome, and it does multi-step knowledge work. From there it was compound moves: plugins, scheduled tasks, computer use in research preview on macOS in March and Windows in April, Dispatch for phone-to-desktop handoff, then Opus 4.7 and Claude Design. Just under four months in, the Claude app holds three modes on one surface (Chat, Cowork, Code) plus a plugin layer for specialized capabilities. The bet is that knowledge work is the prize, and the app is the way to reach it.

OpenAI started Q1 behind on this category. They had the strongest model, the largest consumer footprint, and the best coding CLI, but no agentic desktop product for non-developers. The Codex desktop app launched February 2 on macOS. GPT-5.3-Codex on February 5. Windows on March 4. GPT-5.4 on March 5, which folded the Codex coding capability into the general-purpose model line. The super-app consolidation plan confirmed on March 19. The April 16 “Codex for (almost) everything” release was the culmination: one app, one agent, one mode, with computer use as the headline feature.

Both labs have now publicly committed to the same prize. The thesis is identical: agents are coming for knowledge work, not just for code. The April 16-17 window, where both shipped major releases on the same day, isn’t a coincidence. It’s the two bets landing in public at the same moment.


## The move nobody’s quite framing right

Anthropic’s path out of the coding box runs primarily through structured interfaces: file operations in Cowork, MCP servers, connectors, the three-thousand-plus integrations already in the Claude ecosystem, and the leaked Conway project which uses webhook triggers and a proprietary .cnw.zip extension format. All of that is excellent architecture. It also depends on the ecosystem cooperating. MCP servers have to be built, connectors maintained, webhooks configured. The agent’s reach is bounded by how fast the world ships agent-native interfaces.

OpenAI’s path out of the coding box runs primarily through computer use. The agent drives the same graphical interface a person drives. That changes the math, because it means the agent’s reach is bounded by how much software has a GUI — which is effectively all of it. No vendor has to ship an integration, no standard has to ratify, no ecosystem has to mature. Legacy enterprise software works, and so do internal tools, SaaS that will never build an MCP server, and the vendor portal your ops team tolerates.

The products look similar on a feature matrix. The strategy underneath isn’t.

On computer use specifically, the gap is wider than the coverage suggests. Codex is fast. It moves through a GUI workflow at something close to the speed of a person who already knows the software, not the apologetic crawl most computer-use demos have shown for the last year. Claude’s version, running comparable tasks, is slower: the cursor hesitates, the agent rethinks, retries are common. Tasks that finish in two minutes on Codex take five or six on Claude.

It also just works, which is a separate and more important claim. The failure mode of computer-use products for the last year has been: the agent gets seventy percent of the way through a task, hits an unexpected modal dialog, fumbles, and you take over or restart. Codex’s implementation doesn’t fumble. It backs up when it needs to. It finishes. That reliability moves the capability from “impressive in demos” to “I actually deploy this.”

The underlying model explains some of the gap. GPT-5.4 is the first general-purpose model OpenAI has shipped with native computer-use capabilities baked in. Its OSWorld-Verified score of 75% puts it above the 72.4% human baseline for GUI control. The engineering on top matters too. Alexander Embiricos called the background computer-use implementation “deep OS-level wizardry,” and the key choice was that background agents don’t hijack your cursor or steal focus. You can keep typing while an agent is clicking on the same screen.

Three Codex agents on three unrelated tasks, walk away, come back twenty minutes later, three tasks done. That changed how I schedule my day.

Since the April 16 release, early adopters have been posting their first real deployments, and the range is wider than I expected. Mass-clearing Slack by reading and triaging hundreds of unread bot messages. Walking through a frontend app to catch visual regressions while the developer keeps shipping on the next feature. Reproducing a browser bug, screenshotting the repro, and pasting the images straight into a pull request. Driving a legacy internal dashboard that never had an API, exactly the category of software automation has given up on for years. One user wired up a daily recap that pulls git commits, issue tracker updates, and calendar events, writes meeting minutes into Notion, and drops prioritized todos into Apple Reminders.

None of those are demos. They’re workflows people ran once and then kept running. Computer use stops being a novelty when you reach for it the second time.


## Who actually built this

Codex’s computer use didn’t come from nowhere. In October 2025, OpenAI acquired Software Applications Incorporated, the team behind Sky, an unreleased macOS-native AI interface that did essentially what Codex’s computer use does now. All twelve members joined OpenAI. Ari Weinstein, one of Sky’s co-founders and now at OpenAI, announced the computer-use launch and called it “the first time I’ve ever seen an LLM operate a GUI as fast as a person.” The cursor motion work that makes background computer use feel like a coworker instead of malware traces back to his team’s decade of OS-level automation experience.

Weinstein and his co-founder Conrad Kramer previously built Workflow, the iOS automation app Apple acquired in 2017 and turned into Shortcuts, which is now the system-level automation layer across iOS, iPadOS, and macOS. Sky’s third co-founder, Kim Beverett, spent a decade at Apple as a senior program and product manager working on Safari, WebKit, Privacy, Messages, Mail, Phone, FaceTime, and SharePlay. That’s a decade-plus build of exactly the skill set that makes Codex’s background computer use work the way it does: deep macOS integration, accessibility and screen-recording permission handling, motion paths that don’t feel robotic, OS-level hooks nobody else knows how to implement cleanly.

As far as I know, there is no other team in the world with this combination of experience. Workflow to Shortcuts to Sky to Codex is a line that only exists in one place. OpenAI paid for that line, and the payoff is visible in the April 16 release. The “deep OS-level wizardry” Embiricos described isn’t a metaphor. It’s a specific team’s specific accumulated knowledge, now applied to a product where it matters commercially.

The same pattern shows up elsewhere. Anthropic’s Vercept acquisition earlier this year — the team that shipped Claude’s Windows desktop control within four weeks of joining — is the parallel move. io, the Jony Ive hardware startup OpenAI bought for roughly six and a half billion dollars, is a larger version of the same thing. The labs are spending heavily on talent density in narrow, hard-to-replicate capabilities. Not for the IP, and often not even for the product. For the team.

In an age where models are converging and headline capabilities are moving toward commodity, extraordinary human teams are one of the few remaining moats. The Sky team is the clearest current example. It won’t be the last. If you’re watching the lab-to-lab competition, the acquisition pattern is telling you more about where advantage will live than the benchmark scores are.


## Two theories of the ecosystem

Chronicle shipped on April 20 as a research preview for ChatGPT Pro on macOS. It captures your screen periodically, processes the images on OpenAI servers, and writes local markdown memory files that Codex pulls into future sessions as context. Thibault Sottiaux, who heads Codex, called it early and token-hungry but said it had changed how he and many people at OpenAI work. Altman described it as “telepathy-like.”

The shallow read is that Chronicle is an ambient-memory feature. The deeper read is that Chronicle is the training signal for computer use. If your agent is going to drive the same GUI you drive, it benefits enormously from watching how you drive it. Chronicle is the layer that makes driving the UI smarter over time: your workflows, your app preferences, your muscle-memory patterns become context the agent inherits. The privacy tradeoff (screen captures sent to OpenAI servers, unencrypted local memories, not available in the EU, UK, or Switzerland) is a cost OpenAI accepted because the feature works better with it, and because the data makes the agent better at driving your software over time.

Conway is a different kind of signal. On March 31, Anthropic accidentally published the Claude Code source — roughly five hundred thousand lines of TypeScript — when a packaging error pushed it to a public registry. Buried inside was Conway: an always-on, event-driven agent environment with its own sidebar UI, three panels (Search, Chat, System), webhook-triggered invocation, the .cnw.zip extension format, browser control via Claude in Chrome, and deep connector integration. I’ve written about this at length separately. The short version: Conway assumes the world is going to build for agents, with structured triggers, explicit extensions, event-driven execution. It’s designed to plug into agent-native interfaces that other companies will build over the coming year or two.

That assumption matters, and most of the coverage isn’t examining it. Anthropic wins this bet if MCP adoption accelerates, if enterprise software ships clean integrations, if the standards mature quickly enough for Conway to have a rich substrate to act on. It’s a good bet in many ways: MCP is already spreading, Anthropic is the company pushing it hardest, and the developer ecosystem around Claude Code has real momentum. But it requires the ecosystem to move, and enterprise software ecosystems move slowly. The long tail of internal tools isn’t getting agent interfaces on any timeline that matters.

The practical gap comes down to dependency. Anthropic’s bet pays off only if the ecosystem builds fast enough. OpenAI’s doesn’t carry that dependency.

My read: the second scenario is more likely on the timescale that matters. But it’s a read. If enterprise software moves faster than I think, the picture changes.


## The rest of the distinctive approach

Computer use is the headline, but the two apps also look and work differently in ways that match their underlying bets.

Anthropic’s Claude app is shaped like a tool that assumes you know what kind of work you’re in. Chat mode for discussion, Cowork for bounded file operations, Code for software work. Each mode has a scoped permission model. When you open Cowork, it asks you to point at a folder. That friction is the product: it communicates what’s about to happen so you can be deliberate. The whole app is explicit in the way the rest of Anthropic’s strategy is, with explicit scopes, explicit permissions, explicit interfaces.

OpenAI’s Codex app is shaped like a tool that assumes you don’t want to think about modes. You describe the outcome. The agent decides whether to open files, drive a GUI, run a plugin, browse, or write code. Computer use is the escape hatch when nothing else works. Plugins are opinionated bundles invoked without explicit selection. Memory keeps context flowing. The app is implicit in the same way the rest of Codex is: the agent figures out what to do, because you shouldn’t have to tell it which interface to use.

In practice, both approaches work. The question is whether you want to steer or be driven.

Brockman described the super-app architecture on the Big Technology podcast as a “personal AGI”: ChatGPT as the conversation hub, Codex as the general agent plus coding capability, Atlas as the web execution layer. One app, one orchestrator, one persistent context. He also admitted that OpenAI’s compute is the binding constraint — they don’t have enough even for the two top priorities, personal assistants and Codex — which is a central reason Sora got shut down and product lines were collapsed. The super-app isn’t just a product consolidation. It’s a forced prioritization driven by what OpenAI can actually afford to run at scale.

The detail most of the coverage is missing about the consolidation: compute isn’t just the constraint at OpenAI. It’s becoming the product. If the super-app routes all user activity through a platform where compute gets billed at OpenAI’s margins, then every parallel agent running in the background is revenue. That reframes the consolidation. It’s not just a product bet. It’s a financial architecture, and it explains why the consolidation is happening now rather than later.


## What this means if you’re using these tools

Computer use is the one capability where the gap between Codex and Claude is wide enough that it should change what you use. If your work involves driving software that doesn’t have good APIs, and most enterprise software falls into this category, Codex is the product that’s ready. Claude’s computer use will get there; the research preview is improving visibly. But today, Codex wins on speed and reliability for this specific capability, and the gap is large enough that I’d deploy Codex for any workflow that depends on GUI automation.

On scoped, bounded work, Claude is still tighter. Cowork’s “point at a folder and describe the outcome” ergonomics are cleaner than Codex’s one-agent-figures-it-out for tasks where you want explicit control over what the agent touches. Claude Code remains the better tool for complex refactoring and engineering work where precision matters more than throughput. These aren’t features Codex will close tomorrow. They come from a different design philosophy, and that philosophy works for what it’s good at.

On cross-tool triage, long-running parallel agents, ambient work that doesn’t fit a single mode — Codex is the default now. Chronicle accelerates the gap for anyone on Pro who’s willing to turn it on. Parallel background agents work reliably enough that queuing three or four tasks before stepping out has become a real workflow rather than a party trick.

Use both. Which one you lean on depends on where the work actually lives. If it lives in software that’s going to get proper agent integrations, Claude’s architecture is going to get cleaner and more reliable. If it lives in software that won’t, the long tail, the legacy tools, the internal systems nobody maintains, Codex is the one that reaches it.


## Where the puck is going

Two things to watch over the next six months.

First, Conway. If Anthropic announces it publicly, event-driven agents become a real category alongside ambient-context agents and the two-paths framing crystallizes. If Anthropic delays it or quietly kills the codename, it tells you they’ve lost confidence in the ecosystem-cooperates bet on the timescale that matters, and more of the category converges on computer use plus ambient context by default.

Second, MCP adoption velocity. Anthropic’s bet on the ecosystem only pays off if MCP spreads faster than it currently is. If a major wave of enterprise vendors ships MCP servers in the second half of the year, Anthropic’s architecture looks better and better. If they don’t, or if they ship thin wrappers that don’t work as well as the actual UIs, driving the UI directly stays the better path.

Both labs are going to the same destination — persistent, ambient, event-driven, cross-surface agents that work on your behalf. The split is about how to get there. Right now OpenAI has a structural advantage that most of the coverage is underweighting. The human UI doesn’t require anyone else to cooperate. And every piece of enterprise software already has one.

The practical implication: if your workflow depends on software without good APIs, it just became automatable. For most operators, that’s most of it. And the reason it works isn’t the model. It’s a specific team with a specific history, building a body that doesn’t need anyone’s permission to move. Keep watching the acquisition pattern. It’s telling you more than the benchmarks are.

Six months ago that software was effectively off the table. It isn’t now.

[![](https://substackcdn.com/image/fetch/$s_!7yoH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Face989fe-0486-443a-a6e8-f617dfba0761_1254x1254.png)](https://substackcdn.com/image/fetch/$s_!7yoH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Face989fe-0486-443a-a6e8-f617dfba0761_1254x1254.png)
