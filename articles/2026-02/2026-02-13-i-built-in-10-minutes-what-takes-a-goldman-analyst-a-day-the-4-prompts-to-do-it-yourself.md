---
title: "I built in 10 minutes what takes a Goldman analyst a day + the 4 prompts to do it yourself"
author: "Nate Jones"
published: 2026-02-13
url: https://natesnewsletter.substack.com/p/general-intelligence-just-moved-into
subtitle: "Watch now | Your tools just got a lot smarter overnight."
audience: everyone
scraped_at: 2026-02-22 15:12:28
---

I built a full operating model last week. Revenue projections, cost structure, unit economics, scenario analysis — the works. It took ten minutes. Then I told Claude in PowerPoint to build the board deck from that model — five slides, executive summary, financials, key metrics, risks, asks — using my company’s actual slide template. Twenty minutes later I had a presentation with charts referencing the live Excel data, formatted in my brand’s fonts and colors, that looked like my team spent two days on it. A Goldman Sachs analyst looked at the model and told me it was solid. The kind of output that would have taken him a full day. The deck would have taken another.

Thirty minutes total. From a blank spreadsheet to a board-ready presentation. In Excel and PowerPoint — the tools I already had open.

This is the piece of this week’s AI news that I think most people will sleep on, because it doesn’t have the drama of a benchmark war or the spectacle of sixteen agents building a C compiler. It’s just Excel. And PowerPoint. The tools nobody thinks about twice. And as of this week, they have general intelligence inside them — the same intelligence that built a C compiler, finding zero-day vulnerabilities, coordinating agent teams. Except now it’s building your operating model and your board deck inside the applications you’ve used for twenty years.

And here’s the part that should really stop you: this isn’t about one product release. On Wednesday, Anthropic shipped Opus 4.6 and every Claude-powered Excel and PowerPoint on Earth got smarter overnight. Nobody installed an update. Nobody migrated to a new version. The spreadsheet looked the same. The slide canvas looked the same. The brain inside both leaped a generation. Opus 4.7 is coming. Then 5.0. The applications don’t change. The intelligence inside them compounds. And that pattern — not any single release — is what should change how you think about your tools, your team, and your career.

**Here’s what’s inside:**

- **The ten-minute operating model.** What shipped, how to get it, and what a Goldman analyst said when he reviewed the output.
- **The data connectors that change everything.** Why Moody’s, LSEG, and five other institutional data feeds make this more than a chatbot in a sidebar.
- **Intelligence compounds across tools.** The context layer forming between Excel and PowerPoint — and why it eliminates an entire category of work most people don’t realize they’re doing.
- **Microsoft is becoming a dumb pipe.** What it means when the company that owns Office starts offering someone else’s brain inside it.
- **The slop problem.** Every tool that makes excellent work easy also makes garbage easy. The only filter is judgment — and that’s entirely on you.

I covered Opus 4.6 in a separate piece — what the model can do, why it matters, how it changes what’s possible. This piece is about what happens when that intelligence shows up inside the tools 1.5 billion people already use every day.


## **[Grab the Prompts](https://www.notion.so/product-templates/From-Operating-Models-to-Board-Decks-in-Minutes-3035a2ccb526803f96daeaab4a7e773f?source=copy_link)**

The tools got powerful overnight. Claude in Excel can build in ten minutes what used to take a day. Claude in PowerPoint can produce board-ready decks in twenty. But speed without judgment is just fast slop.

These prompts force the thinking that tools can’t do: the Operating Model Builder makes you clarify your assumptions before building, the Board Deck Generator makes you define the decision before drafting slides, the Slop Filter catches professional-looking output that says nothing, and the Judgment Prompt stops you from building the wrong thing efficiently.

The danger isn’t that AI produces bad work. It’s that AI produces excellent-looking work whether you thought clearly or not. The output looks the same. The difference is judgment — and that’s on you.


## **What actually shipped**

Two things happened in the past two weeks, and taken together they represent something bigger than either one alone.

On January 24th, Anthropic opened Claude in Excel to Pro subscribers — anyone paying $20 a month. The feature had been in limited beta since October 2025, but the January release made it broadly available. Then on February 5th, alongside the Opus 4.6 launch, two things happened at once: Claude in Excel upgraded to Opus 4.6 — the same model that powered the C compiler project — and Claude in PowerPoint launched for the first time.

The Excel integration isn’t a chatbot bolted onto a sidebar. It operates directly on your workbook. It reads your existing data, understands your tab structure, writes and debugs formulas, builds pivot tables, creates charts, applies conditional formatting, and handles data validation — working inside the spreadsheet rather than generating code you copy-paste in. In my testing, it works with local files on your machine — no OneDrive required, no cloud dependency, no uploading sensitive financial data to someone else’s server.

The PowerPoint integration is more interesting than most coverage suggests. It doesn’t just generate slides — it reads your slide masters, layouts, fonts, and color schemes, then creates content that matches your brand exactly. Your template. Your colors. Your font hierarchy. It produces slides that don’t look like AI made them because they match the design system your team already uses. In my experience, charts and diagrams come through as native PowerPoint objects — editable, not static images pasted in. I’ve gotten SVG graphics, Mermaid diagrams rendered as slide elements, process flows, org charts, architecture diagrams — created as the same kinds of shapes and SmartArt your design team would build by hand, except produced in seconds. Every element is editable. Move a box. Change a label. Resize a chart. It behaves like PowerPoint because it is PowerPoint — not a screenshot of something an AI made somewhere else.

The combination matters more than either tool alone. Because both run on the same underlying model, Claude is able to bring the same intelligence to bear across both, and Claude-produced Excel documents play nicely with Claude-produced PowerPoints. Build an analysis in Excel, then tell Claude in PowerPoint to generate the board deck — charts that reference the actual data, narrative that reflects the actual numbers, formatting that matches your actual brand. The workflow that used to take a full day — analyst builds the model in the morning, spends the afternoon building the deck to present it — collapses to the time it takes to describe what you want and review what you get. Analysis to narrative in one pipeline. Data to decision in one sitting.


## **How to get it**

This is the part most coverage skips.

Claude in Excel is available to anyone on Claude’s Pro plan — $20 a month. That’s it. Twenty dollars. Same price as a Netflix premium plan. You install the Claude desktop app, enable the Excel integration, and it appears inside Excel the next time you open a workbook. Claude in PowerPoint launched February 5th and is currently available on Max ($100/month), Team ($30/user/month), and Enterprise plans. Not yet on Pro. If you need both tools and you’re an individual, the Max plan gets you everything. If you’re running a team, the Team plan is the pragmatic entry point.

The pricing matters because of what it implies about the cost of intelligence. A junior financial analyst costs $80,000 to $120,000 a year, fully loaded. An associate at a consulting firm bills at $300 to $500 an hour. The modeling and deck-building work that occupies 30% to 60% of their week — the operating models, the competitive analyses, the board presentations, the client deliverables — is now available for $20 to $100 a month, running inside the tools every organization already owns licenses for.

I’m not saying the junior analyst is obsolete. I’m saying the junior analyst who can only build models and decks has a problem, because the scarce skill is no longer “can you build this” but “do you know what to build, and can you interpret what it means.” That distinction — between execution and judgment — is the entire story of what happens next.


## **The data connectors that change everything**

Here’s where it gets real, and where most people comparing Claude in Excel to Microsoft Copilot miss the point entirely.

Anthropic partnered with Moody’s, LSEG (London Stock Exchange Group), Aiera, Third Bridge, and Egnyte to build financial data connectors directly into the Claude ecosystem. These aren’t generic web scrapers. They’re authenticated, structured data feeds from the platforms that institutional finance actually runs on.

What that means in practice: you can ask Claude to build a comparable company analysis, and instead of manually pulling data from a terminal, the model queries live financial data through these connectors and populates your spreadsheet with current numbers. Revenue multiples, EBITDA margins, growth rates, trading comparables — sourced from the same data providers your bank or fund already subscribes to, flowing directly into your workbook.

Anthropic also shipped pre-built financial skills — purpose-built workflows for the tasks that eat most of an analyst’s week. Comparable company analysis. DCF models. Due diligence data packs. Earnings analyses. Initiating coverage reports. These aren’t templates you fill in. They’re intelligent workflows that understand what a DCF model needs, know how to structure the assumptions tab, and build the sensitivity analysis without being told the convention.

For anyone who has built a DCF from scratch — and I mean actually built one, with properly linked assumptions, a working WACC calculation, and a sensitivity table that doesn’t break when you change an input — you know the mechanical work takes hours. Not because it’s conceptually difficult. Because there are hundreds of cells that need to reference each other correctly, and one broken link — a terminal value that references the wrong growth rate cell, a WACC calculation that pulls from last year’s risk-free rate — means your output is wrong in a way that takes an hour to trace. That mechanical work, which has nothing to do with financial judgment and everything to do with spreadsheet plumbing, is what just got automated.


## **The enterprise proof points**

I need to address the “is this real or is it a demo” question head-on, because the answer matters.

The Goldman Sachs partnership, announced February 6th, puts a stamp on this. Goldman is deploying Claude across accounting and compliance workflows — not as a pilot, as a production tool. When the most prestigious investment bank in the world puts this in production for its own internal operations, the demo question is answered.

AIG reported that Claude made document reviews five times faster, with accuracy improving from 75% to over 90%. Not faster at the expense of quality. Faster and more accurate simultaneously. The error rate went down while the speed went up. That combination — which is rare when you add speed to human processes — is the signature of a tool that doesn’t get tired, doesn’t skip the boring rows, and doesn’t assume the numbers in the summary tab match the numbers in the detail tabs.

Norges Bank Investment Management — which manages Norway’s $1.7 trillion sovereign wealth fund, the largest in the world — reported a 20% productivity increase and estimated 213,000 hours saved across their operations. These are institutions where being wrong about a number has nine-figure consequences. They are not running proof-of-concept demos. They are betting their operational processes on this tool working correctly, every time, on files that move markets.


## **What this looks like on a Tuesday morning**

Let me walk through specific workflows, because “general intelligence in your tools” is abstract until you see what it does in practice.

**The operating model.** You open a blank workbook. You tell Claude: build me a three-year operating model for a B2B SaaS company with $5M ARR, 110% net dollar retention, 70% gross margins, and a sales team of 12. Ten minutes later, you have a multi-tab workbook — revenue projections, hiring plan, cash flow statement, unit economics by customer segment, scenario toggles for bear/base/bull cases. Every formula is linked. The assumptions tab drives everything. Change one input and the whole model recalculates. This is what a Goldman analyst told me would have taken him a full day. Not because the analyst is slow. Because the mechanical work of building and linking 400+ cells correctly takes time that has nothing to do with financial intelligence.

**The board deck.** You’ve built the model. Now you tell Claude in PowerPoint: build a board deck from this analysis — five slides, executive summary, financial overview, key metrics, risks, and asks. It reads the Excel data, generates charts that reference the actual numbers, applies your company’s slide template, and produces a deck that looks like your team made it. Total time from raw data to board-ready deck: under thirty minutes for work that typically takes one to two full days.

**The pitch deck.** You’re raising a Series B. You have your financials in Excel and a pitch template your designer built last quarter. You tell Claude: build a twelve-slide pitch deck from these financials using this template. Market size with TAM/SAM/SOM breakdown. Traction slide with an ARR growth chart pulled from the model. Team slide. Financial projections with a clear path to profitability. Every slide uses your fonts, your colors, your layout grid. The output looks like something your team spent three days polishing. It took forty minutes, and every number traces back to your actual model.

**Due diligence.** You’re evaluating an acquisition target. You upload three years of financial statements. You tell Claude: build a due diligence data pack, flag anything unusual. It structures the data, calculates key ratios, benchmarks them against industry medians through the LSEG connector, and highlights anomalies — a spike in accounts receivable relative to revenue, a declining gross margin trend that the target’s narrative doesn’t explain, a capex pattern that doesn’t match the growth story. A junior associate would take two to three days. Claude takes twenty minutes. And it catches things the associate might miss, because it doesn’t get tired and it doesn’t skip the boring rows.

**Comparable company analysis.** You name ten companies. Claude pulls current trading data through the financial connectors, calculates every relevant multiple — EV/Revenue, EV/EBITDA, P/E, PEG — adjusts for one-time items, formats the output table, and generates the charts for your pitch book. This is the analysis that occupies a first-year banking analyst’s entire evening. Claude does it in the time it takes to run the queries and format the output.

**The quarterly business review.** Your department heads submit their numbers in separate spreadsheets. You consolidate in Excel — revenue by product line, expenses by department, headcount by team, pipeline by stage. Then you tell Claude in PowerPoint: build a QBR deck, fifteen slides, use our corporate template. Revenue trends with commentary. Expense variance versus plan. Headcount actuals versus budget. Pipeline coverage ratios by segment. Each slide tells a story about one metric, with charts that reference the live data. A chief of staff used to spend two days assembling this from six different sources. Now it’s an afternoon — and most of that afternoon is thinking about what story the numbers should tell, not wrestling with chart formatting.

And those are just the finance workflows. Here’s what changes if you never touch a DCF in your life.

**Strategy and competitive analysis.** You have a spreadsheet of fifty competitors — product features, pricing tiers, market positioning, recent funding rounds. You tell Claude in Excel: score each competitor on six dimensions, weight by our strategic priorities, identify the three that matter most. Then you tell Claude in PowerPoint: build a competitive landscape deck with a positioning matrix, threat assessment by segment, and recommended strategic responses. Native diagrams — not screenshots. Editable quadrant charts. Process flows showing where each competitor is headed. The kind of deck a strategy consulting team produces over two weeks, built in an afternoon from data you already had.

**Sales enablement.** Your sales team sends the same ten-slide pitch to every prospect. You hand Claude the company’s CRM data and their last three earnings transcripts. Tell it: customize this pitch for a CFO audience at a mid-market manufacturing company. It rewrites the value propositions, swaps in industry-relevant case studies, adjusts the ROI projections to reflect manufacturing margins, and keeps your brand template intact. Every prospect gets a deck that looks like your team spent a day on it. The sales rep spent five minutes.

**HR and people analytics.** You export twelve months of employee survey data — 2,000 responses, freeform text and Likert scales, across eight departments. You tell Claude in Excel: analyze sentiment by department, identify the three strongest predictors of attrition risk, and build a summary dashboard. Then you tell Claude in PowerPoint: build a people strategy deck for the executive team — one slide per department, top risks flagged, recommended interventions. The CHRO gets a deck backed by actual data analysis, not a consultant’s interpolation from three focus groups.

**Project and program management.** You have a master tracker in Excel with 200 line items across twelve workstreams — owners, deadlines, status, dependencies, risk flags. You tell Claude: build a program status deck for the steering committee. It reads the tracker, identifies the three workstreams that are behind schedule, traces the dependency chains to show what’s blocked and why, and produces a deck with milestone timelines, risk heat maps, and a recommended resequencing plan. The PMO analyst who used to spend a day building this now spends that day on the actual project problems instead.

**The formula and data work nobody talks about.** Before you even get to the headline workflows, there’s the daily grind that Claude in Excel eliminates. Debugging a VLOOKUP chain that breaks when someone sorts a column. Writing a Power Query transformation to clean vendor data that arrives in a different format every month. Building conditional formatting rules that highlight exceptions without hiding the baseline. Tracing a circular reference across four tabs to find the one cell that’s causing it. This is the work that eats two to three hours a week for anyone who lives in spreadsheets — not analytical work, plumbing work. It’s the first thing Claude handles and the thing that frees up the most time before you even start on the big workflows.

Every one of these workflows exists today. Not next quarter. Not as a waitlist. Now.


## **The part everyone will miss: intelligence compounds across tools**

Here’s what none of the individual workflows above make obvious enough, and it’s the thing that matters most.

The time savings don’t add up. They multiply. Having Claude in Excel saves you time on modeling. Having Claude in PowerPoint saves you time on decks. Having Claude in both doesn’t save you twice the time — it eliminates an entire category of work that existed solely because the tools couldn’t talk to each other through a shared intelligence.

Think about what actually eats your week. It’s not building the model. It’s not building the deck. It’s the translation layer in between. You finish the analysis in Excel. Then you open PowerPoint and start re-explaining the same data to a different tool — reformatting numbers into charts, re-contextualizing findings into narrative, re-creating visual elements that represent what you already know. That translation cost — the time spent moving meaning between applications that don’t share context — is where most knowledge workers spend the majority of their production hours. Not thinking. Not analyzing. Translating.

When one intelligence spans both tools, the translation cost drops to zero. Claude doesn’t export data from Excel and import it into PowerPoint. It understands the data in Excel — what the numbers mean, which trends matter, what story they tell — and carries that understanding directly into the presentation. The chart it builds in PowerPoint isn’t a visualization of raw numbers. It’s a visualization of the insight the model already extracted from the analysis. The narrative on the slide isn’t boilerplate summary. It’s the same interpretation the model formed while building the model. Context flows through the pipeline intact. Meaning doesn’t get lost in the handoff, because there is no handoff.

Now extend that logic six months. Claude is already in Excel and PowerPoint. It’s in Slack, in project trackers, in databases through MCP connectors. As the integration surface expands, the context pipeline grows. The quarterly numbers in your spreadsheet become the board deck become the investor update email become the Slack summary for the team — one intelligence maintaining the full context at every step, producing consistent output across every tool, never losing the thread of what the data actually means.

This is the context layer. And it’s going to be enormous. Not the application layer — Microsoft owns that. Not the data layer — your databases own that. The context layer sits between them: the AI’s accumulated understanding of your data, your brand, your audience, your goals, your org’s way of communicating. Every time the model touches a new tool, the context layer gets richer. Every time it sees how your board deck differs from your team Slack update, it learns something about how your organization translates information for different audiences. That contextual understanding compounds across every tool it touches, and it compounds faster when the tools are connected through a shared intelligence rather than siloed behind separate interfaces.

The applications are containers. The data is the raw material. The context layer — the intelligence that understands what the data means and how to express it for every audience in every format — is where the value is accumulating. And unlike the application layer, which Microsoft has owned for decades and which barely changes year to year, the context layer improves with every model upgrade and every new tool integration. It’s the fastest-compounding asset in your technology stack, and most organizations haven’t realized it exists yet.


## **The upgrade that happens while you sleep**

This is what separates what happened this week from a normal product launch.

On Tuesday night, Claude in Excel ran on Opus 4.5 — a strong model, capable, useful. On Wednesday morning, it ran on Opus 4.6. Nobody installed anything. Nobody downloaded a patch. Nobody sat through a migration wizard. The spreadsheet looked exactly the same. But the intelligence inside it had leaped a generation — on Anthropic’s million-token retrieval benchmark (MRCR v2), Opus 4.6 scores 76% where the previous best scored 18.5%, a qualitative shift in how much context the model can actually hold and use. That means it can keep an entire multi-tab model in working memory and understand how every cell relates to every other cell.

Think about what that means for the next upgrade. Opus 4.7 is coming. So is 5.0. Each time a new model ships, every Claude-powered Excel and PowerPoint on Earth gets smarter overnight. The operating model that took ten minutes with Opus 4.6 might take five with 4.7. The pitch deck that needed forty minutes of back-and-forth might need fifteen. The quality of the reasoning improves. The depth of the analysis deepens. The output moves closer to what a senior person would produce — not because you learned a new tool, but because the tool learned on its own.

This is a fundamentally different upgrade cycle from anything the software industry has produced. Microsoft ships a new version of Office every few years. Feature updates land quarterly. The pace of improvement is set by the software company’s release schedule, its engineering priorities, its QA cycle. With Claude inside your tools, the pace of improvement is set by Anthropic’s model releases — and those are happening every few months, with capability jumps that would be measured in years by traditional software standards. The gap between Opus 4.5 and 4.6 included dramatically deeper context handling, nearly doubled reasoning scores, and the ability to coordinate agent teams. That’s not a quarterly update. That’s a generational leap compressed into a single quarter, and it made every Claude-powered tool on Earth smarter the moment it shipped.

Your mental model of what your tools can do is now permanently behind reality. The task Claude in Excel couldn’t handle last month, it handles now. The presentation quality that wasn’t sufficient in January is more than sufficient in February. And by April, both will have improved again. The assumption that you learn your tools once and they stay the same — that the thing you tested last quarter is the same thing that’s running today — is over. Your tools are getting smarter faster than you’re updating your expectations of them, and the gap between what you think they can do and what they actually can do is widening every quarter.

The practical consequence: you need to re-evaluate your workflows continuously. Not annually. Not when someone sends around a blog post. Continuously. Because the boundary between “tasks I do myself” and “tasks I delegate to the tool” is moving, and it’s moving in one direction, and it’s moving fast.


## **The dumb pipe**

I know the question on your mind: doesn’t Microsoft Copilot already do this?

Sort of. But the real answer leads somewhere more important than a feature comparison.

Copilot’s advantage is native integration. It’s built into the Microsoft 365 suite from the ground up. The UI is seamless. It understands the Office ecosystem — SharePoint, OneDrive, Teams — in a way that a third-party tool doesn’t. If your organization lives entirely within the Microsoft stack and wants the least friction possible, Copilot is the path of least resistance.

Claude’s advantages are reasoning depth, local file support, and the financial data connectors. Geoffrey Moore — the “Crossing the Chasm” author, one of the most respected technology strategists alive — published a comparison on LinkedIn that drew thousands of reactions from enterprise leaders. His assessment: Claude wins on the tasks that require genuine reasoning over complex, multi-step problems. Building a financial model from a set of assumptions. Debugging a formula chain across twelve tabs. Structuring an analysis that requires judgment about what matters, not just pattern-matching against previous templates. The local file support matters too — Copilot requires OneDrive for most of its functionality, which means your files live in Microsoft’s cloud. For organizations handling sensitive financial data, running analysis on local files without uploading them to a third party isn’t a convenience feature. It’s a compliance requirement.

But the Copilot comparison is the wrong frame for what’s actually happening. The real story is structural.

In September 2025, Microsoft added Claude models to M365 Copilot. Read that again. Microsoft — the company that invested $13 billion in OpenAI, that built Copilot on OpenAI’s models, that bet its entire AI strategy on a single provider — hedged by putting a competitor’s brain inside its own product. When the company that owns the application layer starts offering someone else’s intelligence inside it, that tells you where the value is migrating.

Microsoft is becoming a dumb pipe.

Not overnight. Not completely. But the pattern is unmistakable, and it mirrors what happened to every platform that got caught between a commoditizing interface and a rapidly improving capability layer. AT&T built the network. Then the network became a pipe for Google and Netflix. The value migrated from the carrier to the service. Browsers were supposed to be the platform. Then they became rendering engines for web applications. The value migrated from the container to what ran inside it.

Excel is a grid of cells. It’s been essentially the same grid for twenty years — new features at the margins, but the same fundamental tool. PowerPoint is a canvas for slides. Same story. The intelligence that now operates inside them leaps generations every few months. The application layer is frozen. The intelligence layer is compounding. And the value is migrating from the application to the intelligence, which is why Microsoft is hedging by offering every major AI model inside its own products — which is exactly what a dumb pipe does. It carries whatever traffic flows through it.

The implication for your organization: stop thinking about your tool choice and start thinking about your intelligence choice. The question isn’t “should we use Excel or Google Sheets?” It’s “which AI model powers our spreadsheet, and is it the best one for the work we do?” The application is a container. The intelligence is the value. And for the first time in the history of productivity software, those two things are chosen separately.


## **When artifacts are free, what’s worth doing?**

This is the section I’ve been building toward, because this is the part that should change how you invest your time — starting this week.

A full operating model used to cost a day of skilled analyst time. Now it costs ten minutes and a $20 subscription. A board deck built from real data used to require a day from someone who knows both the numbers and the narrative. Now it takes thirty minutes. A comparable company analysis used to eat an evening of pulling data and building tables. Now it’s a few minutes of describing what you want.

The cost of producing these artifacts — the models, the decks, the analyses — is collapsing toward zero. Not gradually. Not theoretically. In a handful of product releases. And every model upgrade accelerates the collapse.

So what happens when the artifacts are free?

The consulting model breaks. Not because consultants are unnecessary, but because the consulting business model — revenue equals time multiplied by expertise — depends on the time component being large. When a deliverable that billed at 40 hours of associate time can be produced in 40 minutes, the time component of the equation collapses, and with it the revenue model. McKinsey reported that 75% of its 43,000 employees were using their internal AI tool on a monthly basis by late 2025. They’re not doing this because it’s interesting. They’re doing it because if they don’t compress their own cost structure, someone with the same tools and lower overhead will undercut them on every engagement. The firms that built their businesses selling analysis are racing to redefine what they sell before the market reprices their output at the cost of inference tokens.

The correct response isn’t panic. It’s recognizing what becomes valuable when the artifacts are cheap.

Analysis is becoming a commodity. Judgment never will be. Knowing how to build a DCF is a skill that just got automated. Knowing which assumptions to stress-test, which scenarios to run, what story the numbers are actually telling — that’s judgment. And judgment is what clients pay for. It’s what boards need. It’s what separates a useful analysis from a technically correct one that misses the point.

The people who thrive in this environment aren’t the ones who build the best models. They’re the ones who know what question to ask before the model gets built. Who can look at a completed analysis and say: “This is technically right, but it’s answering the wrong question.” Who understand the business well enough to know which of the seventeen possible analyses is the one that actually drives a decision.

This is the strategic skill I keep coming back to: when production is free, the returns flow to the people who know what’s worth producing. Not more. Better. Not faster. Smarter. The ten-minute operating model is worthless if you’re modeling the wrong scenario. The thirty-minute board deck is worse than worthless if it tells a story that doesn’t match reality. The tool makes you faster. Only you can make sure it’s right.


## **The slop problem**

There’s an uncomfortable truth hiding inside all of this capability.

Every tool that makes it easy to produce excellent work also makes it easy to produce garbage. And we are about to drown in AI-generated garbage that looks professional.

A Stanford and BetterUp study published in Harvard Business Review found that 40% of 1,150 full-time workers had received AI-generated “workslop” from colleagues — technically competent, substantively empty. The estimated productivity cost: $186 per employee per month in time wasted processing work that sounds authoritative and says nothing. Fifty-three percent of recipients found it annoying. Twenty-two percent found it offensive — not because it was wrong, but because it wasted their time with the appearance of substance where none existed.

The board deck Claude builds in thirty minutes looks identical whether you spent an hour thinking about the strategy or whether you typed “make me a board deck about our Q1 results” and walked away. The format is clean. The charts are correct. The layout is professional. The difference between the two outputs — between insight and slop — is invisible to the tool. It’s only visible to you, and to the person receiving it.

This isn’t the adoption question I wrote about earlier — whether you rethink your workflow or just bolt AI onto the old one. This is a different problem. This is about whether you have the judgment to know which work should exist in the first place. The same capability that lets a thoughtful strategist produce a day’s work in ten minutes also lets a careless operator produce a week’s worth of polished nothing in an afternoon. The tool doesn’t know the difference. The tool will never know the difference. The difference is taste — the ability to kill work that looks professional but solves nothing. And that’s entirely on you.

Taste, in this context, isn’t an aesthetic preference. It’s the ability to distinguish between output that serves a purpose and output that merely exists. It’s knowing that a 40-slide deck isn’t better than a 10-slide deck. It’s knowing that the third scenario in your model is the one the board actually needs to see, and the other six are noise. It’s knowing when the analysis is done — when adding more data would dilute the signal rather than strengthen it.

What stands between your organization and AI slop is the same thing that has always stood between mediocre work and excellent work: the judgment of the people deciding what gets produced, what gets shared, and what gets acted on. The tool just raised the stakes, because the volume of output that’s possible went up by an order of magnitude while the ability to distinguish signal from noise stayed exactly the same.


## **The shift underneath**

I want to leave you with the implication I think matters most.

For thirty years, professional value has been built on execution skill. Can you build the model? Can you write the code? Can you design the presentation? Can you structure the analysis? These execution skills created the modern knowledge economy. They’re what universities teach, what hiring managers screen for, what career ladders reward.

The execution premium is evaporating. Not in five years. Now. The ten-minute operating model isn’t a preview of the future. It’s a product you can buy today for $20 a month, and it works. And the model powering it gets smarter every quarter while the price stays the same.

What’s not evaporating — what can’t evaporate — is the thinking that sits above execution. The ability to frame the right question. The strategic awareness to know which analysis matters. The taste to distinguish between output that drives a decision and output that fills a slide. The judgment to look at a technically perfect model and say “we’re modeling the wrong thing.”

When I built that operating model in ten minutes, the Goldman analyst didn’t compliment the formatting. He said it captured the right assumptions and told the right story. The model was a vehicle. The thinking was the value. Claude built the vehicle. I supplied the thinking. That division of labor — human judgment directing AI execution — is the new operating model for knowledge work. And the people who internalize it first will have an advantage that compounds every time the tools get better.

Because the tools will keep getting better. Every quarter. Overnight. Without you doing anything. The ten-minute model will become a two-minute model. The thirty-minute board deck will become a five-minute board deck. The cost of execution will keep falling, and the intelligence doing the execution will keep improving, and neither of those trends shows any sign of slowing down. The premium on judgment and taste will increase with every upgrade — because those are the only inputs the tools can’t supply and the only ones that don’t improve automatically with a model release.

General intelligence just moved into the tools you already use. It’s going to keep getting smarter. The question isn’t whether to adopt it. The question is whether your thinking is good enough to deserve what it produces.

[![](https://substackcdn.com/image/fetch/$s_!-Pfw!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0f3cddde-1973-4348-b8f8-3e9e14048d2b_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!-Pfw!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0f3cddde-1973-4348-b8f8-3e9e14048d2b_1024x1024.png)
