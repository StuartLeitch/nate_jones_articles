---
title: "Web Sources:"
author: "Nate Jones"
published: 2025-10-10
url: https://natesnewsletter.substack.com/p/i-built-a-20-prompt-set-to-kill-ai
audience: everyone
scraped_at: 2026-01-05 19:15:20
---

AI slop is killing companies.

In the last 2 years we’ve taken the cost of content down to zero, so the supply of content has gone through the roof.

There’s not time to read it all. So we don’t. We complain about it, but we think ther’es nothing we can do.

Not anymore! I’ve been staring at the problem for months, and I finally realized there’s a way to use AI to fight slop here. A really sharp prompt, thoughtfully deployed, can vastly simplify the review process for artifacts at work, turning an impossible pipeline of content into a self-policing feedback loop.

Imagine if instead of wondering if an AI has written a good or bad Product Requirements Document and having to read it line by line you could get a quick read and feedback instantly from a prompt! Same with blog posts. Same with customer emails. You get the idea. It’s going to save your team DAYS.

Here’s the full list of anti-slop editor prompts I built:

**The High-Volume Explosion (10-100x increase):**

1. Blog posts and articles
2. Social media content (LinkedIn, Twitter, etc.)
3. Email campaigns and sequences
4. Sales outreach (cold emails)
5. Ad copy (Google, Meta, LinkedIn)
6. Support responses
7. Product descriptions
8. Meeting summaries
9. Video scripts
10. SEO content briefs
11. Landing page copy
12. Follow-up emails
13. Case study drafts
14. Email newsletter content
15. Internal communications (Slack responses, etc.)

**The High-Impact Category (lower volume but expensive when bad):**

16. PRDs and feature specs

17. Technical documentation

18. Executive memos

19. Client deliverables and reports

20. Proposals and pitch decks

---

Quite a list! Look, the point is NOT to stop human eyes or human reviews.

The point is to make human reviews matter more.

Andrej Karpathy said something that’s stuck in my mind for months:“99.9% of attention is about to be LLM attention, not human attention” (March 12, 2025 tweet).

He’s right. And I think we need to start building systems that assume that the human attention needs to be on the correct 0.1% (or 1% if we’re aggressive) of work.

That’s what this prompt system is designed to do for you. Put your human attention where it matters most. Incidentally, by doing this you get all sorts of benefits!

- As a writer, you learn to write better, because you have a clean feedback loop from prompt to artifact to specific, actionable feedback
- As a professional, the AI learns to work with you better (especially systems with memory) as you use this system
- As a manager, your team can save you work by doing first round themselves
- As leader, you can save your teams days of work and increase quality with this system
- As an agentic systems builder, you get some seed prompts you can use to construct automated pipelines to tackle this stuff

It all rests on having an excellent quality gate, and that’s what I’ve focused on here.

Have fun, and go kill some slop today :)

*PS. If you’re wondering if I used a prompt to check my work and help with this article, the answer is yes! Working with a prompt improved my writing significantly.*


### *[Grab the full prompt set for fixing slop here](https://www.notion.so/product-templates/Prompts-to-Fix-Slop-2875a2ccb52680a79752ee9b3b7eef29?source=copy_link)*

These 20 prompts are designed to cover the top 20 most sloppy artifacts in the workplace. You can read on to see what’s driving slop, where we are trying to address the problem today, and a full discussion of why I picked the 20 prompts.

To use these, just pull the prompt for your artifact (search for what you want on the page—20 is a lot), paste it into a thinking model like GPT-5 or Claude 4.5, and add the artifact you want to check.

If you want to modify the prompt, they’re all in a consistent format (discussed below) so you can modify them easily.

---


## The AI Slop Problem Is Fixable

Every business I talk to has the same problem, and they don’t know how to name it. Their content marketing team went from publishing one blog post a week to ten posts a day. Their sales team went from sending 10 personalized emails daily to 100. Their social media manager went from 5 posts a week to 50.

And nobody knows if any of it is any good. Because nobody has time.

And we’re all acting like it isn’t fixable—you need to believe we can fix it! And it doesn’t take hero ball or best intentions. It just takes smart LLMs deployed with good prompts. Yes, we can take AI to fight AI slop lol

Let me show you what this looks like in practice. The data is stark: **93% of marketers now use AI to generate content**, with teams reporting they save an average of **3 hours per piece of content** (Synthesia, 2025). Content volume has exploded—organizations that used to produce 60 blog posts a year are now producing 480+, an **8x increase** with the same headcount.

But here’s the problem: **Ahrefs analyzed 900,000 newly published web pages in April 2025 and found 74.2% contained AI-generated content**. Only 25.8% were purely human-written. And engagement? Email marketing data shows **email volume increased 15% year-over-year**, but response rates are dropping as personalization disappears.

Or take sales: teams have gone from 200 emails a day to 2,000—a **10x increase**. The absolute numbers look better because of volume, but response rates dropped from 8% to 2% as generic AI-generated outreach floods inboxes.

This is what’s actually happening. Not theoretical. Not hypothetical. Right now, across thousands of companies, people are producing 10-100x more content than they were a year ago. And they have no systematic way to know if it’s good.


## Why This Is Happening (It’s Not Just “AI Exists”)

The obvious answer is “because AI makes it easy.” That’s true but shallow. Let me show you the deeper forces at work. We tend to complain about AI slop (fair) but not take the time to understand why it’s occurring—and that’s key to fixing it.

**The economics changed.** The marginal cost of producing content went to near-zero. It used to cost real money and time to produce a blog post—maybe $500 in labor, four hours of someone’s day. Now it costs $0.20 in API calls and 10 minutes. When something becomes 100x cheaper, people produce 100x more of it. That’s not laziness, that’s economics. Microsoft AI CEO Mustafa Suleyman predicts “near-zero marginal cost for new knowledge production” is arriving within 15-20 years—we’re already seeing it happen.

**The incentives are backwards.** Volume metrics are easy to measure—number of blog posts published, number of emails sent, number of social posts live. Quality metrics are hard—engagement rates, conversion rates, actual business outcomes. So people optimize for what’s measured. “We published 200 pieces of content this quarter” sounds better in a performance review than “we published 20 pieces of content and three of them actually drove deals.”

**Competitive pressure is real.** Your competitors are publishing 10x more content. Your sales team sees competitors sending more emails. Your social team sees other companies posting constantly. There’s genuine fear: “What if we miss opportunities by not producing more?” Nobody wants to be the company that lost deals because they didn’t publish enough content. Even if that’s not how it works.

**The tools make it trivial.** I can open Claude right now and say “write me 50 blog post drafts about enterprise software trends” and get them in three minutes. The friction disappeared. There’s no natural brake on production anymore. It used to be that writing was hard, so you only wrote when you had something to say. Now writing is easy, so you write all the time.

**Platform algorithms reward volume.** LinkedIn’s algorithm favors accounts that post frequently. Google rewards sites that publish regularly. Social media platforms want engagement, and more posts mean more chances to get engagement. The platforms themselves incentivize volume over quality. Some platforms like Mediavine have started terminating accounts for AI content overuse, but that’s the exception, not the rule.

**Loss aversion kicks in.** “What if the one post I didn’t publish would have gone viral?” “What if the one email I didn’t send was the one that would have gotten a response?” Better to send everything and see what sticks. This is the same psychology that makes people buy lottery tickets.

Put these forces together and you get what we’re seeing: an explosion of content production with no corresponding increase in quality control capacity. Human attention didn’t scale. We still have 24 hours in a day. We still have the same number of managers who can review content. But production scaled 100x.

That creates a fundamental mismatch.


## What People Are Trying (And Why It Doesn’t Work)

Everyone I talk to knows they have a slop problem. They’re trying to solve it. Here’s what they’re doing, and why each approach fails:

**Approach 1: Blame the writers**

“Just write better.” “Think before you use AI.” “Don’t ship garbage.”

This doesn’t work because it’s not a motivation problem, it’s a systems problem. Your writers aren’t lazy or stupid. They’re responding rationally to the incentives you’ve set up. You’re measuring them on volume, giving them tools that make volume easy, and not giving them any systematic way to evaluate quality before shipping.

Telling someone to “write better” without defining what better means, without giving them objective feedback, without changing the incentives—that’s just hoping really hard that the problem fixes itself.

**Approach 2: Training programs**

“Let’s run a workshop on quality content.” “Here’s what good blog posts look like.” “Review these examples.”

Training helps for about three weeks. Then people forget. Then they’re back to using AI to generate content quickly because that’s what the job demands. And training doesn’t scale—you can train 20 people, but when they’re each producing 50 pieces of content a month, you can’t individually coach each piece.

The data backs this up: **BCG found 74% of companies struggle to achieve and scale AI value** despite training efforts. Organizations that invest in training employees on AI see only **43% higher success rates** in deploying projects—better than nothing, but far from a solution.

Also, training is vague. “Write with more specificity” sounds clear until someone asks “how much specificity?” and you realize you don’t have an objective answer.

**Approach 3: Style tools like Grammarly or Acrolinx**

“We’ll use enterprise content tools to enforce quality.”

These tools catch typos. They enforce brand voice. They’ll tell you not to use “utilize” when you mean “use.” Great.

But they’ll happily approve a blog post that says “many enterprise customers see significant ROI improvements” with zero customer names, zero specific numbers, zero proof points. They’ll approve a sales email that starts with “I hope this email finds you well” and has zero personalization beyond the company name.

Style doesn’t equal substance. Grammar doesn’t equal usefulness. These tools optimize for the wrong thing.

**Approach 4: AI detectors**

“We’ll use AI detection tools to catch AI-generated content.”

Even if these worked—and they don’t. The **FTC v. Workado order (April 2025) found AI detection tools claiming 98% accuracy actually achieved only 53% accuracy** on general-purpose content—”no better than a coin flip,” according to the FTC’s own language. That’s literally worse than random guessing.

But even if they worked perfectly, so what? Bad writing has existed forever. I’ve seen terrible, vague, useless PRDs for a decade before AI existed. I don’t care if a human or an AI wrote “Recently, we’ve seen increased customer demand.” I care that it’s temporally vague and tells me nothing actionable.

Detecting authorship doesn’t solve the quality problem. It just lets you blame the right party for the garbage.

**Approach 5: Manual review**

“All content gets reviewed by a manager before it goes live.”

Now your manager spends 25 hours a week reading blog posts and sales emails. They burn out. They start skimming. They give vague feedback like “make it better” because they don’t have time to be specific about what’s wrong with 40 different blog posts.

Or they give up and approve everything because the alternative is becoming a bottleneck that blocks the entire team.

Manual review worked when each person produced one blog post a week. It doesn’t work when each person produces ten blog posts a week. The math doesn’t work. Human attention can’t scale to match AI production.

**Why they all fail:** Each approach assumes human attention can keep up with AI production. That’s the wrong assumption.


## The Real Problem: Attention Economics Broke

Here’s what actually happened: we moved from a world where human attention was the bottleneck to a world where human attention is a luxury good.

Think about it in economic terms. Production capacity for content increased 100x overnight. But consumption capacity—human attention—stayed flat. Supply exploded. Demand stayed constant. That creates a fundamental mismatch.

**Before AI:**

- Your team produces 60 blog posts a year
- Your manager can read all 60 before they publish
- Quality control scales naturally

**After AI:**

- Your team produces 480 blog posts a year (or 4,800)
- Your manager can still only read 60
- Quality control breaks

You have three options:

1. Read everything (impossible, burns out managers)
2. Read nothing (garbage ships, quality craters)
3. Read randomly (some garbage gets caught, most doesn’t)

None of these work. What you need is option four: systematically filter the content so human attention goes to the 1% that matters.

Andrej Karpathy said something that crystallized this for me. He said “99.9% of attention is about to be LLM attention, not human attention” (March 12, 2025 tweet). That’s exactly right. The question isn’t whether to use AI attention. It’s how to use it correctly.

You need AI attention to match AI production. If AI is creating 100x more content, you need AI to read 98% of it and surface the 1% that needs human review.

But—and this is crucial—you can’t just ask “is this good?” and expect useful answers.


## Why “Is This Good?” Doesn’t Work

I’ve seen dozens of companies try this. They tell their teams: “Before you publish, paste it into ChatGPT and ask if it’s good.”

It doesn’t work. Here’s why:

First, “good” means different things for different content types. A good blog post has specific proof points and concrete examples. A good PRD has testable acceptance criteria and clear dependencies. A good sales email has personalization signals and a low-friction ask. These are completely different quality standards. Asking a generic “is this good?” applies no standard at all.

Second, LLMs will say almost anything is good if you ask them generically. They’re optimized to be helpful and agreeable. They’ll find something nice to say about almost any content. “This blog post has a clear structure and uses professional language” doesn’t tell you if it’s actually useful.

Third, the feedback is too vague to act on. “This could be more specific” or “Consider adding more detail” doesn’t tell you what to do. Where should it be more specific? What kind of detail? How much?

What you need is function-specific quality evaluation with concrete rubrics and actionable feedback. Not “is this good?” but “does this have the structural elements that make it useful for its purpose?”


## The Solution: Function-Specific Quality Gates

Here’s the insight: you need different quality filters for different content types, each evaluating on the dimensions that actually matter for that purpose.

A blog post without specific examples and proof points isn’t credible. A sales email without personalization is spam. A PRD without acceptance criteria wastes engineering time. These are different failure modes. You need different evaluators.

Let me show you how this works with the content type where volume exploded the most: blog posts.


## How to Actually Evaluate a Blog Post

When I built the blog post evaluator, I started by asking: what makes a blog post actually useful versus generic slop?

The answer isn’t “good grammar” or “clear writing.” Those are table stakes. The answer is specificity and proof. Can a reader verify what you’re claiming? Can they act on it? Or is it just corporate word soup?

I evaluate blog posts on five dimensions:

**Specificity:** Are there real examples? Actual numbers? Concrete instances? Or is it all “many customers” and “significant improvements”? A score of five means at least three specific examples with names, numbers, or dates. A score of zero means entirely generic—no concrete evidence anywhere.

**Proof density:** Are claims backed by data, customer quotes, case studies, or screenshots? Can the reader verify what you’re saying? A score of five means every major claim has evidence. A score of zero means all assertions, no backing.

**Positioning clarity:** Is it immediately obvious who this is for and what problem it solves? Within the first two paragraphs, can a reader tell if this is relevant to them? A score of five means first paragraph names the audience, problem, and solution. A score of zero means unclear who should care.

**Differentiation:** Does it explain why not a competitor or the status quo? Is there a unique point of view? A score of five explains what alternatives miss and why this matters. A score of zero could be about any product—nothing distinctive.

**Call-to-action:** Is the next step clear and low-friction? A score of five means specific next step that matches reader intent. A score of zero means no CTA or it’s buried and vague.

Here’s what I tell the evaluator to flag as anti-patterns:

- “Best-in-class” or “industry-leading” without proof
- Metrics with no denominator: “40% faster” (faster than what? measured how?)
- “Trusted by 1000+ companies” without naming any
- Generic pain points: “save time and money” (every product claims this)

Then I ask for specific, actionable feedback. Not “this needs more specificity” but “Paragraph 3 says ‘many enterprise customers saw significant ROI.’ Replace with: ‘Acme Corp reduced manual data entry from 14 hours per week to 2 hours per week within 3 months (source: case study link).’”

That’s feedback someone can actually use. It’s specific about location, explains the problem, shows exactly how to fix it, and explains why it matters.

Here’s the key: this isn’t just filtering. It’s teaching. When someone gets this feedback three times, they start internalizing the pattern. “Oh, I need actual customer names. I need specific numbers with context. I need proof points, not assertions.”


## The Pattern Across Other Content Types

Once you see how it works for blog posts, the pattern becomes clear for other content types.

**Sales outreach** gets evaluated on personalization depth (evidence of research beyond company name), problem hypothesis (specific guess at their pain point), relevance signal (why now—funding, hiring, expansion), value clarity (stated in their outcomes, not your features), and ask size (low-friction, not “30 min demo” on cold email).

What kills sales outreach? “I hope this email finds you well.” Generic pain points that could apply to any company. High-friction asks. Could be sent to a thousand people with find-replace. The evaluator flags all of this and says: “Opening line: replace generic greeting with ‘I saw Acme just posted 4 SDR roles—congrats on the growth!’ to show you did research.”

**Email campaigns** get evaluated on subject line specificity (does it make a concrete promise), personalization signals (segmentation beyond “Hi {FirstName}”), value proposition clarity (obvious benefit in first sentence), social proof (specific customers or data), and friction reduction (clear one-click action).

What kills email campaigns? Subject lines like “Exciting updates.” Opening with “We’re thrilled to announce.” No clear reason why this email matters today. Vague CTAs like “learn more.” The evaluator catches this and provides specific fixes.

**Social media posts** get evaluated on hook strength (first sentence earns the read), specificity (concrete example or data point), insight novelty (is this a fresh take), engagement design (does it invite response), and format optimization (breaks, white space, scannable).

What kills social posts? Starting with “Excited to share.” Vague wisdom like “Leadership is about communication.” No specific examples. Wall of text. The evaluator flags patterns and shows how to fix them.

**Ad copy** gets evaluated on benefit clarity (specific outcome in first 5 words), objection handling (addresses why not competitor), urgency creation (time-bound trigger), friction removal (what exactly happens when you click), and trust signals (specific proof point).

What kills ad copy? Leading with features not benefits. Vague promises like “transform your business.” No clear next step. Generic trust claims like “trusted by thousands.” The evaluator catches this and shows concrete improvements.

**Product descriptions** get evaluated on use case specificity (who is this for exactly), problem-solution mapping (clear pain point addressed), differentiation (why not alternatives), technical precision (specs without jargon), and objection preemption (addresses likely concerns).

What kills product descriptions? Could describe any similar product. No specific use cases. Feature lists without context. Vague benefits. The evaluator forces specificity.

See the pattern? Each content type has different structural requirements for usefulness. You can’t evaluate them all on “clarity and conciseness.” You need function-specific rubrics that check: does this have what it needs to actually work?


## The Full Set: Where Quality Gates Matter Most


### ***[Grab the full prompt set for these here](https://www.notion.so/product-templates/Prompts-to-Fix-Slop-2875a2ccb52680a79752ee9b3b7eef29?source=copy_link)***

Based on what I’m seeing across companies, here’s where the volume explosion is actually happening and where you need quality filters:

**The High-Volume Explosion (10-100x increase):**

1. Blog posts and articles
2. Social media content (LinkedIn, Twitter, etc.)
3. Email campaigns and sequences
4. Sales outreach (cold emails)
5. Ad copy (Google, Meta, LinkedIn)
6. Support responses
7. Product descriptions
8. Meeting summaries
9. Video scripts
10. SEO content briefs
11. Landing page copy
12. Follow-up emails
13. Case study drafts
14. Email newsletter content
15. Internal communications (Slack responses, etc.)

**The High-Impact Category (lower volume but expensive when bad):**

16. PRDs and feature specs
17. Technical documentation
18. Executive memos
19. Client deliverables and reports
20. Proposals and pitch decks

The first 15 are where you’re drowning in volume and can’t possibly read everything. You need AI to filter so you’re only reading the top 2-5%.

The last 5 are lower volume but when they’re bad, the cost is massive—wasted engineering time, poor strategic decisions, lost clients, blown deals. You need AI to catch structural problems before humans invest time.

Together, these 20 cover probably 80% of the content quality pain across most organizations.


## What Actually Changes When You Deploy This

I’ve seen companies implement function-specific quality gates, and the effects are more profound than just “we read less garbage.”

The most immediate impact is time savings. Research shows that marketers using AI save an average of **3 hours per piece of content** (Synthesia, 2025). For a team producing 40 blog posts a month, that’s 120 hours monthly, or **1,440 hours annually**—36 full work weeks recovered.

But the second-order effects matter more. Quality becomes measurable for the first time. You can track trends. Is the team getting better at using AI to produce good content? Are certain writers consistently hitting 4.5+ while others hover at 2.8? You have data instead of gut feel.

Promotable work surfaces faster. When quality is visible and measurable instead of buried in a pile of “everything looks fine,” high performers become obvious. You can promote based on demonstrable skill rather than gut feeling.

Hiring gets dramatically better. Interview candidates by giving them a 2.3-scored blog post and asking them to improve it to 4.0+. You learn more in 30 minutes than in three hours of behavioral questions. Who can spot structural problems? Who gives actionable fixes? Who understands what quality means?

Real-time coaching accelerates learning. Instead of quarterly reviews where you vaguely remember that blog post from six weeks ago was weak, someone gets feedback immediately: “Paragraph 3 lacks specificity—here’s exactly how to fix it.” They revise and resubmit. They see their score go from 2.8 to 4.2. They learn what good looks like through repetition, not through hoping they remember a training session from three months ago.

Client deliverables become professional reputation insurance. Never ship a report under 4.0 to clients. Never send a proposal under 3.8. Your clients can’t tell if you used AI, but they can tell if your deliverable helps them make decisions.

Team benchmarking reveals best practices. Compare performance across teams. Is the East Coast sales team scoring higher on outreach emails? What are they doing differently?


## When This Goes Wrong (And How to Catch It)

I’ve seen quality gates fail in predictable ways. Let me tell you what to watch for.

The most common failure is what I call the override spiral. Managers start constantly marking “REVISE” documents as acceptable. If your override rate goes above 20%, something’s wrong. Usually it means the rubric is calibrated too strictly or it’s missing edge cases.

Then there’s gaming. Documents start hitting the rubric perfectly but feel soulless. Here’s what’s counterintuitive: this is usually fine. If someone “games” their way to specific examples, concrete numbers, and clear proof points, the blog post actually works. Gaming good rubrics produces good content.

The real risk is bad rubrics that reward verbosity. If your rubric incentivizes bloat, fix the rubric. And spot-check occasionally—audit high-scoring posts to make sure they’re genuinely good, not just checkbox compliance. But if checkbox compliance still produces useful posts? You’re fine.

There’s also resistance. People say “AI judging my work feels dystopian.” This is a positioning problem. You reframe it: “AI is helping you ship better work faster, the same way spell-check helps you avoid typos.” Show time savings with real numbers. “You spent six hours in revision cycles last week. With quality gates, you spend 30 minutes getting it right the first time.”

Make it opt-in first. Let people self-check before mandatory review. Once they catch three issues before their manager sees them, they become advocates.

The last failure mode is drift. System scores stay high but outcomes degrade. The team learns to game the rubric while actual quality drops, or business needs evolve but the rubric doesn’t. The fix is quarterly reviews where you correlate scores with business outcomes. If blog posts score 4.5+ but engagement rates are dropping, the rubric needs updating.

Watch these early warning signs: override rate trending up means calibration is too strict. Average scores trending up but outcomes flat means gaming or drift. Self-check usage dropping means resistance. Fix implementation rate under 70% means feedback isn’t actionable enough.


## Why This Matters (Beyond Just Time Savings)

The deeper issue is that AI broke an informal system that worked for decades.

When production was limited by human speed, quality control was informal. You knew who the good writers were. You could read their work. You could give feedback. It scaled because production scaled slowly. One blog post a week? Your manager can read that. One PRD a sprint? Engineering can review it.

AI broke that. Production is now nearly infinite. Informal quality control can’t keep up. You can’t know who the good writers are when everyone is producing 50 pieces of content a month. You can’t read everything. You can’t give individual feedback at scale.

So you need systematic quality control for the first time. Not because people got worse at writing. Not because standards dropped. Because the volume increased 100x and the old informal system mathematically cannot work anymore.

And here’s the opportunity: the same AI that created the problem can solve it, if you use it correctly. You need AI attention to match AI production. You need function-specific rubrics that define what “good” means concretely for each content type. You need actionable feedback that teaches people what quality looks like.

The data is clear: **MIT found that despite $30-40 billion in enterprise AI spending, 95% of organizations see no measurable P&L impact** from their generative AI initiatives. **Only 5% of custom enterprise AI tools reach production**—a 95% failure rate. The problem isn’t AI capability. It’s deployment strategy.

This only works when it’s part of a quality culture. Use it as a teaching tool—when someone gets specific feedback, they learn. Don’t use it as a hammer—consistent low scores after feedback is a management conversation. Adapt it to your standards—these rubrics are starting points. Make it bidirectional—people should self-check before submitting.


## The Challenge

We’re living in a world where 1% of human attention matters and you need to put it in the right place.

The alternative is what’s happening now: drowning in volume, skipping quality control, shipping garbage, burning out managers with endless review cycles, watching response rates drop and engagement crater and wondering why AI hasn’t delivered the productivity gains everyone promised.

Bad writing has always existed. What’s new is the volume. From 2022-2023 alone, **15 billion AI images were created**—matching decades of photography in just one year. What’s new is that informal quality control broke. What’s new is that you need systematic quality control that scales with AI production.

Use AI attention to filter AI output. Put human attention where it matters. Define quality concretely for each content type. Give actionable feedback that teaches, not vague directives that frustrate.

I don’t care if AI wrote it. I care if it’s good.

That’s the standard. And now there’s a way to enforce it at scale.

Stop drowning in the slop.

---

[![](https://substackcdn.com/image/fetch/$s_!pONt!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6ec9d3bd-56c0-4b70-b44a-00508ca9f6c2_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!pONt!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6ec9d3bd-56c0-4b70-b44a-00508ca9f6c2_1024x1024.png)


# Web Sources:

**AI Image Statistics for 2024: How Much Content Was Created by AI**
**<https://journal.everypixel.com/ai-image-statistics>**

**AI expert Andrej Karpathy envisions a web where 99.9% of content**
**<https://the-decoder.com/ai-expert-andrej-karpathy-envisions-a-web-where-99-9-of-content-is-optimized-for-ai-not-humans/>**

**The Content Collapse and AI Slop – A GEO Challenge - iPullRank**
**<https://ipullrank.com/ai-search-manual/geo-challenge>**

**AI Statistics 2025: Top Trends, Usage Data and Insights - Synthesia**
**<https://www.synthesia.io/post/ai-statistics>**

**Ex-OpenAI founder claims 99.9% of web content will be AI-optimized**
**<https://www.windowscentral.com/software-apps/browsing/andrej-karpathy-claims-web-content-will-be-ai-optimized>**

**Andrej Karpathy - X (Twitter)**
**<https://x.com/karpathy/status/1899876370492383450?lang=en>**

**AI Detection or AI Deception? FTC Says Be Ready to Back It Up**
**<https://www.jdsupra.com/legalnews/ai-detection-or-ai-deception-ftc-says-9402609/>**

**FTC Order Requires Workado to Back Up Artificial Intelligence**
**<https://www.ftc.gov/news-events/news/press-releases/2025/04/ftc-order-requires-workado-back-artificial-intelligence-detection-claims>**

**Measuring the ROI of AI in Marketing: Key Metrics and Strategies for Marketers**
**<https://blog.hurree.co/measuring-the-roi-of-ai-in-marketing-key-metrics-and-strategies-for-marketers>**

**MIT Report: Most Organizations See No Business Return on Gen AI**
**<https://campustechnology.com/articles/2025/08/26/mit-report-most-organizations-see-no-business-return-on-gen-ai-investments.aspx>**

**FTC Reaches Settlement Over Generative AI Detection Claims**
**<https://advertisinglaw.fkks.com/post/102ka6f/ftc-reaches-settlement-over-generative-ai-detection-claims>**

**15+ Stats About Achieving ROI From AI Marketing | Iterable**
**<https://iterable.com/blog/15-stats-roi-ai-marketing/>**

**Why 95% of Corporate AI Projects Fail: Lessons from MIT’s 2025 Study**
**<https://complexdiscovery.com/why-95-of-corporate-ai-projects-fail-lessons-from-mits-2025-study/>**

**FTC calls AI detection company’s claim of 98% accuracy bogus**
**<https://www.courthousenews.com/ftc-calls-ai-detection-companys-claim-of-98-accuracy-bogus/>**

**MIT report: 95% of generative AI pilots at companies are failing**
**<https://fortune.com/2025/08/18/mit-report-95-percent-generative-ai-pilots-at-companies-failing-cfo/>**

**TOP AI LEAD GENERATION STATISTICS 2025 - Amra & Elma**
**<https://www.amraandelma.com/ai-lead-generation-statistics/>**

**AI-Driven Email Outreach Strategies for 2025 - Martal Group**
**<https://martal.ca/outreach-strategies-lb/>**

**Sales 2025 Data Report: Trends, AI & Sales Benchmarks**
**<https://www.outreach.io/resources/blog/sales-2025-data-analysis>**

**Building an Enterprise Measurement Framework for Agentic AI - ISG**
**<https://isg-one.com/articles/from-potential-to-performance--building-an-enterprise-measurement-framework-for-agentic-ai>**

**100+ Must-Know Email Marketing Statistics for 2025 | PGM Solutions**
**<https://porchgroupmedia.com/blog/email-marketing-statistics/>**

**RATAS: A Generative AI Framework for Explainable and Scalable**
**<https://arxiv.org/html/2505.23818v1>**

**AI code refactoring: Strategic approaches to enterprise software - DX**
**<https://getdx.com/blog/enterprise-ai-refactoring-best-practices/>**

**Digital Marketing’s Attention Crisis: Standing Out in an Era of**
**<https://influencermarketinghub.com/digital-marketings-attention-crisis-standing-out-in-an-era-of-information-overload-introduction/>**

**Major Platform Cracks Down on AI-Generated Content Overuse**
**<https://www.dkodetech.com/platform-penalizes-ai-generated-content-overuse/>**

[The Economics of Infinite Intelligence: Zero-Cost Innovation and Business Model Disruption

Abstract…

Read more

10 months ago · 1 like · Jakub Žegklitz-Bareš and Metamatics](https://www.hackingeconomics.com/p/the-economics-of-infinite-intelligence?utm_source=substack&utm_campaign=post_embed&utm_medium=web)

**Microsoft AI CEO Says Cost of Information About to ‘Radically Change’**
**<https://www.businessinsider.com/microsoft-ai-ceo-mustafa-suleyman-economics-of-information-radically-change-2024-6>**

**MIT study shatters AI hype: 95% of generative AI projects are failing**
**<https://economictimes.com/magazines/panache/mit-study-shatters-ai-hype-95-of-generative-ai-projects-are-failing-sparking-tech-bubble-jitters/articleshow/123428252.cms>**

**Zero Marginal Cost Intelligence is Inevitable - Compounding Thoughts**

[Zero Marginal Cost Intelligence is Inevitable

Read more

a year ago · 4 likes · Sam Blumenthal](https://compoundingthoughts.substack.com/p/zero-marginal-cost-intelligence-is?utm_source=substack&utm_campaign=post_embed&utm_medium=web)

**Attention economy - Wikipedia**
**<https://en.wikipedia.org/wiki/Attention_economy>**

**AI Adoption in 2024: 74% of Companies Struggle to Achieve and Scale Value**
**<https://www.bcg.com/press/24october2024-ai-adoption-in-2024-74-of-companies-struggle-to-achieve-and-scale-value>**

**6 Ways AI Changed Business in 2024, According to Executives**
**<https://hbr.org/2025/01/6-ways-ai-changed-business-in-2024-according-to-executives>**
