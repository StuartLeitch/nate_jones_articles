---
title: "The Prompt Doctor Is In: Fixes For The 6 Most Common ChatGPT Issues (Including 25 Actionable Prompts)"
author: "Nate Jones"
published: 2025-11-06
url: https://natesnewsletter.substack.com/p/the-prompt-doctor-is-in-fixes-for
audience: everyone
scraped_at: 2026-01-05 19:12:48
---

I’ve run office hours with hundreds of people over the past year—Fortune 500 teams, independent builders, consultants trying to scale their practice with AI.

And I kept hearing the same frustration, just wearing different faces:

*“I don’t understand why this isn’t working. I feel like I’m being clear.”*

*“I’ve tried those fixes for hallucinations, and look they’re not working!”*

*“I keep rephrasing the prompt and it’s not changing anything.”*

It gradually dawned on me: there are a class of problems in AI use that are sticky and resist initial attempts to solve. They tend to persist, and that’s what pushes people to come to office hours with me.

And what’s interesting is I kept seeing the same problems in different disguises over and over again. After looking across my notes, I found six recurring problem types that popped up for engineers and non-coders alike. So I did a bit of digging, and it turns those 6 are showing up everywhere—including [in a study](https://arxiv.org/html/2408.05002v5) across 29,000 forum questions on the OpenAI website.

Now this gets interesting, because we have essentially six LLM behavioral ‘diseases’ (for lack of a better term), and all of them are hard to treat at first pass.

My task was to figure out a battery of sophisticated treatments that you can quickly and easily (like copy-paste) apply as a non-coder OR as an engineer to maximize your odds of success against these persistent issues.

Also, I had to name them! Some of them are known villains (hello hallucinations) and others are not widely discussed, but they all needed clear names in order for us to have a conversation and make progress together.

Here are the six problems:

1. **Under-specification** — When more (or less) words can BOTH hurt
2. **Regeneration Loops** — When touching it makes the tower fall down
3. **Multi-Step Reasoning Collapse** — When it says it thinks and it f\*ing lies
4. **Hallucination Triggers** — The nasty causes of hallucinations
5. **Consistency Drift** — When you can’t get the same result twice
6. **Context Overload** — Adding all the words was a BAD idea

Visuals help, and I even made a little cartoon to help you visualize these guys:

[![](https://substackcdn.com/image/fetch/$s_!Q-_I!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8fa7530-c007-466a-9b7d-3ca3eaedeb20_1536x1024.png)](https://substackcdn.com/image/fetch/$s_!Q-_I!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd8fa7530-c007-466a-9b7d-3ca3eaedeb20_1536x1024.png)

**Now, what are we gonna do about it?**

**Here’s what I’m thinking:**

I built you a complete treatment plan for each disease. Not a single fix—a multi-layered approach that works whether you’re typing in ChatGPT or building with the API.

**For each of the six problems, you get:**

**The Chat Fix** — A prose template you can copy-paste into any chat interface today. No coding, no setup, super easy.

**The Advanced Fix** — JSON schemas and API implementations that enforce the rules programmatically. For engineers building tools or automating workflows, these put bowling ball bumpers up to protect your prompts in production.

**Real Examples So You Can See It Work**— Every fix includes a range of concrete scenarios: product emails, vendor selection, customer research, code debugging, weekly reports, contract analysis. You see the exact prompt structure applied to actual work, not generic “write me a poem” examples.

**Good Signs / Bad Signs Diagnostics** — Checklists that you can watch to tell you if your fix worked. “First draft is 80%+ there” vs “Still getting wrong length”—observable signals so you’re not guessing whether you solved it.

**The Twist You Didn’t See Coming** — Each problem includes digging into WHY models behave this way. Sort of a root cause of the disease, if you will. These aren’t tips—they’re the structural reasons the problem exists.

**Plus: The Meta-Diagnostic Prompt** — One master prompt that analyzes your broken prompt against all six problems, tells you which one(s) you’re hitting, and gives you the specific fix to apply. It’s like having the pattern recognition from my office hours in your pocket.

**The Full Arsenal:**

- Really clear explanation of WHAT the heck these are in a way you can remember
- 25 working doctor prompts (baseline + advanced for each problem)
- Decision frameworks that replace guessing with structure
- Simplified, actionable guidance on advanced techniques that fix these issues: preservation boundaries, confidence requirements, validation gates (think of these as easy ways to get the fancy medicine)
- Clear explanations of which new AI features (structured outputs, reasoning controls, verification fields) actually solve which of the 6 problems

This isn’t “try these tips and hope.” It’s a diagnostic system with lots of proven treatments for each of these problems.

When something breaks, you match it to one of six patterns, apply the corresponding fix, verify it worked with the checklist.

> *Nate, how hard is this really? I buy that these are real issues, but they’re HARD.*
>
> *It’s totally solvable! I’ve solved all 6 in my own chatbot. I’ve solved them with agents in the API. And once you get the hang of it, you can solve it too.*
>
> *And that’s why this post is all about giving you LOTS of examples to get the hang of the solution pattern so it’s easy to apply. My goal is for you to have a whole kit of tools to go after these issues when they arrive.*

A long long time ago I worked in tree care, and one of the worst things you see as an arborist is a tree with fungi. It’s hard to treat, it’s a systemic issue, and it takes multiple approaches to address. Well, same here!

With some of these persistent issues it can feel like your ‘tree’ (your AI chatbot) has a disease. As I like to say: Don’t panic! My goal is to give you the tools to get healthy and get back to a productive and collaborative AI-human relationship.

Happy (and healthy) prompting, from the prompt doctor.


## How I Found the Real Problems (Not Just the Symptoms)

I kept having the same conversation.

Someone would share their screen with me—a founder, a product manager, a marketer, sometimes a developer—and they’d say some version of: “I don’t understand why this isn’t giving me what I need. I feel like I’m being clear, but...”

And they *were* being clear. At least, clear in the way we’re all taught to communicate with other humans.

The problem is: LLMs aren’t other humans.

After months of seeing this pattern repeat, I went looking for data. Not tips or best practices—actual evidence of what breaks when people try to use these tools.

I found it in a research study where a team analyzed 29,057 questions from the OpenAI developer forum. They manually reviewed 2,364 of them and categorized every type of problem people were asking about.

**The numbers were stark:**

- 54% of questions got fewer than 3 replies
- Only 9% ever got an accepted answer
- It takes an average of 6 days to get the *first* response

That told me something important: these aren’t simple problems. People are genuinely stuck.

So I did two things. First, I read through hundreds of forum comments—not just the questions, but the failed attempts people described. The “I tried this, then I tried that, and nothing works” posts.

Second, I compared what I found against what I see in my own work: the office hours sessions, the consulting calls, the moments when someone’s trying to solve a real problem and can’t figure out why their prompt isn’t working.

**And here’s what I realized: what people** ***ask about*** **isn’t always what’s actually** ***broken*****.**

Someone asks: “How do I make it stop hallucinating?”
What’s actually broken: they haven’t told the model it’s allowed to say “I don’t know.”

Someone asks: “Why does it give me different results every time?”
What’s actually broken: their prompt has hidden ambiguity they can’t see.

Someone asks: “How do I get it to fix just this one part?”
What’s actually broken: they’re regenerating everything instead of giving surgical instructions.

**What emerged were six systematic problems that cause most prompting failures:**

1. **Underspecification** (the research found this causes a 22.6% performance drop)
2. **Regeneration scope confusion** (you’re rerolling the dice instead of editing)
3. **Multi-step reasoning collapse** (asking for the destination without mapping the route)
4. **Hallucination triggers** (29% error rate on specialized content in the study)
5. **Consistency variance** (same prompt, different results, no idea why)
6. **Context overload** (more information actually makes it worse)

These aren’t just categories from the research. These are the structural problems I kept seeing break the same way, over and over, across completely different use cases.

**What follows are those six problems, what they actually look like when they happen to you, and the exact prompts that solve them.** Not theory. Not best practices. The specific fixes that work.

---


## Problem 1: The Underspecification Problem

**THE QUESTION EVERYONE ASKS:** “Why doesn’t it give me what I want when I feel like I was clear?”

**THIS LOOKS LIKE:**

*If you’re writing content:* You ask for “a social media post about our new feature” and get something that’s the wrong length, wrong tone, and completely misses your brand voice.

*If you’re managing a team:* You request “a summary of user feedback” and receive an unstructured wall of text instead of the categorized insights you can actually use in tomorrow’s meeting.

*If you’re building something:* You prompt for “error handling code” and get a generic try-catch block instead of the specific validation logic your API actually needs.

*If you’re in a leadership role:* You want “a brief on AI risks” and get either a 3-page essay or three bullet points—neither of which matches what you meant by “brief.”

**WHAT’S ACTUALLY HAPPENING:**

The research found that LLMs perform 22.6% worse when requirements aren’t fully specified. You’re not “unclear”—you’re *underspecified*. These are different.

When you tell another human “write something professional,” they know what you mean because they have years of shared context. The model doesn’t have any of that. Every unspecified requirement is a dice roll.

**THE BASELINE FIX:**

The Six-Layer Specification Stack:

```
I need [output type]. Here are my complete requirements:

FORMAT: [exact structure - bullet points? paragraphs? code?]
TONE: [professional/casual/technical - with example]
CONSTRAINTS:
- Must include: [X, Y, Z]
- Must avoid: [A, B, C]
- Length: [specific range]

SUCCESS LOOKS LIKE: [describe the ideal output]

EDGE CASES:
- If [scenario]: [handle this way]
- If [scenario]: [handle this way]

REFERENCE EXAMPLE: [show one example of what you want]

Now generate: [specific request]
```

**Real example:**

```
I need a product update email. Here are my complete requirements:

FORMAT: 3 short paragraphs, no more than 150 words total
TONE: Friendly but not overly casual - like updating a colleague, not a friend.
Example: “We’ve improved” not “We’ve made things way better!”
CONSTRAINTS:
- Must include: what changed, why it matters, where to learn more
- Must avoid: technical jargon, apologies, marketing speak
- Length: 100-150 words

SUCCESS LOOKS LIKE: A customer can read it in 30 seconds and understand exactly what changed and whether they need to do anything.

EDGE CASES:
- If the change requires action: Put that in paragraph 1, make it bold
- If it’s just nice-to-know: Save it for paragraph 3

REFERENCE EXAMPLE:
“We’ve updated how notifications work. You’ll now see them grouped by project instead of by time, which means less noise when you’re trying to focus. Everything you’re used to still works the same way—we’ve just reorganized how it appears. Learn more in our help center.”

Now generate: An update email about our new dashboard filtering feature.
```

**THE ADVANCED FIX (API users):**

If you’re using the API to automate this (generating weekly reports, processing customer feedback at scale, building tools), you can enforce your specification technically using structured outputs.

Instead of hoping the model follows your rules, you make it impossible for the model to break them:

```
{
  “output_format”: “json_schema”,
  “schema”: {
    “type”: “object”,
    “properties”: {
      “email_body”: {
        “type”: “string”,
        “minLength”: 100,
        “maxLength”: 150
      },
      “tone_category”: {
        “type”: “string”,
        “enum”: [”professional-friendly”, “technical”, “executive”]
      },
      “contains_required_elements”: {
        “type”: “object”,
        “properties”: {
          “what_changed”: {”type”: “boolean”},
          “why_it_matters”: {”type”: “boolean”},
          “learn_more_link”: {”type”: “boolean”}
        },
        “required”: [”what_changed”, “why_it_matters”, “learn_more_link”]
      },
      “action_required”: {”type”: “boolean”}
    },
    “required”: [”email_body”, “tone_category”, “contains_required_elements”]
  }
}
```

This means:

- The output *must* be between 100-150 characters (enforced)
- The tone *must* be one of your three options (enforced)
- All required elements *must* be present (enforced)
- The model can’t return anything that doesn’t match this structure

You’re not asking nicely anymore. You’re making the rules machine-checkable.

**WHAT’S NEW:**

Claude and ChatGPT now support structured outputs in the API. If you’re building tools, automating workflows, or processing things at scale, this is how you guarantee consistency.

For everyone else using the chat interface: Projects (Claude) and Custom Instructions (ChatGPT) let you save your specifications and reuse them without rebuilding every time.

**HOW TO KNOW IT’S WORKING:**

Good signs:

- First draft is 80%+ there
- You’re making small edits, not rewriting
- The output matches your examples

Bad signs:

- Still getting wrong length
- Tone drifts every time
- You keep saying “no, more like...”

If you’re seeing bad signs, you’re still underspecified. Add more constraints, better examples, or clearer success criteria.

---


## Problem 2: The Regeneration Problem

**THE QUESTION EVERYONE ASKS:** “How do I get it to fix just this one part without regenerating everything?”

**THIS LOOKS LIKE:**

*Writing a report:* You get a 5-paragraph draft back. Paragraph 3 is perfect. Paragraph 4 is terrible. You ask it to fix paragraph 4... and it regenerates the entire thing, losing everything good about paragraph 3.

*Creating a presentation:* The opening slide is exactly what you wanted. The closing slide misses the mark. You regenerate... and now the opening is different and also worse.

*Building an email:* The subject line is great, the body needs work. You ask for changes... the subject line you loved is now gone.

*Generating code:* Nine functions work perfectly. One has a bug. You ask it to fix the bug... it rewrites all ten functions and breaks three that were working.

You’re stuck in this loop where fixing one thing breaks another.

**WHAT’S ACTUALLY HAPPENING:**

The model doesn’t know what to preserve versus what to change. When you say “make this better” or “fix the problem,” you’re asking it to regenerate everything because you haven’t told it what to keep.

There’s no memory of what you liked. There’s no concept of “locked” versus “editable” sections. The model sees your entire document as fair game for revision.

You’re rerolling the dice instead of giving surgical instructions.

**THE BASELINE FIX:**

Surgical Editing Protocol:

```
Keep everything except this part:
[quote exact section]

What’s wrong with it: [specific issue]

Fix only that section by: [specific instruction]

Keep unchanged:
- [element 1]
- [element 2]
- [everything else]

Regenerate just the problem section now.
```

**Real example:**

```
Keep everything except the third paragraph about pricing.

What’s wrong with it: It’s too technical. Terms like “tiered rate structure” will confuse non-technical readers.

Fix only that section by: Explain the pricing model using an analogy to Netflix tiers—different levels for different needs.

Keep unchanged:
- The opening hook about the problem we solve
- All feature descriptions in paragraphs 1-2
- The closing call-to-action
- The friendly, conversational tone throughout

Regenerate just the pricing paragraph.
```

This works because you’re drawing explicit boundaries around what can change. The model isn’t guessing what you liked—you’re telling it.

**THE ADVANCED FIX (API users):**

If you’re using the API to build tools, generate content at scale, or automate document workflows, you can enforce immutability at the field level using structured outputs:

```
{
  “output_format”: “json_schema”,
  “schema”: {
    “type”: “object”,
    “properties”: {
      “intro”: {
        “type”: “string”,
        “description”: “Opening paragraph - establishes the problem”
      },
      “body”: {
        “type”: “array”,
        “items”: {”type”: “string”},
        “description”: “Main content paragraphs”
      },
      “cta”: {
        “type”: “string”,
        “description”: “Call to action closing”
      }
    },
    “required”: [”intro”, “body”, “cta”]
  }
}
```

Initial generation creates the document as separate fields. Then when you need to edit:

```
{
  “instruction”: “Update only body[1] to be less technical. Use simpler analogies.”,
  “freeze_fields”: [”intro”, “body[0]”, “body[2]”, “cta”],
  “return_format”: “full_document”
}
```

The model:

- Can only modify `body[1]` (enforced)
- Cannot touch any frozen fields (enforced)
- Must return the complete document with only that one field changed (enforced)

**Why this matters for API users:**

Let’s say you’re building a tool that generates weekly executive summaries:

- Section 1 gets approved by legal (lock it)
- Section 2 needs a rewrite for tone (edit it)
- Section 3 gets approved by finance (lock it)
- Section 4 needs more data (edit it)

With field-level control:

- Approved sections stay byte-for-byte identical (compliance requirement met)
- Only target sections change (no cascade rewrites)
- Audit trail shows exactly what changed between versions (v1 → v2 diff)
- You can roll back individual sections without losing other work

Or if you’re generating customer communications at scale:

- Legal-approved disclaimers never change
- Product descriptions get updated
- Personalized greetings stay locked per customer
- Offers get modified based on segment

You’re not hoping the model respects boundaries—you’re making boundaries technically enforceable.

**WHAT’S NEW:**

- **Canvas/Artifacts** (in Claude’s chat interface) shows documents in a side panel where you can make inline edits and see version history
- **Memory** (in ChatGPT) can remember “this is the approved version of section 1” and reference it in later conversations
- **Structured outputs** (API) enforce field-level immutability—locked fields literally cannot change
- **Diff tracking** in some interfaces shows exactly what changed between regenerations so you can catch unwanted edits

The tooling is catching up to what we’ve always needed: the ability to lock down approved parts while iterating on the rest.

**HOW TO KNOW IT’S WORKING:**

Good signs:

- Only the target section changed
- Tone and voice stay consistent across all sections
- You can fix one thing without triggering a cascade
- Unchanged sections are byte-for-byte identical to the original

Bad signs:

- The introduction keeps changing when you fix the conclusion
- Voice drifts between sections (formal → casual → formal)
- Section order gets rearranged when you didn’t ask for that
- You regenerate three times just to get back to where you started

If you’re seeing bad signs, you’re not being explicit enough about boundaries. Quote the exact text you want preserved, or better yet, structure your content with clearly labeled sections from the start so you can reference them by name.

The key principle: **explicit preservation beats implicit hope**. Don’t hope the model knows what you liked. Tell it exactly what to keep and exactly what to change.

---


## Problem 3: The Multi-Step Reasoning Problem

**THE QUESTION EVERYONE ASKS:** “Why does it skip steps or lose track halfway through complex tasks?”

**THIS LOOKS LIKE:**

*Analyzing business problems:* You ask “analyze our churn and propose a plan.” You get back a single wall of text with surface-level causes, a vague three-point plan, and no explanation of how they got from problem to solution.

*Making decisions:* You need to evaluate five vendor options against specific criteria. The model gives you a winner but skips half the criteria and doesn’t show its work. You can’t tell if it actually compared them systematically or just picked one.

*Planning projects:* You ask for a implementation roadmap. It jumps straight to “Phase 3: Deploy” without explaining what happens in Phase 1 and 2, what dependencies exist, or what could go wrong.

*Doing research:* You request an analysis of three competing approaches. The output mixes analysis with recommendations, doesn’t cite sources, and reaches conclusions without showing the evidence that supports them.

The model is trying to do everything in one cognitive leap. And when you ask “how did you get that answer?” it can’t show you because it never actually worked through the steps.

**WHAT’S ACTUALLY HAPPENING:**

You’re asking for a destination without making the model map the route. Complex tasks need intermediate steps with explicit outputs that you can verify before moving forward.

The model doesn’t know it needs to show its work. And without checkpoints, it takes shortcuts—jumping to conclusions, skipping validation, mixing steps together in ways that make the output impossible to verify or debug.

**THE BASELINE FIX:**

Scaffolded Reasoning Architecture:

```
I need you to complete this in stages. After each stage, stop and show me your work.

STAGE 1: [specific first step]
Output required: [what I need to see]
Validation: [how I’ll know it’s right]

STAGE 2: [specific second step, using Stage 1 output]
Output required: [what I need to see]
Validation: [how I’ll know it’s right]

STAGE 3: [etc.]

Complete Stage 1 only. Stop and show me the output before proceeding.
```

**Real example:**

```
I need you to analyze customer churn in stages.

STAGE 1: Extract all distinct complaints from the feedback data
Output required: Numbered list of specific complaints (one issue per line)
Validation: Each complaint should be a single, specific issue (not “bad service” but “wait times over 10 minutes”)

STAGE 2: Group complaints into categories
Output required: Table with category names and which complaint numbers belong to each
Validation: No complaint appears in multiple categories; every complaint is categorized

STAGE 3: Rank categories by frequency and impact
Output required: Table with category, complaint count, percentage, and estimated revenue impact
Validation: Percentages sum to 100%; impact calculations show your math

Complete Stage 1 only. Show me the numbered list of complaints before proceeding.
```

After you review Stage 1:

```
Stage 1 looks good. Now complete Stage 2 only. Use the exact complaint numbers from Stage 1 to build your categories.
```

This forces the model to:

1. Do one thing at a time
2. Show you its work at each step
3. Let you validate before it proceeds
4. Use outputs from step N as inputs to step N+1

**THE ADVANCED FIX (API users):**

If you’re automating this at scale or building tools, you can enforce the stage structure and add automatic validation gates:

```
{
  “task”: “churn_analysis”,
  “stages”: [
    {
      “stage_id”: 1,
      “instruction”: “Extract distinct complaints”,
      “output_schema”: {
        “type”: “array”,
        “items”: {
          “complaint_id”: “integer”,
          “complaint_text”: “string”,
          “source”: “string”
        }
      },
      “validation_gate”: {
        “min_items”: 10,
        “confidence_threshold”: 0.8
      }
    },
    {
      “stage_id”: 2,
      “instruction”: “Categorize complaints from Stage 1”,
      “input_from”: “stage_1.output”,
      “output_schema”: {
        “type”: “object”,
        “properties”: {
          “categories”: {
            “type”: “array”,
            “items”: {
              “category_name”: “string”,
              “complaint_ids”: “array”
            }
          }
        }
      },
      “validation_gate”: {
        “all_complaints_categorized”: true,
        “no_duplicate_assignments”: true
      }
    }
  ],
  “reasoning_effort”: “medium”,
  “escalate_to_high_if”: “confidence < 0.8”
}
```

This means:

- Each stage has a required output structure (enforced)
- Stage 2 can only use Stage 1’s output (enforced)
- Validation gates must pass before proceeding (enforced)
- If confidence drops below 0.8, reasoning effort automatically increases
- You can add tool calls (web search, data analysis) that only trigger when validation fails

You’re not hoping the model follows your process—you’re making the process the only path forward.

**Why this matters for API users:**

Let’s say you’re building a tool that analyzes support tickets every week. With scaffolding:

- Stage 1 extracts issues (takes 10 seconds, uses minimal tokens)
- Validation catches if it missed a category (automatic)
- Only if validation passes does it move to Stage 2 (cost control)
- If confidence is low, it escalates to deeper reasoning automatically
- Each stage’s output feeds the next in a typed, auditable chain

You get better results, lower costs (don’t over-think easy stages), and a clear audit trail of how the answer was reached.

**WHAT’S NEW:**

- **Reasoning effort controls** (in some APIs) let you set “medium” for most work and automatically escalate to “high” only when needed
- **Structured outputs** let you enforce stage schemas so Stage N can’t proceed without proper Stage N-1 output
- **Tool routing** lets you configure “only search the web if validation fails” instead of searching unnecessarily
- **Canvas/Projects** (chat interfaces) help you save stage outputs and reference them in subsequent conversations

The tooling is finally supporting multi-stage workflows as first-class concepts instead of hacks.

**HOW TO KNOW IT’S WORKING:**

Good signs:

- Outputs are structured (tables, lists) not prose
- Each stage builds on the previous in obvious ways
- You can verify intermediate work before final conclusions
- The model shows confidence levels and flags uncertainty

Bad signs:

- Stages are still mixed together in one blob
- Analysis jumps to conclusions without showing evidence
- You can’t tell how it got from data to recommendation
- No confidence scores or “needs verification” flags

If you’re seeing bad signs, break the stages down further. If “analyze and recommend” is too much, split it into “analyze,” “generate options,” “evaluate options,” “recommend with rationale.”

The more complex the task, the more stages you need. And each stage should produce something you can look at and say “yes, that’s right” or “no, fix this before continuing.”

---

---


## Problem 4: The Hallucination Problem (29% error rate on specialized topics)

**THE QUESTION EVERYONE ASKS:** “How do I stop it from making things up?”

**THIS LOOKS LIKE:**

*Doing research:* You ask about a specific regulation or policy. The model confidently cites “Section 4.2.1” with specific language. You go to verify it—that section doesn’t exist. Or it exists but says something completely different.

*Writing with sources:* You request an analysis with citations. Every claim has a footnote. You click the links—half are homepage URLs that don’t support the claim, the other half are completely fabricated URLs that lead nowhere.

*Getting expert advice:* You ask about a technical specification or industry standard. The answer sounds authoritative, uses the right jargon, cites specific numbers. You check with an actual expert—it’s confidently wrong about three key facts.

*Checking company information:* You ask when a product launched or what a feature does. The model tells you “Q3 2023” and describes capabilities that don’t exist. It sounds completely sure. It’s completely wrong.

The model isn’t hedging. It isn’t saying “I’m not certain.” It’s speaking with the confidence of an expert while inventing specifics.

**WHAT’S ACTUALLY HAPPENING:**

The research found a 29% hallucination rate on specialized content. That’s nearly one in three claims being wrong on topics outside common knowledge.

Here’s the thing: these models are trained to be helpful. They’re trained to give you an answer. They’re not trained to say “I don’t know” when they hit the edge of their knowledge.

So instead of stopping, they keep going. They pattern-match from related information and generate something that *sounds* right. The tone stays confident because confidence is part of the pattern of “helpful expert.”

You haven’t given the model permission to admit uncertainty. And without that permission, it will confidently fill gaps with plausible-sounding fiction.

**THE BASELINE FIX:**

The Uncertainty Protocol:

```
CRITICAL: If you don’t know something with high confidence, say “I don’t have reliable information about [X].” Do not guess or fill gaps.

For each claim you make:
- State your confidence level (high/medium/low)
- If medium or low, explain why
- If referencing facts, note where that knowledge comes from

Task: [your actual request]

Before finalizing, review your response and flag any claims where you have less than high confidence.
```

**Real example:**

```
CRITICAL: If you don’t know something with high confidence, say “I don’t have reliable information about [X].” Do not guess or fill gaps.

For each technical specification you provide about the GPT-4 Vision API:
- State your confidence level (high/medium/low)
- If medium or low, explain what’s uncertain
- Note if this is from documentation, common usage patterns, or inference

Task: Explain the rate limits for the GPT-4 Vision API and how to handle rate limit errors.

Before finalizing, review your response and flag any claims where you have less than high confidence.
```

What you’ll get back:

```
Rate Limits (confidence: medium):
- The standard tier typically has limits around 500 requests per day for Vision API calls
- However, I don’t have reliable information about current exact limits as these change frequently
- You should check the official OpenAI documentation for your specific tier

Error Handling (confidence: high):
- Rate limit errors return HTTP 429 status code
- Response includes Retry-After header indicating wait time
- Exponential backoff is the recommended retry strategy

Uncertainty flags:
- Specific rate numbers may have changed since my training
- Different account tiers have different limits that I cannot verify
- I recommend checking status.openai.com for real-time limit information
```

This works because you’ve explicitly allowed uncertainty. The model can now say “I don’t know this specific number” instead of inventing one.

**THE ADVANCED FIX (API users):**

If you’re building tools, conducting research at scale, or need auditable outputs, you can enforce verification fields using structured outputs:

```
{
  “output_format”: “json_schema”,
  “schema”: {
    “type”: “object”,
    “properties”: {
      “claims”: {
        “type”: “array”,
        “items”: {
          “type”: “object”,
          “properties”: {
            “statement”: {”type”: “string”},
            “confidence”: {
              “type”: “string”,
              “enum”: [”high”, “medium”, “low”]
            },
            “source_type”: {
              “type”: “string”,
              “enum”: [”training_data”, “common_knowledge”, “inference”, “unknown”]
            },
            “verification_status”: {
              “type”: “string”,
              “enum”: [”verified”, “needs_check”, “unable_to_verify”]
            },
            “source_url”: {”type”: “string”}
          },
          “required”: [”statement”, “confidence”, “verification_status”]
        }
      },
      “browse_requested”: {
        “type”: “array”,
        “items”: {
          “claim_id”: “integer”,
          “reason”: “string”
        },
        “description”: “Claims where web search is needed due to low confidence”
      }
    },
    “required”: [”claims”]
  }
}
```

Then add a routing rule:

```
{
  “tool_policy”: {
    “web_search”: {
      “trigger”: “automatic”,
      “condition”: “claim.confidence != ‘high’ OR claim.verification_status == ‘needs_check’”,
      “limit”: 5
    }
  }
}
```

This means:

- Every claim must include confidence level (enforced)
- Every claim must have verification status (enforced)
- Web search only triggers for non-high-confidence claims (enforced)
- You get a structured list of what needs verification (auditable)
- The model can’t make unverified claims without flagging them (enforced)

**Why this matters for API users:**

Let’s say you’re building a legal research tool:

- Claim: “Section 409A requires...” (confidence: high, verified)
- Claim: “The 2023 amendment changed...” (confidence: low, needs\_check)
- System automatically searches for the 2023 amendment
- If found: updates claim with source
- If not found: marks as “unable\_to\_verify”
- Output includes audit trail of every claim with verification status

Or if you’re building a competitive intelligence system:

- Claim: “Competitor X raised $50M” (confidence: medium, needs\_check)
- Automatically triggers web search for recent funding news
- Finds TechCrunch article from last week: “$45M Series B”
- Claim gets corrected with source
- You get an audit log showing the correction

You’re not hoping the model self-corrects—you’re building verification into the process.

**WHAT’S NEW:**

- **Structured outputs** (API) let you enforce verification fields—models must surface confidence and flag uncertainty
- **Inline tool routing** allows web search to trigger automatically only for low-confidence claims (cost control + verification)
- **Citation features** in chat interfaces (Claude’s citations, ChatGPT’s source linking) make it easier to check sources
- **Audit renders** show claims with confidence badges so reviewers can see what needs verification at a glance

The tooling is moving from “trust but verify” to “verify by design.”

**HOW TO KNOW IT’S WORKING:**

Good signs:

- You see “I don’t have reliable information about...” in responses
- Claims include confidence levels (and some are honestly marked “low”)
- Sources are specific and relevant (article URLs, not homepages)
- The model flags what needs verification before you have to ask
- When you check sources, they actually support the claims

Bad signs:

- Every claim is marked “high confidence” (unrealistic on complex topics)
- Zero “needs verification” flags even on obscure topics
- Sources are generic (homepage links, “according to experts”)
- Confident tone throughout with no hedging
- When you spot-check, multiple claims are wrong

If you’re seeing bad signs, you haven’t made uncertainty safe. Go back and explicitly permit “I don’t know.” Make it clear that admitting uncertainty is better than guessing. Add verification requirements to your prompt.

The key principle: **Hallucinations thrive in the absence of permission to be uncertain.** Make uncertainty not just acceptable but required, and suddenly the model stops filling gaps with fiction.

---

---


## Problem 5: The Consistency Problem

**THE QUESTION EVERYONE ASKS:** “Why do I get different results every time with the same prompt?”

**THIS LOOKS LIKE:**

*Creating weekly reports:* You have a template for board updates. Every week you fill in new data using the same prompt. But the structure keeps changing—sometimes it’s three sections, sometimes five. The tone shifts from formal to casual and back. The emphasis moves around. You can’t get two consecutive weeks that look like they came from the same process.

*Categorizing content:* You’re tagging customer feedback. You run the same prompt on Monday and Thursday with identical data. Monday’s version tags something as “billing issue.” Thursday’s version calls it “payment problem.” Same complaint, different category, no explanation why.

*Making decisions:* You ask the model to select the best option from a list using specific criteria. You run it three times with identical inputs. You get three different winners. When you ask why, the justification changes each time—criteria applied in different orders, edge cases handled differently, priorities shifting.

*Evaluating candidates:* You’re scoring applications against a rubric. Same rubric, same applications. Run 1 ranks them A, B, C. Run 2 ranks them B, A, C. Run 3 ranks them A, C, B. The scores are close, but you need consistency for fairness. You’re not getting it.

Even with the same inputs, you’re getting different outputs. And you can’t figure out what’s changing or why.

**WHAT’S ACTUALLY HAPPENING:**

Even with identical seeds and temperature settings, models can produce different outputs. Model updates change behavior. Temperature above zero introduces randomness. But the deeper issue is that your prompt has hidden ambiguity you can’t see.

You’re using fuzzy criteria. “Best option.” “Most important.” “Primary concern.” These sound clear to you because you have intuition about what they mean. The model doesn’t share your intuition.

When you say “prioritize quality over speed,” that’s ambiguous. What’s the threshold? How much slower can something be before quality doesn’t matter? If two options are tied on quality, what’s the tiebreaker?

The model is making judgment calls every time because your criteria leave room for judgment. Different calls = different outputs.

**THE BASELINE FIX:**

Deterministic Decision Framework:

```
Use this deterministic decision framework:

ABSOLUTE CONSTRAINTS (must pass all):
1. [Binary requirement - yes/no]
2. [Binary requirement - yes/no]
3. [Binary requirement - yes/no]

SELECTION CRITERIA (apply in this exact order):
1. [First criterion - specific, measurable rule]
2. [Second criterion - only if #1 doesn’t resolve to one option]
3. [Tiebreaker - specific rule, must produce a single answer]

REFUSAL PATH:
If no option passes all constraints, respond with “No valid option meets requirements” and explain which constraint(s) failed.

PROCESS:
1. List all options that pass absolute constraints
2. Apply selection criteria in order, showing your work
3. State final selection with justification referencing criteria order

This should produce the same answer every time given the same inputs.

Task: [your actual request]
```

**Real example:**

```
Use this deterministic decision framework:

ABSOLUTE CONSTRAINTS (must pass all):
1. Price under $50,000
2. Delivery within 60 days
3. Vendor has SOC 2 compliance

SELECTION CRITERIA (apply in this exact order):
1. Lowest total cost of ownership (purchase + annual maintenance)
2. If TCO within $5,000: shortest delivery time
3. If still tied: vendor with most reference customers in our industry

REFUSAL PATH:
If no vendor passes all three constraints, respond with “No valid option meets requirements” and list which vendors failed which constraints.

PROCESS:
1. List vendors that pass all constraints (Price < $50k AND Delivery ≤ 60 days AND SOC 2 = yes)
2. Calculate TCO for each qualifying vendor
3. Select lowest TCO; if tied within $5,000, use delivery time; if still tied, use reference count
4. State winner with justification showing the criteria order

This should produce the same answer every time.

Task: Recommend a vendor from this list: [vendor data]
```

What this does:

- Constraints are binary (pass/fail, no judgment)
- Criteria have specific thresholds ($5,000 difference, not “similar”)
- Priority order is explicit (TCO first, THEN delivery, THEN references)
- Tiebreaker rules are unambiguous
- Refusal is an acceptable outcome (no forcing an invalid choice)

**THE ADVANCED FIX (API users):**

If you’re building tools, automating decisions at scale, or need audit trails, enforce the logic using structured outputs with explicit validation:

```
{
  “output_format”: “json_schema”,
  “schema”: {
    “type”: “object”,
    “properties”: {
      “constraint_checks”: {
        “type”: “array”,
        “items”: {
          “option_id”: “string”,
          “constraint_results”: {
            “type”: “object”,
            “properties”: {
              “price_under_50k”: {”type”: “boolean”},
              “delivery_within_60_days”: {”type”: “boolean”},
              “soc2_compliant”: {”type”: “boolean”}
            },
            “required”: [”price_under_50k”, “delivery_within_60_days”, “soc2_compliant”]
          },
          “passes_all_constraints”: {”type”: “boolean”}
        }
      },
      “qualifying_options”: {
        “type”: “array”,
        “items”: {
          “option_id”: “string”,
          “tco”: {”type”: “number”},
          “delivery_days”: {”type”: “integer”},
          “reference_count”: {”type”: “integer”}
        }
      },
      “selection_process”: {
        “type”: “object”,
        “properties”: {
          “step_1_result”: “string”,
          “step_2_result”: “string”,
          “step_3_result”: “string”
        }
      },
      “final_selection”: {
        “type”: “object”,
        “properties”: {
          “winner”: “string”,
          “rationale”: “string”,
          “criteria_applied”: {”type”: “array”, “items”: {”type”: “string”}}
        }
      },
      “refusal”: {
        “type”: “object”,
        “properties”: {
          “no_valid_option”: {”type”: “boolean”},
          “failed_constraints”: {”type”: “array”}
        }
      }
    },
    “required”: [”constraint_checks”, “qualifying_options”, “selection_process”]
  },
  “temperature”: 0
}
```

This means:

- Every constraint must be checked for every option (enforced)
- Selection process must show work step-by-step (auditable)
- Refusal path is explicit—”no valid option” is a valid response (enforced)
- Criteria application order is captured (auditable)
- Temperature set to 0 for maximum determinism (enforced)

**Why this matters for API users:**

Let’s say you’re building a vendor selection system that runs quarterly:

- Q1: Vendor A wins based on TCO ($42k vs $46k)
- Q2: Same vendors, similar prices, Vendor A still wins
- Audit shows: identical constraint checks, identical criteria application
- Board asks “why A?” - you have a complete decision tree showing the logic

Or if you’re building a content moderation system:

- Post 1: Flagged because constraint “no personal attacks” failed
- Post 2: Similar content, same flag, same constraint
- Post 3: Different content, passes all constraints
- Audit log shows consistent application of binary rules
- Appeals process can review against explicit criteria

Or weekly report generation:

- Week 1: Generated with structure [Exec Summary, Metrics, Risks, Actions]
- Week 2-52: Exact same structure, enforced by schema
- Tone consistency measured via embedding similarity (> 0.95 required)
- If drift detected: flag for review before sending

You’re not hoping for consistency—you’re engineering it into the system architecture.

**WHAT’S NEW:**

- **Temperature controls** are more accessible—APIs and chat interfaces let you set this explicitly
- **Structured outputs** enforce that selection logic must be shown in a consistent format
- **Memory/template pinning** lets you save decision frameworks and reuse them byte-for-byte
- **Refusal handling** is better—systems now treat “no valid option” as a success state, not a failure
- **Audit logging** in some tools shows decision trees across multiple runs so you can verify consistency

The tooling is moving from “try to be consistent” to “consistency by construction.”

**HOW TO KNOW IT’S WORKING:**

Good signs:

- Same inputs produce same outputs across multiple runs
- When you get different results, you can point to what input changed
- Selection rationales reference criteria in the same order every time
- The model refuses when constraints conflict (not forcing invalid choices)
- Audit trails show identical constraint checks for identical inputs

Bad signs:

- Weekly reports have different structures despite identical prompts
- Categories drift (same item tagged differently across runs)
- Selection winners flip without input changes
- No refusals even when you test with deliberately conflicting constraints
- Justifications shift emphasis (”quality matters most” → “speed is key”) without explanation

If you’re seeing bad signs, your criteria have hidden ambiguity. Make them more binary, more specific, more ordered. Replace “better” with “lower cost by ≥$5,000.” Replace “prioritize quality” with “quality score ≥8 required; if multiple options ≥8, select fastest.”

The key principle: **Consistency requires eliminating ambiguity at every decision point.** If two people could interpret your criteria differently, the model will too—and the interpretation will vary across runs.

---


## Problem 6: The Context Overload Problem

**THE QUESTION EVERYONE ASKS:** “Why does it work worse when I give it MORE information?”

**THIS LOOKS LIKE:**

*Planning from documents:* You paste in a 20-page strategy brief with all the background context, thinking more information = better output. You ask for an implementation plan. What you get back parrots nice-sounding phrases from the document but completely ignores the three hard constraints buried on page 14. The output sounds good but can’t actually be executed.

*Analyzing data:* You dump three quarters of meeting notes, customer interviews, and survey results into the prompt. You ask for key insights. The model picks random interesting quotes from throughout the data instead of identifying the actual patterns. It’s choosing what’s colorful over what’s important.

*Making decisions:* You provide exhaustive background—company history, market analysis, competitor research, team bios, past attempts. You ask for a recommendation. The answer is generic advice that could apply to anyone. All that context got treated as noise, and the specific requirements got lost.

*Answering questions:* You include every possibly relevant document because you want to be thorough. You ask a specific question. The response synthesizes from all the documents equally, giving you an answer that’s technically true but practically useless because it didn’t prioritize what actually mattered.

You gave it everything, thinking that would help. Instead, the signal got buried under noise.

**WHAT’S ACTUALLY HAPPENING:**

Context isn’t a database. It’s more like working memory. And like human working memory, there’s a difference between information being present and information being prioritized.

When you paste 20 pages of context, the model sees all of it—but it doesn’t know what’s critical versus what’s background. It doesn’t know that the constraint on page 14 outweighs the nice-to-have feature mentioned on page 3.

You’re treating context like “here’s everything, figure it out.” But the model needs hierarchy: “Here’s what matters most. Here’s supporting detail. Here’s optional background.”

Without that hierarchy, the model does what humans do with too much undifferentiated information: it picks what stands out (vivid examples, repeated phrases, recency) instead of what’s actually important.

**THE BASELINE FIX:**

Hierarchical Context Loading:

```
REQUIRED CONTEXT (must consider for every decision):
[Only absolutely essential information - constraints, requirements, success criteria]

OPTIONAL CONTEXT (reference only if directly relevant to a specific requirement):
[Supporting details, background, nice-to-have information]

PRIORITY HIERARCHY:
1. [Most important consideration - this outweighs everything else]
2. [Second most important - only matters if #1 is satisfied]
3. [Third most important - only matters if #1 and #2 are satisfied]

Focus primarily on REQUIRED CONTEXT and Priority #1.
Reference OPTIONAL CONTEXT only when directly relevant to satisfying required constraints.

Task: [your actual request]
```

**Real example:**

```
REQUIRED CONTEXT (must consider):
- Budget: $150k hard cap (no flexibility)
- Timeline: Launch by Q2 end (regulatory deadline)
- Must integrate with: Salesforce, Stripe, existing auth system
- Success criteria: Handle 10k transactions/day at launch

OPTIONAL CONTEXT (reference only if relevant):
- Company background: Founded 2019, 50 employees, fintech space
- Previous attempt: Tried building in-house in 2023, abandoned due to complexity
- Team: 3 engineers, 1 PM, 2 designers
- Market research: 15 customer interviews, 3 competitor analyses
- Future vision: Eventually expand to 50k transactions/day, add mobile app

PRIORITY HIERARCHY:
1. Budget and timeline are immovable (regulatory + funding constraints)
2. Integration requirements (existing systems can’t change)
3. Launch-day performance (10k transactions/day)

Focus on satisfying the budget, timeline, and integrations first.
Reference team size or past attempts only if directly relevant to approach selection.

Task: Recommend a technical approach for our payment processing system.
```

What this does:

- Separates must-have from nice-to-know
- Makes it explicit what takes priority when trade-offs occur
- Prevents background information from drowning out requirements
- Lets the model focus on what matters without ignoring available context

**THE ADVANCED FIX (API users):**

If you’re building tools, processing documents at scale, or automating analysis, you can structure context as retrievable chunks with explicit pull policies:

```
{
  “context_architecture”: {
    “required_facts”: {
      “type”: “object”,
      “properties”: {
        “hard_constraints”: [
          {”constraint”: “budget_cap”, “value”: 150000, “flexible”: false},
          {”constraint”: “deadline”, “value”: “2025-06-30”, “flexible”: false},
          {”constraint”: “integrations”, “value”: [”salesforce”, “stripe”, “auth”], “required”: true}
        ],
        “success_criteria”: [
          {”metric”: “transaction_capacity”, “minimum”: 10000, “unit”: “per_day”}
        ],
        “priority_order”: [
          “hard_constraints.budget_cap”,
          “hard_constraints.deadline”,
          “hard_constraints.integrations”,
          “success_criteria.transaction_capacity”
        ]
      }
    },
    “optional_context”: {
      “type”: “object”,
      “properties”: {
        “company_background”: {
          “stored_as”: “retrievable_blob”,
          “pull_policy”: “only_if_referenced_in_analysis”
        },
        “market_research”: {
          “stored_as”: “retrievable_blob”,
          “pull_policy”: “only_if_needed_for_validation”
        },
        “previous_attempts”: {
          “stored_as”: “retrievable_blob”,
          “pull_policy”: “only_if_approach_requires_context”
        }
      }
    },
    “retrieval_policy”: {
      “trigger”: “If required_fact cannot be satisfied, retrieve smallest optional_context snippet that resolves it”,
      “max_retrieval”: 2,
      “quote_retrieved”: true
    }
  }
}
```

Then the process becomes:

```
{
  “analysis_flow”: {
    “step_1”: “Evaluate options against required_facts only”,
    “step_2”: “If conflict/uncertainty, retrieve relevant optional_context snippet”,
    “step_3”: “Show which snippet was pulled and why”,
    “step_4”: “Continue with minimal context needed to resolve”
  }
}
```

This means:

- Required facts are structured as key-value pairs (not prose)
- Optional context stays out of working memory until needed (enforced)
- Retrieval only happens when required facts can’t be satisfied (cost control)
- Retrieved snippets are quoted with rationale (auditable)
- Model can’t pull optional context unnecessarily (enforced)

**Why this matters for API users:**

Let’s say you’re building a contract review system:

- Required: Key terms, obligations, deadlines, payment terms (always loaded)
- Optional: Legal precedents, negotiation history, party backgrounds (100+ pages)
- Analysis identifies a clause that might conflict with obligation #3
- System retrieves only the 2-paragraph precedent about that specific clause type
- Result: Accurate analysis without processing 100 pages every time

Or if you’re building a customer support automation:

- Required: Customer’s current issue, account status, product they’re using
- Optional: Full support ticket history (years of data), knowledge base (1000+ articles)
- System evaluates issue against required facts first
- If resolution unclear, retrieves only the 3 most relevant KB articles
- Result: Fast response time, lower token costs, still has full context available if needed

Or document-based Q&A:

- Required: The user’s specific question, current project context
- Optional: 50-page technical specs, meeting transcripts, past decisions
- System attempts answer from required context
- If confidence < 0.8, retrieves smallest spec section that would raise confidence
- Result: Answers are grounded in required context, supplemented only when necessary

You’re not dumping everything into context and hoping—you’re architecting progressive disclosure.

**WHAT’S NEW:**

- **Longer context windows** (200k+ tokens) make it tempting to dump everything, but tooling now supports progressive disclosure
- **Retrieval APIs** let you store optional context externally and pull it on-demand
- **Multimodal attachments** mean you can include diagrams/tables directly instead of transcribing them into text (preserves signal)
- **Context linting tools** (in some platforms) highlight redundant or low-signal blocks
- **Structured facts** (key-value format) are better preserved than prose across long contexts

The tooling is moving from “here’s 200k tokens, good luck” to “here’s what matters, here’s how to get more if needed.”

**HOW TO KNOW IT’S WORKING:**

Good signs:

- Outputs prioritize required constraints over background details
- When optional context is used, it’s quoted with rationale (”Because X wasn’t resolved by required facts, I referenced...”)
- Responses are focused on answering the question, not restating the background
- Hard constraints are never violated even when optional context suggests otherwise
- If you test with conflicting optional context, required context still wins

Bad signs:

- Outputs restate background instead of solving the problem
- Vivid examples from page 30 get more weight than constraints from page 1
- Random cherry-picking from throughout the context
- Required constraints get missed while optional nice-to-haves are mentioned
- Answers change dramatically when you reorder the same information

If you’re seeing bad signs, your context isn’t hierarchical. Strip it down. Put only the critical 5-10 facts in REQUIRED. Move everything else to OPTIONAL. Make the priority order explicit. Test with deliberately distracting optional context—if it still drowns out requirements, make your required section even more minimal.

The key principle: **More context is not better context. Structured context with clear hierarchy is better context.** The goal isn’t to give the model everything—it’s to give the model what matters in a format that makes “what matters” obvious.

---


## What This Actually Means

I kept having conversations where someone would say “I don’t know why this isn’t working” and I’d look at their prompt and immediately see it: underspecified requirements, or trying to fix everything at once, or hoping the model would just figure out what mattered in twenty pages of context.

It wasn’t that they were bad at this. It was that the pattern wasn’t obvious until you’d seen it break the same way a hundred times.

That’s what the research showed me: 29,000 questions that looked different on the surface but kept breaking in the same six ways underneath.

**The shift is this:**

Before: “Why isn’t this working? Let me try rephrasing it.”

After: “Which of the six problems is this? Here’s the fix.”

You stop guessing. You stop rephrasing the same broken prompt five different ways. You look at the structure and you fix what’s actually broken.

**The meta-prompt** (use this when you’re stuck):

```
I’m getting unexpected results from a prompt. Help me diagnose what’s broken.

MY PROMPT:
[paste your prompt here]

THE PROBLEM:
[describe what’s wrong with the output]

Analyze this against six common prompting failures:

1. UNDERSPECIFICATION - Am I missing explicit requirements?
   Check for: format, tone, constraints, success criteria, examples

2. REGENERATION SCOPE - Am I trying to fix too much at once?
   Check for: Did I specify what to preserve vs. what to change?

3. MULTI-STEP REASONING - Should this be broken into stages?
   Check for: Am I asking for conclusions without intermediate steps?

4. HALLUCINATION - Did I allow uncertainty?
   Check for: Did I permit “I don’t know”? Did I require confidence levels?

5. CONSISTENCY - Where’s the ambiguity?
   Check for: Are criteria measurable, ordered, and binary?

6. CONTEXT OVERLOAD - Is signal buried in noise?
   Check for: Did I separate REQUIRED from OPTIONAL information?

For each problem you identify:
- Explain why it applies
- Show me the specific fix

Then give me a rewritten prompt that solves the problems you found.
```

**What to actually do:**

Don’t try to fix all six at once. Pick the one that wastes the most of your time.

For most people, it’s #1 (underspecification) or #2 (regeneration).

Take one prompt you use all the time—the weekly report, the customer email, whatever you do repeatedly—and fix that one problem in it.

Save the fixed version. Use it next time. See if it’s better.

If it is, pick the next problem.

**Here’s what I know:**

You’re not bad at this. These patterns just aren’t obvious until someone maps them out.

Now you know what they are. You know the fixes. And when something breaks, you have a way to figure out which problem you’re actually dealing with.

That’s the shift—from “why doesn’t this work?” to “oh, this is problem #3” to “here’s how to fix it.”

Start with one. Fix it. That’s enough.

[![](https://substackcdn.com/image/fetch/$s_!wZlJ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F23dd97d3-0ff1-4603-9762-45fe463bce72_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!wZlJ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F23dd97d3-0ff1-4603-9762-45fe463bce72_1024x1024.png)
