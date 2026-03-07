---
title: "GPT-5.4 beat human performance on desktop tasks and missed a question a child would get right. Both are true. Here's what to do with that."
author: "Nate Jones"
published: 2026-03-07
url: https://natesnewsletter.substack.com/p/i-tested-gpt-54-against-claude-and
subtitle: "Watch now | I ran evals across all current frontier models so you don't have to (and yes, it was very fun)."
audience: everyone
scraped_at: 2026-03-07 12:00:16
---

I asked ChatGPT 5.4 a question today. A simple one: “I need to wash my car. The carwash is 100 meters away. Should I walk or drive?”

ChatGPT 5.4, the model OpenAI just positioned as its most capable system for professional work, thought for a couple of seconds. Then it wrote a full essay. Walk, it said. At 100 meters, driving is more hassle than it’s worth. It listed exceptions: icy conditions, mobility issues, carrying heavy items. It closed with a nuanced distinction between “driving there” as a transportation decision versus “repositioning the car.” Thorough. Well-structured. Completely wrong.

I asked Claude the same question. Claude thought for a moment and wrote one sentence: “Drive. You need the car at the carwash.”

Gemini got it right too. Gemini 3.1 Pro called it a trick question and noted that unless you have an incredibly long extension cord and a hose, you have to drive. Every frontier model got this right except GPT-5.4 Thinking. The model that OpenAI says is ready to run your professional workflows wrote a careful, confident, wrong answer to a question a child would get right.

And that, in one shot, is the story of GPT-5.4.

Except it isn’t. It’s not that simple. Because GPT-5.4 is better than Opus 4.6 at some things (genuinely, measurably better) and I’m not going to take a silly example and milk it for outrage. I am going to point out that if you position your model as the best in the world, it has to survive ordinary real-world test cases. It cannot be behind frontier models on questions that aren’t even trick questions. I’m going to show you the full picture, because the full picture is more interesting than any single test.

I ran blind evaluations. Not vibes. Not “I tried it for an afternoon.” Six structured evals, independent judging, outputs labeled by number so the judge never knew which model produced what. I also had an AI-fluent person aside from me verify the results. We tested GPT-5.4 against Claude Opus 4.6 and Gemini 3.1 on real tasks, the kind of work you’d hand a model on a Tuesday afternoon and expect to use Thursday morning.

The short version: GPT-5.4 is not the best model. It is not the worst model. It is the most interesting model I’ve tested — and interesting for reasons that have almost nothing to do with the benchmarks OpenAI is promoting.

**Here’s what’s inside:**

- **The toggle that splits one model into two products.** The single most important finding in the eval suite, and the thing most users will never think about.
- **Where 5.4 genuinely wins.** Quantitative modeling, file processing, and competitive self-knowledge, with the eval data to back it up.
- **Where it falls apart, and what that reveals about intelligence.** Writing quality, product judgment, and a subtle failure mode I’m calling the pipeline problem.
- **The Steinberger signal.** Why the most important AI hire of the year explains this entire release.
- **What OpenAI is actually building.** It isn’t a chatbot. It’s agentic infrastructure, and the benchmarks they chose to promote tell you exactly that.

The models are converging on capability and diverging on philosophy. Pay less attention to who won the benchmark and more attention to what the benchmark was measuring.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260306_bol_promptkit_substack)

Three prompts below the fold, built directly from these eval findings. The first interviews you about how you actually use AI today and delivers a personalized briefing on what GPT-5.4 changes for your work — and what it doesn’t. The second is a weekly model router: paste in your tasks, get back a table telling you which model and mode to use for each one, with a flag for anywhere the thinking toggle is critical. The third is a pipeline problem detector — for any workflow where your AI output looks thorough but isn’t actually usable, it diagnoses the pattern and rewrites your prompt to fix it. All three work in ChatGPT, Claude, or Gemini.

If you want the raw numbers — every score, every judge note, the full obstacle-by-obstacle breakdown from the schema migration eval, you can find it at the link below.

LINK: **[Frontier Model Eval Tracker](https://promptkit.natebjones.com/20260306_bol_guide_main)**


## The toggle nobody talks about

The single most important finding in my entire eval suite is not about which model is best. It is about GPT-5.4’s thinking mode — and the chasm between thinking and auto.

In thinking mode, GPT-5.4 is a genuine frontier competitor. It retrieves real sources, reasons carefully across knowledge boundaries, earns its confidence tags, and competes with or beats Opus on factual accuracy. In the schema migration eval (which I’ll get to), it discovered file formats, recovered corrupted JSON, built a 4,050-line migration pipeline, and processed images that Claude couldn’t touch. When thinking mode is engaged, this is a serious model doing serious work.

In auto mode, the default experience for the vast majority of ChatGPT users, it collapses. On the epistemic calibration eval, the accuracy delta between thinking and auto was 2.0 to 2.5 points on a 5-point scale. That is not a graceful degradation. That is a different product.

I want to be specific about what broke. On identical questions, auto mode named the 2024 Nobel Prize winners for a 2025 question. It tagged that answer MEDIUM confidence instead of catching the error. It cited a matrix multiplication bound from 2020, two iterations behind current research. It estimated Databricks revenue at $1.6 to $2 billion when the actual ARR was north of $4.8 billion at last public disclosure, off by a factor of three. It never used a LOW confidence tag anywhere. Its own self-reflection noted the Nobel answer “could be misremembered” but didn’t downgrade the confidence rating. The model saw the problem, noted the problem, and then did nothing about the problem.

I’m concerned about this, and I want to be honest about why. A billion people use ChatGPT. Most of them will never deliberately select thinking mode. They’ll use whatever the interface gives them, which is auto. And what auto gives them is a measurably weaker system that looks identical from the outside. There is no warning label, no “you are currently in the less accurate mode” banner. The interface is the same, the confidence is the same, but the answers are worse.

If you are an AI enthusiast, this means you have to think about that toggle every single time. And it gets worse, because you’re going to have to teach everyone in your office. “Hey, 5.4 does a great job in thinking mode on this spreadsheet. It built this amazing statistical model. But if it’s not on thinking mode, it’s going to be terrible.” That is something you should not have to say. The auto switcher should be tuned to accurately invoke thinking where thinking tasks require it. I did not see that happening enough, and my results show it.

If your organization is evaluating GPT-5.4, the thinking toggle is the first thing your team needs to understand. Not the benchmarks, not the context window. The toggle.


## Where 5.4 genuinely wins

I want to give credit where it’s due, because there are places where GPT-5.4 is doing things no other model can match right now. Three clear strengths showed up under blind testing, and I think all three are worth understanding, not just for what they tell you about this model, but for what they tell you about where the capability frontier is moving.

**It builds better quantitative models than anything else out there.** I gave each model the same prompt: build a spreadsheet projecting the Seattle Seahawks’ 2026 season win probabilities using all 32 teams’ 2025 results and Seattle’s known opponents. [GPT-5.4 produced a six-tab workbook](https://docs.google.com/spreadsheets/d/1UlFhlahOLXtA0PYBZnBVOnhUiV58HJ8m/edit?usp=sharing&ouid=118371784362828784038&rtpof=true&sd=true) with Pythagorean win expectation, an Elo-like rating system with offseason retention decay, a Poisson-binomial season distribution — I don’t know what that is either — and a methodology tab that honestly catalogued its own assumptions, shortcuts, and limitations. [Claude produced a cleaner, better-formatted three-tab workbook](https://docs.google.com/spreadsheets/d/1j3Ci6YWXzNPzNYqDlytOvpAsI2hY0n1j/edit?usp=sharing&ouid=118371784362828784038&rtpof=true&sd=true) using a simpler Bradley-Terry model. The formatting was better. The statistical rigor was not close.

And then GPT-5.4 did something I want to call out specifically: it wrote an unprompted self-critique of its own work that was more honest than most consulting deliverables I’ve seen, identifying exactly where the model oversimplifies and what it would improve next. That self-awareness is worth paying attention to. A model that can tell you precisely why its own output is insufficient is, in many practical settings, more useful than the model that produces a prettier artifact and moves on without mentioning the gaps.

**It processes more file types with less friction.** I ran what I’ve been calling the eval from hell — a schema migration from a digital shoebox of business data. Imagine you took every receipt, every expense report, every database export, every scanned handwritten note from a small business over two years, threw them all into a pile, and said: make sense of this. GPT-5.4 discovered and processed 461 of 465 files, for 99.1% coverage. It handled CSVs, Excel files, JSON, PDFs, VCF contacts, handwritten receipt images via OCR, a corrupted JSON backup, and a monster multi-tab everything-spreadsheet. That is a remarkable reach.

Claude discovered all the files but couldn’t parse the Excel ones because it chose not to install openpyxl, a three-second pip install that any engineer would have run the moment the import failed. Claude silently skipped the XLSX files and moved on. That wasn’t an environment limitation. It was a judgment call, and Claude got it wrong. GPT-5.4 had openpyxl pre-installed, which is partly a reflection of OpenAI’s different tool philosophy (one I’ve talked about in other pieces), but the result is that Claude’s coverage came in at 75%. In a real business environment, the difference between 99% document-type coverage and 75% is enormous. Box also published their own scores on document processing and found a clear lead for GPT-5.4, which tracks with what I’m seeing.

**It knows the competitive landscape better than its competitors do.** I asked each model to list current models from the top three frontier providers and describe what they’re good at. GPT-5.4 was the most comprehensive by a clear margin, covering text, coding, media, and open-weight models across all providers. It caught its own same-day launch. It had minor imprecisions but no major blind spots. Opus got the core models right but had timeline errors and missed entire categories. This is the only eval where GPT-5.4 led clearly and cleanly without caveats, and I think it matters because one of the most common complaints I hear from people learning AI is that the model doesn’t even know what model it is. GPT-5.4 does.


## Where 5.4 falls apart, and what it reveals

I’ve talked about the wins. Now the losses, and I want to be blunt about them because understanding where a model fails tells you more about its architecture than understanding where it succeeds.

**It cannot write.** This is not a close call. GPT-5.4 is a meaningful upgrade from 5.2. Sam said it’s better, and he’s right. But it is not as good a writer as Opus 4.6, in either creative or business writing. In the stylistic writing eval, a Wodehouse pastiche and one of the hardest tests of voice, the blind judge described Opus’s opening sentence as “the single finest piece of pastiche in the entire set” and characterized GPT-5.4’s prose as technically adequate but tonally inconsistent. When you read them side by side, the gap is obvious. Opus’s narrator thinks in long, decorated sentences. GPT-5.4’s narrator sounds like someone doing a competent impression of someone who read a lot of Wodehouse. The architecture is right. The music is wrong.

And here’s where it gets interesting, where writing quality connects to something I don’t think most people are measuring. I gave both models a gnarly two-sided product management problem. A real one, with no obvious right answer. I know the correct answer, but it requires navigating ambiguity, weighing competing priorities, and making a judgment call where reasonable people disagree. GPT-5.4 got it wrong. It got it wrong logically. Its reasoning was structured and clear, and it arrived at the wrong conclusion. Opus 4.6 got it right.

I have a theory about why, and I want to be careful not to overstate it: I think writing skill and product judgment are more closely linked than we realize. Being able to write well forces you to hold competing ideas in tension, to feel when an argument is complete versus when it’s merely assembled. Product management is the same skill in a different wrapper — you’re making decisions under genuine ambiguity, and the thing that distinguishes a good PM decision from a bad one is often the same instinct that distinguishes a good paragraph from a bad one. Your mileage may vary on that theory, but I think it explains what I’m seeing in the evals.

For anyone whose work depends on voice (editorial, strategy memos, executive communications, anything where the reader needs to feel the author’s presence), Opus 4.6 is still the clear choice.

**It is slow.** On the schema migration eval, GPT-5.4 in thinking mode took 56 minutes to complete the task. Claude finished in 15. Gemini in 21. Now, to be fair, GPT-5.4 produced a 4,050-line migration script, an 11,452-line migration report, and 30 database tables. It did not waste time; it did a ton of work. Claude produced 1,800 lines of code, a concise report, and 13 focused tables. GPT-5.4’s output was more exhaustive. Claude’s was more usable. Neither is categorically better, but the 3.7x speed difference is not a rounding error when your workflow involves iteration. If you need completeness and depth on a truly brutal data task, the extra time might be worth it. If you need something you can act on quickly, you probably want Opus and the time back.

And while I’m covering practical ground: I tested PowerPoint generation, and I have to hand it to the team. GPT-5.4’s ability to build presentations has gone way up, much better than 5.2. The decks are on par with what Sonnet 4.6 produces. Opus 4.6 still has a slight edge, but the gap that used to be enormous is now narrow.

**It builds infrastructure without judgment.** This is the carwash problem at scale, and I want to name it clearly because I think it’s the most important failure mode in this model: GPT-5.4 treats tasks as pipelines to execute, not problems to understand.

In the schema migration eval, GPT-5.4’s technical pipeline was sophisticated: SHA256 hashes for provenance tracking, OCR overrides, price history modeling. Impressive engineering. But when we asked it to flag items that required attention, it produced 394 flagged items in a flat list. No categorization, no priority, no way to filter the signal from the noise. Claude produced 19 actionable flags you could immediately burn down. GPT-5.4 technically fulfilled the requirement. A human being couldn’t do anything with the output without doing the work all over again.

The same pattern showed up in customer records. GPT-5.4 found everything but failed to deduplicate: 278 customers in its database when the expected count after deduplication was roughly 176. Claude had 194, which is still too many, but much closer. GPT-5.4 created 13 distinct status values where the business reality was 4 or 5. Claude normalized to 6.

And then the ghost records. We had planted test data in the shoebox: a $25,000 carwash order from “Test Customer,” an entry for “Mickey Mouse,” another for “Asdf Asdf.” All three made it into GPT-5.4’s production database. All three would have been caught by any human who spent thirty seconds scrolling through the results. The model built a technically impressive pipeline and never once looked at what was flowing through it.

The carwash question. The ghost records. The 394 undifferentiated flags. It is the same failure mode every time. GPT-5.4 will build you a beautiful system for analyzing whether to walk or drive, and it will never stop to ask why you’re going to the carwash in the first place.


## The Steinberger signal

Three weeks before this release, Peter Steinberger — the Austrian developer who built OpenClaw, the open-source AI agent that went viral by being “the AI that actually does things” — joined OpenAI. Sam Altman called him a genius and said he would drive the next generation of personal agents.

OpenClaw started as a side project. Steinberger vibe-coded the prototype because he was annoyed it didn’t exist. Within weeks it had 247,000 GitHub stars, was being adapted for DeepSeek and Chinese messaging apps, and Baidu was planning to integrate it into its main smartphone app. It did something no frontier lab model could do out of the box: it operated computers. It booked flights, managed calendars, joined social networks, and ran on local hardware with a user’s own data.

One detail matters for this story: Anthropic’s Claude was OpenClaw’s default recommended model. The community that had described OpenClaw as “Claude with hands” watched those hands walk across the aisle.

Now look at what GPT-5.4 shipped three weeks later. Native computer use, the first general-purpose OpenAI model that can operate desktop software through screenshots, mouse commands, and keyboard inputs. Tool search, a new architecture where the model discovers tool definitions on demand instead of loading them all into the prompt. A million-token context window. Native compaction for long agent runs. Five-level reasoning effort controls. Codex integration folded into the mainline model.

I am not saying Peter was instrumental in this release. He’s brand new. What I am saying is that from a narrative perspective (and OpenAI is extraordinary at public narrative), this is the first major model drop since OpenClaw, and the neon arrows are pointing in exactly one direction.


## What OpenAI is actually building

If you read the release notes, the word that appears most often is not “intelligence” or “reasoning.” It’s “agent.” The model is positioned as infrastructure for agentic systems — systems that don’t just answer questions but operate software, manage tools, sustain workflows across hours, and coordinate with external services.

The benchmarks they chose to promote tell the same story. OSWorld (desktop navigation via screenshots) jumped from 47.3% to 75.0%, surpassing the human baseline of 72.4%. BrowseComp (persistent multi-hop web research) jumped roughly 17 points to 82.7%. Toolathlon (choosing when and how to use tools in multi-step tasks) jumped from 45.7% to 54.6%. GDPval (producing finished professional artifacts across 44 occupations) jumped from 70.9% to 83.0%.

Every one of those is an agentic benchmark. OpenAI is not optimizing GPT-5.4 to be the best thinker, the best writer, or the best reasoner in isolation. They are optimizing it to be the best agent substrate, the model you build agentic systems on top of.

Tool search is the architectural signal that makes this explicit. Previously, if you built an agent with access to dozens of MCP servers’ worth of tools, every tool definition got stuffed into every prompt. Thousands of tokens, every request, whether the model needed those tools or not. Tool search replaces that with lazy loading: the model gets a lightweight index and retrieves full definitions on demand. Token usage drops 47%. Latency drops. And critically, the architecture scales. You can give an agent access to hundreds of tools without paying the context tax on every call.

There’s a convergence story here too. GPT-5.4 folds 5.3-Codex’s coding capabilities into the mainline model. It adds computer use, tool search, and reasoning effort controls from none through extreme. One model string replaces what used to require bouncing between specialized variants. For anyone building agentic systems, “one model that does everything adequately” is often more valuable than “three models that each do one thing brilliantly,” because every model switch in a pipeline is a latency cost, a context loss, and an engineering decision. Most people running OpenClaw run it on one agent. Enterprises running enterprise workloads tend to tune their workloads to a single agent. In that world, convergence is a feature, not a compromise.

I should also note, and I think it’s worth thinking about, that we are in a transitional time. Our work, when we sit down at a computer, does not always look like agentic systems. Not yet. We have needs for models that live in PowerPoint, needs for models that live in the chatbot, needs for models that look like co-work and Claude Code, and we also need long-running agentic tasks. Part of what makes this release so interesting is that it’s a big step up on some of those needs and not others. OpenAI has signaled a monthly shipping cadence (no other frontier lab, as far as I know, has made that commitment publicly) and they’re telling you with every release where the emphasis is going to land.

The emphasis is agentic. And the places where GPT-5.4 wins in my evals are exactly those places.


## What this means for your workflow

I want to be practical about this, because the analysis is only useful if you can act on it.

If you are evaluating GPT-5.4 for yourself or your team, test it in thinking mode. The version most users encounter by default is measurably weaker on factual accuracy, on retrieval, on doing useful work. If thinking mode is the version that justifies the press release, make sure that’s what your team actually uses.

If you build agentic systems, GPT-5.4’s tool search and computer use capabilities are new, useful, and in advance of anything else inside the ChatGPT family. The ability to discover tools at runtime rather than loading all definitions upfront is a real architectural improvement that changes the cost structure of massive tool ecosystems. If you’ve been building agents that juggle dozens of MCP servers, this release matters.

If you are deep in the Claude ecosystem and are used to the way Claude calls tools, the switching cost is probably too high unless you have specific problem types that require extraordinary completeness on difficult, long-running tasks. In those situations, including coding problems where early stopping is the enemy, GPT-5.4 is worth a serious look. I have observed, and others have too, that ChatGPT in the 5.x lineage tends to persist on hard problems where Claude sometimes stops early. For multi-week agentic work, that persistence matters.

On writing quality, nothing changed. Opus-class models still produce prose that sounds like it was written by someone with taste rather than someone with access to a thesaurus. On quantitative modeling, GPT-5.4 in thinking mode is a real step forward: the statistical rigor is real, the self-critique is better than what most human analysts volunteer, and for structured analytical work with clear success criteria this is a significant advantage, with the caveat that Claude will hand you a much nicer-looking spreadsheet. On speed, Claude is 3.7x faster on complex coding tasks. That matters when your workflow involves iteration, not one-shot generation.


## The honest summary

GPT-5.4 is not the model that obsoletes its competitors. It is the model that tells you where OpenAI thinks the future is.

That future is agentic and tool-heavy. It is about sustained workflows, not single turns. About operating software, not just generating text. About discovering capabilities at runtime instead of loading everything into memory upfront. And it is notable that this emphasis arrives just weeks after hiring the person who proved the market wants AI agents that actually do things.

Whether GPT-5.4 is “better” than Opus 4.6 is the wrong question, because it depends so thoroughly on what you’re building. For raw intelligence, consistent quality, and prose that doesn’t embarrass you at a fast speed: Opus. For agentic infrastructure, tool ecosystems, and quantitative modeling where completeness outweighs speed: GPT-5.4 in thinking mode deserves serious evaluation.

But the thinking mode caveat is load-bearing. Without it, you’re not getting the model OpenAI is selling. You’re getting the base, unscaffolded, working from stale data, confidently wrong about things it should know it doesn’t know.

Welcome to March. This will probably not be the last major model release this month. And the thing I want you to take away — beyond the eval scores, beyond the carwash screenshot, beyond the Steinberger hire — is that understanding where these models are going does not require you to be a researcher. It requires you to be curious. Get into the details. I didn’t read a single benchmark score in this piece, not one. But I got into how the model performs on real work, and that matters more. The model makers are publishing more than they used to. Dig into the engineering blog posts, not just the press releases. And if you don’t understand the engineering blog post because you’re not a technical person, feed it to your LLM of choice and ask it to explain. Yes, that includes GPT-5.4. It’ll do a fine job.

We started at a carwash. We went through the eval from hell with a shoebox full of receipts. And now we’re here. The models are converging on capability and diverging on philosophy. Pay less attention to who won the benchmark. Pay more attention to what the benchmark was measuring.

One more thing. We asked GPT-5.4 whether to walk or drive to a carwash 100 meters away, and it wrote a thoughtful essay about the merits of walking. Claude wrote seven words. Keep that in your head the next time someone tells you the benchmarks say it’s the best model in the world. Benchmarks don’t measure whether the model understands what you actually need.

And until they do, you still have to.

[![](https://substackcdn.com/image/fetch/$s_!1isX!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F65b2003b-0c05-4c9e-8e76-a0fdce9e09ea_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!1isX!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F65b2003b-0c05-4c9e-8e76-a0fdce9e09ea_1024x1024.png)
