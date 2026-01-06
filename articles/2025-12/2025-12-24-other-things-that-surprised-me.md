---
title: "Other Things That Surprised Me"
author: "Nate Jones"
published: 2025-12-24
url: https://natesnewsletter.substack.com/p/why-im-more-optimistic-about-ai-in
subtitle: "Watch now | Call me sentimental but, after some reflection, I'm starting to think things are looking up for AI in 2026."
audience: everyone
scraped_at: 2026-01-05 19:09:29
---

I was taking inventory of 2025 this week—the way you do at the end of a year—and I realized something that surprised me.

A lot went well.

I know. Hear me out.

GPT-5 disappointed a lot of people. The hype cycle got exhausting. “Agents” became a buzzword attached to demos that broke the moment you asked a hard question. I spent a good chunk of the year skeptical that the path from impressive to reliable actually existed for most use cases.

And yet.

When I look back at what I actually watched people build this year—not the announcements, not the benchmarks, but the things that shipped and worked—I find myself genuinely optimistic about where this is going. More optimistic than I expected to be.

This isn’t a predictions piece or a hype piece. It’s an inventory. A pattern recognition piece. Things I noticed that surprised me. Patterns I didn’t expect to see. Progress that happened faster than I thought it would. It’s just a little bit Beautiful Mind…

[![](https://substackcdn.com/image/fetch/$s_!Ic-k!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fde125085-497b-4707-a4ca-0b328cc070b5_1024x572.jpeg)](https://substackcdn.com/image/fetch/$s_!Ic-k!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fde125085-497b-4707-a4ca-0b328cc070b5_1024x572.jpeg)

*(ok ok we have fun)*

Anyway, here’s what’s in the box:

- **The products that won:** What Cursor and Claude Code figured out that others missed
- **The variable most of us didn’t grasp:** Why your domain expertise isn’t translating to AI results
- **What the AI system layer looks like:** The unsexy mechanics that separate demos from production
- **A real pipeline:** Why most AI-generated outbound is slop—and what good systems do differently
- **Other patterns I noticed:** How the best teams are thinking about chaos, protocols, and middleware
- **The Moat Audit:** Twelve questions that reveal whether your system will hold under pressure
- **What to do now:** Concrete next steps based on where you’re starting from
- **Grab the prompt:** Run the audit yourself—an interactive diagnostic for 2026 positioning

The short version: we’re exiting the era when AI gets judged by how clever the release is, how impressive the benchmark looks, how exciting the demo feels. We’re entering the era where it gets judged by whether it works. That transition is hard. But the people who figured out how to make it work in 2025? They’re about to compound.

A year ago, we were coloring in the gaps with hope. We had to imagine what was possible because the pieces didn’t exist yet. Claude Code was in private beta. Reasoning models were brand new. Codex didn’t exist. Neither did Nano Banana Pro. All of that arrived in 2025.

I’d describe it as moving from standard definition to 4K. We’re finally seeing in high fidelity what these systems can actually do—not guessing, not hoping, but watching them work in production.

Here’s what I noticed—jump in for the beautiful mind post of 2025—putting all those patterns together!


## [Grab the prompt](https://www.notion.so/product-templates/A-Moat-Audit-for-2026-2d35a2ccb5268065883ec01c1b40f00b?source=copy_link)

Wouldn’t be a Nate article without a prompt! This one is designed to help you think methodically through your competitive positioning heading into 2026. It walks you through a series of 12 structured questions (also listed below, for completeness) and then helps you analyze your answers and determine a competitive positioning that works for you. It is specifically designed to highlight hidden risks in your competitive positioning you might not have seen otherwise.

---


## **The products that made me pay attention**

Let me start with what caught my eye, because I think the examples make the pattern obvious.

**Cursor** crossed $1B in annualized revenue this year with a $9.9 billion valuation. They started as a fork of VS Code, but that undersells what they built. The whole thing is designed from the ground up for AI-native development.

What does that actually mean? Context windows that span your entire codebase—not just the file you’re looking at, but the full project structure, the dependencies, the patterns you use. Agent mode that handles complex, multi-file transformations while understanding architectural trade-offs. An environment built around human-AI collaboration from day one, not a plugin bolted on afterward.

Here’s the thing: Cursor doesn’t have better model access than GitHub Copilot. GitHub has deep pockets and tight integration with OpenAI. But Copilot was added to an existing editor. Cursor was built as an AI-native environment. The interface, the context management, the way it presents suggestions and handles edits—all of it was designed around the collaboration.

**Perplexity** calls itself an “answer engine,” not a chatbot. That’s not just positioning—it’s an architectural choice. Search is woven into every interaction. Citations appear inline. The whole experience is designed around one job: find accurate information and present it with sources you can verify.

ChatGPT can search the web too. But when you use ChatGPT’s search, it feels like a feature that got added. When you use Perplexity, search is the foundation everything else is built on. According to a recent Adobe survey, 77% of ChatGPT users are using it as a search engine. But ChatGPT wasn’t built for that. Perplexity was.

**Claude Code** changed how a lot of people—myself included—think about building software. It’s Claude, but well-harnessed. Command-line ergonomics designed for agentic coding. Context management that understands codebases. Tool use reliable enough to trust with real work.

**Granola** is an AI notetaker that made an unusual choice: no bots join your calls. Other meeting tools put a visible bot in your Zoom participant list. Granola captures your device audio directly and produces notes you can guide and edit.

The founder’s question was: “How do you design AI so that you’re still in control? You’re still using your judgment, but it’s helping you do your best work?” That question shaped the whole product. The collaborative approach—where you type your own notes during the meeting and Granola augments them—keeps humans in the loop in a way that pure transcription doesn’t.

**Linear** published an essay about “design for the AI age” that crystallized something for me. They describe their product as a “workbench”—an environment that enhances the utility of other tools, including AI tools. Rather than building an AI that autonomously manages your projects, they built structured context where AI can be genuinely useful. Form shapes function.

These products are all winning. And they all have access to the same frontier models you do.

So what do they have that others don’t?


## **The variable most of us missed**

For most of 2025, I thought the formula was: **Model + X = competitive differentiation.**

Your domain expertise. Your proprietary data. Your deep understanding of the customer. That was supposed to be the X that mattered. The models were commoditizing—everyone had access to Claude, GPT-4, Gemini—so the moat had to live in X.

X is real. If you have compelling customer data, genuine domain expertise, unique relationships—those are actual advantages. I still believe that.

But here’s what I missed: **X alone isn’t enough.** There’s a variable in between that determines whether your X actually gets leveraged.

**Model + Y + X.**

Y is what I’ve started calling the harnessing layer. It’s the system design that makes the model actually work for your domain. The validation logic. The routing. The constraint enforcement. The repair steps when something breaks. The boring machinery that turns a chat completion into reliable software.

Without Y, your X just sits there. You might have the best customer data in your industry, but if you can’t build a system that uses it reliably, that advantage stays theoretical. You might understand your domain better than anyone, but if the model can’t be harnessed to apply that understanding consistently, you’re stuck in demo land.

Y is the multiplier that unlocks X.

Look at the products I mentioned:

Cursor’s Y is the AI-native IDE architecture—the context management, the agent mode, the way edits flow through the system. Their X is understanding what developers actually need. But the Y is what makes the X matter.

Perplexity’s Y is the search-first architecture with inline citations. Their X is understanding how people actually want to find information. The Y makes that understanding usable.

Claude Code’s Y is the command-line harnessing, the context management, the tool reliability. Anthropic’s X is Claude itself. The Y is what turns Claude into something you can trust with real coding work.

Granola’s Y is the no-bot-joining design, the collaborative note-editing, the way it keeps you in control. Their X is understanding that people want to be present in meetings, not replaced by transcription. The Y makes that philosophy real.

The teams that shipped in 2025 were the ones who figured out Y. Not the ones with the most resources or the fanciest models. The ones who built the harnessing layer.


## **What the harnessing layer actually looks like**

I want to get concrete, because “system design” can sound abstract. Here’s what I saw in the teams that shipped:

1. **Constraint enforcement in code, not just prompts.**

Models don’t count mid-generation. They don’t “feel” layout. They approximate. The winners in 2025 accepted that reality and stopped fighting it.

Consider a PDF template with hard boxes. Box 7: 412 characters, no more. Box 12: a disclaimer that cannot change. If Box 7 overflows, the PDF fails compliance review. If Box 12 gets paraphrased, legal rejects the batch.

“Please keep this under 412 characters” doesn’t work reliably. “Compress this” produces unpredictable results. What works is discipline: generate → count in code → flag the exact overage → freeze what can’t move → repair only what’s allowed to move → validate again.

OpenAI’s structured outputs with JSON Schema enforcement. Anthropic’s tool use with explicit schemas. These aren’t minor features—they’re acknowledgments that “just ask nicely” doesn’t work for production constraints.

2. **Validation after every transformation, not just at the end.**

Here’s what surprised me: the hardest part isn’t the initial constraint. It’s drift.

It’s relatively easy to build a loop that counts characters, flags overages, and asks a model to tighten copy. That works. The surprise was how fast it breaks when you add an apparently minor requirement like “change the tone.”

Rewriting is a different task than drafting. A model can draft within bounds and then violate those same bounds during a tone pass—even with explicit counts in the prompt. The system wasn’t enforcing the constraint at the moment of transformation. It was checking at the end, after the damage was done.

The design rule that emerged: every transformation ends with validation. No exceptions. And repair happens with error messages and exact deltas, not “try again and do better.” You tell the model precisely what’s wrong—”output is 847 characters, limit is 412, reduce by 435 while preserving the core claim”—and you validate again after the fix.

3. **Explicit frozen-versus-variable boundaries.**

Every production workflow I saw that held up under scale had explicit boundaries between what the model can change and what it cannot.

Frozen: the legal disclaimer. The company name in the header. The citation format. The data that came from the source system.

Variable: the summary language. The tone. The specific phrasing.

When you don’t draw this line, you’re trusting the model to understand what matters. It doesn’t. It will paraphrase your legal disclaimer because it thinks “clearer” is better. It will round your numbers because 47.3% looks awkward.

The fix is boring: freeze what can’t move, pass it through untouched, only let the model touch the variable regions, then validate that the frozen regions are unchanged.

4. **Repair logic with specifics.**

When validation fails, what happens? The lazy answer is “retry with the same prompt.” The better answer is “retry with the specific error, the exact delta, and clear instructions for what to preserve.”

A model that knows “you’re 435 characters over, the core claim must stay, trim the examples” will fix the problem. A model that only knows “too long, try again” will rewrite the whole thing and probably break something else.

5. **Logging you can actually learn from.**

When something breaks, can you trace it back to the specific step that caused it? If not, you don’t have a system—you have a demo. Logging shows up across the stack, but thinking about logging and where you put it is a trait of successful teams.


## **What this looks like in a real pipeline**

The internet is full of people complaining about AI-generated outreach. Fair—most of it is terrible. But the builders who treated outbound as pipeline engineering, not prompt magic, started producing emails that didn’t read like AI slop. That actually got responses.

The difference wasn’t the model. It was the system around it. (I know, I helped design the system.)

What slop systems do: no grounding research, no ICP filtering, no offer discipline, no disqualifying criteria, no claim constraints, no QA loop. Just “write a cold email about our product” and spray.

What the good pipeline does: source pack with real company signals, persona constraints for the specific role and seniority, claim whitelist so you only say things you can defend, cadence logic so touch one and touch three serve different purposes, lint checks for character limits and spam triggers, tone guardrails to kill “I hope this email finds you well,” and human QA on a sample before the batch goes out.

This stuff gets weirdly specific, and I include a few notes here mostly to remind you that when you build agentic systems successful teams go to this level of detail:

> ***TOUCH 1:** Problem-aware hook. Max 847 chars. Must reference one verifiable company signal. No product pitch. CTA: curiosity only.*
>
> ***TOUCH 2:** Social proof. Max 612 chars. One specific outcome from similar company. CTA: “worth a conversation?”*
>
> ***TOUCH 3:** Direct ask. Max 534 chars. Acknowledge previous touches. Clear meeting request. Calendar link required.*
>
> ***CONSTRAINTS:** No “I hope this finds you well.” No “I noticed your company.” No claims not on whitelist. No competitor mentions.*
>
> ***VALIDATION:** Character count per touch. CTA presence. Spam score below threshold. Human review on 10% sample.*

Ultimately the gap between “AI slop” and “solid outbound” comes down to constraint enforcement and validation loops, not model choice. That’s Y in action.


## **What do you do with agent mistakes?**

I remember earlier this year watching a demo of an “autonomous research agent.” It browsed the web, extracted information, summarized sources, synthesized findings. Impressive output. Confident citations.

Then I asked what happens when it returns a citation that doesn’t exist.

Long pause. “We’re working on that.”

Meanwhile, a team I advise had built something much uglier: route the intent → fetch from approved sources only → extract to a strict schema → validate that every citation resolves → compose the draft → diff against the template → flag for human review before send. No autonomy. No browsing. Completely traceable. Shipped in six weeks.

That was the hinge for me. Not “agents don’t work”—they clearly can, for certain problems. But my default changed. Scoped workflows with deterministic checkpoints beat open-ended autonomy for most production use cases.

The industry promised agents that do everything. What actually worked was narrower: LLM-as-tool, surrounded by determinism.

When you let a model decide what to do next, you multiply failure modes. Each decision point is an opportunity for drift. The output might be impressive, but when it breaks, you can’t trace why.

When you route and constrain, you get repeatability. The model does what it’s good at—turning unstructured into structured, drafting language, translating intent into a candidate output. Code does what it’s good at—counting, routing, validating, retrying, producing predictable failure modes.

The pattern I keep seeing over and over is worth reminding you of as we close out the year:

**Generate → Validate → Repair → Validate again**

It’s a drumbeat because it works.

Every step is inspectable. Every failure is attributable. You never trust that a transformation preserved the constraints you set earlier. You check. Every time.

Some people call this anti-agent. I believe they’re wrong. I think it’s pro-agent in the truest sense—understanding what LLMs are actually good at and building systems where they thrive.


## **Why this makes me optimistic**

Here’s the thing about Y: it’s learnable.

You don’t need special access to build a good harnessing layer. You don’t need a research team or a billion-dollar training run. You need to understand your problem deeply, and then you need to do the unglamorous work—schemas, validation, routing, repair logic, logging.

I watched individuals out-execute teams this year. Not because they had better models. Because they treated this as workflow engineering rather than model worship. They built low-tech scaffolding: templates, validators, retries. They iterated aggressively. They instrumented failure so they could learn from it.

And they shipped while larger teams were still arguing about which foundation model to standardize on.

The messy middle—the integration layer, the harnessing layer—is underbuilt. That’s not a problem. That’s an opportunity.

If you already have a real X—domain expertise, customer relationships, proprietary data—and you’ve been frustrated that it’s not translating into AI results, this is probably why. The unlock isn’t a better model. It’s building the system that lets you actually use what you have.

---


# **Other Things That Surprised Me**

The harnessing layer insight was the big one. But I noticed other patterns that made me unexpectedly hopeful.


### **Teams are starting to think about entropy**

This sounds theoretical, but it’s practical.

A lot of teams in 2025 accidentally built systems that increase chaos. Too many unconstrained steps. Too many loops. Too many places for the model to get creative in the wrong direction. The output might look impressive on any single run, but across runs, across edge cases, across scale—chaos accumulates.

People sometimes look at token generators and conclude they’re inherently uncontrollable. Probabilistic. Unmanageable. One response is to wrap them in business rules, which helps. But I think the higher-level insight is that LLMs can actually be entropy *reducers* if you structure where they live correctly.

What was magical before can become disciplined magic.

I see this in the AI-native interfaces that actually feel good to use. TLDraw comes to mind—it feels like magic, but underneath it’s extremely structured. The way Figma is handling AI at the end of 2025. Capsules. These are products where LLMs are harnessed to produce more coherent, more beautifully designed experiences.

There’s less entropy in the system when I can get the answer I need inside the interface I have, without spraying tokens everywhere searching for something on the open internet. There’s less entropy when I can talk to my Figma design and get it correctly laid out, then push it directly into Claude Code.

Entropy is a high-order way of thinking about agentic system design. You can design systems that are high entropy or low entropy, depending on where and how you harness the LLM. Teams are starting to grasp this intuitively, even if they don’t have the language for it yet.


### **Protocols are starting to matter more than prompts**

We’ve been tempted to treat prompting as the primary interface. That was true in the chat era. Now I think we’re going to treat it more as a layer in a more standardized toolchain.

The teams that win won’t be the ones with the cleverest instructions. They’ll be the ones where systems can reliably call tools, pass structured outputs, hand off work between components, and recover when something goes wrong.

On December 9, Anthropic donated MCP to the Linux Foundation’s new Agentic AI Foundation. OpenAI and Block co-founded the effort and contributed AGENTS.md and Goose as founding projects. That’s a signal. The integration layer is turning into shared infrastructure rather than bespoke glue.

What this means for 2026: we’re going to be reinventing the wheel less. There’ll be less custom plumbing and more composable systems.

Integration is a skill, not a secret. The messy middle is underbuilt. The opportunity is wide open.


### **The post-ChatGPT middleware layer is wide open**

Cursor proved you can thrive as a “wrapper.” That’s a big deal. The middleware layer isn’t a consolation prize—it’s where a lot of value gets created.

Part of what makes this work is the insight that not all requests are the same. ChatGPT trained us to treat every utterance identically. But compelling new products route users to different experiences based on intent.

Generative UI is downstream of this insight. If I want to cancel my phone bill, I should get a purpose-built interface—not a chat response telling me where to find the cancellation page.

I expect 2026 to be the year teams get much better at mapping customer intent to a distribution. Handle 90% of common requests with specific, beautiful flows. Route the long tail to more flexible agent workflows. That’s a powerful experience for everyone, not just power users who know how to prompt.


### **Graphical AI is about to become completely normal**

This might be the most underrated shift.

Nano Banana Pro represents a real breakthrough. When you can edit and regenerate images trivially, the economics of visual content change completely.

We’re going to see work product—decks especially—that’s just images now. Not slides with text boxes and bullet points. Generated visuals you can edit and regenerate until they’re right. You can already do this inside Manus. Getting a new deck becomes trivial.

When images are essentially solved, it opens up build opportunities we’re only beginning to explore.


### **The skills repricing is real**

A lot of strong engineers haven’t built the muscles that matter here yet: spec-writing, evaluation design, constraint enforcement. They’re optimizing prompts because that’s the visible lever. The invisible levers—schemas, validation, routing—aren’t in their muscle memory.

The market is starting to reward people who can hold two things in their head at once: how AI behaves at a high level of detail, and the underlying craft of their domain.

Most organizations are still split between an AI person and a domain person. I wonder if 2026 is when we see more roles that put both in the same head. When you pair an AI specialist with a domain expert, each head has only half the picture. The people who have both are going to be incredibly valuable.

The path is four skills: schemas, validation logic, routing patterns, and failure instrumentation. All learnable. You don’t need a CS degree, but you do need comfort with rules, basic scripting or no-code logic, and obsessive testing.


### **Robotics is going to have a huge year**

I’m not just talking humanoids.

We’ve had a full year to build on reinforcement learning groundwork. Nvidia announced their digital warehousing concept back in January—giving robots thousands of simulated years of experience so they’d be safer in real environments. That’s had time to mature.

Toward the end of this year, there was a breakthrough in using POV camera footage of human hands to help robots learn hand movements. The arc of 2025 was getting learning systems in order. The arc of 2026 will be scaling LLM-driven robotic capability.

The winners will be the ones who can ship and continuously update robot brains. Consumers expect LLM updates every few months. They’ll expect the same from their robots—over-the-air improvements that make the machine smarter over time.

The primitives are all there. Building the ecosystem around continuous improvement is the challenge.

---


# **[The Moat Audit](https://www.notion.so/product-templates/A-Moat-Audit-for-2026-2d35a2ccb5268065883ec01c1b40f00b?source=copy_link)**

If you’ve read this far and you’re thinking about your own work, here’s the diagnostic I use. Twelve questions that expose whether you’re building a real harnessing layer—or just hoping the model figures it out.


### **Constraints and drift**

1. **Where do your constraints live—in the prompt, in code, or both?**
2. **What validates output before it ships to a user?**
3. **What happens when a requirement changes mid-workflow—new tone, different length, additional format rule?**
4. **Is validation re-applied after each transformation, or only at the end?**


### **Logging and traceability**

5. **What gets logged?** Failures, retries, diffs, token counts, latency?
6. **When something breaks, can you trace it back to the specific step that caused it?**


### **Determinism and routing**

7. **What’s deterministic in your system versus what’s left to the model’s discretion?**
8. **How do you handle the head of the distribution (common requests) versus the tail (rare, complex ones)?**
9. **What’s your repair logic when validation fails?** Retry with the same prompt? Retry with error context? Escalate to human?


### **Review and boundaries**

10. **Who reviews outputs before they reach users—a human, a second model call, or neither?**
11. **What’s frozen (cannot be changed by the model) versus variable (can be rewritten)?**
12. **If I asked you to change the tone of the output right now, what breaks?**

If you can’t answer these questions, you’ve found your gaps. If you can, you might already be building something durable.

---


## **What To Do Now**

**If you’re just getting started:** Pick one workflow where you’re currently prompting and hoping. Change that view. Add one validation step in code. See what breaks. That’s your curriculum.

**If you’re already building:** Run the Moat Audit on your most important workflow. The questions you can’t answer are the gaps that will bite you.

**If you’re leading a team:** Stop hiring for “prompt engineering.” Start hiring for systems thinking—people who ask “what validates this?” before they ask “what model should we use?” Look for dual fluency. Build your harnessing layer before you optimize your prompts.

---


## **What This Year Clarified**

The teams that exceeded my expectations in 2025 weren’t chasing frontier capabilities. They were engineering reliability. Accepting constraints. Building the harnessing layer. Finding people who could hold both the technical reality and the job-to-be-done in their heads at once.

That’s the pattern. And here’s why I’m optimistic: it’s not a secret. The path is learnable. The tools are accessible. The playbook is visible.

If you have a real advantage—domain expertise, customer data, a genuine understanding of the problem—you can now leverage it. Y is the multiplier that unlocks X. The harnessing layer is what makes your domain expertise matter in production.

A year ago, Claude Code was in private beta. Reasoning models were brand new. Codex didn’t exist. All of these things that feel like essentials for building in 2026 came into being over the course of 2025.

The building blocks exist. The ecosystem is maturing. The hype has settled into something more sustainable: the hard, meaningful work of making AI actually work.

The teams that figured this out in 2025 are about to have a very good 2026.

*What surprised you this year? What are you looking forward to?*

[![](https://substackcdn.com/image/fetch/$s_!fN-k!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc7638f9a-c488-4eba-8c05-2c4ec091f9d7_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!fN-k!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc7638f9a-c488-4eba-8c05-2c4ec091f9d7_1024x1024.png)
