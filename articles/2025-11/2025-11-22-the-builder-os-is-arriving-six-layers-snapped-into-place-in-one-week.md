---
title: "The Builder OS Is Arriving: Six Layers Snapped Into Place in One Week"
author: "Nate Jones"
published: 2025-11-22
url: https://natesnewsletter.substack.com/p/heres-my-stay-sane-prompt-for-ais
audience: everyone
scraped_at: 2026-01-05 19:11:20
---

Guys, this was a WEEK.

I know you feel it too, and honestly we couldn’t even cover all the jaw-dropping stuff in AI. So this is my roundup post. I definitely burned the hours on AI this week, so call it like 20 hours of AI news following for you, wrapped up into a tidy bundle of the 6 stories that really matter.

Sure, you’ll get [Nano Banana Pro](https://natesnewsletter.substack.com/p/google-solved-visual-reasoning-get?r=1z4sm5) and [Gemini 3](https://natesnewsletter.substack.com/p/how-gemini-3-changes-your-job-a-practical?r=1z4sm5), but there’s other ones nobody is talking about I want to cover too.

Like:

- OpenAI making a move on Apple’s turf that’s NOT a device

  - Key to be aware of on model maker strategy / investments
- Meta solving video search

  - If you do ANYTHING with video this is a huge deal
- AI legend Fei Fei Li is back with incredible 3D worlds

  - Massive for gamers, developers, AR/VR folks, artists, and vibe coders
- AI doing new science (like black hole physics)

  - We just need to know this one—good for teachers, professors, and anyone who wants to nerd out on where AI is going
- And of course we have a true agent-native IDE for devs!

I honestly can’t remember the last time we had a week this big in AI. Every story here had to fight tooth and nail to earn its place, and they’re all massive.

As usual, I have a sharp prompt you can grab to figure out the implications of all these stories for YOU, and I also made you a bunch of Nano Banana illustrations AND a few slide decks with a new prompt tool I’m playing with.

If you’re feeling overwhelmed, this is the 10 minutes you need to feel caught up. You’ll know what matters, have the prompts to apply it in your situation, and be back to building or brunch.

Enjoy!


## [Grab the news prompt for AI mega week](https://www.notion.so/product-templates/AI-Mega-Week-News-Prompt-Nov-21-2b35a2ccb526808a9b69d37d1cd2d760?source=copy_link)

I built this prompt so you can have a real conversation about the article without actually reading the whole thing. It includes a complete summary of the week’s AI news—every product launch, every significant announcement—packed with enough detail that you’re not working from abstractions. From there, the model becomes your thinking partner: it asks open-ended questions, helps you compare what’s happening across layers of the stack, surfaces implications you might miss on a first pass, and pushes back when your assumptions need testing. The goal isn’t to summarize *at* you—it’s to help you interrogate the ideas, find what actually matters to your work, and walk away with sharper strategic clarity than you’d get from reading alone.

---


# The Builder OS Is Arriving: Six Layers Snapped Into Place in One Week

This was the week the builder operating system came into focus.

Not another round of leaderboard charts or an “AGI soon” hype cycle, but something cleaner and more practical: six different layers of the builder stack—code, screens, vision, worlds, reasoning, and hardware—became programmable and production-ready at the same time.

The old story was that “the model is no longer the product.” That’s still true. But the deeper story is this:

**Environments are the new product.** The fight is about who owns the builder OS—the places where you write code, make screens, understand the world, simulate environments, generate new knowledge, and run it all on real hardware.

Six releases this week, six layers of that OS coming online:

- **Gemini 3 + Antigravity**: code
- **Nano Banana Pro**: screens
- **SAM 3**: vision
- **Marble**: worlds
- **GPT-5 science paper**: reasoning
- **OpenAI + Foxconn**: infrastructure

These aren’t isolated launches; they’re the rough outline of a new stack. Let’s walk through them.

---


## LAYER 1: Code — Antigravity Becomes the AI Shell

On November 18, Google released Gemini 3 alongside **Antigravity**—a VS Code fork that’s not really a traditional IDE at all. It’s agent-first through and through.

Antigravity agents can see files, terminal, and browser. They can edit code, run commands, click UI, and record artifacts. The platform lets you plug in models as you like, but of course defaults to Gemini 3. And of course, it’s sitting where developers already live—the most popular editor in the world, now forked and turned into a Google-native shell.

**Google is trying to own the command line of the AI era**: the place where work starts, context lives, and all other layers get orchestrated from. (And yes, the Windsurf team built this one with lots of Windsurf IP inside.)

Benedict Evans put it well this week when he described AI coding as the new AWS. Control where developers work and you control everything upstream and downstream of the model. The environment wins. The integration wins. The default wins.

And that’s all reinforced by the idea that agents are a sort of super-lever, enabling very efficient usage of compute. So we think of Antigravity as a coding tool, but it’s smarter to think of it as a foothold into agentic computer use by Google.

Antigravity isn’t competing on model quality—it’s competing on **where the model runs**. Once the editor becomes the OS shell, model choice becomes secondary. Distribution-as-moat, and arguably the most important strategic move of the week.

**What to watch**: Whether Cursor and Windsurf respond by open-sourcing their orchestration layers or doubling down on proprietary features. Whether Claude or OpenAI lean harder into IDE.

---


## LAYER 2: Screens — Nano Banana Pro Turns Images Into UI

On November 20, Google launched **Nano Banana Pro**—and if you think it’s “just an upgraded image model,” you’re missing the point. The computers and agents can see now.

Before Nano, images were at best imperfect with AI (art images seemed to work better, not so much technical images). That dichotomy is gone. Everything looks just about perfect. Nano Banana Pro can put out screens on demand: layouts with real text, labels, structure. It generates readable headlines, body copy, buttons, menus, and multi-language text with consistent fonts and styling. It connects to Google Search, blends up to 14 uploaded images, and outputs at 4K resolution. It can ingest a 20 page paper and visualize it.

But that’s just the start. The real unlock is bidirectional: agents can generate a dashboard mockup, read the text back out, revise it, and iterate in a visual workflow loop that used to require design teams.

**Why this matters**: Images are now promptable. What you stare at all day—screens, docs, decks, ads—is now fully programmable. And not just by you! Nano Banana Pro is coming to Antigravity, and there’s already an API. So read this as Google setting up agents to design, read, iterate on visual surfaces. No wonder Gemini 3 scores so highly on visual interface navigation.

**What to watch**: Whether OpenAI and Anthropic match this capability or stay focused on reasoning. Whether Google is able to unlock meaningful consumer or enterprise adoption vs Anthropic and OpenAI. Whether Adobe recovers.

---


## LAYER 3: Vision — SAM 3 Gives AI a Conceptual Lens

On November 19, Meta launched **SAM 3**—and most folks outside the developer world didn’t notice. We’ve all been sleeping on Meta for a bit since Llama flopped, but credit where it’s due: this model is extraordinary.

If Nano Banana Pro made images *readable* by AI (text in generated images), SAM 3 makes images *understandable* by AI (concepts in any image). SAM 3 is a semantic search engine for video.

[![](https://substackcdn.com/image/fetch/$s_!sjNf!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc8035fcb-314d-4c97-8a20-cfd179e3ba9b_1072x1198.png)](https://substackcdn.com/image/fetch/$s_!sjNf!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc8035fcb-314d-4c97-8a20-cfd179e3ba9b_1072x1198.png)

SAM 3 accepts text prompts and finds all matching instances automatically. Not “click this object” but “find every yellow school bus” or “people sitting down but not wearing red hats.” The shift from geometric segmentation to **concept segmentation** turns any image or video stream into something you can query with natural language.

If you’re having trouble thinking of use-cases, let me suggest just a few:

- “Please find and remove all of the green screen in this scene”
- “Please find all the workers not wearing safety helmets in this video”
- “Find the person on the porch at 11:05 PM”

On Meta’s own concept-segmentation benchmark, SAM 3 more than doubles prior systems like OWLv2 and DINO-X. It was trained on millions of images and videos, with billions of masks and millions of noun phrases.

**Why this matters**: SAM 3 is the **vision layer for building**. It lets you treat the physical world—or gigabytes of video and imagery—as something you can tackle with plain English. Dataset annotation that took hundreds of hours now takes minutes. Video masking that took days takes seconds. Computer vision is rapidly shifting from geometry to concepts. It’s the same leap we saw from SQL queries to semantic search.

**What to watch**: Adoption velocity in annotation platforms (Roboflow, Scale AI). Whether video editing tools (Premiere, DaVinci, CapCut) integrate SAM 3 and kill manual masking workflows, or whether new competitors arise based off SAM 3.

---


## LAYER 4: Worlds — Marble Makes 3D Editable Like Text

We’re still not done! This was the first week World Labs launched **Marble**. Again, almost everyone missed this. It’s Figma for reality. It’s a promptable interface that generates true 3D worlds.

[![](https://substackcdn.com/image/fetch/$s_!z0u_!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1bf94848-f27c-4881-bb99-4a2d65bf3058_1142x752.png)](https://substackcdn.com/image/fetch/$s_!z0u_!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1bf94848-f27c-4881-bb99-4a2d65bf3058_1142x752.png)

Marble produces stable, downloadable 3D scenes with consistent structure—not transient geometry that re-creates on the fly. Its **Chisel editor** lets users block out layouts (walls, floors, materials) before AI fills in visual details. The “structure + style” split is 3D’s version of HTML+CSS: humans define structure, AI handles aesthetics.

Exports support full-resolution Gaussian splats (2 million splats), lightweight versions for real-time playback, and traditional meshes compatible with Unreal, Unity, Houdini, and Blender.

**Why this matters**: Marble is where the OS becomes 3D. Worlds become editable, composable, and exportable—no longer locked in proprietary formats or research demos. We’re getting into a space quickly where we can all create our own 3D worlds if we want.

**What to watch**: Paid subscription adoption (especially the $95/month Max tier). Whether Unity or Unreal integrates Marble natively. Impacts on indie gaming.

---


## LAYER 5: Reasoning — GPT-5 Pro Starts Doing Original Science

We’re STILL not done guys.

On November 20, OpenAI released a preprint showing GPT-5 Pro contributing directly to new scientific results in mathematics, physics, biology, and materials science. Not literature search. Not code cleanup. **Original proofs. Novel experimental proposals. Cross-domain reasoning.**

In mathematics, four new results—carefully checked by experts—were produced by GPT-5 Pro and published for the first time, including novel proofs in convex optimization that humans validated months later. In biology, GPT-5 Pro proposed cancer immunotherapy experiments that matched unpublished lab findings.

[![](https://substackcdn.com/image/fetch/$s_!OArF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4bd4a23c-cdf4-4892-ae6b-f4007b673730_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!OArF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4bd4a23c-cdf4-4892-ae6b-f4007b673730_1408x768.jpeg)

OpenAI documented the failure modes too—overconfidence, fragile reasoning, the need for scaffolding. It’s not magic, but it is a break.

**Why this matters**: I mean, it’s novel science with an AI. I think the implications here are pretty big. Yes, today it’s assisted. Yes, today it’s checked by humans. But the shift from humble minion to research colleague is happening real fast.

**What to watch**: We are beginning to bifurcate. Pro level models are increasingly skewing science and pure code, and I’m not clear how, when, or if we see relevant business use-cases for Pro level models beyond those fields. The best I’ve found so far is very complex legal reasoning problems.

---


## LAYER 6: Infrastructure — OpenAI + Foxconn Team Up

ALSO on November 20, OpenAI and Foxconn announced a collaboration to co-design and manufacture AI data center hardware in the United States. Not just chips—racks, cabling, cooling, power delivery, enclosures. The physical layer.

The agreement includes no financial commitments—a design collaboration where OpenAI provides specs, Foxconn engineers and manufactures, and OpenAI gets first look. Foxconn will build at U.S. facilities in Ohio, Texas, Wisconsin, Virginia, and Indiana.

**Why this matters**: Everything above assumes near-infinite compute. Someone has to make that work. Foxconn is OpenAI’s bet that **owning the racks and power layout** is how you keep up when everyone else is just renting GPUs.

If models are commoditizing, the battle moves to the edges. Google owns where builders work (Antigravity). OpenAI is maneuvering to own the silicon side with this partnership, with Stargate, etc. The stack is compressing from both ends.

Vertical integration is becoming a survival strategy for model makers. Controlling the stack buys you cost, performance, and deployment speed advantages over pure software players. Even Anthropic is getting in on the game. For most builders, this won’t change tomorrow’s code, and that’s the point. If it works, it’s invisible.

**What to watch**: Whether OpenAI can make good on parallel silicon commitments and own the whole stack. Whether Anthropic and Google announce similar manufacturing partnerships.

---


## It’s a good week to want to build stuff

Look, all this competition is fantastic for us, the users and builders in the field. We get queryable video, programmable images, 3D worlds, new agentic IDEs. I know lots of folks who wish they were at the poker table playing with the model makers, but this week I’m not sure I agree.

Looking across the field as a whole, we are seeing a picture of white-hot competition at the model layer, which means LOTS of choice and buyer’s power for all of us. We get to decide what model we want, what workflow we’re going to pick, how we want to build to solve our problems, which agents we’d choose to partner with us, etc.

The other reflection I have is: remember this week the next time you think AI is stuck. We don’t have weeks like this every single week (yet), but we have them often enough that it’s extremely clear there is no scaling wall. AI is going to keep getting relentlessly better. The top is not in sight. We’re just getting started.

---

**P.S.** Just for fun, I built three slide decks that visualize this entire week’s news. Which do you prefer?


#### [Grab the Anthropic and NotebookLM versions](https://drive.google.com/drive/folders/119_s84UDUDGTL_EpBMqeZMEVRSo7Uq7s?usp=sharing)


#### [Grab the Gamma version](https://gamma.app/docs/The-Builder-OS-Is-Arriving-5fh42huyvnhzd8u)

I used the exact same prompt for all three ([grab it here](https://www.notion.so/product-templates/PowerPoint-Prompt-2b35a2ccb52680a88a0df40681f39fb4?source=copy_link)), and I did NOT make that prompt in any tool I’ve told you about…so far. More coming on that Monday ;)

---

Last but not least, today’s article as a Nano Banana image:

[![](https://substackcdn.com/image/fetch/$s_!hB3K!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd02e38d0-3ab5-41cb-bd40-af1553caf737_1408x768.jpeg)](https://substackcdn.com/image/fetch/$s_!hB3K!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd02e38d0-3ab5-41cb-bd40-af1553caf737_1408x768.jpeg)

[![](https://substackcdn.com/image/fetch/$s_!BWWn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9021a29c-bb74-4976-b30d-118d67700b42_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!BWWn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9021a29c-bb74-4976-b30d-118d67700b42_1024x1024.jpeg)
