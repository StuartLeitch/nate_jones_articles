---
title: "The Company Everyone Says Lost the AI Race Is Building the Layer Every AI Winner Has to Use."
author: "Nate Jones"
published: 2026-03-31
url: https://natesnewsletter.substack.com/p/the-company-everyone-says-lost-the
subtitle: "Watch now | Apple isn't building a chatbot -- they’re building the agentic runtime."
audience: everyone
scraped_at: 2026-03-31 12:00:17
---

Everyone thinks Apple lost the AI race. Google shipped agentic features on Android months ago. OpenAI has 900 million weekly users. Anthropic’s agents are writing compilers. And Apple, the company with more than 1.5 billion iPhones in the pockets of the highest-spending consumers on Earth, is still shipping notification summaries that hallucinate news headlines.

Apple isn’t behind. Apple is playing a different game. And if the evidence is right, it’s the game that matters more.

While every AI lab races to build the best model, Apple is quietly building the platform layer that every model will have to pass through to do anything useful on a phone. Not a chatbot. An agentic runtime baked into the operating system itself, one that positions Apple as the chokepoint between users, AI agents, and every application on the device. The model race is a content play. The runtime is a platform play. Apple has never lost a platform play. Meanwhile, OpenAI is pouring billions into a hardware bet with Jony Ive to build the distribution that Apple already owns for free. That is not a company you count out.

Last week, Mark Gurman published the most detailed leak yet on Apple’s Siri overhaul ahead of WWDC on June 8. The headline everyone will write: Siri finally becomes a chatbot.

The chatbot is the skin. The skeleton is far more consequential, and almost nobody covering WWDC is talking about it.

**Here’s what’s inside:**

- **The evidence chain.** Four interlocking signals that reveal Apple isn’t building a chatbot competitor. It’s building the operating system layer that every AI model has to pass through to do anything useful on your phone.
- **The MCP detail nobody is covering.** Apple is wiring the industry’s standard agent protocol directly into iOS. That changes the math for every developer and every AI company, not just Siri.
- **Google’s impossible position.** The Gemini deal that looks like a win-win has an asymmetry buried in it that favors the company controlling the model.
- **What the delay actually tells you.** Why Apple’s lateness looks a lot like every other platform shift Apple has been late to and then won.
- **What you should do before June.** Specific actions for developers, product leaders, and anyone building with AI right now.
- **Four prompts to run this week.** One for each role: iOS developer, SaaS builder, product leader, knowledge worker. Each one gathers your context and builds a concrete action plan tied to the WWDC timeline.

The architecture ships this fall. The window to position for it is the next ten weeks.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260325_z8h_promptkit_1)

This analysis maps the strategic landscape. The prompts turn it into something you can act on before the landscape shifts.

Each prompt targets a different role because the agentic transition hits differently depending on where you sit. If you build iOS apps, the clock is ticking on App Intents adoption and you need a sprint plan scoped to your actual app and team size. If you ship a SaaS product, Apple’s system-level MCP support could give you distribution to 1.5 billion devices at near-zero marginal cost, but only if you structure your capabilities to take advantage of it. If you lead product or engineering, the question is no longer “do we have an app?” but “can an agent use our app?” and the scoring framework in Prompt 3 will tell you exactly where you’re exposed. And if you’re a knowledge worker who uses an iPhone every day, Prompt 4 takes your actual daily workflows and teaches you the delegation reflex that Apple’s agentic Siri is being built to serve.

These are not generic templates. Each one opens by asking about your specific situation, then builds a plan around what it learns. Run them in ChatGPT, Claude, or Gemini. Pick the one that matches your role, or run all four if you wear multiple hats.


## The evidence chain

There are four interlocking signals. Each one is interesting alone. Together they describe a strategy that is architecturally distinct from anything Google, OpenAI, or Microsoft is doing.


## The Siri overhaul

According to Gurman, the new Siri, codename Campo, ships as a standalone app for iPhone, iPad, and Mac. The main interface displays prior conversations in a list or grid. You can pin chats, search across interactions, start new conversations via a plus button. The conversation view looks like Messages: chat bubbles, text entry field, a toggle for voice mode, an option to upload documents and photos for analysis. When you start a new conversation, Siri offers suggested prompts based on prior usage.

This is the surface-level story, and it’s the one that will dominate headlines. Siri looks like ChatGPT now. Fine. But the chatbot app is actually the least interesting part of what Gurman described.

The more significant details are the entry points. Apple is testing a systemwide “Ask Siri” toggle that appears in menus across built-in apps. Highlight text in Safari, tap Ask Siri, and the selected content drops into a new Siri conversation. Pull up related emails. Get deeper context on what you’re reading. A “Write with Siri” option surfaces the Writing Tools menu directly from the keyboard, solving the discoverability problem that buried one of Apple Intelligence’s most useful features. And Spotlight, the search interface that’s been the default way to find anything on an Apple device for two decades, gets replaced by a unified Siri surface that handles both local content queries and broader requests in one place.

Craig Federighi told Tom’s Guide and TechRadar after WWDC last year that building a chatbot was “never the goal,” and that Apple wanted AI integrated “within reach whenever you need it” rather than sending users into a separate chat interface. The chatbot app is a concession to market reality. The systemwide entry points are the actual strategy. Apple doesn’t want Siri to be a destination. They want Siri to be the layer between you and everything else on the device, an ambient agent you invoke from wherever you already are.

That distinction, agent as a layer versus agent as an app, is the design decision that makes everything else possible.


## App Intents as the agentic API surface

This is the developer plumbing that turns the conversational interface into something that can actually do things. And it’s the piece that most non-developer coverage gets wrong or ignores entirely.

App Intents is Apple’s framework for letting apps expose structured actions to the system. It’s been around since iOS 16, but Apple supercharged it at WWDC 2024, launching twelve App Intent domains: Books, Browsers, Cameras, Document Readers, File Management, Journals, Mail, Photos, Presentations, Spreadsheets, Whiteboards, Word Processors. Each domain contains predefined, pretrained intents that Siri can invoke.

The practical version: instead of opening a photo-editing app, tapping through three menus, selecting a filter, applying it, and hitting save, you say “Apply a cinematic preset to the photo I took of Sarah yesterday.” The App Intent makes the action addressable by an agent without walking through the UI. The agent doesn’t need to understand the app’s interface. It talks to the intent directly.

Apple has been testing expanded App Intents on Uber, Amazon, Facebook, Threads, Temu, WhatsApp, YouTube, AllTrails, and a handful of games. The stated trajectory: Siri can scroll through menus, add items to carts, edit photos, comment on social posts, entirely by voice. Over time, Apple plans to extend this further by enabling voice-driven navigation of arbitrary app interfaces, not just apps that have adopted the framework.

This is the difference between a chatbot and an agent. A chatbot answers questions. An agent takes actions inside applications on your behalf, coordinating across multiple apps to complete multi-step tasks. App Intents is what makes the second thing mechanically possible on Apple’s platform, and the developers who haven’t adopted it yet are about to discover that their apps become invisible in an AI-first operating system. If Siri can’t act on your app, Siri can’t recommend your app. If Siri can’t recommend your app, your app doesn’t surface when a user says “order me dinner” or “book a ride” or “schedule that meeting.”

The parallel to search engine optimization a decade ago is almost exact. Apps that don’t expose intents are apps that don’t rank. The difference is the timeline. SEO gave you years to figure it out. Apple’s agentic transition will compress that window into months.


## MCP integration

This is the detail that should restructure your thinking about what Apple is actually building. Almost nobody is covering it, and it’s arguably the most strategically significant signal in the entire WWDC preview.

In the iOS 26.1 developer betas last September, 9to5Mac found code showing Apple building Model Context Protocol support directly into the App Intents framework. MCP, originally proposed by Anthropic, has rapidly become the industry standard for connecting AI models to external tools and services. OpenAI adopted it. Google adopted it. Every major enterprise AI platform supports it or is building support. The MCP spec is, functionally, the HTTP of agentic AI, the protocol layer that lets any model talk to any tool through a common interface.

In practice, that means: instead of each app independently implementing MCP support, which requires the developer to build and maintain a server, handle authentication, manage the protocol surface, developers can use Apple’s system-level integration. Apple handles protocol compatibility. The developer exposes their app’s capabilities through App Intents, and those capabilities become available to any MCP-compatible AI agent.

Not just Siri. Any agent. ChatGPT, Claude, Gemini, whatever open-source model someone runs locally. If a model speaks MCP, and an app exposes intents, the model can act on the app through the operating system’s own orchestration layer.

Apple isn’t building Siri as a chatbot to compete with ChatGPT. They’re building the operating system as an agent runtime that any model, including ChatGPT, can plug into. The App Intents framework is the API surface. MCP is the protocol. Apple controls the chokepoint.

This is a classic Apple move, executed at a higher level of abstraction than usual. Apple has always been a platform company that captures value by controlling the layer between users and third parties: the App Store, the payment rail, the notification surface, the search index. Now they’re doing the same thing for agents. Every AI model that wants to do something useful on an iPhone has to go through Apple’s orchestration layer. Every developer who wants their app to be agent-addressable has to adopt Apple’s framework. The toll booth just moved from “you need our app store to distribute” to “you need our intent system to be actionable.”


## The Gemini deal and CoreAI

In January, Apple and Google confirmed a multiyear partnership where Google’s Gemini models and cloud technology power future Apple Foundation Models. Bloomberg initially reported the deal at approximately $1 billion per year. A subsequent analyst estimate from Deepwater Asset Management put the total value at $5 billion. The Financial Times described it as a cloud computing contract, with one former Apple executive calling it “a necessary byproduct of Apple’s decision not to go big on its AI investments like its competitors.”

The architecture splits cleanly. Apple’s own Foundation Models, roughly 3 billion parameters, optimized for Apple Silicon, running on-device, handle the planner and search operator functions. These are the tasks that require access to personal data: reading your messages, checking your calendar, searching your notes, understanding what’s on your screen. All of that stays on the device. When the request exceeds on-device capacity (web summarization, complex reasoning, deep search) it routes to Gemini running inside Apple’s Private Cloud Compute, where data is encrypted, never stored, never accessible to Apple or Google, and where independent security researchers can verify the code running on the servers.

Google provides the intellectual horsepower. Apple maintains control of the user experience, the data pipeline, and the privacy architecture. Google never sees the user’s identity, device information, or raw personal data. Apple acts as a privacy proxy between the user and Google’s models.

Meanwhile, Apple is expected to announce a CoreAI framework at WWDC as a successor to Core ML. The focus: making it easier for developers to integrate third-party AI models into their apps, with better quantization, memory-efficient adapters, and streaming token generation on Apple Silicon. One of CoreAI’s rumored priorities is integrating third-party AI models, potentially through MCP, into the developer toolkit.


## The architecture

Put the four signals together and the shape of the strategy becomes unambiguous.

Layer one is the user surface. Siri as a conversational agent: standalone app, systemwide entry points, unified search, ambient invocation from anywhere in the OS. This is the layer users see and interact with.

Layer two is the developer surface. App Intents plus MCP as the standardized agentic API, with CoreAI replacing Core ML for model integration. This is the layer where third-party apps become agent-addressable, where Uber, WhatsApp, your banking app, and your project management tool expose their capabilities to agents through a common framework that Apple manages.

Layer three is the model infrastructure. On-device Apple Foundation Models handle personal context and routing. Gemini handles heavy cloud reasoning inside Private Cloud Compute. Privacy functions as the architectural constraint that shapes every other decision.

Apple has never competed to build the best model. They’ve competed to own the platform every model runs on. That’s the race they’re in now.


## What the delay tells you

The bulls on Apple’s AI story don’t want to talk about the next part.

Everything I just described, the conversational Siri, the Personal Context feature, the on-screen awareness, the expanded App Intents, was originally announced at WWDC 2024. Two years ago. It was supposed to ship in spring 2025. It got delayed to early 2026. It got delayed again. Many of the features that Gurman describes won’t actually be ready until this fall, after being previewed at WWDC in June.

Apple faced a false advertising lawsuit over the delays. Critics pointed out that Android flagships shipped with more RAM and more capable on-device models while Apple was still testing. Samsung got Gemini’s agentic features on the Galaxy S26 months before Apple shipped anything comparable. Google has already rolled out Gemini Personal Intelligence to all US users. OpenAI’s ChatGPT agent capabilities have been in production for months. Apple isn’t leading this race. Apple is, by any honest assessment, behind.

The delay might not matter as much as it looks.

Apple’s track record on platform shifts is remarkably consistent: arrive late, win on integration depth. Apple wasn’t first to smartphones, tablets, smartwatches, or ARM-based laptop processors. In every case, Apple waited until it could deliver a vertically integrated experience that competitors couldn’t match (hardware, silicon, OS, developer framework, user experience, all designed as a single system). Then it captured the premium tier of the market for the next decade.

The agentic play follows the same pattern. Google shipped agentic features faster. Google’s UI automation approach, where Gemini uses computer vision to recognize buttons and navigate app interfaces without developer integration, works today on any app, without waiting for developers to adopt a framework. That’s a real advantage. It’s also fragile. Vision-based automation breaks when apps update their UI. It handles edge cases poorly. It requires substantial compute for screen understanding. And it gives Google no structural moat: if the capability is “any model can look at any screen,” then any model can replace Gemini tomorrow.

Apple’s approach is slower but more defensible. By building the orchestration layer into the OS itself (App Intents as the API, MCP as the protocol, CoreAI as the model integration framework) Apple creates a structural advantage that compounds over time. Every developer who adopts App Intents makes the Apple ecosystem more valuable for agents. Every agent that uses MCP through Apple’s system-level integration makes the App Intents framework more valuable to developers. That’s a flywheel, not a feature. Google’s UI automation is a capability that any model can replicate tomorrow.

Whether Apple can close the gap fast enough depends entirely on developer adoption of App Intents, and on whether the WWDC 2026 developer experience is good enough that building for the agentic OS feels like an obvious bet rather than a speculative one.


## Google’s impossible position

The Gemini deal puts Google in a position that has no real precedent in tech. Google is now the AI engine powering both major mobile operating systems simultaneously. Gemini runs Siri’s cloud reasoning on iPhone. Gemini runs the native assistant on Android. Google sits at the center of how roughly 4.7 billion mobile devices interpret and act on natural-language requests.

The bigger prize for Google isn’t the $1 billion annual licensing fee. It’s distribution. Access to Apple’s approximately 1.5 billion iPhone users gives Gemini reach that no standalone AI app can match. If Siri gets materially smarter, and users notice, Google benefits even though Apple gets the credit. There’s a plausible world where Gemini’s foothold inside Siri eventually leads to a preinstalled Gemini chatbot app on iPhones, the same way Google Search became the default across Apple’s ecosystem through a deal now worth roughly $20 billion annually.

But Google isn’t passive on the competitive side. In February, Google launched agentic AI capabilities for Gemini on Android, debuting on Galaxy S26 and Pixel 10. Users delegate multi-step tasks, ordering food through DoorDash, booking Uber rides, reordering groceries, and Gemini executes them autonomously in a virtual window, with users monitoring progress and approving sensitive actions like purchases.

The approach differs from Apple’s in a way that reveals fundamentally different theories of how agentic systems should work.

Apple requires developers to expose structured capabilities. Siri talks to the intent, not the UI. The upside is reliability: when Siri triggers an App Intent, the action is well-defined and tested. The downside is adoption lag. Until developers update their apps, Siri’s agentic capabilities are limited to apps that have opted in.

Google uses UI automation, computer vision that recognizes buttons, form fields, and navigation patterns, letting Gemini operate any app by “seeing” the interface the way a human would. The upside is immediate coverage. No developer adoption required. The downside is brittleness. The agent is pattern-matching against pixels, not calling structured APIs. It breaks when apps redesign their UI. It struggles with non-standard interfaces. And it requires significant compute for screen understanding, which hits inference costs and battery life.

Google also has AppFunctions, its own version of structured app integration, essentially the Android equivalent of App Intents. Samsung Gallery already uses AppFunctions to let users search photos through Gemini. But Google’s headline play is the UI automation, because it gives them coverage now while the structured path scales over time.

The privacy divergence is equally consequential. Apple keeps personal context on-device and routes cloud reasoning through Private Cloud Compute, where data is encrypted and inaccessible to Apple or Google. Google’s Gemini Personal Intelligence explicitly pulls context from Gmail, Photos, YouTube, Search, and other Google services to deliver personalized responses. Google’s approach is more capable in the near term: it has vastly more data surface area to draw from. Apple’s approach is more defensible with the users who pay the most, the privacy-conscious premium segment that generates the majority of Apple’s services revenue.

There’s a wrinkle nobody is gaming out publicly. Google is training Apple’s competition. Every Siri query that routes to Gemini inside Private Cloud Compute generates inference load that Google profits from. But it also generates signal about what kinds of agentic requests iPhone users make: request patterns, task complexity distributions, failure modes. Google can’t see the personal data (Apple’s privacy architecture prevents that), but the aggregate query patterns are valuable intelligence for improving Gemini’s Android experience. Apple is paying Google to power Siri while Google learns from the interaction patterns to make Android’s agent better. The deal that looks like a win-win has an asymmetry buried in it that favors the company controlling the model.

I genuinely don’t know how that asymmetry plays out. Apple knows the dynamic exists. The deal is explicitly described as temporary. Apple’s long-term play is clearly to build or acquire sufficient model capability to run the full stack in-house, the same way Apple replaced Intel chips with its own silicon. The Gemini deal is a bridge, not a destination. The question is how long the bridge needs to be.


## Samsung and the rest of Android

Samsung is the biggest near-term beneficiary in the Android ecosystem. Galaxy S26 gets Gemini’s agentic features first, giving Samsung a differentiation story that no other Android OEM can match right now. The Samsung Gallery integration with AppFunctions, ask Gemini to find photos by description and get results without leaving the conversation, is the kind of tight integration that used to be Apple’s exclusive territory.

But it deepens a dependency that Samsung has been trying to escape for a decade. The more Samsung’s flagship experience depends on Google’s AI, the harder it becomes to negotiate from a position of strength on the terms of that relationship. Samsung spent years and billions of dollars building Bixby, its own assistant, precisely to avoid this kind of dependency. Bixby failed. Now Samsung’s flagship differentiator is a Google product running on Samsung hardware. The hardware vendor becomes, functionally, a distribution channel for Google’s AI, the same dynamic that defined the first era of Android, just one layer up the stack.

For smaller Android OEMs (Xiaomi, OnePlus, Oppo, the rest of the long tail) the question is whether Google makes the agentic features broadly available in AOSP or keeps them as Pixel-and-premium-partner exclusives. The early signals aren’t encouraging. Gemini’s task automation is launching on Galaxy S26 and Pixel 10. Not on Xiaomi’s flagships. Not on budget Androids. If this pattern holds, the Android ecosystem fragments further around AI capability, with the majority of the world’s three billion Android devices unable to match what iPhones and Galaxy flagships can do.

That fragmentation creates a structural opening for Apple in a market segment that historically hasn’t been Apple’s to win: the aspirational mid-tier buyer who cares about having the best phone experience but can’t necessarily afford the iPhone Pro. If “best phone experience” increasingly means “best agentic capabilities,” and the only Android devices with competitive agentic features are the $1,000+ Galaxy flagships, the argument for choosing a $799 iPhone over a $400 Android with no agentic features gets considerably stronger.


## What you should do before June

If you build iOS apps and haven’t implemented App Intents, this is the single most time-sensitive item in this piece. When WWDC happens on June 8, Apple is going to show demos of Siri acting inside apps. The apps in those demos will get a wave of user attention and developer credibility. The apps that aren’t agent-addressable will feel broken by comparison, not because they are broken, but because the user expectation just shifted. “Why can’t I just ask Siri to do this?” is going to become the default question, and if your app doesn’t have an answer, your competitors’ apps will.

If you’re building MCP servers for your product, which is increasingly table stakes for enterprise SaaS, Apple’s system-level MCP support means your investment may get you iPhone and Mac integration at very low marginal cost. The same structured capabilities you expose to Claude or ChatGPT today could become available to Siri and every other agent on Apple’s platform, through the OS’s own orchestration layer. That’s a free distribution channel for your API surface. If you aren’t building MCP support for your product yet, the Apple signal should move it up your roadmap.

If you lead a product or engineering organization, the question you need to be asking right now isn’t “do we have an app?” It’s “can an agent use our app?” Every user flow that requires manual navigation through your UI is friction that an agent could eliminate, and that a competitor’s agent-ready app will eliminate for you. Take your ten most common user actions. How many could be expressed as a structured intent? “Create a new order.” “Reschedule my appointment.” “Show me my balance.” “Send a follow-up message.” Those are the actions that agents will handle first, because they’re well-defined and high-frequency. If your product requires four taps and two screens to accomplish what a competitor accomplishes in one voice command, your retention metrics will tell you what happened before your analytics dashboard can explain why.

If you’re a knowledge worker, which is most of the people reading this, start now. At this point, when someone asks me a question that has a findable answer, my first move is to open an AI, ask it, verify the source, and respond. It is almost always faster, almost always correct, and it leaves me wondering why the other person didn’t try that first. That reflex, the instinct to delegate before you do, is exactly the muscle that Apple’s agentic Siri is designed to serve. The interaction pattern they’re building toward is fundamentally different from how you use your phone today. Instead of “open app, navigate to feature, do the thing, close app, open next app,” it’s “describe the outcome you want and let the agent coordinate across apps to deliver it.” That’s a skill. It requires clarity of intent, knowing what you actually want precisely enough that an agent can act on it. The people who develop that skill on current tools (ChatGPT’s systemwide toggle on iOS, Claude with MCP workflows, even Shortcuts automations) will have a significant advantage when Apple ships its version, because the prompting patterns and the instinct for what to delegate vs. what to do manually transfer directly.

The WWDC developer sessions matter even if you’re not a developer. The sessions on App Intents and Personal Context will telegraph exactly which workflows Apple is targeting first. That tells you where the agentic experience will be polished and where it will be rough. Pay attention to which third-party apps appear in the demos. Those are the apps Apple has been working with most closely, and they’re the ones whose agent integration will be best on day one.


## The deeper game

The story that will dominate WWDC coverage is “Siri finally becomes a chatbot.” The framing undersells what’s happening by an order of magnitude.

The chatbot market is commodity. ChatGPT, Claude, Gemini, Grok, Llama. There are plenty of conversational AI interfaces. They’re getting better fast, and the switching costs between them are low. Building a chatbot is not a durable advantage for Apple. Apple knows this. Federighi all but said it.

What Apple is building is the orchestration layer underneath. App Intents as the API surface, MCP as the protocol, CoreAI as the model integration framework, Private Cloud Compute as the privacy architecture. This is the agentic equivalent of what iOS was to mobile apps in 2008: the runtime that every agent has to target, the platform that captures value by sitting between models and actions, the chokepoint that compounds with every developer who adopts the framework and every user who develops the habit of saying “Siri, do this” instead of opening an app.

The model race gets all the attention. Bigger parameters, better benchmarks, faster inference. That race matters, but it’s not the race Apple is running. Apple is running the platform race, the competition to own the layer that converts AI capability into user-facing utility on the devices people actually carry. And on that dimension, Apple has a structural advantage that no model company can match: they control the hardware, the OS, the silicon, the developer framework, the privacy architecture, and the distribution to more than 1.5 billion devices. When Apple builds the agentic runtime into the OS, every model company has to build for Apple’s platform. When Google ships agentic features on Android, Google is one vendor among many. When Apple ships, Apple is the platform.

This is why the MCP integration matters more than the chatbot. The chatbot catches Apple up to the field. The runtime is where Apple pulls ahead. And the winning move isn’t building the best model. It’s building the layer that makes every model useful, and extracting the toll for access.

I want them to pull it off this time. I am genuinely tired of a Siri that cannot keep up.

WWDC is June 8. Ten weeks. The architecture ships this fall. By the time it reaches users, the agentic phone transition will have been underway on Android for months. Apple will be late. Apple is almost always late. The question, the same question it’s been for twenty years of Apple platform launches, is whether “late but integrated” beats “early but fragmented.”

History says it does. Whether it does this time depends on whether developers adopt App Intents fast enough, whether the Gemini-powered Siri is good enough to change user habits, and whether privacy as an architectural principle, not a marketing message, an actual engineering constraint that shapes every design decision, resonates with enough users to justify the tradeoffs.

I think it will. But the only people who’ll know for certain are the ones who positioned for it before June.

[![](https://substackcdn.com/image/fetch/$s_!UWWT!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdb99785d-7db0-4214-a956-94cc7eafc43c_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!UWWT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdb99785d-7db0-4214-a956-94cc7eafc43c_1024x1024.png)
