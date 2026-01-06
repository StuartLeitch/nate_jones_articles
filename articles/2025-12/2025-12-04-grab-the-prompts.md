---
title: "Grab the Prompts"
author: "Nate Jones"
published: 2025-12-04
url: https://natesnewsletter.substack.com/p/why-your-ai-agents-keep-failing-and
audience: everyone
scraped_at: 2026-01-05 19:10:37
---

*I’ve been watching teams burn months trying to automate their most important workflows. Smart engineers. Good models. Ambitious roadmaps.*

*And then three months in: stalled agents, bloated scope, frustrated leadership, and humans who’ve completely checked out.*

*Meanwhile, down the hall, another team automated three “boring” tasks and freed up 30% of their week.*

*The difference isn’t talent or technology. It’s where they started.*

*The teams that win don’t start with the core of the workflow—the part that requires deep expertise and judgment. They start with the edges: data preparation, QA, synthesis, handoffs, packaging. The mechanical stuff that surrounds the valuable work.*

*This is obvious in hindsight, but almost nobody does it. Because the edges feel like the boring parts. The stuff you do before and after the “real work.”*

*That framing is the trap.*

*Here’s what’s in this post:*

- ***The edge-first framework** — What “edge” actually means, why core-first automation fails, and how to identify the five edge categories in any workflow you touch*
- ***The trust problem nobody mentions** — Why AI automation is an organizational trust exercise, not a technical project, and how attacking edges first earns you the right to eventually touch the core*
- ***Field notes by role** — What edge-first automation looks like for PMs, engineering leads, sales, customer success, and ops—including the common traps each role falls into and where to start*
- ***Eleven companion prompts** — A full prompt manual that turns an LLM into a genuine thinking partner. These aren’t checklists; they give the model enough context on edge-first automation to reason alongside you. Including:*

  - *The Workflow Compass — Map a messy workflow and find the edges. For anyone staring at a process they don’t fully understand yet.*
  - *Edge Discovery Through Human Friction — Surface edges through where time and energy disappear. For teams who know something’s wrong but can’t name it.*
  - *The Fast-Win Filter — Pick which edge to automate first. For when you have multiple candidates and need to prioritize.*
  - *Design a Semi-Manual Version-0 — Build something shippable in days, not months. For avoiding the agent moonshot trap.*
  - *Extract Tribal Knowledge Safely — Get people to share the unwritten rules. For when you need insider knowledge without triggering defensiveness.*
  - *Communicate Edge Automation Without Threatening People — Tell your team what’s happening. For leaders who need buy-in, not fear.*
  - *Edge Stacking ROI Projection — Model the compounding value of multiple edges. For building the case for continued investment.*
  - *Am I Ready to Approach the Core? — Honest readiness assessment. For when you’re tempted to move inward and need a sanity check.*
  - *Diagnose Why My Last Agent Project Failed — Postmortem framework. For anyone whose automation stalled and wants to understand why.*
  - *Build an Edge Automation Portfolio — Find opportunities across adjacent teams. For scaling beyond your own workflow.*
  - *The One-Prompt Guided Journey — End-to-end walkthrough in a single conversation. For people who want the whole experience without switching prompts.*
- ***The path inward** — How edge automation positions you to eventually automate the core, and how to know when you’re actually ready*

*This is field notes from what I’m actually seeing, not theory. No vapor statistics, no Gartner citations—just the pattern that separates teams that ship from teams that stall.*

*If you’ve had an automation project fail, or you’re about to start one and want to avoid the obvious mistakes, this framework will save you months. Grab the prompts, read the breakdown, and let me know where you’re looking to automate.*


# **[Grab the Prompts](https://www.notion.so/product-templates/THE-EDGE-FIRST-AUTOMATION-PROMPT-MANUAL-2be5a2ccb52680fbbccbcf5763450089?source=copy_link)**

This article comes with a companion prompt manual—eleven prompts that walk you through the entire edge-first process, from mapping an unfamiliar workflow to diagnosing why your last automation project failed. The prompts aren’t checklists; they’re designed to turn an LLM into a genuine thinking partner by giving it enough context on the framework to reason alongside you. Grab them, adapt them, and use them as you read.

---


## **Why Core-First Fails**

I understand the instinct to automate the core. You’re staring at a workflow that eats hours every week, and you want to solve the whole problem. The vision is compelling: build an agent that handles the entire process, end to end, and free your team to work on something else.

But most core workflows contain more hidden complexity than anyone realizes until they try to automate them. Ambiguity that humans navigate without thinking. Exceptions that exist only in someone’s head. Tribal knowledge accumulated over years that nobody has ever written down. Teams consistently underestimate the hidden state in their workflows and overestimate how reliably current models will handle edge cases—especially if this is their first serious agent project.

The result is predictable: stalled agents, bloated scope, frustrated engineers, frustrated leadership, and QA cycles that never seem to converge. Trying to automate the core first is like trying to build a self-driving car before you’ve invented cruise control. You’re attempting the hard problem without having learned how your system behaves under load.

When I work with teams through the orientation prompts in the companion manual, one of the first things we establish is the difference between core expertise and edge work. Core expertise involves hard judgment, deep context, and high-stakes decisions where errors cascade. Edge work is repetitive, formatting-heavy, verification-focused—the kind of task where all the inputs are ready and you’re not making the hard calls, just moving and checking. That distinction matters because it determines where you should start.


## **The Five Edges Worth Attacking**

When you pick a valuable workflow to automate, map these five edges before you touch the core.

**Data preparation** is usually the first place to look. How do you collect context for this workflow today? How do you clean inputs, normalize formats, reconcile information from multiple sources? If any of that is manual—and it almost always is—you’ve found an edge worth owning. The time people spend wrestling data into usable shape before the “real work” begins is often shockingly high, and it’s work that requires almost no judgment once you understand the patterns.

**QA** is the second major category. How do you check for completeness, consistency, obvious errors? This is often something an LLM-as-judge can handle without needing to understand the full workflow. You’re not automating the work itself; you’re automating the verification that the work is ready to move forward. The companion prompts include a specific approach for designing these verification layers so they catch the 80% of issues that are mechanical while routing genuine judgment calls to humans.

**Synthesis** covers everything that involves summarizing or consolidating information. Sometimes all you need is to take a sprawling discussion thread and turn it into a clean summary—updating a Jira ticket description, compiling status across multiple workstreams, translating raw data into a format someone else can act on. This work consumes significant human time but isn’t particularly hard for an LLM, which makes it a high-leverage edge to own.

**Packaging** is what happens after the work is nominally done. How does analysis become a brief? How does a decision become a report? How does finished work get formatted for the next stage? With current models handling longer document generation more reliably than they did even a few months ago, you have options here that didn’t exist recently—the ability to get all the way to a finished deliverable, not just a draft that needs heavy editing.

**Coordination** is where tribal knowledge often hides. The pattern is usually someone manually pulling information from one system, talking to someone, then putting that information somewhere else. If you can automate the movement of context from point A to point B—without requiring the human to serve as the translation layer—you’ve often captured enormous value.


## **Why Edges Work**

There’s a reason edges are the right starting point, and it’s not just that they’re easier. Edges are where friction concentrates. Anyone who’s worked seriously on workflow improvement will tell you that the core is usually where things flow most smoothly; the edges are where people groan, where things stall, where the same problems recur week after week.

Edges also tend to be low-judgment tasks. The inputs are ready, the outputs are well-defined, and the work is more about transformation than decision-making. That profile is perfect for current LLMs, even accounting for their imperfections. Your first agent won’t be perfect—you should assume it’s imperfect and design it to deliver value anyway. The companion manual includes a specific prompt for designing “semi-manual version-0” implementations that automate the predictable 70-80% while keeping humans in the loop for everything else. That’s the right ambition level for early edge work.

When something goes wrong at an edge, the errors tend to be cheap and recoverable. The humans who do the core work were handling those edges before; if an exception occurs, they can pick it up without the whole workflow breaking down. You have time to look at the data, understand what went wrong, and improve. Compare that to a core automation error, which typically cascades into multiple downstream problems before anyone notices.


## **The Trust Problem Nobody Mentions**

Here’s what almost nobody says out loud about AI automation: it’s not primarily a technical project. It’s an organizational trust exercise, and if you get the trust wrong, nothing else matters.

The humans involved in valuable workflows tend to have deep knowledge that they can’t fully articulate. They’re fingertipy on the work—they have intuitions and pattern recognition built over years that manifest as “I just know when something’s off.” They need to be confident that your automation won’t cost them that fingertipy feeling, won’t make them less connected to work they’ve spent years mastering.

These people are craftspeople. If the highly valuable part of a customer success workflow is the nuanced understanding of customer history and how to calibrate a response based on years of relationship context, you want to automate around that expertise, not through it. The goal is to let the customer success agent apply their knowledge efficiently, with their full intuition intact, without being distracted by data prep and report formatting.

When you start by attacking the edges, you’re making a statement about what you value. You’re reminding the people doing the work that their judgment matters, that they’re worth keeping in the loop because of the craft they bring. This matters more than any technical consideration, because if you lose that trust, they won’t share the secrets you need for the rest of the workflow. The tribal knowledge stays locked in their heads, and your automation project becomes a purely technical exercise missing all the human context that would make it work.

The companion manual includes specific prompts for extracting tribal knowledge safely and communicating automation initiatives without triggering fear. The framing matters: you’re protecting expertise, not replacing it. When people feel valued rather than threatened, they open up about the exceptions, the unwritten rules, the patterns that newcomers always miss.


## **What This Means for Your Role**

I’ve watched edge-first automation land differently depending on where you sit in the organization. A few field notes on what I’m seeing.

**Product managers** tend to fixate on the core workflow because that’s where the product value lives. Resist this. Your job in edge-first automation is to map the full surface area of the workflow and identify which edges, if automated, would make the core more visible and tractable. The best PM contribution isn’t scoping the agent—it’s scoping the edges so engineering doesn’t boil the ocean. Start by documenting where your users lose time before and after the “real work” happens.

**Engineering and technical leads** often underestimate the organizational complexity and overestimate the technical complexity. The hardest part of edge automation isn’t building the agent; it’s getting the tribal knowledge out of people’s heads and earning enough trust that they’ll actually use what you build. Your job is to ship something semi-manual fast, learn from real usage, and iterate. If your first version takes more than two weeks, you’re overbuilding.

**Sales teams** have some of the highest-leverage edges I’ve seen: CRM updates, call summarization, proposal assembly, competitive research synthesis. The pattern is always the same—reps spend hours on work that doesn’t require their judgment but does require their time. If you’re in sales leadership, audit where your reps lose time outside of actual selling. That’s your edge map.

**Customer success** is where I first noticed the fingertipy problem. The valuable part of CS work is the long-term relationship memory—knowing that this customer had a rough onboarding two years ago, or that this exec prefers direct communication. You cannot automate that, and you shouldn’t try. What you can automate is everything around it: ticket summarization, health score updates, renewal prep, handoff documentation. Protect the craft by eliminating the tedium.

**Operations and RevOps** are often sitting on the most automatable edges in the company and don’t realize it. Data reconciliation, report generation, system-to-system handoffs, QA checklists—this is edge automation paradise. If you’re in ops, you’re probably already doing the manual version of what an agent should handle. Start documenting the steps you repeat weekly; that’s your implementation spec.

The common thread across all of these roles: edge-first automation isn’t about replacing what you do. It’s about reclaiming the time you spend on work that doesn’t require your judgment so you can focus on work that does.


## **The Path Inward**

Attacking the edges doesn’t mean abandoning the core. It means earning the right to approach it.

If you own QA, handoffs, data preparation, and synthesis, you’ve built the infrastructure to eventually automate the core successfully. You’ve learned where the exceptions cluster. You’ve mapped the hidden state that would have blindsided you if you’d started at the center. You’ve earned the trust of the people who know where the bodies are buried—and now they’re actively helping you instead of protecting their territory.

You’re also teaching yourself and your organization how AI automation actually works. This isn’t just a technical project; it’s an upskilling effort for everyone involved. Each edge you automate successfully builds confidence and reveals the next opportunity.

The question of when to approach the core is one of the trickier judgment calls in this whole framework. The companion manual includes a readiness assessment that looks at five dimensions: whether your inputs are now clean and reliable, whether the boundary between edge and core is clear, whether you can see the exceptions that used to be invisible, whether the operators trust what you’ve built, and whether your edge automations run stably without constant intervention. If you can’t answer yes to all five, you’re not ready—and rushing will cost you more than waiting.


## **Applying This Tomorrow**

Pick a workflow you touch every single week that matters to you or your team. Map the edges by asking yourself where you waste time prepping, where you check for errors, where you hand off repeatedly, where you summarize the same information over and over.

Then pick the simplest edge—not the most impressive one, but the one that gives you the fastest, clearest lift. The philosophy here is that early wins build trust, surface exceptions, and create momentum, while overreach kills projects. You want something you can ship and learn from in one to two weeks, not a moonshot that takes months to validate.

Build something semi-manual to start. Maybe it’s a script that handles 80% of cases and flags the rest for human review. Maybe it’s a prompt that generates drafts you refine. The point isn’t to achieve full automation immediately; it’s to start capturing value while you learn the real complexity of the task. The companion prompts walk through exactly how to design these version-0 implementations so they’re useful from day one without requiring months of engineering.

If you automate three or four edges in a row and start feeling good, resist the urge to build a grand unified vision. The workflow itself will reveal the correct place for automation and the correct place for human expertise. That’s how real AI transformation happens—not by replacing the core on day one, but by reclaiming the edges until the path forward becomes obvious.

Where are you looking to automate?

[![](https://substackcdn.com/image/fetch/$s_!zQn0!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F40dd1379-4eb0-44f4-98f3-1ac3b50cc9a4_2048x2048.png)](https://substackcdn.com/image/fetch/$s_!zQn0!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F40dd1379-4eb0-44f4-98f3-1ac3b50cc9a4_2048x2048.png)
