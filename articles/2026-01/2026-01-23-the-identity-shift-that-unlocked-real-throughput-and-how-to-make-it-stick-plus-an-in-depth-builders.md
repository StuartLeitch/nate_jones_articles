---
title: "The identity shift that unlocked real throughput and how to make it stick (plus an in-depth builders guide for 2026)"
author: "Nate Jones"
published: 2026-01-23
url: https://natesnewsletter.substack.com/p/6-practices-for-when-the-models-got
subtitle: "Watch now | What do you do when raw capability stops being the bottleneck? (Spoiler: it's not better prompting skills)"
audience: everyone
scraped_at: 2026-01-23 15:00:17
---

We solved the wrong problem.

For two years, we optimized for capability. Better prompting. Smarter tool selection. More tokens. We treated AI fluency as a skill pack to acquire—learn the right incantations, and the machine would obey.

It worked. The capability ceiling lifted. An average engineer can now produce code at a rate that would have seemed impossible in 2023. Steve Yegge is running 10 to 20 parallel Claude Code instances through his Gas Town orchestrator, churning through implementation plans so fast that the bottleneck isn’t the agents—it’s keeping them fed with work.

And yet.

Cal Newport’s recent New Yorker piece landed with the force of a correction: “Why A.I. Didn’t Transform Our Lives in 2025.” The Year of the Agent dissolved into what Andrej Karpathy now calls “the Decade of the Agent”—a quiet admission that we don’t actually know how to build the digital employees we were promised. Sam Altman said agents would “materially change the output of companies” in 2025. Marc Benioff claimed a “digital labor revolution” worth trillions. OpenAI’s ChatGPT Agent spent nearly a quarter of an hour trying to select a value from a drop-down menu on a real estate website.

Gartner predicts over 40% of agentic AI projects will be canceled by the end of 2027—not because the models fail, but because of escalating costs, unclear business value, and inadequate risk controls. The agents don’t fail because they’re too dumb. They fail because—as Gary Marcus puts it—we’re building “clumsy tools on top of clumsy tools.”

Meanwhile, in the narrow domain of software development, something different happened. Coding agents did work. Claude Code and Codex became genuinely useful. Developers who figured out the workflow reported productivity gains that ranged from meaningful to transformative.

The question is: why the divergence? Why did coding agents succeed where general agents failed?

Newport points to one factor: the terminal is a constrained, text-based environment with immediate, unambiguous feedback. But there’s a deeper answer that matters more for what comes next.

Something doesn’t add up. The models got smarter. The tools got better. And yet the builders I talk to—the ones actually shipping with AI daily—describe a different constraint entirely.

“Raw ability to build is not my limitation anymore,” a friend told me recently. He’d just shipped an iOS app with a full backend in a few weeks, vibe-coded through Claude. “The constraint is how much I can concurrently think sensibly about.”

That’s the shift. The bottleneck moved from capability to cognitive architecture. And almost nobody has updated their operating system to account for it.

**Here’s what’s inside:**

- **The engineering manager identity shift.** Why thinking of yourself as a fleet commander—not an engineer who uses AI—changes how you allocate attention.
- **Killing the contribution badge.** The legacy instinct costing you throughput, and why starting before you’re “ready” produces better output.
- **Strategic deep-diving.** How to move between altitudes—delegating implementation while maintaining embodied understanding.
- **Temporal separation.** Why building and reflecting require different brain chemistry, and how to create feedback loops that make you better, not just faster.
- **Two kinds of architecture.** The distinction between patterns you can delegate and taste you cannot.
- **The experience problem.** What gets lost when you can manifest a vision overnight, and how to preserve the discoveries that reveal what you actually want to build.

The practices that follow aren’t prompting techniques. They’re cognitive architecture for a world where raw capability stopped being the constraint.


## **[Grab the handbook](https://www.notion.so/product-templates/The-Builder-s-Handbook-2026-2ef5a2ccb5268005b25de77768ca9c3f?source=copy_link)**

Knowing you should “think like an engineering manager” doesn’t help when you’re three tabs deep, diffs are scrolling, and you can’t tell if you should dive on the authentication flow or trust the output and keep moving. The handbook is 30 pages of diagnostics, exercises, and prompts that turn these six practices into something you can actually do. The attention-tracking protocol that reveals whether you’re in manager mode or just using the language. The altitude log that surfaces whether you’re diving on the right things or anxiously verifying everything. The rambling exercises with specific uncomfortable starter phrases that override the contribution badge until starting messy becomes automatic.

The failure modes matter as much as the practices. Anxious diving where you review every line and wonder why throughput collapsed. Shallow diving where you “verify” something and then spend three hours debugging it next week. The tourist test for whether you actually understand what you shipped, or just shipped it. These frameworks are extracted from builders figuring this out right now—not written for this article.

---


## **Practice 1: Adopt the Engineering Manager Identity**

*Not metaphorically. Operationally.*

The breakthrough for many builders isn’t a prompting technique. It’s an identity shift. One developer I spoke with put it this way: the moment he started thinking of himself as an engineering manager responsible for his team’s throughput—rather than an engineer who happens to use AI—everything clicked.

This isn’t word games. It changes how you allocate attention.

An engineer’s job is to write code. An engineering manager’s job is to ensure their team produces valuable output. The skills are different. The rhythms are different. The relationship to detail is different.

The enterprise world is catching up to this. A recent CIO piece described “the agentic AI mindset” as redefining work from “how” to “what”—users focus on setting direction and defining outcomes while systems manage the details. IBM’s Chris Hay predicts “we all become AI composers, whether you’re a marketer, programmer or PM.”

But the individual practitioner implications are more radical than the enterprise framing suggests. You’re not managing a team of humans who have their own judgment, context, and memory. You’re managing agents that are stateless, tireless, and prone to confident incorrectness. That requires a specific discipline.

Yegge’s Gas Town documentation maps the progression explicitly. Stage 5 is “CLI, single agent, YOLO. Diffs scroll by. You may or may not look at them.” Stage 7 is “10+ agents, hand-managed. You are starting to push the limits of hand-management.” Stage 8 is “Building your own orchestrator.”

At each stage, the engineering manager analogy holds. You’re responsible for throughput. You’re setting direction. You’re reviewing output. You’re not writing the code yourself—at least not most of it.

The hardest part? Letting go of the identity that got you here. If you built your career on being the person who could write elegant code, who understood systems at a deep level, who could debug anything—the transition feels like loss. But it’s not loss. It’s leverage.

---


## **Practice 2: Kill the Contribution Badge**

Here’s the legacy behavior that’s costing you: the instinct to “bring something comprehensive” before engaging with AI.

I’ve watched builders have breakthroughs when they stopped doing this. The pattern: they used to do pre-thinking work as a badge of honor, proof they’d earned the right to ask for help. Then they stopped. Started rambling into the tool. Let the intent translator do its work. The output got better, not worse.

This runs against every instinct professionals develop over a career. We’re trained that preparation signals competence. That showing up empty-handed is unprofessional. That the quality of our input determines the quality of our output.

With AI, this is often backwards. The models are better at handling unstructured input than you might expect. Your “comprehensive thought” is often just premature structure—constraints that close off better solutions.

There’s a technical reason this pattern emerged, and why it’s now obsolete. It’s a hangover from where the models were in the first half of last year—you had to do a little bit of cleanup or you’d send the model on a tangent and it would never come back.

The models got better. Your habits didn’t update. You’re still optimizing for a constraint that no longer binds.

The practice is simple: start talking before you think you’re ready. Ramble. Let the tool help you find your intent. Your job is knowing what matters, not presenting a polished brief.

Anthropic recently launched something called “Anthropic Interviewer”—a tool that conducts detailed interviews at scale. The insight behind it: if you want to understand what someone actually wants, you don’t ask them to write you a comprehensive brief. You interview them. You ask questions. You let them discover their intent through dialogue.

The same principle applies to your own work. Instead of crafting prompts, have the system interview you. Let your intent emerge through conversation rather than specification.

This is also why the “intent translator” pattern works so well. You don’t arrive with a polished specification. You arrive with raw thinking. The tool helps you crystallize it into something actionable. The crystallization process is where the real value happens—and you can’t do that crystallization if you’ve already locked yourself into a structure before you start.

---


## **Practice 3: Develop Strategic Deep-Diving Capability**

Here’s what distinguishes the best billion-token engineers from the worst: the ability to deliberately change altitude.

The discourse around AI coding has been stuck in a binary: either you understand every line (traditional development) or you accept code you don’t understand (vibe coding). Neither extreme works at scale.

The builders who are thriving have developed something more nuanced: the discipline to drop altitude deliberately, get finger-tippy feel on what matters, then ladder back out to higher abstraction.

Think of it like piloting. Cruising altitude is efficient for covering distance. But you need to descend to see terrain, to land, to refuel. The skill isn’t staying at one altitude—it’s knowing when to change.

The worst vibe coders stay permanently high. They ship features without ever understanding what they’ve built. This creates what we might call “archaeological programming”—future developers reverse-engineering the intentions behind AI-generated systems like anthropologists studying ancient civilizations.

This creates what we might call experiential debt—distinct from technical debt. Technical debt is about code quality. Experiential debt is about the gap between what you’ve built and your embodied understanding of it. A 2025 survey found that roughly 45% of developers said debugging AI-generated code is more time-consuming than debugging code they wrote themselves—not because the code is bad, but because they have no mental map of its logic.

The worst traditional developers stay permanently low. They insist on understanding every line, review every diff, refuse to delegate. Their throughput hits a ceiling.

The best engineers move fluidly. They let agents handle the initial implementation at high altitude. They drop down to examine critical paths—authentication, data handling, core business logic. They verify their mental model matches reality. Then they climb back out and continue.

Cal Newport’s analysis of why coding agents work (while other agents failed) points to something relevant here. The terminal is a constrained, text-based environment where feedback is immediate and unambiguous. When a command fails, you get explicit error messages. The model doesn’t have to guess what went wrong.

Your deep-dives should target similar clarity. Drop altitude where you can verify reality against expectation. Check that the authentication flow actually does what you think. Confirm the database schema matches your mental model. Test the edge cases that matter.

Then climb back out. Your job isn’t to understand every line. It’s to understand the lines that matter.

---


## **Practice 4: Create Temporal Separation**

Build on Tuesday. Reflect on Friday.

This sounds like productivity advice. It’s actually cognitive architecture advice.

One builder I know put Sentry monitoring on a personal project—not because he needed production observability, but because he needed artifacts for his future reflecting self. The goal: get to a point where on Friday or Sunday, he could review all his transcripts and sessions, and strategize improvements for the next week.

The principle is “write drunk, edit sober” adapted for AI-augmented work. You need temporal separation between the generative state and the evaluative state.

When you’re building with agents, you’re in a flow state. Diffs scroll by. Features ship. There’s a frenetic energy—plate spinning. You’re cycling between tabs, providing instructions, checking output, sending agents back to improve.

That state is productive. It’s also not where strategic thinking happens.

The builders who are developing genuine leverage aren’t just shipping faster. They’re building feedback loops that let them improve how they ship. That requires stepping back from the work and looking at patterns.

What kinds of prompts worked well this week? Which agents got stuck, and why? Where did you waste time on problems that should have been caught earlier? What architectural decisions from last month are causing pain today?

You can’t answer these questions while you’re in the middle of building. You need distance. You need different brain chemistry. You need the reflection sessions that most builders skip because they feel like overhead.

They’re not overhead. They’re the difference between getting faster and getting better.

---


## **Practice 5: Distinguish Two Kinds of Architecture**

There’s a conversation that keeps surfacing among builders figuring this out: the difference between two kinds of architecture.

The first kind is civil engineering patterns—the stuff you put in Claude.md files and AGENTS.md. How problems should be solved consistently across a codebase. Technical conventions. Code standards. This kind of architecture is tractable. You can write it down. Agents can follow it.

The second kind is what Christopher Alexander called “the quality without a name”—the thing that makes some towns feel better than others, some products feel more coherent than others. Why do we go on vacation to Paris and not Cincinnati? It’s not just the food. It’s a philosophy of living embedded in the design.

Call this “scaling taste.” And here’s the problem: nobody’s figured out how to outsource it.

This distinction matters because the discourse around AI development conflates these two architectures. People assume that if you can get agents to follow code conventions, you can get them to produce coherent products. You can’t. Not yet.

The first architecture—technical patterns—is where agents excel. Consistent application of best practices across a codebase. Finding repeated examples of bad patterns. Enforcing standards in every code review. Humans aren’t as good at this consistency work. Agents are.

The second architecture—taste, coherence, vision—remains human work. And this is where the cognitive architecture bottleneck really bites. You can delegate the technical patterns. You cannot delegate the judgment about what makes something feel right.

The practice here is recognizing which architecture you’re dealing with. When it’s civil engineering, lean hard on agents. Write down your patterns. Let them enforce consistency at scale.

When it’s the quality without a name, that’s you. That’s where your attention needs to go. That’s what can’t be delegated, at least not yet.

---


## **Practice 6: Accept That Experience Is Not Compressible**

Here’s the counterintuitive insight that the vibe coding discourse keeps missing.

There’s research suggesting that software development is also personal transformation. If you shortcut the software development without any opportunity or time for personal transformation, you have an incomplete development process.

The standard critique of vibe coding focuses on technical debt—bugs, security vulnerabilities, unmaintainable code. That’s real, but it’s not the deepest problem.

The deeper problem is becoming a tourist to your own software. You can build something overnight. But now you don’t have operator’s knowledge. You don’t know where the nooks and crannies are. You don’t have the embodied understanding that comes from building something incrementally.

That experience can’t be compressed. You can’t build an operator’s knowledge of a system at the same speed that AI can build the system itself.

This matters more than the discourse acknowledges. The vision you have for a product is often wrong. Not slightly wrong—fundamentally wrong. The stepwise process of building reveals what you actually want. Ship a version. Use it. Notice what’s missing. Ship again. Your understanding evolves through the building.

If you could instantly manifest your vision without going through the phases in the middle, you’d miss the discoveries that reveal what you actually want to build.

This isn’t an argument against speed. It’s an argument against skipping experience. You can build fast and ensure you’re experiencing each version of the thing. But it requires intentionality. It requires actually using what you build, not just shipping it. It requires letting your understanding evolve through contact with reality.

The builders I know who are genuinely thriving have found ways to preserve this experiential loop while still capturing the speed benefits of AI. They ship fast, but they also use what they ship. They let their understanding develop through iteration, not just through prompting.

---


## **The Shift Underneath**

There’s a frame that keeps surfacing in conversations with builders who are figuring this out: the system prompts you.

We spent 2024-2025 thinking about prompting as a skill we acquire. Get better at prompting, get better output. That frame positioned us as the active agent and the AI as the passive tool.

The builders who are thriving have flipped this. They’ve realized that working with AI is a two-way street. The system is inviting them to level up their conversational intent development skills. It’s surfacing gaps in their thinking. It’s revealing where they don’t actually know what they want.

Your job at that point isn’t to craft better prompts. It’s to understand at a deep human level what matters about what you’re building. To be open to that unfolding as you go through the process.

This sounds woo. But there’s a practical edge to it.

The stable altitude of abstraction we’ve operated at for decades—that’s disrupted now. We need the ability to drop lower than we’ve ever needed to go, and also pop higher than we’ve ever operated. That’s stressful. It feels like turbulence.

I’ve been taking this idea seriously: that intelligence is disrupting our stable altitude of abstraction. We’ve had stable abstraction for a long time. What’s stressing everyone out isn’t that AI is too dumb or too smart. It’s that the comfortable level of abstraction where we used to live no longer holds steady.

The builders who are adapting aren’t just acquiring new skills. They’re updating their relationship to their own cognitive architecture. They’re figuring out where they scale and where they don’t. They’re building systems around their limitations.

What ties these practices together is a recognition that the work has changed at a fundamental level. Adopting the engineering manager identity isn’t a productivity hack—it’s an acknowledgment that your value no longer lives in the code you produce. Killing the contribution badge isn’t about efficiency—it’s about letting go of a form of professional proof that made sense when the bottleneck was different. The discipline of changing altitude, the rhythm of building and reflecting, the distinction between patterns you can delegate and taste you cannot—these emerge from taking seriously the question of what humans are actually for when machines can do most of what we used to do.

That question doesn’t have a permanent answer. The tools will keep changing. The ceiling will keep lifting. What works today will need revision tomorrow. But the underlying inquiry—where does my cognition scale, and where doesn’t it?—that’s the question that stays with you. The builders who thrive won’t be the ones who find the final answer. They’ll be the ones who keep asking the question honestly, and keep rebuilding their practice around what they find.

---


## **The Operating System**

I’ve been calling this an “operating system,” but that framing might be wrong. Operating systems are stable. They’re infrastructure you install and forget. What I’m describing is more like a set of ongoing negotiations with yourself.

The negotiation about identity: when do you let go of being the person who writes the code, and when do you hold on? There’s no universal answer. The engineer who finds meaning in craft isn’t wrong to resist. The builder who’s ready to become a fleet commander isn’t wrong to leap. The question is whether your resistance or your enthusiasm is serving you—or just protecting something that no longer needs protection.

The negotiation about altitude: when do you trust the output, and when do you dive in? I’ve watched builders make both mistakes. Some review every line and wonder why they’re not moving faster. Others ship features they don’t understand and wonder why debugging takes forever. The discipline isn’t staying at one level. It’s developing the judgment about when to change.

The negotiation about experience: how do you capture the speed without losing the learning? This one has no clean answer. You can ship something overnight that would have taken months. But if you skip the months, you skip something else too—the slow accumulation of understanding that turns a builder into someone who knows what they’re building. Maybe you can’t have both. Maybe the tradeoff is real and you have to choose. Or maybe there’s a way to move fast while still preserving the experiential loop, and we just haven’t figured out the rhythm yet.

What I’m confident about: the bottleneck has moved. Raw capability isn’t the constraint anymore. Cognitive architecture is. How much you can concurrently hold in your head. How well you can shift between altitudes. Whether you can let go of the contribution badge without losing your sense of authorship entirely.

What I’m less confident about: whether any of these practices generalize. The builders I’ve talked to are figuring this out in real-time, and what works for someone running 20 parallel agents might not work for someone who’s just starting to trust a single one. Context matters. Your relationship to craft matters. What you’re building and why you’re building it matters.

The one thing that does seem to generalize: the system prompts you now. The AI isn’t just a tool you wield. It’s a mirror that reflects back where your thinking is clear and where it’s muddy. It’s a pressure that reveals which parts of your cognitive architecture scale and which parts don’t. It’s an invitation—or maybe a demand—to figure out what you actually contribute when the machine can do most of what you used to do.

That’s not a problem to solve. It’s a question to live with. The builders who are thriving aren’t the ones who’ve found the answer. They’re the ones who’ve stopped pretending the old answers still work.

[![](https://substackcdn.com/image/fetch/$s_!kUJQ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3d4edadd-b542-4c68-94ea-7ba7577871f0_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!kUJQ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3d4edadd-b542-4c68-94ea-7ba7577871f0_1024x1024.png)
