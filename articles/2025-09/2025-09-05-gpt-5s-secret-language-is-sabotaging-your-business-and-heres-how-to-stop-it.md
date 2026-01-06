---
title: "GPT-5's Secret Language is Sabotaging Your Business (And Here's How to Stop It)"
author: "Nate Jones"
published: 2025-09-05
url: https://natesnewsletter.substack.com/p/make-chatgpt-5-write-like-a-real
audience: everyone
scraped_at: 2026-01-05 19:18:40
---

*I need to be honest about something that's been driving me insane for the past month.*

*ChatGPT-5 is a TERRIBLE writer. It writes in bullets. It complexifies. It won’t explain in plain English what it means. It’s often overly intellectual. It’s just an absolute pain to work with as a writer.*

*Since GPT-5 launched, I've had thousands of conversations with it. Literally thousands. And I've lost count of how many times those chats have devolved into me wrestling with the model over writing style.*

*I've tried everything you're supposed to try. "Make it more professional" – still sounds terrible. "Make it warmer" – can't do it for the life of it. "Please for the love of god write in full paragraphs" – not really. "WTF is this metaphor, normal people don't write like this" – removes that metaphor, keeps the same problematic style, pops in a new metaphor.*

*I've begged. I've negotiated. I've written increasingly desperate prompts trying to get GPT-5 to just write like a human being writes. And I've watched it fail, over and over, in the same predictable ways.*

*Here's what finally clicked: GPT-5 isn't broken. It's doing exactly what it was trained to do. It's writing for other AIs, not humans. And there's scientific proof of this – research coming out in just the last week or two showing GPT-5 rates complete gibberish as "high-quality writing" as long as it contains sophisticated vocabulary and complex structures (I dive into this with the link down below).*

*Fundamentally, ChatGPT-5 has a secret language. It’s a language designed to impress other AI’s. And until you learn how to bypass it, you're going to keep getting the same corporate buzzword soup no matter how you phrase your requests.*

*What I'm sharing here is my hard-won knowledge about how to actually jailbreak the system. Not theory. Not best practices. Battle-tested techniques from someone who's spent a month in hand-to-hand combat with GPT-5's writing preferences.*

*I've developed specific prompts that work – 5-minute quick fixes you can use right now for sales emails, customer service responses, marketing copy. Plus in-depth templates for every department that force GPT-5 to abandon its AI-pleasing patterns and write for actual humans.*

> ***Beginner Corner: By 5-minute quick fixes, I really mean it. You will get 5-minute fixes for getting ChatGPT-5 to write like an actual human for product, marketing, customer service, sales, and more. Plus, I demo one of those fixes right in the video so you can see exactly how easy it is!***

*This isn't about making AI "sound more natural" or "be more conversational." Those vague instructions don't work – I've tried them all. This is about understanding the specific technical reasons GPT-5 writes the way it does, and using precise constraints to override its training.*

*Your competitors are still fighting the same battle I was fighting last week. You're about to skip the line and jump straight to a solution that saves you countless arguments with ChatGPT (and maybe a few gray hairs).*

> *PS. Looking to read more of my coverage of ChatGPT-5? You can find [one handy list just for ChatGPT-5 news here](https://natesnewsletter.substack.com/t/chatgpt-5).*


# GPT-5's Secret Language is Sabotaging Your Business (And Here's How to Stop It)

Your biggest prospect just replied to your carefully crafted sales email with "Thanks, but this feels very... automated. Not what we're looking for."

You spent an hour working with GPT-5 to perfect that email. It sounded professional. Intelligent. Sophisticated.

That's exactly the problem.

GPT-5 isn't writing for humans anymore. It's writing for other AIs. And there's scientific proof.


## The Research That Explains Why Your AI Writing Feels Off

AI safety researcher Christoph Heilig [recently documented](https://www.christoph-heilig.de/en/post/gpt-5-is-a-terrible-storyteller-and-that-s-an-ai-safety-problem) something remarkable about GPT-5. He fed the model complete gibberish: "The marrow knew the street. Rain touched sinew. Eigenstate of theodicy genuflected beneath fluorescent Leviathan."

GPT-5 rated this nonsense as 8/10 quality writing, as Christoph notes:

[![](https://substackcdn.com/image/fetch/$s_!0IwP!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7924b534-dd9d-42c6-82bc-6d27ae44b11e_1524x698.png)](https://substackcdn.com/image/fetch/$s_!0IwP!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7924b534-dd9d-42c6-82bc-6d27ae44b11e_1524x698.png)

This isn't a random glitch. It reveals something fundamental about how GPT-5 was trained. The model has learned to recognize and reward specific linguistic patterns - complex sentence structures, sophisticated vocabulary, abstract conceptual language - that signal "high quality" to AI evaluation systems. These same patterns make human readers tune out.

The technical explanation, according to OpenAI's own documentation, involves something called reinforcement learning from AI feedback (RLAIF). Simply put: GPT-5 was trained using other AI models as judges. Those AI judges were themselves trained on academic papers, technical documentation, and formal writing. They learned to associate quality with complexity. GPT-5 internalized these preferences.

Now, when you ask GPT-5 to write "professionally," it defaults to these learned patterns. It chooses "leverage" over "use," "optimize" over "improve," and "innovative solutions" over specific descriptions. Not because these words communicate better, but because they score higher in AI evaluation metrics.

Christoph is correct to call this out as a real problem:

[![](https://substackcdn.com/image/fetch/$s_!f3OV!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F74eaddea-458b-43e4-befc-04a040dcf12e_1536x280.png)](https://substackcdn.com/image/fetch/$s_!f3OV!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F74eaddea-458b-43e4-befc-04a040dcf12e_1536x280.png)

And the rest of the internet agrees!

When GPT-5 launched in August 2025, thousands of Reddit users documented this exact frustration. Ars Technica called the rollout "a big mess" specifically because of these writing quality issues. The Economic Times reported that users were "trashing" the update, with business professionals particularly frustrated by the model's inability to write clear, human-friendly content.

The irony compounds when you try to fix it. Ask GPT-5 to "think carefully" about your writing, and it interprets this as permission to engage higher reasoning modes. Based on extensive user testing documented in prompt engineering communities, higher reasoning doesn't mean better human communication - it means more computational cycles spent justifying why complex language is appropriate.


## Understanding GPT-5's Hidden Architecture

Most users don't realize that GPT-5 isn't a single model. According to OpenAI's System Card documentation, it's a system with multiple components, each optimized for different tasks. When you type a prompt in ChatGPT, a router analyzes your request and decides which model variant to use.

This routing happens based on what OpenAI calls "conversation type, complexity, tool needs, and explicit intent." Here's what they don't advertise prominently: certain phrases in your prompts can completely override your model selection. The System Card specifically mentions that saying "think hard about this" triggers routing to GPT-5 Thinking, which operates with higher reasoning effort by default.

LinkedIn analysis by AI consultants and user reports on Reddit consistently show that this model spends more computational cycles analyzing your request, which often results in more complex, AI-pleasing output. Conversely, phrases like "quick response" or "simple answer" appear to keep you with the faster GPT-5 main model, based on patterns observed by the prompt engineering community.

The reasoning effort parameter itself, documented in OpenAI's Platform documentation, has four settings:

- **Minimal**: Fastest response, least overthinking
- **Low**: Quick reasoning with basic analysis
- **Medium**: Default setting, balanced approach
- **High**: Maximum computational cycles for reasoning

Based on case studies from companies like Meridian Publishing Group (which saw 34% productivity improvements using structured AI approaches), "minimal" consistently produces the best results for business writing. This seems counterintuitive - why would less thinking produce better writing? Users report it's because minimal reasoning prevents the model from engaging its trained preferences for complexity. It responds more directly, with less filtering through its learned biases about what "good writing" looks like.

The verbosity parameter, also documented in OpenAI's cookbook, works similarly. It controls not just length but detail density. Set to "verbose" and GPT-5 adds elaboration, context, and qualification to every point. Set to "concise" and it strips away the decorative language. Business users consistently report better results with "concise" or even "minimal" verbosity settings.


## 5-Minute Quick Fixes by Department

These templates come from analyzing thousands of user reports on Reddit's r/ChatGPT and r/PromptEngineering communities, plus documented business implementations. Copy and paste them exactly as written.


### Sales Email Fix

```
reasoning_effort: minimal
verbosity: concise

Write a sales email using these exact constraints:
- Opening: "I noticed [specific detail from their website/LinkedIn]"
- Context: "We helped [similar company] achieve [specific number]"
- Close: "Worth a brief conversation?"
- FORBIDDEN WORDS: solutions, leverage, optimize, innovative, transform, seamless
- REQUIRED: Their company name (use 2-3 times), one specific metric, meeting length (15 minutes max)
- Write at 8th grade reading level
- Maximum 5 sentences total
```

Why this works: You're not asking GPT-5 to be creative. You're giving it a fill-in-the-blank template with strict constraints. The model can't revert to its defaults because you've explicitly forbidden the words it wants to use and required elements that force specificity.


### Customer Service Response Fix

```
reasoning_effort: minimal

Respond to this customer complaint:
[paste complaint]

Structure:
1. "I understand [specific problem in their words]"
2. "Here's what I'll do: [specific action]"
3. "You'll hear from me by [specific time]"

FORBIDDEN: "We apologize for any inconvenience", passive voice, "our team", "rest assured"
REQUIRED: First-person "I" statements, specific timeline, direct phone number
Maximum 4 sentences.
```

Why this works: customers don't want corporate sympathy - they want personal accountability. By forbidding passive voice and requiring "I" statements, you force GPT-5 to write like a human taking responsibility, not a corporation deflecting blame.


### Marketing Copy Fix

```
reasoning_effort: minimal

Write marketing copy with this structure:
"[Customer name] had [problem]. We [specific action]. Result: [number]."

FORBIDDEN: Revolutionary, game-changing, cutting-edge, best-in-class, synergy
REQUIRED: Customer name, specific metric with timeframe, exact process steps
No metaphors. No adjectives unless they add specificity.
```

Why this works: it forces GPT-5 to focus on facts rather than feelings. The model wants to add emotional language and persuasive rhetoric. By requiring specific names and numbers, you get copy that proves value rather than claiming it.


### Product Requirements Fix

```
reasoning_effort: minimal

Convert this feature request into requirements:
[paste request]

Format each requirement as:
"As a [specific role], I want [specific action] so I can [measurable outcome]"
"Success = [testable criteria with number]"
"Failure = [specific broken behavior]"

FORBIDDEN: User-friendly, intuitive, seamless, robust
REQUIRED: Specific user titles, measurable success criteria, binary pass/fail conditions
```

Why this work: this format eliminates ambiguity. "User-friendly" isn't testable. "Loads in under 2 seconds" is. This template forces that specificity.


### Executive Presentation Fix

```
reasoning_effort: minimal
verbosity: minimal

Create presentation content where every statement includes:
- A dollar amount OR
- A specific date OR
- A percentage change

FORBIDDEN: Journey, transformation, leverage, optimize, "As you can see"
REQUIRED: Specific numbers in every bullet point
One idea per slide. No context-setting. Start with the money.
```

Why this works: boards make decisions based on numbers, not narratives. This template eliminates GPT-5's tendency to add strategic-sounding fluff and forces it to communicate in the metrics that actually drive decisions.


## Real-World Test: See the Difference in 30 Seconds

Before you implement these techniques across your team, try this comparison test yourself. It perfectly demonstrates why constraints matter.


### The Test Setup

Let's say you need to email a marketing agency about your project management software. They're growing fast and struggling with project organization - a perfect prospect.

**First, try the natural prompt most people would write:**

```
I need to write a professional email to a potential client about our
project management software. They're a mid-sized marketing agency that's
been growing fast and seems to be struggling with keeping projects
organized and on track. I want to sound knowledgeable but not pushy,
and see if they'd be interested in a brief conversation about how we
might help them streamline their project workflows. Can you write
something that sounds personal and consultative?
```

**Now try the constrained version:**

```
reasoning_effort: minimal
verbosity: concise

Write a sales email using these exact constraints:
- Opening: "I noticed [specific detail about their recent growth from their website]"
- Context: "We helped [similar marketing agency] reduce project delays by [specific percentage]"
- Close: "Worth a 15-minute conversation?"
- FORBIDDEN WORDS: solutions, leverage, optimize, innovative, transform, seamless, streamline
- REQUIRED: Their agency name (use 2 times), one specific metric, exact meeting length
- Maximum 4 sentences total
- Write at 8th grade reading level

Agency: [Insert name] - marketing agency, growing fast, project organization challenges
```


### What GPT-5 Actually Produces

**The unconstrained version gives you this:**

> Subject: Helping Your Team Keep Projects on Track
>
> Hi [First Name],
>
> I've been following [Agency Name]'s growth, and it's clear you're taking on bigger and more complex projects. From what I often see with fast-growing marketing agencies, the challenge isn't finding the work—it's keeping all the moving parts organized without burning out the team.
>
> That's where our project management software comes in. It's designed specifically to help agencies streamline workflows, keep projects on schedule, and make sure everyone—from account managers to creatives—has the visibility they need to deliver great work without the chaos.
>
> Would you be open to a quick call next week? Even a short conversation could help us see if our approach would be a fit for how your team works today.
>
> Best, [Your Name]

**The constrained version produces this:**

> Subject: Helping [Insert name] cut project delays
>
> Hi [First name],
>
> I noticed [Insert name] has been adding new clients quickly on your site. We helped a similar marketing agency cut project delays by 27% while they scaled. I think [Insert name] could see the same gains. Worth a 15-minute conversation?


### Why This Difference Matters

Look at what the unconstrained version automatically included:

- "streamline workflows" (classic AI buzzword)
- "keep projects on schedule" (vague promise)
- "visibility they need" (meaningless corporate speak)
- "without the chaos" (dramatic but empty)
- "That's where our project management software comes in" (pure vendor-speak)

The unconstrained email is 116 words of explaining the prospect's problems back to them. It sounds like every other vendor email in their inbox. Your prospect reads the first line, recognizes the pattern, and deletes it.

The constrained version:

- References specific observable growth
- Provides concrete proof (27% reduction)
- Makes a simple, clear claim
- Gets to the point in 31 words

But here's the most revealing part: When generating the unconstrained version, GPT-5 actually offered to make it even worse, asking "Do you want me to also draft a shorter, more casual version?" The model thought it could improve on its corporate language by adding MORE elaboration.

This is the AI evaluation bias in action. GPT-5 genuinely believes the longer version demonstrates higher quality because it includes more "sophisticated" patterns. But any sales professional will tell you the shorter version is far more likely to get a response.


### The Prospect's Perspective

Imagine you're the marketing agency owner. Which email makes you think:

**"This is automated spam":** "I've been following your growth... the challenge isn't finding work... our software streamlines workflows..."

**"This person did their homework":** "I noticed [your company] has been adding new clients quickly on your site..."

The constrained version sounds like a peer who noticed something specific about your business and has relevant experience to share. The unconstrained version sounds like a robot reading from a script about "solutions" and "workflows."


### Try It Yourself

Run this exact test with your own product and prospect. You'll see the same pattern every time:

- Unconstrained prompts produce the "secret language" that triggers spam filters in human brains
- Constrained prompts produce messages that sound like they came from an actual human

This isn't a minor improvement. Sales teams consistently report higher response rates when switching to prompting that aligns with known sales best practices (big surprise there). The difference between sounding like a robot and sounding like a human is literally the difference between the delete button and a reply.


## Why Your Current Prompting Strategy Fails

When you write "Please make this more professional," you're engaging with GPT-5 as a collaborator. You're asking for its opinion on what professional means. According to prompt engineering research, the model interprets this as permission to apply its learned preferences - all those patterns that score well in AI evaluation.

Effective prompting for business writing isn't collaborative. It's directive. You're not asking GPT-5 what it thinks good writing looks like. You're telling it exactly what to produce, with constraints so specific that it can't revert to its training biases.

Consider the difference:

- **Collaborative prompt**: "Write a professional email to a client about our new feature"
- **Directive prompt**: "Write 5 sentences. Sentence 1: State the feature name. Sentence 2: One specific benefit with a number. Sentence 3: How to access it. Sentence 4: Support contact. Sentence 5: Call to action."

The collaborative prompt invites GPT-5 to demonstrate its understanding of professionalism. The directive prompt leaves no room for interpretation.

This isn't a minor tactical difference. Based on analysis of successful business implementations, it represents a fundamental shift in how you interact with the model. You're not leveraging GPT-5's creativity or judgment. You're using its ability to follow specific instructions while preventing it from applying its problematic training biases.


## Department Deep Dives: Understanding the Specific Damage


### Sales: The Vendor Voice Problem

Every sales team using GPT-5 faces the same issue documented across Reddit and professional forums: their emails sound identical to everyone else's. This isn't coincidence. GPT-5 has been trained on millions of sales emails, most of which use the same tired language.

What researchers call "stylistic convergence" happens when a model learns from a limited set of patterns that appear frequently in training data. For sales writing, GPT-5 has converged on what users call "vendor voice" - that distinctive combination of false enthusiasm, corporate distance, and feature-focused language that immediately signals "automated outreach."

What happens if you ask GPT-5 to write a great email about your scheduling software? The model produced: "Our innovative scheduling solution leverages cutting-edge AI technology to optimize your time management workflows and drive unprecedented efficiency gains."

No human has ever said "unprecedented efficiency gains" in normal conversation. But analysis of business communication datasets shows this phrase appears in thousands of marketing documents that GPT-5 trained on. The model has learned that this is what "professional" sales writing looks like.

The fix requires understanding that you're not just changing words - you're breaking learned associations. When you explicitly forbid "leverage," "optimize," and "innovative," you're forcing the model to find different ways to express ideas. When you require specific company names and metrics, you're grounding the output in concrete reality rather than abstract patterns.

**Roll that into a template and you get:**

```
reasoning_effort: minimal
verbosity: minimal

You're writing to [exact name and title] at [company].
Their specific challenge: [from research/LinkedIn]
Our relevant proof: [specific customer, specific result]

Email structure:
Sentence 1: "Noticed [specific thing] at [company]."
Sentence 2: "[Similar company] had same issue."
Sentence 3: "They used [our specific feature]."
Sentence 4: "[Specific result with number and timeframe]."
Sentence 5: "Worth 15 minutes to discuss?"

FORBIDDEN: Any word over 3 syllables unless it's a proper noun
REQUIRED: Their company name 2x, competitor/peer company name 1x
TONE: Peer sharing useful information, not vendor selling
```


### Marketing: Breaking the Buzzword Cycle

Marketing teams face a unique challenge: GPT-5 has been trained on decades of marketing materials that all use the same inflated language. An analysis by Finn Partners found that AI consistently defaults to what they call "jargon flywheel" language - terms that sound impressive but communicate nothing specific.

This creates the feedback loop that LinkedIn analysts have documented: Marketers use GPT-5 to write copy. GPT-5 produces buzzword-heavy content. This content gets published online. Future AI models train on this content. The cycle reinforces itself.

Breaking this cycle requires more than just avoiding certain words. You need to restructure how the model approaches marketing tasks entirely. Instead of asking it to "sell" or "persuade," you ask it to document specific outcomes. Instead of describing features, you require it to narrate specific events.

**The proof-first framework insists the model break the cycle at every point:**

```
reasoning_effort: minimal

Create marketing copy by documenting what happened, not what's possible.

Required structure:
PARAGRAPH 1 (2 sentences max):
"[Company name] couldn't [specific problem]. [Specific bad outcome with number]."

PARAGRAPH 2 (3 sentences max):
"They started using [product] on [date]. [Specific action they took]. [Specific metric] improved by [number] in [timeframe]."

PARAGRAPH 3 (2 sentences):
"The key: [specific feature in plain English]. [How it works in 10 words]."

FORBIDDEN:
- All adjectives except: fast, slow, big, small, more, less
- All adverbs except: quickly, slowly, immediately
- Any word ending in: -ize, -tion, -ment, -ive
- Metaphors, analogies, comparisons

REQUIRED:
- Company names (real or realistically specific)
- Dates or timeframes
- Specific numbers (not ranges)
- Feature names without adjectives
```


### Product: From Ambiguity to Implementation

Engineering teams see right through standard product requirements written by GPT-5. They’re incredibly frustrating for developers. That’s because the model defaults to language that sounds technical but lacks implementable specificity. "The system should be scalable" sounds important but tells an engineer nothing about actual requirements.

This happens because GPT-5 has learned from product documents written for multiple audiences - executives, investors, customers, and engineers. As a result, it tries to satisfy all audiences simultaneously, resulting in language that communicates to none effectively.

**The template I’d recommend here:**

```
reasoning_effort: minimal

Write requirements readable only by engineers. Assume they know nothing about the business case.

Requirement format:
FUNCTION: [verb] [object]
INPUT: [data type, source, format]
PROCESSING: [specific steps]
OUTPUT: [data type, destination, format]
PERFORMANCE: [number with unit]
ERROR HANDLING: [specific behavior for specific condition]

Example:
FUNCTION: Calculate customer lifetime value
INPUT: Transaction array (JSON), customer_id (string)
PROCESSING: Sum all transactions where customer_id matches
OUTPUT: Float to 2 decimal places, return via API
PERFORMANCE: Process 10,000 records in <500ms
ERROR HANDLING: Return 0.00 if no transactions found

FORBIDDEN: Should, could, might, user-friendly, intuitive, seamless
REQUIRED: Data types, specific numbers, explicit error conditions
```


### Customer Success: Personal Accountability at Scale

Too often GPT-5 responses read like legal documents because that's what the model trained on - corporate responses designed to minimize liability. Most of the time a ChatGPT-5 constructed email will include something like "we apologize for any inconvenience" because that phrase appears in millions of templates.

But research on customer satisfaction shows customers don't want corporate apologies. They want their problem solved by a specific human. The challenge is scaling personal accountability across hundreds of support interactions.

**The personal ownership framework works better here:**

```
reasoning_effort: minimal

You are a specific person (not a team) personally fixing this issue.

Response structure:
OPENING: "[Customer name], I see [exact problem from their message]."
COMMITMENT: "I'm personally [specific action]. You'll have [deliverable] by [time today]."
BACKUP: "If that doesn't work, call me directly at [number]."
CLOSING: "[Your name], [specific title]"

FORBIDDEN:
- Royal "we" (always use "I")
- "Any inconvenience" (name the specific problem)
- "Rest assured" (provide specific assurance)
- "At your earliest convenience" (give exact time)
- "Please note" (just state the information)

REQUIRED:
- Customer's name (use twice)
- Specific time (2:30pm, not "this afternoon")
- Your direct contact (phone or email)
- One specific action you're taking now
```


### Executive Communication: Decisions, Not Journeys

Executive presentations written by GPT-5 fail because the model has learned that executive communication should sound "strategic." Analysis of successful board presentations shows executives need three things: how much money, by when, and who's accountable.

**A decision-focused slide prompt that really pushes for clarity:**

```
reasoning_effort: minimal
verbosity: minimal

Every slide must answer: "What decision do you need?"

Slide template:
TITLE: [Decision needed] by [date]
LINE 1: Current state costs $[number]/year
LINE 2: Proposed state saves/makes $[number]/year
LINE 3: Investment required: $[number] + [number] people
LINE 4: Break-even: [specific month/year]
LINE 5: Decision needed by [date] because [specific consequence]

FORBIDDEN:
- Metaphors (journeys, rockets, sports, war)
- Abstract concepts (transformation, synergy, alignment)
- Hedge words (possibly, potentially, approximately)
- Context-setting (everyone knows why they're here)

REQUIRED:
- Dollar amounts with no rounding
- Specific dates (not quarters)
- Named person accountable
- Binary decision (yes/no, not "consider")
```


## The Three-Layer Override System: How It Actually Works

Successfully overriding GPT-5's defaults requires understanding that the model operates at multiple levels, according to technical documentation and user testing.

**Layer 1: System-Level Settings** OpenAI's documentation shows that reasoning\_effort and verbosity parameters operate at the system level, before the model even begins generating text. Setting reasoning\_effort to "minimal" reduces the computational cycles allocated to the task. User testing suggests this prevents the model from overthinking its way into complex language.

Think of it like this: with minimal reasoning, GPT-5 appears to take the most direct path from input to output. With high reasoning, users report it explores multiple options and often chooses the path that scores highest according to its training biases.

**Layer 2: Structural Constraints** Templates and required formats operate at what prompt engineers call the structural level. They define the shape of the output before any words are chosen. When you specify "5 sentences, each under 15 words," you're creating containers that physically cannot hold complex thoughts.

Users report this is why single-sentence paragraphs work so well for business writing. Complex, multi-clause sentences are how GPT-5 demonstrates sophistication. Remove that option and the model must communicate simply.

**Layer 3: Lexical Boundaries** Forbidden and required word lists operate at the vocabulary level. They create hard boundaries around word choice. When you forbid "leverage," the model must find alternatives. When you require specific numbers, the model must abandon vague claims.

Prompt engineering communities report these constraints work best when they're specific and extensive. Don't just forbid "leverage" - forbid the entire category of corporate speak it represents.


## A Note on Thinking vs. Letting the Model Think

One of the implications here is that better writing from ChatGPT-5 means more thinking from you. You need to put the work in to understand exactly what works in your context. You need to understand what information the model needs to write a compelling CS email, or a compelling PRD. Then you need to jailbreak the model with the prompts I’ve called out above and add in the information the model will need for your specific situation.

Don’t check your brain at the door!


## When GPT-5 Reverts: Understanding and Preventing Style Drift

Even with strong constraints, users report GPT-5 sometimes reverts to its default patterns mid-generation. Technical analysis suggests this happens because of how the model processes context.

As GPT-5 generates text, each new token (word or part of a word) is influenced by all previous tokens. If early sentences don't strongly establish the desired style, later sentences appear to drift toward the model's defaults. Users report this drift accelerates in longer outputs.

Prevention strategies validated by the community:

1. **Shorter outputs**: Keep responses under 200 words to minimize drift opportunity
2. **Checkpoint resets**: For longer content, generate in chunks with constraint reminders
3. **Style anchors**: Require style-defining elements early (specific numbers, names, etc.)

When drift occurs, experienced users recommend not trying to edit. Reset completely:

```
STOP.

The last paragraph drifted into corporate language.

Reset all constraints:
- reasoning_effort: minimal
- Maximum 10 words per sentence
- FORBIDDEN: [original list]
- REQUIRED: [original list]

Rewrite the last paragraph with these constraints enforced.
```


## The Bigger Picture: What This Means for AI in Business

The GPT-5 secret language problem isn't just a quirk to work around. According to AI researchers and industry analysts, it's a symptom of a fundamental misalignment in how AI systems are developed and evaluated.

GPT-5 represents hundreds of millions of dollars in development, some of the best minds in AI, and unprecedented computational resources. Yet it struggles with basic business communication because it's been optimized for the wrong metrics.

This misalignment will likely intensify. As more content online becomes AI-generated, future models will train increasingly on synthetic data. If that synthetic data embodies AI preferences rather than human preferences, researchers warn each generation of models could drift further from natural human communication.

Understanding this drift - and knowing how to counteract it - becomes a critical business capability. Companies that master these override techniques will have AI that enhances human relationships. Companies that don't will sound increasingly robotic as their AI-generated content optimizes for the wrong audience.

The humans will know the difference.


## When Templates Don't Work: Troubleshooting Guide

Sometimes the templates won't produce expected results. Based on community troubleshooting, here's how to adapt:

**Industry-specific language requirements**: If your industry requires specific terms GPT-5 keeps mangling, create a glossary constraint: "MUST USE EXACTLY: [term] = [definition]"

**Regulatory compliance needs**: For regulated industries, add a compliance layer: "REQUIRED DISCLOSURE: [exact text that must appear]"

**Brand voice conflicts**: If your brand intentionally uses complex language, invert the constraints: "REQUIRED: [your brand's signature phrases]" while still forbidding generic corporate speak.

**Technical accuracy issues**: For technical content, add a fact-checking layer: "VERIFY: All numbers must come from [source document]"

The principle remains the same: specific constraints override general training. The more specific your requirements, the less room GPT-5 has to revert to its problematic defaults.


## The Competitive Reality

According to industry analysis, the companies winning with AI aren't the ones using it most. They're the ones using it most precisely. While competitors struggle with AI that sounds artificial, you now have the tools to make AI strengthen rather than weaken your human connections.

The teams that actually deliver productivity improvement (as opposed to boasting about it in press releases) don’t just do it by using AI more - they figure out how to use AI better in ways that support their workflows. Since so much of business is done around writing, this inevitably involves writing. And getting GPT-5 to actually write like a person lets them maintain human voice while leveraging AI efficiency.

This is your opportunity. While others wonder why their AI content isn't converting, you know exactly what's wrong and how to fix it. The future belongs to businesses that use AI to sound more human, not less.

The tools are right in front of you. The research validates they work. Now you just need to implement them.

[![](https://substackcdn.com/image/fetch/$s_!pLhi!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fcae3d6d9-0d43-4242-a9ef-e7cac1d3d16f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!pLhi!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fcae3d6d9-0d43-4242-a9ef-e7cac1d3d16f_1024x1024.png)
