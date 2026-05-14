---
title: "Claude Design just cut 60% of your designer's week — here's what to do with the rest + 4 prompts"
author: "Nate Jones"
published: 2026-04-24
url: https://natesnewsletter.substack.com/p/claude-design-replaced-a-week-of
audience: everyone
scraped_at: 2026-05-14 14:33:05
---

Claude Design shipped April 17 alongside Opus 4.7, in research preview. The coverage split cleanly. One camp: Figma’s stock dropped 7% and commentators argued about what that means for the design software industry. Another camp: the tool has real rough edges and commentators argued about whether those break the story. Both frames miss the point.

Sometimes a product ships with warts and the warts don’t matter. Anthropic has a pattern of shipping those. Claude Code was the first. Cowork was the second. Claude Design is the third, the one that makes the strategy finally clear.

All three do the same structural work: intent goes in as natural language, a working artifact comes out, and it hands off directly to the next product in the stack. With Design, the last big category of production work — visual artifacts, the thing every product team makes first and shows to everyone — joins Code and Cowork inside the same pipeline. The prototype isn’t an approximation of the thing anymore. It’s the thing, or one handoff away from it.

Brilliant told Anthropic that its most intricate product pages used to require twenty or more prompts to recreate in competing tools. In Claude Design they need two. Datadog compressed a week-long cycle of briefs, mockups, and review rounds into a single conversation. Earlier this year a Jane Street designer wrote publicly that he now designs in Claude more than in Figma, building working prototypes directly in the codebase instead of making Figma mocks that describe what the code will eventually do. Those aren’t demos. They’re practitioners describing what happens when the mockup-to-production handoff — the twenty-year-old ritual where designers make pixel approximations that engineers then rebuild in code — gets replaced by one conversation that produces the actual UI in the medium it will run in. Most of how your team is structured was built around that ritual. It isn’t the ritual anymore.

**Here’s what’s inside:**

- **Three products, one bet.** How Code, Cowork, and Design work the same way, and why the third one is the piece that makes Anthropic’s strategy finally legible.
- **Eight things you can actually make.** Pitch decks with live embedded AI, 3D configurators, design systems extracted from your codebase in twenty minutes, and five more — each one replacing a tool, a specialist, or a queue.
- **Figma, Stitch, and the medium war.** Why LLMs ended up working in code and markdown instead of Figma files, why Mike Krieger stepped off Figma’s board three days before launch, and why Google and Anthropic are making opposite bets on what it all means.
- **What changes, role by role.** Where PMs, designers, engineers, and founders have to move their craft upstream — and which parts of the two-pizza team stop making sense.
- **Grab the prompts.** A design system extractor that makes Claude Design stop guessing your brand, a prototype sprint that generates every UI state your team usually forgets, an org audit for roles built around costs that just vanished, and a migration decision tree for what stays in Figma.

The warts are real. They’re also the least important thing about what shipped.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260421_y1o_promptkit_1)

Most teams try Claude Design without telling it anything about their brand and then blame the model when the output looks generic. The tool works. It just doesn’t know who you are yet. These prompts fix that by forcing the decisions teams skip: what your visual identity looks like in token form, what states a prototype needs before anyone should review it, which parts of your org exist because the work demands them versus because prototyping used to take a week. The Design System Extractor exists because I’ve watched too many people open a powerful tool with zero context and then conclude the tool isn’t ready. If you can’t describe your own brand in hex codes and type choices, you’re not directing a design tool. You’re rolling dice.


## **What the compression actually looks like**

The headline numbers are striking — Brilliant went from twenty prompts to two, Datadog compressed a week into a conversation — but the real signal is in the mechanics underneath. Datadog’s PM Aneesh Kethini described the shift concretely: what used to be a cycle of written briefs to the design team, a week of mockups, then rounds of review comments, became one conversation where he’d describe a feature, watch Claude Design render it, and refine it in place until the engineering team had something to build against. The week disappeared because the thing everyone was reviewing already was the prototype, not a description of one. Jane Street’s version is sharper still. The designer built prototype features directly in the firm’s production codebase, lived with them for a few days, and used the working artifact as his proposal. Reviewers reacted to the experience, not to a drawing of what the experience might feel like. The feedback loop got better because the thing being reviewed got more real.

The specific thing Claude Design does, across the full range of visual work a product team makes, is collapse the distance between prototype and shipped artifact. A pitch deck comes out as a PPTX you can open in PowerPoint. An animated explainer video comes out as code that runs in a browser. A UI prototype comes out as HTML, CSS, and JSX ready for Claude Code to harden into production. Each output is already in the format it will live in. That’s the whole move.


## How the three products go together

All three non-chat Anthropic products work the same way. You describe what you want in plain language. Claude produces a working artifact. You refine it through conversation. When it’s ready, it hands off to the next Anthropic product. The artifact differs across the three products; the interaction pattern doesn’t.

Claude Code is the one most engineers already understand. You describe what you want built. Claude writes the code, iterates against your tests, and ships pull requests. The code it produces is the code that ships, there’s no intermediate mockup stage. Engineers who’ve used Code seriously didn’t treat it as a faster autocomplete. They restructured how they work around it, because the way Code produces software is fundamentally different from writing it yourself.

Cowork does the same move for knowledge work. You describe an outcome. Claude reads your files, runs multi-step tasks, and produces the actual artifact: a board deck built from six months of meeting notes, a competitive analysis drawn from fifty saved articles, a research directory reorganized from chaos into something usable. Same pattern as Code, applied to documents and analyses instead of software.

Claude Design extends the same pattern to visual artifacts. You describe the prototype, the deck, the landing page, or the interactive UI you need. Claude builds a first version. You refine through conversation or direct edits. Then you export it to wherever it’s going to live. The mechanics are identical to Code and Cowork. What’s new is that visual work, the part most product teams spend the most time on early in a project, just became something anyone can produce in minutes.

For most of the last twenty years, prototyping was a discrete step between spec and build, owned by a specialist designer, producing an artifact that was explicitly thrown away afterward. The prototype existed to figure out what to build. Then you built something separate, in a different medium, with translation losses at every step.

That model existed because prototyping was expensive and the prototype was disposable. A realistic interactive mock took days or weeks of designer time, which meant designers had to ration which directions got prototyped. PMs wrote specs instead of prototyping because they didn’t have the skills or the bandwidth. Engineers translated specs into code, and every translation introduced drift between what was imagined and what shipped. QA existed partly to check whether the code matched the design. Design reviews existed partly because the only way to really test a direction was to invest another designer-week building it out.

Every one of those structures was built around the same two facts: prototyping took days, and the prototype was separate from the shipped thing. Both facts just changed. Most of the team structures built around them are now compensating for something that isn’t true anymore.


## Why Claude Design is the missing piece

Before Design, Anthropic’s stack had a specific hole in it. Chat handled thinking. Cowork handled knowledge-work execution. Code handled software execution. But most product work begins with a visual artifact: a sketch, a mockup, a deck, a rough prototype screen. Visual artifacts are how people show ideas to each other when prose isn’t enough and code is too much. PMs use them to communicate features, designers use them to show direction, and founders use them to pitch products that don’t exist yet. The best PM spec I’ve seen in the last year wasn’t a twelve-page document. It was a rough interactive prototype with twelve lines of context.

Before Design, Anthropic wasn’t in that part of the workflow. You could think in Chat, execute knowledge work in Cowork, and ship software in Code, but the step where an idea became something you could show to someone happened outside Anthropic’s tools. Between “I have an idea” and “Claude Code can build it,” there was a missing step where the idea became visible.

Design closes that gap across a wider range of outputs than any comparable tool. v0 and Lovable handle web UIs. Canva handles decks and marketing collateral. Various AI video tools handle animated explainers. Claude Design handles all of those, plus 3D interactive components, data visualizations with real interactivity, full mobile app mockups with state transitions, and design systems extracted from existing codebases, and does it with your brand applied consistently across every artifact type. The path from idea to shipped product now lives in one place, using one model family, under one design system.

There’s a technical reason this works. Sam Henri Gold laid it out in a sharp post after the launch. Figma spent a decade building sophisticated design primitives — components, variables, modes, props — to make pixel-level design more expressive. Those primitives were Figma-proprietary. They weren’t in the training data for the models now doing most of the design generation. LLMs were trained on code, not Figma files. So when AI models got good at design, they got good at the medium they’d actually learned from: HTML, CSS, SVG, JSX. Code, not design files, became the working material for AI-assisted design, because code is what AI had seen.

Claude Design leans into this directly. The output isn’t a pixel approximation of a UI that has to be rebuilt in code by an engineer. It’s the actual UI, already written in the medium it will run in. The handoff to Claude Code works cleanly because the design artifact is already in the production format.

Claude Design isn’t primarily a Figma competitor. Figma will keep its position as the tool professional teams use for production-grade design work: design systems at scale, component-library maintenance, the craft work that happens in the middle of the product lifecycle. Claude Design is playing a different game. It makes visual artifacts a first-class output of the intent-to-artifact pipeline that Code and Cowork established. Figma owns the middle. Claude Design competes at the beginning (quick exploration, early prototyping) and connects directly to the end (shipped code), skipping past the middle where Figma is strongest.

Google is running a parallel play with Stitch, its own AI UI design tool. Stitch introduced DESIGN.md in March, a plain-text markdown file describing your design tokens, type scale, and component rules, which the AI reads before every generation. Google made the DESIGN.md specification openly available so any tool can read and write it, with semantic color intent built into the format.

That’s a different strategic bet from Anthropic’s. Google is wagering on standardization: expose a simple spec, let it become ubiquitous, compete on Gemini quality inside it. Anthropic is wagering on integration: extract your design system from your codebase automatically, apply it across every artifact type inside the Anthropic stack, hand off directly to Claude Code for production. Stitch is also narrower than Claude Design. It does web and mobile UIs, not decks or animations or 3D. But both companies agree on the underlying shift: code and markdown, not Figma files, are the medium AI works in. They differ on whether the moat is the spec or the stack.

Mike Krieger, Anthropic’s chief product officer, stepped down from Figma’s board three days before Design shipped. Not a coincidence.


## What you can actually make with it

The range is the story. These are things that used to require six different tools, a contractor or two, and a queue, and that now happen in one conversation.

**Pitch decks with live embedded AI.** Generate a twelve-slide Series A deck from your one-pager, with a working chatbot on slide 7 the VC can actually use in the meeting, not a screenshot of one. Export as PPTX or send to Canva. Replaces a static deck tool plus a separately-built demo.

**Animated product explainer videos.** A 45-second explainer rendered in code, which means you can tweak the palette, toggle captions, or retime after generation without starting over. Replaces After Effects or a motion graphics contractor.

An example I created for [AI CRED](https://www.aicred.ai/):

Could not load video.

**3D interactive components.** Product configurators, data globes, orbit-controlled viewers. The kind of thing that used to take three weeks of WebGL work comes out running, with customization sliders Claude generates alongside it. Replaces a custom engineering project.

**Design systems extracted from your codebase.** Point it at your repo, get a design system file in twenty minutes: tokens, type scale, components surfaced from CSS it’s never seen before, applied automatically to every subsequent generation. Replaces a multi-week design-ops engagement.

**Web capture and re-skin.** Grab any competitor’s landing page through the web capture tool, re-render it in your tokens, and you have a branded reference prototype in ten minutes. Replaces a designer inspiration board plus a rebuild from scratch.

**Interactive dashboards and data views.** Build a live, manipulable analytics view as a shareable URL instead of exporting screenshots into a static report. The reader changes parameters; the chart updates. Replaces screenshot-from-Tableau-paste-into-doc.

**Internal admin tools in an afternoon.** Moderation queues, ops dashboards, billing admin panels, the backlog every company has in half-finished state because customer-facing work always took priority. Replaces engineering time that was never going to come.

**Mobile app prototypes with real state transitions.** Multi-screen flows where the transitions between screens actually work, every state drawn by default (empty, error, loading, high-volume, low-volume), ready to hand to Claude Code for production. Replaces static screens plus a separate prototyping tool.

The common thread: each output used to require either its own tool or its own specialist, and the artifact it produced was a rough approximation of the shipped thing. Claude Design produces each one as code that runs in the medium it will live in, inside the same project, under the same design system.


## What changes, role by role

The shift shows up differently in each role, but the underlying change is the same: the distance between having an idea and having something you can show someone dropped from days to minutes, and the shown thing is either the shipped artifact or one step from it.

**For PMs**, the PRD stops being the default artifact. Prototyping a feature communicates what you want better than describing it does, and prototyping now costs minutes. The PMs getting the most out of Design produce a working prototype first, then use it as the thing everyone discusses: engineers scope against it, designers critique it, leadership decides whether to build against it. Prose docs still have a role for pricing, positioning, and go-to-market, decisions that actually need prose, but they stop being where every product conversation starts. Design reviews shift from critiquing static mockups to discussing working prototypes, which is a meaningfully better meeting.

The concrete workflow: paste your user stories and acceptance criteria into Design, prompt for a flow that satisfies them, generate the empty, error, and loading states by default, and put the prototype in the Jira ticket instead of the spec doc. Thirty minutes, end to end. If the feature involves AI behavior, you can embed real model calls in the prototype, so engineering isn’t reviewing a mockup of a chatbot onboarding, they’re using a working chatbot onboarding. For async stakeholder review, you can ask Design to generate a short video walkthrough of your own prototype, which sits in the ticket alongside the clickable version.

**For designers**, the rationing stops. Designers used to have to choose: prototype two directions or just one? Explore or commit? Those calculations no longer matter, because ten directions in an hour is routine. The craft moves upstream: less time making mockups, more time deciding which directions are actually good, and why.

Jenny Wen runs design at Anthropic and previously led FigJam and Slides at Figma. Her framing of the shift inside her own team: mocking and prototyping used to eat 60 to 70% of her day; now it’s 30 to 40%, with another 30 to 40% spent pairing directly with engineers in code. The discovery, mock, iterate, handoff process she was trained in has been replaced by something more continuous, with selection and taste as the craft instead of execution. Professional designers I’ve talked to describe this as getting three hours of their day back, not as getting replaced.

**For engineers**, the handoff changes. Instead of starting from a spec document, you start from a working prototype packaged with a Claude Code handoff bundle, already written in HTML, CSS, and JSX. The conceptual design work, what this thing needs to do, how it should behave, what the UI looks like, moved into the prototyping stage. Your job moves too: less time translating docs into code, more time hardening a working system into something production-ready: security, testing, scale, and the edge cases that didn’t show up in the prototype.

And because a Design prototype can embed real API and model calls, the version you receive isn’t a dead mockup. It’s a functional slice of the system with behavior you can probe, which makes it easier to see what the production architecture needs to look like before you commit to building it. Earlier this year a Jane Street designer wrote publicly about this loop end-to-end, building prototype features directly in the codebase, living with them for days, using the working artifact as the proposal instead of a Figma file describing it. The feedback he got on the running prototype was sharper than anything he’d gotten on mocks — people were reacting to the actual experience, not to a drawing of what it might feel like.

**For founders and operators**, the biggest shift is the pitch-to-prototype loop. You demo the product you’re describing instead of showing screenshots of it. For AI-native founders specifically, Design lets you embed real model calls in the prototype, so the chatbot onboarding in your pitch deck is a working chatbot, the agent workflow in your investor memo is an agent running the workflow, the voice assistant in your demo is actually listening and responding. Fundraising conversations change when what you’re pitching is running, not promised. Operations get lighter when the internal tools that would have sat half-finished for a quarter ship in an afternoon. The first cohort of founders who walk into VC meetings with live embedded AI in their decks will have a serious edge. Almost nobody is doing it yet.


## What this means for teams, not just systems

This doesn’t just change the design process. It changes the org chart.

Two-pizza teams became the standard at Amazon and spread across the industry because coordination overhead was real. Design, product, engineering, and QA each had enough specialized work that splitting them into roles was more efficient than training generalists. The coordination tax was lower than the specialization gain. That math held for twenty years.

That math is changing. When every role can prototype, the walls between roles start coming down. PMs can produce designs, designers can ship code, engineers can write specs. The coordination tax drops because there are fewer handoffs, with each person able to do more of the process themselves.

Rajeev Rajan, then Atlassian’s CTO, told the Pragmatic Summit in February that some of his teams are writing zero lines of code. His phrasing: it’s all agents, or orchestration of agents. Those teams produce 2-5x more output than the previous model. At a parallel gathering that week in Deer Valley, a head of engineering at a 200-year-old agriculture company said two-pizza teams at his company are turning into one-pizza teams. About 20 engineering leaders across the two events confirmed the trend.

Claude Design adds to this by bringing the third specialist function, design, into the same pattern that Code and Cowork already enabled for engineering and knowledge work. A PM who can prototype doesn’t need to queue for a designer. A designer who can ship code doesn’t need to queue for an engineer. Your team gets smaller and faster, because each person can run more of the process themselves.

The same question that applies to your code applies to your team: which parts of your structure exist because the work genuinely requires them, and which parts exist because prototyping used to be expensive? The five-person design team that maintained mockups and handed them to engineering existed because prototyping cost designer-weeks. The QA team that verified engineering output matched design intent existed partly because the translation from Figma to code was lossy. The PM to designer to engineer handoff ritual existed because each role owned an artifact the others couldn’t produce. Those structures existed because prototyping was expensive. That’s no longer true.


## What to know going in

The Pro plan burns through weekly limits fast. Serious daily use needs Max at $100 or $200. This is a Max-tier tool if you’re going to lean on it, not a Pro-tier novelty.

Design is SVG-first, not pixel-first. There’s no native image generator. When Design needs an image, it produces SVGs, which it does well, but it’s a layout and structure tool, not a generate-me-art tool. That’s a deliberate trust-and-safety stance from Anthropic. For most product work it doesn’t matter. For marketing collateral that needs real photography, you hand off to Canva for the final compositing.

Professional design teams still live in Figma for production work. Design systems at scale, component-library maintenance, the deep craft work: none of that moves to Claude Design in V1. The tool raises the floor dramatically (non-designers producing decent work) and the ceiling somewhat (pros exploring further than before). The production middle stays where it is.

The model has aesthetic defaults you need to steer past. Opus 4.7 defaults toward cream backgrounds, serif display type, and terracotta accents, an editorial-hospitality aesthetic that looks great for a boutique hotel and wrong for a fintech dashboard. The fix is straightforward: specify your palette in the opening prompt, give it hex codes, point it at your brand site via the web capture tool, or let it extract tokens from your codebase. It follows the steering. What it won’t do is pick the right aesthetic for your company without you telling it. That’s a prompting skill to build, not a model problem.


## What stays

Not everything changes.

Brand strategy, positioning, and the taste judgments that make a product distinctive: all of that stays, because none of it was about prototyping cost. Claude Design will give you ten directions in an hour. Deciding which direction is on-brand for your company is still your job.

Design review boards in regulated industries — financial services, healthcare, legal — stay because those reviews are about compliance and liability, not production speed. Faster prototyping doesn’t remove the need for approval; it changes what you’re approving.

Human judgment about which problem to solve stays, because Claude Design can’t tell you what matters. It can show you what a solution might look like, once you’ve decided what to solve.

The execution work of design compresses: making mocks, making handoffs, maintaining consistency. The judgment work expands: choosing directions, directing the agent, deciding what’s on-brand. Treat Claude Design as a replacement for judgment and you’ll just ship faster. Treat it as leverage for judgment you already have, and you’ll ship better.


## The cost that disappeared

Three major product releases from Anthropic in roughly nine months: Claude Code, Cowork, and now Claude Design. All three do the same structural work. They take intent expressed in natural language and turn it into a working artifact, refined through conversation, ready to hand off to the next product. Each release removes a production bottleneck in a role that used to be slow: engineers first, then knowledge workers, now designers and anyone else producing visual work.

Read as three separate products, they look like category expansion: a coding tool, a document tool, a design tool. Read as three expressions of one bet, they look like the foundations of a new way of working, where the distance between idea and shipped artifact collapses to a conversation.

The Figma-vs-Design story was never the actual story. The real story is what happens to product organizations when prototyping stops being expensive and the prototype stops being separate from the shipped thing. Most of how your team is structured, the two-pizza teams, the design handoffs, the spec-then-build cycles, the careful rationing of exploration, the QA that catches translation drift between design and code, was built around an assumption that prototyping costs days and ships as a separate artifact afterward. Both halves of that assumption stopped being true. Every structure built on top of them is now compensating for costs that aren’t real anymore.

The warts are real. They don’t matter. The question isn’t whether Claude Design is a Figma killer. The question is how much of your team was built around a cost that just disappeared.

[![](https://substackcdn.com/image/fetch/$s_!tbzT!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faa272399-524e-4baf-9ead-a5e2bbe908d6_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!tbzT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faa272399-524e-4baf-9ead-a5e2bbe908d6_1024x1024.jpeg)
