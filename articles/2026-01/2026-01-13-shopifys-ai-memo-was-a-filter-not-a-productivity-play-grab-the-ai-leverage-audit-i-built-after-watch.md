---
title: "Shopify's AI Memo Was a Filter, Not a Productivity Play. Grab the AI Leverage Audit I built after watching Duolingo fail and Shopify succeed."
author: "Nate Jones"
published: 2026-01-13
url: https://natesnewsletter.substack.com/p/my-honest-field-notes-on-how-the
subtitle: "Watch now | Job postings requiring AI literacy doubled in just 12 months--yet most people still can't decipher usage from leverage."
audience: everyone
scraped_at: 2026-01-13 12:00:17
---

A single memo turned AI fluency into a hiring constraint. Eight months after Tobi Lutke told Shopify to prove AI can’t do the work before hiring a human, the rest of the industry is adopting the same metric—and not for the reasons the skeptics assumed.

The memo was a filter. By making AI usage a performance metric, Lutke wasn’t trying to make Shopify more efficient—he was reshaping who would want to work there and who would thrive once they arrived. The productivity gains, if they come, are a second-order effect of assembling a team adapted to the new reality.

And now that filter is spreading. Meta. Microsoft. Google. Nvidia. Each week brings another company formalizing what was already happening. Job postings requiring AI skills doubled from 5% to 9% in a single year. Workers in occupations requiring AI fluency grew from one million to seven million. Just this week, Josh Miller at The Browser Company mentioned paying premiums for people who are “native to the Claude Code way of building.”

The evidence on productivity itself? Genuinely mixed. One rigorous study found developers using AI took 19% *longer* than those working without it. Another found bottom-quartile support reps got a 35% throughput lift while veterans saw almost no gain. AI amplifies variance rather than raising averages—but the hiring market doesn’t optimize for averages. It optimizes for the possibility of outliers.

**Here’s what’s inside:**

- **The Red Queen logic.** What Lutke actually said in April 2025, and why the memo wasn’t a new philosophy but an existing one applied to a new tool.
- **How Shopify made it real.** The infrastructure—internal LLM proxy, 24+ MCP servers, open-sourced tooling—that made the mandate feasible where most companies would have failed.
- **The copycat wave.** How Duolingo’s version triggered immediate backlash, Fiverr’s maximum-bluntness approach led to 30% layoffs, and Box found a middle path that may prove more durable.
- **Big tech standardizes the metric.** The specific announcements from Meta, Microsoft, Google, and Nvidia—and what Jensen Huang said to managers telling employees to use less AI.
- **The productivity paradox.** Why mixed data doesn’t slow the market—and how variance becomes a hiring premium.
- **The talent market data.** How job postings, skills requirements, and compensation structures are already changing—including the entry-level squeeze intensifying even as companies claim they can’t find AI-fluent talent.
- **Where this heads in 2026.** Role boundaries dissolving, new coordination roles emerging, compensation polarizing, and why the training gap is becoming a strategic liability.

The filter is set. Now we find out who passes.


## [Grab the Prompts](https://www.notion.so/Prompts-The-AI-Leverage-Audit-2e51e6391c8080808c0af944505de595?source=copy_link)

The AI Leverage Audit isn't a prompt pack to "use AI better"—it's a diagnostic that makes adaptation legible. Phase 1 prevents the delusion of protecting tasks that don't need protecting. Phase 2 catches activity theater before it shows up in your performance review as "I use Claude for everything" with nothing to show for it. Phase 3 surfaces where you're running 2023 workflows with 2025 tools. Phase 4 exposes which role boundaries are real constraints versus legacy habits drawn around human limitations that no longer apply.

Each phase builds on the previous; you can't skip ahead without being exposed. The quick version runs in 15 minutes. The full version takes an hour and produces artifacts you can actually share with your manager. These prompts have been pressure-tested against the specific failure modes the article describes—performative productivity, bolt-on usage, and the gap between "I use AI" and "my output is different now."


## The 8-Month Revolution: How the Talent Market Is Restructuring in Real Time

Eight months ago, Tobi Lutke posted a memo that most people dismissed as typical tech CEO posturing. AI is mandatory. Prove the robots can’t do it before you hire a human. Put AI usage in performance reviews. The reactions were predictable: some called it visionary, others called it a smokescreen for layoffs, and most assumed it would quietly fade into the graveyard of executive pronouncements that sound radical but change nothing.

They were wrong. What Lutke actually did was fire the starting gun on a talent market restructuring that is now, in January 2026, accelerating faster than anyone anticipated. And we’re not at the end of this story. We’re watching it unfold in real time, with new signals emerging weekly. Just this week, Josh Miller at The Browser Company mentioned they’re paying premiums for people who are “native to the Claude Code way of building.” That’s one company, one announcement—but it’s symptomatic of something much larger. The job market itself is being rewritten, and the changes that seemed speculative eight months ago are now showing up in actual hiring criteria, compensation structures, and role definitions across the industry. Every week brings another data point. Every month the pattern becomes clearer. And we’re nowhere near the end.


## The April Memo in Context

To understand where we’re going, you have to understand what Lutke actually said in April 2025—and more importantly, what he meant by it. The memo wasn’t a new philosophy for Shopify. It was the application of an existing philosophy to a new capability. Lutke has long operated under what he calls the Red Queen framework, borrowed from Lewis Carroll’s Through the Looking-Glass, where the Red Queen tells Alice that in her kingdom, “it takes all the running you can do, to keep in the same place.”

At Shopify, this translates to a stark reality: in a company growing 20-40% year over year, you must improve by at least that much every year just to re-qualify for your own role. This applies to Lutke himself as well as everyone else. You’re not competing against your past self. You’re competing against the theoretical version of yourself that kept pace with the company’s growth. Stagnation isn’t just failure—it’s slow-motion termination. The April 2025 AI memo wasn’t a new philosophy. It was the Red Queen logic applied to a new capability multiplier.

What the April memo did was identify AI as the new mechanism for that improvement. The specific mandates were stark: reflexive AI usage is now a baseline expectation—not a suggestion, not encouraged, but expected. AI must dominate the prototype phase of all GSD projects. Performance reviews will include AI usage questions, with managers and peers rating colleagues on how “AI native” or “AI reflexive” they are. Teams must prove AI can’t do the work before requesting headcount. And everyone means everyone, including Lutke and the executive team.

The critical shift from Lutke’s earlier encouragement was explicit. As he put it: “The call to tinker with it was the right one, but it was too much of a suggestion. This is what I want to change here today.” He wasn’t asking anymore. He was telling.

When pressed on Twitter for specifics behind his claim that he’d seen people achieve “100X the work,” Lutke cited translations and large-scale refactors and “lots of internal processes.” Forrester’s response was pointed: “Setting appropriate expectations and KPIs, and measuring them continuously, sets you up for success. Inflated hyperbole doesn’t.”

The reaction split predictably along ideological lines. Supporters saw it as the correct path for any company serious about competing. Critics saw it as a smokescreen for headcount reduction dressed up in futurist language. Fortune interpreted the memo as “saying the quiet part out loud”—that we’re headed into an AI-first era where new human hires must prove their worth among AI “employees.” And skeptics pointed to the gap between the productivity claims and the reality that most rigorous studies show gains in the single digits—or in some cases, negative returns when developers spend more time debugging AI-generated code than they would have spent writing it themselves.

But here’s what most people missed: the memo wasn’t primarily about productivity. It was about selection pressure. By making AI usage a performance metric, Lutke wasn’t just trying to make Shopify more efficient. He was reshaping who would want to work there and who would thrive once they arrived. The memo was a filter, and filters work in both directions.


## How Shopify Actually Implemented This

The gap between issuing a mandate and making it real is where most corporate initiatives die. What made Shopify different was that they’d been building toward this moment for years before the memo existed.

A First Round interview with VP and Head of Engineering Farhan Thawar from July 2025 reveals the mechanics behind the memo. Shopify was ahead of the curve before any of this became fashionable. In late 2021, Thawar brought GitHub Copilot to Shopify “so early that he couldn’t even pay for the product yet.” A year before the release of ChatGPT, they were already using Copilot across engineering. By early 2023, they had an 80% adoption rate. GitHub started asking them how they did that.

The infrastructure layer they built is what made the mandate feasible. They created an internal LLM proxy—a centralized system allowing employees to access multiple AI models through a single interface. Users can switch between models seamlessly, and the proxy handles scaling, tracking, and failover in production. They built 24+ MCP servers connecting to Slack, Salesforce, GSuite, and internal systems under Thawar’s directive to “MCP everything”—making every single piece of internal data available for AI interrogation. Once someone creates an MCP connector, everyone can use it.

They also open-sourced Roast, an AI orchestration framework built with Claude Code that “roasts” code contributions with constructive criticism. The key insight from building it: “AI agents need help staying on track, and work much better when you break down complicated prompts into discrete steps. Allowing AI to roam free around millions of lines of code just didn’t work very well.”

Unlike companies that gate advanced models for technical teams, Shopify gives everyone access to everything. No spending quotas. Thawar tracks who’s spending the most on Cursor tokens as “a cool proxy for value”—recently, CTO Mikhail Parakhin topped the list. The tool adoption exploded so fast that Thawar ordered 1,500 Cursor licenses and quickly needed 1,500 more. And the surprising adoption pattern: the fastest-growing user groups aren’t engineering. They’re support and revenue teams.

The legal team’s posture made this possible. When Thawar wanted to adopt Copilot in late 2021, his conversation with legal opened with: “Hey, we’re likely going to do this. How can we do it safely?” Their response: “Let’s figure out a way.” Thawar contrasts this with peers at other companies who were getting blocked by legal resistance. The principle he operates by: “If you don’t default to ‘yes,’ you’re defaulting to ‘no.’”


## The Real-World Use Cases

The specific examples of how Shopify employees use these tools reveal what AI-augmented work actually looks like in practice.

A sales engineer brought MCPs of his most frequently used tools—GSuite, Slack, Salesforce—into a Cursor-built dashboard. He asks “What should I do today?” and the system looks at Salesforce opportunities, notices missing email responses, and prompts action. As Thawar describes it: “He literally doesn’t work in any of those other tools anymore. He works in Cursor as his homepage.”

The Revenue Tooling team deployed an RFP agent that answers RFP questions while learning from winning responses. It improves through accumulated knowledge of what wins deals. Sales reps built automated site audit tools. Thawar frames this as “process power”—not merely accelerating existing workflows but fundamentally restructuring how work gets organized. Making site audits “trivially cheap” enables earlier SDR engagement.

Shopify’s internal AI chat tool originated as a prototype by a senior engineer experimenting with open-source tools. It became so widely adopted that a dedicated engineering team now runs it. This pattern—individual experimentation becoming organizational infrastructure—is the mechanism by which AI-native workflows propagate.


## The Headcount Reality

The numbers tell a story that complicates any simple narrative about AI and jobs. Shopify had roughly 11,600 employees at the end of 2022. After layoffs that year, they were down to around 10,000. After May 2023 layoffs, around 8,300. By December 2024, roughly 8,100. The Logic reported that Shopify’s support team experienced “significant layoffs on an almost monthly basis” throughout 2024.

At a Morgan Stanley conference in March 2025, CFO Jeff Hoffmeister said the company can “keep headcount relatively flat,” though costs may rise because “a higher comp, high-end AI engineer” lifts compensation even with stable headcount.

Some observers theorize the memo is a smokescreen to cover cost-cutting without alarming investors. Though Lutke says it’s not about economics, the flat headcount guidance suggests economic factors remain at play. The truth is probably both: AI enables genuine productivity gains for some workers on some tasks, and it also provides cover for headcount reduction that would have happened anyway.


## The Intern Paradox

One of the strangest developments of the past eight months reveals the strategic logic beneath the surface. Months after the “prove AI can’t do it” memo, Shopify announced a massive expansion of their internship program—from 75 to 1,000 engineering interns.

On the surface, this seems contradictory. If AI can do the work, why hire 1,000 interns? But the logic becomes clear when you understand what Shopify is actually selecting for.

Thawar calls interns “AI centaurs”—naturally comfortable with AI tools because they’ve grown up with them. They push full-timers to stay current. After successfully onboarding 25 engineering interns, Lutke asked Thawar how big they could scale. Thawar originally said 75, then revised to 1,000.

The program is structured as a win on multiple dimensions. Interns bring AI-native skills and fresh perspectives. Shopify gets a massive pool of candidates for full-time positions. Even interns who leave take skills to the ecosystem, which Shopify sees as net positive for the broader environment they operate in.

Other companies have noticed. The pattern suggests a sophisticated talent strategy: restrict experienced headcount while flooding the organization with AI-native talent who can demonstrate what’s actually possible. Rather than trying to retrain experienced workers who may be resistant to change, bring in workers for whom AI-native workflows are simply how work gets done.


## The Performance Review Integration

Shopify incorporated “AI reflexiveness” into 360-degree review cycles. Managers and peers now rate colleagues on how “AI native” or “AI reflexive” they are, whether they use AI as “a thought partner, deep researcher, critic, tutor, or pair programmer,” and their ability to prompt effectively and load context.

The company analyzed AI tool usage correlated to performance reviews and found positive correlations. They plan another analysis after gathering a few years of data to see how the relationship evolves.

The critique of this approach is worth taking seriously. One analyst argued that making AI usage a performance metric is “a fast track to shallow adoption and superficial outputs.” When employees are judged by how often they use AI instead of how effectively they solve problems, the result could be “performative productivity”—the appearance of AI integration without the substance.

Shopify’s counter is that they’ve seen 32% higher employee productivity across departments. But they acknowledge this comes from “a company with years of deliberate AI groundwork.” The infrastructure and culture were in place before the mandate. Most companies trying to copy the approach don’t have that foundation.


## The Copycat Wave and What It Revealed

When Lutke released the memo, Thawar’s inbox exploded. Box, Fiverr, Duolingo, and even Canada’s Prime Minister quickly shared their own versions. The memo had become a genre. Each version revealed something about how different organizations interpreted the same underlying pressure.

Duolingo’s version became a case study in how not to do this. On April 28, 2025, CEO Luis von Ahn shared a memo outlining AI-first transformation: phasing out contractors if AI could do their work, making AI part of performance reviews, restricting headcount growth.

The response was immediate and severe. “This is a disaster. I will cancel my subscription.” “AI first means people last.” Von Ahn eventually walked it back, admitting that when he released the memo, “I didn’t do that well… I do not see AI as replacing what our employees do.” He clarified that the company “never laid off any full-time employees” though the contractor workforce “has gone up and down depending on needs.” Duolingo had cut 10% of contractors in January 2024. Von Ahn acknowledged the backlash “slightly dampened customer growth,” though overall performance remained strong. Duolingo now has “F-r-AI-days”—Friday time for teams to experiment with AI efficiency—and they’ve rolled out 148 AI-generated courses.

Fiverr’s CEO Micha Kaufman took the opposite approach: maximum bluntness. He followed Lutke with: “AI is coming for your jobs. Heck, it’s coming for my job too. This is a wake-up call.” He told employees his expectations were “double or triple the output per unit of time, and the same for the quality.” In December 2025, Fiverr cut 30% of workforce to become an “AI-first” company. Critics called him “super tone-deaf” for implying he’s in the same boat as employees living paycheck to paycheck.

Box’s Aaron Levie found a middle path that may prove more durable. His approach focuses on eliminating busywork with a twist: teams that automate keep the savings for strategic projects. “AI savings shouldn’t return to the CFO—they should fund your next breakthrough.” This framing converts AI adoption from a threat into an opportunity at the team level, which changes the incentive structure entirely.

What the copycat wave revealed was that the underlying pressure was real—every CEO felt it—but the execution varied wildly based on how well leaders understood their own organizations and audiences. Lutke’s version worked at Shopify partly because Shopify had spent years building the infrastructure and culture to support it. When the memo dropped, it was formalizing what was already happening, not demanding a transformation from scratch.


## Big Tech Falls In Line

By late 2025, the holdouts had capitulated. The mandates came in rapid succession, each one confirming that AI usage expectations were becoming industry standard.

Meta announced in November 2025 that “AI-driven impact” becomes a core performance metric from 2026. Employees will be assessed on how they use AI to deliver results. Building AI tools that improve productivity becomes part of evaluation. An “AI Performance Assistant” rolled out in December 2025 to help employees draft reviews. Early adopters receive special recognition through bonuses and raises.

Microsoft’s Julia Liuson, President of Developer Division and GitHub, declared in June 2025: “Using AI is no longer optional—it’s core to every role and every level.” Managers now factor AI usage into performance reviews, with some teams developing formal metrics.

Google’s engineering VP Megan Kacholia announced that engineers use internal AI systems for coding. External AI tools require approval. Sundar Pichai reinforced the message: “In this AI moment, I think we have to accomplish more by taking advantage of this transition to drive higher productivity.” The current stats: nearly half of all new Google code is AI-generated. Pichai says AI resulted in roughly a 10% engineering velocity increase.

And then there was Jensen Huang in November 2025, responding to reports of managers telling employees to use less AI: “I want every task that is possible to be automated with artificial intelligence to be automated with artificial intelligence.” He called resistance “insane.” On job security, he added: “I promise you, you will have work to do.” Nvidia grew from 29,600 to 36,000 employees between fiscal 2024 and 2025, and Huang says they’re “probably still about 10,000 short.”

The pattern across all of these announcements is consistent: AI usage is moving from encouraged to expected to measured. What gets measured gets managed, and what gets managed shapes behavior. The companies that were early to this now have years of data correlating AI tool usage with performance reviews. Whether that correlation reflects genuine productivity gains or simply identifies employees who are good at adopting new tools remains an open question, but from a hiring and retention standpoint, the distinction may not matter. The selection pressure is real regardless of the mechanism.


## The Productivity Paradox

Here’s where the story gets complicated, because the evidence on AI productivity is genuinely mixed—and the gap between executive claims and measured reality remains wide.

The contrarian data is striking. METR ran a randomized controlled trial in July 2025 with experienced open-source developers working on their own repositories. The developers expected AI would reduce completion time by 24%. The actual result: developers using AI took 19% longer than those working without it.

Stack Overflow found that favorable views of AI tools have declined year-over-year. 46% of developers don’t trust AI output accuracy, up from 31%. The top frustration, reported by 66% of devs: AI solutions that are “almost right, but not quite,” leading to time-consuming debugging.

A Danish workforce study found productivity improved by only 3% among 25,000 workers using AI tools—supporting economist Daron Acemoglu’s assertion that markets have overestimated AI productivity gains.

On the other hand, the positive data is equally striking. PwC’s Global Workforce Survey from November 2025 found that 92% of daily AI users report productivity benefits, compared to 58% of infrequent users. Daily users report higher job security (58% vs 36%) and more salary increases (52% vs 32%). PwC’s AI Jobs Barometer found that since GenAI’s 2022 proliferation, productivity growth in AI-exposed industries like financial services and software publishing increased fourfold—from 7% between 2018-2022 to 27% between 2018-2024.

A tech support study of 5,000+ agents at a U.S. tech desk found a 35% throughput lift for bottom-quartile reps—but almost no gain for veterans. A Procter & Gamble study of 776 product professionals found that individuals using AI performed as well as a team of two without.

The nuanced takeaway: McKinsey found that employees use AI 3x more than their C-suite expects—4% of C-suite estimate employees use GenAI for more than 30% of daily tasks, while 13% of employees self-report doing so. 75% of engineers use AI tools—yet most organizations can’t measure productivity improvements.

The pattern that emerges is that AI amplifies variance. It helps lower performers more than veterans. It works better for some task types than others. Individual wins don’t necessarily translate to aggregate organizational gains. But the hiring market doesn’t optimize for averages. It optimizes for the possibility of finding outliers. Companies will pay premiums for AI-native talent not because the average AI-native worker is dramatically more productive, but because the best ones might be—and identifying them has become a competitive priority.


## The Talent Market is Already Restructuring

The data on how the job market itself is changing is now concrete enough to track. Job postings requiring AI skills doubled from roughly 5% in 2024 to 9% in 2025. Workers in occupations requiring AI fluency grew from around one million in 2023 to roughly seven million in 2025—the fastest-growing skill category in U.S. job postings.

The entry-level squeeze is already visible. 66% of enterprises are reducing entry-level hiring as they adopt AI. 91% report automation-driven role changes. Postings for seven-plus years of experience increased while true entry-level roles shrank. Some companies now require prior projects even for nominally junior positions.

The skills gap is widening. 84% of companies report significant skills gaps. AI/ML roles take 89 days to fill. The most evident skills gap, according to Robert Half research, is AI, machine learning, and data science. Nearly 90% of organizations use AI in operations, yet only 9% have achieved AI maturity.

The signals keep coming. This week’s announcement from The Browser Company is one of many. Miller mentioned designers submitting pull requests directly, non-engineers prototyping their own ideas in code, engineers running experimental side projects without sacrificing core commitments. They’re creating new roles like “Design Producer”—modeled on Apple’s producer discipline—to coordinate AI-augmented teams. They’re paying premiums for people who are “native to the Claude Code way of building.”

It’s one company, but it’s not an outlier. It’s a data point in an accelerating pattern that now includes Meta, Microsoft, Google, Nvidia, Shopify, and an expanding list of companies restructuring around AI-native workflows. The restructuring Lutke triggered in April is propagating through the broader market, showing up in job descriptions being quietly rewritten, interview processes adding AI fluency assessments, and compensation models being recalibrated.


## The Employer Reaction and Cultural Concerns

The view from inside these organizations is more complicated than the executive announcements suggest.

One organizational communications analyst observed: “Lütke is convinced AI is crucial to Shopify’s success, but he doesn’t acknowledge employees’ concerns.” Social media reactions ranged from “the correct path to take” to concerns that it “leads to less and less employment of people over time.”

One pattern that keeps surfacing: “It is easier for juniors to bring AI into their daily workflows however, senior employees with more than 10 years of experience are too used to their patterns.” This maps onto the research showing AI helps lower performers more than veterans. The people with the most accumulated expertise may be the most resistant to tools that threaten to commoditize that expertise.

Organizational training expert Mike McBride put it bluntly: “Making any new technology an organizational imperative without meaningful training sends the message leadership understands urgency but not complexity. It might be easier for management to issue directives, but it’s considerably less effective—and more stressful—for staff.”

The “performative productivity” risk is real. When employees are judged by AI usage frequency rather than problem-solving effectiveness, the result may be surface-level adoption without genuine integration. Companies that mandate AI usage without building the infrastructure, training, and cultural support to make it effective may get the appearance of transformation without the substance.


## The Government Response

Canada’s response to these shifts offers a preview of how governments might try to manage the transition. Prime Minister Mark Carney appointed a special advisor for AI and economic opportunity. Key initiatives include $925.6 million over five years for sovereign public AI infrastructure, a $50 million Workforce Innovation Fund for recruitment and retention projects, a reskilling package to train 50,000 workers through employer-based programs, new Job Bank transparency requirements where all postings must include salary and disclose if AI is used in selection, and an AI Strategy Task Force that completed a 30-day sprint in fall 2025 to shape the national approach.

Whether government intervention can meaningfully shape a labor market transition this fast and this global remains to be seen. The pace of change at individual companies is outrunning policy development.


## Where This Is Heading in 2026

We’re eight months into a transformation that will take years to fully play out. The specific predictions will be wrong, but the direction is clear—and the pace is accelerating.

AI fluency is moving from differentiator to baseline. By the end of 2026, expect AI fluency requirements to appear in the majority of knowledge work postings, not as a specialized skill but as an assumed competency like email or spreadsheets. The companies that were early to this—Shopify, and now the big tech firms that have followed—are establishing the expectations that will become industry standard.

Role boundaries will continue dissolving. The pattern of designers submitting PRs, non-engineers prototyping, engineers running side experiments—this will spread. Job titles will become less descriptive of what people actually do. The cost of crossing into adjacent domains is dropping, which means the traditional org chart assumption of clean divisions between roles is becoming obsolete.

New coordination roles will emerge. When everyone can build, someone has to ensure coherence. Expect more positions like Browser Company’s Design Producer—orchestration roles that manage the increased volume of output from AI-augmented teams. These aren’t traditional management roles. They’re synthesis and curation roles for a world with dramatically more creative output per person.

Compensation will polarize. If one AI-fluent worker can do what previously required two or three, the math on salaries changes. Companies will pay significant premiums for workers who can demonstrate genuine AI leverage—not just AI usage, but AI leverage that translates to measurable output. Meanwhile, workers whose productivity doesn’t scale with AI access face relative wage pressure even if their absolute output remains constant. The premium Shopify’s CFO mentioned—paying more for “high-end AI engineers” even with flat headcount—is the leading edge of this shift.

The entry-level squeeze will intensify. The traditional entry-level job—where companies invest in training workers with potential but limited experience—becomes harder to justify economically when AI can handle much of what those roles traditionally accomplished. The paradox is that this happens at the same time companies claim they can’t find enough AI-fluent talent. Shopify’s solution—flooding the organization with 1,000 AI-native interns—may become a template for how companies resolve this tension.

The training gap will become a strategic liability. The companies that invested early in infrastructure—Shopify with their LLM proxy and MCP servers and internal tooling, the big tech firms with their internal AI systems—have a compounding advantage. Late adopters face a chicken-and-egg problem: they can’t hire AI-fluent workers without the infrastructure to support AI-fluent workflows, but they can’t build the infrastructure without workers who understand what to build.

The measurement problem will persist. 75% of engineers use AI tools, yet most organizations can’t measure productivity improvements. The gap between individual productivity gains and organizational metrics will continue to frustrate executives trying to justify AI investments and workers trying to demonstrate their value. Companies will develop better ways to measure AI-augmented work, but the transition will be messy.


## The Selection Pressure Reality

What Lutke understood in April, and what the broader market is now internalizing, is that the AI transition isn’t primarily about productivity. It’s about selection pressure.

The memo wasn’t designed to make Shopify 100x more productive. It was designed to ensure that the people who stay at Shopify and the people who join Shopify are the ones who thrive in an AI-augmented environment. The productivity gains, if they come, are a second-order effect of having assembled a team that’s adapted to the new reality.

This is the Red Queen logic updated for the AI era. The skill ceiling just got much higher. The people who were already 10x can now approach 100x on certain tasks. Those who struggle to integrate AI face relative decline even while maintaining their absolute output. And the companies that structure their hiring, compensation, and performance management around this reality will outcompete those that don’t—not necessarily because their current employees are more productive, but because over time they’ll accumulate talent that’s better adapted to the environment they’ve created.

The internal skepticism, the training gaps, the performative productivity—these are real problems that companies are going to have to solve. But the direction of travel is set. The executives have spoken. The performance reviews are being rewritten. The job postings are changing. The selection pressure is on.

As Lutke wrote eight months ago: “Stagnation is almost certain, and stagnation is slow-motion failure. If you’re not climbing, you’re sliding.”

What’s changed since April is that the rest of the industry has started climbing too. The announcements keep coming—Meta, Microsoft, Google, Nvidia, and now companies like The Browser Company making explicit what was implicit. Each one is a data point in an accelerating trend. The question for 2026 isn’t whether this transition is happening. It’s how fast the restructuring propagates through the rest of the economy, and what happens to the workers and companies that can’t keep pace.

We’re not at the end of this story. We’re watching it accelerate. Eight months ago, Lutke’s memo seemed provocative. Today it reads like a preview of what’s becoming orthodoxy. Eight months from now, we’ll look back at January 2026 the same way—as an early moment in a transformation that’s still gathering speed.​​​​​​​​​​​​​​​​

[![](https://substackcdn.com/image/fetch/$s_!fmyX!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F60caf2ea-21b9-421f-8663-a456b01f88da_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!fmyX!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F60caf2ea-21b9-421f-8663-a456b01f88da_1024x1024.png)
