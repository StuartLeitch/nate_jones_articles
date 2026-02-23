---
title: "What shipped"
author: "Nate Jones"
published: 2026-02-23
url: https://natesnewsletter.substack.com/p/gemini-31-pro-broke-every-benchmark
subtitle: "Watch now | Most AI coverage asks “which model is best?” This post asks the more useful question: best at what kind of hard — and what does that mean for which parts of your job are about to get ea..."
audience: everyone
scraped_at: 2026-02-23 12:00:18
---

Most people are about to open four new browser tabs and sign up for two more AI subscriptions. This post is an argument for understanding what you actually need before you make that move.

Gemini 3.1 Pro just shipped with the largest single-generation reasoning gain any frontier model has produced, doubling its predecessor’s score on novel logic problems in three months. But the more interesting story isn’t the benchmark. It’s what Google’s long game reveals about how you should think about every model release from here forward, and what it means for which parts of your work are about to get dramatically easier and which parts aren’t.

This post breaks down why “which AI should I use” is the wrong question, introduces a six-axis framework for understanding what actually makes your work hard, and explains why the skill that compounds fastest right now isn’t model fluency. It’s knowing whether the output in front of you is actually **good**. The companion guide walks you through how to apply the difficulty framework to one real task before you make any tool decisions. The prompt kit gives you four ready-to-use prompts: a 10-minute rapid audit that maps your work across all six axes, a deep-dive decomposition for your full role, an AI workflow optimizer that pressure-tests your current tools before recommending new ones, and a taste-builder that helps you develop sharper judgment for evaluating AI output in your specific domain.

Here’s what’s inside:

- **The strategic signal nobody’s discussing.** Why Google underpriced its best reasoning model on purpose — and what that tells you about where the AI landscape is actually headed.
- **The six axes of hard.** A framework for decomposing what actually makes your work difficult, and which axes AI is automating on which timeline.
- **The wrong question.** Why “which AI should I use” is finally obsolete, and what to ask instead.
- **The honest model comparison.** Where Gemini 3.1 Pro leads, where Opus 4.6 catches up, and where GPT-5.3-Codex wins — with the data to back it up.
- **The guide.** A walkthrough for applying the difficulty framework to one real task, pressure-testing your current tool before you go looking for new ones.
- **The prompt kit.** A rapid audit that maps your difficulty axes and evaluates your current AI usage in a single conversation, plus prompts for deep role decomposition, workflow optimization, and building domain-specific evaluation skills.

Let me show you why Google made that choice — and what it reveals about which parts of your work are actually at stake.


## LINKS: Grab the [Prompts](https://promptkit.natebjones.com/20260221_l1e_promptkit_1) + [Guide](https://promptkit.natebjones.com/20260221_l1e_guide_main)

These prompts and this guide exist because I've watched too many smart people respond to a new model announcement by opening four subscriptions and getting worse at all of them.

The guide walks you through one task — just one — and helps you decompose it across the six difficulty axes, figure out which axis is actually the bottleneck, and pressure-test whether your current tool can handle it before you go shopping for a new one. Most people discover the gap isn't the model. It's how they're framing the ask.

The prompt kit operationalizes the same framework at scale: a rapid audit maps your work across all six axes in a single conversation, then deeper prompts help you decompose your full role, optimize your current AI workflow, and build the domain-specific judgment to tell whether what the model gave you is actually good. If you can't fill in the blanks, that's the point — it means the landscape has moved faster than your mental model of it.


# What shipped

Google just shipped what might be the smartest AI model available at scale. It doubled the reasoning score of the model it replaced three months ago. It leads on the majority of benchmarks in Google’s published evaluation suite — by one independent count, 13 of 16. It costs two dollars per million input tokens — less than half what Anthropic charges for Opus 4.6, which itself dropped from fifteen to five dollars when it launched on February 5th.

And Google doesn’t need you to use it.

That’s not a weird flex. It might be the most important strategic signal in AI right now, and almost nobody is talking about it. The coverage of Gemini 3.1 Pro has been wall-to-wall benchmark comparisons and pricing tables. What’s missing is the question underneath: why would the richest company in tech — a company committing nearly $200 billion to AI infrastructure this year alone — build the most powerful reasoning engine on the market, price it at the floor, and be perfectly comfortable if you keep using Claude or ChatGPT for your daily work?

The answer reshapes how you should think about every model release from here forward. It changes how you evaluate your own skills. And it explains why most of the conversation about “which AI should I use” is asking the wrong question entirely.

Two weeks ago I wrote about Opus 4.6 and sixteen AI agents building a C compiler. That piece was about a new kind of labor — agents coordinating in teams, managing engineering orgs, doing weeks of sustained autonomous work. This piece is about something different. This piece is about why the company with the deepest pockets and the widest distribution in the history of computing is playing a fundamentally different game from everyone else — and what that means for how you evaluate AI models, choose your tools, and understand which of your problems are about to get dramatically easier to solve and which ones aren’t.


## The Number That Matters

77.1% on ARC-AGI-2.

That benchmark tests whether a model can solve logic problems it has never seen before — not pattern matching from training data, not retrieval from memorized examples, but genuine novel reasoning. Can the model look at a problem it’s never encountered and figure it out from first principles?

Gemini 3 Pro, which shipped in November, scored 31.1%. Three months later, 3.1 Pro more than doubled it. That 46-percentage-point jump is the largest single-generation reasoning gain any frontier model family has produced. Opus 4.6 scored 68.8% on the same benchmark — strong, but more than eight points behind. GPT-5.2 scored lower than both.

The rest of the scorecard tells the same story. 94.3% on GPQA Diamond, a graduate-level science benchmark — the highest score ever recorded by any model. 2,887 Elo on LiveCodeBench Pro, significantly ahead of both GPT-5.2 and the previous Gemini. 59% on SciCode, leading all models on scientific programming tasks. 69.2% on MCP Atlas, the tool-coordination benchmark. A million-token context window with 65,000 tokens of output. All at the same price as Gemini 3 Pro — two dollars per million input tokens, twelve per million output.

These numbers are real. But the benchmark isn’t the point. The point is what Google chose to optimize for. Anthropic built Opus 4.6 for agentic work — sustained autonomous coding, tool calling in loops, agent teams coordinating across codebases for weeks at a time. OpenAI built Codex 5.3 for specialized coding pipelines with self-bootstrapping sandboxes and thousand-token-per-second throughput. Google built Gemini 3.1 Pro to think harder.

Not to code longer or manage more agents — but to reason more deeply about problems it has never seen.

That design choice tells you everything about who Google thinks it is.


## Why Google treats intelligence as the product

Demis Hassabis has been saying the same sentence for fifteen years. “Step one, solve intelligence. Step two, use it to solve everything else.”

He said it when DeepMind was a London startup nobody had heard of. He said it after AlphaGo beat Lee Sedol. He said it at Davos last month. He said it on the Fortune podcast last week, where he predicted artificial general intelligence within a decade and described a future where AI helps humanity “travel the stars and explore the galaxy.” He said it on 60 Minutes, where he talked about curing most diseases within ten years. The sentence hasn’t changed because the mission hasn’t changed.

This is not how anyone else in the AI industry talks. Sam Altman talks about products, partnerships, distribution, the race to a billion users. When OpenAI put ads in ChatGPT last year and users revolted, Altman declared a “code red” and pulled them back — less because ads conflict with a research mission than because they were losing users to Gemini and couldn’t afford the distraction. Hassabis, when asked about the ChatGPT ads at Davos, said he was “surprised” OpenAI moved so fast on advertising. His actual word was surprised. Google’s VP of Global Ads publicly stated there are no ads in Gemini and no plans to add them. The subtext from Hassabis was unmistakable: we’re not thinking about monetizing our AI chatbot. We’re thinking about intelligence.

This is not because Google is above commercial concerns. Google runs the most profitable advertising business in human history. They generated over $73 billion in free cash flow last year from Search, YouTube, and Cloud — and they’re planning to spend more than double that on AI infrastructure. Their 2026 capital expenditure guidance, announced February 4th, is $175 to $185 billion. That’s roughly half a billion dollars a day on compute. They can afford to let Gemini be a research vehicle because their economic engine has nothing to do with whether you personally prefer Claude or ChatGPT for your daily workflow.

Everyone else in AI is trying to figure out how to monetize models. Google is trying to figure out how to build intelligence. The money handles itself.


## Google owns every layer

Here is what Google has that nobody else does: every layer.

They design their own silicon. The Ironwood TPU — seventh generation, announced earlier this year — delivers more than four times the per-chip performance of the previous generation at twice the energy efficiency. It can link up to 9,216 chips in a single pod. Anthropic just signed a deal to use up to one million TPUs under a multiyear arrangement valued in the tens of billions. Meta is reportedly negotiating a similar commitment. When your competitors train their frontier models on your hardware, you have built something beyond a moat. You’ve built the geology.

They train their own models on that silicon. They deploy those models through their own cloud infrastructure — Google Cloud, which by one industry estimate hosts workloads from nine of the ten largest AI research labs. They distribute them to more than 750 million monthly active Gemini users — up from 650 million just one quarter earlier — plus billions more through Search, Android, YouTube, and Chrome. And they fund the fundamental research through DeepMind, which won a Nobel Prize in Chemistry eighteen months ago for AlphaFold — a system that predicted the structure of virtually every known protein, a problem biologists had been working on for fifty years.

This vertical integration — from transistor design to protein folding — is not an accident. It’s the architecture of a company that believes intelligence is a problem in computer science, that the problem is solvable, and that solving it requires controlling the entire stack from physics up through software. Google’s Jeff Dean said they’re working to shrink TPU design cycles from two years down to six to nine months by using AI in the chip design process itself. They’re using intelligence to build the hardware that runs the intelligence. The flywheel is self-reinforcing.

Nobody else has this. Microsoft has Azure and a partnership with OpenAI, but they don’t make chips and their consumer distribution in AI is fragmented — Copilot has been criticized for feeling disjointed across Office products. Amazon has AWS and Trainium, but their models trail the frontier. Meta has research talent and social distribution, but no cloud business and no chip stack. Anthropic has arguably the best product for agentic work right now, but they run on other people’s hardware — Google’s TPUs and Amazon’s infrastructure — and they need every customer they can get to justify their valuation.

Google is the only company that could lose the “model race” entirely — every developer and every enterprise customer choosing Claude or ChatGPT for every task — and still be fine. Because the models are not the business. The models are experiments in intelligence, funded by the largest cash-generating machine in technology, running on proprietary silicon, feeding results back into products used by half the planet.

That changes how you should interpret everything they ship.


## Where 3.1 Pro wins and where it doesn’t

Gemini 3.1 Pro is not a coding agent. It’s not an agent manager. It’s not trying to autonomously close issues across a fifty-person engineering org the way Opus 4.6 did at Rakuten. If that’s what you need, Opus is better at it right now, and Google knows that.

What 3.1 Pro is: the strongest pure reasoner available at scale, at a price point that makes it viable for any problem where reasoning depth matters more than tool orchestration.

At two dollars per million input tokens and twelve per million output, it’s roughly 2.5 times cheaper than Opus 4.6 on input and about half the cost on output — and that’s after Anthropic already cut Opus pricing by two-thirds when they launched 4.6 on February 5th. For a workload processing a billion tokens a month, that’s the difference between a $5,000 Opus bill and a $2,000 Gemini bill. With context caching enabled, Gemini’s costs can drop further still — Google lists cached input reads at significantly reduced rates, though the exact discount varies by model tier. JetBrains’ director of AI called it “stronger, faster, and more efficient.” Artificial Analysis currently ranks it as the top model on their Intelligence Index at roughly half the cost of its nearest frontier peers.

The model also ships with configurable thinking levels — from minimal through high — so you can dial reasoning depth up or down per request. Simple classification or summarization? Minimal thinking, fast and cheap. Novel scientific problem requiring multi-step deduction? High thinking, let it work. This is cost engineering for reasoning at a granularity nobody else offers, and it matters because it means you don’t pay frontier prices for routine tasks.

But here’s the honest comparison, and it matters. When you give these models tools — web search, code execution, database access, file systems — and measure their performance on complex real-world tasks that require using those tools in combination, Opus 4.6 catches up and often pulls ahead. On Humanity’s Last Exam with search and code tools, Opus scores 53.1% versus Gemini’s 51.4%. On GDPval-AA, which measures expert-level office and financial tasks, Opus leads by 289 Elo points — a massive gap. On the Arena coding leaderboard and expert human preference rankings, Claude models consistently win. On SWE-Bench Verified — real-world software engineering — Opus edges Gemini 80.8% to 80.6%, a razor-thin margin but a symbolic one. And on Terminal-Bench 2.0, the benchmark for real-world agentic coding, GPT-5.3-Codex leads both of them at 77.3%.

The pattern is unambiguous: Gemini 3.1 Pro is the strongest naked reasoner. Opus 4.6 is the strongest equipped reasoner — the model that’s best at combining intelligence with the ability to use tools, call APIs, read files, write code, and sustain that work over hours and days. GPT-5.3-Codex is the strongest specialist coder. If intelligence is the engine, tools are the drivetrain. Google built the better engine. Anthropic built the better car. OpenAI built the better racing transmission.

For any individual task, the question isn’t “which model is smartest.” The question is whether the task is bottlenecked by raw thinking or by the ability to act on that thinking across tools and time. And that question turns out to be far more interesting than any benchmark comparison.


## What “hard” looks like at the frontier

To understand what Gemini 3.1 Pro is built for, look at what Google did the week before they shipped it.

On February 12th, they released the upgraded Gemini 3 Deep Think — a specialized reasoning mode that sits above 3.1 Pro on the intelligence curve. Deep Think collaborated with human researchers to solve 18 previously unsolved problems across mathematics, physics, computer science, and economics. These weren’t incremental improvements or benchmark tricks — they were original research contributions.

A conjecture in online submodular optimization had stood since 2015. It proposed a seemingly obvious rule: in a data stream, copying an arriving item is always less valuable than moving the original. Mathematicians had spent a decade trying to prove it. Gemini Deep Think engineered a precise three-item combinatorial counterexample and proved the conjecture false. In a single run. But that wasn’t even the most interesting result. On the Max-Cut problem — a classic network optimization challenge where progress had stalled — Gemini pulled in the Kirszbraun Theorem and measure theory from continuous mathematics to solve a discrete algorithmic puzzle. Human algorithm researchers wouldn’t typically reach into geometric functional analysis for a graph theory problem. The model crossed disciplinary boundaries that human specialists rarely cross, because it doesn’t have disciplinary boundaries.

In physics, it tackled gravitational radiation calculations from cosmic strings — a problem plagued by integrals containing singularities — and found a solution using Gegenbauer polynomials that collapsed an infinite series into a closed-form finite sum. It identified six different solution approaches. It caught a critical error in a cryptography paper that had passed through human peer review unnoticed.

And two days before 3.1 Pro shipped, Isomorphic Labs — DeepMind’s drug discovery spinoff — published results from their AI Drug Design Engine, IsoDDE. The system more than doubled AlphaFold 3’s accuracy on the hardest protein-ligand prediction tasks and outperformed gold-standard physics-based methods like FEP+ at a fraction of the cost and time. It can identify drug binding pockets on proteins using nothing but the amino acid sequence as input — compressing what used to take months of crystallography experiments into seconds. It predicted the location of a novel cryptic site on cereblon — a drug target — that the Dippon et al. team had only just published in 2026 after more than fifteen years of experimental work. Isomorphic Labs has active drug programs with Eli Lilly and Novartis worth over $3 billion in potential milestones, with first AI-designed candidates expected to enter Phase I clinical trials this year.

Protein folding. Mathematical conjecture-breaking. Gravitational radiation. Cryptographic error detection. Crystal growth optimization. These are pure reasoning problems at the extreme end of the difficulty spectrum. They share specific characteristics: the inputs are well-defined (a protein sequence, a mathematical statement, a set of physical equations), the problem can be stated precisely, and the solution requires sustained chains of logical deduction that a human mind can verify but often cannot generate without years of specialized training.

This is the domain where Google’s investment in intelligence-as-a-problem pays off. This is what Hassabis means by “solve intelligence, then use it to solve everything else.” The “everything else” starts with science. It starts with the problems that have the highest ratio of reasoning difficulty to ambiguity — where the question is clear but the answer requires genuine intellectual horsepower to reach.

And it’s why I think the most important question for anyone reading about Gemini 3.1 Pro isn’t “is it better than Opus” but rather: what percentage of your actual work is bottlenecked by this kind of thinking?


## The Problem Taxonomy Nobody Has Built

Here’s where the analysis gets personal and honest. Because “hard” is not one thing. We’ve been treating it as one thing — the benchmarks treat it as one thing, the model marketing treats it as one thing, the LinkedIn discourse treats it as one thing — and the model landscape is now differentiated enough to force us to decompose it.

Think about the problems you face at work. Some are hard because they require deep reasoning — analyzing a complex contract for the clause that creates downstream liability across three jurisdictions, working through a multi-step financial model to find the sensitivity that changes the investment decision, diagnosing why a distributed system fails under a specific load pattern that only appears at scale. These are problems where you need to hold multiple variables in your head, follow a chain of logic through branches and dependencies, and arrive at a conclusion that isn’t obvious from the surface.

But most problems in business aren’t actually hard on a reasoning axis. They’re hard on other axes entirely.

Effort problems. Not intellectually difficult, just large. Auditing three thousand vendor contracts for compliance changes. Migrating a legacy codebase with two million lines of COBOL. Reviewing every customer interaction from last quarter to identify churn signals. The thinking at each step is straightforward — any competent person could do any individual piece. The challenge is sustaining attention and thoroughness across a massive surface area without dropping things. These are the problems agentic AI was built for. Opus 4.6 running for seven hours on Rakuten’s codebase is solving an effort problem. The sixteen agents building a C compiler over two weeks are solving an effort problem. The thinking per step isn’t extraordinary. The endurance is. And that’s not what Gemini 3.1 Pro is optimized for.

Coordination problems. Getting six teams aligned on a shared architecture decision when each team has different priorities and different technical contexts. Routing work across dependencies so that the backend team doesn’t block the frontend team doesn’t block the QA team. Managing information flow so the right people know the right things at the right time — and nobody wastes three days building something that was already decided against in a meeting they weren’t invited to. Rakuten’s deployment of Opus 4.6, where the model autonomously closed 13 issues and correctly routed 12 more across a 50-person organization and six repositories, is solving a coordination problem. It understood not just the code but the org chart — which team owns which repo, who has context on what. Pure reasoning doesn’t help here. Organizational awareness does. And organizational awareness requires tool access, state management, and sustained context across interactions — exactly the capabilities where Opus 4.6 leads.

Emotional intelligence problems. Delivering feedback to a direct report who’s been underperforming but is going through a divorce. Navigating a negotiation where the other party’s stated concern — price — isn’t their actual concern, which is control. Reading a boardroom and knowing that the CFO’s silence means opposition, not agreement. Managing a team through a reorg where half the people are afraid for their jobs and the other half are angling for promotions. Calibrating tone, timing, and transparency in situations where the right thing to say depends on dynamics no model can observe. No current model solves this well. No model even attempts it with reliability. And this is a massive percentage of what makes management and leadership genuinely hard.

Judgment and willpower problems. Deciding to kill a project your team spent six months building because the market signal shifted. Saying no to a lucrative client whose values don’t align with your company’s. Choosing the strategically correct but politically dangerous path when the data supports it but the executive team doesn’t want to hear it. Making the unpopular call. Accepting the career risk. These aren’t reasoning problems — any competent analyst could lay out the logic. They’re courage problems — identity problems, really. And they’re almost entirely unsolvable by AI because the bottleneck isn’t computing the right answer. It’s having the nerve to act on it.

Domain expertise problems. A senior engineer doesn’t debug faster because they reason better than a junior. They debug faster because they’ve seen that exact stack trace before, they know the library’s undocumented quirks, they remember the production incident from 2019 that had the same root cause. A veteran M&A attorney doesn’t evaluate a deal better because they’re smarter. They evaluate it better because they’ve closed three hundred deals and they’ve internalized which representations and warranties actually get litigated and which ones are boilerplate nobody ever enforces. This is experience and pattern recognition — knowledge accumulated through years of repetition — not novel reasoning. Models are getting better at simulating domain expertise through training data, but the gap between “has read about it” and “has lived it” is still real, particularly in domains with thin published literature.

Ambiguity problems. Deciding what to build when the market signal is contradictory. Defining strategy when three plausible interpretations of customer data exist and each one leads to a different product roadmap. Figuring out what the customer actually wants when they can’t articulate it themselves — they say they want “better reporting” but they actually want their boss to stop questioning their numbers. The hard part isn’t computing an answer. The hard part is figuring out what the question is. This is the domain of product sense, strategic intuition, and the ability to hold multiple incomplete mental models in tension until one resolves. Models can help explore the options. They can’t resolve the ambiguity.

Now — and this is the critical move — look at those six axes and ask: which ones does a dramatic improvement in pure reasoning actually help?

Reasoning helps reasoning problems. Obviously. The Gemini Deep Think results — disproving conjectures, solving open research questions, predicting drug binding sites from amino acid sequences — are pure wins for the reasoning axis. These are enormously valuable problems. A single insight in drug discovery can be worth billions. A breakthrough in materials science can reshape an industry. A novel proof can unlock an entire branch of mathematics. The problems on the reasoning axis are some of the highest-value problems humans work on.

But look at how they cluster. Drug discovery. Materials science. Quantitative finance. Formal verification. Theoretical physics. Climate modeling. Genomics. Cryptography. These are largely scientific and mathematical domains — which is exactly where AlphaFold, IsoDDE, and Deep Think’s eighteen solved research problems all live. This is not a coincidence. This is Google telling you, through their research investments, where pure reasoning has the highest leverage.

Now, to be fair: pure reasoning problems do exist in mainstream business. They’re just rarer and more specialized than people assume. Multi-jurisdiction tax optimization is a genuine reasoning problem — the tax codes across twelve countries are known inputs, the question is well-defined, but the interaction effects create a combinatorial space that’s genuinely hard to reason through. Complex derivatives pricing is a reasoning problem. So is novel regulatory compliance — not “read these three thousand contracts” (that’s an effort problem), but “does this new financial instrument trigger reporting obligations simultaneously under Dodd-Frank, MiFID II, Basel III, and the Hong Kong SFC’s updated guidelines?” That’s multi-step logical deduction across interacting rule systems, and it’s the kind of thing Gemini 3.1 Pro on High thinking would handle well. Structural fraud detection — not ML pattern classification, but tracing a chain of seven transactions across four entities and reasoning about whether the structure implies layered money movement — is a reasoning problem.

But notice the pattern: these business reasoning problems cluster in specialized quantitative domains that look a lot more like applied science than like typical knowledge work. And critically, the people who do this work spend most of their time on everything except the reasoning. The tax attorney spends maybe ten percent of her week on the genuine multi-jurisdiction interaction puzzle and ninety percent on client management, document gathering, coordination with local counsel, and navigating ambiguity about what the client actually wants to achieve. The supply chain director’s hardest problem isn’t the multi-constraint optimization math — it’s getting three VPs to agree on demand forecasts before the math can even start. The reasoning slice is real and high-value, but it’s embedded in a much larger mass of effort, coordination, and ambiguity work. Which means a model optimized for pure reasoning helps with the most intellectually demanding ten percent of these roles — but a model optimized for tools and sustained work helps with the other ninety.

For most knowledge workers on most days, the problems they face are hard on effort, coordination, emotional intelligence, ambiguity, and domain expertise. The pure reasoning component — the part that requires genuinely novel, multi-step logical deduction from first principles — is a relatively narrow slice. I don’t have a precise number and I’m skeptical of anyone who claims to. But I do know this: when I look at my own consulting work, and when I look at the work my Fortune 500 clients describe, the moments where someone says “I need to think harder about this” are vastly outnumbered by the moments where someone says “I need to coordinate twenty people on this” or “I need to get through all of this” or “I need to figure out what we’re actually trying to do here.”

That’s why I think Opus 4.6 will get more daily usage, and why I think Google can live with that. Google would rather you used Gemini — they’re not indifferent, they have a Cloud business to grow and an ecosystem to feed. But their AI research program doesn’t depend on winning your daily workflow. They’re competing for the periodic moment when a problem shows up that requires deep, novel reasoning — and in that moment, they want to be the best and the cheapest. They’re also positioning for the scientific frontier, where pure reasoning problems are dense, where the payoffs are measured in Nobel Prizes and trillion-dollar industries, and where Google’s vertical stack — from TPU silicon to DeepMind research to Isomorphic Labs drug programs — gives them a pipeline nobody else can match.

The rest of the time, you’ll probably use Claude or ChatGPT. And Google will sell the TPUs those models run on.


## Build the map before someone builds it for you

Here’s where this gets personal. Three things.

First: stop looking at benchmarks and start mapping traction in your domain. The ARC-AGI-2 scores matter to researchers. They do not tell you which model will best help you prepare a board presentation, debug a React component, analyze a competitive landscape, or draft a regulatory filing. What matters is which model handles the specific tasks in your specific workflow most reliably, and the only way to know that is to test them yourself.

Are you the smartest person in your field about which AI model handles which task type? You should be. Because the gap between “I use ChatGPT for everything” and “I route financial modeling to Gemini on High thinking, coding to Claude Code, quick research to Gemini Flash, and deep document analysis to Opus with its million-token context” — that gap is the difference between commodity usage and genuine leverage. The models have differentiated enough that model routing is now a skill, and nobody is going to build that routing map for your domain except you. A cardiovascular surgeon routes differently from a supply chain analyst routes differently from a creative director. The task-to-model mapping is domain-specific, and it’s the kind of practical knowledge that compounds every week the models improve.

Second: start disentangling the dimensions of difficulty in your work. What in your world is genuinely bottlenecked by reasoning? By effort? By coordination? By emotional intelligence? By domain expertise? By ambiguity? By something else I haven’t named — political risk, regulatory uncertainty, execution speed, talent scarcity?

This decomposition matters because each dimension is getting automated on a different timeline, at a different rate, by different tools. Pure reasoning problems are getting dramatically easier to solve right now — that’s what the ARC-AGI-2 score doubling in three months means. A decade-old mathematical conjecture fell in a single model run. Drug binding pockets that took fifteen years to discover experimentally are being predicted from sequence data in seconds. The reasoning frontier is moving at a pace that should make anyone whose value proposition is “I think carefully about complex problems” sit up and pay serious attention.

Effort problems are getting automated by agentic models that sustain work for hours and days — that’s Opus 4.6 and Codex 5.3. Coordination problems are starting to yield to agent teams and tool-augmented orchestration. Domain expertise is slowly being absorbed into training data, though the gap between “has read about it” and “has done it” remains real.

Emotional intelligence, judgment, ambiguity resolution, and courage are barely touched. They will be the last dimensions to yield, if they yield at all. And this is where the map matters: if you know that most of your value comes from axes that AI isn’t automating, you can sleep soundly. If you discover that most of your value comes from the reasoning axis or the effort axis, you need to move — not panic, but move, deliberately, toward the dimensions where human judgment still dominates.

Without this map, you can’t predict which parts of your value are durable and which are dissolving. Someone will map this — either you, or someone evaluating whether your role justifies its cost.

Third: build the taste to evaluate AI output in your domain. Every model improvement makes this more urgent, not less. When Gemini can reason at 77% on novel logic problems, when Opus can sustain autonomous coding for weeks, when Deep Think can disprove mathematical conjectures and catch errors that passed peer review — the question has shifted from “can AI do it” to something harder: “can you tell whether what AI produced is actually good?”

Lisa Carbone, a mathematician at Rutgers, used Gemini Deep Think to review a highly technical mathematics paper and it caught a subtle logical flaw that had passed through human peer review. That’s impressive for the model. But it took Carbone’s expertise to validate the finding and her authority to act on it — neither step was sufficient alone.

That judgment — the ability to look at a financial model and know the assumptions are wrong, to read a legal analysis and spot the missing precedent, to evaluate a codebase architecture and feel that something’s off before you can articulate why — is the skill that compounds. Every other skill is getting cheaper. That one is getting more valuable, precisely because the models are getting better at generating plausible-looking output that requires deep expertise to verify.

I’m building guides that go deeper on model routing by domain and the problem-axis mapping. But the work of applying them to your world is yours.


## Google’s Quiet Long Game

There’s a version of the AI story that’s about speed and market share — who ships fastest, who wins the enterprise, who reaches a billion users. That’s the story OpenAI and Anthropic are living. It’s an important story. The products they’re building are changing how people work this week.

But there’s another version. The version where a company backed by tens of billions in annual free cash flow and committed to spending nearly $200 billion on AI infrastructure this year, running on proprietary silicon it designs and manufactures, employing the team that won a Nobel Prize for protein structure prediction, operating under a CEO who has been saying “solve intelligence” since before anyone took AI seriously — where that company isn’t trying to win the product race because the product race is a sideshow. The main event is intelligence itself. And if you solve intelligence, the products take care of themselves.

Gemini 3.1 Pro is a marker on that road. It’s the purest reasoning model available at scale, at the lowest price, from the only company with the infrastructure to keep pushing the reasoning frontier indefinitely. It won’t be the most-used model this month. Claude will handle more daily tasks. ChatGPT will have more active users. Google would prefer otherwise — but they can afford the patience, because they’re building the thing underneath the thing. The engine that disproves conjectures, discovers drug binding sites, catches errors in peer-reviewed cryptography papers, and pushes the boundary of what “thinking” means when a machine does it.

One week before 3.1 Pro shipped, DeepMind’s Aletheia agent evaluated 700 open problems from the Erdős conjecture database and found 63 technically correct solutions, fully resolving 4 previously open questions. One week before that, IsoDDE doubled AlphaFold 3’s accuracy on the hardest drug discovery tasks and outperformed gold-standard physics-based methods at a fraction of the cost. These are research results, not product announcements. And they’re coming faster than anyone — including, apparently, the researchers — expected.

For you, the practical takeaway isn’t which model to use. It’s that the model landscape has differentiated clearly enough that “which AI should I use” is finally the wrong question. The right question is “which AI should I use for which problem, and do I even know what kind of problem I’m solving?” Is it a reasoning problem? An effort problem? A coordination problem? An ambiguity problem? Each one has a different best tool, a different automation timeline, and a different implication for your career.

Get specific about that. Build the map. Because the tools are now specific enough to reward specificity, and the people who route well will outperform the people who use one model for everything by a margin that widens every quarter.

The fog is still thick. But at least now we can see the shapes in it.

[![](https://substackcdn.com/image/fetch/$s_!xkM_!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F09db8b0c-b521-41eb-9646-1f2ea07a3d4f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!xkM_!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F09db8b0c-b521-41eb-9646-1f2ea07a3d4f_1024x1024.png)
