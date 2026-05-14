---
title: "You're charging 2023 rates for work AI does in 40 minutes + 2 prompts to see your real exposure"
author: "Nate Jones"
published: 2026-04-07
url: https://natesnewsletter.substack.com/p/313-became-438000-in-30-days-youre
audience: everyone
scraped_at: 2026-05-14 14:34:00
---

Most of the world runs on inefficiency. Not broken-ness. Not stupidity. Gaps — between what something costs to produce and what the market will pay for it, between how fast information moves and how fast anyone acts on it, between what’s possible and what most people know is possible.

The law firm that bills ten hours for two hours of thinking and eight hours of research and formatting isn’t a scam. It’s a business built on the historical cost of finding the right precedent. The consulting engagement where a team spends six weeks building a deck the client could assemble in a day if they had the same information access. That’s a gap in information distribution. The offshore dev team that exists because a San Francisco engineer and a Bangalore engineer cost radically different amounts for overlapping work. That’s a pricing gap built on geography.

These gaps have a name. Economists call them arbitrage — the art of exploiting the distance between what something is worth and what someone is currently paying for it. Since the days of Ea-nasir, a Babylonian copper merchant so notorious for shipping substandard ingots that his customers’ complaint letters survived on clay tablets for nearly four thousand years, the entire economy has been built on these gaps. Whole industries, career paths, and business models exist because some inefficiency was too expensive, too complex, or too invisible to close.

AI is closing them. Not slowly, the way previous technologies did — incrementally, over decades, giving industries time to adapt. AI is closing them on the timescale of model releases. Months. Sometimes weeks.

And every time one closes, three new ones open somewhere else. That’s the dynamic nobody is talking about clearly, and it’s the single most important thing to understand about how work is changing right now.

In late 2025, a bot on the prediction market Polymarket turned $313 into nearly half a million dollars in a single month. It didn’t predict anything. It just closed a pricing gap faster than humans could. A developer claimed to have rebuilt the entire system using Claude in about forty minutes. That bot is a proof of concept for what’s happening to every industry. And 92.4% of the wallets on the same platform lost money, which tells you everything about the difference between having access to AI and knowing what to build with it.

**Here’s what’s inside:**

- **The $313 proof of concept.** How a Polymarket bot revealed the mechanism underneath every industry — and why almost everyone who copied it got slaughtered.
- **The taxonomy of what’s closing.** Five categories of inefficiency AI makes newly exploitable, from speed gaps to the knowledge asymmetry that funded thirty years of offshoring.
- **The compression.** Why democratized access to AI creates the appearance of democratized advantage, and what separates the 7.6% who profit from the 92.4% who don’t.
- **The rotation.** Why the Mythos leak previews a world where disruption never settles — and what that means for every strategic plan written this year.
- **Three questions that map any industry’s future.** A diagnostic you can run on your own role, company, or sector to see where value is heading before it gets there.

The world was built on slowly exploited inefficiencies. The “slowly” part is over.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260328_uqb_promptkit_1)

Reading about arbitrage gaps is useful. Diagnosing your own is what changes decisions. This kit includes two structured prompts — **The Arbitrage Audit** for leaders who need to see which specific inefficiencies their business model depends on and how fast each one is compressing, and **The Career Gap Map** for individual contributors who want an honest read on whether their current skill mix is appreciating or depreciating on a timeline of quarters. Both run as guided interviews: the AI asks hard questions, pushes back on vague answers, and produces a concrete diagnostic with compression timelines and a prioritized action plan. I built them this way because most people can name “AI is changing things” but can’t name the *specific gap* their paycheck depends on — and if you can’t name it, you won’t see it closing until someone else has already built the system that exploits it. The Arbitrage Audit produces a five-category gap map with structural-vs-informational ratings and an unhedged honest read on whether your organization is on the 7.6% side or the 92.4% side. The Career Gap Map calculates your exposure score — the percentage of your current week spent on tasks AI can compress to near-zero — and builds a migration plan toward the upstream skills where value is heading. Run whichever one matches your situation, or run both.


## The $313 proof of concept

In late 2025, a bot on the prediction market Polymarket turned $313 into roughly $438,000 in a single month. It had a 98% win rate across 6,615 trades. It didn’t predict anything.

The bot exploited a simple fact: Polymarket’s short-duration crypto contracts updated their prices slower than the spot exchanges where the underlying assets actually traded. When Bitcoin moved sharply on Binance, sharply enough to make the outcome of a 15-minute contract near-certain, Polymarket was still showing roughly 50/50 odds. The bot bought the mispriced side. Over and over. While humans slept.

A developer reverse-engineered the strategy and claimed to have rebuilt a working version in Rust using Claude in about forty minutes. The full stack — real-time price monitoring, probability calculation, position sizing, automated risk controls — generated from a single prompt session. What previously required a quantitative research team, software engineers, and risk managers now required one person with a laptop and an API key.

That bot wasn’t alone. A separate Claude-powered system generated $2.2 million in two months using probability models trained on news and social data. A swarm model trained on three years of NBA data reportedly generated $1.49 million trading sports contracts, according to the trader who built it. Comparative data showed bots using identical strategies to human traders captured roughly twice the profit. The strategy wasn’t better. The execution was flawless. No fatigue at 3 AM, no oversized positions on “confident” bets, no missed trades during lunch. Humans knew what to do. They just couldn’t do it consistently 6,615 times in a row.

I’m not telling you this because crypto prediction markets matter to your career. I’m telling you because Polymarket is the one place where you can see the mechanism with perfect clarity. The data is on-chain and the trades are public. The compression is measurable: average arbitrage windows reportedly shrank from 12.3 seconds in 2024 to 2.7 seconds in early 2026, according to on-chain analysis. You can watch the inefficiency close in real time.

That same mechanism is happening in every industry. AI identifying a gap, building the system to exploit it, compressing the window until only the most sophisticated players survive. You just can’t see it as clearly because most industries don’t publish their pricing lags on a public blockchain.


## The taxonomy of what’s closing

Once you have the lens (look for the inefficiency that AI makes newly exploitable), you start seeing it everywhere. Five categories keep showing up.

**Speed gaps.** One system updates slower than reality. This is the Polymarket case, and it’s the easiest to understand: the bot reacted faster than the market could reprice. But the same structure exists in any business where information propagates through intermediaries. Your competitor’s pricing model updates in real time while yours updates weekly. Their customer support bot resolves issues in seconds while your team takes 24 hours. Their hiring pipeline screens candidates in minutes while yours takes three weeks. Each of these is a speed gap, and each one is now closable by whoever builds the faster system first.

**Reasoning gaps.** Not speed. Interpretation. A Fed governor makes a statement. A regulatory filing drops. An earnings call reveals a change in strategy. The information is public and available to everyone simultaneously. The gap is in how quickly and accurately someone can reason about what it means, can update their model of the world and act on the new probabilities. LLMs do this faster and more consistently than humans, not because they’re smarter, but because they don’t get tired, don’t have a backlog of other things to read, and can process the full context of a document in seconds rather than hours. The bot that generated $2.2 million didn’t have information others lacked. It interpreted public information faster and acted on the interpretation before the crowd caught up. In your industry, the analog is every decision that waits for someone to read, synthesize, and recommend. That wait time is a reasoning gap. It’s closing.

**Fragmentation gaps.** The same thing is priced differently in different places because nobody’s looking at all the places simultaneously. Sports arbitrage bots scan Polymarket against traditional bookmakers and lock in risk-free margins by buying both sides when the combined price implies a mathematical edge. That’s the financial version. The business version is the consultant who charges $50,000 for an analysis that synthesizes five publicly available data sources, where the value isn’t in the data, it’s in the aggregation. AI does aggregation for free. The intermediary whose value proposition is “I see across silos you can’t” is sitting on a fragmentation gap, and that gap is compressing fast.

**Discipline gaps.** The inefficiency isn’t in the market or the information. It’s in the human executing on it. This is the dynamic we saw in the bot data: same strategy, double the profit, because execution never degraded. Six thousand consecutive decisions, each precisely calibrated. The discipline gap is everywhere in business: the sales team that knows the playbook but doesn’t follow it consistently, the content pipeline that produces erratic quality depending on who’s working that day, the operations team that drifts from protocol under pressure. Anywhere human performance degrades with fatigue, emotion, or boredom is a discipline gap. AI doesn’t close it by replacing the human. It closes it by enforcing the consistency the human can’t maintain alone.

**Knowledge asymmetry gaps.** This is the big one. The macro layer. For thirty years, the dominant gap in the global economy was the labor pricing gap: same work, different cost, depending on geography. Offshore teams existed because the gap between a San Francisco engineer and a Bangalore engineer was wide enough to build an industry in. AI replaces labor arbitrage with intelligence arbitrage. The unit of value shifts from the person-hour to the outcome. One prompt generates a working system that scales at near-zero marginal cost. The company that produces a deliverable in three hours that its competitor still scopes at three weeks has an intelligence gap in its favor. And unlike the labor gap, which was stable for decades because you can’t suddenly move a million engineers, the intelligence gap shifts with every model release.

A recent piece drew the parallel to CNC lathes in the 1980s. When computer-controlled machining arrived, a shop owner could buy a CNC lathe, hire a less-skilled operator, and produce precision parts in a fraction of the time hand milling required. The smart shops hid the machines in the back room and kept the machinist out front for clients. They charged the old rate for work done at the new cost. The margin was enormous. For a while. Then everyone got CNC machines. Prices for many machined components dropped dramatically. The bespoke premium evaporated because precision was no longer a rare skill. It was a machine setting.

That’s the exact arc playing out right now in every knowledge-work industry. The agencies, consultancies, and service firms that are currently using AI to produce deliverables at a fraction of the old cost, while still charging the old rate, are living inside that window. It’s real and profitable. And it’s closing, because knowledge asymmetry doesn’t survive commoditized tools.


## The compression

Here’s the part of the story that the viral threads always leave out.

92.4% of Polymarket wallets lose money.

The bot that turned $313 into $438,000 didn’t win because Claude is available. Claude is available to everyone. It won because someone built a system: dedicated Polygon RPC nodes for sub-100-millisecond execution, Kelly Criterion sizing enforced algorithmically, automated kill switches, 72-hour runtimes without a single manual override. Claude was a component. The system was the strategy.

The copycats who read the viral thread, pasted the prompt, and funded a wallet mostly got slaughtered by transaction costs, gas fees, and the reality that by the time a strategy is public knowledge, the window has compressed past the point where unsophisticated implementations are profitable. An estimated 73% of arbitrage profits now go to bots executing under 100 milliseconds, according to on-chain analyses. If you showed up with a Python script and a consumer internet connection, you weren’t competing. You were donating.

This dynamic matters far beyond crypto because it reveals the core illusion of the current moment: the democratization of AI tools creates the appearance of democratized edge. Access is universal. Advantage is not.

Everyone has access to Claude. Not everyone has reorganized their workflow, decision-making, feedback loops, and quality systems around what Claude makes possible. The executive who deploys an AI chatbot and calls it “transformation” is the Polymarket copycat pasting the prompt. The consultant who uses AI to write faster without redesigning the scoping and delivery process is running an unsophisticated implementation in a market where the windows are compressing.

The gap that matters isn’t “has AI” versus “doesn’t have AI.” That gap already closed. The gap that matters is “bolted AI onto existing process” versus “rebuilt the process around what AI makes possible.” That’s the new inefficiency, and it’s the one that separates the 7.6% who profit from the 92.4% who don’t.


## The rotation

This is the part of the story almost nobody is writing about, and it’s the most important.

The conventional framing treats AI disruption as a one-time event. Technology arrives, disruption happens, new equilibrium settles. That’s wrong. What’s actually happening is a continuous rotation of exploitable gaps, each opened by a new capability step and each compressing on a shorter timeline than the last.

We got a vivid illustration of this in late March.

On March 26, 2026, Fortune reported that a configuration error in Anthropic’s content management system had accidentally exposed draft materials about a model called Claude Mythos. Anthropic confirmed it exists, describing it as “a step change” in performance and “the most capable we’ve built to date.” Leaked drafts indicated the model dramatically outperforms current models in reasoning, coding, and cybersecurity, with one draft describing Mythos as “currently far ahead of any other AI model in cyber capabilities” and warning it “presages an upcoming wave of models that can exploit vulnerabilities in ways that far outpace the efforts of defenders.”

Markets didn’t wait for the model to ship. The software sector ETF fell nearly 3%. Bitcoin tumbled back to $66,000 from the edge of $70,000 (a large quarterly options expiry on Deribit the same day amplified the move, but the direction was set by the leak). Cybersecurity stocks dropped. Prices moved on the information that the model exists, before anyone outside a small early-access group had touched it.

What happens when it actually becomes available?

Every existing AI system gets repriced. The Polymarket bots running on current Claude become the slower horse. Someone running the same strategy on a model with meaningfully better reasoning has a temporary edge. That edge lasts until everyone upgrades, and then the window compresses again. The two-year compression from 12.3 seconds to 2.7 seconds? With a step-change model, that happens in weeks, because the playbook for “rebuild the bot on the new model” is now a known recipe.

But the compression isn’t the important part. The rotation is.

Mythos’s reported strength in cybersecurity creates an entirely new gap that didn’t exist before: the distance between organizations that have hardened their defenses against Mythos-class capabilities and those that don’t yet know the threat model has changed. Defensive security firms with early access will have a window — a real, monetizable edge — in protection calibrated to what this new model can do. That window will last until defensive tooling is widely deployed. Then it will close, and a new one will open somewhere else.

Mythos’s improvements in reasoning create new capability thresholds. Agentic workflows that couldn’t reliably handle complex multi-step tasks on current models might work on Mythos. That unlocks new automation, which creates new gaps between early adopters and everyone else, which compress as the capability becomes table stakes, and then the next model opens the next set of gaps.

And Anthropic isn’t alone. OpenAI reportedly finished pretraining its own next-generation model around the same time as the Mythos leak. Sam Altman told employees that “things are moving faster than many of us expected.” Both companies are racing toward IPOs later this year, which means the cadence of capability releases is about to accelerate. Google, Meta, and a half-dozen well-funded labs are on similar timelines.

Each release is a perturbation that opens new gaps across multiple domains simultaneously. Those gaps compress faster than the last set, because the adoption infrastructure improves every cycle. But the gaps never stop opening, because the capability frontier keeps advancing.

Think about the velocity here. In 2024, a major model release happened every few months and it took the market a year to fully absorb the implications. In 2025, releases were roughly quarterly and absorption compressed to months. In 2026, we’re watching markets reprice within hours of a leaked draft about a model that isn’t even publicly available. The cycle time between “new capability exists” and “the market has priced it in” is collapsing just as fast as the arbitrage windows on Polymarket. The meta-game is speeding up at the same rate as the games within it.

The old mental model — disruption, transition, equilibrium — is broken. There is no equilibrium. There is only the next rotation. The world doesn’t settle into a “post-AI” steady state. It enters a permanent condition of rolling disruption, where the specific inefficiencies that define your industry, your role, and your competitive position are reshuffled with every significant model release.

I want to be careful not to overstate the speed here. Some of these gaps will take years to close, and I could be wrong about which ones compress first. But the direction is clear, and the pace is accelerating in ways that are hard to dismiss even if you’re skeptical of the timeline.


## How to see what changes next

If you accept the frame, the world is built on slowly exploited inefficiencies, AI collapses them on the timescale of model releases, and each collapse opens new ones, then you have a practical lens for reading the future.

For any industry, any role, any business model, ask three questions:

**What inefficiency is this built on?** Every business model rests on a gap. Information asymmetry, execution difficulty, aggregation complexity, talent scarcity, regulatory friction, cognitive load. Name the gap. If you can’t name it, you can’t see it closing, and you won’t see it closing until someone else has already built the system that exploits it.

One example that might hit close to home: product management. The arbitrage gap it was built on? Engineers were considered too valuable to sit in meetings. Someone needed to absorb the organizational overhead so the engineers could code. That was the inefficiency. It funded an entire career path. And now, with smaller teams, better tooling, and AI handling much of the coordination and synthesis work that PMs used to own, that gap is being reshaped in real time.

**How fast can AI close it?** Some gaps are structural and will persist for years: regulatory moats, relationship-dependent trust, physical-world logistics, genuine creative taste, hard-won domain judgment. Others are purely informational or cognitive, and those are closing on the timescale of quarters, not decades. The law firm’s research billing gap is closing faster than the surgeon’s judgment gap. The agency’s production-cost gap is closing faster than the therapist’s rapport gap. The insurance company’s actuarial analysis gap is closing faster than the negotiator’s relationship gap. Be honest about which kind of gap you’re sitting on.

**What new gap does the closure create?** This is where the opportunity lives, and it’s the question almost nobody asks. When AI collapses the cost of producing content, the gap shifts to distribution and taste. Anyone can produce, but not everyone can reach an audience or curate quality. Code generation is the same story: the gap moves to system design and integration. Anyone can generate functions, but not everyone can architect systems that work reliably at scale. Legal research gets commoditized, and the gap lands on judgment and client trust. The research is free. The counsel is not. Data analysis follows the same pattern. Any model can run the regression, but knowing which regression matters requires domain expertise the model doesn’t have.

The new gap is always upstream of the old one: closer to judgment, taste, relationships, and system-level thinking, and further from production, execution, and information retrieval. This is the migration path. And it’s predictable. Once you see the pattern, you can trace where value is heading in your own industry before it gets there.

Take a concrete example. Right now, a junior financial analyst’s job is roughly 70% data gathering and formatting, 20% analysis, and 10% judgment calls. AI is collapsing the 70% toward zero. The naive conclusion is that you need fewer analysts. The better conclusion is that the analyst role migrates upstream: the same person, freed from the gathering and formatting, can now spend 60% of their time on analysis and 40% on judgment. The gap shifts from “who can compile the data?” to “who can interpret the data in context and make a defensible recommendation?” That’s a harder gap to close, because it requires domain knowledge, institutional context, and the kind of integrative reasoning that current models do adequately but not reliably. The analyst who recognizes this migration and develops the upstream skills (judgment, communication, contextual reasoning) is positioning for the new gap. The one who’s just using AI to compile data faster is riding the closing gap, not the opening one.

And the window to make that jump voluntarily is not going to be there forever. At some point, companies are going to decide to cut bait. You may not agree with their timeline, but the organizations I’m watching are already starting to differentiate between the people who are growing into upstream skills and the ones who are just using AI to do the old job faster. Pay attention to how fast your peers are developing, because if you’re not near the front of that curve, the decision may get made for you.

Trace that logic across any role, any industry, and you have a map.

If you can trace that chain, old gap closing, new gap opening, and where you need to be positioned to sit on the right side of the new one, you can work through this. If you can’t, you’re hoping the gap you’re sitting on closes slowly enough for you to figure it out. Hope is not a strategy, and “slowly” is no longer a safe assumption.


## How to make it work for your career

If you’re running an organization: your industry has a 12.3-second window right now. You can’t see it because the inefficiency is your current process. The competitor who will exploit it isn’t the one with the best AI tools. It’s the one who redesigned workflows and decision architecture to compound micro-advantages the way that bot compounded 6,615 trades. Each trade was small. The compounding was everything. If your AI strategy is “we’re running pilots,” you’re the slow side of someone else’s trade. Pilots don’t compound. Systems do.

If you’re building: the specific edges that work today will compress. The Polymarket latency strategy that produced a 98% win rate in late 2025 is already being squeezed, with most profits flowing to sub-100ms infrastructure now. Don’t chase the last window. Position for the next one. When Mythos ships, or when OpenAI’s next model ships, or Google’s, ask: what does this make newly possible that wasn’t possible yesterday? What gaps does it open? That’s where you build.

If you’re an individual contributor: the intelligence gap is the one most relevant to your career. Right now, the difference between what an AI-augmented professional can produce and what a non-augmented one can produce is enormous relative to what the market pays for either. Most salaries and freelance rates still reflect pre-AI productivity assumptions. If you can do in three hours what used to take thirty, you’re capturing surplus. The market is paying you for thirty hours of value whether it knows it or not. That’s a real window. But it’s closing. As more professionals adopt the same tools, the productivity expectation resets and compensation adjusts toward the new cost of production. The CNC operator who charged hand-milling rates while the machine did the work had a great run, until every shop had a CNC lathe and the rates collapsed.

The real question is what you’re doing with the surplus. Are you building skills, systems, and a reputation that compound, moving upstream toward judgment, taste, and system-level thinking? Or are you doing the same job faster and waiting for the market to reprice you? The surplus is a gift. It’s also a countdown.

On risk: remember the 92.4%. The survivorship bias in every AI success story is extreme. Democratized access to tools does not mean democratized advantage. Treat any specific AI-enabled edge as temporary by definition. The window will close, the strategy will be copied, and the returns will compress. What endures is the capability to find the next window: the pattern recognition, the systems thinking, the organizational readiness to move quickly when new capabilities ship. Don’t bet on a single edge holding. Bet on the rotation.


## The practice

There’s a question that keeps coming up in the Polymarket coverage: are these bots a temporary exploit, or the start of a permanent new meta?

Both. Neither. The bots are a temporary exploit. There will always be a new temporary exploit. That’s the new meta.

The permanent change isn’t any single gap closing or opening. It’s the cadence. And the fact that the cadence is accelerating. If you’re oriented around defending one position or exploiting one edge, you will be disrupted. If you’re oriented around the rotation itself, sensing new gaps, moving through them quickly, building the systems and skills to do it again and again, you will compound.

The world was built on slowly exploited inefficiencies. The “slowly” part is over. What replaces it isn’t efficiency. It’s something I’d call micro-turbulence — a faster cycle of inefficiency creation and destruction, where the gaps that define industries and careers are reshuffled with every capability step. Not a flat, efficient market. The opposite: a deeply turbulent one, but turbulent at a scale and speed that’s hard to see unless you know where to look. The Polymarket bot is just the clearest proof of concept. The Mythos leak is the preview of the next turn of the wheel.

The only losing move is to assume the current state is the steady state.

It never is now.

[![](https://substackcdn.com/image/fetch/$s_!XDbH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1d1c6b2d-7aef-4fec-90b0-b595aa7b1186_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!XDbH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1d1c6b2d-7aef-4fec-90b0-b595aa7b1186_1024x1024.png)
