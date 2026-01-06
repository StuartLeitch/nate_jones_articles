---
title: "The Beginner's Handy Guide to Prompt Engineering"
author: "Nate Jones"
published: 2025-09-09
url: https://natesnewsletter.substack.com/p/the-only-prompt-engineering-guide
audience: everyone
scraped_at: 2026-01-05 19:18:27
---

*You asked for everything I know about prompting in one place: here it is!*

*Over the past year, I've written dozens of posts about prompt engineering—deep dives into specific techniques, comparisons of different AI models, advanced strategies for complex tasks. And consistently, week after week, I get the same request in my inbox:*

*"Nate, can you just summarize everything you know about prompting in one clear post? Something I can bookmark and actually follow along with?"*

*The request usually comes with a qualifier: Some readers are complete beginners who feel overwhelmed by scattered tips and tricks. Others are already getting good results but know they're missing something. And many of you are somewhere in between—you've had both brilliant successes and baffling failures with AI, and you want to understand why.*

*So this is that post. Everything I've learned about prompt engineering, organized from the absolute basics to advanced techniques, all in one place. If you've never written a prompt before, you can start at the beginning and work your way through. If you're already comfortable with AI, you can jump to the sections that fill your gaps. And if you're looking for that one definitive guide to share with your team or bookmark for reference—this is it.*

*I've structured this to be both a tutorial and a reference guide. Read it straight through to build your skills systematically, or jump to specific sections when you need them. Either way, you'll have everything you need to turn AI from a frustrating puzzle into a reliable tool that actually saves you time.*

*I’ve structured this around three key pieces:*

1. ***The Beginner’s Handy Guide:** An introductory post in the substack that lays out how to get started and introduces my two longer guides (below)*
2. ***The Complete Beginner’s Guide:** An in-depth guide to prompting aimed specifically at beginners, updated for 2025!*
3. ***The A-to-Z Prompt Engineering Guide:** A desk reference guide to prompting, including dozens of pages on advanced prompting techniques, including team-level insights*

*When I say everything guys, I mean **everything**.*

*But first things first, let’s start with the fundamentals and build from there…*


#### *[Grab the complete beginner’s guide to prompt engineering](https://docs.google.com/document/d/1YCeysmh8ceXLgfMz6ZpM2GRRov5mV0YmhN6vgZCkj74/edit?usp=sharing)*

This beginner's guide to prompt engineering teaches you how to communicate effectively with AI systems like ChatGPT, Claude, and Gemini by crafting clear, specific instructions (prompts) that get you the results you want. The guide explains that AI doesn't actually "think" or understand implied meaning—it recognizes patterns and predicts responses based on exactly what you write—so being precise matters more than being clever or lengthy.

You'll learn practical techniques ranging from the CLEAR framework (Context, Length, Examples, Audience, Role) for structuring prompts, to methods like few-shot prompting (providing examples), chain-of-thought prompting (asking AI to show its reasoning), and persona prompting (assigning AI a specific role).

The guide also covers how different AI models have distinct "personalities" and strengths, how to adjust parameters like temperature for creativity versus precision, and advanced strategies like prompt chaining for complex tasks. Ultimately, it's about transforming AI from a frustrating tool into a reliable partner through practice, persistence, and understanding that good prompt engineering is simply the skill of giving clear directions—much like telling someone to "go to Safeway on Main Street and buy organic milk" rather than just saying "go to the store."


#### *[Grab the complete A-to-Z Prompt Engineering Guide here](https://docs.google.com/document/d/1bMo18rdwXewRL3dBhKIsBx7jsCAX3aILD5SuRqIWjp4/edit?usp=sharing)*

This comprehensive guide takes you on a complete journey through prompt engineering—the skill of crafting effective instructions for AI language models—starting from the absolute basics and progressing all the way to cutting-edge enterprise techniques. Whether you're just curious about how to get better responses from ChatGPT or you're an engineer building production AI systems, you'll find practical, hands-on guidance tailored to your level.

The guide begins by demystifying how AI models interpret your requests and teaches fundamental techniques, then gradually introduces more sophisticated methods like chaining multiple prompts together, augmenting AI with external knowledge databases, and even orchestrating multiple specialized AI agents to collaborate on complex problems.

Beyond just techniques, it addresses real-world concerns like preventing prompt injection attacks, evaluating prompt performance systematically, managing costs, and building maintainable prompt libraries that teams can version and deploy like code. With its structured learning path, domain-specific examples for fields like marketing and legal analysis, and a 2025 addendum covering the latest security practices and personalization strategies, this guide essentially transforms the "art" of talking to AI into a reliable engineering discipline you can master step by step.

---


# **The Beginner's Handy Guide to Prompt Engineering**


## **What Is Prompt Engineering?**

Prompt engineering is simply learning how to write clear instructions for AI chatbots. The difference between getting frustrating, generic responses and getting exactly what you need often comes down to how you ask.

Think of it like giving directions. You could say "go to the store" (vague) or "go to the Whole Foods on Main Street and buy organic milk" (specific). With AI, specificity wins every time.

**Key Reality Checks:**

- AI responds to exactly what you write, not what you mean
- Clear and specific beats long and complex
- Different tasks need different approaches
- There's no "perfect prompt" that works for everything


## **How AI Chatbots Actually Work**

AI chatbots like ChatGPT, Claude, and Gemini are pattern-matching systems. They've been trained on millions of texts and predict what words should come next based on patterns they've learned.

**What This Means for You:**

- They don't "understand" - they recognize patterns
- They have no memory between conversations
- They can confidently state incorrect information
- Being specific helps them find the right pattern

**Context Windows:** Think of this as the AI's "working memory" - how much it can consider at once. Most modern chatbots can handle very long conversations, but they still can't remember yesterday's chat unless you tell them about it.


## **The CLEAR Framework**

Every good prompt should be **CLEAR**:

**Context** - Provide relevant background

**Length** - Specify how long you want the response

**E**xamples - Show what you're looking for

**A**udience - Who is this for?

**R**ole - What expertise should the AI use?

*With 2025 reasoning models, you can mix these up a bit for simple asks and it’s entirely fine. If you’re being precise with a big prompt, the order below works better.*


### **Before and After CLEAR**

**Vague Request:** "Help with email"

**CLEAR Request:**

Role: Professional business writer

Context: I need to decline a meeting invitation politely

Length: 2-3 sentences

Examples: Friendly but clear, like "I appreciate the invitation..."

Audience: My colleague who I work with regularly

The CLEAR version gets you exactly what you need on the first try.

> *Note: Advanced readers and regular followers of the substack will notice I’ve recommended more than one framework for prompting over the last year or so. That’s intentional. Why?*
>
> *Because first, models evolve. Second, different frameworks are memorable for different audiences. And third, each framework has slightly different emphases, which is useful for developing an advanced understanding over time.*
>
> *So beginners: CLEAR is great and will go a long way.*
>
> *If you’re still reading this and you’re advanced go look in the A-to-Z guide for much much more detail and nuance.*


## **Essential Techniques for Beginners**


### **1. Zero-Shot: Just Ask Clearly**

When you don't need to show examples, just be specific about what you want.

"Summarize this article in 3 bullet points focusing on the main findings, written for someone with no technical background"

Use this for: Simple tasks, straightforward questions, quick translations


### **2. One-Shot: Show One Example**

Give one example to set the pattern you want.

"Convert these meeting notes into action items.

Example:

Note: Sarah mentioned she'll review the budget by Friday

Action: Review budget (Owner: Sarah, Due: Friday)

Now convert: Tom said he'd contact the vendor about pricing tomorrow"

Use this for: Specific formats, consistent style, email templates


### **3. Few-Shot: Multiple Examples for Complex Patterns**

Provide 2-3 examples when you need specific style or approach.

"Write product descriptions like these:

Product: Wireless earbuds

Description: "Crystal-clear calls from your couch to your commute. 8-hour battery life keeps up with your day."

Product: Smart watch

Description: "Your health coach, assistant, and style statement on your wrist. Tracks what matters, ignores what doesn't."

Now write one for: Bluetooth speaker"

Use this for: Creative writing, maintaining tone, complex formatting


### **4. Chain-of-Thought: Make AI Show Its Work**

Ask the AI to think through problems step-by-step.

> ***Be careful here!** Chain of thought prompting is not particularly useful with reasoning models, but it is useful with non-reasoning models and enough people use non-reasoning models that I’m choosing to present it here. If your model takes awhile to think, don’t use this technique.*

"I need to choose between two job offers. Please analyze them step by step:

Job A: $80k salary, 10 min commute, small company, great culture

Job B: $95k salary, 45 min commute, large company, standard benefits

Consider:

1. Financial difference after commute costs

2. Quality of life factors

3. Career growth potential

4. Your recommendation with reasoning"

Use this for: Decisions, complex problems, when you want to understand the logic


## **Common Beginner Mistakes and How to Fix Them**


### **Mistake 1: Being Too Vague**

**Wrong:** "Write something about dogs" **Right:** "Write a 200-word beginner's guide to training a puppy, focusing on the first week at home"

**Fix:** Add specifics about topic, length, audience, and purpose


### **Mistake 2: Forgetting Your Audience**

**Wrong:** "Explain quantum computing" **Right:** "Explain quantum computing to a high school student using analogies to everyday things"

**Fix:** Always specify who will read or use the output


### **Mistake 3: No Format Guidance**

**Wrong:** "Give me tips for productivity" **Right:** "List 5 productivity tips for remote workers, each with a one-sentence explanation"

**Fix:** Specify if you want paragraphs, bullets, numbered lists, etc.


### **Mistake 4: Unclear Tone**

**Wrong:** "Write an email to my boss" **Right:** "Write a friendly but professional email to my boss requesting a day off next Friday"

**Fix:** Describe the tone you want (formal, casual, friendly, serious, etc.)


### **Mistake 5: Kitchen Sink Approach**

**Wrong:** Including your entire company history when asking for a tagline **Right:** Include only directly relevant information

**Fix:** Give context that matters, skip what doesn't


## **The Universal Template**

Here's a template that works for most situations:

You are a [role/expertise].

I need you to [specific task].

Context: [relevant background information]

Please create [exact output you want] that is [length] and written for [audience].

Use a [tone] tone.

[Any specific requirements or things to avoid]


### **Real Simple Example Using the Template**

You are a nutrition expert.

I need you to create a meal plan.

Context: I'm vegetarian, trying to increase protein intake, and I have 30 minutes max to cook dinner on weekdays.

Please create a 5-day dinner plan with recipes that take under 30 minutes and written for someone with basic cooking skills.

Use a friendly, encouraging tone.

Include the protein content for each meal and a shopping list at the end.


## **Quick Fixes for Common Problems**


### **Problem: Response Too Long or Too Short**

**Don't say:** "Make it shorter" **Do say:** "Maximum 100 words" or "3-4 sentences" or "One paragraph"


### **Problem: Wrong Style or Tone**

**Don't say:** "Make it better" **Do say:** "Rewrite in a conversational tone, like explaining to a friend"


### **Problem: Missing Important Information**

**Don't say:** "You forgot something" **Do say:** "Please add a section about [specific thing] including [specific details]"


### **Problem: Too Generic**

**Don't say:** "Be more specific" **Do say:** "Focus specifically on [narrow topic] for [specific situation]"


## **When AI Seems to Refuse**

Sometimes AI won't do what you ask because it misinterprets your intent. Reframe your request:

**Seems like:** "Write a fake review" **Reframe as:** "Write an example review for training customer service reps to identify authentic feedback"

**Seems like:** "How do I hack..." **Reframe as:** "How do I protect my system from..."


## **Building Your First Prompt Library**

Start collecting prompts that work well for tasks you do regularly. I keep mine in Notion!


### **Email Response Template**

Write a [type of email] to [recipient] about [topic].

Keep it [length] and use a [tone] tone.

Include [specific points].

End with [type of closing].


### **Content Creation Template**

Create a [type of content] about [topic] for [audience].

Make it [length] with [tone/style].

Include [must-have elements].

Focus on [main message].


### **Problem-Solving Template**

I'm facing this challenge: [describe problem]

My constraints are: [limitations]

Help me find [number] solutions that [criteria].

Consider [important factors].


### **Summary Template**

Summarize [document/article/meeting] in [length].

Focus on [key aspects].

Written for [audience].

Ignore [irrelevant parts].


## **Testing and Improving Your Prompts**

The three-try rule: Never settle for the first response.

**Try 1:** Write your initial prompt **Try 2:** Add missing specifics based on what wasn't right **Try 3:** Refine format, tone, or examples

Example progression:

Try 1: "Write a cover letter"

Result: Too generic

Try 2: "Write a cover letter for a marketing position at a tech startup"

Result: Better but still formulaic

Try 3: "Write a cover letter for a marketing position at a tech startup. I have 5 years of social media experience and increased engagement by 200% at my current job. Keep it under 300 words, confident but not boastful."

Result: Exactly what you need


## **Key Principles to Remember**

1. **Be Specific:** Vague requests get vague results
2. **Provide Context:** AI can't read your mind
3. **Define the Output:** Say exactly what format you want
4. **Specify Audience:** Who will use this?
5. **Set Boundaries:** Include length, tone, and style
6. **Show Examples:** When format matters, show what you want
7. **Iterate:** First attempts are rarely perfect


## **Your Quick Reference Checklist**

Before hitting enter, check:

- ✓ Is my request specific and clear?
- ✓ Did I specify the length I want?
- ✓ Is the audience defined?
- ✓ Did I indicate the tone/style needed?
- ✓ Is all the context necessary and relevant?
- ✓ Would an example help clarify what I want?


## **Emergency Reset**

When nothing seems to work:

Let me start over. I need your help with something specific.

Task: [one clear thing you need]

Background: [only essential context]

Output: [exactly what format/length you want]

Can you help me with this?


## **The Most Important Thing**

The difference between frustrating and excellent AI interactions usually isn't the AI - it's the prompt. Take 30 extra seconds to be specific about what you want, and you'll save minutes (or hours) of back-and-forth.

Start with the CLEAR framework. Practice on your real tasks. Build a collection of prompts that work. Remember: AI responds to what you write, not what you mean - so make your meaning clear.

Every expert was once a beginner. The only difference is practice. Your next prompt can be better than your last one, and that's all that matters.

[![](https://substackcdn.com/image/fetch/$s_!LPtc!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F50a046f7-f517-424b-a3f7-8ba717a594b3_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!LPtc!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F50a046f7-f517-424b-a3f7-8ba717a594b3_1024x1024.png)
