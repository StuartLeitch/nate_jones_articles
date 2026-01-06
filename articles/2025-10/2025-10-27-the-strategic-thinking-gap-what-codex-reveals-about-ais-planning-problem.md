---
title: "The Strategic Thinking Gap: What Codex Reveals About AI’s Planning Problem"
author: "Nate Jones"
published: 2025-10-27
url: https://natesnewsletter.substack.com/p/how-i-made-a-new-ai-discovery-a-coding
audience: everyone
scraped_at: 2026-01-05 19:13:24
---

I was writing a post on strategy, and I accidentally made an AI discovery.

I believe this is the very first detailed guide ever to using the OpenAI Codex model for a non-engineering purpose.

That’s surprising, because OpenAI released the Codex model for code, specifically.

Despite that, it turns out Codex is by far the best strategic thinking AI out there.

Not one that replaces you. But one that helps you think better.

Because strategy is hard. For most of us I find it feels abstract and difficult to apply.

This post is all about making strategy (with AI) ACTUALLY useful.

And that’s a tall order, because so far LLMs haven’t helped much with strategy.

They’re not great at strategic thinking without structure. And when they do strategy, they communicate it badly—overwritten, unfocused, proving they read the textbook instead of helping you decide.

Not anymore. I’m writing this guide so it’s easy for you to get started with the best strategy tool on the market.

Strategy isn’t just for executives. It’s not some secret practice.

Strategy is just sharp thinking about hard problems, communicated well.

Everyone makes decisions with long-term consequences. Everyone needs to think through tradeoffs before committing.

And I don’t want you to start from scratch with a gnarly problem like strategy, because strategy requires a different prompting approach than traditional asks of AI.

So I built these 29 strategy prompts to help you do the strategy work with your LLM of choice. Yes, they’ll work with any AI, even though they’ll work great with Codex.

Here what’s in the prompt pack:


#### AI Strategy & Implementation

- AI Model Strategy: API vs. Fine-tune vs. Build
- AI Architecture: RAG vs. Fine-tuning vs. Prompt Engineering
- AI Vendor Selection: Provider Strategy
- AI Evaluation Strategy: How to Measure Quality
- AI Data Strategy: Collection, Quality, and Moat
- AI Product Moat: What Makes You Defensible


#### Strategic Portfolio & Investment

- M&A: Build vs. Buy vs. Partner
- Portfolio Strategy: Invest, Harvest, or Divest
- Sunset vs. Invest Decision
- Fundraising: Timing, Amount, and Terms


#### Product Strategy & Positioning

- Platform vs. Point Solution
- Feature Prioritization Under Constraint
- Product Packaging / Bundling Strategy
- Brand Positioning Pivot
- Competitive Response


#### Technical Architecture & Infrastructure

- Technical Architecture: Rewrite vs. Optimize
- Capacity Planning / Technical Investment
- Make vs. Buy for Support/Operations


#### Go-to-Market & Channel Strategy

- GTM Strategy: Customer Segment Focus
- Channel Strategy: Direct vs. Partner
- Product-Led vs. Sales-Led GTM Motion
- Customer Success Model


#### Monetization & Market Strategy

- Pricing Model Evolution
- Freemium / Monetization Strategy
- Geographic Expansion: Market Selection
- Marketing Budget Allocation


#### Talent & Organization

- Team Build-Out: Hire vs. Contract vs. Offshore
- Talent Retention: Comp Adjustment vs. Role Change vs. Accept Attrition
- Sales Territory/Structure Redesign

I know. A lot of prompts.

But the point is not the number. It’s that I want you to have actual starting points to jump in on tough decisions that matter in a way that’s useful.

Anyway, the prompts are just the start. We’re packing in this guide:

- The 29 strategy prompts that work anywhere
- A quick start guide to Codex for newbies complete with an install prompt!
- A detailed breakdown of how Codex works better for strategy vs other models
- A reflection on strategy and how to do it well in the age of AI
- A note on emergent properties in LLMs (like how we discover new stuff—like this)
- A bonus note from a kid in the 80’s on not being afraid of the command line :)

Almost by definition, strategy matters more than most things. I want us all to have tools to get better at it, and I am so thrilled I discovered that Codex is so good at this.

So jump in, have fun and happy strategizing!


## [Grab all 29 strategy prompts here](https://www.notion.so/product-templates/Strategy-Prompts-for-Codex-2995a2ccb5268079922be40ac6a619c6?source=copy_link)

These 29 prompts are designed to help you work through complex strategic decisions—the kind of multi-dimensional analysis where Claude Opus 4 (Codex) particularly excels. Each prompt guides you through evaluating trade-offs using multiple strategic frameworks, surfacing hidden assumptions, identifying critical uncertainties, and developing defensible recommendations when there’s no obvious right answer.

Codex’s extended thinking capacity and ability to maintain coherent reasoning across layered problem spaces makes it especially effective for these challenges, which often require holding competing considerations in tension while avoiding common cognitive traps.

That said, these prompts are model-agnostic by design: they’ll work productively with any capable LLM (Claude 4.5, GPT-5, Gemini 2.5 Pro, etc.) to sharpen your strategic thinking, surface blind spots, and structure messy decisions. Use these prompts when you need to move past generic frameworks and quick takes—they’re built to help you develop the nuanced, contextual analysis that real strategic decisions require, turning ambiguous situations into actionable clarity.

---


# **The Strategic Thinking Gap: What Codex Reveals About AI’s Planning Problem**


## **Quick Start: What You Need to Know**

**What is Codex?** OpenAI’s command-line AI agent, launched May 2025, now generally available. It’s powered by GPT-5-Codex (or codex-mini for faster tasks) and marketed as a coding tool, but it’s actually the best strategic thinking partner I’ve found for any technically adjacent problem.

**Installation (2 minutes):**

1. Open your terminal (Command Prompt on Windows, Terminal on Mac)
2. Run: npm install -g @openai/codex
3. Sign in with your ChatGPT account when prompted

Additional Setup Notes

- You may need to set your OpenAI API key as an environment variable (for direct API usage, which is not required): `export OPENAI_API_KEY=”your-api-key”`.
- Windows users may need to use WSL or PowerShell/Git Bash, but the same npm command applies.
- Verifying install: Run `codex --version` to confirm it’s installed correctly.


#### [An initial prompt for install help](https://www.notion.so/product-templates/Codex-install-prompt-2995a2ccb526808b894fe878899ab2a8?source=copy_link)

---

**Permissions:** Included with ChatGPT Plus ($20/month for 30-150 local tasks every 5 hours), Pro ($200/month for 300-1,500 tasks), or API access. Free tier has limited access.

**Sample strategy prompts to try immediately:**

- “I’d like to think through a complicated problem. Can you help me lay out options and technical pros and cons? Specifically, I’m looking to design [describe your system]. What strategic questions emerge that I need to answer to design this effectively?”
- “I’m evaluating build versus buy for [capability]. What technical approaches exist and what are the tradeoffs I need to consider?”
- “I need to design a [type of pipeline/workflow] that balances [competing concerns]. What are the key architectural decisions I need to make?”
- “I’m planning a migration from [current state] to [future state] for a [size] team. What are the highest-risk failure modes and how should I sequence the work?”

**Follow-up prompts after you get initial analysis:**

- “Ladder this up into 3-5 highest leverage questions”
- “Summarize this for a non-technical 12th grade reading level. Present options and strategic questions clearly and concisely.”

Now here’s why this matters and what I learned comparing it to Claude Code.

---


## **The Pattern You Just Watched**

The video above shows something that should concern anyone building with AI: we have a planning problem masquerading as a capabilities problem. When I gave identical prompts to Codex and Claude Code—asking them to help me think through a multi-agent system design—I didn’t get different levels of quality. I got different cognitive modes entirely. Codex stayed strategic. Claude Code went tactical immediately. And that gap reveals something fundamental about how we’re using these tools and what we’re missing.

This isn’t about which model writes better code. Both can write excellent code. This is about which model thinks better before any code gets written, and more importantly, what that distinction tells us about where the real leverage in AI actually lives right now.

In the video, I asked both systems to help me design a multi-agent workflow for JIRA ticket triage. The system needs to assess whether reported issues are bugs, trigger code review if confirmed, and begin drafting pull requests. There are obvious fail states and degradation paths to consider. This is the kind of problem that requires architectural thinking before implementation thinking.

Codex came back with three distinct architectural approaches. It presented them at the right altitude—tool-augmented, event-driven, or agentic pipeline—and then asked me component-level questions about degradation paths, classification uncertainty, and model hallucination. All of this was scannable, legible, and operating at the strategic layer. When I asked it to ladder up the highest leverage questions, it gave me automation boundaries, quality metrics, governance considerations, operational resilience, and investment tradeoffs. These are the right questions for system design.

Claude Code did something completely different. It jumped immediately into single-agent versus multi-agent implementation, started building out confidence threshold tables, and dove into specific failure mode classifications before I’d validated the approach. It wasn’t wrong—nothing it proposed was facially incorrect—but it was solving the wrong problem. I asked for strategic thinking and got tactical execution. The bias for action that makes Claude Code excellent for iterative coding sessions actively undermined its value for planning work.

This distinction matters more than most people realize because we’re at an inflection point where the bottleneck in AI-assisted development has shifted from execution to planning. Cursor didn’t launch planning mode on a whim. They launched it because their users kept getting trapped in implementation rabbit holes, building the wrong thing efficiently. The planning layer is where leverage lives now, and most of the tooling we have access to is optimized for the wrong layer.


## A Second Test: Strategic Business Analysis

To see if this pattern held beyond technical system design, I ran a second test with a business case: evaluating two competing market entry strategies for a fictional motorcycle company entering the U.S. market in 1962. Team A proposed competing head-on with Harley-Davidson in premium performance. Team B proposed creating a new market for practical, everyday transportation bikes.

This is intentionally easy mode. The parametric weights of these models almost certainly include the Honda case study—this is one of the most famous examples of disruptive innovation in business school curricula. I’m not asking for genuinely new strategic insight. I’m deliberately slow-rolling the hard stuff and asking for really clear communication of analysis the models should already know how to do.

I tested Claude Sonnet 4.5, GPT-5 with extended thinking, Claude Code, and Codex. All four produced competent analysis, identified the right frameworks, and reached similar conclusions. But Codex won on information density and respect for reader intelligence.

**Claude 4.5** wrote like a strategy consultant producing a deck for clients who need convincing. When applying disruptive innovation theory: “Examining these proposals through multiple frameworks reveals fundamental differences in their strategic logic. Disruptive Innovation Lens: Team B proposes classic market-creating disruption. They’re targeting non-consumption—people who would never buy a Harley-Davidson...” Highly readable but information-inefficient at roughly 2,400 words. This is the model for external communications, not internal memos.

**GPT-5 Thinking** produced structured output with nested bullets and heavy indentation. On the same analysis: “Resource-based view (RBV). Our VRIN assets today: small-engine manufacturing know-how, reliability/QC, simple designs, and a currency cost advantage. Team A discards these and demands new engines, frames, speed validation...” Solid content but formatted like expanded research notes rather than synthesized argument. You reassemble the reasoning yourself.

**Claude Code** used formal numbered subsections and careful hierarchy—a consulting firm’s written deliverable. But it suffered from demonstrative rigor: proving it knows what good analysis looks like by including every canonical element. The cognitive traps section ran 200+ words on availability bias, sunk cost fallacy, confirmation bias, and planning fallacy. All correct, but does the CEO need a tutorial on cognitive bias, or does she need you to identify the specific traps this decision presents?

**Codex** made different choices. Same disruptive innovation analysis: “Team B via disruptive innovation framing positions Pacific as a market creator, targeting non-consumers (students, commuters) with a low-cost, reliable ‘good-enough’ option.” No announcement of framework use. No promise to reveal insights. It applies the analysis and moves on.

This pattern held throughout. Codex dispatched the inferior option quickly rather than giving false equivalence. It integrated frameworks into argument flow rather than announcing them. On cognitive traps, it identified three specific risks and three concrete mitigations—no extended meditation on why bias matters.

The result read like an internal memo from a senior strategist who respects your time. Complete without being exhaustive, decisive without being arrogant.

The differences weren’t about analytical depth—all four reached similar conclusions. The difference was information architecture. Claude 4.5 writes for clients who need persuasion. GPT-5 Thinking writes to show reasoning process. Claude Code writes to demonstrate methodological completeness. Codex writes for executives who need to make a decision.

When producing strategic analysis for sophisticated readers, the goal isn’t proving you know frameworks. It’s presenting the clearest possible argument in the smallest space while preserving necessary complexity. Codex won both tests not because the analysis was better, but because it respected the reader’s time and intelligence. In professional strategic communication, that respect separates analysis that’s correct from analysis that actually gets used.


#### [Curious? Check out all 4 responses here](https://www.notion.so/product-templates/The-business-case-study-test-2995a2ccb5268031ad5acebe627ab74a?source=copy_link)


## **Why Strategic Thinking Is Different From Execution**

There’s a fundamental cognitive difference between strategic thinking and tactical execution that maps surprisingly well onto how different AI tools behave. Strategic thinking requires maintaining altitude, resisting premature specificity, and identifying high-leverage decision points before committing to an approach. Tactical execution requires the opposite—bias for action, rapid iteration, and getting concrete fast.

These aren’t better or worse modes. They’re different modes for different contexts, and using the wrong mode at the wrong time is expensive. If you execute tactically when you need to think strategically, you build the wrong thing. If you stay strategic when you need to execute tactically, you never ship. The problem is that most AI tools don’t distinguish between these modes cleanly, and more importantly, most users don’t know how to prompt for the mode they actually need.

Codex has a distinct cognitive profile that makes it exceptional at strategic work. It naturally operates at higher levels of abstraction. When you ask it about system design, it gives you architectural options before implementation details. When you ask it about tradeoffs, it identifies the decision points that matter most. When you ask it to translate technical concepts, it can restate them at any level of abstraction you need without losing fidelity. This isn’t just a matter of prompt engineering—though prompting matters—it’s about how the model was trained and what behaviors were reinforced during that training.

Claude Code has the opposite profile, and this makes it excellent for different use cases. It wants to move fast, iterate quickly, and get into implementation. That bias for action is genuinely valuable when you’re in the middle of a coding session and you want to explore ideas through code. But when you’re trying to evaluate architectural approaches or design system boundaries, that same bias becomes a liability. You end up debugging decisions you shouldn’t have made in the first place.


## **Sidebar: On Discovering Emergent Properties**

Large language models develop capabilities that weren’t explicitly intended by their creators. Codex’s strategic thinking ability is one of these emergent properties. OpenAI trained it on code and software engineering tasks, marketed it as a coding agent, and most coverage focuses on its ability to write and debug code.

But somewhere in that training on pull requests and technical documentation, it learned to maintain abstraction levels, structure complex decision spaces, and compress analysis into high-leverage questions. Nobody designed this capability explicitly - it emerged from the model’s exposure to how engineers actually think about problems.

This pattern shows up across AI tools: they develop abilities beyond their marketed use cases, and most users never discover them because they take the marketing literally. The practical insight is that you should experiment with tools beyond their stated purpose. The capabilities are already there. You just have to try things that weren’t in the demo. Sometimes, you get a nice surprise!


## **The Real Use Case Nobody Talks About**

Here’s what people are systematically missing about Codex: it’s not a coding tool that happens to do other things. It’s a technical thinking tool that happens to write code. And that distinction opens up an enormous range of use cases that have nothing to do with software engineering per se.

Product managers can use Codex to design system architectures without writing the code themselves. They can explore technical tradeoffs, understand dependency graphs, and evaluate build-versus-buy decisions at a level of sophistication that was previously only accessible if you had senior engineering expertise. The tool doesn’t just answer questions—it helps you understand what questions you should be asking.

Executives evaluating strategy can use Codex to pressure-test vendor claims, understand architectural implications of different choices, and get ground truth on what’s actually hard versus what’s just complex. The strategic planning layer that Codex excels at maps directly onto executive decision-making contexts where you need insight without needing to execute the implementation yourself.

Consultants planning client implementations can use Codex to rapidly explore option spaces, identify risk surfaces, and develop recommendation frameworks that account for technical constraints. The ability to ladder up from specifics to strategic questions and back down again is exactly what consulting work requires, and Codex does this more naturally than any other tool I’ve found.

The through-line in all these use cases is that you’re using AI to think about systems, not to build them. And thinking about systems is actually more accessible than most people realize. You don’t need to be able to write production code to understand system design. You don’t need an engineering degree to evaluate architectural tradeoffs. What you need is a thinking partner that can operate at the right level of abstraction for the conversation you’re trying to have, and that’s what Codex provides.


## **What This Reveals About AI Positioning**

We’re in a bizarre moment where the best strategic thinking tools are being marketed as coding tools, and this creates massive accessibility barriers. Non-engineers hear “Codex” and think “not for me.” They hear “Claude Code” and assume it’s for software developers. But the actual capabilities these tools provide—systematic thinking about complex technical problems—are relevant to a much broader audience than just people who write code professionally.

This is a positioning problem that’s actively harmful. We’re leaving enormous value on the table because people don’t realize these tools can help them think through problems they’re already facing. The person who needs to design a content moderation pipeline doesn’t think of themselves as needing a coding tool. They think they need strategic advice, architectural guidance, or consulting support. But what they actually need is exactly what Codex provides: a systematic way to explore option spaces, understand tradeoffs, and identify decision points before committing to an approach.

Anthropic does this, by the way. They use Claude Code for legal work, marketing projects, HR systems. They understand that the underlying capability isn’t about code generation—it’s about systematic thinking applied to complex problems. But that understanding hasn’t translated into how these tools are marketed or explained to potential users, and so most people never discover these use cases.

The positioning problem extends beyond just who uses these tools to how they use them. Even people who know these tools exist often use them wrong because they don’t understand the cognitive mode distinctions I described earlier. They use Codex for rapid iteration when they should use Claude Code. They use Claude Code for strategic planning when they should use Codex. They use Claude.ai for technical system design when they should use either of the command-line tools. And nobody is explaining these distinctions clearly because everyone is too focused on model benchmarks and API pricing.


## **The Installation Barrier Is Fake**

One reason people avoid these tools is that they live in terminals, and terminals feel scary if you’re not a developer. But this fear is completely unfounded. The installation process I described at the top of this article is genuinely the entire process. Two minutes. One command. Sign in with your existing account. Done.

I know this feels daunting if you lived through the Windows and DOS era where command-line interfaces were genuinely hostile to casual users. But modern CLI tools are nothing like that. They’re designed for accessibility, they have good error messages, and they hold your hand through setup. The terminal isn’t something to fear—it’s just a different interface paradigm, and one that happens to be extremely efficient for certain kinds of work.

The actual barrier isn’t technical. It’s psychological. People have convinced themselves that terminals are for developers, and therefore anything accessed through a terminal isn’t for them. But this belief is self-fulfilling. If you never try these tools because they’re in terminals, you’ll never discover that they’re not actually that scary and that they provide capabilities you can’t get anywhere else.


## **How to Think With Codex**

The key to using Codex for strategic thinking is understanding how to prompt for the cognitive mode you want. This isn’t about memorizing magic incantations—it’s about being clear with the system about what altitude you want to operate at and what kind of thinking you need.

When you’re in planning mode and you need strategic clarity, you start with the prompt structure I gave you at the top of this article. The phrase “I’d like to think through a complicated problem” signals to the system that you’re not asking for implementation—you’re asking for architectural thinking. The request for “options and technical pros and cons” reinforces that you want to stay at the strategic layer. And the explicit question about “what strategic questions emerge” tells the system to help you identify decision points rather than jumping to solutions.

Once you have that first-pass strategic analysis, you can ladder up further by asking explicitly for the highest-leverage questions. “Ladder this up into three to five highest-leverage questions” is remarkably effective at getting the system to identify decision points that actually matter versus details that can be deferred. This is the kind of thinking that’s genuinely hard for humans to do systematically because we get anchored on local details, and having a tool that can step back and identify the critical path is enormously valuable.

And when you need to share your thinking with non-technical stakeholders—which is most of the time if you’re doing strategic work—you can ask Codex to translate everything it just told you into plain language. The system understands this request and can restate technical concepts without losing fidelity. This is not a trivial capability. Most technical documentation fails at this because human experts struggle to remember what it’s like not to know what they know. Codex doesn’t have this problem.


## **When to Use What Tool**

Understanding which tool to use for which context is half the battle. Codex excels when you’re in planning and design phases, when you need to evaluate multiple approaches before committing, when you’re presenting to non-technical stakeholders, or when you’re making architectural decisions that will be expensive to reverse. The structured, scannable outputs it produces and its natural tendency to operate at higher levels of abstraction make it ideal for these contexts.

Claude Code excels when you’re actively iterating on code, when you want conversational back-and-forth during implementation, when you prefer exploratory problem-solving through rapid prototyping, or when you’re debugging and refactoring existing systems. The bias for action that undermines its strategic thinking capabilities is exactly what makes it valuable for execution contexts.

Claude—the web interface you’re probably most familiar with—excels when you’re writing documents or content, when you need to search your Drive or email for context, when you want conversational AI with memory across sessions, or when you’re not working on technical systems at all. It’s the most accessible interface and the best general-purpose tool, but it’s not optimized for either strategic technical thinking or rapid code iteration.

The mistake most people make is using the same tool for everything because it’s the one they know best. But these tools have genuinely different cognitive profiles, and matching the tool to the task type compounds your effectiveness dramatically. Using Codex for strategic planning and Claude Code for implementation gives you the best of both worlds. Using the wrong tool for the context means fighting against the tool’s natural tendencies, and that’s exhausting and inefficient.


## **What You Should Try Next**

If you’re facing a complex decision right now—not implementing it, just designing it—try using Codex to think it through. Install the tool using the instructions at the top of this article if you haven’t already. Use the prompt structure I described. Ask for architectural options, tradeoffs, and strategic questions. Then ask it to ladder up the highest-leverage decision points. Then ask it to translate everything into language you can share with non-technical colleagues.

Compare what you get from this process to what you’d get from Claude Code or ChatGPT or any other tool you normally use for this kind of thinking. The difference won’t be subtle. You’ll get more structured thinking, clearer identification of decision points, and better altitude control throughout the conversation. And that difference compounds over time because every strategic decision you make well creates leverage for everything downstream.

The broader lesson here is that we’re still figuring out what these tools are actually good for and how to use them effectively. The marketing says they’re for coding. The reality is they’re for thinking about complex systems, and coding happens to be one application of that capability. But strategic planning, architectural design, risk assessment, option evaluation—these are all instances of the same underlying capability, and they’re all more accessible than most people realize.

Strategic thinking used to require deep expertise or expensive consulting support. Now it requires a two-minute install and knowing how to ask the right questions. That’s a fundamental shift in accessibility, and we’re only beginning to understand what it enables.

[![](https://substackcdn.com/image/fetch/$s_!CJ6u!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3063276f-cfed-446d-bc34-7b9e4d70eb65_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!CJ6u!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3063276f-cfed-446d-bc34-7b9e4d70eb65_1024x1024.png)
