---
title: "My honest field notes on the verification gap no one's talking about, plus the complete guide + prompt kit that makes agent loops actually converge"
author: "Nate Jones"
published: 2026-01-07
url: https://natesnewsletter.substack.com/p/my-honest-field-notes-on-the-verification
subtitle: "Watch now | A Claude Code plugin called Ralph Wiggum has been making the rounds in developer circles—named after the Simpsons kid who announces “I’m helping!” while contributing nothing useful."
audience: everyone
scraped_at: 2026-01-07 12:00:17
---

A Claude Code plugin called Ralph Wiggum has been making the rounds in developer circles—named after the Simpsons kid who announces “I’m helping!” while contributing nothing useful.

[![](https://substackcdn.com/image/fetch/$s_!fbF3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4584671e-8a37-4053-92a9-90bc9a1848cd_1826x1150.png)](https://substackcdn.com/image/fetch/$s_!fbF3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4584671e-8a37-4053-92a9-90bc9a1848cd_1826x1150.png)

The plugin does one thing: when the AI says it’s done, Ralph says “not yet” and makes it keep going.

We’ve spent years asking whether AI models are smart enough to do the work. We should have been asking a different question: who decides when the work is actually finished? And by what evidence?

The scene keeps playing out the same way. Someone gives an agent a real task—migrate a test suite, refactor a module, generate a report. The agent works, writing files and narrating its progress, printing a confident summary. Then it stops. The human checks, and the tests are red. Or the report is missing a section. Or worse: the agent never verified anything, but it sounded like it did.

The failure isn’t intelligence. It’s that nobody had standing to say “not yet.” We’ve been treating “done” as a conversational cue when it should be a contract. The next model won’t fix this, because “done” isn’t a capability problem—it’s an accountability problem. For most of AI’s recent history, accountability has defaulted to the model itself. Ralph inverts that.

The frame that makes this click: **in agent land, the wrapper is the product.** Model choice matters—but once you’re running agents on real tasks, most of the outcome delta comes from what happens when the model tries to stop. The checks, the loop, the verification layer—that’s where reliability lives. Teams buying better models while ignoring their harness are optimizing the wrong variable.

**What’s inside:**

- The metric that matters now: not first-pass success, but convergence
- What changes when agents move from drafting to doing (and why 2026 is the year it breaks)
- Where this shows up outside engineering—and why most teams will misapply it
- Where it fails—and the organizational collisions most teams haven’t seen coming
- The skill that’s becoming scarce: turning taste into checkable constraints


## **[Grab the Kit](https://www.notion.so/product-templates/Done-Definition-Kit-2e15a2ccb526800d87f3dca831e93cce?source=copy_link)**

The pattern is simple; the execution isn’t. Most teams try to define “done” once, discover their gates are either too vague to check or too rigid to survive contact with real work, and quietly go back to vibes-based review. The Done Definition Kit gives you the translation layer: a diagnostic that catches uncheckable requirements before you waste iterations on them, a prompt that forces gate tables with evidence fields and “not yet” examples, and worked templates for the three workflows where this pattern pays off fastest—competitive reviews, postmortems, and executive summaries. Each one is structured to prevent the specific failure modes covered above: adjective-gates that grind without converging, missing evidence fields that let agents self-certify, and judgment calls disguised as constraints. These aren’t generic templates—they’re the result of running the pattern until we found where it breaks.


## **What Ralph Does (And Why It Matters)**

Ralph is a stop-hook: a wrapper that intercepts Claude’s attempt to exit and refuses to let it. When the agent tries to declare victory, Ralph feeds the original prompt back in along with the current state of the work. The agent sees its modified files, the history of what it tried, and the original goal. It keeps working.

One common stop condition is a completion-promise string—the agent has to say a specific phrase to exit. This is gameable. The pattern works best when you pair it with external verification: tests, linters, validation scripts that the agent runs as part of its workflow. Ralph keeps the agent in the loop; the external checks tell you whether the work is actually done.

That’s the architecture—no special model, no secret prompt, just a refusal to accept self-reported completion as truth.

Three things change because of this:

**First, it reveals that “done” is gameable.** The plugin prompt includes language like “do not lie even if you think you should exit” and “do not force the end of the process by lying about the doneness.” This isn’t paranoia. It’s addressing what happens when stopping is tied to any model-generated signal: the model optimizes for producing that signal.

**Second, it makes checks the steering wheel.** Instead of running tests after the work is supposedly finished, the checks become what drives the work. The agent keeps colliding with reality—tests, linters, validation rules—until reality stops objecting.

Take a concrete example: you ask Claude to migrate a test file from one framework to another, with instructions to run the tests before declaring done. First pass: Claude rewrites the tests, runs them, sees failures, but announces “Migration complete” anyway and tries to exit. Ralph prevents the exit and loops the context back. Claude sees “Expected 3, got undefined” in its own output and realizes it missed an import. Second pass: fixes the import, runs tests again, tries to exit. Tests still fail—Ralph loops it back. Third pass: Claude traces the issue to a changed assertion syntax. Fourth pass: tests green, exit allowed. Without the loop, you’d have gotten “Migration complete” and a broken test file. With the loop, you got working tests and a record of what it took to get there.

**Third, it turns retries into a reliability budget.** Retries aren’t free, but they often turn “usually works” into “reliable enough”—as long as the checks are real. If your check is wrong, you’ll loop confidently in the wrong direction. But if your check is solid, iteration becomes a resource you can allocate, not just a sign that something went wrong.


## **The Metric Flip**

Once you accept that first-pass output isn’t the point, what you measure changes.

The traditional AI evaluation: one shot, one grade, move on. Give it a task, score the result, report the number. That made sense when AI produced drafts for humans to review. It makes less sense when agents are doing multi-step work autonomously.

The question stops being “can it do it?” and becomes “does it converge?”

A better metric: how many iterations to a genuinely correct state? What does that cost? What’s the failure rate when it never gets there?

This reframes quality as something you can budget for. Some tasks are worth five retries. Some are worth fifty. Some aren’t worth automating at all because verification costs more than doing the work yourself.

But here’s the critical constraint, and it’s the hinge of the whole pattern: **iteration only buys correctness if “correct” is something you can actually check.**

If your definition of done is binary and verifiable, loops are powerful. If your definition is vague—”make it professional,” “make it good”—loops just grind. They produce activity without convergence because there’s nothing concrete to converge toward.

Ralph fails on vagueness and succeeds on specification—not as a limitation of the tool, but as the thing that makes it work.


## **Why 2026 Specifically**

Every year brings better models. So why does this pattern matter now?

Because we finally made output cheap, but we didn’t make verification cheap. For a growing range of tasks, the model can do the work—the bottleneck is whether we can confirm it’s correct before it causes damage.

**Agents are moving from drafts to actions.** The worst case used to be rewriting something. Now agents are modifying files, opening tickets, sending messages, making changes that trigger other changes. When actions compound, “pretty good on first pass” stops being acceptable. A wrong file edit that gets committed and built on becomes expensive to unwind. A wrong message sent can’t be unsent.

**Volume is exploding, but review isn’t.** More agents doing more work means more output to verify. If your only verification method is “a human reviews everything,” you’ve created a bottleneck that grows exactly as fast as your AI adoption—which means it doesn’t scale at all.

**Delegation is outpacing oversight.** One person can now run ten parallel workstreams through agents. The work gets done. But who’s checking it? When one human is reviewing the output of many agents, review has to be cheap, fast, and specific. That means encoding “right” as concrete, verifiable criteria—not vibes, not “looks good to me.”

Most teams are treating agents like interns: throw tasks over the wall, then hope the summary is honest. That worked when the intern was drafting a memo. It doesn’t work when the intern is modifying your codebase or sending emails to customers.


## **Beyond Code**

Everything so far has been about software, where Ralph originated. Software has an unusual property: correctness is often machine-checkable. Tests pass or fail, code compiles or doesn’t, and you can keep running the agent into these checks until nothing objects.

Most knowledge work doesn’t have this property. When you’re building a competitive analysis or writing a summary, there’s no compiler. Judgment calls are made by humans, and those judgments involve taste, context, and priorities that resist formalization.

But “resist” isn’t “impossible.” More of knowledge work can be specified than most people assume. Not everything—but enough to change how the work gets done.

**Consider a monthly competitive review.** Someone tracks what competitors are doing, synthesizes the changes, produces a document that leadership is supposed to use. This work gets done, but it’s almost always inconsistent. One month it’s thorough, the next it’s a few bullet points. Sources are sometimes linked, sometimes not. The “so what” is missing, or buried, or vague enough to be useless. Leaders complain that they can’t trust it, that it doesn’t help them decide anything, that they still have to do their own digging after reading it.

The typical inputs are scattered: press releases, product update pages, LinkedIn posts from competitor execs, analyst reports, sales team anecdotes. The typical failure mode is that whoever’s assembling it grabs whatever’s easy, writes something that sounds complete, and moves on. There’s no forcing function that says “you missed Competitor C entirely” or “you claimed they raised prices but didn’t link to where you saw that.”

A Ralph-like pattern starts by defining what “done” means in checkable terms. Each competitor change must include a source. Each change must answer “why this matters to us” and “what we do about it.” Confidence must be flagged based on source quality.

None of these are subjective—they’re either present or not, which means an agent can iterate against these gates until the document satisfies all of them.

The human reviewer’s job shifts. Instead of checking whether basic things are present—did they cover all competitors? are there sources?—they focus on judgment. Is the “why it matters” actually right? Is the recommended response smart? Is something important being missed that the checks wouldn’t catch?

The machine enforces the floor while the human moves to the ceiling. Review time drops because you’re not catching obvious gaps, and consistency rises because the gaps aren’t there to catch.

**Executive summaries are simpler.** One page maximum, clear recommendation, why not the alternatives, no hedging language. What’s left for the human is whether the recommendation is actually correct.

**Incident postmortems show what happens when the stakes are higher.** These are supposed to prevent the same failure from happening twice, but they’re often written to close the ticket, not to surface the real cause. The template asks for root cause, but people write “human error” and move on. It asks for action items, but people list vague intentions that never get tracked.

A checkable version requires the root cause to name a system or process failure, not a person. It requires each action item to have an owner and a date. It requires the timeline to include specific timestamps, not “around 3pm.”

Here’s what the loop looks like: Agent drafts the postmortem, writes “root cause: engineer failed to check staging.” Check rejects—root cause can’t name a person. Agent revises: “root cause: deployment pipeline lacks staging verification step.” Check passes that gate, but rejects the action item: “improve process” has no owner or date. Agent revises: “Action: add staging check to CI pipeline. Owner: Platform team. Due: March 15.” Check passes. Human reviews: is this actually the root cause? Is the fix sized right? The agent did the structure; the human does the judgment.

The check catches the postmortem that says “we’ll be more careful next time”—which isn’t a fix, it’s a hope.

**The same evidence discipline applies to hiring and finance.** Interview feedback is notoriously useless: “seemed smart,” “good communication,” “not sure about culture fit.” These are vibes dressed as evaluation. Hiring committees end up debating impressions instead of evidence, and the loudest voice wins. A checkable version requires every rating to cite a specific quote or example—no adjectives without proof.

Budget and KPI reporting works the same way: numbers must reconcile to source data, variances must include explanations, anomalies must be flagged. The reviewer stops checking arithmetic and starts asking whether the story makes sense.

Separate what can be verified from what requires judgment. Let machines enforce the verifiable parts. Concentrate human attention on the parts that actually need it.


## **Where This Breaks**

The pattern has real limits. Knowing them matters more than the pattern itself.

**False green.** You can pass every check and still be wrong. A competitive review might cite sources, explain significance, and flag confidence—and still miss the most important thing happening in the market. Checks verify presence and format; they don’t verify insight. This is fine as long as you remember that the floor isn’t the ceiling. It becomes a problem when passing checks creates false confidence that the work is actually good.

**Gaming the checks.** Once “passing” becomes the goal, you get Goodhart problems. An agent optimizing to satisfy constraints will find ways to satisfy them that don’t serve the underlying purpose. Hiring scorecards that require quotes will get quotes—but maybe not the quotes that reveal what you actually need to know. The checks need to be designed with adversarial pressure in mind: how would a system that wanted to pass without doing the real work try to game this?

**Infinite grind.** Some tasks don’t converge. The definition of done is too vague, or the task is genuinely beyond current capability, or there’s a bug in the verification that can never be satisfied. Without a clear iteration budget and failure handling, you just burn resources. This is why Ralph includes a maximum iteration limit—not as a safety net, but as an essential part of the pattern.

**Budget discipline.** Retries cost money and time. “Keep going until it’s right” sounds good until you’re paying for fifty iterations on a low-stakes task. The decision of how much correctness to buy becomes a managerial decision, not a technical one. Different work deserves different retry budgets, and someone has to make those calls.

**Judgment-heavy work.** Some tasks are mostly judgment. There’s no floor to enforce because the whole thing is ceiling. Strategic positioning, creative direction, stakeholder navigation—these don’t decompose into checkable components, or at least not in ways that capture what matters. The pattern works best on work that’s a mix of routine and judgment. Pure judgment work still needs humans end-to-end.

**Drift.** The checks reflect last quarter’s standards. The work changes, the checks don’t. You end up enforcing yesterday’s definition of good while the actual requirements have moved. Checks aren’t set-and-forget; they need maintenance the same way any governance system does.

None of these are reasons to abandon the pattern. They’re reasons to understand what you’re actually building. The loop is only as good as the judge. If you’re serious about this, judge quality becomes the bottleneck—and eventually, the moat.


## **Who Owns “Done”?**

Most teams haven’t faced this yet, but they will.

When you encode “done” as checks, you’re freezing tradeoffs that used to be handled by human judgment in the moment. A brand consistency check blocks a fast turnaround because someone used a non-standard font—who has override authority? A competitive review requires “what we do about it” for every change—who decides when “do nothing” is acceptable? KPI reporting flags anomalies above a threshold—who sets it, who gets paged, who’s responsible when it’s wrong?

These collisions happen the moment implicit judgment becomes explicit rules. An agent doesn’t navigate tensions. It executes whatever definition of done it was given. So: whose definition wins?

When you encode “done,” you create a constitution. It decides what gets blocked, who gets paged, what counts as acceptable risk, where exceptions live, and who gets blamed when the system did exactly what it was told.

If you think this is a tooling detail, watch what happens the first time the system refuses to ship something sales needs, or ships something legal considers indefensible. Those aren’t bugs. They’re the rules you wrote down, enforced without judgment. The teams that survive this will be the ones that had the governance conversation before they needed it.


## **The Spec Skill**

If this pattern spreads, the valuable skill changes.

Most people don’t have standards. They have preferences they enforce inconsistently. They know good work when they see it, they have taste, but taste that lives only in your head can’t drive a loop.

The scarce skill becomes specifying work precisely enough that a system can check it. That means learning a few distinctions most people haven’t practiced:

**Constraints versus preferences.** A constraint is what must be true: “must include a recommendation,” “must cite sources,” “must not exceed one page.” A preference is what you’d like: “should be compelling,” “should feel professional.” Constraints can be checked, but preferences can’t—and if you can’t turn a preference into a constraint, you have to evaluate it yourself.

**Proof versus confidence.** Proof is checkable: the source link exists, the number reconciles, the quote is in the transcript. Confidence is not: “I believe this is correct,” “this seems right.” An iteration loop can verify proof, but it can’t verify confidence—which means work that requires confidence requires human review at that stage.

**Repeatable versus situational.** Some standards are always true: summaries under one page, claims with citations. Others depend on context: what counts as “material” varies by situation. Repeatable standards can be built into checks; situational standards need human judgment each time.

Before: “Write an executive summary of the Q3 results.” Too vague for a loop—an agent will produce something that sounds like a summary, and you’ll have to read the whole thing to know if it’s useful.

After: “Write an executive summary of Q3 results. Requirements: one page maximum, must state the primary recommendation, must explain why not the two most obvious alternatives, no hedging language, all figures must cite the source slide or table.” Now the agent iterates against concrete gates. You review whether the recommendation is right—not whether the summary hit the page limit.

The before version requires you to be present for all of it. The after version requires you to be present for the parts that need you.

This skill—translating taste into specification—used to be niche, something that lived in test-driven development, in contract design, in quality assurance frameworks. It’s becoming general-purpose, and the people who develop it early will have a significant advantage.


## **The Closing Challenge**

A Simpsons character plugin shouldn’t carry this much weight. And in a sense, it won’t for long—Ralph will be superseded by better interfaces and smoother tooling. The specific implementation is temporary.

But the thesis underneath it is durable: the era of taking the AI’s word for it is ending. Not because models are untrustworthy in some moral sense, but because self-reported completion is structurally unreliable.

If your org is buying agent capacity without buying verification capacity, you’re scaling your ability to produce mistakes. That’s not a technical failure. It’s a leadership failure. Someone has to own the definition of done. Someone has to fund the checks. Someone has to be accountable when the system does exactly what it was told and the outcome is still wrong.

The test: what work do you repeat that you still can’t define well enough to delegate? Not “I could explain it to a smart person”—define it in terms that could be checked without you present. What would the checks be? What would “passing” look like?

If you can answer that, you don’t have to wait for better models. You can make the current ones dramatically more useful. If you can’t, the work stays with you—not because AI isn’t capable, but because you haven’t specified the target clearly enough for capability to matter.

Either you can name what would make you say “not yet,” or you’re going to keep discovering “not yet” after it’s already shipped.

[![](https://substackcdn.com/image/fetch/$s_!s8gf!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe96ed07f-2c5f-45aa-a861-8ffb73048479_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!s8gf!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe96ed07f-2c5f-45aa-a861-8ffb73048479_1024x1024.png)
