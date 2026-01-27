---
title: "I built an 11-tab financial model in 10 minutes + the prompting guide that makes it repeatable"
author: "Nate Jones"
published: 2026-01-27
url: https://natesnewsletter.substack.com/p/anthropic-just-put-claude-inside
subtitle: "Watch now | Just 5 months ago, AI was only just starting to crack Excel. Now, weeks of modeling work can happen in minutes."
audience: everyone
scraped_at: 2026-01-27 12:00:17
---

This morning I built an eleven-tab financial model in ten minutes. Sensitivity analysis, opportunity cost comparisons against S&P 500 returns, risk quantification, market data by zip code, cash flow projections—the whole apparatus. Two weeks of work compressed into the time it takes to make coffee. Norway’s sovereign wealth fund reports saving 213,000 hours with the same tool. This is not incremental improvement. This is a phase change in what knowledge work means.

And here’s the part that should break your model of how AI competition works: the tool is Claude, it’s now embedded inside Microsoft Excel, it’s connected to financial data feeds that Microsoft doesn’t have built-in access to, and Microsoft is paying Anthropic thirty billion dollars for the privilege of hosting it on Azure.

On Friday (January 24, 2026), Anthropic opened Claude in Excel to anyone with a Pro subscription—twenty dollars a month. Before that, it was gated to expensive enterprise tiers. Now it’s not. What Anthropic has built is a template for how the next phase of AI competition actually works. The race to build better base models is approaching diminishing returns. The race to embed intelligence in workflows, backed by proprietary data partnerships, is just beginning. Anthropic understood this before almost anyone else, and Excel is their proof of concept.

**Here’s what’s inside:**

- **What Claude in Excel actually is.** Not a formula assistant—a native sidebar with full structural awareness of your workbook, cell-level citations, and transparent change tracking.
- **Where it’s transformative and where it’s not.** The honest breakdown of what works, what requires human input, and what’s functional but not polished.
- **The strategic shift nobody’s talking about.** Why the model race is hitting diminishing returns, and why workflow integration backed by data partnerships is the new competition.
- **The data moat strategy.** How Anthropic assembled licensed partnerships with LSEG, Moody’s, S&P Capital IQ, and others—and why Microsoft can’t easily replicate it.
- **The coopetition paradox.** Microsoft is simultaneously hosting Claude, competing against it, and collecting billions from Anthropic. What this tells us about where AI is heading.
- **What I built.** Three spreadsheets that demonstrate the transformation: a rent-vs-buy calculator, a FAANG-vs-AI equity analysis, and an AI trends data compilation.
- **The prompts and best practices.** How to actually use this thing, with the specific language that gets results.

Let me show you what Anthropic actually built—and why it matters for how you work.


## **[Grab the Guide](https://docs.google.com/document/d/1wd6XHve66ufY3P2tMfnGoraymJYNEjRE11kFhnAvzgA/edit?usp=sharing)**

I spent a lot of hours figuring out what works and what doesn’t in Claude in Excel—the prompting patterns that get architecture instead of one-off formulas, the recovery workflow when you hit memory limits, the debugging language that actually traces errors instead of generating new ones. I put it all in a guide so you can skip the tinkering phase and get straight to building. Installation steps, first-win prompts, the mental model shift that matters, and the specific phrases that unlock multi-tab models, sensitivity analysis, scenario comparisons. Grab it, open Excel, and have fun!


## **What Claude in Excel Actually Is**

Before the strategy, the mechanics—because they matter.

Claude in Excel is a native sidebar add-in that lives inside Microsoft Excel with full awareness of your workbook. Not “paste cells into a chat window” awareness. Actual structural awareness: every tab, every formula, every cell reference, every dependency chain that connects assumptions to outputs. Ask it to explain how a model works and it traces the actual formula relationships in your actual spreadsheet, with cell-level citations you can click to navigate directly to the relevant locations. Ask it to update an assumption and it modifies cells while preserving the formula dependencies that would break if you weren’t careful. Ask it to debug an error and it doesn’t just hand you a fixed formula—it explains the root cause, shows you the broken reference, walks you through what went wrong.

Every action gets logged in a transparent change trail. This sounds like a compliance checkbox until you remember that finance models get audited, reviewed by skeptical colleagues, handed to successors who need to understand the logic. The ability to demonstrate how AI-assisted changes were made is the difference between a tool you can deploy and a liability compliance will never approve. Anthropic built this transparency into the core architecture, which is why regulated industries are adopting Claude faster than they adopted previous AI tools.

The underlying engine is Claude’s most capable models. On complex, multi-tab workbooks, you need a model that can hold the entire structure in context, reason about cross-tab dependencies, and maintain coherence over dozens of iterative exchanges. Claude can do that. When I built the eleven-tab rent-vs-buy model, it maxed out a chat window’s context—but that wasn’t a failure, just a checkpoint. I started a new chat, Claude read the existing work, and we kept building. The system is more robust than it first appears.


## Where It’s Transformative and Where It’s Not

Let me be honest about what works and what doesn’t, because the speed transformation is so dramatic that the limitations barely register—but you should still know them.

**What’s transformative:**

The core capability—building, explaining, debugging, and iterating on complex spreadsheets through natural language—is genuinely weeks-to-minutes fast. Claude handles multi-tab architectures well; I’ve built 3-4 tab models in single prompts and 8+ tab models across sessions with easy handoffs. It searches for and populates certain data itself—housing prices by zip code, historical S&P returns, standard benchmarks. It suggests analyses you didn’t ask for; the Risk Analysis tab in my rent-vs-buy model was entirely Claude’s idea. You’re not just getting faster execution. You’re getting an AI that thinks through problems with you and surfaces considerations you might have missed.

**What requires human input:**

Specialized data that isn’t publicly searchable—I had to fetch METR benchmark data manually and paste it in. Proprietary datasets, anything behind paywalls, real-time pricing (unless you have the MCP connectors on higher tiers). Claude needs you to bring some raw materials.

**What’s functional but not polished:**

Charting. Claude structures data for visualization well—the right columns, proper ranges, correct references. But gorgeous charts? You’re doing that last mile yourself. Five minutes of formatting work. Given that you just saved two weeks of model construction, this is not a meaningful friction.

**What’s a checkpoint, not a wall:**

Memory limits. Complex builds will max out chat windows. When it happens, save your spreadsheet, start fresh, tell Claude to examine the existing work. It orients itself in about two minutes by reading what’s already built. The eleven-tab model took multiple sessions. Total time was still measured in minutes, not days.

At the scale of transformation we’re talking about—weeks becoming minutes—these limitations are rounding errors. If someone offered to compress your workload by 1000x but you’d occasionally need to paste in some data and touch up a chart, you wouldn’t call that a caveat. You’d call that a miracle with minor inconveniences.


## The Shift No One’s Talking About

For the past three years, AI competition has been legible: train bigger models, score higher on benchmarks, ship faster inference, repeat. OpenAI and Anthropic and Google raced to build better reasoning engines while everyone else watched the leaderboards. That competition was real and it mattered—the capability gains were extraordinary. But it was always going to hit diminishing returns. The question was never whether foundation models would get good enough for most professional tasks; the question was what would happen after they did.

We’re now living in the “after.” Frontier models can all write competent code, analyze documents, reason through multi-step problems, and maintain coherent context over long conversations. The differences between GPT-5, Claude Opus 4.5, and Gemini on most practical tasks are marginal—noticeable to researchers, invisible to users trying to get work done. When the models converge, the competitive moat has to come from somewhere else.

Anthropic’s answer: workflow integration backed by data partnerships. Don’t just build a better model; embed it where work actually happens and connect it to information that competitors can’t access. Excel was the obvious first target—not because spreadsheets are sexy, but because Excel is the operational nervous system of global finance. Every investment bank, every asset manager, every FP&A team, every consultant runs on Excel. Trillions of dollars in decisions flow through cells and formulas maintained by analysts in Microsoft’s forty-year-old software. If you can become the default intelligence layer for that workflow, you’ve captured something far more durable than a benchmark score.


## The Data Moat Strategy

The Claude in Excel add-in is interesting. What Claude connects to is transformative.

Since July 2025, Anthropic has been assembling licensed partnerships with the institutional data providers that professional finance actually runs on. Through the Model Context Protocol—their open standard for AI-to-system connections—Claude can now pull from: LSEG for live market data; Moody’s for credit ratings and company information; S&P Capital IQ for financials; and others including FactSet, Morningstar, PitchBook, and Aiera. These aren’t API integrations cobbled together by a product team. They’re formal partnerships where major financial data providers have enabled their information to flow into Claude’s reasoning.

This matters because any language model can help you write a SUMIF formula. That’s table stakes. What a generic model cannot do is pull this morning’s pricing from the London Stock Exchange, cross-reference it against current Moody’s credit ratings, check it against S&P fundamentals, and update your comparable company analysis—all in one fluid workflow, inside the application you’re already working in. That requires access to data that doesn’t exist on the public internet, data that institutions pay substantial subscription fees to access, data that is the actual raw material of professional financial analysis.

The strategic logic is simple: the quality of AI outputs depends entirely on the quality of inputs. Anthropic can’t out-train OpenAI on base model capabilities—they’re too close in performance. But they can out-connect them. By securing these data partnerships, Anthropic has built capabilities that competitors cannot easily replicate, not because Microsoft or Google lack technical ability, but because replicating it requires negotiating the same licenses with the same institutional providers who have already committed to someone else. Relationships compound. Moats deepen over time.

On top of the connectors, Anthropic packaged six pre-built Agent Skills that productize the workflows junior analysts spend their days performing: DCF models with WACC calculations and sensitivity tables, comparable company analysis with auto-refreshing metrics, due diligence data packs generated from data room documents, earnings analysis that extracts guidance changes from transcripts. Each represents hours of analyst drudgery compressed into a prompt. The models need human review—Claude is good at first drafts, not final judgment—but the productivity multiplier is real. Norway’s sovereign wealth fund reportedly saved 213,000 hours. We’re talking about work that took weeks compressing into minutes.


## The Coopetition Paradox

And now for the part that breaks conventional competitive analysis entirely.

Microsoft and Anthropic announced a thirty-billion-dollar partnership. Anthropic committed to purchasing massive Azure compute capacity; Microsoft gets to host Anthropic’s models and collect infrastructure revenue. Claude is available inside Microsoft Copilot Studio, meaning enterprises can build agents powered by Claude on Microsoft’s platform. Claude Opus 4.1 powers Microsoft’s Researcher agent in M365 Copilot as an alternative to OpenAI. Microsoft’s documentation lists Anthropic as a subprocessor for Excel Agent Mode, Word agents, PowerPoint agents.

So Microsoft is simultaneously: hosting Claude as an alternative model in its flagship productivity suite, competing against Claude with its own Copilot for Excel, and collecting billions from Anthropic for Azure infrastructure. This is coopetition at a scale that has no historical precedent. The companies are partners at the infrastructure layer, competitors at the product layer, and intertwined in ways that make “winning” and “losing” almost meaningless categories.

The dynamics get stranger when you examine the product overlap. Copilot for Excel requires files saved to OneDrive with AutoSave enabled—every change commits immediately to the cloud. Many finance teams hate this because they want control over when work gets saved, the ability to experiment without permanent changes, deliberate version control. Claude in Excel works with local files. This isn’t a technical limitation; it’s a product decision that reflects Microsoft’s cloud-first strategy versus Anthropic’s willingness to meet users where they are. Microsoft’s own strategic choices created a gap that a competitor could exploit from inside Microsoft’s own application.

What does this tell us about where AI is heading? First, that model providers and platforms are separating—Microsoft doesn’t need to win the model race anymore. Second, that vertical integration is the new competition—Anthropic isn’t trying to beat Copilot by building a better general-purpose assistant; they’re building a specialized tool that’s better for finance than anything Microsoft can offer. Third, that the “one AI to rule them all” thesis is dying—the future looks like multiple specialized AI systems optimized for different domains and workflows. Fourth, that infrastructure providers win regardless of which AI models succeed.


## The Capability Curve That Made This Possible

None of this works if the AI can’t actually sustain complex work over time. The reason Claude in Excel is viable now is the extraordinary improvement in model endurance over the past year.

METR measures the median task duration that frontier models can reliably complete—how long an AI can sustain coherent work on a problem before it loses the thread. A year ago, frontier models were crossing the one-hour mark for the first time. Now they’re approaching three hours of sustained focus on a single problem.

That’s the capability threshold that makes workflow integration viable. You can’t embed an AI in complex financial modeling if it loses context after five exchanges. You need a model that can hold an eleven-tab spreadsheet in working memory, understand the dependencies between tabs, reason about formula chains, and maintain coherence over dozens of iterative refinements. That’s not incremental improvement; that’s a phase change in what’s possible.

The infrastructure buildout enabling this is staggering. Datacenter capital expenditure is now measured in hundreds of billions annually and accelerating. The AI GPU market has grown by an order of magnitude in just a few years. Training compute has scaled by orders of magnitude since AlexNet in 2012. This is infrastructure deployment at a pace we haven’t seen since electrification.

I’ve been tracking this progression in real time. In [September](https://natesnewsletter.substack.com/p/finally-ai-can-do-excel-and-powerpointget), I called it the biggest step forward for real-life work in six months—Claude could finally create actual Excel files with working formulas, and an eight-tab spreadsheet with VLOOKUPs took under three minutes. In [October](https://natesnewsletter.substack.com/p/weve-had-two-massive-excel-ai-launches), the capability expanded: AI could now edit your existing sheets, not just create new ones. By [December](https://natesnewsletter.substack.com/p/new-chatgpt-52-complete-teardowni), models were sustaining forty-minute analytical workflows across ten-thousand-row datasets. I quoted Whitehead in September: “Civilization advances by extending the number of important operations which we can perform without thinking of them.” That felt profound at the time—looking back, it was just the opening act. What happened Friday—Claude moving inside Excel with native awareness, institutional data access, and a twenty-dollar price point—isn’t a sudden breakthrough. It’s the moment the capability curve became impossible to ignore.


## What I Built (And What It Proves)

Let me make this concrete with three spreadsheets I built using Claude—not to show off, but to demonstrate what’s now possible.


### [The Rent vs. Buy Calculator](https://docs.google.com/spreadsheets/d/1H2c6Obm9zWMut2VNkILs8M9YzhYJ3cG_/edit?usp=sharing&ouid=118371784362828784038&rtpof=true&sd=true)

[![](https://substackcdn.com/image/fetch/$s_!ZQpa!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1fa2ae6d-388b-4fe8-bb52-03027d5aacee_1072x863.png)](https://substackcdn.com/image/fetch/$s_!ZQpa!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1fa2ae6d-388b-4fe8-bb52-03027d5aacee_1072x863.png)

Start with something everyone eventually faces: should you rent or should you buy? This isn’t a simple comparison—it’s an eleven-tab model that actually thinks through the decision properly. Building it maxed out an entire chat window’s context; the model is that comprehensive.

[![](https://substackcdn.com/image/fetch/$s_!u03y!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9ed819ed-9537-4c5e-8f8c-f11cfef28d18_890x664.png)](https://substackcdn.com/image/fetch/$s_!u03y!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F9ed819ed-9537-4c5e-8f8c-f11cfef28d18_890x664.png)

Flip to the Summary tab—this is your dashboard. Right at the top, a recommendation: RENT & INVEST or BUY. For the default assumptions I’ve got loaded, it says rent, with a $334,000 financial advantage over ten years. That’s not intuition; that’s math. Below that, the market signal based on price-to-rent ratio—over 20 means rent is favored, under 15 means buy, and Manhattan at 23.1 is telling you something.

[![](https://substackcdn.com/image/fetch/$s_!Qk9I!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffba35bae-6f43-4827-8db6-ad7418048eef_1052x857.png)](https://substackcdn.com/image/fetch/$s_!Qk9I!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffba35bae-6f43-4827-8db6-ad7418048eef_1052x857.png)

But here’s where it gets interesting. Go to the Opportunity Cost tab. This is the analysis most rent-vs-buy calculators skip entirely. What if you took your down payment and invested it in the S&P 500 instead? The tab shows historical returns—10.5% over a hundred years, 15.7% over the last decade—and models what your money would become if you stayed liquid. This isn’t anti-homeownership propaganda; it’s just making the implicit explicit. When you buy a house, you’re not just buying shelter. You’re making a bet that real estate in your market will outperform equities, and you’re giving up the liquidity that lets you respond to opportunities and emergencies. The model quantifies that tradeoff.

[![](https://substackcdn.com/image/fetch/$s_!6WEF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faecd2069-16f8-4ffc-92fd-702e7c2648f2_970x849.png)](https://substackcdn.com/image/fetch/$s_!6WEF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Faecd2069-16f8-4ffc-92fd-702e7c2648f2_970x849.png)

And then there’s the Risk Analysis tab—and this one is important because it was Claude’s idea, not mine. I didn’t ask for it. When we were building out the model, Claude suggested that a proper rent-vs-buy analysis should name and quantify the risks on both sides, then went ahead and built the tab. Market risk—your house could decline 20%, here’s what that costs you. Liquidity risk—you can’t sell quickly, here’s what that means. Maintenance risk—roofs fail, HVAC dies, budget accordingly. The renting risks are there too. This is the part that matters: you’re not just getting 100x faster execution. You’re getting an AI that thinks through the problem with you and surfaces analyses you might not have considered.


### [FAANG vs. AI Super Cycle Analysis](https://docs.google.com/spreadsheets/d/1dIlfjB-APkRVg4hce3TIgp-IVPbwO_Gq/edit?usp=sharing&ouid=118371784362828784038&rtpof=true&sd=true)

[![](https://substackcdn.com/image/fetch/$s_!HBhm!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F928536a4-1c8a-4177-ae11-9d601beb791a_2254x1340.png)](https://substackcdn.com/image/fetch/$s_!HBhm!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F928536a4-1c8a-4177-ae11-9d601beb791a_2254x1340.png)

Now let’s shift to something with broader market implications. Everyone’s talking about AI stocks, but almost nobody is asking the right comparative question: how does this cycle actually compare to the last one? I built a model to find out.

The Executive Summary tab frames it: we’re comparing the FAANG+M cycle from March 2009 to December 2019—post-financial-crisis, mobile and cloud as catalysts—to the AI infrastructure cycle from November 2022 to now. Both periods start after major corrections, which makes the comparison valid. You’re measuring from similar starting conditions.

[![](https://substackcdn.com/image/fetch/$s_!xp1p!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F56f23417-8bd7-4aa3-a5a5-7ee0979d6dea_958x777.png)](https://substackcdn.com/image/fetch/$s_!xp1p!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F56f23417-8bd7-4aa3-a5a5-7ee0979d6dea_958x777.png)

Look at the key metrics in my model. Average CAGR for FAANG+M was 35%. For AI infrastructure, it’s 44%—and that’s only three years in. But here’s the number that should stop you cold: NVIDIA’s CAGR is 103%. One hundred and three percent. Netflix was the top FAANG performer at 52%, which seemed unbelievable at the time. NVIDIA is doubling that. We are watching something historically unprecedented, and the model makes that legible.

[![](https://substackcdn.com/image/fetch/$s_!MtzV!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4a310e03-8c4a-41d6-b974-38628fb56cad_825x774.png)](https://substackcdn.com/image/fetch/$s_!MtzV!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4a310e03-8c4a-41d6-b974-38628fb56cad_825x774.png)

The Deep Dive Analysis tab shows why the current cycle is structurally different from the last one. FAANG returns relied heavily on multiple expansion—investors paid progressively higher multiples for the same earnings. In my compiled data, the P/E premium over the S&P went from 38% at the start to 105% at the end. AI infrastructure is different. Multiples expanded fast initially, but they’ve actually compressed recently—from 45x to 35x—because earnings are catching up. NVIDIA’s price is insane, but so is NVIDIA’s revenue growth. The model makes this distinction visible, and it matters for how you think about where we are in the cycle.


### [AI Trends Data Compilation](https://docs.google.com/spreadsheets/d/1M34UFtelKn9hcxZfMDHYiBxKRFkTvVoi/edit?usp=sharing&ouid=118371784362828784038&rtpof=true&sd=true)

[![](https://substackcdn.com/image/fetch/$s_!17v-!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7d7609b9-26a1-457a-b605-4698370d923e_1081x775.png)](https://substackcdn.com/image/fetch/$s_!17v-!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7d7609b9-26a1-457a-b605-4698370d923e_1081x775.png)

Finally, let me show you the data that contextualizes everything else. This is four tabs of the numbers that define the moment. Unlike the rent-vs-buy model where Claude could search for and populate housing data itself, some of this required me to go fetch the source data—I pulled the METR benchmark numbers directly from METR.org and fed them in. The model isn’t magic; it needs help with specialized data that isn’t easily searchable. But once it has the data, it can structure it, build the visualizations, and surface the insights.

[![](https://substackcdn.com/image/fetch/$s_!fmqf!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3c5825f4-7296-479a-9577-88dca146de5b_985x471.png)](https://substackcdn.com/image/fetch/$s_!fmqf!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F3c5825f4-7296-479a-9577-88dca146de5b_985x471.png)

The Memory Wall tab shows a problem most people don’t know exists. Since 2016, GPU compute has scaled by 106x—from the P100 to the B200, that’s a hundred-fold increase in FLOPS. But memory bandwidth? Only 11x. Compute is racing ahead; the ability to feed data to that compute is falling behind. This is why NVIDIA’s pricing power is so durable and why the next architectural breakthroughs matter so much. The constraint isn’t building faster chips; it’s building chips that can actually use their speed.


## The Question That Matters Now

On Friday, Anthropic opened Claude in Excel to anyone willing to pay twenty dollars a month. Almost nobody noticed. But if you understand what Anthropic actually built—the workflow integration, the data partnerships, the vertical specialization strategy—you see something larger: a template for how AI competition works after the models converge.

The models are good enough. The question now is who controls the workflows, who owns the data relationships, who gets embedded in the places where real work happens. Anthropic bet on Excel and financial services as their beachhead, and the early results—213,000 hours saved at Norway’s sovereign wealth fund, production deployments at Citi and Deutsche Bank and Bridgewater—suggest the bet is paying off.

For individuals: the tools to do weeks of analytical work in minutes are now accessible. Twenty dollars a month and a clear sense of what you’re trying to accomplish.

For organizations: the AI strategy that made sense eighteen months ago—wait, pilot, evaluate—no longer fits competitive reality. Organizations that embed AI in core tools and connect it to proprietary data will have compounding advantages. Organizations that wait will find competitors have locked up the workflow positions that matter.

The spreadsheet is where numbers become decisions, where assumptions become forecasts, where data becomes strategy. An AI that lives there, that understands the formulas and dependencies, that can trace the logic and explain the implications and suggest improvements while maintaining the audit trail that lets you trust the results—that’s not a chatbot anymore. That’s a new kind of colleague. And as of Friday, that colleague is available to basically anyone who wants one. The question is no longer whether AI will transform knowledge work; it’s whether you’ll be the one using it or the one being replaced by someone who does.

[![](https://substackcdn.com/image/fetch/$s_!Ri6h!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F75adcc93-c03a-4e9e-9805-68dfdd1372d3_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Ri6h!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F75adcc93-c03a-4e9e-9805-68dfdd1372d3_1024x1024.png)
