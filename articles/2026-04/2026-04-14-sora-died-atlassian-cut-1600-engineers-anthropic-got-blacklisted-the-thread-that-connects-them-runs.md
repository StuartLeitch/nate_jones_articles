---
title: "Sora died. Atlassian cut 1,600 engineers. Anthropic got blacklisted. The thread that connects them runs through your org."
author: "Nate Jones"
published: 2026-04-14
url: https://natesnewsletter.substack.com/p/sora-died-atlassian-cut-1600-engineers
audience: everyone
scraped_at: 2026-05-14 14:33:38
---

March 2026 was one of the densest months in AI history. Three frontier models shipped in a single month — GPT-5.4, Gemini 3.1 Ultra, and Grok 4.20. GTC happened. The SaaSpocalypse continued. A major AI product was killed. A frontier lab got blacklisted by the government. The takes were written. The benchmarks were compared. You’ve already read those takes.

I don’t want to repeat them. I want to show you what happened *underneath*.

While everyone was comparing benchmarks, OpenAI’s flagship video product was burning $15 million a day in inference costs against $2.1 million in *total lifetime revenue*. The first real ad dollar entered a ChatGPT conversation and converted at 1.5x the rate of search. Atlassian had just reported cloud revenue up 26% — and its stock was still down 84% from its peak — because Wall Street wasn’t pricing the present, it was pricing a future where AI agents don’t need software seats. And a frontier AI lab got blacklisted by the U.S. government for refusing to build autonomous weapons, then watched its app go to number one on the App Store the same week.

None of those stories are about which model won a benchmark. All of them are about something harder to see and more consequential: the AI industry is leaving the capability phase and entering the economics phase. The question is no longer *what can we build*. It’s *what can we sustain*.

Here’s what’s inside:

- **Inference became the kill metric.** Sora died because serving it cost more than anyone would pay — and the physics of why apply to every AI product you’re building on.
- **The first real ad dollar entered the AI interface.** Criteo’s ChatGPT integration produced 1.5x conversion rates and the first credible threat to Google’s $300 billion ad model.
- **The physical path for AI is closing.** The White House cleared the regulatory lane, but 12 states, 50+ local governments, and Iranian drones are blocking where the infrastructure actually gets built.
- **The SaaS business model broke.** Per-seat pricing, the most durable model in enterprise tech for twenty years, is being repriced in real time — and the stocks are pricing it in before the seat counts even decline.
- **Safety posture became a market position.** The Anthropic-Pentagon standoff sorted AI labs into categories that governments and enterprise buyers are now using to make real procurement decisions.
- **The Open Brain skill that does this for you.** Weekly News Analysis skill tracks 30 companies across 10 categories, re-ranks using what your Open Brain already knows about you, and produces a personalized structural diff every week — plus 6 prompts that work in any AI client. For paid subscribers.

Each shift operates at a different altitude — physics, monetization, geography, business models, geopolitics — but they all feed the same underlying story. Let me show you what I found.


## LINK: Grab the [Prompts](https://promptkit.natebjones.com/20260405_9b7_promptkit_1) & the [Weekly News Analysis Skill](https://github.com/NateBJones-Projects/OB1/tree/main/skills/weekly-signal-diff)

This new Open Brain skill and prompt kit exist because I got tired of doing this analysis manually. The skill — [Weekly Signal Diff](https://github.com/NateBJones-Projects/OB1/tree/main/skills/weekly-signal-diff) — starts with 30 AI companies across 10 categories as a bootstrap layer, then re-ranks everything using what your Open Brain already knows about your interests, projects, and priorities. The output isn't a news summary. It's a structural diff that tells you what changed and why it matters *to you specifically*, not to the industry generally. If you have OpenRouter connected, it can optionally pull live, cited search through Perplexity Sonar before producing the digest — and the finished analysis saves back into your Open Brain, so the signal compounds week over week.

The prompts force the same diagnostic questions I used to write this article, so whether or not you've built Open Brain yet, the framework works. If you've ever finished a month of AI news and realized you absorbed a lot of takes but couldn't name the three things that actually changed, this is built to fix that.


## Inference became the kill metric — and Sora was its first victim

On March 24, OpenAI announced it was shutting down Sora. The standalone app, the video generation features inside ChatGPT, all of it, with the API staying live through September. Six months after public launch, the Disney billion-dollar deal collapsed with it. No money had ever changed hands.

The headline story is “AI video product fails.” The deeper story is bigger than that.

At peak usage, Sora was burning an estimated $15 million *per day* in inference costs against $2.1 million in total lifetime revenue, according to analyst estimates and mobile intelligence data. That’s not a pricing problem. That’s a physics problem. No go-to-market adjustment bridges a gap that wide. Bill Peebles, OpenAI’s own head of Sora, had already admitted on social media that the economics were “completely unsustainable.”

This matters because it is the loudest signal yet of a shift in where the hard constraint lives. For the last three years, the AI narrative has been about training: who can build the biggest cluster, who can afford the most data, who can push the frontier. But a paper published in January by Google’s Xiaoyu Ma and Turing Award winner David Patterson spelled out what the Sora numbers confirmed. *LLM inference is a crisis.* Their core argument: the hardware the industry is using for inference was never designed for it. The decode phase of a transformer is inherently sequential and memory-bound, not compute-bound. We’ve been optimizing for the wrong bottleneck. Memory bandwidth improves at a fraction of the rate compute FLOPS (floating point operations per second, the standard measure of raw processing power) scale. The gap is widening, not closing.

The industry spent 2024 and 2025 in a training arms race. March 2026 made it clear the next arms race is inference economics, and the companies that can’t close the gap between cost-per-generation and revenue-per-user are going to hit the same wall Sora hit.

Google’s TurboQuant, a compression algorithm that shrinks the KV-cache by at least 6x, is a direct response. So is Runway’s approach to video generation, which prioritized inference efficiency from the start. Runway charges users roughly $0.50 for a 10-second clip. Sora’s estimated compute cost per clip was $1.30 before even reaching the consumer. The survivors are the companies that treated serving cost as a first-class design constraint, not an afterthought.

**The underlying shift:** The most dangerous number in AI is no longer the training FLOP count. It’s the inference cost per unit of revenue. Every AI product team needs this metric on their dashboard. If it’s not there, you are flying blind toward the same wall that killed a $300 billion company’s flagship product in six months.


## The first real ad dollar entered the AI interface — and it converted at 1.5x

On March 2, Criteo became the first ad-tech company to integrate with OpenAI’s advertising pilot in ChatGPT’s free and Go tiers. Within days, Criteo was pitching its 17,000 advertisers on placing ads directly inside ChatGPT conversations.

Most coverage treated this as a footnote. It is not a footnote.

The early data from a sample of 500 Criteo retailers showed that users arriving at retail sites from LLM platforms converted at approximately 1.5x the rate of other referral channels. The sample is small and the time window is narrow. But the *direction* of the signal matters enormously, because it begins to answer a question the entire digital advertising industry has been dancing around: where does the ad dollar go when the search results page disappears?

The shift underneath is this: in a conversation interface, there is no list of ten blue links. There is no page 1 versus page 2. There is a recommendation, singular, woven into a response the user trusts. Criteo’s pitch deck, shared with Digiday, frames this explicitly: the purchase funnel compresses from a multi-step process into a single conversation. Discovery, consideration, and conversion happen in the same context window.

What Criteo is selling is something the ad industry hasn’t seen in a decade: a genuinely new *surface*, and the first one that credibly threatens Google’s core monetization model. Google built a nearly $300 billion advertising business on capturing search intent. If conversational AI captures that intent upstream, before the user ever opens a browser, then the value migrates with it.

OpenAI isn’t selling the ads directly. Criteo is. That’s a signal in itself. OpenAI is building the *surface* and letting the existing programmatic infrastructure operate within it, piping product relevance signals into conversations through Criteo’s MCP server. This is the pattern that will define AI monetization: the model provider creates the context, the ad-tech layer fills it.

**The underlying shift:** The interface where people make decisions is migrating from search to conversation. The advertising industry’s $1.1 trillion global budget will follow. If your company monetizes through search visibility, organic or paid, March 2026 is when your strategic planning horizon shortened dramatically.


## The regulatory path cleared but the physical path is closing

On March 20, the White House released a National Policy Framework for AI: four pages of legislative recommendations urging Congress to establish a single federal standard that preempts state AI laws imposing conflicting requirements. No new regulatory body. Reliance on existing sector-specific regulators and industry-led standards. Copyright questions deferred to courts. Streamlined permitting for AI infrastructure. Two days earlier, Senator Blackburn released a 291-page discussion draft of the TRUMP AMERICA AI Act operationalizing the same vision. The legislative machinery is in motion.

That’s the headline, but what it misses is bigger.

The White House framework can preempt state *AI regulation*, rules about model transparency, bias audits, liability for deployers. What it cannot easily preempt is the wave of state and local resistance to the *physical infrastructure* AI requires to exist. And that wave is breaking right now.

As of March, lawmakers in at least 12 states had filed data center moratorium bills, formal pauses on new construction while legislators study impacts on power grids, water supplies, land use, and consumer electricity rates. The states include Virginia (home to Data Center Alley in Loudoun County, the densest data center corridor on Earth), Georgia, New York, Maryland, Oklahoma, Vermont, South Dakota, Michigan, and Minnesota. At the local level, more than 50 governments have passed short-term freezes, from St. Charles, Missouri to DeKalb County, Georgia to three counties in Indiana. On March 25, Senator Sanders and Representative Ocasio-Cortez introduced the Artificial Intelligence Data Center Moratorium Act at the federal level, a long shot under Republican control, but a signal of where midterm politics are heading.

The bills sit in an entirely different legal surface than the White House framework targets: zoning, energy, water, and land-use. Federal preemption of state AI laws does nothing to override a county that won’t rezone farmland for a gigawatt campus, or a state utility commission that refuses to approve the grid interconnection. The constraint here isn’t regulatory theory. It’s megawatts, aquifers, and voter backlash. A Heatmap poll of nearly 4,000 voters found data centers had a net approval of just +2%, less popular than gas plants, wind farms, or even nuclear facilities. That’s a NIMBY problem, and NIMBY problems don’t yield to White House frameworks.

And the geography question got more complicated in March — violently. Iranian drones struck AWS facilities in the UAE and Bahrain, damaging physical infrastructure and disrupting cloud services across the region. For the first time, commercial hyperscale data centers became explicit kinetic military targets. Reuters reported that an affected UAE insurance platform was working with AWS to temporarily shift workloads outside the region, but that local data residency rules required regulatory approval before the migration could proceed.

Meanwhile, nearly $700 billion in hyperscaler capex commitments for 2026 need somewhere to land. The UAE, Saudi Arabia, and Southeast Asia are attracting billions. Microsoft announced its Saudi Arabia East region going live in Q4 2026. Google and the Saudi Public Investment Fund are advancing a $10 billion AI hub. Vietnam’s first 200 MW AI data center breaks ground this month. The Middle East and Asia are positioning as alternative compute geographies precisely as U.S. domestic sites face permitting gridlock and community resistance.

So the real picture in March is a three-layer contradiction: the White House is trying to clear the regulatory path, communities are blocking the physical path, and the geopolitical path is getting shot at.

**The underlying shift:** The question of *where AI physically lives* is becoming contested at every level: federal, state, local, and international. If you are making decisions about compute capacity, inference deployment, or data residency, the binding constraint in 2026 is not AI regulation. It’s whether the building gets built, the grid connection gets approved, and the facility doesn’t become a target. The geography of AI is now a first-order strategic question, not an ops detail.


## The SaaS business model broke

On March 11, Atlassian CEO Mike Cannon-Brookes sent an email to staff announcing 1,600 layoffs, 10% of the company’s global workforce. More than 900 of those roles were in software R&D. Twenty minutes after Cannon-Brookes published a blog post and video message, affected employees received their emails. They got six hours on Slack to say goodbye. Then the accounts were locked.

The same announcement disclosed that CTO Rajeev Rajan would step down on March 31 after nearly four years. He was replaced by two executives, one titled “CTO Teamwork,” the other “CTO Enterprise and Chief Trust Officer.” Both come from AI-native backgrounds. The message was not subtle.

Cannon-Brookes framed the layoffs as “adaptation,” self-funding further investment in AI and enterprise sales. The stock, already down more than 70% from its 52-week high, ticked up 2% in after-hours trading.

The part nobody connected loudly enough: In October 2025, *five months before the layoffs*, Cannon-Brookes appeared on the 20VC podcast and said technology creation is “not output-bound.” Atlassian, he predicted, would employ *more* engineers in five years, not fewer. He pledged to hire more new graduates than in previous years.

Then March came, and over 900 R&D roles disappeared. Either the AI landscape shifted so dramatically in five months that the CEO’s entire workforce thesis became obsolete, or the workforce thesis was never the real driver of the decision. The market pressure tells the second story more cleanly. Atlassian’s stock was caught in the broader SaaSpocalypse, a selloff that erased more than $1 trillion in market capitalization from enterprise software companies as investors repriced the per-seat licensing model that has powered SaaS for two decades.

The mechanism is simple. Jason Lemkin, one of the most respected voices in SaaS investing, articulated it in a single sentence: if 10 AI agents can do the work of 100 reps, you need 10 Salesforce seats, not 100. That’s a 90% revenue compression for the same work output. Atlassian had just reported cloud revenue up 26%. Its Teamwork Collection had crossed a million seats. And the stock was still down 84% from its peak — because Wall Street wasn’t pricing the current seat count. It was pricing the seat count in a world where agents do the work.

Block cut 4,000 jobs in February 2026 citing an “intelligence-native” model. Workday had already cut 8.5% in early 2025; by February 2026, it cut another 2%. Oracle said AI was enabling it to shrink development teams. By early March, tech layoffs globally had surpassed 45,000, with AI among the most frequently cited justifications.

**The underlying shift:** The per-seat pricing model, the single most durable and valuable business model in enterprise technology for the last twenty years, is under structural threat. The companies that survive this repricing will be the ones that can transition to outcome-based or consumption-based pricing before their seat counts erode further. This is not a layoff story. It’s a pricing-model story. And pricing-model transitions kill more companies than technology shifts do.


## Safety posture became a market position — and the sorting has begun

This is the shift that will look most obvious in hindsight and that most people are still processing as a political drama rather than an economic one.

On February 26, Anthropic CEO Dario Amodei published a statement explaining that the company could not accept the Pentagon’s demand that its AI models be available for “all lawful purposes.” Anthropic had two red lines: no use of Claude in fully autonomous weapons, and no use for mass surveillance of American citizens. The Pentagon said it could not accept a private company dictating terms on a classified network. Negotiations collapsed.

What happened next was unprecedented. On February 27, President Trump directed federal agencies to “immediately cease” all use of Anthropic’s technology. Secretary of War Pete Hegseth designated Anthropic a “supply chain risk to national security,” a classification traditionally used against companies tied to foreign adversaries. The designation required defense contractors to certify they don’t use Claude in any work with the military. Trump told Politico he “fired” Anthropic. Within hours, OpenAI announced its own deal with the Pentagon for classified deployments.

The sequence itself was dramatic. But what makes it important is what it revealed about how the market now sorts AI companies, and the decisions every lab, every startup, and every enterprise buyer now has to make.

Anthropic held its red lines and got blacklisted. It sued the government on March 9, alleging retaliation and First Amendment violations. A federal judge on March 26 temporarily blocked the supply chain risk designation, calling the government’s measures an attempt to “cripple” the company and questioning why a failed contract negotiation warranted a punishment typically used against foreign adversaries.

OpenAI stepped in and claimed its contract had *better* safeguards. The company published some contract language, then revised it days later after critics pointed out the guardrails were vague. OpenAI’s head of robotics, Caitlin Kalinowski, resigned over the deal. Internal employees publicly expressed frustration that a contract of this magnitude had been rushed. Former Pentagon officials said on the record they didn’t believe the surveillance restrictions were real. ChatGPT uninstalls surged 295% overnight. Claude went to number one on the App Store.

The part I keep coming back to: even while designating Anthropic a supply chain risk, the DOD continued using Claude to support military operations in Iran. The government was simultaneously calling Anthropic a security threat and relying on its technology in active combat.

The contradictions are important, but they’re not the point. The point is that safety posture is no longer just an ethics question or a talent-retention strategy. It’s a *market-position* question with revenue consequences that run in both directions. Anthropic’s stance cost it a $200 million contract and triggered a government-wide ban. But it also drove record consumer adoption, generated enormous goodwill among enterprise buyers who value AI governance, and created a differentiation signal that no marketing campaign could buy. OpenAI captured the defense revenue but absorbed reputational damage, internal dissent, and scrutiny that will follow it into every future enterprise deal where trust is part of the conversation.

For every other AI company, and for every enterprise making procurement decisions, the Anthropic-Pentagon standoff creates a new variable in the equation. The labs are being sorted into “deploy-first” and “safety-first” categories by governments, and that sorting has commercial consequences. Deploy-first companies will capture defense and national security revenue but may lose talent and enterprise trust. Safety-first companies may retain both but get locked out of the largest single buyer of technology on Earth.

**The underlying shift:** Safety posture is now a market-positioning decision with direct revenue implications, not an abstract ethics discussion. The sorting has begun, and every AI company (lab, startup, and buyer) now sits on a spectrum that governments, investors, and enterprise procurement teams are using to make real allocation decisions. If you build on, invest in, or buy from AI companies, the question “what is this company’s relationship with defense” is no longer optional due diligence. It’s a first-order strategic variable.


## The through-line

If you connect these five shifts, they tell a single story about where the AI industry actually is right now, and it’s a different story than the one the model releases tell.

Inference costs are the new binding constraint, not training budgets. Sora didn’t die because the technology wasn’t impressive. It died because serving it cost more than anyone would pay. The monetization layer is migrating from search to conversation, and the first real conversion data says the money will follow. The physical geography of AI is becoming contested ground, cleared at the federal level, blocked by communities at the local level, and targeted on the geopolitical stage. Business model assumptions built on human headcount are breaking, and the per-seat pricing model that powered twenty years of enterprise software is being repriced in real time. And the relationship between AI companies and the state is fracturing along a safety-versus-speed axis that will define market position for years.

None of these shifts were driven by a model release. All of them will shape which companies, and which business models, survive the next twelve months.

The capability phase rewarded the question: *what can we build?* The economics phase is starting to reward a different question entirely: *what can we sustain?* The benchmarks will change again next quarter. That question won’t.

[![](https://substackcdn.com/image/fetch/$s_!4irJ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Facf97850-f10c-487a-9b6d-ee865d8d023f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!4irJ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Facf97850-f10c-487a-9b6d-ee865d8d023f_1024x1024.png)
