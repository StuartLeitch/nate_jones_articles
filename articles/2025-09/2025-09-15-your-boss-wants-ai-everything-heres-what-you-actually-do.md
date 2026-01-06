---
title: "Your Boss Wants AI Everything. Here's What You Actually Do."
author: "Nate Jones"
published: 2025-09-15
url: https://natesnewsletter.substack.com/p/the-real-talk-guide-to-using-ai-agents
audience: everyone
scraped_at: 2026-01-05 19:18:04
---

"Nate, I need an AI project for the board this quarter. I gotta have one. Can I use it for the quarterly sales reports?"

"Nate, my boss told me to do AI but I don't think he knows what he's asking for. What do I do?"

"Nate, where do I actually use AI agents? I hear so much about them and I don't want to fall for the hype."

These questions all boil down to one thing: we don't know how to match problems to solutions anymore because AI is drowning out common sense.

I get messages like these every single day. Smart people being asked to force AI into places it doesn't belong. Engineers who know better but can't articulate why ChatGPT is the wrong tool for their reporting problem. Product managers trying to navigate between board pressure and technical reality.

After years of watching this pattern—first with big data, then machine learning, now with generative AI—I've developed a horse sense about when to use what tool along with executive talk tracks that help me communicate what I mean to anyone who needs to listen.

This week I’m sharing all of it here, so you’re equipped to actually know when to use AI Agents, when to use Generative AI, and so you know how to push back when simpler tools work better.

What you're getting:

1. A four-category framework that instantly clarifies which tool fits which problem
2. The exact scripts I use when executives demand AI for problems that need simpler solutions
3. Real examples from companies like Walmart, JPMorgan Chase, and BMW showing what actually works
4. A simple decision tree you can use in any meeting to determine the right approach
5. The risk-adjusted ROI calculations that make the business case clear

The framework doesn’t take an engineering degree to understand, I promise. Once you get it, you'll spot AI washing instantly, know when agents actually make sense, and save yourself and your team from expensive mistakes that should have been cheap wins.

Most importantly, you'll finally have the confidence to make the right call. When someone demands AI for that quarterly sales report, you won't just know they're wrong—you'll know exactly why, what to propose instead, and how to explain it in terms they'll understand. That's the difference between being right and being effective.


# Your Boss Wants AI Everything. Here's What You Actually Do.

Your CEO watched a ChatGPT demo last week. Now they want AI in production by Monday. Meanwhile, your actual problem is that the monthly sales reports take too long to generate. Sound familiar?

I've been watching this pattern play out across companies for the past two years. Smart executives who should know better are demanding AI solutions for problems that don't need them. Engineers are either rolling their eyes or gleefully overengineering systems that will cost ten times what they should. And somewhere in the middle, actual business problems aren't getting solved.

The core issue isn't that people don't understand AI. It's that they don't understand problems. They've been handed a shiny new hammer and now everything looks like a nail. But here's the thing: most business problems aren't nails. They're screws, or bolts, or sometimes just things that need to be left alone.

After twenty years in tech and countless conversations with teams trying to navigate this mess, I've developed a framework that actually works. It's not complicated. It doesn't require a PhD. It just requires you to think clearly about what problem you're actually trying to solve.


## The Four Categories That Matter

Every data and insights problem falls into one of four buckets. Not five, not ten, not "it depends." Four. Once you understand which bucket your problem belongs in, the solution becomes obvious.

The first bucket is plain old data processing. If you need to sum up monthly sales by region, that's data processing. If you need to clean messy customer records, that's data processing. If you're calculating payment volumes for the last quarter, that's data processing. The test is simple: can you write it as x plus y equals z? Then it's data processing. Use SQL. Use a spreadsheet. Use anything except AI.

Look at what Shopify merchants actually need—revenue tracking by product category across time periods. That's a SQL query. When banks match transactions across systems for monthly close, that's data processing. When manufacturing companies calculate stock levels and reorder points, that's basic math. Healthcare providers counting patient visits by insurance type for compliance reporting? Also just counting. CRM systems aggregating deal values by sales rep and territory? Still just aggregation.

I cannot emphasize this enough. If your problem has deterministic rules and you're considering AI, you're about to waste enormous amounts of time and money. A SQL query that takes two hours to write will outperform an AI system that takes two months to build and breaks randomly.

The second bucket is traditional machine learning. This one has almost disappeared from conversations, which is insane because we spent decades perfecting it. You use traditional ML when you have rich historical data and need to predict a specific outcome. Predicting customer churn? Traditional ML. Forecasting seasonal demand? Traditional ML. Detecting fraud patterns? Traditional ML.

JPMorgan Chase doesn't use ChatGPT to assess loan default risk. They use ML models trained on payment history. General Electric monitors turbine sensors to predict equipment failures before they happen—that's pattern recognition on structured data, not generative AI. Walmart forecasts demand for over 70 million SKUs using historical sales, weather, and economic data. BMW's production lines detect manufacturing defects using computer vision models that have been trained on thousands of examples of good and bad parts. Airlines and hotels optimize pricing based on demand patterns, seasonality, and competitor data through traditional ML algorithms that have been refined for decades. Progressive analyzes driving patterns to calculate personalized auto insurance premiums using telemetry data fed into predictive models, not large language models.

The key distinction is that you're optimizing for a single variable using structured data. You have clear success metrics. You can measure accuracy. The model either works or it doesn't. No hallucinations, no creative interpretations, just pattern recognition applied to structured problems.

The third bucket is generative AI. This is where large language models live. You use this when you need to generate novel content: text, images, code. When you're summarizing documents, translating languages, or drafting customer responses, generative AI makes sense. But—and this is crucial—it only makes sense if the value it provides is at least 10x what you could get from simpler solutions.

Zendesk's Answer Bot generates contextual responses from knowledge bases and reduces ticket volume by 30%. That's real value. Goldman Sachs uses an internal AI assistant to proofread emails and summarize research documents—tasks that would take humans hours. GitHub Copilot helps developers write code 55% faster by suggesting completions. Orange telecom automatically generates targeted advertising materials based on customer segmentation. Law firms use AI to summarize case law and generate initial contract drafts. E-commerce platforms generate thousands of product descriptions from images and specifications.

Why 10x? Because generative AI is expensive. Not just in compute costs, though those add up fast. It's expensive in maintenance, in handling edge cases, in dealing with hallucinations. If you're not getting massive value from it, you're lighting money on fire.

The fourth bucket is AI agents. These handle dynamic, multi-step workflows with decision points. An agent that books conference rooms, handles conflicts, and notifies attendees—that's an agent problem. Not because it's cool, but because it requires autonomous decision-making across multiple systems.

Real agent use cases are rarer than vendors want you to believe. Customer service orchestration that routes tickets, escalates issues, and follows up automatically might be an agent problem if the routing logic is complex enough. Supply chain systems that monitor inventory, place orders, negotiate with suppliers, and adjust logistics are getting into agent territory. Financial trading systems that analyze market conditions, execute trades, and manage risk across portfolios have been using agent-like architectures for years. IT operations that detect system issues, diagnose root causes, and implement fixes automatically are moving toward agent systems. Sales process automation that qualifies leads, schedules demos, sends follow-ups, and updates CRM records could benefit from agents if the workflow is sufficiently complex. Facility management systems that coordinate maintenance, book resources, manage access, and optimize building operations represent the kind of multi-system orchestration where agents make sense.

But notice the pattern. These are all cases where you need autonomous decision-making across multiple systems with complex, dynamic logic. If your "agent" is just following a flowchart, you don't need an agent. You need better workflow software.

---


### 📋 **Role-Specific Sidebar: For CTOs**

**Your Decision Framework:** Will this create technical debt or simplify operations? Do we have the talent to maintain this complexity level? What's the blast radius if this fails? Does this advance our core technology capabilities?

**When to Push Back:** If the solution requires more engineering resources than the problem merits, or if it introduces systemic risk for marginal gains.

---


## The Power Law Nobody Talks About

Here's what most people miss: these categories don't scale linearly. If basic data processing gives you 1x value, traditional ML gives you 10x, generative AI gives you 100x, and agents give you 1000x. But the costs scale the same way. The maintenance burden scales the same way. The talent requirements scale the same way.

This isn't a ladder where you climb to the highest rung. It's a toolkit where you pick the simplest tool that solves your problem. Most problems need a screwdriver, not a laser cutter.

I've watched companies build AI agents to generate reports that could be handled by a cron job running SQL. They spent six months and hundreds of thousands of dollars to solve a problem that needed two days and a junior developer. The report wasn't any better. It was actually worse because it would occasionally hallucinate numbers.

The talent problem compounds this exponentially. The same person who can write SQL queries for data processing usually can't build production ML models. The engineer who can tune traditional ML models might not understand the complexities of prompt engineering and managing hallucinations in generative AI. And the number of people who can actually build reliable agent systems? Tiny.

Companies keep asking their existing teams to jump three levels of complexity overnight. You wouldn't ask a carpenter to suddenly become an electrical engineer, but that's essentially what happens when you tell your data analyst to build an AI agent system.

---


### 🎯 **Role-Specific Sidebar: For Product Managers**

**Your Evaluation Criteria:** Does this actually solve a user problem or just showcase technology? Can we measure improvement objectively? Is this a feature or a competitive advantage? Does this fit our product narrative or create confusion?

**PM Reality Check:** If you can't explain the value proposition in one sentence, the solution is probably too complex.

---


## How to Actually Think About This

Developing what engineers call "taste" isn't mystical. It's pattern recognition. When someone describes a problem to you, you should immediately be categorizing it. Are there deterministic rules? Data processing. Need to predict an outcome from historical data? Traditional ML. Need to generate content? Maybe generative AI, if the value justifies it. Need autonomous multi-step orchestration? Maybe agents, but probably not.

The "probably not" is important. In my experience, 90% of problems presented as agent problems aren't. They're workflow problems that need better human processes. Or they're automation problems that need traditional programming. The number of genuine agent use cases is smaller than vendors want you to believe.

Amazon's "Just Walk Out" stores are the perfect example. They claimed it was AI-powered checkout. It was actually people in India watching cameras and manually tracking purchases. That's not an AI failure. That's a fundamental misunderstanding of what problems AI can actually solve.

This kind of AI washing is everywhere. Vendors claim proprietary AI without technical specifics. They promise immediate deployment without customization periods. They're reluctant to discuss error rates or accuracy metrics. There's no observable AI decision-making in their interface. When you see these red flags, you're probably looking at humans doing the work while the company claims it's AI.

Beyond recognizing AI washing, you need to understand how different approaches fail. Data processing fails with bad logic or incorrect formulas, but you can unit test for that and fix it quickly. Traditional ML fails through model drift and distribution shift, which you can detect through performance monitoring and handle with retraining. Generative AI fails through hallucinations and inconsistent outputs, requiring human review and fact-checking systems. Agent failures cascade—they create infinite loops and compounding errors that can be catastrophic without proper safeguards.

The data maturity of your organization determines what's even possible. Traditional ML needs hundreds to thousands of examples while GenAI can sometimes work with dozens. Structured data favors ML while unstructured multi-modal data suits GenAI. Real-time requirements often eliminate complex AI approaches entirely. Poor data quality kills ML projects, though GenAI can sometimes work around gaps.

Your organizational readiness matters as much as technical capability. More sophisticated AI requires more organizational adaptation. Regulated industries may need traditional approaches despite AI capabilities. The total cost of ownership includes maintenance, monitoring, and iteration that most budgets don't account for. Change management becomes exponentially harder as you add AI complexity.

I use a risk-adjusted ROI framework that refines my basic 10x rule. Data processing only needs 2x improvement to justify investment because the risk is low. Traditional ML needs 5x improvement to account for model drift. GenAI requires that 10x improvement because of hallucination risk. Agents need 20x improvement to justify the risk of cascading failures.

---


### ⚙️ **Role-Specific Sidebar: For Engineering Leaders**

**Your Technical Assessment:** How much architectural complexity can the team handle? Can we debug and monitor this effectively? What breaks, and how do we detect and recover? Do we have the skills to maintain this properly?

**Engineering Wisdom:** The best code is no code. The best AI is no AI. Start with the simplest solution that could possibly work.

---


## The Scripts That Actually Work

When your VP demands ChatGPT for the quarterly report, you need to reframe the conversation around value, time, and cost. Don't just say no. Present options with clear trade-offs.

Tell them you've analyzed three approaches. With a data pipeline, it's two days to build, $500 total cost, 100% accuracy on all known metrics. You can pull data from Salesforce, Google Analytics, and your financial system, create automated charts, and have it running reliably by Friday with all standard KPIs plus trend analysis. If they want predictive insights about next quarter, you can add ML models for demand forecasting and churn prediction—that's an additional three weeks with your data science team, roughly $15,000 in resources, and about 85% accuracy on predictions initially that you'll need to iterate to improve. For text summaries and insights using generative AI, you're looking at a week to prototype, then three to four months to handle hallucinations and fact-checking, plus $2,000 monthly in compute costs. The challenge is ensuring accuracy since AI might generate plausible-sounding insights that aren't actually supported by your data. You recommend starting with option one because it delivers reliable results immediately, and if the predictive insights prove valuable, you can add the ML models as a fast follow.

When your CEO announces they want AI agents handling 95% of customer support by next month, you need a different approach. Express enthusiasm for the vision of reducing support burden, then show them a realistic path that actually gets there. Phase one is smart routing using simple keyword matching and category classification to route tickets to the right teams—two weeks of work that reduces resolution time by 40% without any AI. Phase two adds traditional search and FAQ matching for common issues since your data shows 60% of tickets are repeat questions that could be deflected with better self-service. Phase three, once you have clean data from the first two phases, introduces AI that drafts responses for agents to review and send, typically handling another 25% of volume while maintaining quality. Phase four, only after proving accuracy in phase three, lets AI send responses directly for the most straightforward cases. The difference between this approach and jumping straight to autonomous agents is success rate—you'll hit 95% automation eventually, but without the horror stories of AI giving wrong answers to angry customers.

When your CMO says competitors are using AI for market analysis and you need an AI system that monitors everything and gives strategic insights, you need to cut through the hype. Explain that most "AI competitive intelligence" tools are actually web scraping with basic sentiment analysis—that's data processing, not AI, and you can build it for 90% less cost. What you actually need is one week to set up monitoring for competitor websites, press releases, job postings, and social media using web scraping and RSS feeds. Two weeks to build an analysis pipeline that categorizes and visualizes trends, tracking pricing changes, product launches, and hiring patterns automatically. One week for smart alerts that notify you when significant changes happen. AI only adds value if you want to process unstructured content like earnings call transcripts or analyze sentiment in customer reviews at scale, but you should start with structured monitoring first since that gives you 80% of the insight for 20% of the cost. The reality check is that competitive advantage comes from executing better than competitors, not from monitoring them more sophisticatedly.

---


### 💼 **Role-Specific Sidebar: For Business Leaders**

**Your Strategic Questions:** When do we break even on this investment? Does this create sustainable differentiation? What's the downside if this doesn't work? What else could we do with these resources?

**Executive Reality:** The companies winning with AI are using it strategically, not universally. They pick their spots.

---


## The Industry Reality Check

Healthcare talks endlessly about AI diagnostics, but look at what actually works. Patient appointment scheduling and insurance eligibility verification remain data processing problems. Predicting readmission risk based on vitals and medical history uses traditional ML that's been working for years. Summarizing patient charts and generating initial diagnostic notes is where generative AI starts to make sense. Coordinating care between specialists, scheduling follow-ups, and managing referrals involves complex workflows that might benefit from agents, but most hospitals are nowhere near ready for that level of automation.

Financial services tells a similar story. Daily transaction reconciliation and regulatory reporting is just data processing, despite vendor claims otherwise. Credit scoring models and algorithmic trading strategies have used traditional ML for decades—JPMorgan Chase isn't suddenly switching to ChatGPT for loan decisions. When Goldman Sachs uses generative AI, it's for summarizing market research and generating client communications, not for making trading decisions. Portfolio rebalancing with automated compliance checking and tax optimization gets into agent territory, but the firms doing this successfully have been building toward it for years, not jumping straight to autonomous systems.

Manufacturing might be the most grounded industry when it comes to AI adoption. Production line efficiency metrics and inventory tracking remain data processing problems. Predictive maintenance on machinery uses traditional ML—General Electric has been doing this successfully for years without needing large language models. BMW's quality control systems use computer vision models trained on specific defects, not generative AI trying to imagine what a defect might look like. When generative AI does appear, it's for technical documentation and safety procedure updates. Supply chain coordination with automated vendor negotiations might use agents eventually, but most companies are years away from trusting agents with vendor relationships.

E-commerce provides perhaps the clearest view of appropriate AI use. Daily sales reports and customer demographic analysis stay in data processing. Product recommendation engines and dynamic pricing use traditional ML refined over decades. Product descriptions and personalized marketing content showcase generative AI's strengths. Customer service workflows with automated returns and refund processing become complex enough for agents, but only after you've nailed the simpler pieces first.


## The Advanced Implementation Reality

Sophisticated implementations don't choose a single category—they combine approaches strategically. You use data processing for core metrics and reporting, traditional ML for specific predictions where you have quality training data, GenAI for content creation and summarization, and agents only for genuinely complex workflow orchestration.

The key is progressive enhancement. Start with manual processes or simple automation as your baseline. Add data processing for basic insights. Layer in ML for specific predictions once you have good data. Introduce GenAI for content creation needs when the value justifies it. Only then consider agents for complex multi-step workflows. Each step must prove its value before you move to the next.

Implementation sequencing matters enormously. Begin with a pilot phase—a small, controlled test with clear success metrics. Move to an expansion phase with gradual rollout and continuous monitoring. Reach production phase only with established maintenance processes. Continue with an optimization phase based on real-world performance. Most companies try to skip straight to production and wonder why their AI initiatives fail.

The hybrid approach often works best. Rather than forcing everything into one category, use each tool where it excels. A customer service system might use data processing to route tickets, traditional ML to predict resolution time, generative AI to draft responses, and agents to coordinate complex escalations. Each component does what it does best without overengineering.


## Future-Proofing Your Decisions

AI capabilities advance rapidly, but that doesn't mean you should jump to the most advanced option. Model performance improvements mean what requires GenAI today may be solvable with traditional ML tomorrow. Compute costs for AI inference continue declining, but they're still significant. Development frameworks are improving, but they're not magic. AI-as-a-service offerings are expanding, but they still require integration and maintenance.

Developing engineering taste for AI decisions requires systematic practice. Build a pattern library of successful and failed AI implementations. Understand business context beyond technical requirements. Learn to assess AI vendor claims critically—most are vastly overstated. Stay current with AI capability evolution and limitations, but don't chase every new model release.

When management pushes for inappropriate AI solutions, you need a structured response. First, acknowledge their vision—show you understand what they want to achieve. Then reframe around value, presenting multiple approaches with different trade-offs. Present options with clear metrics for timeline, cost, risk level, and capability. Finally, recommend based on their stated priorities, whether that's speed, cost, or risk tolerance.

Different stakeholders need different messages. C-suite executives care about competitive advantage and measurable business outcomes. Operations teams emphasize reliability, maintainability, and user adoption. Technical teams need to understand implementation complexity and resource requirements. End users just want improved experience and reduced friction. Tailor your message to your audience.


## The Boring Solutions That Win

Most of what companies are calling AI projects should be SQL queries. Most of what they're calling agent workflows should be better spreadsheets. Most of what they're calling innovative is just expensive.

This isn't anti-AI. I use AI tools every day. But I use them for problems that actually need them. When I need to analyze unstructured customer feedback across thousands of documents, I use generative AI. When I need to predict equipment failures from sensor data, I use traditional ML. When I need to sum up last quarter's revenue, I use SQL.

The skill that matters now isn't knowing how to use AI. It's knowing when not to. It's having the taste to recognize that a boring solution that works beats an exciting solution that might work. It's having the courage to push back when someone wants to use a bazooka to kill a fly.

Data quality beats model complexity every time. Garbage in, garbage out applies 10x more when you introduce AI. Fix your data pipelines before reaching for models. If you have great quality data, you can use simpler, cheaper models. If you don't have data quality, make that your priority instead of chasing AI.

Start with humans in the loop. When deploying LLMs or agents, surface suggestions for humans to vet first. Build trust gradually. Gather feedback systematically. Only automate once you've proven the system works. The companies that skip this step are the ones with AI horror stories.

The ultimate goal isn't using AI—it's solving business problems efficiently. Sometimes that requires cutting-edge AI agents. More often, it needs well-designed data processing pipelines. Developing taste means knowing the difference and having the organizational support to choose appropriately.

As AI capabilities continue advancing, my framework will evolve, but the underlying principle remains constant: match solution complexity to problem complexity, measure real value, and build incrementally from simple to sophisticated approaches.

Your job isn't to use AI. Your job is to solve problems. Sometimes AI is the right tool. Usually, it isn't. The sooner we all accept this, the sooner we can stop wasting time and money on solutions looking for problems and start actually getting things done.

The next time someone says you need AI for something, ask yourself: what would this look like with just SQL? Start there. Only move up the complexity ladder when the value genuinely justifies it. Your future self—and your budget—will thank you.

[![](https://substackcdn.com/image/fetch/$s_!y5tF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff09d784c-dabf-41dc-a64f-0b2652d1d700_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!y5tF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff09d784c-dabf-41dc-a64f-0b2652d1d700_1024x1024.png)
