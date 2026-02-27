---
title: "Prompting just split into 4 different skills. You're probably practicing 1 of them (+ 7 prompts and a pre-flight to close the gap)"
author: "Nate Jones"
published: 2026-02-27
url: https://natesnewsletter.substack.com/p/prompting-just-split-into-4-different
subtitle: "Watch now | Most people think they’re good at prompting."
audience: everyone
scraped_at: 2026-02-27 12:00:17
---

Most people think they’re good at prompting. They’re not — they’re good at *chatting* with AI, which is a different skill that’s rapidly becoming table stakes.

Here’s what I mean. Two people sit down with the same model on the same Tuesday morning. Same subscription, same context window. One types a request, gets back something 70% right, spends forty minutes cleaning it up — good use of AI, maybe 30% faster than doing it by hand. The other spends eleven minutes writing a structured specification, hands it to an autonomous agent, makes coffee, and comes back to finished deliverables that hit every quality bar she defined up front. Does this five times before lunch. Her output this week would have taken three weeks in 2024.

Same model. Same Tuesday. The difference isn’t talent or technical ability. It’s that she’s practicing a discipline that most people don’t know exists yet — and the gap between the people who’ve found it and the people who haven’t is already 10x and compounding. Three model releases in February alone (Opus 4.6, GPT-5.3-Codex, Gemini 3.1 Pro) shipped with autonomous agent capabilities that make chat-based prompting feel like bringing a phone book to a search engine fight. The models stopped being conversation partners and started being workers. Workers that run for hours, then days, without checking in. And the skill of directing a worker you can’t supervise in real time is a fundamentally different discipline from the skill of having a productive conversation.

The word “prompting” is hiding four of those disciplines. This piece names them, shows where each one breaks, and gives you the tools to close the gaps you didn’t know you had.

**Here’s what’s inside:**

- **The 35-minute wall.** Why every assumption in the 2025 prompting playbook collapses once agents start running autonomously — and the Anthropic data that shows exactly where.
- **What Tobi Lütke figured out first.** The Shopify CEO’s insight about context engineering that made him a better leader, not just a better AI user.
- **The Klarna trap.** What happens when your context is excellent but your intent is missing — and why $40 million in projected savings turned into a customer satisfaction crisis.
- **Five new primitives and a four-month roadmap.** The specific skills replacing the old prompt engineering toolkit, in the order that produces the fastest results.
- **7 prompts and a pre-flight check.** A pen-and-paper thinking exercise before you touch AI, a 10-minute quick start that scores where you stand and builds your first context document, and the full build-out — specification engineer, intent framework builder, eval harness, constraint architecture designer, and the problem statement rewriter that trains the Lütke primitive. Start with the pre-flight.

The framework starts with a shift that happened faster than most people registered — and understanding exactly when and why it happened is the key to everything that follows.


## **LINK: [Grab the prompts](https://promptkit.natebjones.com/20260225_hfy_promptkit_1)**

These prompts exist because I’ve watched too many smart people hit a ceiling they can’t name. They know something changed — the old tricks aren’t landing the way they did three months ago — but they can’t see the new disciplines clearly enough to practice them deliberately.

The kit starts where most kits don’t: a pen-and-paper pre-flight that gets your thinking out of your head before AI has a chance to reshape it. Skip it and you’ll build on the AI’s version of what you wanted instead of your own. From there, the quick-start diagnostic scores where you stand across all four disciplines in ten minutes and produces a starter context document you can use immediately. The problem statement rewriter builds the core primitive Lütke identified — self-contained requests that don’t rely on AI to fill in the gaps. And the full build-out covers the rest: a deep diagnostic with a personalized four-month roadmap, a context document builder, a specification engineer that follows the Anthropic interview workflow, an intent and delegation framework builder designed to prevent the Klarna pattern, an eval harness that follows Lütke’s personal testing approach, and a constraint architecture designer that prevents the smart-but-wrong failure mode before you delegate.

Seven prompts and a pre-flight check. Start with the pre-flight.


## First, what changed.

The prompting skill that mattered in 2024 was conversational. You sat in a chat window, typed a request, read the output, iterated. Over time you got better at phrasing things, providing examples, structuring instructions. If you’re good at that — and if you’ve been following this newsletter, you probably are — you’ve been building a real skill. It works. You’re faster than you were a year ago.

But that skill has a ceiling, and in early 2026, a lot of people hit it. The models that shipped between October and February didn’t just get smarter — they got autonomous. The thing about an agent that runs for days without checking in is that everything you relied on in a conversation — your ability to catch mistakes in real time, provide missing context when the model asks, course-correct when things drift — all of that has to be encoded before the agent starts. Not during the run, but before it begins.

That’s not a harder version of the same skill. It’s a genuinely new discipline. And the shift happened fast. Between October 2025 and January 2026, the 99.9th percentile of Claude Code turn duration — the longest stretches where Claude works without human intervention — nearly doubled, from under twenty-five minutes to over forty-five. Anthropic published the data in their February 2026 agent autonomy study. TELUS deployed generative AI across 57,000 employees, who created over 13,000 custom AI solutions. The initiative has saved more than 500,000 hours, and 47 large-scale solutions have generated over $90 million in measured benefits, according to a Google Cloud case study. Zapier reports 89% AI adoption across their 360-person team, with more than 800 internal agents running across their operations. This isn’t coming — it landed.

This piece builds on my earlier work on [intent engineering](https://natesnewsletter.substack.com/p/klarna-saved-60-million-and-broke) but goes beyond it to lay out a full framework for prompting in 2026. Intent engineering is one layer. Here’s the whole stack.


## **What Tobi Lütke figured out before everyone else**

In September 2025, Shopify CEO Tobi Lütke sat down with Ben Gilbert and David Rosenthal on the Acquired podcast and said something that most listeners skipped past because it sounded like a technical aside. It wasn’t.

He was describing his personal eval process — a folder of prompts he runs against every new model release, systematically probing capabilities the way an ML engineer runs a test suite. Then he made the pivot. As he put it on the show, the fundamental skill of using AI well is being able to state a problem with enough context that, without any additional information, the task is plausibly solvable. He called it “context engineering.”

Read that again. He’s not talking about clever prompt tricks or magic words that make Claude produce better output. He’s talking about a communication discipline: can you state a problem so completely, with so much relevant surrounding information, that a capable system could solve it without going out and fetching additional context? Can you make your request self-contained?

That sounds simple. It is extraordinarily difficult. And Lütke’s critical insight — the one that makes this a leadership observation rather than a technical one — is that the discipline transfers. Getting good at providing AI with complete context made him better at everything else. Better emails. Better memos. Better decision-making frameworks for his 8,100-person company. He argued that what companies call “politics” is often just bad context engineering — buried disagreements about assumptions that nobody surfaced explicitly because humans are sloppy communicators who rely on shared context that doesn’t actually exist.

Lütke took this further inside Shopify. He required AI exploration in the prototype phase of every project — not because the AI output would be production-quality, but because even when AI is bad at a task, the attempt produces an eval. You now know where the model fails, and when the next model ships, you can retest. He had teams write “constitutions” — documents capturing the non-platitude decisions Shopify makes, where a reasonable competitor might choose the opposite. Then he tested new products against these constitutions using AI, and refined the constitutions themselves through the process.

This is what it looks like when someone internalizes that the bottleneck isn’t model capability — it’s input quality. The discipline of articulating what you actually want — completely, unambiguously, with all necessary context included — is the meta-skill underneath every successful AI deployment. And it’s the skill that most “prompt engineering” training completely ignores in favor of template libraries and magic-word tricks.

Lütke’s Shopify memo — the one that went viral in April 2025 — put a finer point on it: “Learning to use AI well is an unobvious skill. My sense is that a lot of people give up after writing a prompt and not getting the ideal thing back immediately.” His internal memo required employees to demonstrate that AI couldn’t handle a task before requesting additional headcount — a policy that was widely covered in TechCrunch and The Wall Street Journal — and pushed AI adoption into how Shopify evaluated employee contributions. He wasn’t being punitive. He was forcing the communication discipline on an entire organization because the people who develop it early will sequester the best careers.

The chess analogy Lütke made on Acquired lands differently once you see it through this lens. The best chess game every year is machine versus machine, and nobody watches those games. We don’t care about chess — we care about humans playing chess. AI tools are instruments to be played, not replacements for the player. But an instrument is only as good as the player’s technique. And the technique for playing these instruments just changed fundamentally.


## **The four skills hiding inside “prompting”**

Here’s the framework. Prompting — the broad skill of providing input to AI systems — has diverged into four distinct disciplines, each operating at a different altitude and time horizon. They build on each other. Skipping one creates the kind of failures we’re seeing at scale across the enterprise.

Discipline One: Prompt Craft. This is the original skill. Synchronous, session-based, individual. You sit in front of a chat window. You write an instruction. You evaluate output. You iterate. The skill is knowing how to structure a query — clear instructions, relevant examples, appropriate constraints, explicit output format. It’s what Anthropic’s prompt engineering documentation covers, and what a thousand blog posts and LinkedIn courses teach.

Prompt craft hasn’t become irrelevant. It’s become table stakes. The way knowing how to type was once a professional differentiator and is now just assumed. If you can’t write a clear, well-structured prompt in 2026, you’re the person in 1998 who couldn’t send an email. Important, sure — but no longer differentiating.

The key shift: prompt craft was the whole game when AI interactions were synchronous and session-based. You wrote something, got something back, refined it in real time. The human was the intent layer, the context layer, and the quality layer simultaneously. That model broke the moment agents started running for hours without checking in.

Discipline Two: Context Engineering. Anthropic published the foundational piece in September 2025, defining context engineering as “the set of strategies for curating and maintaining the optimal set of tokens during LLM inference, including all the other information that may land there outside of the prompts.” LangChain’s Harrison Chase was blunter in a Sequoia Capital interview: “Everything’s context engineering. It actually describes everything we’ve done at LangChain without knowing that that term existed.”

Context engineering is where the industry’s attention is focused right now. It’s the shift from crafting a single instruction to curating the entire information environment an agent operates within — system prompts, tool definitions, retrieved documents, message history, memory systems, MCP connections. The prompt you write might be 200 tokens. The context window it lands in might be a million. Your 200 tokens are 0.02% of what the model sees. The other 99.98% is context engineering.

This is the discipline that produces CLAUDE.md files, agent specifications, RAG pipeline design, memory architectures. It’s the discipline that determines whether a coding agent understands your project’s conventions, whether a research agent has access to the right documents, whether a customer service agent can retrieve relevant account history.

Anthropic’s engineering team identified the core challenge precisely: “LLMs degrade as you give them more information.” Not because they can’t hold the tokens, but because retrieval quality drops as context grows. The benchmark data bears this out — on MRCR v2, a needle-in-a-haystack test that hides information across a million tokens, Sonnet 4.5 scored just 18.5%. The context window was a filing cabinet with no index. Context engineering is the practice of building the index.

The practical implication: the people who are 10x more effective with AI than their peers aren’t writing 10x better prompts. They’ve built 10x better context infrastructure. Their agents start every session with the right project files, the right conventions, the right constraints already loaded. The prompt itself can be simple because the context does the heavy lifting.

Discipline Three: Intent Engineering. I wrote about this at length in a prior piece, so I’ll be brief on the concept and focus on where it sits in the stack. Context engineering tells agents what to know. Intent engineering tells agents what to want. It’s the practice of encoding organizational purpose — goals, values, tradeoff hierarchies, decision boundaries — into infrastructure that agents can act on.

Klarna’s story is the proof case. Their AI agent resolved 2.3 million customer conversations in the first month, slashed resolution times from eleven minutes to two, and projected $40 million in savings. Then customer satisfaction cratered because the agent was optimizing for speed when the organizational intent was relationship quality. The context was excellent, but the intent was missing. A human agent with five years at the company would have known when to bend a policy or spend three extra minutes. The AI knew nothing about what Klarna actually valued — only what it could measure.

Intent engineering sits above context engineering the way strategy sits above tactics. You can have perfect context and terrible intent alignment, which gives you Klarna — a technically brilliant agent destroying unmeasured organizational objectives. You cannot have good intent alignment without good context, because the agent needs information to act on the intent. The disciplines are cumulative, not substitutive.

The practical frontier of intent engineering includes what I’d call delegation frameworks — organizational decision boundaries translated into machine-readable parameters. When customer request X conflicts with policy Y, here’s the resolution hierarchy. When speed conflicts with quality, here’s the threshold where quality wins. These aren’t rules in the traditional sense. They’re encoded judgment — the kind of institutional knowledge that senior employees carry and new hires absorb through months of osmosis. Agents need it on day one, in structured form, updated continuously.

Discipline Four: Specification Engineering. This is the newest discipline, and the one almost nobody is talking about explicitly — even though the best practitioners are already doing it.

Specification engineering is the practice of writing documents that autonomous agents can execute against over extended time horizons without human intervention. Not prompts, not context documents, not intent frameworks — but specifications. Complete, structured, internally consistent descriptions of what the output should be, how quality is measured, what constraints apply, what tradeoffs are acceptable, and what done looks like.

Anthropic’s own engineering team discovered this the hard way. They reported that even Opus 4.5 — the most capable model available — fails to build a production-quality web app if you give it only a high-level prompt like “build a clone of claude.ai.” The agent tries to do too much at once, runs out of context mid-implementation, and leaves the next session guessing at what happened. The fix wasn’t a better model. It was a specification pattern: an initializer agent that sets up the environment, a progress log that documents what’s been done, and a coding agent that makes incremental progress against a structured plan in every session. The specification became the scaffolding that let multiple agents — working across multiple context windows — produce coherent output over days.

The shift from prompt to specification mirrors a transition that happened in human engineering decades ago. When you’re building something small, verbal instructions work. When you’re building something large enough to require a team or to span multiple sessions, you need blueprints. Anthropic needed blueprints. The team was made of AI agents. The blueprints were specifications.

This is where Anthropic’s best practices documentation for Claude Code becomes revealing. The recommended workflow for complex features: “Interview me in detail. Ask about technical implementation, UI/UX, edge cases, concerns, and tradeoffs. Don’t ask obvious questions — dig into the hard parts I might not have considered. Keep interviewing until we’ve covered everything, then write a complete spec to SPEC.md.” The agent writes the specification collaboratively with the human, then executes against it in a fresh session with clean context.

That workflow is specification engineering. The human provides judgment and intent. The agent helps formalize it into a structured document. Then the agent executes autonomously against the document. The specification becomes the contract between human intent and machine execution.

The practical skill isn’t writing code or crafting prompts. It’s the ability to describe an outcome with enough precision and completeness that an autonomous system can execute against it for days. That’s a fundamentally different skill from writing a good prompt in a chat window, and the people who are excellent at one are not automatically excellent at the other.


## **Why the 2025 mental model breaks**

The mental model most people carry — “prompting means writing good instructions for AI” — fails for a specific, structural reason: it assumes synchronous interaction.

In the synchronous model, you’re always there. You see the output in real time. You correct mistakes immediately. You provide additional context when the model asks or when you notice it going off track. The human is a live feedback loop operating at the speed of the conversation. Quality control is continuous and implicit.

Long-running autonomous agents break every assumption in that model.

Anthropic’s own autonomy study documented the practical ceiling: even among the most experienced Claude Code users, the longest uninterrupted sessions top out around forty-five minutes — and METR’s evaluations suggest models can handle tasks equivalent to nearly five hours of human work, meaning the trust gap is enormous. Context drift, error compounding, hallucination accumulation — the longer an agent runs without human correction, the more likely it is to produce work that needs rework. The deployment overhang is real, but so are the failure modes that create it.

This means everything you relied on in synchronous prompting — your ability to catch mistakes early, provide mid-course corrections, supply missing context when the model asks — becomes a structural vulnerability when the agent is running at 2 AM and you’re asleep. The quality that came from your real-time oversight has to be embedded in the specification before the agent starts working.

The Planner-Worker architecture that’s dominating production deployments reflects this reality. A capable model plans the work, decomposes it into subtasks, defines acceptance criteria. Cheaper, faster models execute the subtasks. The planning phase — the specification — determines the quality ceiling. Execution without good specification produces what I call the 80% problem — output that’s almost right but not quite. Stack Overflow’s 2025 Developer Survey found that 66% of developers cite “AI solutions that are almost right, but not quite” as their top frustration, and many report the rework takes longer than doing the task from scratch.

The shift from “fix it in real time” to “get the specification right up front” changes the bottleneck skill. Real-time prompting rewards verbal fluency, quick iteration, and a good eye for output quality. Specification engineering rewards completeness of thinking, anticipation of edge cases, clear articulation of acceptance criteria, and the ability to decompose complex outcomes into independently executable components. Different people are good at these different things. Some people who were exceptional at synchronous prompting will struggle with specification work, and some people who were mediocre at chat-based interaction will turn out to be excellent specification engineers.


## **The primitives that replaced the old playbook**

In 2025, the primitives of prompt training were: clear instructions, relevant examples, chain-of-thought reasoning, output formatting, and iterative refinement. These were the building blocks. If you mastered them, you could extract strong results from any frontier model.

In 2026, the primitives have shifted. The old ones still matter — they’re the foundation. But the ceiling is elsewhere. Here are the new primitives, in order of how much leverage they provide.

Primitive One: Self-Contained Problem Statements. This is Lütke’s insight, formalized. Can you state a problem with enough context that the task is plausibly solvable without the agent going out and fetching additional information? The discipline of self-containment forces clarity. It surfaces hidden assumptions. It makes you articulate constraints you normally leave implicit because you trust the human on the other end to fill in the gaps. AI doesn’t fill in gaps the way humans do. It fills them with statistical plausibility, which is a polite way of saying it guesses in ways that are often subtly wrong.

Training this primitive: take a request you would normally make conversationally — “update the dashboard to show the Q3 numbers” — and rewrite it as if the person receiving it has never seen your dashboard, doesn’t know what Q3 means in your organizational context, doesn’t know which database to query, and has no access to any information other than what you include. That’s the level of self-containment an agent needs.

Primitive Two: Acceptance Criteria. If you can’t describe what “done” looks like, an agent can’t know when to stop — or more precisely, it will stop at whatever point its internal heuristics say the task is complete, which may bear no relationship to what you actually needed. The 80% problem is almost always an acceptance criteria problem. The specification said “build a login page” when it should have said “build a login page that handles email/password, social OAuth via Google and GitHub, progressive disclosure of 2FA, session persistence for 30 days, and rate limiting after 5 failed attempts.”

A useful exercise: for every task you delegate, write three sentences that an independent observer could use to verify the output without asking you any questions. If you can’t write those three sentences, you don’t understand the task well enough to delegate it.

Primitive Three: Constraint Architecture. What the agent must do. What the agent must not do. What the agent should prefer when multiple valid approaches exist. What the agent should escalate rather than decide autonomously. These four categories — musts, must-nots, preferences, and escalation triggers — form the constraint architecture that turns a loose specification into a reliable one.

The CLAUDE.md pattern that’s emerging in the coding community is a practical implementation of constraint architecture. The best CLAUDE.md files aren’t long lists of rules. They’re concise, high-signal constraint documents: use these build commands, follow these code conventions, run these tests before marking a task complete, never modify these files without explicit instruction. The community consensus, per Anthropic’s own documentation: for each line in your CLAUDE.md, ask “Would removing this cause Claude to make mistakes?” If not, cut it.

The way to build this muscle: before delegating a task, write down what a smart, well-intentioned person might do that would technically satisfy the request but produce the wrong outcome. Those failure modes are your constraint architecture. Encode them.

Primitive Four: Decomposition. Large tasks need to be broken into components that can be executed independently, tested independently, and integrated predictably. This is software engineering’s oldest lesson — modularity — applied to AI task delegation. Anthropic’s long-running agent harness splits every complex project into an environment setup phase, a progress documentation phase, and incremental coding sessions — each independently verifiable. A marketing content audit requires the same decomposition: inventory, quality scoring, gap analysis, and recommendation generation, each with defined inputs and outputs.

Try this: take any project you’d estimate at “a few days of work” and decompose it into subtasks that each take under two hours, have clear input/output boundaries, and can be verified independently of the other subtasks. That’s the granularity at which agents work best, and it’s the granularity at which specification engineering operates.

Primitive Five: Evaluation Design. The Lütke eval pattern — building a growing test harness of prompts with expected results, running it against every new model — is the individual-scale version of what organizations need to do at every level of AI deployment. How do you know the output is good? Not “does it look reasonable,” which is how most people evaluate AI output. Actually good. Defensibly, measurably, consistently good.

If prompt craft is the art of input, evaluation design is the art of knowing whether the input worked. And in a world where agents run for hours or days, evaluation design is the only thing standing between “AI-generated output” and “AI-generated output we can actually use.”

Here’s how to start: for every recurring AI task, build a simple eval. Three to five test cases with known-good outputs. Run them periodically — especially after model updates. This catches regression, builds your intuition for where models fail, and creates institutional knowledge about what “good” looks like for your specific use cases. Lütke does this personally. Your team should do it systematically.


## **Where to start and what to build first**

If you’re reading this and wondering where to start, here’s the practical sequence. This isn’t theoretical — it’s the progression I see producing results in the organizations I advise and the practitioners I talk to.

Month one: Close the prompt craft gap. Most people are worse at basic prompting than they think. Reread Anthropic’s prompting documentation. Actually do the interactive tutorial. Run Lütke’s eval pattern: build a folder of five tasks you do regularly, write your best prompt for each one, and save the outputs as your baseline. You’ll revisit these.

Month two: Build your personal context layer. Write a CLAUDE.md equivalent for your own work — not for code, but for whatever your work actually is. Your goals, your constraints, your communication preferences, your quality standards, the institutional context that a new team member would need six months to absorb. Start every AI session by loading this context. The difference in output quality will be immediate and obvious.

Month three: Practice specification engineering. Take a real project — not a toy problem — and write a specification for it before touching AI. Acceptance criteria, constraint architecture, decomposition into subtasks, evaluation criteria for each subtask. Then hand the specification to an agent and see what comes back. The gap between what you expected and what you got is the gap in your specification. Tighten it. Run again. This iteration builds the muscle faster than any course.

Month four and beyond: Build intent infrastructure. This is the organizational layer. If you manage people or systems, start encoding the decision frameworks your team uses implicitly. What do we optimize for when speed and quality conflict? What gets escalated versus decided autonomously? What does “good enough” actually mean for each category of work? Write it down. Structure it. Make it available to agents. This is the work that scales from one person to an entire organization, and it’s the work that almost nobody has started.

The progression from prompt craft to specification engineering isn’t a ladder where you abandon the lower rungs. It’s a stack where each layer makes the layers above it possible. Good specifications require prompt craft fundamentals. Effective agent systems require good context engineering. Aligning agent behavior with organizational goals requires intent engineering. And delegating complex, multi-day autonomous work requires specification engineering that integrates all three layers beneath it.


## **The skill that transfers to everything else**

There’s a final dimension to this that goes beyond AI, and it’s the one I keep coming back to because it’s the most personally transformative.

Lütke said the discipline of context engineering — stating problems with enough context that they’re plausibly solvable without additional information — made him a better CEO. Not a better AI user — a better leader. Because the same discipline that makes an AI agent work well makes human communication work better. Clearer requests, more complete context, fewer buried assumptions. Less of what organizations politely call “alignment issues” and honestly call “I thought you meant something different.”

The best human managers I’ve worked with already operate this way. They give complete context when delegating. They specify acceptance criteria. They articulate constraints. They decompose complex projects into independently executable pieces. They build evaluation frameworks so their teams know what “good” looks like. These are the four disciplines of AI input — and they’re also just the disciplines of effective leadership.

What’s happening right now is that AI is forcing the communication discipline that the best leaders practice intuitively onto everyone who wants to be effective. You can’t rely on shared context with a machine. You can’t assume the AI will “just know” what you mean the way a colleague who’s sat next to you for two years might. You have to be explicit, complete, and precise. And if being explicit, complete, and precise with AI makes you better at being explicit, complete, and precise with humans — which it does, universally, in every case I’ve seen — then the AI communication discipline is also a leadership development program.

That’s not the framing you’ll see in most “how to prompt” courses. It should be. The skill of providing high-quality input to intelligent systems — AI or human — is the fundamental skill of the agent age. The people who develop it will run organizations where agents and humans both perform at their ceiling. The people who don’t will wonder why their AI investments keep producing the 80% problem and their human teams keep having “alignment issues.”

The prompt, as most people practice it, has run out of ceiling. The specification is the prompt now. And the specification, done right, is just what clear thinking always looked like — finally made explicit, because the machines won’t let us be lazy about it anymore.

[![](https://substackcdn.com/image/fetch/$s_!mMmr!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe19dd288-29ec-4320-807b-6707094fc6a4_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!mMmr!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe19dd288-29ec-4320-807b-6707094fc6a4_1024x1024.png)
