---
title: "Decoding Company Strategy Through Job Postings: How AI Transforms Trivial Data Into Strategic Intelligence"
author: "Nate Jones"
published: 2025-09-25
url: https://natesnewsletter.substack.com/p/grab-my-prompts-i-used-ai-on-job
audience: everyone
scraped_at: 2026-01-05 19:17:07
---

**I just used AI to uncover the specific technical issues Anthropic—a $183B AI giant—is likely experiencing internally.**

**How? Not because I have a hotline to their founder. LOL.**

**Nor have they admitted this stuff publicly.**

**No. I did it by reading their job postings with AI.**

Yesterday, I was talking with a job seeker and had a realization that made me drop everything and build something new.

We’re sitting on a goldmine of corporate intelligence that’s been hiding in plain sight: job postings.

But we don’t really have a good way to access that intelligence. There are just too many jobs to reasonably analyze by hand.

Until now.

What used to take teams of analysts weeks to decode can now be done in seconds with the right AI prompts. And I’m not talking about just finding open positions—I’m talking about reverse-engineering entire company strategies, spotting operational weaknesses, and identifying exactly where competitors are vulnerable.

I spent the last couple of days building and testing this approach on real companies, and the results were so revealing that I had to share everything immediately. Here’s what you’re getting:

- **A 10-minute demo video** where I expose Anthropic’s strategic gaps using nothing but their public job postings
- **A ready-to-remix Lovable mini-app** that runs this analysis automatically (built it myself, takes any company URL)
- **I built a Job Seeker’s Intelligence prompt** that reveals hidden culture issues, growth trajectories, and which roles are actually worth pursuing vs. ghost postings
- **I built a Competitive Intelligence prompt** that extracts B2B sales weaknesses, technical debt indicators, and strategic pivots your competitors don’t want you to see—great stuff for PMs, C-suite, marketers, sales, and more
- **The bigger picture**: Why job postings represent a new class of “invisible data” that AI has suddenly made visible—and what this means for privacy, strategy, and competitive advantage in 2025

Whether you’re job hunting, running competitive intelligence, evaluating investments, or just curious about what your own company is telegraphing to the world, these tools will change how you think about publicly available information.

Let’s crack this code together.

(And PS. Yes you get all that Anthropic tea in the video.)


## Two ways to get the intelligence:


#### *1. Want to dive straight in? [Grab the Lovable app here](https://hiring-radar.lovable.app/)*

This is a mini-app I built that does the search for you and presents the results in a really digestible way. Lovable makes it easy to remix the app and make it your own!

> Using Lovable means using your Perplexity API key, which anyone can get (Perplexity gives you free credits), but it can feel a bit scary. [API guide here](https://www.perplexity.ai/help-center/en/articles/10352995-api-settings#h_944fe9569b).


#### *2. Want to use prompts in Perplexity or ChatGPT? Scroll down for prompts!*

- Pick the job seeker’s prompt for job hunting, switching roles, or looking at your own company for intel!
- Pick the competitive analysis prompt for product intelligence, board-level analysis, and insights on growth strategy + weaknesses


# Decoding Company Strategy Through Job Postings: How AI Transforms Trivial Data Into Strategic Intelligence

The era of AI has unlocked an unexpected goldmine of business intelligence: job postings. What was once considered mundane recruitment data has become a window into company strategy, operational weaknesses, and market positioning. This transformation represents a broader shift in how we should think about publicly available information in the age of large language models.


## Beyond Traditional Job Search Analysis

A year ago, analyzing a company’s job postings meant manually reviewing hundreds of listings, categorizing roles, and attempting to spot patterns—a time-consuming process that few could justify. Today, AI can process thousands of postings in seconds, identifying strategic patterns that would have been invisible to human analysts working at scale.

The power lies not just in volume but in strategic inference. Modern LLMs can be prompted to reason about what’s missing from job postings as much as what’s present. When Anthropic posts multiple roles for startup account management but no sales engineers, it reveals an early-stage B2B strategy under pressure. When they lack platform engineering roles despite rapid scaling, it suggests potential technical debt accumulating beneath their impressive AI capabilities.


## A Multi-Lens Intelligence Tool

The real breakthrough is that job posting analysis serves multiple stakeholders simultaneously. Job seekers can identify not just open positions but infer company culture and growth trajectories. A lack of internship postings combined with senior-heavy hiring suggests a company prioritizing immediate execution over talent pipeline development.


### The Job Seeker’s Perspective

For those looking to understand a company from a career perspective, here’s a battle-tested prompt that extracts actionable intelligence:

```
Company Name / URL: [Insert Company Name or career page URL]

You are OSINT forensics. I will enter a company name or careers URL.
Your job is to pull **the Inside Scoop for job seekers** from job postings.
PHASE 1 — DISCOVERY
- Check the official careers site and major job boards (LinkedIn, Indeed, BuiltIn).
- Gather only recent postings (<90 days). Mark older ones as ARCHIVE.
- Record: job title, location, posting date + source, pay if listed, and 1–2 short snippets.
PHASE 2 — SIGNALS
From the postings, note:
- Growth cues: “first hire,” “90-day pilot,” “new team.”
- Stability cues: roles focused on renewals, compliance, or customer success.
- Red flags: jobs open >90 days, reposted without changes.
- Org focus: Sales, Product, Engineering, Customer Success, etc.
PHASE 3 — INSIGHTS
Write four sections, 2–3 bullets each. Keep it practical and grounded.
1. **Where They’re Investing** — teams growing now, with examples.
2. **Career Opportunities** — roles most open to job seekers (fresh vs stale).
3. **Culture & Work Style** — remote vs onsite, growth language vs risk.
4. **Watch Outs** — weak spots (e.g., no new engineering hires, high churn focus).
PHASE 4 — RECEIPTS
Provide a short table:
- Claim | Snippet | Job + date + source | Confidence (0-100) | ARCHIVE if >90d
RULES
- Always show dates and sources.
- Be direct: highlight both opportunities and risks.
- Tone: insider and useful, not PR.
OUTPUT
- Title: **”The Inside Scoop for Job Seekers: [Company] — [Month Year]”**
- Show insights + receipts in clean markdown.
```

This prompt transforms raw job data into career intelligence, highlighting not just what’s available but what it means for your career trajectory. The emphasis on recent postings (<90 days) and the distinction between fresh and stale opportunities helps job seekers avoid wasting time on positions that may already be filled or deprioritized.


### Competitive Intelligence and Strategic Analysis

For competitive intelligence professionals, investors, and strategic analysts, this more comprehensive prompt delivers deeper insights. It should run well in both ChatGPT and Perplexity.

```
Company Name / URL: [Insert Company Name or career page URL]

You are OSINT forensics. I will enter a company name or careers URL.
Your job is to pull **the Inside Scoop** from job postings, not their PR.
PHASE 1 — DISCOVERY
- Find the official careers site + aggregator listings (LinkedIn, Indeed, BuiltIn).
- Gather the most recent postings (<90 days). If older, tag them as ARCHIVE.
- Record: title, location, posting date + source, comp if listed, and 1–2 verbatim snippets.
PHASE 2 — SIGNALS
From the postings, mark:
- Build cues: “from scratch,” “platform,” “internal SDK.”
- Buy cues: “evaluate vendors,” “RFP,” “integration partners.”
- Now cues: “first hire,” “90-day pilot,” “active this week.”
- Later cues: “multi-year,” “incubation,” stale reposts.
- Org labels: e.g., Platform, Safety, Customer Success, Gov Sales.
PHASE 3 — INSIGHTS
Write **six sections**, 3–5 bullets each. Each bullet must have 1 counterpoint or missing piece.
Keep it skeptical and falsifiable.
1. Inferred Product Strategy — where they’re investing, AND what’s missing.
2. Inferred B2B Sales Approach — how they sell, AND where the motion looks stressed.
3. Inferred Job & Career Insights — what’s real for job seekers, AND what looks ghost/archived.
4. Inferred Cultural Insights — product vs sales culture; note contradictions.
5. Inferred Company Weaknesses — gaps, attrition tells, bottlenecks.
6. Inferred Company Strengths — where they actually look strong.
PHASE 4 — RECEIPTS
Produce a compact table:
- Claim | Snippet | Posting + date + source | Reasoning | Confidence (0-100) | ARCHIVE if >90d | Claims to Confirm
RULES
- Separate “Posting-only” from “External context” if you pull outside info.
- Always show dates/sources.
- Lower confidence on cultural/benefits fluff; higher only on verifiable hiring signals.
- Highlight absences (e.g., “no fresh eng hires in 90d”) as clearly as presences.
- Use sharp, insider tone. Avoid corporate optimism.
OUTPUT
- Title the report: **”The Inside Scoop: [Company] — [Month Year]”**
- Render sections + receipts table in clean markdown for readability.
```

This intelligence-focused prompt goes beyond surface-level analysis. The requirement for counterpoints and missing pieces forces the AI to think critically about what’s not being said. The distinction between “build” versus “buy” cues reveals whether a company is investing in proprietary technology or relying on external solutions—critical intelligence for competitors and partners alike.


## The Big Picture: Invisible Data is Everywhere

Job postings exemplify a broader category of “invisible data” or “trivial data” that AI has suddenly made valuable. This is information that has always been public but was too voluminous or scattered to analyze effectively. The implications extend far beyond recruitment intelligence.

Consider the parallel with social media imagery. What seems like innocent travel photos becomes location data when AI can identify landmarks and infer geographic patterns. Financial disclosures buried in lengthy reports become accessible strategic indicators. Patent filings reveal R&D directions. Conference speaker lists map influence networks.

This shift demands a fundamental reconsideration of what constitutes sensitive information. Companies must now assume that any pattern visible across their public data will be detected and analyzed. The aggregation of seemingly harmless details can reveal strategic intentions as clearly as any internal memo.


## Implementation Notes

Everyone has this in their pocket now. A well-crafted prompt in ChatGPT or Perplexity can deliver strategic analysis that would have required a team of analysts just two years ago.

The key lies in prompt engineering—being explicit about the lens through which you want to examine the data. Notice how both prompts above include specific phases (Discovery, Signals, Insights, Receipts) that structure the AI’s analysis.

The “RULES” sections enforce rigor, requiring dates, sources, and confidence levels. This isn’t just about asking questions; it’s about architecting a systematic investigation via a strong prompt. And yes, I absolutely worked with ChatGPT-5 to help craft these prompts—it’s a fantastic meta-prompt tool as long as you have a good feedback loop

The prompts also have subtle differences in frame that are worth noting as you craft your own versions. The job seeker prompt asks for “practical and grounded” insights, while the intelligence prompt demands a “skeptical and falsifiable” approach. These give you different camera angles on the same data.


## Strategic Implications

Organizations must now operate under the assumption that their job postings telegraph strategy to anyone paying attention. This doesn’t mean abandoning job postings, but it does mean being intentional about what patterns emerge from collective hiring decisions. The better approach is to use this intelligence capability proactively—analyzing your own postings as competitors would see them and adjusting strategy accordingly. (Yes, you can use these prompts for that.)

For people and small companies, this represents a massive leveling of the intelligence playing field. A job seeker can now understand a potential employer’s trajectory as well as many insiders. A startup can map the competitive landscape with the thoroughness of an enterprise intelligence team. A sales professional can identify exactly where a prospect organization is struggling before the first call.


## A Few Last Practical Tips

When using these prompts, remember:

1. **Freshness matters**: The 90-day cutoff isn’t arbitrary. Older postings often represent filled positions or abandoned initiatives.
2. **Multiple perspectives enhance accuracy**: Run both prompts on the same company to triangulate insights. What the job seeker prompt identifies as “growth opportunity” might be revealed as “scaling chaos” in the intelligence analysis.
3. **Verify high-stakes insights**: The “Claims to Confirm” column in the intelligence prompt isn’t optional—it’s your roadmap for validation through other sources.
4. **Watch for patterns across competitors**: Running these analyses across multiple companies in the same sector reveals industry-wide trends versus company-specific strategies.

The transformation of job postings from recruitment tools to strategic intelligence represents just the beginning. There will be lots more use-cases like this.

As AI capabilities expand, more categories of “waste data” will become valuable intelligence sources. The winners in this new landscape will be those who recognize these opportunities first and act on the insights they reveal. The question isn’t whether to use these tools, but how quickly you can integrate them into your decision-making process before your competitors do the same.

With these prompts in hand, you’re equipped to start extracting intelligence immediately. The only remaining question is: which company will you analyze first? I already picked Anthropic :)

[![](https://substackcdn.com/image/fetch/$s_!TUkA!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F28cdb679-f905-4fb8-8477-76de9dffd4d1_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!TUkA!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F28cdb679-f905-4fb8-8477-76de9dffd4d1_1024x1024.png)
