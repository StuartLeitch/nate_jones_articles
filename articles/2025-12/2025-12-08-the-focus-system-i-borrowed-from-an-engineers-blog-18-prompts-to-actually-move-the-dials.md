---
title: "The focus system I borrowed from an engineer's blog + 18 prompts to actually move the dials"
author: "Nate Jones"
published: 2025-12-08
url: https://natesnewsletter.substack.com/p/grab-the-18-prompts-i-use-to-diagnose
audience: everyone
scraped_at: 2026-01-05 19:10:21
---

*When people ask how I “get so much done,” they usually assume I have more discipline, better hacks, or some kind of magical AI setup.*

*I don’t.*

*What I do have is a mental model I borrowed from an engineer named Can Duruk, plus a handful of AI workflows that help me quietly adjust the conditions of my day instead of just grinding through it.*

*Duruk’s insight is simple: your ability to focus isn’t really a character trait. It’s a function of three things—how often you’re interrupted, how long it takes your brain to reload after each interruption, and how much unbroken time your work actually requires. Once you see those three variables, you can stop treating bad days as personal failures and start treating them as something you can actually reason about.*

*The math is a little uncomfortable. Research shows that many knowledge workers get interrupted every few minutes. If your brain needs ten or fifteen minutes to reload each time, the numbers don’t work out. No amount of willpower fixes arithmetic.*

*But the same math is also kind of hopeful. Small changes to those parameters can produce surprisingly large effects. One fewer interruption per hour might dramatically change how many deep work blocks you get in a week. That’s where AI starts to feel useful to me—not as a productivity boost, but as a way to nudge those variables.*

***Here’s what’s inside:***

- ***The three-variable model in plain language.** How interruption rate, recovery time, and block size interact to shape your day before it even starts.*
- ***What the research actually says.** The numbers from real workplaces, and why they explain a lot of the exhaustion people feel.*
- ***How I’ve been using AI on each variable.** Some workflows I’ve found helpful for reducing interruptions, reloading context faster, and reshaping work to fit fragmented time.*
- ***18 prompts you can use.** Organized by what you’re trying to do:*

  - ***Diagnosis & Baseline** — Figure out your own λ, Δ, and θ, or audit your calendar to see what your schedule actually allows.*
  - ***Reducing Interruptions (λ)** — Build a triage system for email and messages, convert meetings to async, or audit your own self-interruption habits.*
  - ***Faster Context Reload (Δ)** — Capture your state at the end of a work block, synthesize scattered sources into a single status snapshot, design a personal reload ritual, or extract decisions from messy handwritten notes.*
  - ***Reshaping Work (θ)** — Chunk a project to fit your fragmented schedule, decompose a single overwhelming task, or match today’s tasks to your actual calendar.*
  - ***Team-Level Focus** — Audit focus capacity across a team, draft focus norms that aren’t preachy, or calculate the true cost of a meeting in focus blocks destroyed.*
  - ***Weekly Practice** — Set up a one-week experiment, run a weekly review through the λ/Δ/θ lens, or troubleshoot what went wrong on a bad day.*

*The full article breaks down the model, walks through how I use AI on each variable, and includes the complete prompt library. If you’ve ever gotten to 5pm and realized you spent the whole day responding to things—Slack pings, “quick questions,” meetings that could have been emails—without ever touching the work that actually matters to you, this might help explain what’s happening. And more importantly, give you something to do about it.*


## **[GRAB THE PROMPTS](https://www.notion.so/product-templates/Prompts-for-deep-work-2c25a2ccb526808e9a1bcf43b899d316?source=copy_link)**

This is a library of 18 prompts organized around Can Duruk’s λ/Δ/θ model of focus. The idea is simple: instead of generic productivity advice, these prompts help you see and adjust the three variables that actually determine whether deep work is possible on any given day.

The library covers diagnosis (figuring out your own parameters), intervention (reducing interruptions, reloading context faster, reshaping work to fit your calendar), team-level management (for people who influence how others work), and weekly practice (experiments, reviews, and troubleshooting bad days). Each prompt ends with an activation trigger so the model actually runs instead of just acknowledging your request.

I’ve been using versions of these for months. They’re not magic—they just make the system visible enough to adjust.

Source: <https://justoffbyone.com/posts/math-of-why-you-cant-focus-at-work/>


### **The model**

Duruk’s essay takes something most of us have felt—”my whole day disappeared and I’m not sure why”—and frames it the way an engineer might frame a system problem. Three parameters, some simulations, and a map of where deep work is likely and where it’s basically not.

Here’s how I think about it.

There are three numbers that quietly shape your day. The first is how often you’re interrupted per hour. Duruk calls this λ. It includes everything—Slack, email, “got a sec?” questions, calendar pop-ups. Anything that pulls your attention away from what you were doing.

The second is how long it takes your brain to actually get back into the problem after an interruption. This is Δ. You’re back at your desk, but you’re not back in the work yet. Research suggests this is often 10–16 minutes for things like email and instant messages. That number surprised me.

The third is the minimum block size for what you’d consider “real work”—how much uninterrupted time you personally need before it feels like you made meaningful progress. This is θ. For a lot of knowledge work, this might be 45–90 minutes. If your blocks are consistently shorter than that, you’re mostly thrashing.

The structure matters more than the Greek letters. Once you name these three things, you can look at your calendar and get a rough sense of whether deep work is even realistic on a given day.


### **Why small differences matter**

Duruk adds one more piece that stuck with me: a way to count how much real work you actually get from a day.

Take all your focus blocks—the stretches between interruptions. For each one, ask how many theta-sized chunks fit inside it, rounding down. Add those up. That’s your capacity.

The rounding down is harsh.

His example: you have three focus blocks—90 minutes, 45 minutes, and 20 minutes. Total focus time is 155 minutes. But your capacity depends on what you consider a “unit” of real work. If your threshold is 30 minutes, you get 4 units. If it’s 45 minutes, you get 3. If it’s 60 minutes, you get 1.

Same 155 minutes. Very different outcomes.

This matches how my days actually feel. I “worked all day,” but if the blocks were the wrong shape, it doesn’t add up to much. The math just describes the vibe.


### **What the research says**

The uncomfortable part of Duruk’s analysis isn’t the model itself. It’s what happens when you plug in real numbers.

Field studies have found that knowledge workers switch activities roughly every three minutes. People receive something like 7–8 email and IM alerts per hour. Recovery after each interruption takes 10–16 minutes. Microsoft’s more recent data suggests that heavy collaborators—people living in meetings and messaging—can see interruptions every couple of minutes during core hours.

When Duruk runs simulations at those parameters, the results are pretty grim. Most days don’t even produce a single 15-minute block of uninterrupted focus, let alone 60.

His conclusion: at realistic interruption rates and recovery times, deep work is statistically rare. Not because people lack discipline, but because the environment has been structured in a way that makes focus almost impossible.

When I first read that, a lot of things made more sense. The tiredness. The feeling of working all day without making progress. It wasn’t a character flaw. It was just what the numbers predicted.


### **A different way to think about it**

Once you start seeing your day as a point on a map—defined by these three variables—the self-blame starts to feel less useful.

If your expected number of deep work blocks is basically zero at 9am, you probably shouldn’t expect magic by 4pm. Focus isn’t a moral achievement you’re failing to reach. It’s something you can measure, and maybe adjust.

I’ve started thinking in three questions before any serious work session:

What kind of day is this? Low interruptions with empty calendar space, or high interruptions with back-to-back calls?

What kind of work am I trying to do? Something that needs 90 minutes of continuous thought, or something I can do in 25-minute chunks?

What would have to change for this to work better? Fewer interruptions, faster recovery, or smaller pieces of work?

The hopeful part: the system is sensitive. A single fewer interruption per hour, or a slightly shorter recovery time, or a slightly smaller work chunk, can change the distribution of your week more than you’d expect.

That’s where AI has started to feel useful to me. Not as a way to do more, but as a way to shift those variables a little bit.


### **How I’ve been thinking about AI here**

When I say “using AI for focus,” I mean something pretty specific:

Using it to reduce how many things get through to me. Using it to reload context faster after interruptions. Using it to reshape work so more of it fits into the time I actually have.

The rest—summarizing documents, drafting emails—is just implementation. The framework is what I keep coming back to.


### **On interruptions**

This is the hardest variable to change because it’s mostly about other people and culture. But it’s also the most powerful lever, according to the math. Doubling your interruption rate more than doubles your lost time, because interruptions cascade and fragment your remaining blocks.

I’ve been treating AI as a kind of gate in front of my attention.

On the email side, I use AI-powered filters to sort things by urgency. Important threads get through. Low-stakes notifications get batched. Things that look like routine questions get queued for later. You can do this with dedicated tools, or you can hack it with simple rules that route different categories into different buckets. The prompt library includes one for designing a three-tier triage system—immediate, batched, and digest—that you can customize to your actual role and relationships.

On the meeting side, I try to default toward async when possible. Status updates that can be written instead of spoken. Decision documents instead of reading sessions on video calls. Calendar tools that protect certain blocks unless someone explicitly overrides. There’s a prompt specifically for converting a recurring meeting to async—it walks you through diagnosing whether the meeting is actually about status, decisions, or relationship maintenance, then helps you design the replacement and write the transition message.

The tradeoffs are real. Some things get misclassified. People who expect instant responses may feel like I’m less available. Occasionally something sits for an hour longer than I’d like.

I’ve decided those costs are worth it for moving my day into a more workable region. Your math might be different.

One thing worth noting: Duruk points out that roughly half of interruptions are self-inflicted. The tab-switching, the inbox checking, the Slack grazing. This was humbling to read. I’ve started using AI as a mirror for this—the self-interruption audit prompt helps you identify your triggers and design friction interventions that actually work. It’s not AI doing work. It’s AI making your own patterns harder to ignore.


### **On recovery time**

This is the quiet one. The interruption itself isn’t the whole cost—it’s how long the interruption lingers after it’s technically over.

If you’re interrupted ten times a day and you can shave five minutes off each recovery, that’s almost an hour of capacity you didn’t have before.

I’ve been using a mix of simple habits and AI for this.

At the end of a work block, or when I’m forced to stop, I try to leave myself a few notes. What I just did, what’s next, what’s still unclear. If it’s complicated, a quick voice note. Then I use the context capture prompt to clean that up into something short and searchable—a “reload packet” that’s optimized for resuming in under two minutes.

The next time I come back, I don’t start from zero. I have a little packet from my past self.

For work that spans multiple tools—docs, issues, Slack, code—I’ll sometimes dump the relevant pieces into one place and use the cross-source synthesis prompt to get a single status snapshot. “Given this document, this thread, and this pull request, what did we decide and what’s still open?” It hands me a story instead of making me reconstruct one.

I still use a paper notebook a lot. Flipping back a page often reloads context faster than any digital tool. When my handwriting is too messy to read, I take a photo and use the handwritten notes extraction prompt. It turns scribbles into decisions, action items, and open questions I can actually search.

The pattern is simple: invest a little at the end of each block to make the next reload cheap. AI just makes that investment easier to capture and retrieve.


### **On the shape of work**

This is the part I find most interesting.

If your standard for “real work” is 90 minutes of uninterrupted focus, but your life only produces 30-minute windows, you’re going to feel like a failure constantly. The math guarantees it.

One response is to lower your standards—convince yourself that 15 minutes is enough. But there’s another option: keep your standards honest for the work that really needs long blocks, and reshape everything else to fit smaller chunks.

This is where AI has been genuinely helpful.

I’ll describe a large goal—something like “write a long piece on X”—and use the project chunking prompt to break it into tasks that match my actual calendar. It asks about my protected focus blocks, my interruptible windows, and which parts require my judgment versus could be delegated. Then it delivers high-theta tasks for my best time, mid-theta tasks I can do between meetings, and low-theta tasks I can do when I’m tired or hand off entirely.

For a single overwhelming task—the kind where you keep looking at it and then doing something else—the task decomposition prompt helps you work backward from “done,” find natural breakpoints, and tag each subtask by the kind of focus it needs.

This doesn’t do the work. It changes the shape of the work so more of it survives a messy day.

The risk is real: if you over-fragment everything, you can lose your sense of the whole. That matters. So I try to protect the few things that genuinely need long blocks, and reshape only the rest.


### **At the team level**

If you manage people or influence how a team works, the math has different implications.

Duruk suggests treating focus like uptime—something you can measure and manage toward. That might mean agreeing that people should get a certain number of uninterrupted blocks per week, or that you don’t schedule recurring meetings before a certain hour, or that Slack isn’t expected to be real-time except in emergencies.

AI can help with measurement. The team focus audit prompt analyzes calendars across multiple people, flags who’s most fragmented and why, identifies “zombie meetings” that no one owns but everyone attends, and recommends structural changes ranked by total blocks recovered.

There’s also a prompt for estimating the true cost of a meeting—not just the time in the room, but the fragmentation cost (how many focus blocks does it break?) and the context-switch tax (recovery time multiplied by attendees). It’s a useful exercise before adding another recurring meeting to everyone’s calendar. The prompt ends by asking: what would this meeting need to produce to be worth that cost?

The harder part is cultural. You still need the willingness to say no to things. AI just makes the costs more visible. The focus norms prompt helps you draft team agreements that protect focus without being rigid or preachy—it asks about what’s been tried before and why it failed, because most focus initiatives die from implementation, not intention.


### **Building a practice**

The model is only useful if you actually use it. I’ve found that a weekly rhythm helps.

The one-week experiment prompt helps you set up a controlled test: defend one 90-minute block each morning, pick one high-theta task per day, end each block with a context capture, and let the rest of the day be messy. On Friday, compare what you accomplished in those blocks versus the rest of the week. It’s a way to feel the parameters instead of just reading about them.

After that, the weekly review prompt helps you look at your week through the λ/Δ/θ lens. What changed? What broke your focus most? What worked? What one adjustment should you try next week?

And for the days that just fall apart—which still happen—the troubleshoot prompt helps you diagnose what went wrong. Was it too-high λ, slow Δ recovery, or a mismatch between your tasks and your available blocks? Where could you have intervened? Is this a one-off or a pattern?

The goal isn’t to optimize every day. It’s to notice the system and adjust it over time.


### **A small experiment**

If any of this resonates, here’s something you could try for a week.

Defend one 90-minute block each morning. No meetings, no messaging, no email. Use whatever filters make sense so only real emergencies get through.

Pick one substantial task per day. Something that actually benefits from uninterrupted time. Use the chunking prompts to break it into milestones if that helps.

At the end of each block, spend a few minutes capturing where you are. Use the context capture prompt to turn your notes into a reload packet.

Let the rest of the day be whatever it is. Don’t try to fix everything at once.

On Friday, compare. What did you accomplish in those morning blocks versus the rest of the week? How did it feel?

You might start noticing the parameters. And once you notice them, they’re hard to unsee.


### **Closing thought**

I don’t think focus is a mystical trait that some people have and others don’t. I also don’t think AI is a magic solution that makes broken systems work.

But I do think attention is something you can reason about. You can notice the variables that shape your day. And you can use whatever tools are available—including AI—to nudge those variables in a better direction.

That’s what I’ve been trying to do. Not perfectly, not with any grand system, just a little bit at a time.

The prompts are linked above. Take or leave whatever’s useful.

[![](https://substackcdn.com/image/fetch/$s_!zaRo!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F60fba33c-8fa4-4cfb-9618-28532b231b0d_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!zaRo!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F60fba33c-8fa4-4cfb-9618-28532b231b0d_1024x1024.png)
