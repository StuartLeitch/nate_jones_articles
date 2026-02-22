---
title: "$185 billion is the down payment — the 4 skills that survive when agents code for months"
author: "Nate Jones"
published: 2026-02-14
url: https://natesnewsletter.substack.com/p/the-650-billion-infrastructure-bet
subtitle: "Watch now | The infrastructure that looked like a bubble six months ago now looks like a down payment. Here’s what changed and what it means for your career."
audience: everyone
scraped_at: 2026-02-22 15:12:25
---

Google just told investors they’re spending $185 billion on AI infrastructure in 2026. Alphabet shares fell as much as 7% in trading on February 5th.

Not because Wall Street thinks the number is too high. Because Wall Street is starting to realize it might not be high enough.

Alphabet reported Q4 earnings on February 4th — the same week a markdown file erased $285 billion in enterprise software market cap. The earnings themselves were immaculate. Revenue exceeded $400 billion for the first time in company history. EPS of $2.82 beat the $2.63 consensus (LSEG). Cloud revenue accelerated. Search held steady despite every AI-will-kill-Google prediction of the past three years. By every conventional measure, this was a company performing at the peak of its powers.

And then Sundar Pichai announced the capex number.

$175 to $185 billion. For a single year. That’s roughly double the $91 billion Google spent in 2025, which was itself a 74% increase over 2024. Analysts had been expecting around $120 billion. Google blew past that expectation by nearly 50%.

CFO Anat Ashkenazi broke down the allocation: approximately 60% on servers, 40% on data centers and networking equipment. Pichai described maintaining a “brutal pace” to compete in AI. The word choice was deliberate. This isn’t a company making a measured strategic investment. This is a company sprinting because it believes the cost of slowing down is existential.

The stock recovered most of its losses by Thursday’s close. But that initial drop told you what the market’s instinct was before the analysts had time to write notes. $185 billion sounds like too much money. It sounds reckless. It sounds like a company that has lost discipline, caught up in an arms race it can’t win.

The market’s instinct is wrong. And the speed at which it’s becoming obviously wrong is the real story.

**Here’s what’s inside:**

- **The narrative flip.** How AI agents destroyed the bubble thesis in a single week — and why the math that said “overhyped” six months ago now says “underbuilt.”
- **Infrastructure inversion.** The pattern from railroads to fiber to AWS — and the structural difference that means AI infrastructure builders won’t end up like the telecom companies that went bankrupt while YouTube got rich.
- **The inference gap.** Why agent workloads make chatbot-era infrastructure projections look like a rounding error, and what Ashkenazi’s 60/40 server split actually tells you.
- **The compressed window.** Why the platform-building timeline has collapsed from decades to months, and what that means for anyone waiting to see how this plays out.
- **The rails under your career.** Four things — maybe only four things — that survive when agents can code for months and review contracts autonomously.

Let me show you how the consensus flipped — and why the people who figured it out first have an edge that compounds from here.


## **[Grab the prompts](https://www.notion.so/product-templates/Infrastructure-Inversion-Prompt-Pack-3055a2ccb526808f87f5e0136e464fb9?source=copy_link)**

There are four prompts for this one — because reading about infrastructure inversions and actually inventorying your own position are two completely different activities, and most people do the first without ever doing the second.

The **Infrastructure Position Diagnostic** forces you to answer whether you’re a platform, a defensible tenant, or a vulnerable tenant — and what your actual dependency surface looks like when the rails shift underneath you.

The **Skill Depreciation Inventory** splits your current work into execution and judgment, then tells you which side of that line is appreciating. Most people discover their time allocation is inverted — they’re spending 70% of their hours on the skills that are depreciating fastest.

The **Window Compression Calculator** exists because “wait and see” feels like a strategy but is actually a bet that the window stays open longer than every historical precedent suggests.

And the **Value Capture Map** traces where the value you create actually flows — because in an infrastructure inversion, the question isn’t whether you’re productive. It’s whether you own any of the output.

These prompts are blunt. They will tell you things you’d rather not hear about where your leverage actually lives.


## **Six months ago this was a bubble**

Rewind to mid-2025. The dominant narrative in financial media was that AI infrastructure spending had decoupled from reality. Goldman Sachs published a widely-cited research note asking whether Big Tech was spending too much on AI with too little to show for it. Sequoia’s David Cahn wrote his “$600 billion question” analysis, pointing out that the total revenue of all AI companies combined couldn’t justify the infrastructure being built. Jim Covello at Goldman called generative AI “overhyped.” The Economist ran a cover on the AI bubble. Barron’s asked whether Nvidia was the next Cisco.

This wasn’t fringe skepticism. It was the consensus. And it was built on real numbers. Training runs cost hundreds of millions of dollars. AI products were impressive demos but hadn’t yet restructured any industry’s economics. ChatGPT was generating revenue but burning through compute faster than it could monetize. The math didn’t close. Every serious analyst could see it.

Then agents happened.

Not the concept of agents — people had been talking about AI agents for years. The actual deployment of agents into production workflows, consuming massive amounts of inference tokens and delivering value so obvious that the market couldn’t ignore it. Anthropic’s Claude Cowork shipped plugins that could triage legal contracts, automate compliance reviews, and generate audit summaries. The legal plugin was roughly 200 lines of structured markdown. It wiped 16% off Thomson Reuters in a single session. OpenAI launched Frontier, an enterprise agent platform, and signed HP, Intuit, Oracle, State Farm, and Uber as launch customers — not for demos, for production deployment. Coding agents at Cursor, Codex, and Claude Code crossed from “useful autocomplete” to “autonomously generating thousands of production commits.”

The agents didn’t just work. They consumed compute at a scale nobody had modeled. Every agent running a contract review is making dozens of inference calls. Every coding agent generating a thousand commits per hour is burning through tokens continuously, around the clock, at a rate that makes chatbot usage look like a rounding error. When you multiply that by enterprise-scale deployment across legal, finance, engineering, compliance, customer service — the inference demand curve goes vertical.

And just like that, the narrative flipped. Not gradually. In weeks. The question stopped being “is AI overhyped?” and started being “do we have enough compute for what’s about to happen?” The $285 billion SaaSpocalypse wasn’t just a repricing of software companies. It was the market absorbing, in real time, that AI agents are powerful enough to restructure entire industries — and that the infrastructure to run those agents at scale doesn’t exist yet.

Derek Thompson captured the shift with precision: the odds that AI is a bubble declined significantly, and the odds that we’re actually quite underbuilt for the necessary levels of inference went significantly up. You cannot simultaneously believe that AI agents are powerful enough to crash enterprise software and that the infrastructure spending to support those agents is excessive. Pick one.

The market picked. And now we’re watching what happens when the world’s largest companies all reach the same conclusion at the same time.


## **The scale of the bet**

Google isn’t alone. That’s the first thing to understand.

Amazon announced roughly $200 billion in 2026 capex. Microsoft is running at approximately $145 billion annualized. Meta guided $115 to $135 billion, driven by its Superintelligence Labs buildout. Even Oracle, which barely registered in cloud infrastructure five years ago, is deploying tens of billions.

Add it up. The five largest technology companies on Earth will spend somewhere between $650 and $700 billion on AI infrastructure in 2026 alone. Goldman Sachs projects the hyperscalers will spend $1.15 trillion cumulatively between 2025 and 2027 — more than double what they spent in the previous three years combined. Bloomberg ran the aggregate number with a headline that landed somewhere between awe and alarm: “A Staggering $650 Billion.”

These are numbers that don’t fit neatly into existing frameworks for evaluating corporate investment. Microsoft’s capital intensity has reached 45% of revenue — historically unthinkable for a software company. Amazon’s capex has already exceeded total annual free cash flow, forcing them to the debt markets. Google is about to spend more on infrastructure in a single year than the GDP of Ukraine.

Google isn’t just spending cash reserves — on February 9th they issued $20 billion in senior unsecured notes, later boosted to over $30 billion, including a 40-year tranche and a £1 billion century bond. When a company sitting on $100 billion in cash starts borrowing at this scale, they’re not hedging. They’re accelerating.

The natural reaction is that this must be a bubble. And six months ago, that reaction would have been defensible.

It isn’t anymore.


## **The case for panic (and why it expired)**

The bear case wasn’t stupid. It just aged out.

OpenAI’s annual recurring revenue hit $20 billion in 2025 — impressive, but that’s the largest AI company in the world, and its revenue represents roughly 3% of the infrastructure investment being made on its behalf. The math doesn’t close. Not this year. Probably not next year either. Every previous infrastructure boom that looked like this — spending wildly ahead of revenue — ended in tears for someone. The bears had historical precedent and they had arithmetic on their side.

But the conclusion they drew — that the spending is premature, that we’re in a bubble — died this week. The SaaSpocalypse was the proof of demand. Not projected or theoretical demand — revealed demand, priced by the market in real time, $285 billion worth of conviction that AI agents are restructuring enterprise economics right now.

And the enterprise adoption curve confirmed it with hard numbers. Anthropic went from fewer than 1,000 business customers two years ago to over 300,000 by September 2025, reaching 44% enterprise penetration by January 2026. OpenAI’s revenue tripled. Sarah Friar, their CFO, said enterprise now represents roughly 40% of the business, targeting 50% by end of 2026. And on February 5th — the day after Google’s capex announcement — OpenAI launched Frontier, an enterprise agent platform, and signed HP, Intuit, Oracle, State Farm, Thermo Fisher, and Uber as launch customers for deployment into live workflows. The same week the SaaS repricing wiped out a quarter-trillion in market cap, Fortune 500 companies were signing contracts to deploy the agents that caused it.

The bears were making the right argument six months too late.


## **Infrastructure inversion: the pattern nobody learns**

Every major economic era begins the same way. Massive overbuilding of infrastructure. Investor panic. The infrastructure looks like a catastrophic misallocation of capital. And then — a few years after the crash, sometimes a decade — someone figures out what the infrastructure is actually for. It turns out to be for something nobody who funded the construction ever imagined.

The railroads did this first. Between 1865 and 1873, American railroad mileage doubled — from 35,000 miles to over 70,000. Railroad stocks and bonds ballooned to $10.6 billion, nearly ten times the national debt. When Jay Cooke & Company collapsed in September 1873, it triggered a panic that drove 121 railroads into bankruptcy and took down 18,000 businesses. Five years of depression followed.

Then Gustavus Swift and Philip Armour figured out refrigerated railroad cars. Suddenly you could ship fresh meat from Chicago to New York. Then to small towns across the country. A national market for perishable goods — something that had literally never existed in human history — emerged because the rail infrastructure was already there, sitting idle, available at a fraction of its construction cost. Sears built the first great mail-order retail business on the same cheap rail network. The railroads went bankrupt. The economy they enabled was the largest the world had ever seen.

Fiber optics repeated the pattern a century later. Between 1996 and 2001, telecom companies issued over $500 billion in bonds and laid 80 to 90 million miles of cable. When the bubble burst, the wreckage was staggering. Global Crossing. WorldCom. A trillion dollars in debt written off. Ninety-five percent of installed fiber sitting dark.

And then YouTube launched in 2005 on bandwidth that cost almost nothing. Netflix pivoted from mailing DVDs to streaming in 2007, because bandwidth had collapsed in price. AWS launched in 2006 and built the cloud computing industry on top of infrastructure the telecom companies had spent half a trillion dollars building and then abandoned. The fiber companies went bankrupt. The economy they enabled — streaming, cloud, the entire modern internet — became the largest in human history.

AWS itself is the most recent iteration. Amazon launched S3 in March 2006 and EC2 five months later. For six years, the revenue was modest. Analysts questioned the investment. Bezos was criticized for prioritizing infrastructure over earnings. The returns didn’t become visible until 2013, when AWS crossed $3 billion in revenue with gross margins over 80%. By then, the companies AWS had enabled — Airbnb, founded 2008; Uber, founded 2009; Stripe, founded 2010 — had proved you could build billion-dollar businesses on cloud infrastructure without owning a single server.

The infrastructure wasn’t the product. It was the platform. And the platform enabled companies the original investors never imagined.

This is the pattern: massive investment, crash, discovery. The infrastructure is never built for the thing that makes it valuable. It’s built for what the builders can imagine. It becomes valuable for what the next generation of builders imagines.

The telecom companies that laid the fiber didn’t profit from YouTube. The railroad financiers who went under didn’t profit from Sears. The pattern’s usual lesson is brutal for infrastructure builders: you pour the foundation, someone else builds the house.

But this cycle has a structural difference that changes the math, and almost nobody is talking about it.

Railroads were dumb pipes. Fiber was a dumb pipe. AWS was a slightly smarter pipe — Amazon sold generic compute and storage, and the intelligence lived in the applications built on top. The infrastructure builders captured hosting fees. The application builders captured the value.

AI infrastructure isn’t a dumb pipe. Google, Anthropic, OpenAI — they’re not selling bandwidth or storage. They’re selling intelligence. Every inference call is a purchase of cognitive capability. The model is the product, and the infrastructure exists to serve the model at scale. When an agent reviews a contract or writes code or manages a supply chain, the value it delivers flows directly through the model provider’s API. The infrastructure and the intelligence are vertically integrated in a way that railroads and fiber never were.

This means the companies building AI infrastructure are positioned to capture value from the applications built on top — not just hosting fees, but a share of the actual cognitive work those applications perform. That’s a fundamentally different economic structure than any previous infrastructure inversion. It doesn’t guarantee these companies will win. But it means the analogy to “telecom companies that laid fiber and then went bankrupt while YouTube got rich” is misleading. The model makers aren’t laying dumb cable. They’re selling the thing that makes the cable valuable.


## **The inference gap**

There’s a distinction in the AI infrastructure conversation that most observers miss, and it’s the key to understanding why the bubble-to-underbuilt narrative flipped so fast.

The first phase of AI infrastructure spending — 2023 through mid-2025 — was about training. Building massive clusters of GPUs to train foundation models. Training is expensive but bursty: you need enormous compute for months, and then the model is done. The investment is front-loaded. This is the phase the bears were analyzing when they called it a bubble, and their math was correct: you don’t need $650 billion a year to train models.

But the next phase — the one we just entered — is about inference. Running those trained models at scale, continuously, for millions of users and millions of AI agents, 24 hours a day, 7 days a week. Inference is cheaper per unit but it never stops. And agents changed the inference math in a way that nobody — not the bulls, not the bears, not the hyperscalers themselves — had fully priced in.

A human using ChatGPT generates a modest inference workload. They type a question, wait for a response, read it, maybe ask a follow-up. Minutes between requests. Modest token consumption.

An AI agent autonomously reviewing contracts generates inference continuously. It reads the document, cross-references clause libraries, checks compliance databases, generates summaries, flags exceptions, routes to human reviewers — and then moves to the next contract without pausing. One agent doing the work of ten paralegals, consuming tokens around the clock, at a rate that makes chatbot usage look like dial-up.

Now multiply that by every workflow the SaaSpocalypse said is about to get automated. Contract review. Financial auditing. Data analysis. CRM management. Compliance checking. Code generation. Customer service. Each of those workflows, when performed by agents instead of humans, requires continuous inference compute. And the enterprises signing up for OpenAI Frontier and Claude Cowork aren’t deploying one agent. They’re deploying fleets.

This is why the narrative flipped so violently. The bears were right that $650 billion is insane if you’re building training clusters for chatbots. They were wrong because the actual demand is inference for agents, and agents consume compute at a scale that makes training look like a rounding error. Ashkenazi’s 60/40 split — 60% servers, 40% data centers — tells you Google understands this. They’re not building training clusters. They’re building inference capacity for a world where AI agents are the primary consumers of compute.

And even that framing understates the gap. Fidji Simo, OpenAI’s CEO of Applications, said something this week that most people glossed over: “We spent months integrating… and we didn’t even get what we wanted.” The CEO of Applications at the most valuable AI company on Earth, saying enterprise AI integration is harder than expected. The models are good enough. The infrastructure to connect AI agents to enterprise systems isn’t. The plumbing isn’t there. The connectors aren’t there. The security layers aren’t there. Demand is outrunning the plumbing, and the plumbing is exactly what the $650 billion is building.


## **The window is compressed**

Every infrastructure inversion has a window — usually three to seven years — where the infrastructure is being built and the companies that will eventually use it are just getting started. The companies that build during that window become the platforms. The companies that wait become tenants.

Amazon built AWS between 2003 and 2006 and had the dominant cloud platform before most enterprises knew they needed one. The companies that waited for cloud to “prove itself” ended up paying Amazon’s margins for the next twenty years.

That window is open right now for AI infrastructure. But the timeline is compressed in a way that should concern anyone who thinks they can wait.

Railroads took twenty years from overbuild to the economy that justified them. Fiber took ten. AWS took six. The current cycle is moving at roughly eighteen months — because the demand signal didn’t take years to arrive. It arrived in a single week, in the form of the largest single-week repricing in enterprise software history and a set of Fortune 500 agent deployments that proved enterprise demand is real, immediate, and accelerating.

Google’s $185 billion makes sense when you understand this compression. They’re not spending too much. They’re spending at the pace required to build the platform layer before someone else does. The same is true for Amazon, Microsoft, and Meta. None of them can afford to wait because the lesson of every prior infrastructure inversion is that the platform builders capture the economics of everything built on top. Miss the window, and you’re renting someone else’s infrastructure for the next decade.

The companies that look like they’re burning cash in 2026 will look like they were laying the foundation in 2028. The companies that showed “discipline” by spending less will look like they missed the most important infrastructure build since cloud computing.

The empires that endure aren’t the ones that discover the new economy. They’re the ones that own the rails.


## **Where this goes at speed**

So where does the infrastructure actually go? What gets run on it? The honest answer requires taking the current trajectory seriously, which most people are not doing because the trajectory is uncomfortable.

Code proved to be the breakthrough application for AI agents, and the reason is worth understanding because it tells you where everything else is heading. Code is the one domain where an agent’s output is immediately and objectively verifiable. You run it. It either works or it doesn’t. That tight feedback loop — generate, test, fix, generate again — is exactly the kind of iterative cycle that agents excel at. There’s no ambiguity about quality. No subjectivity. No waiting for a human to evaluate whether the output is good enough. The agent can evaluate its own work, at machine speed, and improve.

That’s why coding agents crossed from useful to transformative before agents in any other domain. Cursor is generating a thousand production commits per hour. StrongDM published a framework where code is written and reviewed entirely by agents. A researcher at OpenAI spent $10,000 on Codex tokens and automated his entire research workflow. These aren’t experiments. These are production systems, running now, generating real output that ships to real users.

Today, coding agents work in bursts — an hour here, a few hours there, guided and redirected by humans who set the direction and evaluate the results. But the trajectory is clear. Context windows are expanding. Working memory is multiplying. The ability of an agent to hold an entire codebase in its head and reason across it coherently is improving on a timeline measured in weeks, not years. Opus 4.6 5x’d working memory in a single week. If that pace holds — and there’s no evidence it’s decelerating — by the end of 2026 we’re looking at agents that can sustain autonomous coding runs for days. Possibly weeks. Possibly months.

Think about what that means for infrastructure demand. An agent coding autonomously for a month, continuously generating and testing and refining, is consuming inference compute 24 hours a day at a volume that no analyst model has accounted for. Multiply that by every enterprise that decides to build custom software instead of renting SaaS — and the SaaSpocalypse just gave them a very good reason to consider it — and the inference demand curve doesn’t just go vertical. It goes exponential.

And code is just the domain where the feedback loop closed first. Legal analysis is next — contract review has clear success criteria and structured output. Financial auditing. Medical diagnostics. Engineering design. Every domain where output quality can be systematically evaluated is a domain where agents will cross from useful to autonomous on a timeline that is compressing faster than anyone planned for. The infrastructure that looks like overbuild right now is being sized for the chatbot era. The agentic era will make it look like a down payment.


## **The rails under your career**

The infrastructure inversion pattern plays out at every scale, including the individual. And the question it forces — at every scale — is the same: what do you actually have that’s valuable when the infrastructure shifts underneath you?

Google is spending $185 billion because they’ve calculated that the cost of underbuilding is existential. Not risky. Existential. They’d rather be wrong and have spent too much than be right and have spent too little, because in an infrastructure inversion, the penalty for underbuilding is permanent. You don’t get to catch up later. The window closes.

Your career works the same way. And the question you need to answer honestly is: what human skills survive when agents can code for months, review contracts autonomously, and generate production-quality work at machine speed?

Four things. Maybe only four things.

**Taste.** The ability to look at what an agent produces and know — not analytically, not by checklist, but by hard-won instinct — whether it’s right. Whether it’s good. Whether it solves the actual problem or just the stated problem. Agents can generate enormous volumes of competent output. They cannot yet tell the difference between competent and excellent, between technically correct and strategically right. The people who can make that distinction — who have refined their judgment through years of doing the work — become exponentially more valuable when the cost of generating options drops to zero. Taste is the filter. Without it, you drown in competent mediocrity.

**Exquisite domain judgment.** Not general intelligence — agents have that in abundance. The specific, contextual, hard-to-articulate understanding of how a particular domain actually works. The lawyer who knows which clauses actually matter in a negotiation, not just which clauses exist. The engineer who knows which architectural decisions will create pain in eighteen months. The executive who knows which market signals are noise and which are structural. This knowledge is accumulated over years and encoded in intuition that agents can approximate but not yet replicate, because it depends on experience that isn’t in any training set.

**Phenomenal ramp.** The ability to learn fast when everything is evolving fast. Not “I took a course on AI” learning. The kind of learning where you’re using the tools daily, your mental model is updating weekly, and you’re comfortable operating at the frontier of capability even when the frontier moved since last Tuesday. In a world where Opus 4.6 5x’s working memory in a week, where Codex ships a desktop app, where Claude Cowork goes from interesting tool to market-moving event in 48 hours — the ability to absorb change at speed and stay current isn’t a nice-to-have. It’s the meta-skill that makes all the other skills usable. The AI cannot keep up with itself. The humans who can keep up with the AI have an edge that compounds daily.

**Relentless honesty about where value is moving.** This is the hardest one, because it requires looking at your own work and asking which parts of it are actually valuable and which parts are execution that an agent will handle better, cheaper, and faster than you can. Most people don’t want to do this inventory. It’s threatening. It requires admitting that some of the skills you spent years building are depreciating. But the people who do the inventory — who are honest about which parts of their work are taste and judgment and which parts are execution and process — are the ones who can reallocate their time toward the things that still matter before the market forces the reallocation for them.

If you’re waiting for AI to “settle down” before investing serious time in these skills — before rebuilding your professional infrastructure around what actually survives the transition — you’re making the same bet as the companies that waited for cloud computing to “prove itself” in 2008. They spent a decade renting Amazon’s infrastructure at Amazon’s margins. You’ll spend the equivalent period paying a learning-curve tax in a labor market that has already moved on, working for people who figured this out while you were waiting for stability.

Stability isn’t coming. The pace is accelerating, not settling. And the gap between “I use AI tools” and “I’ve rebuilt how I work around what AI makes possible” is the individual version of the gap between “we added AI features to our SaaS product” and “we rebuilt our architecture to be agentic-first.” The first approach feels productive. The second approach is what actually changes outcomes.


## **Year one**

Six months ago the consensus was that AI infrastructure spending was a bubble. The math didn’t close. The demos were impressive but the economics weren’t there. Serious people made serious arguments that the hyperscalers had lost discipline, that the spending was ahead of demand by years, that this was fiber optics all over again.

Then agents started running. They consumed inference compute at a volume nobody’s models had accounted for. They delivered value so obvious the market repriced $285 billion in 48 hours. And the consensus flipped — not gradually, not over quarters, but in weeks — from “this is overhyped” to “we don’t have enough compute for what’s about to happen.”

That’s the story of this week. Not Google’s earnings. Not the stock price. The moment the world absorbed that agents are real, that they’re eating massive amounts of tokens, that they’re delivering enormous value, and that the infrastructure to support them at the scale they demand doesn’t exist yet.

Google is spending $185 billion. Amazon is spending $200 billion. A trillion dollars will pour into AI infrastructure by 2027. Some of that money will be wasted. Some of the companies deploying it will fail to capture the returns. But unlike every previous infrastructure inversion — unlike railroads, unlike fiber, unlike even AWS — the companies building this infrastructure aren’t laying dumb pipes. They’re selling intelligence. And the demand for intelligence, it turns out, is the one resource whose consumption scales with how good it gets.

The railroad barons couldn’t have imagined Sears. The telecom engineers couldn’t have imagined Netflix. But the model makers can see exactly what’s being built on their infrastructure, because every inference call runs through their API. The agents are the product. The infrastructure exists to serve the agents. And the agents are the foundation of everything that comes next.

This is an agentic world. This is year one.

The $185 billion isn’t reckless. It isn’t even aggressive. It’s the opening investment in an economy that doesn’t fully exist yet but that announced its arrival this week with $285 billion in conviction. The market looked at Google’s capex number and saw a company spending too much. The market will look back at 2026 the way we look back at the early AWS data centers, or the first transcontinental railroad, or the fiber optic cables lying dark under the Atlantic.

The foundation of everything that came next. Laid in the year that agents proved they were real.

[![](https://substackcdn.com/image/fetch/$s_!PHHE!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc1b90c49-a6d2-43a4-a11f-b627035137eb_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!PHHE!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc1b90c49-a6d2-43a4-a11f-b627035137eb_1024x1024.png)
