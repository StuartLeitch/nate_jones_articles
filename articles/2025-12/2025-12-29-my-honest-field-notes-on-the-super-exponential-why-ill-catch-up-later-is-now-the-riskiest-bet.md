---
title: "My honest field notes on the super-exponential + why \"I'll catch up later\" is now the riskiest bet"
author: "Nate Jones"
published: 2025-12-29
url: https://natesnewsletter.substack.com/p/my-honest-field-notes-on-working
subtitle: "Watch now | Yes, I'm the person who spends 20 minutes writing specs before delegating a 2-hour tasks. This piece gets at why that 20 minutes is worth it."
audience: everyone
scraped_at: 2026-01-05 19:08:46
---

While everyone was arguing about confidence intervals, they missed the point.

METR published their latest benchmark results showing Claude Opus 4.5 completing tasks at 50% success that would take a human nearly five hours. The discourse immediately split into camps. One group declared the future had arrived. Another pointed to the wide error bars and dismissed it as noise. Both camps were staring at a snapshot and arguing about pixels when they should have been watching the movie.

The story isn’t the point estimate. The story is the trajectory. The 50% horizon has been doubling roughly every seven months since 2019. In 2019, it was measured in seconds. By 2021, it had grown to minutes. By 2023, it reached tens of minutes. Now we’re measuring in hours. And the doubling period itself appears to be compressing—what was seven months historically looks closer to four months in recent data.

When your doubling time is shrinking, you’re not on an exponential curve. You’re on something steeper, a super-exponential where the rate of change is itself changing. Our brains are not built to process curves like this. We see “five hours” and it doesn’t feel urgent—a long meeting, a flight to Chicago, nothing that demands immediate action. But the curve doesn’t care what feels urgent.

If that pace holds—and I want to be careful here, because the confidence intervals are wide—the horizon reaches ten hours by spring, twenty by summer, and approaches a full work week by fall. Whether the exact numbers land precisely there matters less than the direction and the acceleration. The question worth asking isn’t whether you can delegate a five-hour task right now. The question is what happens to work, and to the people who do it, when the kinds of things that become delegatable keep expanding at this pace.

Here’s what we’re covering:

- **Why both camps are wrong**—the hype crowd and the dismissive crowd are each looking at a data point when they should be watching a curve
- **What METR actually measures**—and why time horizons reveal dynamics that accuracy benchmarks systematically hide
- **The 50%/80% gap**—the difference between what’s possible and what’s dependable, and what it means to operate in the space between them
- **How scope changes over time**—the kinds of work that become delegatable at ten hours, twenty hours, and forty hours, and why this matters more than any single benchmark result
- **Knowing what correct looks like**—the skill that’s quietly becoming the most valuable thing you can develop
- **The recursive loop**—how AI systems training AI systems bends the curve in ways that historical extrapolation might not capture
- **What this means for how we work**—not prescriptions, but observations about what seems to be changing and what that might require of us


## **[Grab the prompts](https://www.notion.so/product-templates/The-Delegation-Toolkit-2d55a2ccb5268058be19d76fd9758824?source=copy_link)**

This is a delegation toolkit built for the 50%/80% reality—agents that can attempt multi-hour tasks but need verification systems to catch the failures that look like successes. You’re getting seven prompts: a core delegation framework, specialized versions for research, document creation, code, and process execution, plus a verification prompt to run on any output before you trust it, and a spec-writing assistant for when you’re not sure what you need to specify. These are designed to be structured thinking tools—scaffolding that forces you to answer the questions that determine whether delegation produces leverage or liability.


## **The shrug is the bug**

The reaction to the METR results has split into two camps, and both have gotten it wrong in ways that matter.

The first camp is the hype crowd. They read “50% success at five hours” and hear that we can now delegate five hours of work to an agent. But that’s not what the data says. Fifty percent success means a coin flip—half the time, you get output with errors you can’t afford to ship. Some of those errors will be obvious, cases where the agent got stuck or went in circles. But many will be subtle. The output will look professional and complete. It will have the right structure and the right citations. And somewhere inside it, something will be wrong in a way you won’t notice until it causes problems downstream. The 80% reliability horizon, where you can actually depend on the output without extensive verification, sits at around 27 minutes for Opus 4.5. The gap between what’s possible and what’s dependable remains enormous.

The second camp is the dismissive crowd, and their take sounds more sophisticated but is equally mistaken. They point to METR’s confidence intervals, which run from 1 hour 49 minutes to 20 hours 25 minutes at 95% confidence. That’s an enormous range, almost twenty hours of uncertainty, and they use it to wave the whole thing away. The methodology is too noisy. The data is too sparse. Wake me when there’s something real to talk about.

METR has been transparent about why the intervals are so wide. Their task suite was designed when the horizon was measured in minutes, so they have plenty of tasks in the five-to-thirty minute range but relatively few beyond one hour and very few beyond four hours. Until recently, no agent could complete tasks that long, so there was no reason to build them. When you’re estimating performance at durations where you only have a handful of data points, your confidence intervals balloon. That’s just how statistics works.

But focusing on the uncertainty of this specific point estimate completely misses the larger pattern. We went from seconds to minutes to hours in a consistent progression across years. The direction is unambiguous. The pace appears to be accelerating rather than slowing. Even if you take the most conservative interpretation and assume the true horizon is closer to two or three hours than five, that still represents a massive jump from where we were twelve months ago. And if doubling continues at anything like the historical rate, the next twelve months will see another jump of similar magnitude.

The uncertainty cuts both ways. The curve might slow down, but it might also be moving faster than the point estimate suggests. Neither camp is reckoning with what the trajectory implies.

**Why time horizons reveal what other benchmarks hide**

Most AI benchmarks work by defining a fixed set of tasks and measuring what percentage of them a model can complete. SWE-bench asks what fraction of software engineering problems a model can solve. MMLU asks what fraction of questions a model can answer correctly. These are useful measurements, but they share a structural limitation: they have ceilings. The ceiling is 100%, and you cannot score higher than perfect.

We’re already bumping against these ceilings. Frontier models score in the mid-80s on SWE-bench and are saturating MMLU. When a model improves from 81% to 83%, what does that actually tell you about how its real-world capabilities have changed? Very little. You can’t tell whether it’s dramatically better at the hardest problems or marginally better at medium ones. The benchmark has compressed the signal into a narrow band where meaningful differences become invisible.

METR’s time-horizon approach sidesteps this problem entirely. Instead of asking what percentage of a fixed task set AI can complete, they ask a different question: how long can a task take a human professional and still be completed by an AI agent at a given success rate? The unit of measurement shifts from percentage points to hours.

Time has no ceiling. A task can take one minute or one hour or one day or one week. When you measure against time instead of accuracy, you stretch the measurement axis infinitely, and that lets you see dynamics that accuracy benchmarks hide. What you see, when you look at METR’s data across years, is acceleration—not just progress, but progress that appears to be speeding up.


## **The space between possible and dependable**

There’s a number buried in METR’s data that deserves more attention than it’s getting: the 80% horizon.

At 50% success, Opus 4.5 can handle tasks that take humans roughly five hours. But at 80% success, where you can actually depend on the output without extensive verification, the horizon drops to around 27 minutes. That gap—hours of possibility on one side, minutes of dependability on the other—defines the operating reality for anyone trying to get real work done with these systems today.

Other research has found similar patterns. Stanford’s AI Index 2025 used RE-Bench, a different evaluation framework focused on research engineering tasks, and found that at two-hour time budgets, top AI systems scored roughly four times higher than human experts. But at 32-hour budgets, humans outperformed the AI systems by about two to one. The systems excel at concentrated bursts of focused work but struggle as duration extends and complexity compounds.

This matches what anyone actually working with agents knows intuitively. If you give an agent a focused task with clear parameters—a specific coding problem, a well-defined research question, a structured analysis—it can often deliver faster and at higher quality than you could produce yourself in the same time. But if you give it a complex project with ambiguous requirements and multiple judgment calls spread across many hours, you’re gambling. The system might produce something excellent. It might also produce something that looks excellent but contains errors you won’t catch until they’ve caused damage.

The work right now involves learning to operate in the space between possible and dependable, delegating tasks that are long enough for the leverage to matter but short enough that you can verify the output before errors compound into problems.


## **How scope changes as the horizon extends**

The question that matters isn’t what you can delegate today at five hours. It’s how the kinds of work that become delegatable change as the horizon extends to ten hours, twenty hours, and beyond.

At five hours, you’re delegating tasks—discrete pieces of work with clear boundaries. Research this topic and summarize what you find. Draft a document on this subject. Analyze this data set and identify the patterns. The work fits in a single sustained session. Success criteria can be specified in advance. Output can be verified against the specification.

At ten hours, the nature of the work starts to shift. You’re no longer delegating tasks but something closer to projects—complete deliverables that require planning, multiple phases, and synthesis across different activities. A comprehensive competitive analysis that covers an entire market landscape. A working prototype of a feature including documentation. A full technical specification for a product. The work has internal structure. It requires the agent to make sequencing decisions, to notice when early assumptions need revision, to maintain coherence across a longer arc.

At twenty hours, you’re delegating initiatives. Strategic plans. Complete first drafts of substantial documents like grant proposals or white papers. Full redesigns of business processes including implementation recommendations. The work spans what would be multiple work sessions for a human. It requires not just execution but judgment about what to prioritize and when to stop.

At forty hours—roughly one full work week—the scope expands further still. Complete business plans for new ventures. Comprehensive audits of organizational structure. First drafts of book-length material. End-to-end product development cycles from specification through prototype through documentation. Work at this horizon involves so many dependencies and decision points that the distinction between delegating work and delegating judgment starts to blur.

The point isn’t to forecast exactly when each of these horizons becomes possible. The point is that each expansion opens entirely new categories of work to delegation. A five-hour task is not simply a forty-hour task done for less time—it’s a fundamentally different kind of work with different requirements for specification, verification, and oversight. The skills required to delegate effectively at each level are different, and they build on each other. Someone who has spent months learning to delegate five-hour tasks well will have intuition that transfers when the horizon extends. Someone who waits until forty-hour delegation is possible will be starting from scratch on a much steeper slope.


## **Knowing what correct looks like**

Here is the skill that’s quietly becoming the most valuable thing you can develop: the ability to recognize when output is right and when it’s wrong, even when the wrong output looks entirely professional.

When a language model hallucinates in a text generation context, it produces false statements. The damage is limited to the credibility of the text. But when an agent hallucinates in an operational context, it takes false action. It might submit incorrect information, make commitments that can’t be kept, or produce deliverables built on foundations that don’t hold. The errors are no longer contained in language—they propagate into the world.

The dangerous failure mode isn’t the obvious one where the agent gets stuck or produces gibberish. The dangerous failure mode is the output that looks right. The competitive analysis with a clean table of data, proper formatting, and citations that appear legitimate—except two of the prices come from cached pages that are eighteen months out of date. The contract review that flags the standard risks but misses the clause that creates liability in this specific jurisdiction. The research synthesis that correctly summarizes nine sources and subtly mischaracterizes the tenth in a way that changes the conclusion.

At 50% reliability, some version of this failure mode shows up in half your runs. The question is whether you can catch it.

This is where domain expertise transforms from a nice-to-have into a genuine control surface. If you understand your field deeply—not at the level of surface familiarity but at the level where you know what wrong looks like before you can articulate why—you can direct agents toward useful work and catch their errors before those errors ship. If you don’t have that depth, you’re operating the system but not controlling it.

Consider the difference between a junior analyst and a senior litigator both using an agent to review a contract. Both can write the prompt. Both can receive the output. Only the litigator knows which clauses are load-bearing in which jurisdictions. Only the litigator recognizes when boilerplate language interacts with other terms to create unintended consequences. Only the litigator can verify the output against decades of pattern recognition about what contracts like this usually do and don’t contain. The analyst can use the tool. The litigator can trust their own judgment about when to trust the tool’s output.

That difference becomes existential when something goes wrong. And at 50% reliability on multi-hour tasks, something will go wrong regularly.


## **The recursive loop**

There is a dynamic in current AI development that makes extrapolation from historical data complicated, and it’s worth being direct about both what we know and what remains uncertain.

AI systems are increasingly involved in their own development. Anthropic’s Constitutional AI process, which is documented in published research going back to 2022, uses AI-generated feedback to train models. In their RLAIF approach—reinforcement learning from AI feedback—models evaluate which responses better follow specified principles, generating preference data that feeds into training the next iteration. The model critiques and revises its own outputs, and that data improves subsequent versions.

This pattern has spread across the major labs. AI systems now participate in data curation, synthetic data generation, evaluation, and training optimization. Each generation of improvements makes aspects of the next generation easier to achieve. The process that produces capability gains is itself gaining capability.

This doesn’t mean the curve will continue forever at the current rate. There may be barriers we haven’t encountered yet. The improvements might slow as the systems approach limits we can’t currently see. But it does mean that using pre-2024 trends to predict what happens in 2026 requires caution. The training process itself has changed in ways that might make historical extrapolation either too conservative or too aggressive—and we won’t know which until we see what happens.

What seems clear is that 2025 was the year the infrastructure for agentic work got built. The tooling exists. The orchestration frameworks have matured. The integrations are live. The people who spent this year building workflows and developing intuition for failure modes have a foundation. The people who watched from the sidelines and planned to catch up later are starting from zero exactly as the capability jumps accelerate.


## **What this means for how we work**

There is grief in this transition for some people, and it would be dishonest to pretend otherwise. Not everyone’s expertise will become more valuable when combined with AI fluency. Some skills that took years to develop will matter less as agents become capable of executing the underlying tasks. Career trajectories that made sense under previous assumptions may need revision. This is genuinely hard, and acknowledging it matters.

At the same time, the evidence suggests that domain expertise isn’t being replaced wholesale—it’s being transformed into something different. The litigator who understands contract law deeply will have more leverage than ever, because they can direct agents toward useful work and catch errors that a less experienced person would miss. The engineer who knows a codebase intimately can verify agent output in ways that someone loading context for the first time cannot. The skill of knowing what correct looks like becomes the control surface that determines whether delegation produces leverage or liability.

The research on professional networks suggests something similar about how opportunity works in times of transition. The LinkedIn study tracking twenty million users over five years found that moderately weak ties—professional acquaintances rather than close friends—were the most effective path to new jobs, particularly in digital industries. The people three connections out from you see information that hasn’t yet reached your immediate circle. Expanding your surface area for opportunity means building those connections, making your work visible, and being someone whose capabilities are known to more than just your immediate team.

What seems to matter most right now is developing the skills that compound as the horizon extends. Specification—learning to define tasks precisely enough that agents can execute without constant guidance. Verification—building the ability to check output efficiently and catch the failures that don’t announce themselves. Intervention—recognizing when a run is going sideways before it wastes hours or produces work that will need to be redone.

These skills don’t become obsolete as agents grow more capable. They become more valuable, because each jump in capability raises the stakes on each delegation. The gap between someone who can effectively delegate a week’s worth of work and someone who cannot will be enormous. And the intuition required to operate at that level can only be built through practice at the levels that come before.

The curve isn’t waiting for planning cycles or organizational readiness assessments. It isn’t waiting for the tools to mature or the best practices to be established. The people who figure out how to work with agents effectively won’t just be more productive than those who don’t—they’ll be operating in a fundamentally different mode, with fundamentally different leverage over their work and their time.

Whether you participate in that transition or not, the 40-hour work week is getting rewritten. The only question is whether you’re developing the skills to be holding the pen.

[![](https://substackcdn.com/image/fetch/$s_!rWIo!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fad71b850-bc5d-456d-937b-5a7877690f4f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!rWIo!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fad71b850-bc5d-456d-937b-5a7877690f4f_1024x1024.png)
