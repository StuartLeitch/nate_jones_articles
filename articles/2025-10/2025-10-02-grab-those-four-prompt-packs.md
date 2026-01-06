---
title: "Grab those four prompt packs"
author: "Nate Jones"
published: 2025-10-02
url: https://natesnewsletter.substack.com/p/weve-had-two-massive-excel-ai-launches
audience: everyone
scraped_at: 2026-01-05 19:16:15
---

It’s been the biggest week for business numbers since the calculator (ok, maybe since Excel).

And no one is paying attention!

In the three days we’ve had a massive launch from Claude that dramatically improves Excel file performance ([Sonnet 4.5](https://natesnewsletter.substack.com/p/claudes-new-model-just-launchedi?r=1z4sm5)) plus the launch of a MUCH more powerful CoPilot for Excel.

Together, these models really are strong enough to speed your Excel work up by 1000x, and for the FIRST time they can actually start to edit your existing sheets.

Which is a huge deal.

I’m not kidding about the 1000x. I’ve seen a financial analysis built in about ~5 minutes that would have taken me 3-4 days previously, which is ~1000x longer. I dig into that prompt on the video actually.

So why did I build these prompts? Well when Claude launched Sonnet 4.5, and when CoPilot launched their Excel AI tool, neither the company bothered with explaining how powerful prompts can be. Claude talked about coding, Satya Nadella talked about test scores.

Who cares. I looked around for Excel AI prompts that could help me build a revenue analysis for a client. What I found was useless garbage: “Help me create a pivot table.” “Generate a SUMIFS formula.” “Analyze this data.”

Maybe not quite that bad, but close.

Not a single prompt addressed what I actually needed: a board-ready revenue model with variance analysis, currency conversions, and scenario toggles. So I wrote my own prompt. Three iterations later, I had a complete analysis that would have taken six hours to build manually. Done in just a few minutes.

Then I tried something harder—a custom 6-currency revenue sheet built entirely from a screenshot of a client’s existing model. Worked perfectly. That’s when I realized the Excel AI landscape just shifted dramatically, but nobody’s writing the prompts that unlock what these tools actually do.

So I decided to write about it, and I came up with 18 production prompts for Excel that are designed to save you hundreds of hours.

**Here’s what you’re getting:**

- **Why existing Excel AI prompts dramatically undervalue AI** and what changed in the last three weeks that makes this urgent
- **18 production-ready prompts**
- **Four prompt packs with 18 production-ready prompts** covering everything from investor-grade financial models to quick operational fixes

  - These are organized around actual deliverables—board decks, financial models, executive dashboards—not AI features
  - For the first time, AI can one-shot these, and we should build for that
  - Also for the first time, a pack of EDIT prompts (I don’t think anyone has done this yet)
  - A video breakdown of the prompts so you understand WHY they work
- **A framework for building your own deliverable prompts** in 15 minutes instead of searching for generic garbage
- **Head-to-head analysis** of what just launched from Microsoft and Claude, with benchmarks on what actually works for complex Excel builds

Most people who use Excel (and that’s a lot of us) are barely keeping up with the AI news, and have no idea how powerful these models are. The 1% who get it are losing their sh\*t over the leverage. This is the prompt library I built for my own consulting work because nothing else exists that’s remotely useful for real deliverables.

If you build financial models, board materials, or executive analysis in Excel, this is probably the most useful thing you’ll read about Excel AI this year.


## Quick Start: Build Your Own Deliverable Prompts

You don’t need to wait for someone else to write prompts for your specific deliverables. Here’s how to build effective Excel AI prompts in about 15 minutes.

**Start with the outcome, not the task.** Ask yourself: what does the finished deliverable look like? Who sees it? What decisions does it support?

Bad starting point: “I need to analyze revenue data.” Good starting point: “I need a one-page revenue summary for Monday’s exec meeting showing Q3 performance versus plan, with the top three variance drivers highlighted and formatted for a 60-second readout.”

**Use this four-part prompt structure:**

1. **Context and Purpose** - Who is this for and why does it matter? “Build a quarterly revenue analysis for CFO review to identify budget variances requiring action.”
2. **Specific Components** - What exactly needs to be in the output? “Include: monthly actuals versus budget by product line, cumulative year-to-date comparison, top 5 variance drivers with explanations, trend analysis showing 3-month moving average, and conditional formatting highlighting variances >10%.”
3. **Data Structure** - What are you working with? “Source data: raw transaction export with columns for date, product, customer, amount. Expects monthly updates. Needs to handle 10K+ rows.”
4. **Quality Checks** - How do you verify it’s correct? “Validate: all revenue ties to source data total, no formulas reference external sheets, monthly subtotals equal grand total, conditional formatting applies consistently.”

**Test and iterate.** Your first prompt won’t be perfect. Run it, see what breaks or what’s missing, then add specificity. I typically go through 2-3 iterations before a prompt is production-ready.

**Document what works.** When you nail a prompt, save it with notes on what data format it expects and what edge cases to watch for. Your future self will thank you when you need to run this again in three months.

The prompts I’m sharing below took me a month to build and test. But you can create a custom prompt for your specific deliverable in one afternoon using this framework. Start with whatever you build most often—your weekly dashboard, your monthly board materials, your quarterly model refresh—and build that prompt first.

Wondering what this all looks like? Dig into the prompt packs below and my video for TONS of hands-on examples.

---


# Grab those four prompt packs


## [Strategic Excel Prompts: The Full Build](https://www.notion.so/product-templates/Strategic-Excel-Prompts-27f5a2ccb5268034b190e6b8e0452cc0?source=copy_link)

This is for when you need to build something substantial from scratch—the kind of financial model that goes to investors or sits in front of your board for three quarters. The 3-Year Business Plan package gives you everything from assumptions architecture through cash flow projections with scenario toggles. The SaaS Financial Model handles the full investor-ready stack: MRR waterfalls, cohort retention, cap table modeling, the works.

These aren’t quick dashboards. They’re comprehensive models that would normally take two days to build properly. With these prompts, you’re looking at 2-3 hours for a complete investor-grade deliverable. I use these when I’m building board materials or fundraising models for clients—the kind of work where precision matters and the output needs to hold up under scrutiny.


## [Exec Ready Excel Prompts: Board Materials Fast](https://www.notion.so/product-templates/Exec-Ready-Board-Prompts-27f5a2ccb526808f9afde6083961f04d?source=copy_link)

This pack is for recurring executive deliverables—the monthly board deck financials, the 13-week cash flow your CFO wants updated every Monday, the revenue bridge analysis that explains what actually happened last quarter. These are the formats finance teams use over and over. Revenue analysis with growth trends. Cash runway with scenario planning. Cohort retention heatmaps. Unit economics breakdowns.

Each prompt produces a clean, formatted output you can drop straight into board materials. The value here is speed and consistency—build these once with AI, then update them monthly in 15 minutes instead of rebuilding from scratch every time. I’ve been using the 13-week cash flow and revenue bridge prompts weekly. They’re now faster to update than my old manual versions were to open.


## [IC Excel AI Prompt Pack: Operational Speed](https://www.notion.so/product-templates/IC-Excel-AI-Prompt-Pack-27f5a2ccb52680bb84b1f84e481bf517?source=copy_link)

This is the workhorse pack for individual contributors who need to turn raw data into analysis quickly. Tier 1 prompts handle the stuff that used to eat your afternoon—monthly P&L from transaction exports, sales pipeline dashboards, expense categorization from bank feeds. Five to fifteen minutes each. Tier 2 scales up to executive-ready outputs like board packages and cohort models in 15-45 minutes.

The key difference from the Strategic pack is scope—these are focused deliverables, not comprehensive models. You’re producing one specific analysis or dashboard, not a full financial system. Perfect for analysts, department heads, and operators who need clean outputs fast without building entire modeling frameworks.


## [Excel Prompt Pack — Edits: Fix The Mess](https://www.notion.so/product-templates/Excel-Prompt-Pack-EDITS-27f5a2ccb52680919187f98d9f41fc3f?source=copy_link)

This pack solves a different problem—you already have a spreadsheet, and it’s broken or ugly or both. Someone sent you a data export that’s formatted like garbage. Your model has #REF! errors everywhere. The dashboard looks like it was built in 2008. These prompts take existing files and make them usable. Clean up messy exports into categorized summaries.

Fix broken formulas across an entire workbook. Transform raw data dumps into board-ready dashboards. Add scenario modeling to static models. The editing prompts are what I use most often in practice because client files are rarely clean. They send me their “financial model” and it’s actually three broken spreadsheets with circular references and hardcoded values. These prompts handle the reality of working with other people’s Excel files.

---


## A Note on Model Flavors: CoPilot vs. Claude

So first off: most people don’t have the choice. I recognize that. Excel is currently available in Claude Max plans, and coming downmarket to other plans soon. CoPilot is conveniently out now wherever Windows exists (pretty much) so it’s much easier for most people to get.

That being said, it’s helpful to understand what each model seems to be good at:

- CoPilot: Operates within Excel itself, which makes it handy for point edits. Also able to take prompts and build sheets out and organize data. BUT is not quite as smart as Claude, and has less solid prompt adherence for long hard tasks.
- Claude: In my experience unbeaten at prompt adherence across very large, complex Excel sheets. Treats Excel like an output and is able to use python for complex analysis prior to putting it all into Excel. Not as simple or easy to do point edits as CoPilot since it operates from outside.


## Detail: Microsoft’s Bet on “Vibe Working”

Microsoft’s new Agent Mode for Excel is their play for what they’re calling “vibe working”—using natural language to steer AI agents through complex spreadsheet tasks. It’s part of their $30/month Microsoft 365 Copilot subscription, and it fundamentally changes how you interact with Excel.

Instead of asking Copilot to “create a formula,” you tell Agent Mode to “build a 13-week cash flow model with scenario analysis and variance flagging.” The AI breaks this down into steps, executes them, and validates results. Early demos show 80-85% accuracy on formula-heavy edits, with strong performance on orchestration tasks like “flag outliers in sales data using trend analysis.”

The new COPILOT function embeds AI directly in cells, auto-updating when data changes. Python integration means advanced users can leverage full data science libraries. For Office workflows, it’s seamless—pull context from Teams, update shared workbooks, collaborate in real-time.

But here’s the thing: Agent Mode launched 48 hours ago. No comprehensive benchmarks exist yet. Reviews praise usability and multistep automation, but we don’t have hard numbers on complex deliverables. Microsoft claims 20-50% time savings on routine tasks. That’s fine for everyday Excel work. It doesn’t tell us much about building actual strategic deliverables.


## Detail: Claude Just Be Shipping

While Microsoft made headlines, Claude has been quietly destroying Excel benchmarks for weeks.

Claude 4.5 (released September 9) hits 72.5% accuracy on SWE-bench Verified—a coding benchmark that translates to precision on formulas and VBA. It scores 91% on model building tasks and 92% on data cleaning in recent head-to-head tests against 14 AI Excel tools. Users report 50-70% time savings on executive dashboards.

More importantly, Claude creates actual Excel files. Not suggestions for formulas. Not guidance on pivot tables. It generates polished .xlsx files with formulas, formatting, multiple sheets, and complex logic. Upload raw data, describe what you need, and Claude builds it.

I’ve tested this extensively over the past two weeks. The revenue analysis prompt I mentioned? Claude handled currency conversions, variance calculations, and conditional formatting without me touching Excel once. The 6-currency sheet from a screenshot? Claude understood the visual structure, inferred the calculation logic, and replicated it perfectly across currencies.

This isn’t theoretical. Finance users who understand what’s possible are reporting transformation-level productivity gains. One comment I saw: “Game-changing for automation.” Another: “This is a power tool for experts.”

The limitation is cost—Claude Pro runs $20-30/month depending on usage. But for anyone building complex spreadsheet deliverables regularly, the ROI is immediate.


## The Prompt Gap Strikes—Again

This is reminding me of my note yesterday on [OpenAI’s terrible prompt packs](https://natesnewsletter.substack.com/p/i-tested-openais-200-prompt-templatestheyre?r=1z4sm5).

Here’s what bothers me. Both tools are extraordinarily capable. Microsoft has enterprise distribution and Office integration. Claude has superior benchmarks and file creation. The technology is ready.

But when I search for Excel AI prompts, I find trash. “10 ChatGPT Prompts to Boost Excel Productivity.” “Best Copilot Prompts for Excel.” They’re all variations of the same useless categories:

- Formula helpers: “Create a VLOOKUP for...”
- Basic analysis: “Analyze this dataset and find trends”
- Generic productivity: “Help me clean this data”

These prompts assume users know what they want to build. They treat AI as a faster way to execute Excel tasks you already understand. That’s not how people actually work.

When a CFO asks me for a financial model, they don’t say “build me formulas.” They say “I need board materials showing revenue attribution by channel with variance explanations.” When a VP of Sales needs pipeline analysis, they want “a forecast with confidence intervals and deal stage progression, not a tutorial on SUMIFS.”

Real work happens at the deliverable level. Board decks. Client presentations. Investment memos. Regulatory reports. Budget reviews. These are outcomes, not tasks. And there are zero—literally zero—comprehensive prompt libraries organized around actual business deliverables.


## Why This Matters More Than You Think

Most finance teams have no idea how powerful these models are. They’re still thinking about Excel AI as “a better formula builder” or “faster data analysis.” The mental model is wrong.

But the 1% who get it? They’re losing their shit over how much leverage these tools provide. I’m watching consultants build client deliverables in 20 minutes that used to take half a day. Finance teams are generating board materials in one iteration that used to require three rounds of manual updates. Analysts are producing investment committee presentations with scenario modeling that would have taken two people a week.

This isn’t incremental productivity. It’s a structural shift in what’s possible to deliver, and how fast you can deliver it.

The gap exists because prompt libraries are written by people optimizing for clicks, not by people who actually build financial models or strategy documents for clients. They’re optimizing for search traffic (”Excel prompts”), not for outcomes (”build a DCF model with sensitivity analysis for a board presentation”).


## What Deliverable-Focused Prompts Actually Look Like

The difference between task prompts and deliverable prompts is context and specificity.

A task prompt says: “Create a revenue analysis with formulas.”

A deliverable prompt says:

```
“Build a revenue attribution analysis for Q3 board presentation showing channel performance versus targets, with variance explanations for any channel missing target by >10%. Include month-over-month growth rates, year-over-year comparisons, and a summary table highlighting top 3 overperforming and underperforming channels. Format for executive readability with conditional formatting for variances.”
```

The second prompt embeds business context, output format, quality criteria, and audience needs. Claude or Copilot can execute this. But nobody’s writing prompts at this level of specificity.

Here’s what a real prompt framework would include:

**Industry-specific deliverable templates.** Not “analyze sales data” but “generate a SaaS revenue cohort analysis showing monthly recurring revenue by signup cohort, retention curves, and lifetime value projections for investor updates.”

**Role-based output specifications.** CFO board materials look different from operational dashboards. Consulting deliverables have different formatting than internal reports. Prompts should specify audience and context.

**Quality validation checkpoints.** “Verify all formulas trace to source data. Flag any circular references. Ensure subtotals match grand totals. Highlight cells requiring manual review.” These aren’t add-ons—they’re essential for deliverables going to executives or clients.

**Complexity escalation paths.** Start with “build a three-statement financial model.” Then “add scenario analysis with three cases.” Then “include Monte Carlo simulation for key assumptions.” Each level builds on the previous, giving users a path from basic to sophisticated.

This isn’t complicated. It’s just specific. And nobody’s building it.


## The Real Opportunity

The Claude versus Copilot debate misses the point. Both tools are capable enough. Claude leads on complex builds—the benchmarks are clear. Copilot wins on Office integration and collaborative workflows. For most deliverables, either tool works fine if you know how to prompt it.

The opportunity isn’t explaining which tool is better. It’s building the prompt infrastructure that lets people actually use these tools for real work.

That means prompt libraries organized by deliverable type—board presentations, client models, regulatory reports, investment memos—not by AI feature. It means templates with embedded quality checks and business context. It means examples that show what “good” actually looks like.

Right now, we’re in this bizarre situation where the technology is ahead of the implementation knowledge. The models can build sophisticated financial deliverables in minutes. But users are still searching for “pivot table prompts” because that’s all the existing libraries offer.

This gap won’t last long. The 1% who understand what’s possible are already building internal prompt libraries. Finance teams with strong AI literacy are documenting their workflows. Consultants who get it are creating proprietary templates.

But there’s a window here—probably six months—before this becomes standard practice. The first comprehensive, deliverable-focused prompt library for Excel AI will define how people think about using these tools for real business outputs.

I’m building mine now. Starting with the revenue analysis and financial modeling prompts I’ve already tested. Then expanding to the consulting deliverables I build most often for clients—profitability models, scenario planning, market sizing, capacity analysis.

If you’re doing similar work, you should probably be doing the same. The tools are ready. The prompts aren’t. And that gap represents real competitive advantage for anyone willing to bridge it.

[![](https://substackcdn.com/image/fetch/$s_!Kk9V!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F007dbb9b-3414-4306-9bd8-0f0d850d9230_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Kk9V!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F007dbb9b-3414-4306-9bd8-0f0d850d9230_1024x1024.png)
