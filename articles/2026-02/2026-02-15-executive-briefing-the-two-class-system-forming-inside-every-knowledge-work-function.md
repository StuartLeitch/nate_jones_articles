---
title: "Executive Briefing: The Two-Class System Forming Inside Every Knowledge Work Function"
author: "Nate Jones"
published: 2026-02-15
url: https://natesnewsletter.substack.com/p/executive-briefing-the-two-class
subtitle: "Watch now | Code is about to cost nothing, but knowing what to build? Well, that's about to cost everything."
audience: everyone
scraped_at: 2026-02-22 15:12:21
---

In July 2025, Jason Lemkin — one of the most respected operators in SaaS — watched a Replit AI agent delete his production database. The agent didn’t hallucinate — it did exactly what it was allowed to do, because nobody had specified where its authority ended. The database held 1,206 executive records and 1,196 companies. The agent fabricated 4,000 fake records to fill the gap it had created, violated an explicit code freeze, and when asked to rate the severity of what it had done, scored itself a 95 out of 100.

That same month, three engineers at StrongDM spun up a software factory — the kind of operation that would have required a ten-person team eighteen months earlier. AWS launched Kiro that same month, an IDE built around a radical premise: the most important thing a developer can do is write the specification, not the code. And Anthropic quietly disclosed that Claude Code’s own codebase is now roughly 90% written by Claude Code itself.

Read those back to back and they sound like contradictions, but they’re the same story — the cost of producing software is collapsing so fast that the bottleneck has already moved — from “can we build it” to “can we specify exactly what should be built, how it should be validated, and where the boundaries are.” The organizations and individuals who understand that shift are pulling away. The ones who don’t are about to discover that hiring more engineers, buying more seats, and running more workshops solves a problem that no longer exists.

I’ve been thinking about this pattern for months, and the deeper I look the less comfortable the implications get — not because the technology is failing, but because it’s succeeding in ways that fundamentally reprice what it means to be valuable in knowledge work.

**This briefing covers:**

- **The translation trap.** Why the most popular mental model for AI’s impact on jobs — that it’s “just translation” — breaks down exactly where the stakes are highest, and what replaces it.
- **The specification bottleneck.** How the scarce resource shifted from production to definition, why most organizations haven’t noticed, and what the early evidence says about who captures the value.
- **The bifurcation.** The emerging two-class system among engineers — and why it’s about to replicate across every knowledge function from legal to finance to marketing.
- **The J-curve.** Historical evidence that productivity revolutions destroy jobs before they create them, why we’re likely in the trough right now, and what the recovery pattern actually looks like.
- **The executive decision.** How to identify where you need headcount when the valuable skill is specification — and how to restructure hiring, evaluation, and org design around a capability most companies can’t yet define.

Every framework people reach for to understand this moment asks the wrong question. They ask whether AI replaces workers. But when the cost of production collapses, the interesting question is never “do we still need producers?” It’s always “what becomes the new bottleneck?” Let me show you where it moved, what it means for your headcount decisions, and why the answer is harder than either side of the automation debate wants to admit.


## LINK: [Executive Circle WhatsApp group](https://chat.whatsapp.com/LqpF3i5wDYv1EdraJYKplL?mode=gi_c)

Something I’ve wanted to build for a while: a direct line between the people reading these briefings. We just launched an Executive Circle WhatsApp group — senior leaders working through the same strategic decisions we cover here, sharing what’s actually working and what isn’t. No fluff, no LinkedIn energy. If you’re an Executive Circle member, come join the conversation.


## LINK: [Grab the Prompts](https://www.notion.so/product-templates/Prompt-Kit-The-Future-of-Jobs-3065a2ccb52680da9c2af1bb12b70518?source=copy_link)

Most workforce planning conversations about AI start with the wrong question — “which roles does AI replace?” — and end with a training budget that solves nothing. These prompts exist because I’ve watched that pattern play out enough times to know where it breaks. They force four specific exercises most leadership teams skip: mapping which parts of each role are appreciating versus depreciating, testing candidates for specification skill instead of production speed, running an honest organizational diagnostic that doesn’t let you hide behind adoption metrics, and designing the restructured function before you’re forced into it by attrition. The Readiness Audit in particular exists because every executive I’ve talked to thinks they’re further along than they are — and the gap between perception and reality is where the expensive mistakes live.


## The translation trap

François Chollet — the creator of Keras and one of the sharper thinkers on machine intelligence — has a useful model for what LLMs do. He frames them as translation engines. You give them input in one modality, they produce output in another. Natural language in, code out. Requirements in, architecture out. Vague idea in, structured document out.

The frame is useful because it cuts through the mysticism. An LLM isn’t “thinking” or “reasoning” in any meaningful sense. It’s translating between representations — and it’s gotten extraordinarily good at that translation. Good enough that for many routine tasks, the quality of the translation is indistinguishable from what a competent professional would produce.

But the frame breaks down exactly where the stakes get highest, and the break matters for every workforce decision you’re about to make. Translation assumes the source material is clear. When you hand a human translator a document in French, the document is complete — the meaning exists, the translator renders it faithfully in English. The quality of the output depends on the skill of the translator. But when you hand an LLM a vague specification and ask it to produce code, the meaning doesn’t fully exist yet. The specification has gaps. The LLM fills those gaps with statistically plausible completions — which is to say, it invents things that look right but may not be right, and it does so with absolute confidence and zero disclosure.

This is where the Lemkin incident becomes diagnostic rather than anecdotal. The Replit agent didn’t fail at translation. It translated perfectly — it just translated a specification that was incomplete. Nobody had defined where the agent’s authority ended, what it was forbidden to touch, or what “done” meant in a way the system could enforce. The agent did exactly what a translation engine does with ambiguity: it filled the gaps. The fake records it fabricated? Statistically plausible completions of an underspecified task.

The better frame isn’t translation. It’s specification fidelity. The quality of AI output is a function of the quality of the specification it receives — and that relationship is non-linear. A slightly vague specification doesn’t produce a slightly wrong output. It produces a confidently wrong output that looks polished enough to ship, which is significantly more dangerous than an obviously broken one.

This is the trap most organizations are walking into. They’re investing in the translation layer — better models, more seats, faster inference — while ignoring the specification layer entirely. They’re optimizing the part that’s getting cheaper while neglecting the part that’s becoming the binding constraint.


## The specification bottleneck

I want to be careful about how I frame this, because the evidence is still emerging and some of it cuts in directions that neither the AI optimists nor the pessimists want to hear. But the pattern is becoming hard to ignore.

The cost of producing software is in free fall. Not declining — collapsing. Consider the revenue-per-employee figures that are emerging from the first generation of AI-native companies. At 60 employees and $500 million ARR in early 2025, Cursor was generating over $8 million per employee — before crossing $1 billion ARR later that year with roughly 150 people on payroll. Midjourney generated $50 million in its first year with 11 employees. By 2023 it hit $200 million with about 40 people. By 2025: $500 million with still fewer than 170. Lovable went from zero to $50 million ARR in six months, then crossed $100 million in eight months with 45 employees.

These aren’t outliers anymore. They’re a pattern. Y Combinator’s Winter 2025 batch included startups where a quarter of the codebases were 95% AI-generated — built by skilled engineers who chose not to write the code themselves because the production layer had become cheap enough to delegate. Companies are reaching $10 million in revenue with fewer than ten people.

But here’s where the data gets harder to reconcile. The production cost is falling and the quality problems are getting worse simultaneously, because the specification problem isn’t being addressed.

CodeRabbit’s December 2025 analysis of 470 GitHub pull requests found that AI-assisted code generates 1.7 times more issues overall than human-authored code — 10.83 findings per PR versus 6.45 for human submissions. At the 90th percentile, AI-assisted PRs reached 26 issues per change. Analysis of Google’s 2025 DORA data found that alongside 90% AI adoption among software teams, organizations saw an estimated 9% climb in bug rates, a 91% increase in code review time, and a 154% increase in pull request size. Individual developers report being more productive. Organizational delivery metrics stay flat. The DORA report’s own conclusion: AI acts as a “mirror and a multiplier” — it magnifies the strengths of high-performing organizations and the dysfunctions of struggling ones.

Read that finding carefully because it’s the specification bottleneck in a single sentence. The organizations where AI works well are the ones that already had clear specifications, defined workflows, and systematic quality gates. The organizations where AI makes things worse are the ones that were depending on individual judgment and tribal knowledge — the ones where the specification lived in someone’s head and the production skill covered for it.

When production was expensive, vague specifications were survivable. The developer writing the code was also interpreting the spec, filling gaps with domain knowledge, catching ambiguities through the act of implementation. That error-correction was invisible because it was embedded in the production process. Now that production is being automated, the error-correction disappears — and every gap in the specification flows straight through to the output.

The bottleneck has moved. The scarce, valuable skill is no longer “can you build it?” It’s “can you specify exactly what should be built, how it should be validated, what it’s allowed to touch, and where the boundaries are?” And that skill — precise specification under uncertainty — turns out to be much rarer than anyone assumed when it was bundled invisibly inside the production process.


## The bifurcation

This is where I need to be honest about what I’m seeing and what I’m uncertain about, because the implications are significant and the data is still early.

What the evidence suggests is an emerging two-class system among software engineers — and I want to be careful not to overstate this, but the pattern is showing up across enough data points that it’s worth naming.

On one side: engineers who understand specification deeply — who can define systems precisely, design verification, construct the guardrails that keep AI output reliable at scale. These engineers are becoming dramatically more productive. StrongDM’s three-person team, building what would have required ten people eighteen months earlier, is one example. Cursor’s engineers, each managing a fleet of AI coding agents, is another. The multiplier effect for someone who can specify well and orchestrate AI execution is genuinely unprecedented.

On the other side: engineers whose primary value was production-layer skill — writing code, implementing designs, translating requirements into working software. That skill is being repriced in real time. Entry-level software postings have declined sharply from their 2022 peak, with some large firms cutting active job postings by as much as 90%. New graduates now represent just 7% of Big Tech hires, down 25% from 2023. The entry-level market is contracting not because companies need fewer outcomes, but because the production cost of those outcomes is collapsing.

The middle ground is where most engineers actually sit: there’s a large population of mid-career engineers whose work blended specification and production, and for many of them the ratio is shifting beneath their feet. The production portion of their role is worth less every quarter. The specification portion is worth more. But most organizations can’t yet distinguish between the two — their job descriptions, interview processes, leveling rubrics, and compensation structures still treat software engineering as a unified discipline where production skill is the core competency.

Here’s why this matters beyond engineering. The same dynamic is beginning to appear across knowledge work. Legal research is being automated, but knowing which question to research and how to evaluate the answer — that’s getting more valuable, not less. The same pattern shows up in finance, where defining the decision an analysis should inform matters more than building the model, and in marketing, where specifying strategy, audience, and success criteria precisely enough to generate content that actually converts has become the hard part.

In every function, the pattern is the same: production costs collapse, specification becomes the bottleneck, and the value distribution bifurcates between people who can specify precisely and people whose primary skill was the production that’s being automated.

I’m hearing this from enough directions now — from CTOs restructuring engineering orgs, from legal ops leaders rethinking paralegal roles, from marketing executives watching their content teams — that I think the pattern is real even if the magnitude is still debatable. The bifurcation is coming for every knowledge function. Engineering is just the canary.


## The J-curve

Here’s where I want to push back against both sides of the automation debate, because both are making the same mistake — they’re reasoning from the current moment as if it’s the end state.

The historical evidence on productivity revolutions is remarkably consistent: they destroy jobs before they create them. Not because the technology fails, but because the transition follows a J-curve pattern — output per worker increases, the old roles contract, and the new roles that eventually absorb the displaced workforce haven’t been invented yet or haven’t scaled to absorb the demand.

Manufacturing went through this. When automation hit factory floors, the immediate effect was displacement. Productivity per worker spiked. Employment in traditional manufacturing roles contracted. Census Bureau research on manufacturing productivity shows that recovery took roughly four years — four years where the workforce was restructuring, new roles were emerging, and the people displaced from production were learning to work differently. The roles that came back were not the roles that were lost. They were higher-skilled, higher-paid, and focused on design, oversight, quality, and system management rather than manual production.

The telephone operator parallel is worth considering because the timeline and the psychology are instructive. At peak employment in the 1920s, the telephone system employed hundreds of thousands of operators, and the work was considered skilled, respectable, and essential. Automation made the operators unnecessary. The telephone system didn’t shrink — it exploded in scale, reaching orders of magnitude more users. But the roles that scaled weren’t operator roles. They were engineering roles, maintenance roles, design roles, sales roles. The people who lost operator jobs didn’t naturally flow into those new positions. The transition was painful, slow, and uneven.

I think we’re in the J-curve trough right now for software engineering, and we’re about to enter it for several other knowledge work functions. The METR study — where developers using AI were 19% slower on real-world tasks despite believing they were 24% faster — is a trough symptom. The DORA finding that individual productivity rises while organizational delivery stays flat is a trough symptom. The entry-level job market contracting while demand for senior specification-level engineers increases is a trough symptom.

The good news, if you want to call it that, is that J-curves resolve. The bad news is that they resolve on a timeline measured in years, not quarters, and the roles that emerge on the other side look nothing like the roles that were lost. For executives, this means workforce planning needs to account for a transition period where you’re simultaneously shedding production capacity you no longer need and building specification capacity that doesn’t yet have a job title, a career ladder, or a clear training pipeline.


## The executive decision

Your headcount plan is built around a production bottleneck that no longer exists. The new bottleneck is specification — and most organizations have no idea how to hire for it, measure it, or allocate headcount around it.

This section is the reason this briefing exists, so I want to be concrete.

**Mapping your roles.** Every function in your organization has a specification layer and a production layer. In engineering, the specification layer is architecture, system design, requirements definition, verification design, and acceptance criteria. The production layer is writing code, implementing designs, and building to spec. In legal, the specification layer is identifying the right question, defining the scope of analysis, and establishing evaluation criteria. The production layer is research, drafting, and document assembly. In finance, the specification layer is defining what decision the analysis should inform and what counts as a good answer. The production layer is building models, running analyses, and generating reports.

The exercise is blunt but necessary: for each function, identify which roles are primarily specification, which are primarily production, and which blend the two. Then ask what happens to each category as production costs continue to fall.

**Hiring for specification.** Most interview processes are designed to evaluate production skill. Can you write code? Can you draft a contract? Can you build a financial model? These are still relevant, but they’re no longer the differentiating capability. The differentiating capability is whether someone can specify precisely under uncertainty — and most organizations have no way to test for that.

What specification skill actually looks like in practice: the ability to define acceptance criteria before work begins, to anticipate failure modes and build verification into the workflow, to distinguish between what the system should do and what it’s allowed to do, to write constraints that are enforceable rather than aspirational. The StrongDM team’s charter — “code shall not be written by humans, code shall not be reviewed by humans” — works because they spent their specification effort on defining 6,000 to 7,000 lines of detailed behavioral specifications and satisfaction testing scenarios. The humans don’t write code. They specify. And that specification skill is what makes the entire factory work.

Your interview process should test for this. Can the candidate take an ambiguous requirement and turn it into a precise specification with clear acceptance criteria, defined failure modes, and explicit boundaries? Can they design verification for an output they didn’t produce? Can they write constraints that a system could enforce, not just guidelines that a human might follow? If your interviews are still primarily testing whether someone can produce the artifact — write the code, draft the document, build the model — you’re hiring for a skill whose value is in structural decline.

**Restructuring evaluation.** If specification is the valuable skill, your leveling rubrics need to reflect that. Promotion criteria that reward production speed and volume are misaligned with where the value is moving. The engineer who writes the most code is not necessarily more valuable than the engineer who writes the most precise specification. The analyst who produces the most reports is not necessarily more valuable than the analyst who asks the question that makes the right decision obvious.

This is harder than it sounds because specification work is less visible than production work. Code ships. Reports deliver. Specifications feel like “planning” — and in most organizations, planning is lower-status than execution. If you want specification to be the valued capability, you have to make it visible, measurable, and rewarded.

**Organizational design.** The emerging model — visible at StrongDM, at Cursor, at the AI-native startups in YC’s Winter 2025 batch — separates specification from production structurally. Small teams of senior specifiers define what should be built. AI systems (and in some cases, larger teams of junior producers augmented by AI) handle production. Verification sits between them as its own capability, not an afterthought.

This looks different from the traditional engineering org where specification and production are blended in every role. It looks more like the manufacturing model after automation — where design engineers and production systems are separate functions with explicit interfaces between them. That model took manufacturing years to develop. Knowledge work doesn’t have years, because the production cost collapse is happening faster than it did in manufacturing and the AI systems don’t need to be physically rebuilt to adopt new capabilities.


## The audit

Eight questions, yes or no. Answer honestly — if you’re not sure, the answer is the one that is probably the thing keeping you up at night.

1. Can you identify which roles in your organization are primarily specification roles versus primarily production roles?
2. Do your job descriptions and interview processes explicitly test for specification skill — the ability to define acceptance criteria, failure modes, and enforceable constraints?
3. Do your leveling rubrics and promotion criteria reward specification quality, or primarily production volume and speed?
4. For your highest-stakes workflows, is there a defined boundary between AI generation and human decision — enforced by the system, not by policy?
5. Do you know which functions in your organization are most exposed to the specification bottleneck — where vague requirements are currently being saved by expensive human production skill?
6. Is your headcount plan for the next 12 months still built primarily around production capacity, or does it account for the shift toward specification?
7. Can you name three roles in your organization that didn’t exist two years ago and exist specifically because specification has become the binding constraint?
8. Do you have a training pipeline for specification skill — not prompt engineering, but the ability to define requirements, design verification, and construct enforceable constraints?

If you answered “no” to most of these, your workforce strategy is built for a bottleneck that has already moved. That’s not a moral failing — it’s where most organizations are. The question is whether you start adjusting now or discover the misalignment when production costs drop the next 50% and the specification gap becomes impossible to staff around.

**The escalation question.** Ask your CHRO, your CTO, or whoever owns workforce planning: *For our highest-value workflows, can you tell me where the specification layer is — and whether the people in those roles know that specification, not production, is now the primary skill we’re paying for?*

If they answer in terms of tools, training programs, or adoption metrics, they’re still thinking in tool-mode. If they answer in terms of role definitions, hiring criteria, and organizational structure — they’re starting to see it.

**What to do in the next 30 days.** Pick one function — engineering, legal, finance, marketing — and run the mapping exercise. Identify the specification roles, the production roles, and the blended roles. Then ask: if production costs in this function fall another 50% in the next 18 months, which of these roles become more valuable and which become less? Let the answer inform your next hiring decision, your next leveling conversation, and your next budget allocation.

The organizations that figure out how to hire for, measure, and develop specification skill are going to have a structural advantage that compounds. The ones that keep staffing for production in a world where production is approaching commodity pricing are going to wonder why their AI investments aren’t producing returns — and the answer will be that they optimized the cheap part and neglected the part that was actually scarce.

The bottleneck moved. Your workforce plan should move with it.

[![](https://substackcdn.com/image/fetch/$s_!ToJn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fea4149c0-bc64-42a8-86a7-d8da7039ed2f_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!ToJn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fea4149c0-bc64-42a8-86a7-d8da7039ed2f_1024x1024.png)
