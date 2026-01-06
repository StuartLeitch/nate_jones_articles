---
title: "How to Build a Personal Knowledge System That AI Can Actually Use"
author: "Nate Jones"
published: 2025-10-29
url: https://natesnewsletter.substack.com/p/i-spent-3-months-testing-knowledge
audience: everyone
scraped_at: 2026-01-05 19:13:18
---

I have a confession to make: I am generally bad at notes.

I was bad at notes before AI, and AI is finally doing what AI is SUPPOSED to do—help me with my weak spots.

What I’m sharing here is from really bloody experience. I’ve tried a LOT of note-taking apps, and I’ve abandoned most of them. Evernote? Tried it. Obsidian? Tried that too. Notes? I have hundreds of notes buried by Apple’s terrible AI.

I’m finally ready to share how I approach notes in the age of AI.

I wanted to take my time with this piece, because notes are VERY personal and I wanted to write a guide that would feel relevant for YOU, not just for me.

After a ton of testing, I’ve come to a conclusion that surprised even me: for most people, for most things, NotebookLM is probably the correct notes solution.

Why? Three simple reasons:

1. It has a generous free tier and and is very easy to use (don’t sleep on that value)
2. Most actual value in notes is accurate retrieval around a theme
3. Google has built an insanely accurate retrieval model into NotebookLM

TLDR; this is a free tool that’s insanely accurate at recalling your notes so you don’t lose them. And that’s good enough for most people.

This begs the question: WHY is NotebookLM not the top choice on every internet listicle? Most of them will go for classic note-taking apps with lots of ‘features.’

That’s the issue: they’re too complex, and they’re too opinionated. The features lock you into a usage pattern, or they’re flexible but technical (like Obsidian).

NotebookLM is neither, which means you can easily customize it to you.

But the problem is because NotebookLM isn’t on the notes listicles (I KNOW) no one is really writing guides for it as a knowledge base.

Which means I couldn’t find a great guide for building a comprehensive notes system using NotebookLM, including multiple setup options, suggested prompts, how to use it with ChatGPT, etc.

So I fixed that. Here’s what you get:

**18 copy-ready retrieval prompts organized by use case**

- Research and learning (multi-source explanations, pattern finding, gap identification, evolution over time)
- Client and project work (background extraction, requirements by category, progress tracking, risk identification)
- Document comparison (contradiction finding, version diffs, completeness checks)
- Source verification (citation audits, provenance, exact quote extraction)

**3 complete end-to-end workflow examples**

- Learning a technical topic (retrieval in NotebookLM → design decisions in Claude)
- Client analysis (concern extraction with dates → alignment analysis → steering committee prep)
- Competitive research (strategy extraction per competitor → positioning gaps → differentiation in Claude)

**4 organization schemas by role**

- Consultant, Researcher, Product Manager, Founder
- Each includes typical active projects, archive patterns, and query cadence at scale

A 19 minute NotebookLM podcast about this article :)

**Project management frameworks that prevent the common failure modes**

- Naming conventions that scale to 20+ projects
- Decision framework for when to split vs. merge projects
- Size guidance (ideal: 15-50 sources, split at 75+, quality degrades at 100+)
- Archiving strategy and quarterly maintenance

**Good vs. bad prompt comparisons**

- Side-by-side examples showing why vague prompts fail
- How to frame for retrieval vs. synthesis
- Handoff patterns for moving from NotebookLM to Claude with context intact

**The 6 most common pitfalls with specific fixes**

- Asking for thinking instead of retrieval
- Project bloat from indiscriminate source adding
- Not copying extractions (chats don’t save)
- Vague prompts that return noise
- Ignoring citations (defeats the entire purpose)
- Using NotebookLM for final outputs (wrong tool for that job)

**5-minute setup walkthrough**

- Narrow project naming
- Source addition patterns (files, URLs, docs, transcripts)
- Scoping questions to inventory what you have
- First retrieval prompt to validate the system

Why did I write all this out? Because it’s HARD to do notes well.

It generally sucks. We’re afraid to lose notes. We’re afraid to get organized. We want AI to help but not hallucinate.

And I want it to be easy. NotebookLM can help with all this, but only if you know how to get organized. That’s what this guide solves for.

Who is this for? The list is long!

- Anyone who wants to not lose their notes again!
- Product Managers keeping notes on customers
- Engineers reviewing technical architecture conversations
- UX doing customer research
- Marketing doing competitive research
- Sales trying to track and learn from prospect conversations
- Students
- Vibe coders figuring out how to keep their build notes organized
- Professors, teachers, and academics
- Anyone trying to learn AI (I use it for this one!)
- People using OTHER notes apps (YES)

The list goes on. You get the idea. Happy note-taking!

> One small note on why I think people using other notes apps would find this guide helpful: I’m framing it specifically in terms of how you retrieve clean context out of notes applications to hand to a reasoner LLM for thinking. I find most built-in AI in notes apps is not great (unless you do extensive tinkering), so the work done around prompts and workflows can cross-pollinate for you!

Alright, let’s dig in and start organizing our notes for AI, with AI, and most of all in ways that makes sense for OUR brains :)


## [Grab the NotebookLM Personal Knowledge Guide](https://www.notion.so/product-templates/NotebookLM-Practical-Knowledge-Guide-29a5a2ccb52680289924c4d9da1245ff?source=copy_link)

Hit the link and grab the full setup guide so you can get going, because knowledge systems are personal.

Most people know they need a better system for organizing knowledge that AI can actually use. Fewer people know how to build one that works. This guide gives you 18 copy-paste prompts, 3 complete workflow examples, 4 organization schemas for different roles, and project management frameworks to make Notebook LM useful in the next hour instead of staying theoretical.

You’ll get 14 retrieval prompt templates optimized for research, client work, document comparison, and source verification—plus 4 handoff framing examples showing exactly how to move extracted context from Notebook LM into Claude or ChatGPT for thinking. The guide includes side-by-side good vs bad prompt comparisons, a 5-minute setup walkthrough, naming conventions that scale to 20+ projects, decision frameworks for when to split or merge projects, and detailed breakdowns of the 6 most common pitfalls (with fixes).

The difference between people who get value from AI knowledge systems and people who don’t usually comes down to having the right prompts, the right organization structure, and knowing which tool does what job. This guide is all three.

---


#### Just for fun, grab the NotebookLM Podcast about … this article

Audio playback is not supported on your browser. Please upgrade.

---


# How to Build a Personal Knowledge System That AI Can Actually Use

People keep asking me the same question: how do I give AI more information than fits in a chat window? They have dozens of articles saved, client documents scattered across folders, research papers they need to synthesize. They want AI to help them make sense of it all, but they don’t know how to organize it, and they definitely don’t know how to make it reliable.

The answer for most people is simpler than you think. You need a project-based retrieval system that works at the scale of dozens to hundreds of documents. You need it to be accurate enough to trust. And you need it to fit into a workflow where you can move from retrieval to thinking without rebuilding everything from scratch.

For that use case—which covers most of the people asking me this question—NotebookLM is the best solution available right now. It’s free, it requires no code, and it has the lowest hallucination rate of any retrieval system I’ve tested. But more importantly, it fits into a specific workflow that makes AI knowledge systems actually useful instead of just impressive.

Let me show you how to use it properly.


## Why NotebookLM

I’ve been looking for months for something I could recommend to non-technical people who need to organize knowledge for AI use. The requirements were straightforward: accurate retrieval, easy source management, flexible enough to handle different file types, and simple enough that you don’t need to be an engineer to set it up.

NotebookLM hits all of those. The accuracy matters most. When you ask it a question, it retrieves from your documents and cites exactly where the information comes from. You can click through to see the source. The hallucination rate is remarkably low because the system is tightly constrained to what’s actually in your documents. It won’t make things up the way a pure language model will.

It’s also drag-and-drop simple. You can upload PDFs, link to web articles, connect Google Docs, add audio files, paste in text. The system handles the file types and makes everything searchable. You don’t write code. You don’t configure APIs. You don’t debug anything. You just add sources and start asking questions.

And it’s free, which matters when every other tool in this space is asking for a subscription.

The combination of accuracy, ease of use, and zero cost makes it the obvious recommendation for the common case. But the real value isn’t in the features. It’s in how you organize knowledge and how you move between retrieval and thinking.


## Why NOT other tools?

Here’s why Notebook LM beats the alternatives for this specific use case:

---


#### Why Not Obsidian + Local RAG?

Obsidian with a custom RAG setup is powerful—if you’re an engineer willing to maintain infrastructure. You’re configuring embeddings, tuning retrieval algorithms, managing database updates, and debugging when things break. For people who need that level of control over thousands of evergreen notes, it’s worth the investment. But for the common case of project-scoped knowledge at the dozens-to-hundreds scale, you’re spending engineering time to solve a problem Notebook LM handles out of the box. The accuracy is comparable, the setup time is 100x faster, and you’re not maintaining a system.


#### Why Not Notion AI?

I love Notion! I wrote about it recently and I use it all the time.

That being said, Notion AI generates content based on your workspace, but it’s not optimized for retrieval accuracy. It’s a reasoning model that happens to have access to your docs, not a retrieval system designed to minimize hallucination. You’ll get synthesis and suggestions (plus agentic action which is cool), but the citation quality is weaker and the grounding is looser. Notion excels at collaborative workspace management—that’s what it’s built for. If you need accurate retrieval from specific sources with reliable citations, Notebook LM’s architecture is purpose-built for that job. Both are good—but most people I talk to about this care a lot about hallucinations so I leaned into the more accurate tool.


#### Why Not ChatGPT/Claude with File Uploads?

Uploading files to ChatGPT or Claude puts them in context for that conversation, but you’re limited by context window size and you lose them when the chat ends. There’s no persistent project organization. You can’t build a collection of 50 sources and query across them systematically over time. And these are thinking LLMs, not retrieval systems—they’ll reason about your documents, but they’re not architecturally optimized to minimize hallucination the way a tightly-constrained RAG system is. They’re better at the thinking step after you’ve extracted accurate information, not at the extraction itself.


#### Why Not Perplexity with Sources?

Perplexity searches the web. That’s fundamentally different from searching your specific documents. If you want to query across proprietary information, client documents, internal notes, or anything not publicly available, Perplexity can’t help. It’s excellent for external research and discovery, but it’s the wrong tool for personal knowledge management. You need something that searches what you’ve explicitly added, not the public internet.


#### Why Not Traditional Note Apps (Evernote, Apple Notes, etc.)?

Traditional note apps weren’t designed for AI retrieval. Their search is keyword-based, not semantic. They don’t provide citations. They don’t structure information for RAG. You can store documents there, but you can’t query them with natural language and get grounded, cited answers back. They’re filing systems, not retrieval systems. The architecture doesn’t match the use case.


#### Why Not Custom-Built RAG Systems?

If you’re a company with engineering resources and specific requirements, building custom RAG makes sense. You control the infrastructure, tune for your exact use case, and integrate with your existing systems. But for individuals who need personal knowledge management without writing code, the time-to-value calculation is completely different. Notebook LM gives you 80% of the value with 5% of the effort. You’re not debugging embeddings or managing vector databases. You’re dragging files into projects and asking questions.

---

**The Sweet Spot Notebook LM Occupies:**

It’s the only tool that combines:

- RAG-level retrieval accuracy (low hallucination)
- Zero technical setup (no code, no configuration)
- Project-based organization (coherent knowledge domains)
- Any file type (PDFs, docs, web links, audio)
- Persistent collections (not per-conversation)
- Free (no subscription)

For the most common use case—people who need accurate retrieval from project-scoped sources without engineering effort—nothing else hits all six requirements. Other tools are better at other jobs, but for this specific workflow, Notebook LM is architecturally matched to the problem.


## How to Organize Projects

Everything in NotebookLM is project-based. That’s the right mental model. Don’t try to build one universal system that holds all your notes from the past decade. Build focused projects that contain related information for a specific purpose.

A project might be everything related to a client engagement. It might be research for a particular article you’re writing. It might be documentation for a product you’re evaluating. The scope is whatever makes sense as a coherent unit of knowledge that you’ll want to search across together.

Here’s how I think about project boundaries: if two pieces of information would appear in the same search query, they belong in the same project. If you’d never search for them together, they probably belong in separate projects.

For a consulting client, I might have one project with recent emails, meeting notes, shared documents, and deliverables from the past six months. I don’t need ten years of client history because the recent context is what matters for current work. If I’m researching a technical topic, I’ll create a project with relevant papers, blog posts, documentation, and examples. Once I’ve learned what I need, that project sits there as a reference, and I start a new one when I move to the next topic.

The project structure keeps things manageable. You’re not trying to search across everything you’ve ever read. You’re searching within a focused domain where the information actually relates to each other.

Adding sources is straightforward. You can upload files directly or paste links to web content. If something’s behind a paywall, download it and upload it. NotebookLM doesn’t care. The system will index whatever you give it and make it searchable.

The key is to keep projects coherent. Don’t throw random documents into a project just because you have them. Add sources that actually contribute to the knowledge domain you’re building. If you find yourself wanting to add something unrelated, that’s a signal to start a new project instead.


## The Two-Step Workflow

This is the part that makes the system actually useful instead of just interesting. NotebookLM is not a replacement for Claude or ChatGPT. It’s a different tool that does a different job. Understanding that distinction changes how you use it.

NotebookLM is optimized for retrieval. It’s designed to find accurate information in your documents and surface it with citations. It does this extremely well. What it doesn’t do well is think about that information, synthesize across multiple concepts, or create new content from it.

That’s because retrieval and thinking are architecturally different. A retrieval system like NotebookLM grounds its responses in the documents you gave it. It pulls from those sources and cites them. It doesn’t rely on the language model’s parametric memory—the training data baked into the model. That’s why the hallucination rate is so low.

A thinking system like Claude or ChatGPT does the opposite. It uses its parametric memory to reason, synthesize, and create. It can search the web if you ask, but its primary mode is generating from what it knows. That makes it powerful for thinking through problems, but less reliable for fact retrieval unless you’re explicitly constraining it.

The workflow I use combines both. I use NotebookLM to retrieve accurate information from my documents. I ask it specific questions about what’s in there, and it gives me precise answers with citations. Then I copy that information out and paste it into Claude or ChatGPT when I need to think about it, synthesize it with other knowledge, or use it to create something new.

Here’s what that looks like in practice. Let’s say I’m writing an article about AI implementation strategies and I have a project in NotebookLM with case studies, research papers, and documentation from several companies I’ve worked with.

I’ll ask NotebookLM: “What specific obstacles did companies face when rolling out AI tools to non-technical teams?” It retrieves the relevant information, gives me examples from my sources, and cites exactly where each piece came from. I can verify the information by clicking through to the source documents.

That gives me a clean extraction of accurate information. But I’m not done. I copy that response and paste it into Claude with a new prompt: “Based on these documented obstacles, what patterns suggest underlying organizational issues versus tool-specific problems? Suggest a diagnostic framework I could use with clients.”

Now Claude is thinking. It’s synthesizing the information I gave it, drawing on its broader knowledge of organizational behavior, and creating something new. The retrieval happened in NotebookLM where it’s most accurate. The thinking happens in Claude where it’s most capable.

This two-step pattern solves a real problem. If I tried to do everything in NotebookLM, I’d get accurate retrieval but shallow synthesis. If I tried to do everything in Claude, I’d risk hallucinations because it would be generating from memory instead of grounding in my specific documents. By splitting the workflow, I get accuracy where I need accuracy and thinking where I need thinking.

The handoff is just copy-paste. There’s no API integration, no complex setup. You extract what you need from NotebookLM, frame it appropriately for the thinking LLM, and continue from there. It’s a modular workflow that plays to each tool’s strengths.


## The Ephemeral Chat Problem

NotebookLM has one major drawback: it doesn’t save your chat history. You can have a long conversation, extract valuable insights, and then when you come back later, it’s gone. You have to start over.

> UPDATE Oct 29: HA as I write this Google has announced they are fixing this. Read about it here: https://blog.google/technology/google-labs/notebooklm-custom-personas-engine-upgrade/
>
> I would grab some of these principles and use them for cross-ChatGPT pollination still (pulling chats out, keeping them in a doc, etc.) but the core issue is one Google is thankfully fixing.

This is annoying, and I don’t know why Google did it this way. But it’s workable if you adjust your workflow.

The key is to treat NotebookLM conversations as ephemeral by design. Don’t expect to return to them. Instead, make sure you’re copying out anything valuable as you go. When NotebookLM gives you a useful extraction, paste it somewhere permanent immediately—into a note, into your thinking LLM, into a document you’re working on.

Some people create a separate “extractions” project in NotebookLM where they save important responses as new source documents. That way the information is preserved and searchable for future queries. It’s a bit of a workaround, but it functions like a conversation archive.

Another approach is to keep a running document outside NotebookLM where you paste significant extractions along with the query that produced them. Over time this becomes a log of what you’ve learned from your sources. You can search it later, and you have the context of what question you were asking when you found that information.

The broader point is to plan for ephemerality. NotebookLM is a retrieval tool, not a conversation partner you return to. Use it to extract accurate information, move that information somewhere permanent, and don’t rely on being able to reconstruct the chat later.


## Common Mistakes

The biggest mistake is trying to make NotebookLM think. People will ask it to “analyze the implications” or “develop a strategy” based on the documents. The system will try, but the output is shallow compared to what you’d get from a thinking LLM. NotebookLM is optimized for retrieval, not reasoning. If you want analysis, retrieve the information first, then move to a tool built for thinking.

Another common issue is project bloat. People start adding sources indiscriminately and end up with projects that contain hundreds of loosely related documents. At that point the retrieval quality degrades because the system has too much noise to search through. Keep projects focused. If you’re adding a document and you have to stretch to explain why it belongs, it probably doesn’t.

People also underestimate the value of citations. When NotebookLM gives you an answer, click through to verify the sources. This catches cases where the retrieval is technically accurate but missing context. It also helps you understand what information is actually in your documents versus what you assumed was there.

Finally, don’t ignore the retrieval-thinking split. If you try to do everything in one tool, you’re either getting shallow thinking or unreliable retrieval. The workflow is better when you let each tool do what it’s good at.


## Prompting for Retrieval

Retrieval prompting is different from the prompting you do with Claude or ChatGPT. In a thinking LLM, you want to encourage reasoning, provide examples, and give the model room to synthesize. In a retrieval system, you want to be specific about what information you’re looking for and where it should look.

Good retrieval prompts are precise. Instead of “What does the research say about AI adoption?”, try “What specific obstacles to AI adoption appear in the case studies from companies with fewer than 500 employees?” The narrower prompt helps the system target the right documents and extract the right information.

Ask for citations explicitly. “List the three main findings about X and cite which document each comes from.” This forces the system to ground its response and makes it easy for you to verify.

Request source summaries when you’re not sure what’s in your project. “Summarize what each source document says about quarterly planning.” This helps you understand what information is available before you drill into specific questions.

Chain focused queries rather than asking one broad question. Start with “What are the main topics covered in these documents?” Then follow up with “Now focus on the customer feedback sections and extract specific complaints.” Sequential narrowing keeps the retrieval sharp.

When you shift topics in a conversation, explicitly tell NotebookLM to run a fresh search. “Leaving aside the previous context, search for information about budget constraints.” This prevents the system from coasting on prior retrievals when you’ve moved to a new question.

The pattern across all of these is specificity and grounding. You’re not trying to coax the system into creative thinking. You’re directing it to find precise information in specific places. The prompting style follows from the architecture.


## When You Need to Go Beyond

NotebookLM works well for dozens to a few hundred sources organized into focused projects. If you’re operating at that scale, it’s the best tool available for non-technical users.

But it doesn’t work for everything. If you have tens of thousands of notes accumulated over years and you want to build an evergreen knowledge system that connects everything, NotebookLM isn’t the right tool. At that scale you need a custom solution—probably something built on Obsidian with a local language model and purpose-built retrieval infrastructure.

That’s an engineering project. You’re setting up databases, configuring embeddings, tuning retrieval algorithms, and maintaining the system over time. For people who need that level of capability and have the technical skill to build it, the investment makes sense. But it’s not accessible to most people, and it’s overkill for most use cases.

The decision framework is straightforward. If your knowledge system is project-based and operates at the scale of dozens to hundreds of sources, use NotebookLM. If you need a comprehensive evergreen system that spans thousands of notes and years of history, you probably need to build something custom.

For everything in between, think about whether you’re solving a real problem or chasing an ideal. A lot of people think they need a universal knowledge system when what they actually need is better project organization. The 80/20 is usually in focused projects with recent information, not in comprehensive archives of everything you’ve ever read.


## What This Actually Solves

The underlying problem isn’t that you can’t fit everything in a chat window. The problem is that knowledge work requires different cognitive modes, and single-tool solutions force you to compromise.

You need accurate retrieval from your specific sources without hallucination. You need sophisticated thinking and synthesis that draws on broader knowledge. You need to create new content that integrates what you’ve learned. Those are different operations, and they work better when you use the right tool for each step.

NotebookLM gives you reliable retrieval for project-scoped knowledge. Claude and ChatGPT give you thinking and creation. The workflow is modular: retrieve accurately, extract precisely, think deeply, create effectively.

That’s not the only way to build a knowledge system, but it’s the most accessible approach that actually works for most people. It’s free, it requires no code, and it respects the architectural differences between retrieval and reasoning instead of trying to force one tool to do everything.

If you’ve been struggling to organize knowledge in a way that AI can help with, start here. Build a project in NotebookLM with a few dozen relevant sources. Ask it specific questions. Extract the accurate information it gives you. Move that to a thinking LLM when you need to synthesize or create. See if the workflow fits your needs.

For most of the people asking me how to organize their knowledge for AI, this is the answer.

[![](https://substackcdn.com/image/fetch/$s_!bSq4!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F752be20a-fe94-4f36-975a-fce1598b7c2e_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!bSq4!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F752be20a-fe94-4f36-975a-fce1598b7c2e_1024x1024.png)
