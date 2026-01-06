---
title: "Why capable AI is a liability when intent is off + my template that makes interpretation visible before action"
author: "Nate Jones"
published: 2026-01-02
url: https://natesnewsletter.substack.com/p/my-honest-field-notes-on-why-ai-agents
subtitle: "Watch now | Asking AI to do something for you without being explicit is basically rolling the dice. Here's how you get AI to actually do what you need it to (instead of its best guess)."
audience: everyone
scraped_at: 2026-01-05 19:08:32
---

You ask AI to “find a time for a quick sync with the team,” and it drops the meeting right into the one two-hour block you keep clear every week for focused work. Technically, everyone was available. The AI did exactly what you asked. It just missed the thing you didn’t say out loud: that block is protected for a reason.

This feels like a small annoyance when AI is just suggesting things for you to review. You catch the mistake, you fix it, you move on. But AI isn't just a chat interface anymore. A growing number of tools now let AI take real actions on your behalf—booking meetings, sending emails, editing files, managing workflows. And the same pattern gets dangerous fast once AI can actually do those things.

In technical contexts, this looks like a developer asking a code agent to “clean up this module and simplify.” The agent makes it shorter by stripping out what looks like redundant complexity, and the result looks clean—fewer lines, tighter logic. But in the process, it also removed the edge-case handlers that only fire in unusual situations and the error logging that makes debugging possible when something breaks. The agent heard “simplify” and optimized for brevity. The developer meant “make it easier to read without changing how it works.”

These aren’t edge cases. They’re the predictable failure mode when you let capable systems act on underspecified intent.

In chat, a misread costs you a follow-up message. With tools, a misread becomes an email you usually can’t claw back once it’s delivered, a file you can’t recover if it wasn’t backed up, a relationship you can’t un-burn. This isn’t a hallucination problem. It’s an objective problem: the model did exactly what you asked, interpreted through a goal you didn’t mean—and committed before you could stop it.

The fix is not “better prompts.” The fix is making interpretation visible, and gating the actions that can’t be undone.

Here’s what’s inside:

**Why intent breaks:**

- The structural shift from chat to tools (and why it changes everything)
- Why “write better prompts” doesn’t solve this
- The three failure patterns that cover most agent mistakes

**What the fix looks like:**

- Surfacing interpretation before action
- What an intent doc actually looks like
- Gates: when to pause, when to proceed
- Deciding when to require confirmation

**Making it stick:**

- The audit trail you need when something goes wrong
- A quick gut check for your current systems

Let’s start with why this keeps happening—and why the obvious fixes don’t work.


## **[GRAB THE PROMPTS](https://www.notion.so/product-templates/The-Intent-Problem-Prompt-Kit-2d95a2ccb52680b5973fe350c35c5351?source=copy_link)**

This prompt kit isn’t a generic checklist—it’s the implementation layer for everything above, built for different speeds depending on what you need.

The 60-Second Install gives you one paste-anywhere instruction that forces any AI to show its interpretation before acting. The 5-Minute Habit adds the intent doc—the same four-line template from this article—so “what do you think I mean?” becomes a standard check before anything goes out. The 20-Minute Upgrade applies the three buckets (let it run, checkpoint, always confirm) so you’re not babysitting every action or letting risky ones slip through.

For teams deploying agents, there’s more: an audit prompt to surface where you’re exposed, a disambiguation prompt that prevents the AI from silently picking one interpretation when two are valid, and a receipt prompt so you can reconstruct what happened when something goes wrong.

These patterns came from watching real intent failures—the follow-up emails that torched relationships, the “clean up the docs” disasters, the polished decks that lost their argument. They’re designed to catch the failure modes that actually happen, not theoretical edge cases.


## **THE SHIFT THAT CHANGED EVERYTHING**

The problem becomes obvious once you see it: chat mistakes are cheap, but tool mistakes are commitments.

In chat, the model misunderstands and you notice and you correct it. The whole medium is reversible. You type a clarification, the model adjusts, no harm done except to your patience.

But once you give models access to tools—files, email, calendars, databases, money—a misread intent stops being a conversational hiccup and starts being an action in the world. The agent isn’t suggesting a response for you to review. It’s sending the email, deleting the file, modifying the record.

Some of those actions have undo buttons. The ones that matter usually don’t. You can restore a deleted file if it’s backed up. Email is trickier than people think: some clients let you cancel by delaying delivery (Gmail’s Undo Send gives you 5–30 seconds), but once a message is actually delivered you generally can’t pull it back—Outlook’s recall only works under specific Exchange/M365 conditions within the same organization. You can roll back a database change if you caught it quickly. You can’t undo the reputational damage from an agent that contacted someone who’d explicitly asked to be left alone.

Hallucination is a knowledge problem—you fix it with better retrieval, citations, grounding. Intent misalignment is an objective problem. And objective problems get more dangerous as capability increases, because capable systems pursuing wrong objectives cause more damage than incapable systems pursuing right ones.

---


## **WHY “WRITE BETTER PROMPTS” DOESN’T FIX THIS**

The instinct is to solve intent problems with better prompts. Be more explicit, add constraints, specify edge cases, write longer instructions.

This helps. But it doesn’t solve the problem.

Intent isn’t in the text the way facts are. You can put facts in a prompt: names, dates, constraints, instructions. Intent is different—it’s your priorities and how they’re ordered, the tradeoffs you’d accept, what “done” means in your head versus what “done” sounds like in the words you chose, what you’d regret if the model guessed wrong.

Humans read that stuff from sparse signals. Someone says “clean up the code” and another engineer infers: don’t break anything that’s currently working, preserve the weird stuff that looks unnecessary but probably isn’t, ask if you’re unsure. We simulate consequences before we act. We ask when we’re uncertain. Models don’t run that inference reliably. They pick an interpretation that seems reasonable, and they execute.

And longer prompts often bury the one sentence that matters. Positional effects in long contexts (”Lost in the Middle,” Liu et al. 2023) show that performance can drop when key information sits in the middle of long prompts—models tend to weight the start and end more heavily. You carefully specify your constraints in paragraph four, and the model’s attention doesn’t prioritize the critical instruction. More tokens can dilute the signal instead of strengthening it.

You can’t fully specify intent in text. Users can’t articulate all their constraints even when they try. And models don’t reliably extract intent even when it’s there.

---


## **THE THREE WAYS INTENT BREAKS**

In practice, most failures I see fall into one of three buckets.


### **The ambiguity problem: when AI picks one meaning without clarifying**

The request has multiple plausible interpretations, and the model commits to one without surfacing the choice.

“Simplify” could mean reduce nesting, reduce files, or reduce dependencies—those are different tasks with different outcomes. “Clean up the docs” could mean organize them, summarize them, or delete the old ones. The model picks one reading and runs with it, and you find out which reading it picked by discovering what it did.

The code-cleanup example from the opening is this pattern. “Simplify” had multiple valid meanings. The developer meant “make it easier to read without changing behavior.” The model heard “make it shorter.” Both interpretations are defensible. Only one preserves the error handling.

When the model detects multiple plausible meanings, the fix is to force the ambiguity into the open. Don’t silently pick one—surface two concrete interpretations and let the user choose. “I can do either (A) refactor for readability while preserving all behavior, or (B) remove code that appears unused. Which one?” The safer interpretation is the default; the user has to actively choose the riskier path.


### **Wrong Optimization Target**

Sometimes AI nails the thing you can count while entirely missing the point.

You ask it to “tighten up this email,” and it makes it shorter. It cuts the sentence that was doing the real work—the one that acknowledged the other person’s concern, or explained why you were asking, or softened a request that could read as a demand. The email is now 40% shorter. It’s also going to start a fight you’ll spend two hours repairing.

Same pattern with meeting summaries. You ask for a recap with action items, and what comes back looks clean: decisions, owners, next steps, all neatly formatted. But one of the “decisions” was actually still under discussion, and a key caveat got flattened into false certainty. You walk into the next meeting thinking everyone’s aligned, and you’re not.

The proxy metric improved. The real outcome got worse. You’ll see this with decks that get “polished” until the narrative falls apart, with engagement metrics that climb while conversions tank, with code that gets “cleaner” while edge cases break. The AI did what you asked. It optimized for the thing that was easy to measure, not the thing you actually needed.

This one’s harder to catch than ambiguity, because the output looks like success until you see what it cost.


### **Social Boundary Violations**

Some constraints aren’t written anywhere. They live in context—who’s in what mood, what history you have with someone, what shouldn’t be said yet, who shouldn’t be in the room. Humans pick up on these signals without thinking about it. AI doesn’t.

You tell an agent to “follow up with anyone who hasn’t replied in two weeks.” It does. It also follows up with the contact who explicitly asked to be left alone last month. It follows up with the person who said no and is now getting a third touch. The instruction was technically fulfilled. The relationships are burned, and you find out when the replies start coming in angry.

Or you ask AI to share a project update with “the team,” and it includes someone who wasn’t supposed to see the budget numbers yet—or worse, someone who’s about to be affected by a decision that hasn’t been communicated. The AI didn’t have the context that a human would have known instinctively: not yet, not them.

These failures are tricky because the AI followed the instruction correctly. The problem is that the instruction didn’t include the social constraint, and the AI had no way to infer it. It can’t read the room, sense tension, or know that “the team” doesn’t mean everyone with that label in a system.

The fix isn’t to hope AI gets better at social inference—it’s to make the boundaries explicit before the agent acts. That means exclusion lists that are actually maintained, status flags that mean something (”do not contact,” “on leave,” “pending sensitive conversation”), and a system that surfaces uncertainty when it’s about to do something involving people. If the agent had paused and said “two of these contacts haven’t been messaged in 90+ days—should I check before reaching out?”—the damage never happens.

That’s the thread connecting all three failure modes: the AI commits before you can catch the misread. The fix is making interpretation visible and putting gates on the actions that can’t be undone.

---


## **WHAT THE FIX LOOKS LIKE**

Here’s the problem: you’ve never had to spell out exactly what you mean. When you ask a colleague to “share this update with the team,” you don’t hand them a list of who counts as “the team,” who shouldn’t see it yet, and what to leave out. You don’t have to. They know the context, they can read the room, and if they’re unsure, they ask.

AI doesn’t work that way. It takes your words, picks a reasonable interpretation, and executes. The context you didn’t say—because you’ve never had to—becomes the gap where things go wrong.

The fix is making that context explicit before the AI acts. Not in the form of longer prompts, but as a visible interpretation you can check: here’s what I think you’re asking for, here are the boundaries I’ll stay inside, here’s where I’m not sure. You look at it for five seconds, catch the misread, and correct it before anything happens.


### **What an intent doc looks like**

Think about “share this update with the team.” With a human, you’d just say that. With AI, the version that works looks more like this:

**Task:** Share the Q1 project update

**Who:** Marketing core team only (Jamie, Sam, Alex, Taylor). Not extended stakeholders, not exec sponsors—they get a separate version after Friday.

**What:** Summary and timeline. Exclude anything in draft, anything marked sensitive, and the budget section until it’s final.

**If uncertain:** Flag follow-up questions for me. Don’t answer on my behalf.

That’s it. This assumes you’ve already given the AI the relevant context—who’s on which list, what’s tagged as sensitive. The intent doc tells it how to apply that context for this specific task.

The point isn’t that you write this out every time. The point is that the AI should surface something like this back to you before it acts, so you can catch the misread before it becomes damage.


### **What a gate looks like in practice**

For actions that touch other people or can’t be undone, the AI should pause and show you what it understood—not just ask “are you sure?” but make the interpretation visible.

For the team update, that means seeing who’s about to receive it before it sends. If the exec sponsors are on the list and shouldn’t be, you catch it. If the budget section is attached and shouldn’t be, you catch it.

For a follow-up campaign, that means seeing which contacts are flagged—the one who asked to be left alone, the one who’s been dormant for six months, the one whose status says “on leave.” You’d spot the person you shouldn’t email before the email goes out.

The confirmation isn’t a speed bump. It’s the moment you see what the AI thinks you meant—before anything irreversible happens.


### **Deciding when to gate**

Not every action needs a checkpoint. The goal isn’t to slow everything down—it’s to catch the ones that can’t be undone.

A simple framework: think about what happens if the AI gets it wrong.

**Low-risk actions** — drafting a document, organizing files, summarizing something for your own review — don’t need gates. If the interpretation is off, you’ll see it and fix it. No damage done.

**Actions that touch other people or systems** — sending emails, posting messages, scheduling on someone else’s calendar, pushing changes to production — gate by default. A misread here affects someone besides you.

**Anything irreversible** — deleting without backup, spending money, external communications at scale — gate it, log it, no exceptions. If you can’t undo it easily, you see the interpretation before it executes.

That’s the whole policy. Drafts run free. Outbound actions get a checkpoint. Anything you can’t take back requires confirmation.


### **When something goes wrong, you need the receipts**

If your AI can act, you need an evidence trail for when it’s wrong. Not for compliance theater—for figuring out what happened and fixing it.

A good audit trail should let you answer:

- What the user asked
- What the system thought that meant (the interpretation it chose)
- What it actually did
- What it touched (people, files, systems)
- What it chose *not* to do (exclusions, guardrails that fired)
- What it was uncertain about, and how that got resolved
- Who approved it (if gated) and when

So when someone asks “why did 200 customers get that email?”—you don’t have to guess. The log shows you said “follow up with everyone who hasn’t replied,” the system included the do-not-contact list, and no gate fired because the threshold was set too high.

Most failures aren’t mysterious. Someone meant one thing, the system inferred another, and then it committed. If you log the interpretation next to the action, you don’t have to argue about what happened—you can see it.

---


## **A quick gut check**

If you’re using AI that can take actions—not just draft things for you to review—these questions will tell you whether you’re running with guardrails or without.

**Can your agents show you what they think you mean?**

Not their plan—their interpretation of the objective. If you asked “what do you think I want?” right before execution, would the agent have an answer? If not, you only learn what it understood after it’s already acted.

**Where are your gates?**

Think about the most dangerous things your AI can do. For each one: is there a checkpoint? Does it pause and show you its interpretation before executing? If the answer is “no” or “it depends on the prompt,” that’s where you’re relying on luck.

**If something went wrong tomorrow, would you have receipts?**

Could you reconstruct what happened? Not just what action the AI took—what it thought you meant, what it excluded, what it flagged as uncertain. If you can’t answer that, you’re debugging blind.

---


## **The bottom line**

Models will improve. That will help. But the gap is structural: intent lives in the user’s head, not fully in the user’s words.

The architecture isn’t a bandaid for weak models. It’s a recognition that interpretation might be wrong, and some mistakes are more expensive than others.

The through-line is simple: make the AI show you what it thinks you mean before it does anything that matters. If you can see the interpretation, you can catch the misread. If you can’t, you’re hoping it guessed right.

If your agent can’t do that, you don’t have an agent. You have a slot machine with API access.

[![](https://substackcdn.com/image/fetch/$s_!G9Fb!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd268f6fc-9f6e-407c-b7b3-9e276d8304d9_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!G9Fb!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd268f6fc-9f6e-407c-b7b3-9e276d8304d9_1024x1024.png)
