---
title: "The Router Era: Gemini 3 and the End of “Which Model Is Best?”"
author: "Nate Jones"
published: 2025-11-19
url: https://natesnewsletter.substack.com/p/how-gemini-3-changes-your-job-a-practical
audience: everyone
scraped_at: 2026-01-05 19:11:31
---

Every few months these days, a new AI model forces us to rethink what we expect from computers.

Gemini 3 is one of those moments.

It doesn’t just talk. It can look at screens, understand videos, absorb huge piles of mixed information, and make sense of things that used to require a human staring, scrolling, or watching.

Suddenly, a whole category of “I need to look at this myself” work has just become fair game for acceleration (or semi-automation). That includes UI bugs, messy dashboards, long meetings, sprawling docs—stuff that was too visual and context messy before.

Gemini 3 is the first of a new wave of truly multimodal models, truly visual and agentic models. It’s going to change how we do our jobs. Not because AI replaces us, but because it changes where our attention is worth spending.

For the last couple of years, the big AI question was: Which model is best?

Gemini 3 forces a better one: Which model should handle which kind of work?

I’ll give you a cheat sheet: if the task involves seeing or doing, Gemini 3 should be at the top of the list. If it involves writing or persuading, GPT 5.1 or Sonnet 4.5 is still your best friend.

Gemini 3 forces a better one: Which model should handle which kind of work? Here’s a cheat sheet: if the task involves seeing or doing, Gemini 3 is your engine. If it involves writing or persuading, GPT 5.1 or Sonnet 4.5 is still your best friend.

That simple split hides a surprising amount of complexity. We’re just at the beginning of figuring out where Gemini 3 starts to shift our workflows, but I think we can already see directional indicators of how this new model will reshape work.

Here’s what’s in the box:

- **The Gemini 3 Work Prompt**: a paste-and-go prompt that interviews you about your work (and your team, if applicable), maps your workflows, and tells you where Gemini 3, GPT 5.1, Sonnet 4.5, or smaller models actually belong.
- **Workflows, role-by-role**: a role-by-role draft map across PM, engineering, design, marketing, sales, data, support, and exec workflows. I did the hard work of pulling out the implications of the model and looking at new use-cases Gemini unlocks, plus where it’s not worth the change.
- **Cost–Benefit & Risk Calculator**: guidance for deciding where Gemini 3 clears the bar (and where it doesn’t)
- **The Router Era**: Notes on how Gemini 3 changes human work: what “see & do” work shifts to the model, and the specific areas we humans still lead
- **A Custom 90-Day AI Plan**: the prompt will give you a suggested action plan to roll toward Gemini 3 in a smart way
- **The “Not Yet” List**: guardrails to keep you from blowing yourself up with early agentic workflows

This isn’t a story about a new model. It’s a story about how your job changes when AI can finally see. I’m not saying this to be dramatic: the workflows Gemini 3 is opening up with multimodal capabilities can save you hundreds of hours of work over a year. WEEKS of work. The model will also enable new kinds of work we haven’t been able to do much of yet at all.

This is one of those step-change moments when AI turns on the lightbulbs on a whole new part of the human-AI collaborative world. We’re just beginning to explore it.

If you want clarity—not hype—on what that means for your role, read on.


## [Grab the Gemini 3 Work Prompt](https://www.notion.so/product-templates/Map-to-where-to-use-Gemini-3-2b05a2ccb52680c384b5d164d1093ba7?source=copy_link)

Here’s the routing prompt: it walks you through deciding where Gemini 3 actually makes sense versus GPT 5.1, Sonnet 4.5, or cheaper models.

The model interviews you about your organization—teams, current tools, constraints, goals. Then it builds a workflow map by role: PM, engineering, data, customer success, sales. Each workflow gets rated on visual intensity, context window requirements, stakes, and nuance needs.

From that, you get a routing plan. For each workflow, which model should be primary, which should be secondary, and why. The prompt explicitly flags high-potential Gemini 3 cases—screens, video, large mixed-context documents—and “stay with what you have” cases like pure text chat, basic coding tasks, or high-volume low-stakes work where cost matters.

Next comes the cost-benefit and risk analysis for each Gemini 3 candidate. Human time saved versus token costs, latency, and failure modes. Finally, the model produces a 90-day action plan: top pilots to run, v1 routing rules, AI platform and ops implications, and a short “do not try this yet” list so you don’t deploy agents into production before you’re ready.

---


# The Router Era: Gemini 3 and the End of “Which Model Is Best?”

This isn’t a launch recap. It’s a practical guide to how Gemini 3 should change how you route work across models.

Gemini 3 came out yesterday as, by most public benchmarks, the strongest frontier model in the world. The most important thing about it has nothing to do with benchmarks. The real story is that Gemini 3 makes it impossible to keep asking “which frontier model is best.” It’s clearly dominant at some things and unremarkable at others. It’s phenomenal at video, screens, and massive context windows. It’s not obviously better at persuasive writing or everyday chat. That gap matters.

If your organization is still saying “we’re an OpenAI shop” or “we’re an Anthropic shop,” you’re solving the wrong problem: the interesting question is no longer which model, it’s how you route between them. Someone in your organization needs to own the routing layer, and they need to own it now—not as a side project, as an actual function.

I want to give you a simple abstraction to work with. Every abstraction is wrong, but some are useful.

This one fits on a flashcard: if it’s a see-or-do task, think Gemini 3.

If it’s a write or talk task, think Claude Sonnet 4.5 or ChatGPT 5.1.

If it’s cheap bulk work, use small flash models. Burning Gemini 3 on mass summarization is usually just setting money on fire.

None of this is a law, but it’s a reasonably good default. You’ll find edge cases, but it beats pretending one model can do it all.


## What Actually Changes With Gemini 3

The real unlock isn’t better chat. It’s that surfaces that were effectively dark to AI are becoming legible. Before Gemini 3, raw user interfaces were hard to code, hard to design, and hard to analyze. Long, messy video was basically off-limits, and giant piles of code, docs, and screenshots had to be digested by humans—a PM, a designer, an SRE—before AI could do anything useful.

Gemini 3 can read the UI directly instead of guessing from logs. It can watch footage instead of reading transcripts, and it can digest much bigger chunks of “everything related to this system” at once. The workflows that move the needle won’t be “better chat.” They’ll be things you simply couldn’t do with AI before: UI debugging, design QA, admin panel automation, video research, user testing at scale.

That’s where the leverage is.

A good diagnostic question for each team is simple: where do you have a lot of eyes-on-glass work today? That’s where Gemini is most relevant.


## The Hard Skill Is Now Specification and Review

Models are getting better at doing. The bottleneck is shifting toward telling them what to do and deciding whether what they did is acceptable. Put Gemini 3 inside the new Antigravity code editor and the shift becomes literal. In Antigravity, agents propose terminal commands, code diffs, and browser actions. You approve or reject their artifacts, their plans, their patches, their refactor proposals.

That’s not “prompt engineering” in the pejorative sense. It’s much closer to working with a colleague to write a runbook, design a spec, or do fast and high-quality code review. Antigravity isn’t the only way to develop; every engineer has a stack that feels ergonomic to them. Some are finding Antigravity compelling. Others are sticking with Cursor, Codecs, or Claude Code, all viable options.

But Antigravity is shifting where we pay attention in ways anyone building with agents needs to understand, even if you’re not a coder. It dares you to focus on where you need to intervene with an agent that’s building something rather than focusing on the code itself. We’ve seen glimpses of this in how Cursor is evolving, but Antigravity leans in hardest on that pattern.

This implies that great work going forward will look weirdly similar whether you’re a product manager or a tech lead. It’s work done by people who can describe what they want built with clarity and who can smell a bad artifact quickly. Anyone who has worked around code knows that’s true. Evaluate Gemini less on “can it write code for me?” and more on “can I articulate intent, get a useful artifact back, and refine quickly?”


### A Quick Note on Risk

None of this means “let Gemini 3 loose on prod and don’t think about it.” The right mental model is supervised agents: they propose plans, patches, and UI actions; you approve and monitor. The failure modes are still real—wrong command, wrong record, wrong interpretation of a chart. The win isn’t removing humans from the loop; it’s making that loop cheaper and higher leverage—reviewing one good diff instead of twenty half-baked branches.


## Context Abundance Changes Where You Pay Cognitive Taxes

A million token context window with strong retrieval doesn’t mean you dump in your knowledge base and go to sleep. It shifts where you spend effort. You spend less time curating perfect little packets of context. You spend more time deciding what question is worth asking and how you want the answer structured.

Gemini is now good enough that another hour cleaning context often buys you less than ten minutes spent on a better question and output format. For example: asking for a migration plan instead of yet another bulleted summary. You need to start thinking in terms of query design, not just data preparation. Given that we can throw in a chunk of the repo and docs, what’s the most valuable question to ask? What structured artifact do we want back—a diff, a table, a synthesis, a six-pager?

Teams that excel at asking sharp questions and defining outputs will outrun teams that burn that same hour shaving a few stray paragraphs out of the context window.


## What This Actually Changes in the Org


### Product Managers

**What changes**

You can treat raw UX and video artifacts as first-class inputs, not homework you have to watch before you ask for help. For early discovery and competitive analysis, prompts like “what’s going wrong in these videos and screens?” or “compare the flows across these three apps and propose a hybrid” suddenly work.

You can also ask for specs grounded in what the product actually looks like—user stories, edge cases, acceptance criteria—by giving Gemini real screens instead of just prose.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1**

Narrative PRDs, stakeholder docs, decision memos, and exec emails still belong with Claude Sonnet 4.5 or ChatGPT 5.1. You want maximum clarity and persuasion there, so use the tool your organization already prefers for writing.


### Go-To-Market Teams

**Marketers: what changes**

You can ask “what patterns do you see in our winning TikToks?” or “what’s visually different between high-CTR and low-CTR ads?” and get structured takes you couldn’t get before. Post-hoc creative analysis and large-batch asset audits become something a small team can pilot in a week.

**Sales: what changes**

Call review improves when you care about slides, faces, and body language, not just transcripts. “Show me where the prospect leaned in or tuned out” becomes answerable. Long, ugly RFPs and security questionnaires digest faster when you throw PDFs and screenshots at Gemini. Back-office heavy lifting like RFP compliance, contract comparisons, and video call analytics stops being a one-off hero project and becomes something you can realistically wire into the normal tooling stack. Prep work like “summarize this sixty-minute discovery call plus whitepaper into a one-pager for my next meeting” gets easier.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1**

Brand voice, punchy copy, and long-form content strategies are still human-plus-writer-model collaborations. Cold outreach, follow-ups, and objection handling stay with the tool your team prefers for conversational work.


### Customer Support and Ops

**What changes**

Tickets with screenshots become much richer inputs; “cluster these issues by what’s actually broken on-screen” works now. Internal tooling with no API but stable UIs moves from “un-automatable” to “pilot-able” with supervised UI agents. Automated triage and tagging from screenshots become practical—you can get most of the way there before a human ever opens the ticket. Drafted actions in internal admin panels—”here’s the sequence I’d take, confirm?”—are finally worth your time to pilot.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1**

Reply drafting, tone-sensitive conversations, and escalation emails still need empathy and naturalness, which means Claude Sonnet 4.5 or ChatGPT 5.1.


### Executives

**What changes**

You can ask “who’s lying to me, even if politely” in a more systematic way. “Compare the story the deck tells to the raw P&L and KPI tables” becomes a legitimate query. Big mixed packs—board decks plus annexes plus screenshots—become digestible as a single object rather than exercises in cherry-picking. Board pack audits that ask “does the visual story understate risk or overstate progress?” are worth running. Town hall vibe checks over video become possible.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1**

Your own writing—CEO letters, strategy memos, sensitive emails—should stay with the tool that best matches your voice. Use Gemini to analyze, not to speak as you.


### Frontend Engineers

**What changes**

UI state and visual bugs become something the model can see, not infer from logs alone. Design system migrations can be partially driven by visual matches, not just class names and grep. Visual debugging—”here’s a video of the bug, here’s the repo, find and propose a fix”—stops being heroic. Design QA—”find components that look like the old button and suggest the new one”—stops being a purely manual search and becomes something you can hand off for a first pass.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1 or existing tools**

Everyday component scaffolding, small bug fixes, and simple CSS tweaks are already near-solved with existing tools. The marginal gain from Gemini is small there.


### Backend and Platform Engineers

**What changes**

You can productively say “here’s the whole service—code, configs, runbooks, diagrams—help me reason about it” with less elaborate sharding. Terminal agents are starting to transform into viable assistants you can supervise. Monolith archaeology, untangling old services, migrations, and breaking-change risk analysis move from fantasy to “we should pilot this in a safe environment.” Supervised runbook execution in staging for health checks and multi-step workflows finally clears the bar from “neat demo” to “we should actually try this”—at least for low-risk systems.

**What stays on existing tools**

CRUD endpoints, well-scoped micro-tasks, and simple infra scripts should use the fastest, cheapest model already integrated into your editor. No point getting fancy.


### Designers

**What changes**

The model can now critique, compare, and spot inconsistencies in actual UIs, not just talk about design systems in the abstract. You can feed it screens across devices and ask “where are we off-brand or off-grid?” Design QA and audits—finding spacing, contrast, and alignment issues across many screens—become something you can put in a checklist. Translating visual intent into code-ready descriptions for engineers works better when the model can see the design.

**What stays on Claude Sonnet 4.5/ChatGPT 5.1**

Naming, UX writing, and narrative framing for design reviews still need a writer-focused model.


### Data Analysts

**What changes**

The boundary between data in dashboards and data in documents gets thinner. You can treat screenshots, PDFs, and CSVs as one blob of evidence and ask for conclusions. Quarterly or multi-report analyses can stay inside one context instead of spreading across dozens of little chats. Exploratory analysis that spans dashboards, charts, and docs becomes fluid. “Explain this anomaly using everything in this folder” works.

**What stays on existing tools**

Day-to-day SQL help, notebook work, and “please write the Pandas code” tasks are less about vision and more about tight code feedback loops. Use whatever works for that.


### Video Editors

**What changes**

Logging and first-pass structuring can be largely automated. “Show me all the good hooks in this two-hour recording” becomes answerable. B-roll selection from large unlabeled libraries becomes a search problem, not a memory problem. Rough cuts, highlight selection, and semantic B-roll search all move from tedious to tractable. Turning long footage into candidate timelines you then refine is worth piloting.

**What stays in your hands**

Final pacing, comedic timing, and emotional arc are still yours. Gemini can hand you a skeleton. You own the performance.


### AI Enthusiasts

**What changes**

You can play with agents that use the editor, terminal, and browser together without building the whole harness yourself. Personal desktop automation experiments for dev setup and small admin tasks are worth trying now. Building proof-of-concept workflows where the model touches real tools, not just text, becomes straightforward.

**What stays on cheaper models**

Quick prompts, tiny scripts, and “I just want this one function” should use whatever’s fastest and cheapest for low-stakes experiments.


## The Pattern Across All Job Families

If you zoom out across everything, the pattern is consistent. Gemini 3 is for work you currently do with your eyes and your patience. Claude Sonnet 4.5 and ChatGPT 5.1 are for work you do with your voice and your keyboard. A simple routing question each team can ask: where are we stuck watching, scrolling, clicking, and reading for hours just to understand what’s going on?

Those are your first Gemini 3 candidates. Everything else can stay where it is for now.


## Where Gemini 3 Is Not Worth the Migration (Yet)

There’s real cost in moving workflows: new prompts, new glue code, new mental models. If a workflow is already “chat-saturated” and text-only—emails, PRDs, small code snippets, basic SQL—you probably shouldn’t move it just because Gemini is new and shiny.

If you find yourself swapping out ChatGPT 5.1 or Claude Sonnet 4.5 for Gemini on a Jira ticket grooming bot or a one-page weekly summary, you’re almost certainly doing change for its own sake.

Use Gemini 3 where the bottleneck is eyes and patience: video, screens, and big mixed blobs of code, docs, and screenshots. Leave everything else on the tools that are already working until you have a concrete reason to switch.


## Economics and Constraints

Be explicit about economics. Gemini 3 is a high-bandwidth engine; it tends to cost more in tokens and latency than a flash model and sometimes more than ChatGPT 5.1 or Claude Sonnet 4.5. Use it where the value of seeing and doing—screens, video, whole systems—is big enough to pay for that. Everywhere else, cheaper and simpler is still the right answer.

The ROI calculation is straightforward: if you’re replacing three hours of a designer manually auditing screens with ten minutes of Gemini plus twenty minutes of human review, the token cost is noise. If you’re using Gemini to summarize a five-paragraph email, you’re burning money for no reason.


## What You Should Actually Do

First, stop testing Gemini 3 by writing emails and summarizing documents. If your lived experience with these models is biased toward light coding, quick summaries, and everyday chat, these are exactly the areas where Gemini 3’s advantage is least visible. If you poke around in chat for an hour and conclude it’s not that different, you’re not wrong. You’re looking in the wrong place. Don’t judge Gemini 3 on your first ten prompts. Ask yourself: does this give me the ability to imagine accelerating work that used to be off limits?

Second, explicitly charter an AI platform group if you don’t have one. Once you accept that some tasks go to Gemini, some to Claude Sonnet 4.5, some to ChatGPT 5.1, someone has to maintain that. Who owns the prompts? Who owns the tools and artifacts? Who teaches teams how to work with these different layers? This is part software engineering, part product management, part platform team.

Give them a clear scope:

- **Routing:** decide which workflows go to Gemini vs Claude Sonnet 4.5 vs ChatGPT 5.1 and keep that map up to date.
- **Supervision:** define how artifacts are reviewed, what “approval” looks like, and what gets logged.
- **Education:** build shared patterns and prompts so every team doesn’t reinvent the wheel.

We’re still evolving what that role means, but if you think one staff engineer who’s a champion on AI can just do this, you’re probably underinvested. Give them a charter big enough to evolve the impact of AI across the organization.

Loop in security, data, and IT early on anything agentic. They’re the ones who will bless—or quietly kill—workflows that touch terminals, production UIs, or sensitive docs. Give them visibility into the routing rules and the supervision surfaces (artifacts, diffs, logs) and treat them as design partners for guardrails rather than last-minute gatekeepers.

Also: don’t rip out what already works. Keep Copilot or Cursor in your editors, keep your warehouse and BI stack as the source of truth. Gemini is a new engine you route certain workloads to, not a mandate to rebuild your whole toolchain.

Third, remember that your intuitions about any model from here on out are almost certainly incorrect if you only test chat. The most interesting workflows from here won’t be better chat. They’ll be places you previously wrote off as “too visual,” “too messy,” or “too big” for AI to touch at all.

The unit of strategy is no longer the model. It’s the routing layer, the specification layer, and the review layer. Build those well, and the models will keep getting better underneath you. Your job is to redesign the work. The models are just the engines.

[![](https://substackcdn.com/image/fetch/$s_!Kif7!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2fb369e8-8e26-482d-9ee9-9935212afb8d_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Kif7!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2fb369e8-8e26-482d-9ee9-9935212afb8d_1024x1024.png)
