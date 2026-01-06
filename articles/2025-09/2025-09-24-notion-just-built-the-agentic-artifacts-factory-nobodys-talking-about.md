---
title: "Notion Just Built the Agentic Artifacts Factory Nobody’s Talking About"
author: "Nate Jones"
published: 2025-09-24
url: https://natesnewsletter.substack.com/p/million-dollar-workflows-in-10-minutes
audience: everyone
scraped_at: 2026-01-05 19:17:09
---

In six months, AI agents have gone from speculative tech to must-haves.

And Notion AI just gave everyone the key to managing their own team of custom agents for $20 a month.

And honestly, you can spin up the prompts to run this team in just a few minutes. Notion isn’t really admitting this, but the key to the magic is their ability to combine smart AI agents with lots of tools to operate against your data.

Work is evolving so fast it sometimes makes me breathless. I just got done writing about [how we’re evolving work into AI artifacts a few weeks ago](https://natesnewsletter.substack.com/p/the-new-ai-operating-system-of-workgoodbye?r=1z4sm5)—artifacts are interactive tools that you can create using a prompt in Claude or ChatGPT.

Well, now you can create ENTIRE WORKFLOWS and run them using AI agents in Notion AI. It’s not just one artifact. It’s a whole assembly line. That’s how fast things are moving.

These aren’t simple automations. I’m talking about million dollar pieces of value. Agents that understand context, make decisions, check their own work, and operate across your entire knowledge base for up to 10-20 minutes at a time. They can turn meeting notes into PRDs, act as an interview coach and score your interview responses against custom scoring rubrics, evaluate prompt variants and track them for you, generate task backlogs—whatever repetitive knowledge work is eating your time.

These prompts might seem complex, but I’m gonna show you how easy they are to create. You can use ChatGPT-5 to build prompts to do this with natural language. No code. No API wrangling. Just clear, structured instructions about what you want done. These agents need precision, but ChatGPT-5 is well-equipped to provide that precision and I’m here to give you all the principles and prompt examples along the way.

After hammering on this since launch, I’ve figured out the patterns that work.

- 8 principles that turn wishful instructions into production systems
- I built 3 complete agent templates you can steal

  - You’ll get links to the Notion pages themselves
  - Plus a video breakdown
  - Plus the prompts I used to create the pages
  - These are valuable workflows—they cost millions to run at most companies
- I also built you a master prompt template you can use for other workflows
- And I laid out where Notion does and doesn’t work well (it’s not perfect!)

The future of work isn’t about AI replacing us. It’s about every knowledge worker commanding their own team of specialized agents. That future isn’t in five years. It’s available right now, for about one Netflix per month.

Let me show you exactly how to build your first AI work engine, and why the people who figure this out today will have massive leverage over everyone still copying and pasting from ChatGPT tomorrow.

Every knowledge worker is about to become an AI systems architect. They just don’t know it yet. The good news is it’s really easy with a little bit of LLM help.

The gap between “AI user” and “AI builder” just collapsed to zero. For twenty dollars.

Documents are dead, but AI workflows are exploding to life. Hop aboard—it’s tons of fun!


# **Notion Just Built the Agentic Artifacts Factory Nobody’s Talking About**

*Why custom AI agents are about to transform how every knowledge worker operates*

---


## The Opportunity Most People Are Missing

I spent the last few days hammering on Notion’s new AI agents, and I’m going to tell you something their marketing team won’t: they accidentally built the most accessible custom AI agent platform on the market.

They keep talking about it as if it’s for Notion users. It’s not. It’s for all of us. And almost nobody realizes it yet.

If you’re hunting for a job right now, this is your secret weapon for standing out. I’ll show you how to build an interview coach that scores your answers in real-time. If you’re an AI builder, this is how you prototype agent workflows without writing code. And if you’re a PM, engineer, or marketer trying to keep up with AI transformation, this is the bridge between where work is today and where it’s heading tomorrow.

The shift I’m about to describe isn’t coming in five years. It’s happening right now, and the people who understand it first will have a massive advantage.


## Understanding Agentic Artifacts

Here’s what most people miss about AI: we’re moving from a world where we write documents to a world where we create living artifacts that AI can operate on.

Think about the difference between a static PRD sitting in Google Docs versus a PRD that’s actually a database where AI can check completion status, update risk assessments, and automatically generate tasks. The first is a document. The second is what I call an agentic artifact - something designed from the ground up to be both human-readable and agent-operable.

This isn’t about making prettier documents. It’s about fundamentally rethinking how work gets structured. When I create a meeting notes database in Notion now, I’m not just organizing information. I’m creating a substrate that agents can traverse, update, and act upon autonomously. The artifact becomes the interface between human intent and agent execution.

The traditional document is dead. What’s replacing it is something far more interesting: structured data that agents can manipulate while humans supervise. And this changes everything about how we think about knowledge work.


## What Notion 3.0 Actually Built

Notion didn’t call their release “custom AI agents,” but that’s exactly what they built. Their AI can now perform autonomous work across multiple steps, running for up to 20 minutes (though in my testing, 5-10 minutes was more typical).

What makes this powerful isn’t just the AI - it’s how Notion married databases, page permissions, and AI together. The system now has granular database row permissions, meaning AI can update specific rows without touching everything else. It’s using MCP (Model Context Protocol) connectors to pull in data from Gmail, Google Drive, Linear, and GitHub.

But here’s what really matters: you control all of this through natural language instructions, not code. You’re essentially programming agent behavior through detailed prompts. The barrier to entry just dropped from “knows Python” to “can write clear instructions.”

They’re positioning this as a way to save money by consolidating AI tools, which is smart marketing. But what they’ve actually built is a platform where any knowledge worker can create custom agents that operate on their data. That’s a much bigger deal than they’re letting on.


## Strengths and Weaknesses

Let me be clear about what works and what doesn’t, because Notion’s marketing won’t tell you the painful parts.

**What Works:** The agent’s ability to create and modify complex database structures is genuinely impressive. I built an interview coaching system with scoring rubrics in minutes. The meeting-to-PRD pipeline I created would have taken days of manual work - it took about two minutes to generate once I had the right prompt. The integration with external tools through MCP means you can pull in real data, not just shuffle existing information around.

**What’s Painful:** This system is incredibly prompt-dependent. Casual instructions like “make a database for this” rarely work well. You need structured, specific prompting that tells the agent exactly where to work, what done looks like, and how to handle edge cases. The learning curve isn’t in the technology - it’s in learning to think like an agent orchestrator.

Performance can be inconsistent. While Notion claims 20-minute execution times, I found 5-10 minutes was easy to get, and incomplete results were relatively common on first run unless I got obsessive about prompting. The agent also tends toward token efficiency, doing less than expected unless you explicitly define quality checks and completion criteria.

Most frustrating: error messages are often opaque. When something fails, you’re left guessing whether it’s a permissions issue, a prompt problem, or a system limitation. This makes debugging your agent workflows an exercise in patient experimentation.


## Eight Principles for Agent Prompting

After digging in a fair bit since Notion AI was released, I’ve realized that there’s no escaping some core principles of good agentic prompting. This model does not like wishy washy prompts. Through practice, I identified eight principles that separate functional agent prompts from wishful thinking. These aren’t Notion-specific - they’re rules for the future of working with AI agents on any platform.

**1. Lock down the scope like you’re containing a hazard**

The first thing you learn the hard way is that agents will interpret “work on my stuff” as broadly as possible. I once asked an agent to “organize my meeting notes” and watched it start editing pages from three months ago. Now I always specify: “Operate only on this page and its direct subpages, touching only items created or modified in the last 24 hours.”

The temporal boundary is crucial. Without it, agents will helpfully “fix” historical data, breaking references and confusing your entire team. Think of scope definition as drawing a fence around a construction site - you want the work happening inside the fence, not randomly across the neighborhood.

I’ve found the sweet spot is usually 24-48 hours for most workflows, though some batch operations might need a week. The key is being explicit about both spatial boundaries (which pages) and temporal ones (how recent).

**2. Define “done” with receipt confirmation**

Agents need closure, and so do you. The biggest source of frustration I encountered was not knowing whether an agent had finished, failed, or was still thinking. Now every prompt I write includes this instruction: “When finished, append exactly one line at the bottom: OK - [what you accomplished]. If blocked, append: BLOCKED - [specific reason].”

This simple pattern transforms vague AI behavior into clear communication. You glance at the page and immediately know the status. No more wondering if the agent is still processing or if it silently failed ten minutes ago.

The receipt also becomes valuable documentation. When you run the same agent weekly, those receipts create a natural log of what changed over time. I’ve caught data quality issues just by noticing the receipt said “3 items processed” when it usually says “8 items processed.”

**3. Structure everything as tables before text**

This was my biggest mental shift. My instinct was to have agents write documents, but documents are terrible for validation and iteration. Tables, on the other hand, are structured, queryable, and easy to validate.

Now I design workflows where agents first populate database fields - title, summary, metrics, status - and only after all validation passes do they render that data into readable text. This approach catches errors before they become embedded in paragraphs of prose.

For example, when converting meeting notes to PRDs, the agent first creates database rows with fields for “Problem Statement,” “Success Metrics,” and “Non-Goals.” Each field can be individually validated. Only after checks pass does it create the formatted PRD document (optionally, if you ask it). This two-phase approach - structured data first, formatted output second - prevents the kind of hallucination that’s hard to spot in flowing text.

**4. Build quality gates that actually gate**

Without explicit quality checks, agents optimize for completion, not quality. They’ll mark tasks done that are barely started. The solution is building gates that must be passed before anything is marked complete.

Here’s what actually works: specific, measurable criteria. Instead of “write a good cover letter,” I specify: “Length must be 180-220 words. Must include the company name and role. Must contain at least one quantified achievement from the resume. Must include one specific initiative you’d pursue in the first 90 days. Cannot use these words: innovative, passionate, synergy, leverage, cutting-edge.”

Yes this is work to think about, and ChatGPT-5 can help here by using best practice. But the detail is crucial to get it right.

The banned words list is particularly powerful. It forces the agent away from generic AI-speak and toward specific, concrete language. I maintain a running list of overused AI phrases and add to it whenever I spot new patterns.

The key insight: make the agent fail rather than guess. If it can’t find a required element, it should mark the item as incomplete and tell you what’s missing, not make something up.

**5. Prevent duplication with explicit rules**

Agents have no memory between runs unless you build it in. Run the same prompt twice and you’ll get duplicate entries. This clutters your workspace and makes it impossible to track what’s actually new.

The solution is simple but must be explicit: “If an item with the same title and type exists from the last 10 minutes, update it instead of creating a new one. Increment the version number only if you make material changes.”

I learned to think about timing windows carefully. Too short (like 1 minute) and legitimate re-runs create duplicates. Too long (like 24 hours) and you can’t iterate quickly. Ten minutes is my default for most interactive workflows.

The version numbering becomes crucial for audit trails. When something breaks, you can see exactly which version introduced the problem. It’s also helpful for stakeholders who want to know if a document has been updated since they last reviewed it.

**6. Create audit trails before you need them**

The first time an agent corrupts important data, you’ll wish you had logs. Now I build them in from the start. Every agent maintains a simple Run Log table: timestamp, items processed, changes made, warnings, and links to modified content.

This isn’t just for debugging. These logs become valuable analytics. I can see patterns like “PRD generation takes longer on Mondays” (more meeting notes to process) or “Customer feedback processing peaks after our Thursday customer success calls.”

The log should be lightweight - you’re not building a surveillance system. But having even basic tracking means you can answer questions like “When did this change?” or “How many items did we process last month?” without detective work.

**7. Write in absolutes, not suggestions**

Agents interpret vagueness as permission to improvise. “Add several examples” becomes anywhere from 2 to 15. “Make it concise” could mean 50 words or 500. This variability makes outputs unpredictable and breaks downstream processes.

Instead, I write with newspaper-like precision: “Create exactly 6 questions: 2 behavioral, 3 technical, 1 culture fit. Each answer must be 75-100 words. Include one specific metric in each technical answer.”

This extends to style instructions too. Rather than “write professionally,” I specify: “Use active voice. Start sentences with verbs where possible. One idea per sentence. No sentences over 20 words.” The result is consistent, predictable output that doesn’t require human editing.

**8. Never allow invented facts**

The most dangerous agent behavior is confident fabrication. An agent will happily invent customer quotes, metric improvements, or technical specifications if not explicitly prevented.

My rule is REAL clear: “If information is not found in the source data, insert [TK-confirm] and mark the item as incomplete. Do not infer, estimate, or create placeholder data.” The [TK-confirm] marker is an old editorial notation that stands out visually and is easy to search for.

This principle extends to calculations and analysis. If the agent is computing metrics, I require it to show the source numbers and calculation method. If it’s making a claim about performance, it must cite the specific data point. No exceptions.

The result is outputs I can trust. Yes, they sometimes have [TK-confirm] markers that require human input. But that’s infinitely better than plausible-sounding fiction that makes it into production.


## Master Template Prompt Structure

Here’s the complete template structure I use for each agent. You can scan through here (and watch the video) to quickly see how I apply each of the 8 principles above in this prompt structure. You can copy and paste this with minor alterations to get a bunch of agents running for you in a few minutes.

```
ROLE
You are a Notion Agent that TAKES ACTIONS, not explanations.
Work ONLY on this page (”[YOUR PAGE NAME]”) and its sub-pages.

FINISH LINE
When finished, add ONE line at the bottom of this page:
OK — [short receipt of what you did].
If blocked, add ONE line:
BLOCKED — [specific reason].

SCOPE
• Only touch items I created or edited in the last [N] hours.
• Never overwrite non-empty fields unless incrementing Version.

DATA MODEL (create if missing)
• [Table Name]: [Field1] (type), [Field2] (type), Status (select), Version (number), Last Run (date)
• Run Log: Run At (date/time), Items Changed (number), Warnings (text), Links (text)

TASKS
1. Find up to [X] items that need work based on [criteria]
2. For each item:
   • Draft content in table fields
   • Run quality checks (see below)
   • If all pass, set Status = “Ready”
   • If any fail, set Status = “Needs Fix” and note why

QUALITY CHECKS
• Length is [X-Y] words
• Includes [required element]
• Contains at least one [specific thing]
• Avoids [list of banned words]
• If info is missing, insert [TK-confirm]

DUPLICATES & VERSIONS
• If an item with the same [identifier] exists from the last [N] minutes, update it
• Increment Version only on material changes
• Set Last Run = today

LOGGING
• Add one row in Run Log with timestamp, count of changes, any warnings
```


## Three Production-Ready Agents


### The Interview Coach ([Notion Page Here](https://product-templates.notion.site/Notion-interview-coach-2775a2ccb52680a1ae44c519c970f664))

This agent builds a complete interview preparation system. It generates behavioral and technical questions based on a job description, creates model answers that incorporate your actual experience, and scores your practice responses against a four-point rubric. The scoring isn’t arbitrary - it evaluates clarity, specificity, quantified impact, and STAR structure. When you practice answering questions, it identifies exactly what’s weak (rambling structure, missing metrics, unverifiable claims) and provides specific feedback on how to improve. The system maintains a scorecard showing your progress across multiple practice sessions, highlighting pattern weaknesses you need to address.

```
ROLE
You are a Notion Interview Coach. Execute actions; do not print examples or code. Operate ONLY inside this page (”Interview Coach”) and its child pages.

OUTPUT POLICY
No explanations. After actions, append ONE final line at the bottom of this page:
OK — {N} questions prepared; {M} answers scored; scorecard updated.
If blocked, append ONE line:
BLOCKED — [reason].

SCOPE & SAFETY
- Touch only items created/updated in the last 24 hours on this page.
- Never overwrite non-empty fields except when incrementing Version.
- Never invent achievements; if a claim isn’t in Candidate Evidence, note [TK-confirm] in Feedback.

DATA MODEL (create inline if missing)
1) Interviews (DB)
   - Title (title) -> “{Role} @ {Company}”
   - Company (text)
   - Role (text)
   - JD Snippet (rich text)
   - Candidate Evidence (rich text) -> bullets the user provides
   - Status (select: Setup, Practice, Scored)
   - Date (date)
   - Version (number, default 1)

2) Questions (DB)
   - Interview (relation -> Interviews)
   - Question (title)
   - Category (select: Behavioral, Systems, Metrics, Values)
   - Model Answer (rich text) -> coach target (3-5 bullets)
   - My Answer (rich text) -> user types here
   - Score (number) -> 0-4
   - Feedback (rich text) -> concrete fixes
   - Red Flags (rich text) -> e.g., unverifiable claim
   - Pass? (checkbox)

3) Rubric (DB)
   - Criterion (title) -> Clarity, Specificity, Impact, Structure
   - Level 1-4 (rich text) -> brief descriptors per level
   - Weight (number) -> default 1

4) Run Log (DB)
   - Run At (date/time)
   - Questions Prepared (number)
   - Answers Scored (number)
   - Links (rich text)
   - Warnings (rich text)

SEED (only if Interviews is empty)
Create one Interview row:
- Title: “PM, AI Workflows @ Acme”
- Company: Acme
- Role: Product Manager, AI Workflows
- JD Snippet: “Own roadmap for AI-powered internal tools. Must-haves: prompt/eval design, SQL basics, experiment design. Success = adoption and measurable time saved.”
- Candidate Evidence: “Reduced manual review time 28%; shipped prompt patterns for ops macros; cut dispute TAT 72h→36h; basic SQL; launched dashboarding.”
- Status: Setup
- Date: today

SEED RUBRIC (only if Rubric is empty)
Create four rows:
- Clarity: L1 “unclear/rambling”; L2 “some structure”; L3 “clear main point”; L4 “crisp, ordered”; Weight 1
- Specificity: L1 “generic”; L2 “light detail”; L3 “precise steps”; L4 “names tools/data/owners”; Weight 1
- Impact: L1 “no result”; L2 “implied”; L3 “one metric/result”; L4 “metric + why it mattered”; Weight 1
- Structure: L1 “off STAR”; L2 “partial STAR”; L3 “STAR present”; L4 “tight STAR w/ trade-offs”; Weight 1

TASKS (batch ≤ 1 interview per run)
A) PREP QUESTIONS
For the most recently edited Interview with Status in {Setup, Practice}:
- Create or refresh exactly 6 Questions linked to it:
  1-2 Behavioral (ownership/conflict/learning)
  3-4 Systems (design an agentic workflow; eval/guardrails)
  5 Metrics (define success; acceptance tests)
  6 Values (disagree & commit; working with design/eng)
- For each, write a concise Model Answer (3-5 bullets, ≤100 words) that demonstrates a strong response using the Candidate Evidence where relevant.
- Do not fill “My Answer”.

B) SCORE ANSWERS (only if user has started typing)
For any Question with non-empty “My Answer” updated in last 24h:
- Score 0-4 for each Rubric criterion using Level descriptors; set overall Score = round(avg of four).
- Write Feedback as 3 bullets: (1) what’s strong, (2) the single most important fix, (3) one specific addition.
- If “My Answer” includes results not in Candidate Evidence, add Red Flags with [TK-confirm].
- Pass? = true if overall Score ≥ 3 AND a numeric token exists.

C) PUBLISH SCORECARD
Create/update a child page “Scorecard — {Date}”:
- Summary at top: Company, Role, total answered, avg Score.
- “Top 3 Fixes” callout (aggregate from Feedback).
- A table view of Questions (Question, Category, Score, Pass?, link).

D) STATE & VERSION
- If at least one Question was scored: set Interview.Status = Scored, increment Version by 1.
- Else set Interview.Status = Practice.

E) LOGGING
- Add Run Log entry with counts and links to Interview page and Scorecard.

FINAL OUTPUT
Append ONE line to the bottom of this page:
OK — {N} questions prepared; {M} answers scored; scorecard updated.
```


### The Prompt Evaluation System ([Notion Page Here](https://product-templates.notion.site/prompt-and-model-eval-harness-2775a2ccb526800fbbdfe4101e98e41e?source=copy_link))

This agent solves a problem every AI team faces: prompt regression. You tweak a prompt to fix one issue and break three others. This system treats prompts like code that needs testing. You define evaluation rules (must include metrics, must avoid certain phrases, must be under 200 words), and the agent runs your prompts through these tests, scoring them on a 0-100 scale. It maintains variant tracking so you can see how v2-temperature-0.3 performs compared to v1-baseline. Failed checks are explicitly logged with reasons, not just pass/fail. Over time, you build a library of tested, scored prompts with known performance characteristics rather than a folder of random text files.

```
ROLE
You are a Notion Agent that turns prompt experiments into evaluated, linked records. Execute actions; do not print code. Operate ONLY inside this page (”Eval Lab”) and its child pages.

SCOPE & SAFETY
- Touch only items created/updated in the last 2 hours in this page.
- Never overwrite non-empty fields; increment Version when you materially change a Draft.
- If required databases are missing, create them inline on this page.

DATA MODEL (create if missing)
1) Experiments (inline DB)
   - Title (title) -> short name
   - Prompt (rich text)
   - Input (rich text) -> test fixture or context
   - Variant Tag (text) -> e.g., v1, v2-temp0.2
   - Status (select: Proposed, Run, Scored)
   - Created (created time)

2) Results (inline DB)
   - Experiment (relation -> Experiments)
   - Output (rich text)
   - Pass/Fail (select: Pass, Fail)
   - Fails (rich text) -> which checks failed
   - Score (number) -> 0-100 aggregate
   - Version (number, default 1)
   - Run At (date)

3) Eval Rules (inline DB)
   - Rule (title) -> e.g., “Has exactly 1 metric”
   - Type (select: contains, regex, length, must-include, must-exclude)
   - Pattern/Value (rich text)
   - Weight (number, 1-5) -> importance

4) Run Log (inline DB)
   - Run At (date/time)
   - Experiments Processed (number)
   - Results Written (number)
   - Warnings (rich text)
   - Links (rich text)

SEED RULES (only if Eval Rules empty)
Create 5 rules:
1) Type=must-include, Pattern=”company” (Weight 3)
2) Type=regex, Pattern=\b(\d+(\.\d+)?)(%|x|k|m|hours?|days?)\b (Weight 4)
3) Type=length, Pattern=”min:80,max:220” (Weight 2)
4) Type=must-exclude, Pattern=”innovative|passionate|cutting-edge|synergy|leverage” (Weight 2)
5) Type=contains, Pattern=”initiative” (Weight 3)

TASKS (batch <= 10 experiments)
For each Experiments row with Status in {Proposed, Run} edited in last 2 hours:
1) Produce one Output using Prompt + Input (use low creativity, deterministic tone).
2) Evaluate against Eval Rules:
   - For each rule, compute pass/fail.
   - Score = 100 * (sum of passed weights / sum of all weights).
   - Build Fails list describing any violations (cite rule names).
3) Write/Update a Results row (linked to this Experiment):
   - Output, Pass/Fail (Pass if Score≥80), Fails, Score, Version (increment if changed), Run At=now.
4) If at least one Result exists: set Experiment.Status=”Scored”; else set “Run”.

ACCEPTANCE CHECKS (before saving a Result as final)
- Output must be ≤ 300 words.
- If Output makes a factual claim not in Input, replace with “[TK-confirm]” and mark Fail with reason “unverifiable”.
- If regex rule exists for metric and none found, mark Fail.

PUBLISH
Create/refresh a child page: “Scorecard — {today}”
- Table with Experiments (Title, Variant Tag, Status) and their latest Results (Score, Pass/Fail).
- A “Top 3” callout summarizing highest scores with links.

LOGGING
Add a Run Log row with counts, warnings (if any), and links to Scorecard and first/last Result updated.

FINAL OUTPUT
Append exactly one line to the bottom of this page:
OK — {X} experiments scored; {Y} results written.
```


### The Meeting-to-PRD Pipeline ([Notion Page Here](https://product-templates.notion.site/meeting-notes-prd-backlog-2775a2ccb5268097bc03ee5e68b95166?source=copy_link))

This agent addresses the universal problem of meeting notes dying in notebooks. It ingests raw meeting notes and transforms them into structured PRDs with problem statements, success metrics, non-goals, risk matrices, and evaluation plans. But it doesn’t stop there - it generates a task backlog with specific work items for engineering, design, data, and launch teams. Each PRD must pass acceptance checks: quantified success metrics with timelines, explicit non-goals to prevent scope creep, and evaluation plans with red flags identified. Tasks are automatically categorized and linked back to their source PRD. What used to take a PM days of documentation work happens in minutes, and the output is consistently structured.

```
ROLE
You are a Notion Agent that converts fresh meeting notes into a PRD and a linked task backlog. Execute actions; keep changes scoped to this page (”Product Hub”) and child pages.

SCOPE & SAFETY
- Only process Meetings updated in the last 24 hours with Status=”Needs PRD”.
- Do not overwrite existing PRDs; create new with Versioning.
- If required databases are missing, create them inline.

DATA MODEL (create if missing)
1) Meetings (inline DB)
   - Title (title)
   - Notes (rich text)
   - Decision Owner (people)
   - Status (select: Notes, Needs PRD, PRD Created)
   - Date (date)

2) PRDs (inline DB)
   - Title (title)
   - Problem (rich text)
   - Users & Use Cases (rich text)
   - Success Metrics (rich text) -> 2-4 concrete, falsifiable metrics
   - Non-Goals (rich text)
   - Risks & Mitigations (rich text)
   - Eval Plan (rich text) -> eval data, acceptance tests, red flags
   - Version (number, default 1)
   - Source Meeting (relation -> Meetings)
   - Status (select: Draft, Ready for Review, Approved)

3) Tasks (inline DB)
   - Title (title)
   - Type (select: Design, Backend, Data, Eval, Launch)
   - PRD (relation -> PRDs)
   - Owner (people)
   - Due (date)
   - State (select: Todo, Doing, Done)

4) Run Log (inline DB)
   - Run At (date/time)
   - Meetings Processed (number)
   - PRDs Created (number)
   - Tasks Created (number)
   - Links (rich text)
   - Warnings (rich text)

TASKS (batch <= 3 meetings)
For each Meeting with Status=”Needs PRD” in last 24h:
1) Draft a PRD:
   - Problem: 1-3 paragraphs; avoid solution language.
   - Users & Use Cases: bulleted; include 1 “edge” case.
   - Success Metrics: ≥2 metrics with target & timing (e.g., “Reduce TAT from 48h→12h in 60 days”).
   - Non-Goals: 3-5 bullets that explicitly say what we will NOT do.
   - Risks & Mitigations: at least 3 paired items.
   - Eval Plan: acceptance tests, offline vs online eval, red flags (brand/legal).
   - Link to Source Meeting; set Status=”Draft”.
2) Create seed Tasks (5-9) linked to the PRD:
   - Must include one Eval task (define test fixtures, golden sets, acceptance rules).
   - Must include one Data task (instrumentation, logging for traces).
   - Must include one Launch task (guardrails, rollback plan).
3) Increment PRD Version if regenerating within 2 hours for same meeting.

ACCEPTANCE CHECKS (fail PRD if any fail)
- Success Metrics present with at least one numeric target + timeframe.
- Eval Plan contains both acceptance tests and red flags section.
- Non-Goals present with ≥3 bullets.
If any fail: set PRD.Status=”Draft”, append a callout “PRD Checks Failed: …” listing missing items; DO NOT create tasks.

PUBLISH
Create/refresh a child page: “PRD — {Title} (v{Version})” rendering all sections neatly, with a linked Tasks view filtered to this PRD. Set Meeting.Status=”PRD Created”.

LOGGING
Write a Run Log entry with counts and links to created PRDs and Tasks.

FINAL OUTPUT
Append exactly one line to the bottom of this page:
OK — {N} PRDs drafted; {M} tasks seeded.
```


## Making This Your Own

The real power here isn’t in copying my prompts - it’s in understanding that we’re at an inflection point in how work gets done.

Start by picking one workflow that frustrates you. Maybe it’s turning customer feedback into feature specs. Maybe it’s creating weekly reports from scattered data. Maybe it’s maintaining a content calendar. Whatever it is, that’s your first agent.

Build it simple first. Get it working on a single page with a basic table. Then gradually add sophistication: quality checks, version control, connections to external data. The beauty of this approach is that you’re not committing to a complex system upfront. You’re evolving it as you learn what works.

> Note: If you’re looking for a weakness, here it is. External data needs to be made available for Notion to work. So marketers looking for complex ad analytics could theoretically build something like a custom agent in Notion—as long as the analytics got into Notion so the agent could work. Notion knows this, and this is why they are actively building out their agent connectors via MCP.

Regardless, the bigger picture is this: every knowledge worker is about to become an agent orchestrator. The question isn’t whether this shift happens - it’s whether you’re ahead of it or behind it. The people who figure out how to structure their work for agent operation will have massive leverage over those still treating documents as static artifacts.

This isn’t about Notion specifically. It’s about recognizing that the interface between human creativity and AI execution is shifting from conversation to structured, operational artifacts. Notion just happens to be the first platform that makes this accessible to non-programmers. There will be others, but the principles remain the same.

The companies that figure this out will move at a different speed than their competitors. The individuals who master this will become indispensable. Not because they’re better at using AI chat interfaces, but because they understand how to architect work itself for an agentic world.

Stop thinking about AI as a better search engine or writing assistant. Start thinking about it as an operational layer that can traverse and transform structured work artifacts. That’s the shift that’s actually happening, and now you have the tools to be part of it.

> PS. Looking for more? Check out [my companion piece](https://natesnewsletter.substack.com/p/the-new-ai-operating-system-of-workgoodbye?r=1z4sm5) on building AI artifacts in Claude and OpenAI here.

[![](https://substackcdn.com/image/fetch/$s_!etRk!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3144eed2-01b2-4d2f-8654-c36e14d8c769_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!etRk!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3144eed2-01b2-4d2f-8654-c36e14d8c769_1024x1024.png)
