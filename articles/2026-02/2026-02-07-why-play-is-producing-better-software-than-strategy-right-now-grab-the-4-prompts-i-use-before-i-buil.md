---
title: "Why play is producing better software than strategy right now + grab the 4 prompts I use before I build anything"
author: "Nate Jones"
published: 2026-02-07
url: https://natesnewsletter.substack.com/p/why-play-is-producing-better-software
subtitle: "Watch now | This is your reminder: AI is not just all doom, gloom, and work! There's fun to be had."
audience: everyone
scraped_at: 2026-02-07 12:00:20
---

Something clicked in the last six weeks, and the word I keep reaching for is *playfulness*. Which is probably not what you expect.

The AI discourse is loud right now, and most of it is ominous. Jobs disappearing. Deepfakes and misinformation. Existential risk. The think pieces are anxious; the comment sections are angry. I’m not here to dismiss any of that — the concerns are real and worth taking seriously.

But there’s a different story happening in parallel, quieter and stranger, and I want to talk about that instead.

By early 2025, “vibe coding” — Karpathy’s term for building software by prompting — started spreading fast. But for most of the year, it was still work. You had to fight the tools. Babysit the AI through its confusion. Debug weird failures that made no sense. The friction was high enough that you had to be serious about what you were building. You wouldn’t waste that effort on something frivolous.

What shifted isn’t just that the tools got better — though they did. The models hold context longer. The agentic patterns matured. The builder platforms got more reliable. But the real change is downstream of all that: the friction dropped enough that building software stopped feeling like work and started feeling like play.

And play produces different things than strategy.

Last week, a service called Fable started making the rounds. You upload a photo of your pet, and it generates a Renaissance portrait — your dog as a Baroque duke, your cat as a Flemish noblewoman — then ships you a physical print. It’s ridiculous. It’s delightful. Depending on which viral screenshots you believe, it’s doing six figures a month.

That’s not an “identify a market need and execute” story. That’s a “wouldn’t it be funny if…” story. Someone was playing. They built the joke. The internet turned out to have demand for it.

The internet has always been an infinite pool of demand. What’s new is that the cost of probing that demand just collapsed. You can try things now. Build the dumb idea. See what happens. If nobody cares, you lost a weekend. If they do, you’ve got something.

**Here’s what’s inside:**

- **The hobby nobody expected.** Why software creation is going through its “smartphone camera” moment — and what that means for people who’ve never written a line of code.
- **Software vision.** The real skill that separates people who thrive with these tools from people who bounce off them — and it isn’t coding.
- **The honest limitations.** A few failure modes that kill projects, and how to avoid them without slowing down.
- **The tool decision.** Builder platforms vs. CLI tools — which path fits your situation, and what you’re trading either way.
- **The skill that actually matters.** Why experienced developers extract more value from AI coding tools than beginners — and what that tells you about what to practice.

Let me show you what the weekend window actually looks like — and how to tell if you’re the kind of person who should climb through it.


## **[Grab the Prompts](https://www.notion.so/product-templates/The-First-Build-Prompt-Kit-2ff5a2ccb52680ffa2f3e1b01fc588c7?source=copy_link)**

Most people who read an article like this do the same thing: feel inspired, open a tool, start prompting — and burn a weekend generating code that solves no clear problem. The issue is almost never the tools. It’s that they skipped the thinking the tools can’t do for them. I built a four-prompt sequence to force that thinking before you touch anything: whether you’re actually the right person for this, what you’re really trying to build, which tools fit your situation, and what’s honestly achievable before Monday morning. The Software Vision Check in particular exists because I’ve seen too many people discover the hard way that their problems aren’t software-shaped — and nobody told them that was fine. If you can’t get through the first prompt, you just saved yourself ten hours of frustration. That’s the point.


## **The satisfaction of making things**

There’s a particular kind of satisfaction that comes from making something that works. You have an idea. You figure out the pieces. At some point the thing you imagined becomes a thing that exists. You made it.

People who build for a living know this feeling. Carpenters, cooks, designers, engineers. The material varies, but the satisfaction is recognizable. You had a vision. Now you have an artifact.

For most of software’s history, this satisfaction was gated behind years of specialized training. The gap between “I wish this existed” and “I made it exist” was too wide for casual crossing. Most ideas died in that gap — not because they were bad, but because the activation energy was too high.

That gate is opening. And the people walking through aren’t just startup founders looking for leverage. A lot of them are hobbyists, building things for fun, with no business model in sight.


## **The hobby nobody expected**

A designer builds a personal dashboard that shows the phase of the moon, their Spotify listening stats, and how many days until their next vacation. A retiree automates their greenhouse irrigation. Someone makes a browser extension that does one absurd thing perfectly. A friend group gets a custom Telegram bot that alerts them when concert tickets drop.

None of these are businesses. They’re projects — built for the satisfaction of building, used by the maker and maybe a few friends.

This is new. For most of software’s history, building required enough specialized knowledge that it was primarily professional. Hobbyist programmers existed, but “I code for fun” was a niche identity, not a casual weekend activity.

What’s emerging looks more like what happened with photography. Taking good photos once required serious expertise — exposure, developing, darkrooms. Then cameras got easier. Then smartphones made everyone a photographer. Professional photography still exists, but alongside a vast amateur ecosystem of people who just like taking pictures.

Software is going through a similar transition. The professionals aren’t going anywhere — complex systems still require deep expertise. But alongside professional development, there’s now space for casual creation. Building for yourself, for fun, for friends. Because you had an idea and now you can make it real.

And because it’s play, people try weird things. They follow ideas wherever they go. Some of the most interesting software I’ve seen recently has this hobbyist energy — not polished, not scalable, but genuinely creative in ways commercial software rarely is.

Occasionally, one of these playful projects finds an audience. The internet is vast and has appetite for nearly anything interesting. Pet renaissance portraits weren’t a market analysis. They were a joke that landed.


## **Who this is for**

Tell someone they can now build any app they want and most people say “cool!” — then never think of anything to build. Not because they’re uncreative. Because most people’s problems aren’t software-shaped, and most won’t notice even when they are.

There’s a concept from parkour called “parkour vision” — the trained ability to see walls as surfaces to run along, gaps as spaces to jump through, railings as pathways. The city looks different to a traceur than to everyone else. Software vision is similar. Programmers are trained to see repetitive tasks as automation opportunities. They look at a manual workflow and think “I should script this.” The rest of us just... keep doing it manually.

The people who take to vibe coding aren’t necessarily technical. They’re people who already have software vision, or who develop it quickly. They notice when a problem is software-shaped: “I keep doing this same thing over and over.” “I wish I could see all this information in one place.” “It’s annoying that these two systems don’t talk to each other.”

If you’ve ever spent an afternoon building a complicated spreadsheet to solve a problem, you probably have software vision. If you’ve duct-taped together Zapier automations, or written macros, or bent a tool to do something it wasn’t designed for — that’s the disposition. You don’t need to know how to code. You need to notice when a problem could be solved by software, and be curious enough to try.

The other thing you need: comfort with ambiguity. Things won’t work on the first try. You’ll describe what you want, get something close but not right, and need to figure out how to refine the description. If you require step-by-step instructions for everything, this will be frustrating. If you’re okay with experimentation — if the iteration is part of the fun — you’ll do fine.


## **The honest limitations**

A few failure modes worth understanding.

The first is moving so fast you never stop to think. When building is instant, the bottleneck shifts to knowing what you actually want. It’s easy to prompt before you’ve figured that out — to generate piles of features that don’t fit together, to end up hip-deep in code that doesn’t serve any clear purpose. The build/test/iterate loop is so fast it’s intoxicating. You can burn a weekend generating software that solves no real problem.

The discipline is to pause. Describe what you want in plain language before you start prompting. Know why you’re building this, what it should do, what success looks like. The tools will happily turn vague intentions into working code. Working code that misses the point is worse than no code at all.

The second is confusing “works on my laptop” with “ready for users.” AI is compressing the cost of creating software toward zero. A working prototype that took months now takes hours. But AI does nothing to compress the cost of owning software in production. Someone still has to answer for it. Who maintains this when it breaks at 2am? Who carries liability when it fails? Who integrates it with everything else?

For personal projects, this doesn’t matter. Your greenhouse automation can crash. Your friend-group bot can have bugs. The stakes are low, imperfection is fine.

For anything with real users depending on it, the gap between “prototype” and “production-grade” is still real. In May 2025, a security researcher scanning Lovable’s public “Launched” showcase found vulnerable Supabase configurations in about 10% of the projects analyzed — databases exposed to the public internet, API keys visible to anyone who looked. The pattern is consistent: AI handles the happy path and misses the edge cases.

This is where platforms like Lovable are making a bet. They’re running the Shopify playbook: start with a vibe, and we’ll help you grow up. The tools are extending the bridge toward production — adding the authentication, the security, the scaling infrastructure — so you don’t have to start over when something takes off. The gap is narrowing. But it’s not gone.

The honest scope: vibe coding is for prototypes, personal tools, experiments, and probing whether an idea has legs. If something catches — if the internet turns out to want pet renaissance portraits — you’ll need to either level up your understanding or bring in someone who can take it the rest of the way. The playful prototype got you to the point where that investment makes sense.

There’s a third thing worth understanding, especially if you get ambitious: AI coding tools degrade over long conversations. The model starts contradicting itself, forgetting what it built, suggesting changes that break previous work. Engineers call this context rot, and it kills projects that outgrow a single session. The fix is to break work into small tasks and run each in a fresh context — many short conversations that each complete cleanly, with memory persisting through your codebase, not through the AI’s context window. For a weekend prototype you might never hit this wall. For anything bigger, you’ll want to manage sessions deliberately.


## **The tool decision**

There are two fundamentally different paths, and which one makes sense depends on who you are and what you’re building.

**Path one: the builder platforms**

Tools like Lovable, Bolt, and Replit’s agent. You describe what you want in a chat interface, and the platform generates a complete application — frontend, backend, database, deployment. You never see a terminal. You might never see the code at all.

This path makes sense if you have zero technical background and no interest in acquiring one, if you need something fast and don’t care about understanding the internals, or if the thing you’re building is a prototype you might throw away. You’re trading control for speed — these platforms own your deployment and infrastructure, and you’re okay with that.

The tradeoff is control. These platforms optimize for speed to first demo, not for long-term maintainability. The code they generate is often difficult to modify outside the platform. If you outgrow the tool, you’re frequently starting over rather than iterating.

For a quick experiment or a disposable prototype, this is often the right call. Get to the thing, see if it’s worth pursuing, don’t worry about the foundation.

**Path two: the CLI tools**

Tools like Claude Code, Cursor, or Windsurf. You work in a code editor or terminal. The AI writes code, but you see it, you run it locally, you commit it to your own repository, you deploy it where you choose.

This path makes sense if you have some technical comfort — even rusty or informal — and you want to understand and own what you’re building. Maybe you’re making something you’ll maintain over time, or you just want the flexibility to change tools without starting over.

The tradeoff is friction. There’s more setup. You need to be comfortable enough with the command line to run basic operations. When things break, you’re more exposed to the underlying complexity.

But the code is yours. It lives in your repository. You can read it, modify it, take it to a different tool, hire someone to work on it later. The skills you develop transfer across tools as the ecosystem evolves.

For someone building something they care about long-term, this is usually the right call. The extra friction upfront pays dividends in control and flexibility.


## **What you can actually build**

Let me draw realistic boundaries.

A weekend of focused effort — eight to ten hours — gets you a working web application with a handful of features. User login. A database. The ability to create, read, update, and delete things. Deployment to a live URL you can share. Concretely: a client intake form that saves responses to a database and sends you notifications, a personal dashboard pulling data from APIs you already use, a content calendar tailored to your specific workflow, an internal tool for a small team that does one thing well, a landing page with a waitlist that actually captures emails.

These aren’t impressive to professional developers — they’re table stakes. But if you’ve been doing these things manually, or paying for SaaS tools that don’t quite fit, the ability to build exactly what you need changes your relationship to software.

A month of weekends — thirty to forty hours — gets you a complete minimum viable product. Multiple user types with different permissions. Integrations with external services. Payment processing. The kind of thing that used to require a technical co-founder or a significant check to an agency.

This is where the stakes get higher. You’re not just experimenting; you’re building something you might show to customers. The security and maintainability concerns become real. You need to either understand what you’re building well enough to evaluate it, or bring in someone who does before launch.

What you cannot realistically build: anything requiring deep expertise you don’t have. Complex real-time systems. Sophisticated algorithms. Infrastructure that needs to scale reliably. Applications in regulated industries where compliance matters.

The heuristic: if you can describe the exact behavior you want, including what should happen when things go wrong, you can probably build it. If your specification is vague or requires domain knowledge you lack, you can’t.


## **The skill that actually matters**

Remember software vision — the ability to notice when a problem is software-shaped? There’s a second skill that builds on it, and this one is counterintuitive: AI coding tools work better for experienced developers than for beginners. The people who already know how to code extract the most value. The people who can’t code at all often struggle to get anything useful.

Which seems backwards — isn’t the whole point to help non-coders build things?

The explanation is that the valuable skill isn’t coding — it’s specification. Experienced developers know how to break problems into pieces. They know what questions to ask: What happens when the user isn’t logged in? What if the database is slow? What if someone enters invalid data? They can evaluate whether the AI’s output makes sense.

Beginners tend to prompt vaguely (”build me an app”), accept whatever the AI generates, and hit a wall when something doesn’t work. They don’t have the mental models to debug or to know what questions to ask.

The good news: you don’t need to become a professional developer. You need to develop enough intuition to specify clearly and evaluate critically. That’s a smaller gap than learning to code from scratch, and it closes faster with practice.

The way you build that intuition is by building things. Start small. Notice what goes wrong. Develop a sense for what questions to ask. Each project teaches you something about how to work with these tools.


## **Developing the practice**

The path to the satisfaction of building isn’t a tutorial. It’s more like developing a practice.

Start with something you actually want — not a learning exercise, something you’d use. The motivation carries you through the frustration of early attempts. If you’re building a generic todo app because some guide suggested it, you’ll quit. If you’re building a tool that solves a real annoyance in your life, you’ll push through.

Describe before you build. Write down, in plain language, what you want the thing to do. “A dashboard” is useless. “A page that shows me my calendar for today, the weather, and the top 5 items from my task list, refreshing every time I open it” is something you can build. The more precisely you can describe the behavior, the better your results.

Accept that early attempts will be rough. The rhythm — describe, see what you get, refine, iterate — feels awkward at first and natural after a few cycles. Plan to throw away your first project, or your first three. This isn’t waste; it’s calibration.

And know when you need help. If you’re putting something in front of users — especially if it handles their data — a few hours of professional security review before launch is worth it. The AI-generated prototype gets you to the point where you have something worth reviewing.


## **The deeper shift**

I don’t know exactly where this goes. Maybe it stays niche — a hobby for people with certain inclinations, like ham radio or kit cars. Maybe it becomes more widespread, and “I built a little app for that” becomes as common as “I made a spreadsheet for that.”

What I keep coming back to is the conjunction of three things that haven’t been true together before:

Building software is inherently satisfying — the feeling of making something that works. That’s always been true, but it was gated behind years of specialized learning.

The internet has nearly infinite demand for interesting things. That’s been true for a while, but probing that demand was expensive. You had to invest real time and money before you knew if anyone cared.

Now the cost of building is approaching zero for hobbyist-scale software. The gate is open. The cost of experimentation collapsed.

Put those together and something new emerges. You can be playful. You can try the dumb idea, the weird idea, the idea that makes you laugh. If it doesn’t work, you lost a weekend. If it does — if it turns out the internet has appetite for pet renaissance portraits or whatever absurd thing you dreamed up — you’ve got something.

That’s not a hustle. It’s not an arbitrage opportunity. It’s closer to what happens when any creative tool becomes accessible: more people make things, the things they make are weirder and more varied, and occasionally something catches.

Some people will walk through this door to build businesses. The startup use cases are real. But the more interesting story might be the people who walk through just because making things is fun. No monetization strategy. No growth metrics. Just the pleasure of building your own tools and following your ideas wherever they lead — with a lottery ticket attached to each one.

The tools exist now. The question is whether you’re curious enough to play.

[![](https://substackcdn.com/image/fetch/$s_!81qI!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9be1e6de-9598-414e-b5b0-b13b58f026ae_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!81qI!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9be1e6de-9598-414e-b5b0-b13b58f026ae_1024x1024.png)
