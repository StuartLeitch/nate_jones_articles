---
title: "How Search Works When AI Does It"
author: "Nate Jones"
published: 2025-10-28
url: https://natesnewsletter.substack.com/p/unlocking-perplexitys-power-proven
audience: everyone
scraped_at: 2026-01-05 19:13:21
---

We hate ChatGPT for hallucinating. It’s the # 1 worry I hear about AI, hands-down.

But what if we were just using the wrong tool for the job all along?

Here’s the deal: ChatGPT is a reasoning engine. We keep asking it to search. And then we’re shocked when it makes things up.

There’s another tool out there called [Perplexity](https://www.perplexity.ai/). It’s a search engine powered by AI. Not a reasoning engine.

And that difference matters, because Perplexity actually retrieves sources before answering.

BUT Perplexity isn’t magical if you don’t know how to talk to it. Most of us are prompting Perplexity like ChatGPT, and we’re getting crappy results.

And the guides out there don’t help. Most just say “ask your question and add ‘cite sources.’” That’s not prompting. That’s hoping.

This is serious stuff, because hallucinations are the #1 reason people don’t trust AI, Perplexity is probably our best tool out there to beat them, and people aren’t being taught how to use it!

So I built the guide to Perplexity that doesn’t exist.

This is the complete system for making Perplexity work. And more—it’s really a full guide for understanding how retrieval systems work differently than reasoning systems—because Retrieval Augmented Generation (Perplexity’s tech) is everywhere now. Your company’s internal search. Customer service tools. Research assistants.

Everyone is using it in systems at work, and no one is training for it. That means learning how to prompt for retrieval systems versus reasoning systems is a huge career unlock.

**Here are the keys to get that unlock:**

**The Article: 8 Principles of Retrieval Prompting**

- Why ChatGPT prompts fail in Perplexity
- How RAG architecture changes everything about prompting
- The 8 principles that separate good retrieval prompts from garbage
- When to use which tool (decision framework, not guessing)
- Real examples of each principle

**The Prompt Pack: 40+ Copy-Paste Prompts**

- Side-by-side comparisons (ChatGPT style vs Perplexity style, same query)
- Threading sequences that teach discovery patterns
- Deliberately broken prompts so you feel what fails
- Department templates (legal, financial, technical, market research)
- Variations showing exactly what changes matter
- Basically, Perplexity school in-a-box!

**The Converter Tool**

- Takes your existing ChatGPT prompts
- Transforms them into retrieval-optimized Perplexity prompts
- As a bonus, builds a reasoner prompt you can use on Perplexity outputs
- One prompt that fixes all your other prompts so they search in Perplexity

**The Hallucination Defense System**

- Cross-check prompt you run in ChatGPT/Claude to audit Perplexity
- Five verification-enforced prompting techniques
- Patterns for catching citation drift, vague synthesis, bad sources
- How to make hallucinations structurally harder through prompt design

This article teaches through experience. Perplexity is free to use. You can run the prompts. You feel the difference. Then the principles click and you feel that career unlock.

Hallucinations can be virtually killed off with the right approach, but you have to get passionate about understanding how to use AI differently.

This is the guide for that.

My goal is simple here: Take fact checks and search from your personal pain point to something you excel at, so you can do even complex searches in just a couple of minutes with confidence.

Let’s start searching, and let’s start killing hallucinations!


## [Grab the Prompt Pack](https://www.notion.so/product-templates/Perplexity-Prompt-Pack-29a5a2ccb52680f4a451c251e170a5fa?source=copy_link)

Before you read this guide, I need to tell you about something that will make it far more useful. I’ve built a companion prompt pack with 40+ copy-paste prompts that teach you how Perplexity works through experience rather than explanation.

The pack includes side-by-side comparisons showing ChatGPT-style versus Perplexity-style prompts for the same query, threading sequences you can run to feel how discovery works, and deliberately broken prompts so you experience the failure modes firsthand.

It also includes two critical tools: a converter that transforms your existing ChatGPT prompts into retrieval-optimized versions for Perplexity, and a comprehensive cross-check prompt you can use in ChatGPT or Claude to audit Perplexity’s outputs for hallucinations, citation issues, and synthesis drift.

The cross-check section alone includes five verification-enforced prompting techniques and systematic patterns for catching bad sources, vague claims, and missing conflicts.

Reading about the differences is useful. Running the prompts and feeling the quality shift is transformative. Grab the pack, work through a few examples, then come back here. The architectural principles below will click much faster once you’ve experienced what they’re describing.

---


# How Search Works When AI Does It

Perplexity sits in an odd position. Most people know it exists, fewer understand what makes it different from ChatGPT, and almost nobody prompts it correctly. That’s a problem, because the gap between mediocre Perplexity use and expert use is wider than you’d think. The architecture demands different prompting strategies, and the differences aren’t obvious.

I’m going to walk through how Perplexity actually works, why that architectural difference from ChatGPT matters for your prompts, and eight specific principles that transform search quality. This isn’t about features. It’s about understanding what happens when you hit enter, and adjusting your approach accordingly.


## The Architecture That Changes Everything

The difference between Perplexity and ChatGPT comes down to where each system looks for answers. ChatGPT is parametric. When you ask it a question, it searches its own weights—the patterns encoded during training. It’s reasoning over what it learned, not retrieving what exists. Yes, ChatGPT now has web search capabilities, but that’s an add-on layer. The fundamental engine is still optimized for pattern completion, not document retrieval.

Perplexity works the opposite way. It’s built on retrieval-augmented generation, which means every query triggers a live search across indexed documents. The system fetches relevant sources, extracts paragraphs, and conditions its answer on that fresh evidence. It’s not remembering patterns. It’s finding documents and synthesizing them.

This architectural split has consequences. ChatGPT excels when the task requires reasoning—when you need to apply logic, generate creative solutions, or work through complex chains of inference. Perplexity excels when the task requires facts—when you need current information grounded in sources you can verify. ChatGPT says “based on patterns in my training, I believe X.” Perplexity says “these sources claim X—here’s where I found them.”

The gap between fluency and factuality is widening as LLMs improve. Models sound more confident, more coherent, more persuasive. That makes it harder to spot when they’re wrong. RAG architecture provides an accountability layer. Every claim points to a source. You can verify the reasoning chain. That transparency matters, especially as AI-generated content floods the internet and makes it harder to distinguish signal from noise.

Perplexity also offers Research Mode, which layers agentic workflows on top of RAG. Standard search performs one retrieval pass. Research Mode performs dozens, reading hundreds of sources and making multiple passes to refine results. It’s autonomous decision-making about what to search next based on what it’s finding. When you need depth, Research Mode is worth the extra compute time.

So when I talk about prompting strategies, I’m not giving you generic LLM advice. I’m giving you principles tuned to how retrieval systems think.


## Principle One: Surgical Context Over Verbose Prompts

Retrieval systems reward specificity differently than reasoning systems do. With ChatGPT, you often load up the prompt with context to help the model reason effectively. With Perplexity, you want to be surgical. Two or three carefully chosen words can shift your results from generic to precise.

The mechanism here is semantic targeting. When you search for “climate models,” you’re giving the retrieval system a broad semantic space to explore. Every document that mentions climate models becomes relevant. When you search for “climate prediction models for urban planning,” you’re narrowing the semantic space dramatically. You’re telling the system exactly which corner of the knowledge graph to explore.

This doesn’t mean your prompts should be long. It means the words you include need to be load-bearing. Each word should narrow the retrieval space in a useful direction. Think of it as providing hooks for the retrieval algorithm rather than explaining what you want.

Here’s a practical example. If you’re researching machine learning techniques for retail, “machine learning retail” gets you everything. “Retail customer segmentation using machine learning” gets you what you actually need. The added specificity—customer segmentation—tells the system which subdomain of retail ML to prioritize. You’re not writing for an LLM that needs to understand your intent. You’re writing for a search algorithm that needs semantic anchors.

The distinction matters because it inverts your intuitions from ChatGPT prompting. With ChatGPT, you explain what you want and why. With Perplexity, you specify what to retrieve. The former is about guiding reasoning. The latter is about targeting documents.


## Principle Two: Few-Shot Examples Break Retrieval

Few-shot prompting is excellent advice for ChatGPT. You give the model examples of what you want, and it pattern-matches to produce similar outputs. I recommend it constantly for standard LLM work. Do not do this with Perplexity.

The problem is architectural. Few-shot examples work for parametric models because they guide pattern completion. The model sees your examples and adjusts its generation strategy accordingly. RAG systems don’t complete patterns—they retrieve documents. Your examples become retrieval constraints.

If you say “give me examples of French architecture like the Louvre,” the retrieval system sees “like the Louvre” and optimizes for that. You’ll get museums similar to the Louvre. You won’t get cathedrals, châteaux, or anything else that doesn’t match that narrow semantic cluster. The few-shot example didn’t guide the answer—it constrained the retrieval pool.

The fix is straightforward. Be direct about what you want without providing narrow examples. “Survey major styles of French architecture from medieval to contemporary, including both civic and religious buildings” works. You’re specifying scope without artificially narrowing the retrieval space.

This principle generalizes. Anytime you’re tempted to give Perplexity an example to clarify what you mean, stop. Rephrase your intent directly instead. Examples narrow retrieval in ways you probably don’t want.


## Principle Three: Speak the System’s Language

Perplexity has parameters in its API that control search behavior. Even if you’re not a developer using the API directly, you can invoke many of these through natural language. And you should, because vague requests produce vague results.

Don’t say “only search recent sources.” That’s ambiguous. Recent could mean last week, last month, last year. Say “limit results to sources published after January 1, 2024.” Don’t say “find academic research”—switch to Academic focus mode and specify “peer-reviewed studies from the last five years.”

The principle here is that Perplexity is wired to understand certain types of constraints. Dates, source types, domain filters, search depth—these aren’t just preference settings. They’re parameters that directly configure how the retrieval step operates. When you give the system crisp boundaries, it performs better because it doesn’t have to infer what you mean.

If you’re working with the API, you have even more control. You can set explicit source filters, adjust the number of documents retrieved, control recency weights, and tune other parameters that shape retrieval behavior. But even in the chat interface, plain language works. “Search only .gov and .edu domains” or “prioritize sources from the last month” will both steer the system effectively.

The underlying insight is that retrieval systems have levers you can pull. Unlike a purely parametric model where your only leverage is the prompt itself, RAG systems expose controls over the retrieval step. Learning which levers exist and how to invoke them is part of becoming proficient.


## Principle Four: Force Triangulation, Not Convergence

One of the biggest mistakes people make with Perplexity is treating it like an oracle. They ask a question, get an answer, and assume that answer represents Truth. It doesn’t. It represents a synthesis of whatever documents the system retrieved, and the internet is full of conflicting claims.

Build that into your prompts. Instead of asking “what are the health benefits of intermittent fasting,” ask “compare findings from at least three peer-reviewed studies on intermittent fasting, and note any conflicts in their conclusions about metabolic effects.” Notice what you’re doing—you’re explicitly requesting triangulation rather than convergence. You’re telling the system not to smooth over disagreement, but to surface it.

This forces Perplexity to cast a wider retrieval net. It can’t just grab the first few documents that seem relevant and synthesize them into a clean narrative. It has to find multiple perspectives and explicitly acknowledge where they diverge. That constraint makes the retrieval step more robust.

You can take this further. After Perplexity gives you an answer, ask for source summaries or key quotes so you can assess provenance before trusting the synthesis. Request a citations audit: “highlight which specific claims in your answer map to which sources.” This catches retrieval drift—the phenomenon where an LLM starts making claims that seem plausible but aren’t actually grounded in the retrieved documents.

When the topic matters, chain focused sub-queries. Start with “what’s the current state of research on X,” then follow up with “now drill into primary research on the most promising approach,” then “pull counterpoints or limitations from critics.” Each query refreshes the retrieval graph and keeps the system anchored to evidence rather than drifting into synthesis that feels right but isn’t verified.

The meta-principle here is skepticism. Perplexity is a tool, not a source of truth. Your job is to use it as a starting point for investigation, not an endpoint.


## Principle Five: Progressive Deepening Over Single-Shot Queries

With ChatGPT, I usually recommend bringing your full intent into a structured initial prompt. You want to load up the context window with everything the model needs to reason effectively. Perplexity works differently. You want to treat it like a conversation where each answer opens up new questions.

Start broader than you would with ChatGPT, then iteratively drill down with increasingly specific follow-ups. Your first query maps the territory. You’re asking “what exists here?” rather than “give me the answer.” Then you thread through the search space, following promising paths as you discover them.

This approach works because Perplexity does fresh retrieval on every turn. You’re not just elaborating on a fixed context—you’re dynamically steering the system through the corpus. Each follow-up is an opportunity to refine the retrieval parameters based on what you just learned.

Here’s a concrete example. I was curious about how South Korea’s work culture might interact with AI coding tools. My first query was broad: “South Korea work culture and coding productivity.” The results mentioned something about Claude Code gaining traction in Korean development teams. That was interesting, so I followed up: “how is Claude Code being adopted in South Korea specifically.” That led me to discover a whole subculture I had no idea existed—Korean developers using Claude Code to navigate brutal work hours and extreme productivity pressures.

I never would have found that with a single query. The progressive deepening approach let me discover something genuinely novel by threading through the retrieval space. The first query established the landscape. The follow-up zoomed in on the most interesting corner.

One tactical note: when the topic shifts in a conversation, nudge the system to refresh retrieval. Say “run a fresh search before answering” or “ignore previous context and search for X.” This prevents the system from coasting on stale context from earlier in the thread. RAG systems can fall into a rut where they keep synthesizing from the same document pool because they’re not triggering new retrievals.


## Principle Six: Concrete Output Constraints Reduce Hallucination

This is a hallucination mitigation technique disguised as a prompting principle. When you specify concrete output constraints, you force Perplexity to verify claims at a granular level rather than making broad attributions.

Say “provide evidence for every claim you make here” or “list specific section references or page numbers so I can check your work.” This makes the system more accountable. It can’t just synthesize a plausible-sounding answer from vaguely related sources—it has to tie every assertion back to something specific.

You can also request structured outputs that make verification easier. “For each claim, provide: the claim itself, the supporting source, the relevant quote, and your confidence level in that source.” This gives you a checklist you can work through when you need high confidence in the results.

The goal isn’t to eliminate hallucinations. That’s not realistic with current RAG systems. The goal is to make hallucinations easier to catch. If Perplexity can’t provide granular evidence for a claim, that’s a signal to dig deeper or verify through another channel.

This principle works because it changes the task from synthesis to verification. When you ask Perplexity for an answer, you’re asking it to take retrieved documents and weave them into a narrative. That synthesis step is where drift happens. When you ask Perplexity to map specific claims to specific sources, you’re asking it to demonstrate the chain of evidence. The second task is harder to fake.


## Principle Seven: Toggle Focus Modes Mid-Conversation

Perplexity has several focus modes: Academic, Writing, Social, Finance, and a few others. Most people set the mode once at the start of a conversation and forget about it. That’s leaving capability on the table.

The real power comes from toggling focus modes mid-conversation to reset the system’s retrieval lens. If you’re searching for something and the results feel stale or off-track, switching to a different focus mode forces the system to reframe its search strategy.

Here’s how this works in practice. Let’s say you’re researching French architecture and the results feel too touristy—you’re getting travel blogs and surface-level overviews. Switch to Academic mode in the middle of the conversation. You don’t need to start over. Just change the mode and ask your next question. The system will pivot to peer-reviewed sources, academic journals, and scholarly analyses.

This is different from how you’d handle a stuck conversation with ChatGPT. With ChatGPT, you’d typically want to clear the context window and start fresh. With Perplexity, the focus mode switch acts as a retrieval reset while preserving the conversational thread. It’s a more surgical intervention.

You can also combine focus modes with source filters for even more control. Switch to Academic mode and say “now search only .edu domains for architectural preservation case studies.” You’re stacking retrieval constraints to narrow in on exactly what you need.

The underlying principle is that retrieval systems benefit from explicit guidance about what kind of sources to prioritize. Focus modes are a blunt instrument for that guidance. Learning when to switch modes and how to combine them with other constraints is part of advanced Perplexity use.


## Principle Eight: Build Reusable Spaces for Recurring Workflows

Perplexity has a feature called Spaces that lets you create custom search environments with preset instructions. If you have recurring search workflows, this is substantial leverage.

A Space is essentially a saved prompt that runs automatically on every query in that thread. You can specify source preferences, output formats, focus modes, and any other constraints you want. Then whenever you start a conversation in that Space, those instructions are active by default.

I have a Space for competitive intelligence research that automatically limits results to the last 90 days, prioritizes primary sources over news aggregators, and requests structured outputs with citations for every claim. I have another Space for academic research that enforces Academic mode, filters for peer-reviewed sources, and asks for conflict disclosure in every answer.

The value here is consistency. You’re encoding your retrieval preferences once and then reusing them across dozens of queries. You’re not retyping the same constraints every time or hoping you remember to set the right parameters.

Spaces also let you share search environments with teammates. If you’ve dialed in an effective set of constraints for a particular domain, you can package that up and distribute it. It’s a form of search expertise that scales beyond individual use.

The meta-insight here is that effective search isn’t just about individual queries—it’s about building systems that capture what you’ve learned about how to query effectively. Spaces let you encode that knowledge.


## Avoiding Hallucinations: A Practical Framework

Perplexity hallucinates. It’s a RAG system built on an LLM, and LLMs hallucinate. The architecture mitigates this by grounding answers in retrieved documents, but it doesn’t eliminate the problem. You need to be smart about verification.

First, never trust single-source answers. If Perplexity cites only one source and it’s an unfamiliar blog or a random LinkedIn post, treat that with serious skepticism. The internet is full of AI-generated spam, and Perplexity cannot reliably distinguish between legitimate sources and synthetic slop. If you see a claim backed by a single sketchy source, verify it against a well-sourced article from a reputable publication before accepting it.

Second, be especially careful with quote attributions. If Perplexity describes a quote, go to the cited source and search for that phrase. It’s often there, but it may not be verbatim. It may be paraphrased, or it may lack the connotation that Perplexity’s synthesis suggests. Context matters, and RAG systems sometimes lose context in the retrieval-to-synthesis pipeline.

Third, use another LLM as a verification tool. I’m serious about this. Take Perplexity’s output, drop it into ChatGPT or Claude along with the citations, and ask that system to evaluate the claims critically. Look for logical inconsistencies, check whether the sources actually support the synthesis, identify any retrieval drift. Two-LLM verification loops work because they have different failure modes. ChatGPT might hallucinate facts, but it’s good at spotting logical inconsistencies. Perplexity might synthesize poorly, but it grounds claims in sources. Using both gives you complementary error detection.

Finally, if you’re working on precision-critical queries, use Academic focus mode. This prioritizes peer-reviewed sources like PubMed and Semantic Scholar, which reduces the probability of encountering AI-generated spam in the retrieval pool. It’s not perfect, but it’s a meaningful filter.

The broader point is that hallucination isn’t a binary problem you solve. It’s a risk you manage through verification workflows. The more critical the information, the more verification steps you need.


## Why This Matters

You might be wondering: why bother with all of this? We have Google. We have ChatGPT with search. Isn’t Perplexity just the awkward middle ground?

No. Perplexity solves a problem that neither Google nor ChatGPT fully addresses: the knowledge recency problem.

LLM training data gets out of date fast. ChatGPT’s parametric knowledge is frozen at its training cutoff. Yes, it can search the web now, but that’s not its core strength. Its fundamental architecture is optimized for reasoning over known patterns, not for fetching fresh facts. Google is fast, but it’s not AI-native—it gives you a list of links, not a synthesized answer grounded in evidence.

Perplexity sits in a different design space. You can update a RAG knowledge base multiple times a day. The index is live. And because the system is optimized for retrieval and synthesis rather than pure pattern completion, it’s better at surfacing recent information coherently.

As LLMs get better at sounding confident, we need systems that can ground claims in verifiable evidence. ChatGPT is becoming more fluent, more persuasive, more coherent—but that doesn’t mean it’s more factual. The risk is that we start trusting it because it sounds right, not because it is right.

Perplexity offers an accountability architecture. Every claim is tied to a source. You can verify the chain of reasoning. That transparency matters, especially as AI-generated content floods the internet and makes it harder to distinguish signal from noise.

I’m not saying Perplexity is perfect. RAG systems have failure modes, and I’ve outlined many of them here. But architecturally, it’s solving the right problem. We need AI-native search that prioritizes verifiable evidence over fluent confabulation. We need systems that let us see the sources, not just trust the synthesis.

That’s why I use Perplexity so much. It’s not replacing ChatGPT for reasoning tasks, and it’s not replacing Google for quick link-finding. But when I need to explore a knowledge space, discover unexpected corners of the internet, or ground claims in recent evidence, Perplexity is the tool I reach for.

Search is changing. The old model—type keywords, get links—is giving way to something different. AI-native search synthesizes answers from sources and exposes the reasoning chain. If you’re still approaching this like it’s 2015 Google or like it’s ChatGPT with a search button, you’re leaving capability on the table.

Learn how RAG systems think. Adjust your prompting accordingly. The results will speak for themselves.

[![](https://substackcdn.com/image/fetch/$s_!ND3L!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F90826b65-feab-43ad-a09e-b3434e5fe4ac_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!ND3L!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F90826b65-feab-43ad-a09e-b3434e5fe4ac_1024x1024.png)
