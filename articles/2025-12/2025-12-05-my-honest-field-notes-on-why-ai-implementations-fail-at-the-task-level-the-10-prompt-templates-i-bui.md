---
title: "My honest field notes on why AI implementations fail at the task level + the 10 prompt templates I built to fix it"
author: "Nate Jones"
published: 2025-12-05
url: https://natesnewsletter.substack.com/p/grab-the-10-prompts-i-use-to-decompose
audience: everyone
scraped_at: 2026-01-05 19:10:33
---

*Everyone wants to know which AI to use. It’s the wrong question, and it’s quietly become one of the most expensive mistakes I see.*

*The pattern is always the same. A team picks a model—usually whatever’s newest or whatever IT approved—then throws entire workflows at it. Summarize these interviews. Write this report. Analyze this data. When outputs disappoint, they blame the model, upgrade to something more expensive, and repeat. I’ve seen companies burn through three enterprise contracts in a year this way.*

*Almost nobody tells you this explicitly: AI doesn’t fail at the workflow level. It fails at the task level. And most workflows contain five or six tasks pretending to be one.*

*“Generate a PRD” sounds like one thing. It’s actually customer synthesis, UI analysis, feature design, roadmap alignment, and document construction. Each requires different capabilities. When you throw them all at ChatGPT, you get a document that looks professional and falls apart under scrutiny. Not because the model is bad—because you asked a specialist to be a generalist.*

*McKinsey says 80% of organizations use AI somewhere. BCG says 74% haven’t seen tangible value. It’s not just skills or data quality. In the implementations I see, the deeper gap is that we’re planning at one level of abstraction and executing at another.*

*Here’s what I’ll cover:*

- *The task decomposition framework I use to break workflows into AI-ready pieces—with real examples from regulatory reporting, customer success, and product development*
- *Which models I’ve found work best for which cognitive tasks—not benchmarks, but patterns from dozens of implementations*
- *What multi-model setups actually cost in practice, and why they quietly beat “one model for everything” once you do the math*
- *How to build model intuition through deliberate practice—the skill that separates teams getting value from teams getting frustrated*

*No theory. No benchmarks. Just what I’ve seen work.*


## **[Grab the prompt.](https://www.notion.so/product-templates/Task-Decomposition-and-Model-Selection-A-Prompt-Guide-2bf5a2ccb526806f9abdfe72d4c4cb14?source=copy_link)**

I’ve built a complete task decomposition system you can use immediately. Most people read about frameworks then struggle to apply them. This prompt walks you through breaking any workflow into atomic tasks, identifying cognitive types, and matching model capabilities—no theory required. Copy it, use it today on your worst workflow, and you’ll see exactly why “which model should I use?” is the wrong question. Then I’ll show you why this approach works through real examples.


## **The Framework: Five Types of Cognitive Work**

Most workflows break into five cognitive types requiring fundamentally different capabilities. Think about replying to a complex email: you extract key requests from a noisy thread, synthesize them into a single view, analyze what matters, generate a response, then validate it for accuracy. Five different types of work. In my experience, they often benefit from different tools.

**Extraction**: pulling specific information from unstructured sources—action items from meeting notes, risk factors from contracts, entities from documents. For high-volume structured pulls, I’ve found smaller models work well: Claude Haiku, GPT-4o mini. Fast, cheap, accurate enough. No reason to burn expensive tokens finding phone numbers.

**Synthesis:** combining multiple inputs into a coherent picture. Taking fifty customer interviews and finding the three patterns that matter. When I need to hold massive context—hours of transcripts, hundreds of pages—I’ve had better results with Gemini’s longer context windows. Claude and GPT-4 handle shorter synthesis tasks competitively; the differences show up when inputs get truly large. Your results will vary with prompt design and domain.

**Analysis**: applying logic, calculations, or rules to structured problems. Computing financial ratios, evaluating architectural tradeoffs, determining regulatory compliance. In my deployments, GPT-4 and o1-style reasoning models have been most reliable for multi-step calculations where precision matters. Claude is competitive on many reasoning tasks—some evaluations find it stronger in certain domains—but when a twelve-step calculation needs to be exactly right, I tend to reach for GPT-4 first.

**Generation**: creating new content meeting specific requirements—narratives, documentation, responses. Claude Sonnet and Opus have earned their reputation for voice-consistent long-form writing that holds up across revisions. GPT-4 produces technically correct prose that can read flat without careful prompting. Gemini surprises me with creative outputs but requires more curation. All three produce quality work; in my experience, Claude tends to need less steering on tone.

**Validation**: checking correctness against rules or requirements—verifying calculations, ensuring compliance, catching inconsistencies. I often split this: GPT-4 for hard rule checking, Claude for nuanced review that surfaces business logic problems the rules don’t cover. When stakes are high, I run both.

These are starting points I’ve developed through practice, not universal truths. Models update quarterly. Your domain shapes everything. But matching task types to model strengths beats hoping one tool can handle it all.


## **When $3,100 Beats $1,200**

Fortune 500 financial services company, Q3 2024. They’d bought ChatGPT Enterprise for regulatory reporting—MiFID II compliance, hundreds of rules about trade disclosure with specific thresholds and exceptions. The promise: feed in transaction data, get out quarterly reports.

Six weeks in, their Head of Compliance called the outputs “technically correct but practically useless.”

I watched an analyst work. Four hundred pages of transaction records dumped into ChatGPT with instructions to generate the report. What came back looked perfect. Proper sections, regulatory references, professional formatting. But buried inside were errors that took senior analysts hours to find. The model confused pre-trade and post-trade transparency requirements. It applied wrong calculation thresholds to different instrument types. These weren’t obvious mistakes—they were the kind that slip past review and surface months later when regulators start asking questions.

The Head of Compliance said something I think about constantly: “It knows all the words but doesn’t understand the work.”

We mapped what human analysts actually do. Six distinct steps: cleaning data, classifying transactions, applying calculations, running logic trees by instrument class, generating variance narratives, cross-referencing regulatory updates. Six cognitive tasks with different requirements, collapsed into one prompt and one prayer.

Rebuilt with task decomposition—lightweight models for cleaning, Gemini for classification, GPT-4 for calculations, Claude for narratives—accuracy went from “hours of cleanup” to “minor edits.” Monthly cost tripled from $1,200 to $3,100. Weekly analyst time saved: 60 hours. At $150/hour loaded cost, that’s $36,000 monthly in recovered capacity.

The math worked. But more interesting was *why* it worked: we stopped asking the model to understand compliance and started asking it to do specific things it was actually good at.


## **When Accuracy isn’t Intelligence**

Series B SaaS startup, November 2024. They wanted AI-generated quarterly business reviews. First attempts produced decks full of statistics without meaning. Logins up 27%. Tickets down 12%. Feature requests listed alphabetically.

The problem wasn’t accuracy—every number was correct. The problem was intelligence. When senior CSMs prepare QBRs, they don’t just report that logins increased. They notice that heavy workflow automation combined with ignored analytics means a customer is tactical, not strategic—a retention risk hiding behind good usage numbers. They recognize twelve different support tickets as symptoms of one root cause. They read frustration between the lines of polite feature requests.

The model could count. It couldn’t see.

Different failure than the compliance case. There, the model made precision errors in rule application. Here, it lacked the contextual judgment to know what numbers meant. Same symptom—professional-looking output that missed the point—but different underlying breakdown.

We rebuilt with that distinction in mind. Data aggregation stayed with a lightweight model. Pattern recognition in usage data went to Gemini. Root cause analysis of tickets went to GPT-4. Narrative construction went to Claude. Each model handled what it handled well. The final deck required twenty minutes of customization instead of a full rewrite.


## **Building Intuition: Why You Can’t Skip the Practice**

Here’s something uncomfortable: you can’t read your way to model intuition. You develop it by doing the work.

Tech company, December 2024. Training product managers on AI-assisted requirements. Week one, I presented the framework. Everyone nodded. Everyone went back to using ChatGPT for everything. Week two, I made them track results. Average output quality: 3.2 out of 5. Week three, paired work.

Two PMs, same requirements task. PM #1 used ChatGPT throughout—forty-five minutes, extensive revisions needed. PM #2 decomposed the work: customer quotes to one model, technical constraints to another, user stories to a third, acceptance criteria to a fourth. Thirty-five minutes, minimal revisions.

But PM #2 couldn’t have made those routing decisions on day one. The choices came from weeks of feeding the same tasks to different models and observing what happened. Noticing that one model kept consistent formatting across revisions while another drifted. Seeing that one handled ambiguous inputs gracefully while another demanded precision. That kind of knowledge doesn’t transfer through documentation. It transfers through reps.

Most teams would save more by spending a few hundred dollars on deliberate experiments than they lose rewriting mediocre first drafts for months.


## **What Multi-Model Actually Costs**

ChatGPT Plus at $20/month is fine for casual use. It’s not a production strategy.

Teams running production workflows typically spend $110-220 monthly across multiple tools: small models for extraction, reasoning models for analysis, Claude for generation, specialized tools for specific needs. That’s five to ten times the basic subscription. It’s also less than one hour of knowledge worker compensation. The question isn’t whether you can afford multiple models. It’s whether you can afford outputs that need constant cleanup.


## **A Few Edge Cases Worth Knowing**

Once you’re routing by cognitive type, a few situational patterns emerge. Multimodal work—especially long video and audio—is where I’ve seen Gemini pull ahead in my projects. Massive context windows, same story: Gemini’s million-token capacity handles inputs that choke other models. Agentic workflows are more nuanced; Claude handles structured, code-centric automations well, while ChatGPT’s agent mode has worked better for me on broad SaaS integrations. Predictability matters in regulated environments, and Claude models tend to show consistent behavior across edge cases—though predictability comes as much from prompt discipline as model choice.

None of this is permanent. These are observations from deployments over the past year, not laws of physics.


## **The Shift**

Portkey’s analysis of two trillion tokens found that advanced users increasingly route across multiple providers, cutting costs 30-40% while improving quality. The pattern holds: treating AI like a toolkit beats treating it like a vendor relationship.

But the real shift is conceptual. We’ve been approaching AI like enterprise software—standardize on one solution, train everyone the same way, measure adoption. That mental model is why Gartner forecasts that roughly a third of generative AI projects will be abandoned after proof of concept by end of 2025.

Companies getting value have made a different realization. “Write a document” isn’t one task. It’s twelve tasks that happen to produce one artifact. Each might benefit from different capabilities. That’s not a bug in how AI works. It’s the nature of knowledge work—complexity we’ve been hiding behind human flexibility for so long we forgot it existed.

Stop asking which model for your workflow. Start asking which model for each task inside it.

It won’t magically fix your AI strategy. But it will finally align how these systems work with how your work actually gets done.

[![](https://substackcdn.com/image/fetch/$s_!NwCX!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7c31970d-f5a9-4724-b78d-f099d0d4d1e8_2048x2048.png)](https://substackcdn.com/image/fetch/$s_!NwCX!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7c31970d-f5a9-4724-b78d-f099d0d4d1e8_2048x2048.png)
