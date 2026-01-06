---
title: "The 9 Circles of AI Hell: How to Diagnose and Prevent AI Failures at Work"
author: "Nate Jones"
published: 2025-10-26
url: https://natesnewsletter.substack.com/p/executive-briefing-the-9-ways-ive
audience: everyone
scraped_at: 2026-01-05 19:13:28
---

This one’s personal to me. This is the piece about how to keep your AI initiative out of the papers—or from blowing up the company.

If you’re curious, yes I’ve seen all of these play out in various stages over 2025 at big companies and small.

The good news is that I’ve seen enough AI failures play out that I can start to classify them and understand what’s going on organizationally. Sounds nerdy, but knowing how AI failures work helps me avoid them.

That’s why I’ve kept careful notes and put together a set of predictable patterns of AI failure. My goal is to give leaders at all levels tools to avoid AI failures.

Yes, failure costs money. It can get your name in the paper in the way you don’t want. But after seeing so many of these I’m convinced the worst cost of AI failure is not money.

The real cost of AI implementation failures is measured in people. It’s the wear and tear on teams. It’s people who get de-motivated and burned out because organizations burn a tremendous amount of goodwill getting nowhere on AI. It’s people who give up promising careers or switch to better companies because they don’t want to deal with bad AI projects anymore. The bottom line is that bad AI can cost you your best people.

If you’re reading this and you’re not a leader, the good news is that these patterns are something you can see and address at the team level too. As with so many patterns in AI, they’re fractal: they can recur at large and small scales across a business and unfold in similar ways.

And that’s good news, because it means that even if you’re not a Fortune 500 CEO, you still have a lot of power to diagnose these failures and address them in your area.

Want to know what I found? Here’s all 9 of the AI failures in this week’s guide:

- **The Integration Tar Pit** - Why working prototypes stay stuck in pilot purgatory

  - Useful for people who have working demos but can’t get stakeholder sign-off
- **The Governance Vacuum** - How minor incidents trigger full AI project freezes

  - Useful for people who face security or compliance blockers without clear owners
- **The Review Bottleneck** - Where your productivity gains disappear into human oversight

  - Useful for people who spend more time fixing AI output than creating it
- **The Unreliable Intern** - When supervision costs approach doing it yourself costs

  - Useful for people who can’t predict when their AI will fail catastrophically
- **The Handoff Tax** - Why optimizing one step barely moves the needle

  - Useful for people who automated individual tasks but overall workflow didn’t speed up
- **The Premature Scale Trap** - How successful pilots collapse under real-world conditions

  - Useful for people whose controlled pilot success didn’t transfer to broad rollout
- **The Automation Trap** - When teams work faster but results don’t improve

  - Useful for people who increased activity but didn’t change business outcomes
- **The Existential Paralysis** - Why competitors ship while you’re still strategizing

  - Useful for people who debate AI strategy endlessly without making concrete decisions
- **The Training Deficit & Data Swamp** - What kills adoption after you’ve already paid

  - Useful for people who deployed tools but see low usage or data access problems

I think the prompt I built really matters for this one. Because I want you to get the value for YOUR specific situation, and a deep dive on the particular failure mode you’re grappling with.

That’s what the prompt for this week does: gives you a guided conversation on you unique situation and then helps you think through how to tackle your unique AI adoption challenges so you get back to healthier AI adoption patterns.

I wrote this one for the ones out there who have a sinking feeling that maybe the AI initiative is not going quite according to plan.

If that’s you, I’ve been there, I’ve seen what goes wrong, and I’ve seen how to fix it. There is hope! Let’s jump in and see if we can build better AI systems together.

> ***This is an Executive Circle briefing**, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via this [60 second video](https://youtu.be/KC3GkEnHR-8) explaining what’s in each tier, and you can change your plan [here](https://support.substack.com/hc/en-us/articles/360044105731-How-do-I-change-my-subscription-plan-on-Substack). Enjoy, and back to regular programming Monday!*


## [Grab the Diagnostic Prompt for Your AI Problems](https://www.notion.so/product-templates/Executive-Briefing-9-AI-Adoption-Fails-Custom-Diagnostic-Prompt-2985a2ccb52680c2925ed46ca1fba433?source=copy_link)

This diagnostic prompt matches a stalled AI initiative to one of nine blockers—governance gaps, integration bottlenecks, data architecture problems, premature scaling, and five others.

All you have to do is describe what’s stuck. The prompt identifies the pattern, delivers immediate actions with ownership assignments, suggests success metrics, estimates resource requirements, and specifies when the problem needs C-suite intervention versus delegation. Think of it as a starting point, and as always, push back on AI when you think it gets it wrong.

---


# The 9 Circles of AI Hell: How to Diagnose and Prevent AI Failures at Work

Over months of consulting with Fortune 500 companies, I’ve identified nine specific patterns where AI projects stall. Not the spectacular failures—those are obvious. The slow deaths. Projects that work technically but never ship. Teams that pilot for eighteen months and call it progress.

The patterns recur across industries. The symptoms are observable. The interventions are specific. Most organizations treat each stalled project as unique. They’re not. The same blockers surface repeatedly, and leaders who’ve scaled AI have already documented what breaks and why. The differentiator is pattern recognition speed.

What follows is a diagnostic tool. When your AI initiative stalls, match your symptoms to the patterns below. Apply the targeted intervention. Set a 30-day checkpoint to verify you’re addressing root cause, not symptoms.

---


## When Projects Stay in Pilot Mode


#### **The Integration Tar Pit**

Engineering ships working code in weeks. Sales cycles stretch to 6-12 months. Legal hasn’t signed off. Compliance has concerns. Cross-team stakeholder meetings multiply faster than progress.

Brendan Falk, CEO of Hercules and advisor to multiple Fortune 500 AI deployments, documented this in June 2025: “AI makes the engineering fast. But sales, product, system integration, and implementation are incredibly slow. Customers don’t know what they want, getting stakeholders aligned... legal needs to approve everything.”

Organizations budget for AI development but not for the coordination cost of deploying it. A working prototype isn’t the same as a system that fits your data architecture, compliance requirements, and political landscape.

The fix requires pre-wiring approval paths before writing code. Map every team that touches data, security, or budget. Get preliminary sign-off on the integration approach, not just the technical approach. Assign a deployment PM whose only job is eliminating non-technical blockers—a separate role from the engineering lead. Stage-gate the pilot differently. First gate is “do we have data access and legal clearance?” Not “does the model work?”

If you can’t get five stakeholders in a room for two hours, you can’t deploy AI across their domains. Kill the pilot or escalate. After 30 days, you should be able to name the person responsible for each integration dependency. If you can’t, you haven’t fixed this.


#### **The Governance Vacuum**

Red team exercises reveal vulnerabilities. Security teams flag deployment as “unapproved architecture.” No clear owner for “what happens if the AI does X.” Minor incidents trigger full project freezes.

Traditional security approaches simply don’t work. Prompt injections, hallucinations, and unauthorized tool usage aren’t theoretical risks anymore, and these kinds of risks have to be treated as first-class citizens in any implementation.

Instead, AI governance often gets treated as something you bolt on after the pilot works. In regulated industries, governance failures kill projects faster than technical failures. Security reviews need to start at the requirements phase, not the deployment phase. This is the identity layer—a monitoring system that tracks what every AI agent can access and what it actually does.

Define failure modes explicitly. What does the AI do when it’s uncertain? When it hits a rate limit? When it gets a prompt injection attempt? Establish who can shut down the AI system immediately and what triggers that action. Document this before launch, not after an incident.

Run a tabletop exercise after 30 days simulating an AI incident. If the team can’t articulate response steps in under 10 minutes, governance isn’t ready.

---


## When Quality Is Inconsistent


#### **The Review Bottleneck**

AI generates output fast, but human review takes as long as doing it manually. Engineers report “babysitting” the AI. Output quality varies wildly—sometimes brilliant, sometimes nonsensical. Teams debate whether AI actually saves time.

Sundar Pichai noted in Google’s Q3 2024 earnings that more than a quarter of all new code at Google is generated by AI, then reviewed and accepted by engineers. Google sees 20-30% productivity gains, but hallucinations and context misses demand heavy review. The AI accelerates the wrong part of the workflow—generation, not judgment.

Organizations measure AI success by “how much can it produce” rather than “how much does it reduce total cycle time including review.” Redesign for human-in-the-loop from the start. Don’t build “AI that writes reports.” Build “AI that drafts sections a human assembles.” The human becomes editor, not reviewer-of-everything.

Instrument review time. Track how long humans spend fixing AI output versus how long the task took pre-AI. If review time exceeds 50% of original task time, the AI isn’t helping yet. Narrow the AI’s scope. Google’s 25% figure works because the AI handles well-defined, narrow tasks—boilerplate code, repetitive patterns. Expand scope and review burden explodes.

Build quality feedback loops. When a human corrects AI output, feed that correction back into prompts or fine-tuning. Most organizations treat every AI interaction as independent. That’s why quality doesn’t improve.

After 30 days, measure time-to-completion for ten tasks: five with AI, five without. Include review and editing time. If AI tasks aren’t at least 30% faster end-to-end, you have a review bottleneck.


#### **The Unreliable Intern**

AI handles 80% of a task perfectly, fails catastrophically on the other 20%. Teams can’t predict when failures will occur. Supervision cost of the AI approaches the cost of just doing the work. Discussions of “will this ever be reliable?” start happening.

Andrej Karpathy, formerly of OpenAI, spoke on the Dwarkesh Podcast in October 2025: “They just don’t work. They don’t have enough intelligence, they’re not multimodal enough, they can’t do computer use... They don’t have continual learning. You can’t just tell them something and they’ll remember it.” Agents are “cognitively lacking” like unreliable interns. More than 60% of enterprise pilot agents need constant human tweaks.

Organizations deploy AI on tasks that require judgment, memory, or context that current systems can’t handle. The task isn’t AI-ready yet. Audit the task for “intern-suitability.” Would you assign this to a smart but forgetful intern who can’t learn from mistakes? If no, current AI isn’t ready.

Break complex tasks into subtasks. AI handles data retrieval and formatting. Humans handle synthesis and judgment. Set supervision ratio thresholds. If the AI requires more than 20% supervision time, the economics don’t work. Shelve it or narrow scope.

Karpathy forecasts a decade until agents have the capabilities enterprises need. Invest in learning and experimentation, but don’t bet the business on agents working reliably today. After 30 days, calculate the actual supervision-to-output ratio. If it exceeds 1:5, the task is too complex for current AI.

---


## When Scale Doesn’t Match Expectations


#### **The Handoff Tax**

AI handles one step in a multi-step process. Handoffs between AI and humans create delays. The overall cycle time barely improves. Teams realize they’ve optimized one bottleneck while creating two new ones.

This is the “faster horse” problem. You automated the wrong part of the workflow. Automating individual steps within legacy workflows produces marginal gains. Redesigning the entire workflow around what AI does well produces step-function improvements.

Map the full workflow before deploying AI. Identify not just what’s slow, but what creates dependencies. AI should eliminate handoffs, not create new ones. If your workflow has five human steps and you automate step three, you still have four handoffs. Redesign so AI handles steps 1-3 as a unit, or steps 3-5 as a unit.

Measure cycle time for the entire process, not individual steps. If you reduce step three from two hours to 30 minutes but overall cycle time only drops 10%, the handoffs are eating your gains. After 30 days, if cycle time improvement is less than half your per-step time savings, you have handoff tax.


#### **The Premature Scale Trap**

Leadership sees a successful pilot and immediately pushes for company-wide rollout. The pilot worked in a controlled environment with motivated users and clean data. At scale, edge cases multiply. Support costs explode. Quality degrades.

This pattern shows up when success metrics from the pilot don’t transfer to production. The pilot team understood the AI’s limitations and worked around them. The broader organization doesn’t. They treat AI as infallible, hit edge cases, and blame the tool.

Before scaling, document every workaround the pilot team used. Those workarounds become training for the broader rollout. Test with skeptical users, not just enthusiastic ones. Pilot in the messiest part of the organization, not the cleanest.

Scale in stages. Go from five users to 25, not five to 500. Each stage reveals new failure modes. Build support infrastructure at each stage before expanding. After 30 days, if support tickets per user are increasing rather than decreasing, you scaled too fast.

---


## When Strategy Feels Stuck


#### **The Automation Trap**

AI speeds up existing processes but doesn’t change outcomes. Teams are busy but not more effective. Activity increases, results don’t. Leadership realizes they’ve automated inefficiency.

This happens when organizations deploy AI before asking whether the process should exist at all. Companies automate approval workflows that shouldn’t require approval. They speed up report generation for reports no one reads.

Before deploying AI, ask: “Should we be doing this at all?” Many automated tasks should be eliminated, not sped up. Measure outcome metrics, not activity metrics. Don’t track “time saved per task.” Track “did customer satisfaction improve?” or “did we reduce headcount requirements?”

Prototype the “zero-process” version. What if AI eliminated this entire workflow? Could customers self-serve? Could systems auto-resolve? Start there, then compromise back to reality. Use AI deployment as a forcing function to kill zombie processes—workflows that exist purely because “we’ve always done it this way.”

After 30 days, name the outcome metric that should improve for each automated process. If you can’t, you’re automating for automation’s sake.


#### **The Existential Paralysis**

Leadership debates whether AI will cannibalize core business. Conflicting directives: “move fast” versus “don’t risk the franchise.” AI investments feel defensive rather than offensive. Strategy discussions loop endlessly without decisions.

Satya Nadella spoke at Microsoft’s September 2025 town hall: “I’m haunted by the possibility that Microsoft’s biggest businesses could be disrupted by AI... The biggest threat to Microsoft is AI, and it could wipe out a $3.8 trillion giant.” Despite $80 billion in AI investment and 30% automation, strategic decisions remain human-led because outcomes are unpredictable.

AI’s pace of change outstrips strategic planning cycles. By the time you have a five-year AI strategy, the landscape has shifted. Adopt a portfolio approach. Allocate budget across three horizons: fast payoff incremental improvements, 2-3 year bets on emerging capabilities, and option value on 5-10 year wildcards. Don’t try to predict which wins—diversify.

Set decision-making speed targets. Complex AI strategy questions get 90 days maximum. If you can’t decide in 90 days, the uncertainty is structural. Make your best guess and commit. Separate “learning” investments from “scaling” investments. Some AI projects teach you what’s possible—small budget, high learning. Others scale proven wins—large budget, clear ROI. Mixing the two creates paralysis.

Scenario-plan the disruption explicitly. What if your core product is 50% automated in three years? What if competitors offer it free? War-game these scenarios so they’re not abstract fears. After 30 days, leadership should be able to articulate three specific AI investment decisions made in the last 90 days. If they can’t, you’re stuck in analysis mode.

---


## When Adoption Stalls


#### **The Training Deficit**

Low adoption rates despite tool availability. “We tried AI, it didn’t work” sentiment. Users revert to old workflows. Complaints that AI “makes more work, not less.”

Chris Burchett, SVP at Blue Yonder, has spoken about this extensively. His take is that organizations will need to address two main things before they can properly implement AI: their people and their data. A cultural shift will be needed that fundamentally acknowledges AI as a teammate.

Organizations deploy tools before teaching people how to use them effectively. Training gets treated as one-time onboarding, not ongoing capability building. Allocate 3-6 months for training before expecting ROI. Burchett’s timeline is real. Budget for this upfront, not as an afterthought when adoption stalls.

Train on workflows, not tools. Don’t teach “how to use ChatGPT.” Teach “how to research competitive intelligence using AI” or “how to draft customer emails using AI.” The task is the entry point, not the tech. Create AI champions, not mandates. Identify early adopters who’ve seen wins. Have them teach peers. Adoption spreads peer-to-peer faster than top-down.

Instrument usage and intervene. Track who’s using tools and who isn’t. For non-adopters, run one-on-one sessions to understand blockers. Often it’s “I tried once, got a bad result, gave up.” After 30 days, survey 20 employees. Ask: “Do you use the AI tool regularly?” and “Why or why not?” If “why not” answers cluster around lack of training, you have a training deficit.


#### **The Data Swamp**

AI can’t access the data it needs. Data quality issues surface only after deployment. Different teams have incompatible data formats. AI outputs are wrong because inputs are messy.

Burchett again: “These organizations will also need to have a big data strategy.” The combination of people and data predicts success. Most failures stem from data silos that prevent AI from functioning.

Data infrastructure work is boring, expensive, and slow. AI deployment is exciting and fast. Organizations skip the infrastructure step. Conduct a data audit before AI deployment. Catalog what data exists, where it lives, who owns it, and what quality issues are known. If you can’t complete this audit in four weeks, your data isn’t ready.

Prioritize data access over data perfection. AI can handle messy data better than no data. Focus on getting access first, improving quality second. Assign data stewards. For each AI project, name the person responsible for ensuring data availability and quality. Not the AI team—the data team.

Build connectors, not copies. Avoid creating duplicate data warehouses “just for AI.” Build APIs or connectors so AI accesses live data. Duplication creates synchronization problems. After 30 days, the AI should be able to access 80% of the data it needs without manual intervention. If not, you have a data architecture problem.

---


## Why This Matters

The typical failure mode for AI projects: Try something. It doesn’t work. Conclude “AI isn’t ready” or “our organization isn’t ready.” Move on.

This diagnostic forces precision. Which pattern of failure is this? What specific intervention does that pattern require? When will we know if the intervention worked? As I’ve said over and over again, precision matters.

It replaces vague frustration—”AI is hard”—with diagnostic clarity: “We have Falk’s integration bottleneck, and here’s how to fix it.”

But there’s something else worth seeing here. After documenting these nine patterns, what strikes me is how often the same underlying issues keep surfacing in different forms.

Take measurement. The governance vacuum, the review bottleneck, the automation trap—they all stem from organizations tracking metrics that feel productive but don’t connect to actual outcomes. You’re measuring AI accuracy when what matters is whether the supervision cost makes it worthwhile. You’re tracking time saved per task when what matters is whether customers are happier or whether you actually reduced headcount needs. The fix isn’t better AI. It’s having the discipline to measure what your business actually cares about.

Or take ownership. The integration tar pit persists because nobody can make the cross-functional decision. The training deficit happens because training is “IT’s problem” until adoption stalls and suddenly it’s “the business unit’s problem.” The data swamp sits there because data access has no steward with real authority. These aren’t nine separate coordination failures—they’re all the same pattern. Someone needs to own the decision, with actual authority to act, and most organizations can’t or won’t assign that clearly.

Then there’s the infrastructure gap. Organizations skip the boring work—the data connectors, the staged rollouts, the 3-6 months of capability building—because AI deployment feels urgent and infrastructure work doesn’t. But the training deficit, the premature scale trap, and the data swamp all punish this choice. The leaders who’ve successfully scaled AI put in months of foundational work before expecting returns. They knew that infrastructure determines whether pilots ever become products.

And finally, there’s the systems thinking problem. Organizations treat AI as a drop-in replacement for human tasks within existing workflows. That’s what creates the handoff tax—you optimized step three but the four handoffs around it ate your gains. That’s the automation trap—you sped up a process that shouldn’t exist at all. The pattern that works is harder: ruthlessly redesigning workflows around what AI does well, not just plugging AI into what you already do.

So many leaders in AI have already paid the learning tax for these lessons. My goal is to help you pattern-match your failure (or risk of failure), so you can skip ahead to the intervention. But the real value is recognizing that most of these failures share common roots. There are patterns here. Fixable patterns. Fix the measurement, the ownership, the infrastructure, and the systems thinking, and you won’t need to diagnose most of these patterns in the first place. They just won’t happen.

[![](https://substackcdn.com/image/fetch/$s_!Ms7g!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4753a10c-33f4-487d-bd6a-44717923ae02_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Ms7g!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4753a10c-33f4-487d-bd6a-44717923ae02_1024x1024.png)
