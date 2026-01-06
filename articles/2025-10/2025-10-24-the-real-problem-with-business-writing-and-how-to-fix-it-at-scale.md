---
title: "The Real Problem With Business Writing (And How to Fix It at Scale)"
author: "Nate Jones"
published: 2025-10-24
url: https://natesnewsletter.substack.com/p/i-spent-200-hours-teaching-ai-writinghere
audience: everyone
scraped_at: 2026-01-05 19:13:34
---

It’s the universal problem. EVERYONE is drowning in AI docs slop.

I’ve written guides for [Excel](https://natesnewsletter.substack.com/p/finally-ai-can-do-excel-and-powerpointget?r=1z4sm5), and for [Powerpoint](https://natesnewsletter.substack.com/p/powerpoint-is-the-hardest-thing-for?r=1z4sm5).

Writing a really good guide for Word (docs) was the hardest for me.

That’s because the problem is SO big. We all spend DAYS a week in docs. Reviewing them. Writing them. Editing them.

And increasingly complaining about them because they’re AI slop.

And that has real consequences—almost every business I know is having issues with employees producing AI slop that impedes business decision-making.

Let me let you in on a secret: the problem is NOT the model. I get asked that all the time. It’s not the model—it’s the organization.

Specifically, organizations relied on talented employees to maintain a document bar for hundreds of years. That’s gone now.

We don’t have a new way to maintain a document bar. And we desperately need one.

That’s why I wrote this. To solve the biggest AI problem in business: how to scale good business writing.

After hundreds of hours teaching business writing and seeing what works and what doesn’t, I’m sharing a full writing kit for AI here. It’s not just for Word. It’s for Google Docs. For Slack. For anywhere you have a need for less AI slop and more business writing.

Here’s what you get:

- The nine principles of business writing with AI that eliminate slop

  - **Every Document Exists to Change Someone’s Mind or Behavior**
  - **Structure Is a Forcing Function for Thought**
  - **Constraints Do More Work Than Instructions**
  - **Quality Scales Through Self-Evaluation, Not Human Review**
  - **Failure Modes Are More Predictable Than Success**
  - **You Can’t Prompt Your Way Around Bad Inputs**
  - **Every Organization’s Documents Sound the Same Unless You Fight It**
  - **Iteration Is About Diagnosis, Not Polishing**
  - **Documents Don’t Exist in Isolation—They Exist in Workflows**
- Eight production-ready prompts built on these principles, plus a quality evaluator skill for Claude (or ChatGPT)

  - Meeting Notes (from transcript or raw notes)
  - Status Report (weekly/monthly updates)
  - Executive Brief (decision memo)
  - Project Proposal (resource allocation request)
  - PRD (Product Requirements Document)
  - Technical Documentation (user guide / how-to)
  - Post-Mortem / Incident Report
  - SOP / Process Document (standard operating procedure)
  - Business Evaluation Claude Skill (document quality evaluator you can run automatically—also works in ChatGPT)
- A video walking through exactly why generic prompts fail and how these principles fix the core problems—plus a demo of how you can modify these prompts for your business
- A framework for customizing these prompts to your organization’s standards, voice, and decision-making processes
- Real examples showing the difference between AI slop and documents that actually help teams execute
- And yes, a special note on how to adapt prompts and strategy for Microsoft Copilot (check out my [full Copilot guide here](https://natesnewsletter.substack.com/p/the-complete-microsoft-ai-copilot?r=1z4sm5))

This isn’t about finding better AI tools. Every company I work with already has access to models that can write production-quality docs. The problem is they don’t know how to prompt for it, and they don’t know how to scale quality evaluation across their teams.

If your organization is producing AI documents faster than you can evaluate them, if you’re drowning in meeting notes that capture nothing actionable, if your teams are converging on that bland default AI voice—this is the methodology that fixes it.

This is how you teach AI to write like your business actually thinks.

Let’s write better.


## *[Grab the prompts and business evaluator skill](https://www.notion.so/product-templates/Prompts-for-Business-Writing-2955a2ccb526808692e0d4e42e3a3d3b?source=copy_link)*

I’ve built a practical framework for business documents that actually works.

The foundation is nine core principles—things like defining purpose upfront, building in constraints, adding self-checks, and using real inputs instead of generic templates. I’ve applied these principles to eight document types that come up constantly: meeting notes, status reports, executive briefs, project proposals, PRDs, technical documentation, post-mortems, and SOPs.

For each document type, you get a complete prompt that embeds these principles. I’ve also included the reasoning behind each prompt’s structure, guidance on adapting it to your specific workflow and voice, the common failure modes it’s designed to prevent, and concrete examples showing what good output looks like compared to the usual AI slop.

The practical result: you draft faster, make clearer decisions, and execute more reliably. The quality checks are built into the prompts themselves, so you catch typical AI errors—vagueness, hallucinated details, missing context—before anyone else sees them.

I’ve also created a downloadable Business Evaluation Skill that scores any document against these same nine principles. It returns prioritized, actionable fixes, so you can both create and systematically improve business writing across your team.

---


## Using these prompts with Microsoft Copilot

These prompts work in Copilot, but you’ll need to adapt them slightly.

Copilot has access to your Microsoft 365 context—recent emails, documents, meeting transcripts—which means you can replace explicit input sections with references like “based on yesterday’s leadership sync” or “using the Q4 roadmap in my OneDrive.” The trade-off: Copilot’s context window is smaller and it’s more aggressive about summarizing, so your prompts need to be tighter.

Strip out any examples from the prompt itself and instead point Copilot to a reference document you’ve saved. The self-check sections are critical here—Copilot will confidently generate plausible nonsense if you don’t explicitly tell it to verify claims against source material.

Test each prompt once, save the working version as a Copilot prompt template, and iterate from there. The evaluation skill won’t run directly in Copilot, but you can paste its output into a new Copilot session and ask it to score the document.

---


# The Real Problem With Business Writing (And How to Fix It at Scale)

I’ve spent the last six months watching companies drown in their own documents. Not because people got worse at writing. Not because standards dropped. But because AI made it possible to produce 100x more documents without 100x more thinking.

The volume broke the system. And nobody knows how to fix it because we never needed systematic quality control before. When production was limited by human speed, quality control was informal. You knew who the good writers were. You could read their work. You could give feedback. It scaled because production scaled slowly.

AI broke that. Production is now nearly infinite. And the old quality control system—read everything, give feedback, hope people improve—mathematically cannot work anymore.

So here’s what I’ve learned about what actually matters when you’re trying to maintain quality at AI-assisted scale. These aren’t tips. These are the structural principles that separate organizations shipping garbage from organizations shipping work that matters.

---


## Part 1: Understanding What Documents Actually Do

Before you can prompt AI to write anything useful, you need to understand what business documents are actually for. This sounds obvious, but most document failures happen because nobody asked the fundamental questions: why does this document exist, and what is it supposed to make happen? These first two principles are about purpose and structure—the foundation everything else builds on.


### Every Document Exists to Change Someone’s Mind or Behavior

This sounds obvious. It’s not.

Most business documents fail because nobody asked “what is this supposed to make happen?” before writing it. A status update that doesn’t surface blockers. A proposal that doesn’t request a decision. Meeting notes that don’t capture what was decided or who’s doing what next. Technical documentation that explains the system but doesn’t help anyone actually use it.

The first principle is simple: if you can’t articulate what this document is supposed to make someone do or understand differently, you shouldn’t write it. And if you’re prompting AI to write it, you need to tell it that purpose explicitly, because AI has no idea why documents exist in organizations.

When I review documents that people say “feel like AI wrote them,” the problem is never the prose quality. It’s that the document has no theory of change. It explains things. It describes things. It analyzes things. But it doesn’t orient the reader toward a decision or action. That’s because the human prompting the AI didn’t specify the outcome.

Here’s what this means practically: before you prompt AI to write anything, you need to answer “who reads this and what do they need to do after reading it?” Not what information do they need. What behavior change or decision does this enable. If you can’t answer that, the document is already broken before AI touches it.


### Structure Is a Forcing Function for Thought

The second principle: structure is not formatting. Structure is the logic of your argument. And most people confuse the two.

When AI produces that generic five-section document with Introduction, Background, Analysis, Recommendations, Conclusion—that’s not structure. That’s a template. Templates don’t force you to think. They let you fill in boxes without developing an actual argument.

Real structure does two things. First, it sequences information in the order the reader needs it to make a decision. Second, it makes gaps in your thinking visible. If you can’t fill a section, that tells you what you don’t know yet.

Here’s why this matters for AI-assisted writing: when you give AI a template (”write this in five sections”), it will happily fill every section with content whether or not that content advances an argument. It will pad. It will include generic transitions. It will create the appearance of completeness while saying nothing.

But when you specify structure as logic—”state the problem, provide three solution options with trade-offs, recommend one with reasoning, specify what decision you need”—AI has to actually construct an argument. The structure forces it to think, the same way it forces humans to think.

I learned this watching product managers prompt AI to write PRDs. The ones who said “write a PRD with these sections: Overview, Requirements, Timeline” got documents that looked like PRDs but contained no actual decisions. The ones who said “write a PRD that helps engineering answer: what are we building, why, what are the acceptance criteria, what are we explicitly not building” got documents that engineering could actually use (assuming they gave good inputs).

The structure you specify determines whether AI produces content or clarity. Most people specify templates and wonder why the output is generic.

---


## Part 2: Controlling AI Generation to Prevent Slop

Once you understand purpose and structure, the next challenge is controlling what AI actually produces. These three principles are about the mechanics of prompting: how to use constraints to force prioritization, how to build quality control into the generation process itself, and how to test for predictable failures rather than hoping for excellence.


### Constraints Do More Work Than Instructions

Third principle: every word you add to a prompt that says “include this” is less valuable than a word that says “don’t include that.”

This is counterintuitive. We think prompting is about telling AI what to generate. But AI’s default is to be helpful, comprehensive, thorough. It will include everything that might be relevant. The problem isn’t getting AI to add more. The problem is getting it to choose.

Constraints force prioritization. When I tell AI “write this in exactly 500 words,” it has to decide what matters most. When I say “one page maximum,” it can’t pad. When I say “use only the data I provided, do not infer or estimate,” it can’t fill gaps with plausible-sounding nonsense.

The best document prompts I’ve seen are 70% constraints and 30% instructions. They spend more words on what not to do than what to do. Because the quality problem in AI-generated writing isn’t that it fails to generate content. It’s that it generates too much content with too little signal.

Here’s how this shows up in practice.

Bad prompt: “Write an executive brief about this project.” AI will give you five pages analyzing everything.

Good prompt: “Write a one-page executive brief. First paragraph must contain the decision request. Include exactly three options. Each option: two sentences maximum. No background section. No conclusion section. End with your recommendation and the single most important risk.”

The second prompt forces AI to prioritize. The first prompt allows it to be comprehensive, which in business writing is almost always wrong.


### Quality Scales Through Self-Evaluation, Not Human Review

Fourth principle: if your quality control system depends on humans reading everything, you’ve already lost.

The math is brutal. If AI lets someone produce 50 documents a week instead of 5, and you have 10 people doing this, you now need to review 500 documents a week instead of 50. Even if you hire more reviewers, you’re just moving the bottleneck. Review doesn’t scale.

What scales is making the AI review its own work before it gives it to you. This sounds like a trick. It’s not. It’s the only way I’ve found that actually works at scale.

Here’s what I mean: before AI outputs a document, make it check its own work against explicit criteria. Not “is this good” but “does this document contain a decision request in the first paragraph? Are all three options listed? Is each option two sentences or less? Are there any claims without supporting data? Are there any sections I was told not to include?”

When you force AI to self-evaluate against specific criteria, two things happen. First, it catches most slop before you see it. Second, it makes the AI actually construct the document differently, because it knows it will be checked. The same way humans write differently when they know someone will review their work carefully.

The organizations I’ve seen successfully maintain quality at AI scale all do some version of this. They don’t try to review everything. They build self-evaluation into the generation process. The AI becomes its own first-pass reviewer. Then humans spot-check, looking for patterns of failure rather than reviewing every document.

This only works if you specify concrete quality criteria. “Is this good” doesn’t work. “Does this have specific numbers with sources” works. “Is this clear” doesn’t work. “Is every action item assigned to a specific person with a specific deadline” works. The more concrete your quality checks, the more reliable the self-evaluation.


### Failure Modes Are More Predictable Than Success

Fifth principle: you can’t define what makes a great document, but you can define what makes a broken one.

Every document type has predictable failure modes. Meeting notes without action items. Executive briefs without decision requests. Technical docs that skip steps. Proposals without budgets. Status reports without blockers.

These aren’t style preferences. They’re functional failures. A meeting note without action items doesn’t do the job of a meeting note, which is to ensure follow-through. An executive brief without a decision request doesn’t do the job of an executive brief, which is to get a decision made.

This is the key insight for quality control at scale: you don’t need AI to recognize great writing. You need it to recognize broken documents. And broken is much easier to define than great.

When I work with companies on this, I have them make a list: what are the failure modes for each document type we produce regularly? Then we build those directly into the prompts. Not as aspirations (”write a great status report”) but as checks (”after writing, verify: does this report identify specific blockers? Are they assigned to owners? Is there a clear ask for help?”).

This works because broken is objective. You can test for it. Either there’s a decision request or there isn’t. Either action items have owners and deadlines or they don’t. Either technical steps are numbered and complete or they’re not.

Great is subjective. Broken is measurable. At scale, you optimize for “not broken” first, and “great” is a bonus.

---


## Part 3: Protecting Input Quality and Organizational Voice

The mechanical aspects of prompting matter, but they can’t overcome two deeper problems: bad inputs and voice convergence. These principles address what happens before you prompt (ensuring you have real information, not assumptions) and what happens after repeated AI use (preventing everything from sounding the same).


### You Can’t Prompt Your Way Around Bad Inputs

Sixth principle: garbage in, garbage out. But it’s more subtle than that.

AI will happily write a comprehensive document from incomplete information. It will fill gaps. It will make reasonable-sounding inferences. It will create the appearance of completeness. And you won’t notice until someone tries to act on the document and discovers half the information is plausible fiction.

The best prompt in the world can’t overcome bad inputs. If you’re writing a project proposal and you don’t actually know the budget, AI will estimate. If you’re writing meeting notes and you don’t have the decisions documented, AI will infer from context. If you’re writing technical documentation and the specs are vague, AI will make reasonable guesses.

This is dangerous because the output looks complete. It has the right structure. It has the right tone. It passes all your quality checks. But it’s built on assumptions, not facts.

I learned this watching a product team use AI to write PRDs. They’d feed it brainstorming notes and customer feedback snippets and ask for a PRD. The AI would produce a beautiful document with acceptance criteria, success metrics, technical requirements. Engineering would start building, then discover halfway through that the acceptance criteria were never actually agreed to—AI had inferred them from the brainstorming notes.

The principle: before you prompt AI to write anything, you need to verify you have the actual information required. Not “I sort of know this” but “I have the specific data, decisions, examples I need.” If you don’t, the prompt should be “help me identify what information I’m missing” not “write the document.”

This means the discipline happens before prompting. You need to know: what information does this document type require? Do I have it? If not, what questions do I need to answer first?

Most people skip this step because AI makes it easy to skip. Bad inputs plus good prompts equals confident nonsense.


### Every Organization’s Documents Sound the Same Unless You Fight It

Seventh principle: AI has a default voice, and it will eat your organization’s voice if you let it.

Here’s what happens: Person A uses AI to write a proposal. Person B uses AI to write a status report. Person C uses AI to write meeting notes. Six months later, every document in your organization has the same cadence, the same transitions, the same hedge language, the same generic professionalism.

You lose differentiation. You lose personality. You lose the signal that comes from how people write, not just what they write. Everything starts to sound like it came from the same corporate communications template, even when it’s coming from engineering, product, and sales.

This isn’t just aesthetics. Voice carries information. When an engineer writes bluntly and a product manager writes diplomatically, that tells you something about certainty levels. When someone’s writing is careful and qualified, that signals they’re uncertain. When it’s direct and specific, that signals confidence. AI’s default voice is always diplomatically hedge-y, which flattens this signal.

The principle: if you want documents that sound like your organization, you need to either specify voice in every prompt or accept that everything will sound like generic AI.

I’ve seen two approaches work. First, organizations that develop explicit voice guidelines—”our executive briefs are direct and recommendation-forward, not hedged and analysis-heavy”—and include those in every prompt. Second, individuals who develop personal voice specs they reuse—”I write in first person, use short sentences, am blunt about problems.”

What doesn’t work: assuming AI will “figure out” your voice from context. It won’t. It will use its default unless you override it explicitly every time.

This is extra important for external documents. Your marketing should sound like your marketing, not like everyone else’s AI-generated marketing. Your customer-facing docs should carry your brand voice. If you’re not specifying this, you’re converging to generic.

---


## Part 4: Making AI Writing Work in Your Actual Workflow

The final challenge isn’t about individual documents—it’s about how documents fit into your organization’s actual work. These last two principles address iteration (how to improve drafts efficiently) and workflow integration (how to make documents that people can actually use in context).


### Iteration Is About Diagnosis, Not Polishing

Eighth principle: most people iterate by saying “make it better.” This doesn’t work.

When AI gives you a first draft and something feels off, the instinct is to say “improve this” or “make it more professional” or “make it clearer.” AI will rewrite the whole thing. You’ll read the rewrite, still feel like something’s off, ask for another pass. Three iterations later you have a document that’s been fully rewritten but still doesn’t do what you need.

The problem is diagnostic. You haven’t identified what’s actually wrong. You just know something doesn’t feel right. And AI can’t diagnose that for you—it will just try variations until you’re satisfied, which is an inefficient way to find the problem.

The principle: effective iteration requires specific diagnosis before the next prompt.

Here’s what this looks like in practice. First draft comes back and something feels wrong. Before you prompt for changes, you need to articulate: what specific thing is broken? Is it that Section 2 is too long? Is it that the examples are generic? Is it that the tone is too formal? Is it that there’s no clear recommendation? Is it that the structure is illogical?

Once you can name the problem specifically, you can fix it specifically. “Section 2 is too long—cut it from 400 to 200 words by removing the background context and keeping only the three main points.” That gets you a targeted fix. “Make it better” gets you a rewrite.

This is hard because diagnosis is the actual skill. Anyone can tell when a document doesn’t work. Knowing why it doesn’t work and what specific change would fix it—that’s expertise. And AI doesn’t remove the need for that expertise. It just makes the cost of not having it more expensive, because you waste iterations.

The organizations I’ve seen succeed at AI-assisted writing have people who can read a draft and quickly identify the specific failure. Not “this feels off” but “this has no decision request, Section 3 makes claims without data, and the conclusion is vague.” Then they can iterate efficiently.

If you can’t diagnose specifically, you end up in rewrite loops. And at some point it’s faster to just write it yourself.


### Documents Don’t Exist in Isolation—They Exist in Workflows

Ninth principle: most people prompt AI to write individual documents. They should be prompting AI to write documents that fit into their organization’s actual workflow.

Here’s what I mean. A status report isn’t just information. It’s an input to a decision process. Someone reads it, escalates blockers, reallocates resources, updates roadmaps. If the status report doesn’t surface information in the format that decision process needs, it doesn’t matter how well-written it is.

Meeting notes aren’t just a record. They’re supposed to ensure follow-through. If your organization tracks action items in Asana, and your meeting notes format doesn’t match what you can easily import into Asana, you’ve created friction. People won’t follow through.

Technical documentation isn’t just explanation. It’s supposed to help someone solve a problem. If your docs don’t match how people actually troubleshoot—if they’re organized by feature when people search by error message—they don’t work no matter how complete they are.

The principle: before you prompt AI to write a document, you need to know how that document is used in your organization’s workflow. Who reads it? What do they do with it? What format makes that easier?

This shows up in subtle ways. Some organizations make decisions in meetings and need notes that are action-oriented. Others make decisions async in docs and need notes that are context-heavy. If you prompt AI to write “meeting notes” without specifying which workflow you’re in, you’ll get generic notes that don’t serve either purpose well.

The best document prompts I’ve seen include workflow context. “Write status report formatted for our Monday standup review, where we track blockers by owner and escalate anything over 3 days old.” That tells AI not just what information to include, but how to structure it for actual use.

Most people skip this because they think of documents as standalone artifacts. But documents are tools in workflows. And if the tool doesn’t fit the workflow, it doesn’t matter how good the tool is.

---


## The Real Skill Is Knowing What to Specify

The meta-principle underneath all of this: the bottleneck in AI-assisted writing isn’t AI capability. It’s human ability to articulate what they actually want.

Most people prompt AI the way they brief junior employees: vaguely, assuming the AI will figure out what they meant. But AI can’t read your mind. It can’t infer your standards. It doesn’t know what matters in your organization.

Every time someone shows me a bad AI-generated document, the problem is in the prompt (by which I mean the prompt and/or the inputs that are part of the prompt). They said “write a status report” when they meant “write a status report that surfaces blockers, assigns them to owners, and makes a specific ask for help—here’s your info.” They said “write meeting notes” when they meant “write meeting notes that document decisions with decision-makers and action items with owners and deadlines—here’s my transcript.”

The gap between what people say and what they mean is where quality dies. And AI forces that gap into the open. With humans, you could be vague because they’d ask clarifying questions. With AI, vague prompts get vague output, and people blame the AI.

But here’s what I’ve learned: forcing yourself to be specific enough to prompt AI well makes you better at knowing what you actually want. It makes you better at writing yourself. It makes you better at giving feedback to humans. Because it forces you to articulate your quality standards explicitly instead of relying on “I know it when I see it.”

The organizations that succeed at AI-assisted writing aren’t the ones with the best writers. They’re the ones with the clearest standards. They know what makes a document work in their context. They can articulate it concretely. They can test for it systematically.

That’s the real work. Not prompting AI. Knowing what you’re trying to produce clearly enough that you can specify it.

[![](https://substackcdn.com/image/fetch/$s_!zvdN!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2d9717a8-fd5f-4cc6-99f1-171134d4ffcb_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!zvdN!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2d9717a8-fd5f-4cc6-99f1-171134d4ffcb_1024x1024.png)
