---
title: "You're Loading 66,000 Tokens of Plugins Before You Even Type. That's Why Your Limit Disappears."
author: "Nate Jones"
published: 2026-04-02
url: https://natesnewsletter.substack.com/p/your-claude-sessions-cost-10x-what
subtitle: "Watch now | Token management is a indicator of AI fluency. Here's how to get better at it."
audience: everyone
scraped_at: 2026-04-02 12:00:16
---

I recently saw a production AI pipeline that ingests multiple long-form conversations per user, runs analysis across dozens of dimensions, and generates fully personalized output. All on the most expensive models money can buy. The cost per user? Less than a quarter. Most of you are spending more than that asking Claude what to have for dinner.

That number should bother you — not because frontier AI is expensive, but because it isn’t. Frontier AI running on the most expensive models available costs pennies when you know what you’re doing. The problem is that most people don’t know what they’re doing. They’re burning 5x, 10x, sometimes 20x what they should on the exact same work, and they think that’s just what AI costs.

The models aren’t expensive. Your habits are expensive.

And with Claude usage limits dominating every AI community on the internet, those habits are finally catching up with people. So I want to be direct about what I’m actually seeing.

**Here’s what’s inside:**

- **The ChatGPT migration problem.** Why habits from ChatGPT are catastrophically expensive on Claude, and the single fix that changes everything.
- **What I’m actually seeing.** The four levels of token waste, from rookie to “advanced,” with real numbers.
- **The math that should scare you.** Clean vs. sloppy sessions, Mythos pricing implications, and why the gap keeps widening.
- **A diagnostic.** Six questions to find out if you’re the problem.
- **What we’re building.** The Stupid Button, KISS Commandments, and the Heavy File Ingestion skill already in the OB1 repo.

The usage limit crisis started getting loud about a week ago. Some of it is real infrastructure strain — but some of it is fixable.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260330_161_promptkit_1)

Token waste shows up in patterns, not one-off mistakes, which means you can’t fix it with a pep talk. You fix it with executable diagnostics that look at your actual habits and tell you what’s wrong.

The prompt kit below contains the **Stupid Button** — the blunt diagnostic from the article built as a copy-paste prompt — plus four supporting tools for the specific fixes it surfaces: rescuing bloated conversations without losing your work, routing tasks to the right model tier, auditing agent architectures against the KISS commandments, and translating your typical session into actual token economics so you can see where your budget went. These aren’t generic “be mindful about tokens” prompts. They’re built around the failure modes in this article, the ones I see dozens of times a week when people ask me why they’re hitting their limits.

Start with the Stupid Button, let it identify your waste patterns, then use whichever follow-up prompts match what it finds. And if you’re in the “rookies bleeding out on document ingestion” category: the **[Heavy File Ingestion](https://github.com/NateBJones-Projects/OB1/tree/main/skills/heavy-file-ingestion)** (link) skill in the continuously growing **[OB1 repo](https://github.com/NateBJones-Projects/OB1)** (link) stops that leak at the infrastructure layer — converts files to markdown on ingest and creates lightweight indexes so you never pay the raw-PDF penalty again.


## **The usage limit crisis**

If you’ve been anywhere near the Claude ecosystem in the last seven days, you’ve seen the meltdown. Anthropic confirmed that peak-hour session limits are now tighter, and your five-hour session window burns faster between 5am and 11am Pacific on weekdays. Pro subscribers are getting hit hardest. Even some Max users paying $100 to $200/month are reporting their meters jumping from 50% to 100% on a single prompt, and one Max 20x subscriber watched their allotment evaporate in 90 minutes doing the same work that used to last all day.

Reddit is furious. PCWorld, TechRadar, The Register, PYMNTS, MacRumors — all running stories about users hitting walls. Anthropic says about 7% of users are newly affected. The vibes are bad.

Some of this is real infrastructure constraint. Millions of new users showed up after Anthropic’s Pentagon standoff, the 1M token context window just went generally available at standard pricing with no more long-context surcharge, and agentic workflows through Claude Code and Cowork are burning compute at rates that flat-rate subscriptions were never designed to absorb. Anthropic is capacity-constrained. That part is real.

But nobody in the outrage cycle is asking the harder question, which is whether most of the people hitting their limits are doing it to themselves.


## **The ChatGPT migration problem**

I need to single this out because it’s the biggest driver of the complaints I’m seeing.

A massive wave of users just migrated from ChatGPT to Claude. Some came because of the Pentagon thing, some came because Claude is better at the work they do, and it doesn’t really matter why. What matters is they brought their ChatGPT habits with them, and those habits are catastrophically expensive on Claude.

ChatGPT and Claude handle conversation context in fundamentally different ways. ChatGPT manages long conversations by progressively compressing or dropping older messages to stay within limits. You lose history, but you never pay an escalating cost per message. You can let a thread run for 100 turns and your 100th message costs roughly the same as your 10th, because ChatGPT has already shed the first 80.

Claude doesn’t do this. Claude tries to keep your *entire* conversation in its context window. That enormous 1M token window Anthropic just made free at standard pricing? It means Claude *can* hold a massive conversation, and it will try. Every new message you send resubmits everything before it — every document you loaded, every response Claude generated, every tangent you explored.

This means the cost per turn in a Claude conversation escalates as the conversation grows, and not linearly. A message at turn 5 might cost around 2,000 tokens. By turn 30, the accumulated context could push that to 40,000 or more. At turn 50, you could be looking at 80,000 tokens per exchange. That’s the math of maintaining full conversational context, and I want to be careful not to overstate the precision of those numbers — they’re illustrative, not measured — but the direction is unambiguous. Every turn costs more than the last.

If you’re coming from ChatGPT and you’re used to letting threads run to 50, 60, 80 turns without thinking about it, you just discovered why you’re hitting your Claude limit in an hour. You’re paying the accumulated weight of every previous exchange on every new message, and Claude’s generous context window is letting you dig yourself deeper into that hole without any resistance.

The fix is simple but requires a habit change: **start new conversations constantly.** When you shift topics, open a fresh chat. When a conversation gets past 15 to 20 turns, copy the relevant context into a new chat and continue there. Think of Claude conversations as disposable work sessions, not persistent threads. This single habit change will do more for your usage limits than anything else in this article.


## **What I’m actually seeing**

I review AI workflows constantly — dozens a week. Architectures, agent harnesses, Claude Desktop setups, Cowork environments. And the token waste I see is so consistent, so patterned, and so fixable that I’ve started to think of token burn rate as the single most revealing metric of someone’s actual AI fluency. Not how many tools they use, not how many agents they’ve deployed. How many tokens they burn relative to what they accomplish.

Here’s what the spectrum looks like.

**The rookies are bleeding out on document ingestion.** This one drives me insane because it’s so easy to fix. A brand-new Claude Desktop user drags three PDFs into a conversation, maybe 1,500 words each. Just 4,500 words of text. They say “summarize these” and Claude processes the raw PDFs with all the formatting overhead: headers, footers, embedded fonts, layout metadata, the entire binary structure decoded into tokens.

Those 4,500 words of content could cost tens of thousands of tokens to ingest as PDFs. If they’d asked Claude to convert them to markdown first — which takes ten seconds with code execution — the same content would cost 5,000 to 6,000 tokens. That’s potentially a 10x penalty or worse for not knowing a single trick. And these users do it every session, multiple times a day, and then wonder why they hit their limit before lunch.

The waste compounds, too, because once those tokens are in your conversation history, they’re being resubmitted on every subsequent turn. By turn 10, you’ve effectively paid for those PDFs ten times. By turn 20, twenty times. The rookie who converted to markdown first is paying for 5K tokens per turn instead of tens of thousands. The gap widens with every message.

**The intermediate users are killing themselves with conversation sprawl.** I covered the mechanics above, but a specific case illustrates how invisible this problem is.

Someone showed me a conversation last week. 62 turns about a product launch. They’d loaded some reference docs early on, asked a bunch of planning questions, iterated on copy, went back and forth on positioning — normal knowledge work. By the end, each exchange was consuming roughly 85,000 tokens. They hit their limit in what felt like five minutes of actual work, and their reaction was “Claude is broken.”

Claude wasn’t broken. Claude was faithfully carrying 62 turns of accumulated context because they never started a fresh conversation. If they’d broken that into four 15-turn conversations, copying forward only the relevant decisions and outputs each time, the same work would have consumed roughly one-quarter of the tokens. Same output, same quality, 75% less burn.

**The plugin hoarders are paying a boot tax they don’t know exists.** One of our community members ran `/context` in Claude Code last week and discovered he was loading **66,000 tokens in every single session before doing anything.** Before a single prompt, before a single line of code — just the overhead of skills, plugins, and custom frontmatter he’d accumulated was eating over half his context window on boot.

He halved it by removing 36 plugins and cleaning up skill frontmatter. He’d been driving with the parking brake on. And he’s a technical user who builds things. Imagine what the average Claude Desktop user’s overhead looks like if they’ve been installing every shiny plugin they see recommended on Twitter.

**The advanced users are the most expensive disaster,** and it’s worth pausing on why because it’s counterintuitive. The self-described “context engineers” building agentic systems — you’d think they’d be the most disciplined. They’re often the worst, because the waste is hidden behind infrastructure.

The pattern looks like this: an agent harness that passes 200K tokens of unindexed context on every call. A system prompt that’s 15K tokens long because nobody pruned it after the fifth iteration. Reference documents dumped raw into every agent’s context window instead of indexed and retrieved on demand. No prompt caching, so the same stable context — system prompt, tool definitions, reference material — gets billed at full price on every single API call.

These people are spending $50 to $100/day on workflows that should cost $10 to $15. And they think that’s what AI costs.

---


## **The math that should scare you**

I want to make this concrete, because I think the abstract version of “you’re wasting tokens” doesn’t land until you see the actual numbers side by side.

**Sloppy session on Opus 4.6:** You feed raw PDFs into context (tens of thousands of tokens vs 5K), let a conversation sprawl to 30+ turns (escalating cost per turn), use Opus for everything including reformatting and proofreading. Over a five-hour session: roughly 800K to 1M input tokens, 150K to 200K output tokens including thinking. At $5/$25 per million, that’s $8 to $10 worth of compute.

**Clean session, same work:** Convert documents to markdown first, start fresh conversations every 10 to 15 turns, use Opus for reasoning and Sonnet for execution and Haiku for polish, scope context to what’s needed. Over the same five hours: 100K to 150K input tokens, 50K to 80K output. Blended rates across models. **About a dollar.**

Same output. Same quality of work. An 8 to 10x difference in cost. Scale it across a week and the sloppy user burns $40 to $50 in compute while the clean user burns $5 to $7. Across a 10-person team on API, that’s $2,000/month vs $250/month. For subscription users, it’s the difference between hitting your limit daily and forgetting limits exist.

Now here’s where it gets serious.

Anthropic’s Mythos model leaked on March 26, accidentally left in a publicly searchable data store along with close to 3,000 unpublished assets, because apparently the company building the world’s most advanced AI models configured their CMS with the security posture of a shared Google Doc. Mythos sits in a new tier called “Capybara,” above Opus. Anthropic calls it “a step change” in capabilities, dramatically better on coding, reasoning, and cybersecurity benchmarks. It’s the most capable thing they’ve ever built.

It’s also expensive enough that they’ve described it as not ready for general availability partly due to cost. A new pricing tier *above* Opus almost certainly means we’re looking at something north of $5/$25 per million tokens. Potentially well north. The leaked draft describes Capybara as “larger and more intelligent than our Opus models,” and “more expensive” — a new ceiling on the pricing structure, not a replacement.

The problem with token waste is that **it scales with the price of intelligence.** If you’re currently wasting 10x on Opus at $5/M input, that’s $45/M in unnecessary burn. When the next frontier model costs $15/M input, the same habits waste $135/M. Your sloppiness gets more expensive every time the models get better.

And the models will keep getting better. Every quarter, every release. The trajectory is unambiguous. The people who learn token discipline now will be the ones running Mythos-class models next quarter. Everyone else will be priced out of the frontier by their own habits.

---


## **The part where you find out it’s you**

I’ve been saying for weeks that what the industry actually needs is a stupid button. Not a gentle guide — a blunt diagnostic that looks at your actual behavior and tells you where you’re being dumb. We’re building one. But until it ships, here’s the manual version, and I’d encourage you to be honest with yourself, because the most expensive habit is the one you’ve convinced yourself isn’t a problem.

The first thing to check is whether you’re feeding Claude raw PDFs and images when all you actually need is the text. If you are, you’re paying a 10 to 20x markup on every document interaction and you probably don’t even realize it. Converting to markdown first takes Claude ten seconds with code execution. And when it writes that conversion code, save it — don’t let it regenerate a fresh script every time, because that regeneration itself costs tokens you didn’t need to spend.

The second thing — and this is the one that catches most people — is conversation length. When was the last time you started a fresh conversation? If you can’t remember, you’re carrying the context debt of potentially dozens of turns on every new message. Your most recent messages are the most expensive ones you’ve sent all day. Start new conversations aggressively. Copy over only what matters.

Then there’s model routing, and I want to be careful here because the advice isn’t “never use Opus.” Opus is your architect. It plans, reasons, makes judgment calls on hard problems. But it should not be reformatting your tables, proofreading your emails, or doing any task that doesn’t require real reasoning. Sonnet handles execution. Haiku handles cleanup. Switching models within a workflow isn’t a compromise — it’s the tell of someone who actually understands what they’re paying for.

There’s also the question of what’s loading in your context before you even type. Run `/context` in Claude Code and look at the number. If you’ve been accumulating skills and plugins without auditing them, you could be loading tens of thousands of tokens before your first prompt. Trim ruthlessly. Every token of system prompt overhead compounds across every turn of every conversation.

For API builders specifically: are you caching your stable context? Prompt caching gives you a 90% discount on repeated content. Cache hits on Opus cost $0.50/M vs $5/M standard. If your system prompt, tool definitions, and reference documents aren’t cached, you’re paying ten dollars for every dollar of stable context, and this should be the first thing you set up.

And finally — this one sounds strange until you see the numbers — are you letting Claude do web research the expensive way? A builder I know personally built a Claude Code plugin that routes all web searches through Perplexity instead of Claude’s native search. In our testing: 5x faster (6.8 seconds vs 36.2 seconds average), structured citations, and the number that matters: **10,000 to 50,000 tokens saved per search** because Claude doesn’t have to ingest and process raw web results in its context window. Over a research-heavy session, this single plugin saves more tokens than most people spend on their actual work. It’s **[open-source](https://github.com/justfinethanku/LEJ-Perplexity-Powered-Search-for-Claude)**.

If three or more of those hit home, you’re probably burning 5 to 10x what you need to. Which means your usage limit complaints aren’t really about Anthropic’s capacity. They’re about your workflow.


## **What we’re building to fix this**

Writing about token discipline helps, but tools help more, and I’ve learned enough by now to know that any habit you have to consciously maintain is a habit that eventually breaks.

**The stupid button (token burn tester)** exists at three levels, because the problem exists at three levels of sophistication. Level 1 is a prompt — something you run against your recent conversations that identifies the specific wasteful patterns: feeding raw documents, conversation sprawl, model misuse, redundant context loading. It looks at your actual habits and tells you what to fix first. Anyone can use it, any plan, no setup required. We’re targeting the Claude Desktop user who just wants to know “why do I keep hitting my limit?” and needs a concrete answer.

Level 2 is a skill — an invokable tool that audits your Claude Code or Desktop environment in real time. It measures your per-session token overhead, flags system prompt bloat, checks your plugin and skill loading, and gives you a before-and-after when you make changes. Think of it as a linter for your AI workflow. You wouldn’t ship code without running a linter. Why would you run an AI workflow without checking your token overhead?

Level 3 is the infrastructure layer — guardrails that sit directly on your knowledge store (your OpenBrain, your MCP servers, your reference context) so you stop burning tokens on *input.* Automatic markdown conversion before documents enter context, index-first retrieval instead of dump-and-search, context scoping that enforces minimum-viable-context per query. This is where token management stops being a discipline you have to maintain and becomes infrastructure that maintains itself. You shouldn’t have to remember to do the right thing every time. The system should make the wrong thing hard.

**The KISS commandments for agents** came from a pattern I kept noticing — people asking me “is my agent architecture stupid?” dozens of times a week, and the answer being yes for the same five reasons almost every time. We’re codifying it into something people can use as a pre-deploy checklist.

First, index your references. If an agent is getting raw documents instead of relevant chunks, you’ve already failed. The entire point of retrieval is to scope what the model sees to what it actually needs. Dumping a full document set into every agent call isn’t “giving the agent context” — it’s making the agent do retrieval work you should have done at the infrastructure layer.

Second, prepare context for consumption. Pre-process, pre-summarize, pre-chunk. A reference document should arrive in an agent’s context window ready to be *used*, not ready to be *read*. If the model’s first 5,000 tokens of reasoning are spent understanding the format of your input, you’ve wasted those tokens.

Third, cache your stable context. System prompts, tool definitions, persona instructions, reference material that doesn’t change between calls — all of it should be cached. At a 90% discount on cache hits, this is the lowest-effort, highest-impact cost reduction available. If you’re making thousands of agent calls a day and not caching, do the math on what you’re throwing away.

Fourth, scope each agent’s context to the minimum it needs. A planning agent doesn’t need your full codebase. An editing agent doesn’t need your project roadmap. Passing everything to every agent is architectural laziness, and it has a direct cost — both in tokens burned and in degraded agent performance. Models perform worse when they’re drowning in irrelevant context. Scoping isn’t just about cost. It’s about quality.

Fifth, measure what you burn. If you don’t know your per-call token cost, you’re flying blind. Instrument your agent calls. Track input tokens, output tokens, thinking tokens, cache hit rates. You can’t improve what you don’t measure, and most teams building agentic systems have literally no visibility into their per-call economics.

Five rules. Most agentic architectures I review violate at least three of them. Following all five typically cuts costs by 5 to 10x and — this is the part people don’t expect — makes the agents *perform better* because they’re not drowning in irrelevant context.


## **The real point**

There’s a cultural problem underneath all of this, and I’ve been thinking about why it’s so persistent.

Somewhere along the way, people started treating high token consumption as a badge. Burning through your rate limit fast means you’re doing important work. Running up a big API bill means you’re building something serious. Token count became a vanity metric — the AI equivalent of “I’m so busy.”

It’s the opposite. High token burn is almost always evidence that you’re making the model *process* when you should be making it *think.* You’re paying Claude to ingest, parse, and reorganize information that should have been prepared before the prompt was sent. Processing is expensive and adds no intelligence. Thinking — when the context is clean, scoped, and pre-digested — is cheap and is where all the value lives.

Pennies per user. That’s what a complex, multi-step AI pipeline costs on the most expensive models available when the token management is tight. Your mileage may vary depending on your use case and scale, but the order of magnitude is real. That number should radicalize you.

Token discipline is going to be one of those skills that separates people who use AI from people who are fluent in it. Not because it’s hard — it’s actually one of the easier things to fix once you see it. But because most people never look. They pay the bill, or they hit the limit, and they assume that’s just what AI costs. It isn’t. And the longer you wait to figure that out, the more expensive the lesson gets.

[![](https://substackcdn.com/image/fetch/$s_!DbuK!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef8a9bf5-708f-4894-bafa-42571151461f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!DbuK!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fef8a9bf5-708f-4894-bafa-42571151461f_1024x1024.png)
