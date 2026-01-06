---
title: "Most People Talk About Models. Almost Nobody Talks About The Mess You Hand Them."
author: "Nate Jones"
published: 2025-11-20
url: https://natesnewsletter.substack.com/p/the-gemini-3-vs-chatgpt-51-prompting
audience: everyone
scraped_at: 2026-01-05 19:11:28
---

“But WHICH IS BETTER NATE?!” I keep getting asked this about ChatGPT 5.1 vs. Gemini 3, and the correct answer is: “Wrong question.”

The right question is: “What meaningful differences exist between these models that I should account for when working with them?”

Or, simpler: “How the heck do I prompt Gemini 3, and is it different than GPT 5.1?”

Yes, these models are different. Yes, you are gonna have to prompt them differently.

And yes, this guide is ALL about showing you how to do that.

And while I’m aware that Gemini 3 is killing it on benchmarks, I think for our purposes here it’s useful to not worry too much about benchmark scores.

Instead, we can think of 5.1 and Gemini 3 as very strong general-purpose models.

After using them for a few days, the difference between them seems to come down to whether you’re asking the **right model to resolve the right kind of uncertainty.**

Stay with me, that sounded abstract.

Here’s what I mean:

1. One model is happier taking a **messy pile of context**—screenshots, transcripts, logs, videos—and compressing it into structure, as long as you’re very specific about the output you want. That’s Gemini 3.
2. The other is happier taking **clean, organized inputs** and then doing **high-entropy work** on top—reasoning, planning, narrative, multi-step decisions. That’s ChatGPT 5.1.

If you mix those up, the models may do ok, but you probably won’t catch them at their best. ChatGPT 5.1 shipped just over a week ago, and Gemini 3 dropped two days ago. I’ve been running them side-by-side, and the practical difference is not a light switch (“this one can, that one can’t”). It’s more of a dimmer switch, where Gemini 3 has a bright bulb on messy context, and GPT 5.1 has a bright bulb on complex tasks.

Don’t get lost in metaphors, though. isn’t a vibes essay.

It’s a prompting guide with concrete examples and copy-paste templates that shows you how to get better work out of *both* models by understanding what each one is optimized for.

**In this piece, you’ll get:**

- **A simple mental model for picking the right model**

  - Understand when and where to use GPT 5.1 vs. Gemini 3 on work tasks, and a rule of thumb so you actually remember it!
- **How to prompt ChatGPT 5.1**

  - What to **keep** doing, what to **stop** doing, and what to **start** doing
  - Before/after prompts for exec memos, planning docs, and team comms that show how to break big, messy asks into clean, focused steps
- **How to prompt Gemini 3**

  - How to use it as a multimodal “entropy eater” for big piles of mixed-format research (videos, images, spreadsheets, documents).
  - Exactly where to put your instructions in long-context prompts and how to tell it which pieces of content to actually pay attention to.
- **Templates you can copy and paste**

  - Ready-to-use prompt skeletons for both models that you can drop into your system instructions or internal wiki today.
- **Real workflows, not toy examples**

  - Incident analysis (Gemini 3 reads logs + screenshots, 5.1 writes the RCA).
  - Product discovery (Gemini 3 pulls insights from interviews and surveys, 5.1 turns those into PRDs and bets).
  - Board prep (Gemini 3 finds what changed in your spreadsheets and past presentations, 5.1 writes the story).

**Bonus Super Prompt:**

You’ll also get my **GPT 5.1 vs Gemini 3 Prompt Configurator.**

It’s a big helper prompt that asks you a few sharp questions about your task (what you’re trying to do, what materials you have, what output you need) and then writes a **custom, model-specific task prompt**.

I include two detailed examples: one that creates an executive memo prompt for 5.1, and one that creates a research synthesis prompt for Gemini 3 that turns interviews, surveys, support tickets, and screenshots into an organized list of problems.

This is a hands-on article. If you want to stop arguing about benchmarks and start getting more done with the models you already have, this is the guide.

Put on your goggles and gloves, and let’s get into the workshop!


## [Grab the GPT 5.1 vs Gemini 3 Prompt Configurator](https://www.notion.so/product-templates/GPT-5-1-vs-Gemini-3-Prompt-Config-2b15a2ccb52680258d4ddeb8ee63a0ec?source=copy_link)

I built an entropy-aware meta-prompt that generates model-specific task prompts for ChatGPT 5.1 and Gemini 3. Instead of guessing how to structure prompts for each model, you answer a few questions about your task—what you’re trying to do, what your inputs look like (clean data vs messy transcripts, multimodal vs text-only), and what output format you need—and it returns a ready-to-use prompt optimized for the model you’re targeting.

I’ve included two examples to show how it works. The first takes a structured pilot summary and generates an exec-memo prompt for ChatGPT 5.1. The second builds a long-context, multimodal research prompt for Gemini 3 that processes interviews, surveys, support tickets, and screenshots into a structured problem-space map.

> *Note: This prompt is the one you need for working. The prompts you’ll see throughout this article are sample prompts. They’re much lighter, and I’ve opted to put them in line with the text because I think you need to SEE the examples to feel the difference.*

---


# Most People Talk About Models. Almost Nobody Talks About The Mess You Hand Them.

I’ve spent the last couple days running ChatGPT 5.1 and Gemini 3 through their paces, and I need to tell you something that matters more than any benchmark: these models want fundamentally different things from you. One is better at taming messy inputs; the other is better at solving hard, cleanly-framed problems.

This isn’t about which one is “better.” It’s about understanding that when you hand a model the wrong kind of problem, you’re burning tokens and getting mediocre results. When you match the model to the job, you get work that actually ships.

**TL;DR:**

- **Gemini 3 = context entropy specialist:** give it messy multimodal input + tight schemas
- **ChatGPT 5.1 = task entropy specialist:** give it clean inputs + complex jobs
- **Good prompting = decide which entropy you’re lowering yourself, and pick the model accordingly**

Both models are extremely capable general-purpose LLMs. They can each write emails, draft PRDs, refactor code, and summarize documents just fine. What I’m describing here are stable tendencies—the places where they feel unfairly strong or surprisingly brittle when you’re doing non-trivial work. Think “biases at the edge,” not hard capability walls.

Let me explain what I mean, and then I’ll give you the specific prompting patterns that make each model sing.


## The Entropy Problem (And Why You Should Care)

Here’s the thing most people miss about LLMs: every model call has a limited “analysis budget.” It can spend that budget reducing uncertainty in your inputs, or it can spend it solving complex tasks, but doing both at once gets expensive and fragile fast.

There are two kinds of uncertainty that matter:

**Context entropy** is about how messy your inputs are. Are you dumping in logs, screenshots, PDFs, videos, and transcripts all at once? Are there competing signals, irrelevant details, or mixed formats? That’s high context entropy. The model has to spend effort just figuring out what matters.

**Task entropy** is about how open-ended the job is. Vague objectives, competing constraints, multiple stakeholders, unclear success criteria—these force the model to spend tokens deciding what kind of answer you even want before it can generate one.

When both are high simultaneously, you get hallucinations, sprawl, and outputs that sound confident but miss the mark. The model is trying to clean up your mess *and* solve an ambiguous problem *and* write coherently all in one shot. That’s where things break.

**Rule of thumb: lower context entropy when you want the model to do complex thinking; lower task entropy when you’re throwing it a huge messy pile.**

Good prompting is about manually lowering entropy on one side so the model can spend its capacity on the other.

**Example: High Context + High Task Entropy (What Not To Do)**

```
Here are 40 pages of customer interviews, three screenshots from our dashboard,
and a CSV export from HubSpot.

Please analyze everything and tell me how to fix our churn problem. Also give me
ideas for new features and write an email to the CEO summarizing your recommendations.
```

This is asking the model to parse messy, multi-format input (high context entropy), infer what “fix churn” even means (high task entropy), then write an email on top of that. This is exactly where you get confident, fuzzy output that sounds smart and is 20% grounded at best.


## The Real Difference Between ChatGPT 5.1 and Gemini 3

ChatGPT 5.1 and Gemini 3 are optimized at different points in this tradeoff, and once you see it, you can’t unsee it.

Both models can do both jobs, so don’t hear this as a light switch or binary capability. It’s not. I’m talking about a point of emphasis for each model—where they’re easiest to use and most forgiving.

**Gemini 3 is built to eat context entropy.** It wants your messy, multimodal chaos—logs, PDFs, screenshots, video, lengthy transcripts—and turn it into structure. It can also do complex tasks, but this is where it feels unfairly strong. It’s tuned to be concise by default, and Google’s own documentation explicitly tells you to put massive context blocks first and instructions at the end. It’s saying: feed me the universe, but tell me exactly what artifact you want me to produce from it.

**ChatGPT 5.1 is built to handle task entropy.** It wants clean, relatively organized inputs and then you can hand it complex multi-step work: reasoning, planning, narrative development, tool orchestration. It can read long context, but it’s at its best when you don’t make it wade through junk. OpenAI tuned this model to follow instructions precisely, particularly around writing style and structure, which was a major complaint about GPT-4o.

This creates a clear implication for how you work with each.

**Example: Same Problem, Different Model Jobs**

Problem: You want to understand why paid search CAC has quietly crept up over the last two quarters.

**Gemini 3 job:**

```
Here are:
- 6 months of channel performance exports (CSV)
- 12 screenshots of our marketing dashboards
- 10 interview transcripts with our performance marketers

Based on ALL of this, identify 5–7 grounded hypotheses for why paid search CAC increased.

For each hypothesis, output:
- name
- evidence (quote or reference from CSV/dashboard/interview)
- confidence (High/Med/Low)

Return a JSON list.
```

**ChatGPT 5.1 job (using Gemini’s output):**

```
Here is a JSON list of 5–7 CAC hypotheses with evidence and confidence levels.

Turn this into a 2-page executive brief for the CMO:
- Stakes and summary
- 3 key drivers of CAC increase
- 3 recommended changes for the next 90 days
- Risks and trade-offs

Tone: direct, non-defensive, VP-level.
```

Gemini 3 handles context entropy. ChatGPT 5.1 handles task entropy.


## How to Prompt ChatGPT 5.1

**Treat 5.1 like an internal function library for complex, well-defined jobs.** It loves clear roles, specific audiences, and explicit tone instructions. It performs best with curated, relevant context—not giant raw dumps.

**What to keep doing:**

Define role, audience, and tone every time. This is still high-leverage. Be explicit about output structure: sections, headings, bullet counts, JSON schemas. Use modes intentionally—instant for quick edits, thinking for hard reasoning or refactors. Let 5.1 drive the narrative. This model likes to eat problems. Executive memos, product narratives, internal explainer docs—it excels here.

**Example: Good vs Bad Prompt for 5.1 (Exec Memo)**

Bad 5.1 prompt:

```
Here’s a dump of Slack messages from the last incident and some notes from the
SRE team. Write a memo for leadership about what happened and what we should do.
```

Context is messy, task is vague. You’re asking it to be an analyst, investigator, and communications lead at once.

Better 5.1 prompt (after you or another model pre-structures the context):

```
You are Head of Engineering writing to the exec team.

Here is a 1-page structured summary of the outage (timeline, impact, root cause,
and fixes already shipped):
[paste curated summary]

Write a 600–800 word memo with:
1. Brief overview (2 short paragraphs)
2. Timeline (bulleted)
3. Root cause and what we’ve changed
4. 3 clear next steps

Tone: calm, accountable, no spin, written for non-technical executives.
```

Now 5.1 can spend its budget on framing, prioritization, and language, not cleaning up the raw mess.

**What to stop doing:**

Stop dumping huge unfiltered context windows into 5.1. You pay more and dilute the model’s value. Stop hiding the task inside a wall of background. I see this constantly in so-called “big prompts.” You don’t need a page of company lore from the wiki. Just ask for what you want. Stop packing four or five jobs into one prompt. Idea generation is a different task than critique, which is different from selection. Break them out. The model prefers clean inputs.

**Example: Splitting a “Kitchen Sink” Prompt Into 3 Clean Calls**

Instead of this:

```
Here’s our Q2 OKR doc and some notes. Generate new OKRs, critique them,
choose the best ones, and write an email to the team.
```

Break it into three jobs:

**Call 1 – Idea generation:**

```
Here is our Q2 OKR doc and Q3 priorities (1 page).
Generate 10 candidate Q4 OKRs using the same format.
```

**Call 2 – Critique and selection:**

```
Here are 10 candidate OKRs.
Score each 1–10 for clarity, ambition, and measurability.
Recommend a final set of 4–6 with a short justification.
```

**Call 3 – Communication:**

```
Here are the final OKRs we selected.
Draft an internal announcement email to the team (400–600 words, direct, no fluff).
```

Same model, same data, better results because you lowered task entropy in each call.

**What to start doing:**

Codify your most common 5.1 tasks as “functions.” Define reusable patterns with stable formats. If you draft internal memos regularly, create an explicit pattern and invoke it deliberately: “Draft an internal memo using my standard format.” Put it in project instructions if you use it constantly.

Give step plans when you want deliberate thinking. “First ask three clarifying questions, then propose three options, then choose one, then write the doc.” This backfills the model into careful reasoning.

Be explicit about tools. Tell the model what’s available and what constraints apply. Is web search important? Say so upfront.

Constrain verbosity and register. “This needs to be five to seven bullets for a VP audience” helps the model nail both length and language level.

**Example: “Function” Prompt for 5.1 You Can Reuse**

```
You are my internal comms drafter.

Your job: turn structured bullet points into clear internal emails.

INPUT:
- Audience: [e.g. ‘all engineers’, ‘leadership team’]
- Goal: [what I want them to do or understand]
- Key points: [3–7 bullets]

OUTPUT:
- Subject line (3 options)
- Body (250–400 words) in my voice: direct, no corporate filler, assume the
  reader is smart but busy

If the bullets are ambiguous, ask me 3 clarifying questions before you draft.
```

Now you can call this pattern over and over with different bullets, instead of reinventing the prompt each time.


## How to Prompt Gemini 3

**Treat Gemini 3 as your entropy eater for messy, multimodal input.** It’s built for different work.

**What to keep doing:**

Be precise and unambiguous. Gemini 3 responds well to clear goals and output formats. Having structure on output still helps—JSON, tables, standardized tags, whatever you use. Use stepwise reasoning when tasks are complicated. Step one, step two, step three still works.

**Example: Straightforward Structured Task for Gemini 3**

```
You will receive:
- 12 user interview transcripts (B2B buyers)
- A CSV of win/loss reasons from the CRM

Task: Build a ‘Problem Space Map’ for our onboarding experience.

Based ONLY on the data:
- Identify 5–10 distinct user problems
- For each:
  - name
  - 2–3 representative quotes (with interview IDs)
  - frequency estimate (High/Med/Low)
  - severity estimate (High/Med/Low)

Return a markdown table.
```

This is still just clear goal plus clear schema, which works on any LLM—but Gemini 3 can comfortably read all 12 transcripts and the CSV in one shot.

**What to stop doing:**

Stop treating Gemini 3 like it’s “ChatGPT from Google.” Its real edge is multimodal: ingesting video, images, text, and very lengthy context as first-class objects. If you only send short text prompts, you’re not using what makes it different.

Stop putting detailed instructions at the top when you use huge context. Google’s docs are explicit here: put context first, instructions at the end. With long docs, code bases, or videos, the pattern is context up top, then anchor your instructions at the bottom: “Based on the information above, do X.”

Stop assuming Gemini 3 will be verbose by default. It’s tuned to be concise. If you want longer, more narrative answers, you need to say so explicitly.

Stop referring to multimodal inputs vaguely. “See screenshot above” is weak. Instead: “Use image one (funnel dashboard) for conversion rates and image two (checkout screen) for UX issues. Compare them by analyzing drop-off points in the funnel flow.”

**Example: Long-Context, Multimodal Prompt in the Right Shape**

Bad Gemini 3 prompt:

```
Here are two Loom videos of the onboarding flow, plus some screenshots and logs.
What do you think?
```

Better Gemini 3 prompt:

```
You are a UX analyst.

CONTEXT
- Video 1: full onboarding flow on desktop (00:00–04:30)
- Video 2: onboarding flow on mobile (00:00–03:15)
- Image 1: final ‘Success’ screen (desktop)
- Image 2: final ‘Success’ screen (mobile)
- Logs: signup and verification events for the last 10k users

[link or embed these artifacts here]

TASK
Based on ALL of the above, do the following:
1. List the top 5 UX issues that would cause drop-off, referencing specific
   timestamps or images
2. For each issue, include:
   - description
   - where_it_shows_up (e.g. ‘Video 2 @ 01:45’, ‘Image 2’, ‘log field X’)
   - likely_impact (High/Med/Low on completion rate)
3. Keep your answer concise and structured as a JSON list

Do not suggest generic best practices; ground everything in the actual artifacts above.
```

Here, context comes first, the anchored task comes last, and each modality is named and indexed.

**What to start doing:**

Use Gemini 3 as your entropy eater. Give it those giant messy bundles—logs, PDFs, transcripts, multiple videos. Ask it to output structured, grounded artifacts: issue lists, timelines, hypotheses, tables.

Anchor your long-context prompts explicitly. A good pattern: role and global constraints up top, big context blocks in the middle, then at the very end: “Based on the information above, do X in Y schema.”

Specify verbosity and persona every time. “Use a conversational tone, 800 to 1,000 words” or “Return a terse bullet list.” Don’t assume the default will match what you need.

Name and index every modality. “Image one,” “Video two from 1:30 to 2:00,” “CSV columns one through four.” Tell it what to use. You get better retrieval when you’re precise about what matters in the pile.

Use reasoning controls deliberately. Raise thinking level only when you need cross-document synthesis. Keep it low for labeling or pure extraction.

**Example: Gemini 3 as “Entropy Eater” Before 5.1**

Step 1 – Gemini 3:

```
You will receive:
- 30 pages of Slack discussion about last quarter’s roadmap
- The Q3 roadmap doc (Google Doc)
- A CSV of shipped features with adoption metrics

Task: Identify mismatches between what we planned to do and what we actually
shipped and saw adopted.

Based on ALL the information above, output a table with:
- item (feature or initiative)
- planned_status (from roadmap)
- actual_status (from CSV/logs)
- comment (1–2 sentences explaining the mismatch)
```

Step 2 – ChatGPT 5.1:

```
Here is a table of roadmap vs reality mismatches.

Write a 1,000-word honest retro for the product & eng leadership team:
- What patterns you see
- 3–5 root causes
- 3 concrete changes you recommend to how we plan Q1

Tone: direct, non-blaming, focused on learning.
```


## Copy/Paste: Prompt Skeletons

At this point you’ve got the mental model; here are the bare-bones shapes you can actually paste into your system instructions or internal docs.

**Default ChatGPT 5.1 Prompt Shape:**

```
You are [specific role] writing for [specific audience].

Here is [clean, pre-structured context]:
[paste 1–2 pages max]

[Multi-step task definition]:
1. [First step]
2. [Second step]
3. [Third step]

Tone: [specific register and constraints]
Output: [format, length, structure]
```

**Default Gemini 3 Long-Context Prompt Shape:**

```
You are [role with global constraints].

CONTEXT
[Modality 1]: [description and location]
[Modality 2]: [description and location]
[Modality 3]: [description and location]
[paste or link all artifacts here]

TASK
Based on ALL of the information above, do the following:
1. [Specific extraction or synthesis task]
2. [Output format and schema]
3. [Verbosity instruction: concise/conversational/detailed]

Ground everything in the artifacts above. Reference [specific modalities] explicitly.
```


## When to Use Which Model

Use **Gemini 3** when your inputs are chaotic but your task definition can be tight. Examples: “Here’s 50 pages of user feedback, three dashboards, and a CSV. Reduce this to ten grounded problems using this JSON schema, with evidence for each.” You’re saying: use your capacity to find signal in the mess; I’ll keep the job definition narrow.

Use **ChatGPT 5.1** when your inputs are structured but your task is complex. Examples: “Here’s a two-page structured summary of user problems, metrics, and constraints. Turn this into a two-page exec memo with stakes, options, and a recommendation in my voice.” You’re saying: use your capacity to explore the decision space and write; I’ll keep the inputs clean.

**Concrete Scenarios:**

**Incident analysis**

- Gemini 3: ingest logs, stack traces, screenshots, and incident channel transcripts to produce a grounded timeline and candidate root causes
- 5.1: take that structured timeline and write the customer-facing RCA and internal postmortem

**Product discovery**

- Gemini 3: ingest raw interview transcripts, survey exports, and support ticket samples and output a ranked list of problems with evidence
- 5.1: turn that problem list into PRDs, bets, and an internal strategy memo

**Board prep**

- Gemini 3: digest KPI spreadsheets, past board decks, and narrative updates and output the 10 most important changes since last quarter
- 5.1: turn those into a coherent board deck narrative and a speaking script

If you want it in one line: use Gemini 3 to tame the chaos of your inputs, use ChatGPT 5.1 when you’re tackling hard thinking and communication around structured inputs.

---

Both models are genuinely strong. We’re still at the beginning of understanding what Gemini 3 can do, particularly around coding and visualization. But the stable difference I see after a few days of use comes down to entropy: which kind of uncertainty are you asking the model to resolve, and which are you resolving yourself?

The models that win in your workflow aren’t the ones with the best benchmarks. They’re the ones where you’ve matched the entropy profile of the problem to what the model actually wants to eat.

[![](https://substackcdn.com/image/fetch/$s_!gwJ4!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff335390c-d43f-4ceb-a667-930deab1a34b_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!gwJ4!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff335390c-d43f-4ceb-a667-930deab1a34b_1024x1024.png)
