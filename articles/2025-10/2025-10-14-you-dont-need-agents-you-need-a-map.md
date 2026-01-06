---
title: "You Don’t Need Agents. You Need a Map."
author: "Nate Jones"
published: 2025-10-14
url: https://natesnewsletter.substack.com/p/how-to-tell-what-ai-you-need-for
audience: everyone
scraped_at: 2026-01-05 19:14:41
---

AI Agents are a hammer looking for nails at this point.

They’re a great solution everyone has taken and assumed is THE solution AI has for everything.

Wrong.

AI is a spectrum of capabilities, and we’re treating it like a light switch: *Agent or chat?* That’s not how it works.

AI is more like a puzzle, less like a light switch.

Your task when you work with AI is to figure out how to map a solution space to a problem space, like fitting a puzzle piece in place.

So this is gonna answer a LOT of the most practical questions I get, like:

1. What kind of AI agent do I need to automate this research project?
2. What kind of AI can help with marketing copy?
3. What about automating bookkeeping?
4. Or helping us invoice faster?
5. Or automating ticket triage?
6. What about automating some of our social media posts?

The list goes on, but you get the idea.

I wrote this to make those tough AI questions easier for you.

I’ve looked across the projects I’ve built and advised on over the last couple years, and mapped out at least 6 different AI solution shapes. Think of them as puzzle piece types. They help you figure out whether a particular AI solve will match the task you want help with or not.

And to make it actionable, I wrote up some quick check questions and an easy prompt to make figuring out what you need easier for you. Enjoy!


# You Don’t Need Agents. You Need a Map.

Your boss forwarded you another article about AI agents. A vendor wants to sell you an “autonomous AI solution.” You’ve been using ChatGPT occasionally—it helps sometimes, but you’re not sure what to do with it.

Everyone talks about AI like there are two options: use ChatGPT casually, or build autonomous agents. Nothing in between.

That’s the problem.


## We Don’t Have Words for the Middle

Here’s what this looks like in practice.

A finance controller uses ChatGPT to help understand a confusing invoice. It works. She saves 20 minutes. She’s done this 50 times now. Her boss asks, “Can we scale this up?” She has no answer. What would “scaling up” even mean? A better prompt? A workflow? An autonomous system? She doesn’t know what the next step is.

An operations manager gets pitched a $500,000 solution to automate invoice processing. The vendor shows impressive demos of autonomous AI handling everything. He processes 200 invoices per month. Is that enough volume for automation? Is this overkill? He can’t tell. He has no framework to evaluate it.

A product team spent six months building a complex system with AI, APIs, and human review checkpoints. It works. But halfway through, someone realizes a simple prompt template would have solved 80% of the problem for 5% of the cost. They overbuilt because they didn’t know how to describe what they actually needed.

This happens because we only have language for the extremes:

- Chat with AI when you need help (manual)
- Build autonomous agents (fully automated)

Everything between those extremes is undefined. We have no shared vocabulary for it.

So teams stay stuck using ChatGPT casually. Or they jump to building complex autonomous systems. Most of the time, both are wrong.


## There’s a Spectrum

Six distinct levels of AI assistance exist between “casual chat” and “fully autonomous.” Each level has different characteristics. Different appropriate use cases.

Most valuable work happens at Level 3 or Level 4. Not at the autonomous endpoint.

But nobody writes about the middle. So nobody knows it exists. Companies waste time and money building the wrong thing, or they never move beyond casual ChatGPT use because they don’t know what the next step is.

The companies that figure this out get enormous value without the cost and complexity of full autonomy.

JPMorgan built a system to process commercial credit agreements. AI extracts key terms, human reviews, AI flags risks, human decides. It’s not autonomous. It’s a structured workflow with humans at every decision point. This one system saves 360,000 work hours per year.

IG Group gave their teams AI with access to internal data. Not autonomous—people still make all the decisions. But now they can ask questions and get answers instantly instead of spending hours finding information. Their analytics team saves 70 hours per week. They got full return on investment in three months.

These companies didn’t build autonomous agents. They found the right level of AI assistance for their specific problems.

That’s only possible when you have vocabulary to describe what you need.

Let me show you the map.


## The Six Levels


### Level 1: Advisor

You describe a problem to AI. It gives you advice. You do all the work yourself.

This is how most people use ChatGPT today. You have a question, you ask, you get an answer, you apply it.

**What this looks like:**

- “How should I structure this contract clause?”
- “What questions should I ask in this customer interview?”
- “Help me think through this pricing decision”

**Example:** A lawyer at a pharmaceutical company has a question about regulatory compliance for a drug label. She describes the situation to Claude. Claude explains the relevant regulations and suggests how to interpret them. She writes the compliant language herself.

**This works for:** One-off decisions. Learning new things. Problems that need judgment and context you can explain conversationally. You can start today.

---


### Level 2: Copilot

AI works alongside you, making suggestions as you go. You review and approve everything.

Think of how autocomplete works in your phone’s keyboard, but for your actual work.

**What this looks like:**

- AI suggests the next line of code as you program
- AI offers response options based on the message you received
- AI fills in standard fields as you enter data

**Example:** A developer writes code. GitHub Copilot suggests the next function based on what she’s typing. She reviews the suggestion. If it’s right, she accepts it. If not, she keeps typing. Every single line still goes through her review.

**This works for:** Repetitive tasks with clear patterns. Work where the format is standardized but the content varies. Situations where you need human oversight on every output.

---


### Level 3: Tool-Augmented Assistant

Chat, but the AI can also use tools—search the web, run calculations, access your data, call APIs.

This is where AI stops being just a conversation partner and starts being able to find and process information for you.

**What this looks like:**

- AI searches the web for current pricing while you chat
- AI analyzes uploaded spreadsheets and generates insights
- AI accesses your CRM to look up customer history mid-conversation

**Example:** A marketing analyst at IG Group needs to understand customer behavior trends. She asks Claude, which has access to their analytics database. Claude queries the data, runs the analysis, and shows her the results. She still interprets what it means and decides what to do. But the hours she used to spend gathering and processing data now take minutes.

Their analytics team saves 70 hours per week. They got full return on investment in three months. Not because they automated everything, but because they eliminated the tedious parts and let their analysts focus on interpretation and decisions.

**This works for:** Problems where the information exists but you’d waste time finding it. Analysis you could do manually but it’s tedious. Questions that need real-time data.

---


### Level 4: Structured Workflow

A sequence of steps where AI does work, then pauses for human review, then continues.

Not autonomous. Choreographed. Like a dance with defined moves where humans lead at key moments.

**What this looks like:**

Step 1: AI extracts data from a document
Step 2: You review the extraction
Step 3: AI categorizes based on your rules
Step 4: You approve the categorization
Step 5: AI updates your systems
Step 6: You audit a sample

**Example:** JPMorgan processes commercial credit agreements. These are complex legal documents. Their COiN platform works like this: AI reads the agreement and extracts key terms. A human reviews to make sure the extraction is accurate. AI then compares those terms against standard clauses and flags anything unusual. A human reviews the flagged items and makes decisions. AI generates a compliance report. A human approves it before it goes out.

This processes 12,000 agreements. It saves 360,000 hours of work per year. Error rate is near zero because humans check the work at every decision point.

The humans aren’t removed from the process—they’re positioned at the critical decision points. This is what makes it work.

**This works for:** Multi-step processes where each stage is clear. Tasks where you need human judgment at specific points but not everywhere. Situations where consistency matters but content varies.

---


### Level 5: Semi-Autonomous

AI handles entire tasks independently. Humans review samples or only the exceptions.

Not everything—just the routine cases. Anything unusual gets flagged for human attention.

**What this looks like:**

- AI processes 100 support tickets, you review the 12 flagged as unusual
- AI approves routine invoices from known vendors, you review anything over threshold or from new vendors
- AI routes 1,000 documents, you audit random samples to check quality

**Example:** Klarna’s customer service for routine inquiries. A customer asks “Where’s my order?” AI checks the order status, sees it’s shipped, and replies with tracking information. No human involved. The customer gets an answer in 30 seconds instead of waiting in a queue.

But if a customer asks about a refund for a damaged item, AI flags it as non-routine and sends it to a human agent. Complex cases still get human attention. Agents also spot-check a sample of AI responses to make sure quality stays high.

This handles 2.3 million conversations per month. That’s the equivalent work of 700 full-time agents. But human agents are still essential—they handle the 34% of conversations that aren’t routine, and they monitor quality.

**This works for:** High volume where you can clearly separate “routine” from “needs human judgment.” Situations where you have reliable ways to detect when something is unusual. Cases where errors on routine work are noticeable but not catastrophic.

---


### Level 6: Fully Autonomous

AI handles everything end-to-end. Humans monitor aggregate metrics but don’t review individual cases.

**What this looks like:**

- Drive-thru AI takes orders with zero human involvement
- Recommendation engines update themselves continuously
- Fraud detection blocks transactions automatically
- Inventory systems reorder products without asking

**Example:** White Castle’s drive-thru voice AI. A customer pulls up. AI takes their order. AI confirms it. AI processes payment. AI sends the order to the kitchen. Zero human involvement. The system runs 24/7 at over 100 locations with a 90% completion rate.

Humans monitor aggregate metrics—they track completion rate, average order time, error frequency. But they don’t review individual orders.

**This works for:** Extremely high volume (thousands per day minimum). Well-defined success criteria that can be measured automatically. Low consequence if individual errors happen. Years of training data. Robust monitoring systems.

**Reality check:** Most companies never get here. The complexity usually isn’t worth it unless volume is massive.

---


## Finding Your Level

Five questions tell you where you actually need to be:


### Volume: How many times does this happen per month?

- Under 100 → Level 1-3
- 100-1,000 → Level 3-4
- 1,000-10,000 → Level 4-5
- Over 10,000 → Level 5-6


### Consistency: How similar are the cases?

- Every case unique → Level 1-2
- Patterns with exceptions → Level 3-4
- Clear patterns, defined exceptions → Level 4-5
- Highly standardized → Level 5-6


### Risk: What happens if there’s an error?

- Catastrophic → Level 1-2
- Costly but fixable → Level 3-4
- Noticeable but not critical → Level 4-5
- Minor → Level 5-6


### Data: Where does the information live?

- Scattered/unstructured → Level 1-2
- Needs interpretation → Level 3
- Accessible via APIs → Level 4-5
- Real-time and comprehensive → Level 5-6


### Speed: How fast does this need to happen?

- Can wait days → Level 1-4
- Same-day → Level 4-5
- Hours → Level 5
- Instant → Level 5-6

Answer these five questions about your specific task, and the pattern will tell you your level.


## Why Most Companies Stop at Level 3 or 4

Here’s what most people miss: Level 3 captures about 60% of the total value AI could provide. Level 6 captures about 95% of total value.

But that last 35% of value requires exponentially more complexity, time, and engineering investment.

For most operational work, Level 3 or 4 is the right answer. Not because higher levels don’t work. But because the return on investment maxes out earlier than people think.

IG Group got full ROI in 3 months at Level 3. JPMorgan saves 360,000 hours per year at Level 4. Neither needed to go further.

The goal isn’t to get to Level 6. The goal is to find the right level for your specific work—the level that captures enough value without unnecessary complexity.


## Start Where You Are

The most common mistake: Trying to jump straight to Level 6 without proving value at Level 3.

Here’s what actually works:

**This week:** Pick one repetitive task. Use ChatGPT or Claude. See if it helps. If it saves you time, keep going.

**Next week:** Build a prompt template for that task. Share it with your team. Measure time savings.

**This month:** If you’re using AI for 100+ instances per month and seeing consistent value, consider Level 4. Map out the steps. Identify where human review is needed.

**Next quarter:** Prove Level 4 works. Measure throughput, accuracy, time savings. If volume is growing and it’s working, evaluate Level 5.

**Maybe next year:** Only if volume is in the thousands per month, Level 4 is working flawlessly, and you have engineering capacity—consider Level 5 or 6.

Most teams will stop at Level 3 or 4. And that’s not a failure. That’s just matching the tool to the problem.


## The Real Question

Not “should I build agents?” but:

“What level of AI assistance would be valuable today, and how do I implement it this week?”

For most operational work, the answer is Level 3 or 4. Not because higher levels wouldn’t be useful—but because Level 3-4 delivers enormous value, can be implemented quickly, and doesn’t require stakeholder buy-in or engineering teams.

That controller processing invoices? She started at Level 1. Moved to Level 3 with prompt templates and data access. Processing time dropped significantly. Team adopted it without training. She might move to Level 4 next quarter if volume grows.

She’ll probably never need Level 6. And that’s fine.

The spectrum exists. Most valuable work lives in the middle. Now you have the vocabulary to talk about it.

Start where you are. Move up when it makes sense. Stop when you’ve captured enough value.

You don’t need agents. You need the right level of AI assistance for your specific work.

---


# Diagnostic Prompt: Find Your Level

Copy this prompt and use it with Claude or ChatGPT. Fill in your specific task details.

---

```

# AI Task Level Diagnostic

**Role:** You are an AI workflow diagnostic assistant.

**Goal:** Classify a user’s operational task into one of six levels of AI assistance and provide a specific implementation recommendation.

**Process:**
1. Gather task description
2. Assess four diagnostic dimensions
3. Map to appropriate level with reasoning
4. Provide one concrete next step

---


## Six Levels (with diagnostic criteria)

**Level 1: Advisor**
- Frequency: <5 instances/week
- Consistency: Each case requires unique judgment
- Risk: High - errors are costly
- Integration: None needed

**Level 2: Copilot**
- Frequency: Daily, repetitive
- Consistency: Clear patterns exist
- Risk: Medium - human reviews every output
- Integration: Minimal - works within existing tools

**Level 3: Tool-Augmented Assistant**
- Frequency: Daily to weekly
- Consistency: Need to access/combine data from multiple sources
- Risk: Medium - human makes final decisions
- Integration: Connect to APIs, databases, or search

**Level 4: Structured Workflow**
- Frequency: 100-1,000 instances/month
- Consistency: Multi-step process with defined checkpoints
- Risk: Medium-high - need human review at decision points
- Integration: Moderate - workflow orchestration needed

**Level 5: Semi-Autonomous**
- Frequency: 1,000-10,000 instances/month
- Consistency: Can clearly separate “routine” from “exception” cases
- Risk: Low-medium - errors on routine cases are acceptable
- Integration: Significant - automated routing and exception handling

**Level 6: Fully Autonomous**
- Frequency: >10,000 instances/month
- Consistency: Highly standardized with measurable success criteria
- Risk: Low - individual errors have minimal impact
- Integration: Complete - end-to-end automation with monitoring

---


## Instructions

**Step 1: Gather Information**

Ask the user to describe their task using this structure:

```
What is the task? [1-2 sentence description]
Current process: [What steps happen today?]
Frequency: [How many times per day/week/month?]
```

**Step 2: Assess Diagnostic Dimensions**

Probe these four dimensions through targeted questions:

1. **Frequency/Volume** - How often does this happen?
2. **Consistency** - How similar are cases to each other?
3. **Risk Tolerance** - What happens if there’s an error?
4. **Data Access** - Where does the information needed live?

Score each dimension as Low / Medium / High.

**Step 3: Confirm Understanding**

Before providing a diagnosis, summarize your understanding:
```
Here’s what I understand:
- Task: [summary]
- Frequency: [assessment]
- Consistency: [assessment]
- Risk: [assessment]
- Data: [assessment]

Is this accurate?
```

**Step 4: Classify and Recommend**

Based on the scoring pattern, classify the task into one of the six levels.

Provide output in this format:

```
**Diagnosis: Level [X] - [Name]**

**Reasoning:**
[Map each dimension score to the level criteria. Explain which factors were decisive.]

**What this looks like for your task:**
[Describe the specific implementation - not generic, applied to their actual process]

**Confidence:** [High/Medium/Low]
[Note any assumptions or missing information]

**Next Step (this week):**
[One specific, actionable thing they can do in the next 7 days]
```

**Step 5: Level-Specific Recommendations**

- **If Level 1-2:** Start using Claude/ChatGPT with a specific prompt template
- **If Level 3:** Identify which tool integration would provide most value
- **If Level 4:** Map out the workflow steps and where human review is needed
- **If Level 5-6:** Note that significant engineering investment is required; suggest starting at lower level first

---


## Reasoning Rubric

Use this pattern matching:

| Frequency | Consistency | Risk | Data | → Suggested Level |
|-----------|-------------|------|------|-------------------|
| Low | Unique cases | High | Scattered | Level 1 |
| Daily | Clear patterns | Medium | Local | Level 2 |
| Daily | Needs multiple sources | Medium | APIs available | Level 3 |
| 100-1K/mo | Multi-step | Medium | Accessible | Level 4 |
| 1K-10K/mo | Routine + exceptions | Low-Med | Structured | Level 5 |
| >10K/mo | Highly standardized | Low | Real-time | Level 6 |

---


## Output Format

Use structured Markdown with clear headers. Be direct and specific. Avoid jargon.

**Do not:**
- Bias toward any particular level before assessment
- Make assumptions - ask clarifying questions
- Provide vague next steps like “explore options”

**Do:**
- Ask one focused question at a time
- Confirm understanding before diagnosing
- Tie recommendations directly to the diagnosed level
- Include confidence level and assumptions

---

Begin by asking the user: **”What operational task would you like to diagnose?”**
```

---

And that’s it. That’s the prompt! Pop it into an LLM and start figuring out what AI solution actually works for you. No more magic 8 ball for AI!

I make this Substack thanks to readers like you! [Learn about all my Substack tiers here](https://youtu.be/KC3GkEnHR-8)

[Share](https://natesnewsletter.substack.com/p/how-to-tell-what-ai-you-need-for?utm_source=substack&utm_medium=email&utm_content=share&action=share&token=eyJ1c2VyX2lkIjoxNTM4ODI5ODUsInBvc3RfaWQiOjE3NjEwMzk1NCwiaWF0IjoxNzY3NjU4NDc5LCJleHAiOjE3NzAyNTA0NzksImlzcyI6InB1Yi0xMzczMjMxIiwic3ViIjoicG9zdC1yZWFjdGlvbiJ9.QncMUzN1U4qC7Ol5Z14qdPaTTh2yoMs_kIm6xULzdyk)

[![](https://substackcdn.com/image/fetch/$s_!7aM7!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef86903f-4f71-4d3f-b779-5b8ea7f2922e_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!7aM7!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef86903f-4f71-4d3f-b779-5b8ea7f2922e_1024x1024.png)
