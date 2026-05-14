---
title: "Karpathy's viral AI wiki has a flaw most of the 100K people who bookmarked it haven't noticed yet"
author: "Nate Jones"
published: 2026-04-22
url: https://natesnewsletter.substack.com/p/your-ai-re-derives-everything-it
audience: everyone
scraped_at: 2026-05-14 14:33:12
---

A few weeks ago, Andrej Karpathy posted an idea that more than a hundred thousand people bookmarked. On the surface it sounded almost too simple: use your AI to build and maintain a personal wiki. You throw raw material into a folder, articles, research, meeting notes, whatever you’ve got. The AI reads all of it, pulls out what matters, connects ideas across sources, flags where things contradict, and keeps a running set of organized notes that gets smarter every time you feed it something new. No database, no special tools. Just folders, text files, and an AI doing the work of a full-time research librarian.

Since Karpathy’s post went up, I’ve gotten hundreds of messages asking some version of the same question: “Nate, is this the same thing as Open Brain?” “Does this make Open Brain obsolete?” “Is the wiki better?” The honest answer is more interesting than any of those questions assume. These two systems solve the same problem from opposite directions, and the difference between them is one of the most consequential design decisions you can make right now if you’re building anything serious with AI.

**Here’s what’s inside:**

- **The insight most of those hundred thousand bookmarkers missed.** The wiki isn’t the breakthrough. What matters is a deeper shift in how the AI relates to your knowledge over time, and almost nobody is talking about it clearly.
- **The fork that determines everything.** Every AI knowledge system has to decide when the hard thinking happens: at write time or at query time. That single choice shapes what the system costs, where it breaks, and what kind of trust you’re placing in the AI.
- **Where each approach cracks under load.** Specific failure modes for both the wiki and the database, including why a neglected wiki is more dangerous than a neglected database, and why most teams are choosing their architecture by accident.
- **The hybrid that gives you both.** A concrete architecture that combines [Open Brain’s](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres) structured storage with Karpathy-style compiled synthesis — and the wiki compiler recipe to build it.
- **How to decide what to build this week.** Clear criteria based on your actual situation: solo vs. team, research vs. operations, one project vs. long-term infrastructure.

This piece is the full comparison I wish someone had written before I started building.


## **LINKS: [Grab the prompts](https://promptkit.natebjones.com/20260405_2ro_promptkit_1) + Wiki Compiler (OB1)**

Choosing between these architectures is one thing. Actually building one without stalling at the first design decision is another. The [prompt kit for this article](https://promptkit.natebjones.com/20260405_2ro_promptkit_1) walks you through that part: a diagnostic that tells you which architecture fits your actual situation, a schema designer that produces the editorial policy your wiki lives or dies by, a synthesis agent you can run every time you ingest a new source, an auditor that catches wiki drift and hidden contradictions before they compound, and a hybrid blueprint if you want both layers working together. Five prompts, each one built around a specific failure mode from the article.

If you already have [Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres) running, the hybrid I describe below isn’t hypothetical anymore. The [Wiki Compiler recipe](https://github.com/NateBJones-Projects/OB1/tree/main/recipes/wiki-compiler) is live in the OB1 repo. It extracts entities and relationships from your stored thoughts, builds typed reasoning edges (supports, contradicts, supersedes), and generates per-entity wiki pages and topic-level synthesis pages from your database. You can run it on demand or schedule it as a recurring compilation pass. Your SQL stays the source of truth. The wiki is the compiled, regenerable view on top. If a page is wrong, you fix the underlying data and regenerate. That’s the whole point.


## Karpathy’s big insight (it’s not the wiki)

Before I get into the comparison, I need to explain why Karpathy’s post matters. Because on the surface it looks simple, maybe too simple. Folders and text files? That’s the big idea?

Yes. But the wiki isn’t the insight. The insight is about what the AI is doing.

Here’s how almost everyone uses AI with their documents today. You upload files to ChatGPT, or you use NotebookLM, or you set up some kind of retrieval system. Then you ask a question. The AI goes and finds the relevant chunks of your documents, reads them, and gives you an answer. This works. But what’s actually happening under the hood: the AI is rediscovering your knowledge from scratch every single time you ask.

Ask a question that requires connecting five documents? The AI has to find all five, read them, figure out how they relate, and produce a synthesis. Ask a similar question tomorrow? It does the whole thing again. Nothing was saved. No connections were preserved, no synthesis retained. The AI did real cognitive work and then threw it all away.

This is how ChatGPT file uploads work. This is how NotebookLM works. This is how most retrieval-augmented generation works. The AI is smart in the moment and amnesiac afterward.

Karpathy’s insight is: **what if the AI didn’t throw away the work?**

What if, instead of just finding relevant chunks and answering questions, the AI actually wrote down what it learned? What if every time you added a new source, the AI read it, figured out what mattered, and updated a set of organized notes, notes that already contained everything it had learned from every previous source? What if those notes included cross-references, flagged contradictions, tracked how your understanding evolved?

That’s the wiki. It’s not a clever file organization system. It’s a persistent artifact where the AI’s understanding lives. The AI reads a paper on Monday, writes up what it learned, and links it to what it learned last week. On Friday, when you ask a question, the AI doesn’t have to re-read everything from scratch. The synthesis is already sitting there, the cross-references already built, the contradictions already flagged.

Karpathy’s own words: “The knowledge is compiled once and then kept current, not re-derived on every query.”

That’s the sentence that matters. Most AI knowledge tools re-derive. His wiki compiles. That’s a fundamentally different relationship between AI and your information.

He described his working setup as having the AI agent on one side and Obsidian (a note-viewing app) on the other. The AI makes edits based on their conversation, and he browses the results in real time, following links, checking the graph view, reading updated pages. His metaphor: “Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase.” In plain English: the note app is where he reads; the AI is who writes; the wiki is what gets built.

Think of it like this. Most AI tools are like having a brilliant research assistant who reads your entire filing cabinet every time you ask a question, gives you a great answer, and then immediately forgets everything they figured out. Karpathy’s wiki is like that same assistant keeping a running set of notes, organized, cross-referenced, updated, so that each question builds on the last one instead of starting over.

That’s why more than a hundred thousand people bookmarked the post. Not because folders and text files are exciting. Because “an AI that builds up understanding over time instead of starting from zero every session” is the thing everyone’s been waiting for.

But there’s a catch that almost nobody in those bookmarks is thinking about yet. Every time the AI turns a raw source into a wiki page, it’s making editorial choices. What to include, what to leave out, how to frame the connections between ideas. Those are the AI’s choices, not yours. Important nuance that got dropped might matter six months from now, and you won’t know it’s missing because the wiki reads so cleanly. This is the same trap as dashboards in analytics: a dashboard is easier to read than a spreadsheet, but it can hide exactly the thing you need to see.

Karpathy is honest about this. His architecture keeps all the raw sources untouched in their own folder, so you can always go back to the originals. But most people building on his pattern won’t maintain that discipline. In practice, the wiki will become the thing they trust. The source of truth will quietly shift from the raw material to the AI’s summary of it. And if the AI’s summary missed something, or framed something slightly wrong, that error is now baked into your understanding. You won’t question it, because it reads like something you already know.


## The fork in every knowledge system

Now here’s where Open Brain enters the picture and things get interesting.

Every knowledge system with an AI at its core has to answer one question: **when does the AI do the hard thinking — when information comes in, or when you ask about it?**

This is the fork. Everything else follows from it.

Karpathy’s wiki is a **write-time** system. When a new source arrives (an article, a paper, a set of notes) the AI doesn’t just store it. It reads the source, extracts what matters, and writes that understanding into the wiki. It updates topic pages. It revises summaries. It adds links between related ideas. It notes where new data contradicts something filed last week. The hard work happens once, at the moment information comes in. After that, you can browse the wiki and get pre-built understanding without the AI doing any work at all.

Open Brain is a **query-time** system. When new information arrives, it gets stored faithfully — tagged, categorized, made searchable. But nobody synthesizes anything yet. The data sits in structured tables, waiting. When you or your AI agent asks a question, the AI reads the relevant entries, does the thinking fresh, and produces an answer on the fly. The hard work happens at the moment you need it, not before.

Think of it this way. Karpathy’s wiki is like a study guide that a really good tutor writes for you as you learn a subject. Every time you cover new material, the tutor updates the guide, adding new sections, revising old ones, connecting ideas across chapters. When exam day comes, you just read the guide. The thinking has been done.

Open Brain is like a perfectly organized filing cabinet with a brilliant librarian standing next to it. Every document is filed, indexed, and searchable. When you need an answer, the librarian pulls the relevant files, reads through them, and tells you what they mean. The filing is pristine. But the librarian has to do the thinking fresh every time you ask.

Study guides and filing cabinets are both useful. They’re good at very different things.


## Why this matters for you

Now for the version that isn’t about architecture.

If you only store stuff, your AI has to figure out what it all means every single time you ask. You’ve been feeding it articles, meeting notes, and research for six months. You ask a question that requires connecting five different sources. The AI has to find those sources, read them, figure out how they relate, and produce a synthesis, from scratch. Every time. Nothing was pre-built. Nothing compounds. You’re paying full cost on every question, and the hundredth question isn’t any cheaper than the first.

If you only build a wiki, your AI can read the summary but can’t do anything precise with the raw data underneath. You want to pull every deal over $50K from the last quarter? Filter all meetings by client name? Have three different AI tools query your knowledge base at the same time? A folder of text files can’t answer those questions. The understanding is there, but the structured data to act on it isn’t.

You’ve probably noticed that your hundredth conversation with an AI doesn’t feel meaningfully different from your tenth. You’re more skilled at prompting, sure. But the AI itself hasn’t gotten any smarter about you, your domain, your accumulated context. No model upgrade will fix it. It’s a storage architecture problem, specifically the question of whether anyone is doing the work of turning raw information into compiled understanding, and whether that compiled understanding is available the next time an agent acts on your behalf.

For a team, the stakes are sharper. Most organizations are generating enormous volumes of AI-touched knowledge right now (meeting summaries, strategy docs, research outputs, Slack threads) and almost all of it is write-once-read-never. Nobody maintains it. Nobody synthesizes across documents. Nobody flags that the Q2 strategy deck contradicts what the CEO said in last week’s all-hands. Your company’s AI-generated knowledge is either a compounding asset or a growing pile of noise. The choice between these two outcomes is a design decision, and most teams are making it by accident.

And here’s a subtlety that matters more for teams than individuals: sometimes contradictions are the most valuable thing in your knowledge base. Engineering thinks the timeline is twelve weeks. Sales promised the client eight. A wiki that resolves that contradiction into one coherent narrative, picking a side or splitting the difference, actually hides the most important strategic signal in the system. The gap between what engineering knows and what sales promised *is* the problem your leadership needs to see. A database that stores both views without resolving them preserves that tension. A well-meaning wiki can smooth it away. For teams, the right system might need to *surface* contradictions side by side rather than resolve them into tidy prose.


## The AI’s job description changes

One of the sharpest practical differences between these approaches is what the AI actually spends its time doing.

In Karpathy’s system, the AI is primarily a **writer**. Its job is to maintain a document. When you add a new source, the AI reads the raw material, then writes or updates wiki pages: summaries, concept explanations, cross-references, an index. It’s doing editorial work. It’s making judgment calls about what’s important, what connects to what, and where the contradictions are.

In Open Brain, the AI is primarily a **reader**. Its job is to answer questions by pulling from structured data. When you or an agent asks something, the AI searches the database, reads the relevant entries, and produces a fresh synthesis. It’s doing analytical work on the fly.

Same AI. Completely different job description. And this has real consequences.

When the AI is a writer, you interact with it intensively when new information comes in. Adding a single research paper might trigger updates across a dozen wiki pages. That’s the heavy operation. But afterward, getting answers is cheap, because the thinking has been done.

When the AI is a reader, adding new information is cheap. Write a row, tag it, done. The heavy operation is every question, because the AI has to reconstruct understanding from data every time. Simple lookups are fast. Deep synthesis questions are expensive. And that cost recurs every time you ask something similar, because nothing was pre-built.

This difference raises a question most people aren’t asking yet: **whose understanding is it?**

When your AI maintains a wiki, and a colleague asks you about a topic, and you check the wiki before answering, are you sharing your understanding, or the AI’s interpretation of your sources? You’re trusting that the AI’s capture of your thinking is good enough to share with your colleagues as yours. With a database, provenance is different. These are facts, from identified sources, with timestamps. You can trace any claim back to where it came from. You know what you know, and you know why you know it. With a compiled wiki, you’re trusting not just the AI’s ability to retrieve information, but its editorial judgment about what matters and how things connect. That’s a deeper and more consequential kind of trust.

It also means the instructions you give the AI, the schema file that tells it how to organize your wiki, quietly becomes the highest-leverage document in the whole system. It’s not a configuration file. It’s an editorial policy for your personal knowledge base. The quality of that schema determines the quality of every synthesis the AI produces. Most people will underinvest in it, and the wiki will be worse than it should be as a result.


## What each approach is good at

Let me be specific.

**Karpathy’s wiki wins when:**

You’re deep in research. When you’re reading ten papers on a topic over two weeks, each one building on or contradicting the last, the wiki approach is dramatically better. By paper five, the wiki already contains a synthesis of the first four. Paper five gets integrated against that existing picture. Contradictions are flagged at the moment of ingest. Cross-references are built automatically. By paper ten, you have a rich, navigable artifact that represents the current state of your understanding, not just the current state of your files.

This also wins for personal knowledge that evolves over months (health tracking, self-improvement, competitive analysis), and for any domain where the value is in the connections between sources rather than in any single source alone.

The other place it wins: the wiki still works even without an AI in the loop. It’s human-readable text files. You can open them in any note app, browse the links, follow the connections. If every AI API went down tomorrow, you’d still have organized, useful notes. That’s a real form of durability that a database can’t match.

**Open Brain wins when:**

You need precise, structured operations across your knowledge. “Show me every meeting note from Q1 where pricing was discussed.” “Pull the three most recent competitor updates and compare them.” “Find all action items assigned to me in the last two weeks.” These are database queries. They return exact, filterable results. A folder of text files can approximate this with keyword search, but it breaks fast, especially when you need to combine filters, sort by date, or work across hundreds of entries.

Open Brain also wins for multi-agent access. When you have Claude Code, ChatGPT, Cursor, and a scheduled automation all needing to read from and write to the same knowledge store in the same hour, you need a database that handles simultaneous access, not a directory of files where two agents editing the same page creates a mess.

And it wins at volume. Open Brain handles thousands of entries across dozens of categories with search, metadata, and relational queries. Karpathy’s own research wiki runs to about a hundred articles. The pattern works well at that scale, maybe into the low thousands with extra search tooling, but it was never designed for the volume an organization generates. When you’re dealing with thousands of contacts, transactions, events, or tasks, structured storage is the only sane option.


## Where each one cracks

Every system has a load where it starts to break. Here’s where.

**Karpathy’s wiki cracks at:**

**Team use.** The moment two people (or two agents) try to update the same wiki page, you have a conflict. Not just a technical conflict — a semantic one. Two agents reaching different conclusions about the same concept from different sources. For a solo practitioner this is invisible. For a team, it’s a serious problem.

**Fast-moving domains.** If your knowledge changes daily (project status, competitive positioning, live deal flow) the cost of re-synthesizing the wiki on every update becomes punishing. Every change potentially ripples across multiple pages. Karpathy’s system is optimized for knowledge that moves at “papers and articles” speed, not “Slack messages and ticket updates” speed. If you don’t think about the speed of business your knowledge system was designed for, you’re going to implement the wrong one.

**Dangerous when neglected.** This is the one that worries me most. A neglected database just has gaps: the old facts are still true, there’s just missing recent stuff. A neglected wiki *drifts*. Old syntheses become increasingly wrong as new information doesn’t get integrated, but they still read with confidence because they’re well-written prose. Database staleness looks like ignorance, and you know you’re missing something. Wiki staleness looks like misinformation, and you don’t know you’re wrong, because the page reads like it knows what it’s talking about. Confident prose you don’t question is more dangerous than a gap you can see.

**Precise queries.** “How many sources mention transformer attention?” You’d have to read every file. “What percentage of articles were updated in the last 30 days?” There’s no structured metadata to query. “Give me all companies sorted by number of mentions.” You need a database for that, not prose.

**Open Brain cracks at:**

**Deep synthesis quality.** When a question requires understanding the relationships between fifteen different stored entries, the AI has to discover and reconstruct those relationships on the fly. It has no pre-built map. It’s searching shelves every time. For complex multi-source questions, the answer is usually good but rarely as good as a pre-built synthesis that had time to integrate everything deliberately.

**Browsability.** Open Brain is headless. There’s no artifact you open and wander through. You can build dashboards and briefings on top of it (and the Life Engine extension does exactly that), but the default experience is: ask a question, get an answer. For people who think by reading and exploring, following links, stumbling on unexpected connections, this is a real gap.

**Catching contradictions.** In the wiki, contradictions surface when new information comes in, because the AI is actively integrating against existing pages. In a database, contradictions sit silently in adjacent rows until someone asks exactly the right question to expose them. You can build periodic audits (and Open Brain supports this), but it’s a bolt-on, not a default behavior.

**Telling a story.** Databases store facts. They don’t tell stories. If you need “give me the overall arc of how my understanding of this topic evolved over six months,” a database hands you timestamped entries. A wiki hands you a narrative with cross-references. The difference matters for reflection, learning, and explaining your thinking to other people.


## The principles both systems share

What struck me most about these two approaches: they disagree on almost every implementation detail and agree on almost every underlying belief.

**You own the artifact, not the tool.** Karpathy’s files are text in a folder you control. Open Brain’s data is in a database you own. Neither system hands your knowledge to a platform that can reprice, deprecate, or lock you in. Karpathy calls this “file over app.” I’ve called it building with “no SaaS middlemen.” Same conviction, different file formats.

**The AI does the grunt work. You do the judgment work.** In both systems, the human’s job is curation and questioning. What sources go in. What questions to ask. What the priorities are. The AI’s job is the tedious, high-volume work nobody wants to do by hand: summarizing, cross-referencing, maintaining, updating, filing. Same division of labor. Only the specific tasks differ.

**Memory compounds through structure, not accumulation.** Dumping everything into a pile doesn’t make you smarter. Karpathy’s wiki compounds because each new source gets integrated into an existing web of interlinked pages. Open Brain compounds because each new entry is categorized, embedded, and relationally connected to everything else. Both systems reject the “just throw it in and search later” model that makes most AI knowledge tools feel like slightly better Google Drives.

**The knowledge base should be AI-native.** Karpathy designed his wiki to be worked on by Claude Code, Codex, or any AI that can read and write files. Open Brain was designed from day one for MCP — the open protocol that lets any AI tool connect. Both systems assume that the primary user of the knowledge base isn’t you reading in a browser. It’s an AI agent working on your behalf. Human readability is a bonus. Agent accessibility is the requirement.


## The hybrid I’d actually build next

If I’m being honest about what the mature system looks like, it’s neither of these alone. It’s both.

I’ll lay out the specific architecture I’d propose, and what I think should become the next major Open Brain extension.

**Keep Open Brain as your permanent store.** Everything goes in. Every meeting note, article clip, research finding, task, contact. Tagged, searchable, queryable. This is your durable memory layer. It handles high volumes, precise queries, multi-agent access, and recall across every domain of your life. It’s the source of truth.

**Add a wiki layer as the compiled view.** A new process where a compilation agent runs on a schedule (daily, weekly, or on-demand after major ingest). The agent reads from Open Brain’s structured data, synthesizes across entries, and produces wiki pages: topic summaries, entity profiles, trend analyses, contradiction reports, an index. These pages are generated artifacts. Think of them like a daily briefing that a really good chief of staff writes by reading everything in your files and distilling it into something you can actually browse.

**The compilation agent follows Karpathy’s patterns** — cross-referencing, linking related topics, flagging contradictions, maintaining an evolving synthesis. But it works from structured data, not raw files. That means it can do things Karpathy’s ingest can’t: filter entries by date or category before synthesizing, weight by confidence, exclude outdated items. The synthesis is richer because the underlying data is richer.

**The wiki pages are the easy-to-read layer.** Browse them in Obsidian or any note app. Your AI reads them for pre-built context before doing deep work. They’re your “hot” reference, and when you’re actively working on a topic, the wiki gives you instant access to the current state of your understanding without the AI having to reconstruct it from database rows every time.

**The database stays the single source of truth.** New information always goes into Open Brain first. The wiki is never edited directly. This prevents the error-compounding problem that several commenters on Karpathy’s post flagged: if the AI writes something slightly wrong into the wiki and it stays there, the next answer builds on that wrong thing, and errors accumulate. In the hybrid model, the database is always authoritative. The wiki is generated from it. If the wiki has an error, you fix the source data and regenerate. The wiki never drifts from reality because it’s always rebuilt from reality.

In Open Brain terms, this is a recipe, a composable workflow that reads from the database and produces output. A “wiki compiler” recipe would query relevant tables, synthesize pages through the AI, write the output to a wiki directory, and log the compilation. It could run on an automated schedule, getting better every cycle because the underlying data grew since last time. That’s the compounding loop.

What you end up with: Open Brain for structured storage and agent access. Karpathy-style wiki for compiled understanding and human browsability. The database feeds the wiki. The wiki never contradicts the database. You query either one depending on what you need — a precise fact or a synthesized narrative.


## How to decide what to build right now

**Build a Karpathy-style wiki if:** You’re going deep on one research topic. You’re a solo user. You don’t need precise queries or multi-agent access. You think by reading and browsing. You want something running in thirty minutes with zero infrastructure. Karpathy’s gist is designed to be pasted into Claude Code or Codex, and the AI builds the whole system for you.

**Build Open Brain if:** You need multiple AI tools accessing the same memory. You’re capturing high-volume information across many categories. You need structured queries. You’re building automated agent workflows. You’re thinking about this as infrastructure for years, not a single project.

**Build both if:** You have Open Brain running and you want a browsable, pre-synthesized understanding layer on top of it. Filing system plus briefing book. You need both, and neither replaces the other.


## What Karpathy got right that everyone should steal

Regardless of which system you build, two ideas from Karpathy’s post are worth adopting immediately.

**The idea file as a publishing format.** Karpathy didn’t write a tutorial. He didn’t ship a tool. He published a high-level description of an idea, designed to be pasted into an AI agent that would then build the specifics with you. This is a new way to share technical knowledge, a blueprint for an AI to execute, not a step-by-step for a human to follow. It respects the reader’s agency (you and your agent decide the details together) while giving them a proven pattern to start from. I think we’re going to see a lot more of this.

**The AI as maintainer, not oracle.** The deepest insight isn’t the wiki structure. It’s the role the AI plays. Most people treat AI as something you ask questions to. Karpathy treats it as something that has an ongoing job — maintaining a knowledge artifact that gets better over time. The AI isn’t here for one-off answers. It’s here for sustained work that compounds. The question is just the interface.

Open Brain embeds the same principle through extensions, recipes, and the Life Engine’s autonomous loop. But Karpathy stated it more cleanly than anyone: you never write the wiki yourself. The AI writes and maintains all of it. You curate, you explore, you ask the right questions. The AI does the grunt work.

That division of labor — human judgment, AI maintenance — is the real pattern underneath both of these systems. And it’s the pattern that makes AI knowledge actually compound instead of just accumulate.


## Where this is going

Karpathy noted there’s room for “an incredible new product” in this space. He’s right. But I think the product that wins isn’t a better wiki tool or a better database. It’s the hybrid — structured storage, compiled synthesis, multi-agent access, and human browsability in one stack.

There’s a deeper question hiding underneath all of this, though, and it’s the one that will determine whether Karpathy’s approach gets more important or less important over the next two years. His entire system is implicitly a bet that context windows (the amount of text an AI can process at once) will stay small relative to the amount of knowledge you accumulate. If you could dump everything into one enormous prompt, you wouldn’t need to pre-compile anything. You’d just let the AI re-derive every time.

Context windows are getting bigger. Gemini can already handle over a million tokens. So is pre-compilation dying?

No. And this is the part that’s easy to get wrong. There’s a real difference between “the AI can see all your documents” and “the AI has already thought carefully about how they relate.” Seeing isn’t understanding. A massive context window full of raw sources still requires the AI to do the synthesis work live, during your query, under time pressure. Pre-compilation means that work was done deliberately, with your guidance, not rushed. That distinction will matter even when context windows are ten times bigger than today. More input doesn’t eliminate the need for thought. It actually increases it.

So I built Open Brain to handle this too. The wiki compiler recipe is live in the OB1 repo. It reads your database, synthesizes across entries, and produces Karpathy-style wiki pages you can browse in Obsidian or any note app. Your database stays the source of truth. The wiki is the readable layer on top.

The tools are different. The principle is the same. And the people who get this right first will have an advantage that widens every single week.

---

*The Open Brain repo is at [github.com/NateBJones-Projects/OB1](http://github.com/NateBJones-Projects/OB1).*

*[Karpathy’s LLM Wiki gist can be found here.](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)*

*Both are free, open, and designed to be built with an AI agent at your side.*

[![](https://substackcdn.com/image/fetch/$s_!T_vq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F23abd7af-2f1f-48c5-9759-3d1c18cc87b0_1448x1086.png)](https://substackcdn.com/image/fetch/$s_!T_vq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F23abd7af-2f1f-48c5-9759-3d1c18cc87b0_1448x1086.png)
