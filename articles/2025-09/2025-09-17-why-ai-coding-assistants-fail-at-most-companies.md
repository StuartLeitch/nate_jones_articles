---
title: "Why AI Coding Assistants Fail at Most Companies"
author: "Nate Jones"
published: 2025-09-17
url: https://natesnewsletter.substack.com/p/forget-claude-vs-codex-the-14-ai
audience: everyone
scraped_at: 2026-01-05 19:17:32
---

*Engineering teams ask the wrong questions about AI all the time.*

*And the rest of us suffer.*

*Because this isn’t just about picking the best tool (Claude or Codex?) for AI coding.*

*It’s really about the kinds of assumptions we make when we add massive rocket boosters to our existing systems. Because that’s what AI is: a rocket booster. It can lift you to the moon, or you can crash out with bad assumptions, bad data, bad team practices…the list goes on.*

*So when OpenAI launched a brand new ChatGPT-5 model for engineers and made it available via their Codex platform, I wanted to do a special on Codex and how teams should use it.*

*But then I looked at my inbox. And I shook my head. Because that would be irresponsible until we talk about this piece first: the truth is that the right tool is the wrong question for most teams, because a suboptimal tool with the right team and infrastructure configuration will matter MUCH more than a perfect coding model.*

*And so we’ll do Codex! In fact if you want the details on that I recorded a bonus video on Codex just for this newsletter. And we’ll a deep dive soon.*

*But in the meantime, most of this newsletter is about 14 questions that engineering teams need to be asking—not just for themselves, but for all of us.*

*Because the truth is so called “coding agents” are increasingly used for much more than coding, so these technical decisions affect product managers, marketers, customer success—really everyone in the business. And teams aren’t asking that wider question when they evaluate these tools because they’re used to software.*

*So let’s ask ourselves better questions! Let’s give ourselves the chance to actually accelerate with AI by setting up our infrastructure so that AI rockets us in the right direction, not toward a big messy disaster.*

*Both futures are possible, and these questions are what separate good teams from bad. Dig in and let’s have a good conversation on this one!*

> *PS. Curious for more engineering posts? Check out a bunch on [Claude Code](https://natesnewsletter.substack.com/t/claude-code), [software engineering as a whole](https://natesnewsletter.substack.com/t/engineering), and [how coding is changing in the age of AI](https://natesnewsletter.substack.com/t/coding).*


# Why AI Coding Assistants Fail at Most Companies


## Sidebar: Yes Codex dropped an update

I was going to write about Codex. I really was. But what I’m actually gonna do is give you a quick summary of Codex and then hop right into the bigger issue: *you’re not ready for Codex.* Because you’re probably not asking the real questions you need to ask about how you engineer.

Want the deets on Codex? Check out this extra video here:

Could not load video.


## But that’s not the real story

The real story is that most people ask the Claude vs. Codex question when they SHOULD be asking these questions instead. (And no it’s not just me asking this—[check out this viral Reddit post](https://www.reddit.com/r/vibecoding/comments/1myakhd/how_we_vibe_code_at_a_faang/) on vibe coding at FAANG.)

So with infrastructure top-of-mind, this piece is divided into two sets of 7 questions each:

Section 1: *What do I do before picking an AI agent?*

Section 2: *I picked an AI agent, now what do I do?*

And because we like to have fun around here, I’ll give you one bonus question here at the top:


#### ***Bonus Q: Do we know where in our overall development workflow we are bottlenecked?***

Why ask that? Because that’s a question that may imply you don’t need a coding AI to go faster at all. What if the bottleneck is your PM’s? Or what if the bottleneck is your own understanding of code? What if the bottleneck is your marketing team’s approval loops?

Most teams would benefit from asking this first, because that’s the more correct way to frame the problem.

That being said, if you do need a coding AI—these are the questions to ask!


## If you are trying to add a coding AI…

1. **What specific problem are we solving?**

   - **Why Ask**: Vague goals like “boost productivity” lead to misaligned tools and unmet expectations. Define measurable outcomes (e.g., “cut onboarding time by 25%” or “reduce bug rates in UI code by 15%”).
   - **The Stakes**: A 2024 GitHub study found 55% faster task completion with Copilot for boilerplate tasks, but only when teams targeted specific use cases like unit test generation or code refactoring. Broad “productivity” goals often diluted ROI, with 60% of surveyed teams reporting unclear benefits due to undefined objectives. X posts from engineering leaders highlight that focusing on narrow tasks (e.g., automating CRUD operations) yields better results than expecting holistic gains.
   - **Action**: Actually name what you are specifically solving for here. What problem matters that a coding assistant can help with?
2. **Do we have strong engineering practices to amplify?**

   - **Why Ask**: AI amplifies existing patterns—consistent or chaotic. Without design docs, TDD, or clear error-handling standards, AI can propagate antipatterns, increasing tech debt.
   - **The Stakes**: A **2025 METR study of experienced developers found that AI tools actually slowed developers down by 19%** when working on real-world projects, contradicting developer expectations of 24% speedup. **The Uplevel 2024 study tracking 800 developers showed AI coding assistants introduced 41% more bugs** while providing no significant productivity improvements. **IBM research indicates that incorporating AI into traditional coding tasks can reduce error rates by up to 30% when proper governance frameworks are established**, but only when teams have documented standards and consistent practices in place.
   - **Action**: Can you name a particular practice you know could be better across the technical team? Can you define the inputs needed to level up?
3. **Does the tool align with our workflow and tech stack?**

   - **Why Ask**: Mismatched integrations (e.g., poor IDE support) disrupt workflows, reducing adoption. Compatibility with languages or frameworks is non-negotiable.
   - **The Stakes**: A Jellyfish guide emphasized that tools like Codex thrive in VS Code-heavy workflows but struggle in niche environments (e.g., legacy COBOL systems). A 2025 IEEE study on Brazilian teams found 65% adoption rates for tools with seamless GitHub integration, versus 30% for those requiring custom setups. X discussions note that CLI-focused teams prefer Claude Code, while IDE-centric ones lean toward Codex’s browser integrations.
   - **Action**: Test across your primary IDE, sure. But also look at those non-conventional workflows that may be high value (like non-technical people using your coding agent).
4. **How will we measure success and track changes?**

   - **Why Ask**: Without metrics, you can’t distinguish real gains from perceived ones. Track quality and debt, not just speed.
   - **The Stakes:** **GitClear's analysis of 211 million lines of code from 2020-2024 reveals an 8-fold increase in duplicated code and a 39.9% decline in refactoring activities** when AI tools are used without proper quality controls. **Google's 2024 DORA report found that while 25% increase in AI usage can quicken code reviews, it also results in 7.2% decrease in delivery stability**. **McKinsey reports companies pay an additional 10-20% to address technical debt**, while **IBM research shows over 70% of IT budgets go to maintenance of current systems, leaving less than 30% for new projects**.
   - **Action**: First name why the metrics are matter, then figure out how to measure them and install the metrics.
5. **Is security and data privacy addressed?**

   - **Why Ask**: AI can leak IP or introduce vulnerabilities (e.g., hardcoded secrets). Compliance risks are real in regulated industries.
   - **The Stakes**: **Veracode's 2025 GenAI Code Security Report analyzing 80 coding tasks across 100+ large language models found AI-generated code introduces security vulnerabilities in 45% of cases**. **Java is the riskiest language with over 70% security failure rate, while Python, C#, and JavaScript show 38-45% failure rates**. **AI models failed to secure code against cross-site scripting in 86% of cases and log injection in 88% of cases**. Despite advances in syntax accuracy, **security performance has remained unchanged over time, with GenAI models choosing insecure coding methods 45% of the time**.
   - **Action**: Demand vendor clarity on data usage. There is no substitute.
6. **Do we have buy-in and training plans?**

   - **Why Ask**: Resistance from seniors or over-reliance by juniors derails adoption. Training prevents misuse and builds trust.
   - **The Stakes**: **Harvard Business Review's 2025 study confirmed only 41% of engineers adopted AI tools after a year, with female engineers at 31% and those over 40 at 39%**. **Fastly's 2025 survey found 95% of developers spend extra time fixing AI suggestions**, while **32% of senior developers report that half their shipped code is AI-generated, turning them into "AI babysitters"**. **Research shows AI adoption breakdown is 40% technical challenges, 30% personal transition issues, and 30% cultural/organizational factors**, indicating that simple prompting workshops miss the real barriers to effective adoption.
   - **Action**: Don’t skip this one. Invest like 3-4x more here than you think you need to.
7. **What’s the total cost beyond pricing?**

   - **Why Ask**: Setup, maintenance, and fixing bad outputs add hidden costs. ROI hinges on sustainable integration.
   - **The Stakes**: Geeky Gadgets reported that 25% of teams underestimated maintenance costs (e.g., context engineering), spending 15% more time on fixes than anticipated. A 2025 IEEE study noted that small teams (<10 devs) saw higher relative costs due to setup overhead. Blogs warn that rushed pilots under delivery pressure inflate long-term debt, offsetting initial gains.
   - **Action**: Expect your costs to show up before the value does—and in particular value scales non-linearly at big teams. You’ll get a big bang of value once you get that first large AI-assisted project through.


## If you already have an AI and it’s not working…

1. **Is the AI amplifying inconsistencies in our codebase?**

   - **Why Ask**: AI learns from your code’s patterns—good or bad. Inconsistent error handling or naming conventions lead to erratic suggestions.
   - **The Stakes**: An arXiv study found that teams with mixed error-handling styles saw a 15% increase in debugging time due to AI propagating inconsistencies. X threads describe cases where AI mixed exceptions and error codes, breaking systems. A 2025 IBM study noted that clean codebases with documented patterns reduced AI-related bugs by 20%.
   - **Action**: Figure out how to measure this in a way that matters to you. Comments on PR’s? Bugs in production? Issues flagged in architecture reviews? Define it and do it.
2. **Are we reviewing and testing AI output rigorously?**

   - **Why Ask**: Blindly accepting AI code, especially by juniors, invites subtle bugs. Reviews must treat AI output like human code.
   - **The Stakes**: **Fastly's 2025 survey confirmed 95% of developers spend extra time fixing AI-generated code**, with **senior developers shipping 2.5x more AI code but becoming quality gatekeepers**. **The Uplevel study found developers using AI assistants introduced 41% more bugs into production**, while **METR's randomized controlled trial showed experienced developers took 19% longer to complete tasks when using AI tools**, despite believing they were 20% faster. **Veracode's analysis reveals 45% of AI-generated code contains security vulnerabilities**, requiring rigorous human oversight to catch flaws that automated testing often misses.
   - **Action**: Are your teams actually checking AI PR’s? Be honest.
3. **Is prompting or context the issue?**

   - **Why Ask**: Vague prompts or poor context (e.g., outdated docs) lead to irrelevant code. Clear specs are critical.
   - **The Stakes**: A 2025 IEEE study found that 60% of AI errors stemmed from ambiguous prompts, fixable with iterative refinement (e.g., breaking tasks into steps). Blogs on X emphasize “test-first” prompting: Generate a failing test, then ask AI to fix it, improving accuracy by 30%. AlgoCademy notes that teams with up-to-date docs saw 40% fewer context errors.
   - **Action**: Prompting is probably an issue, as is context retrieval / data chunking. Assume it’s an issue until you can prove it’s not a blocker and zero in here.
4. **Are errors due to tool limitations or our setup?**

   - **Why Ask**: AI struggles with complex tasks (e.g., legacy systems) or niche domains without proper setup. Distinguish tool flaws from user error.
   - **The Stakes**: CTOL reported that Codex excels at simple tasks but fails 40% of complex, context-heavy tests. A 2025 government study noted 25% lower accuracy in poorly documented systems. X posts suggest switching to agentic modes (e.g., GPT-5-Codex’s `--full_auto`) for multi-step tasks, boosting success by 15%.
   - **Action**: Take an audit approach. How can you root cause issues you’re discovering by getting curious about *why* rather than settling for a generic blame-the-AI position. Think Five Why’s here.
5. **Is team usage causing problems?**

   - **Why Ask**: Over-reliance erodes skills; resistance stalls adoption. Misuse (e.g., copy-pasting without review) compounds errors.
   - **The Stakes**: AlgoCademy found that 30% of juniors lost coding fluency after over-relying on AI, while seniors’ resistance dropped adoption by 20%. A LinkedIn post noted that pairing AI with mentorship reduced blind acceptances by 35%. X threads report teams catching 10% more breaking changes with mandatory “why” explanations in reviews.
   - **Action**: Especially with juniors, make sure that you can show that team understanding is scaling. It shouldn’t just be a promotions thing.
6. **Are metrics showing real issues?**

   - **Why Ask**: Velocity gains can mask quality degradation. Measure amplification (e.g., pattern consistency) over raw output.
   - **The Stakes**: **The Uplevel 2024 study tracking nearly 800 developers found 41% higher bug detection rates in teams using GitHub Copilot**, with **no significant improvements in cycle time, pull request throughput, or developer burnout metrics**. **METR's study revealed a massive disconnect between perceived and actual AI impact - developers estimated 20% faster completion but actually took 19% longer**. **GitClear's analysis shows AI-generated code has 41% higher churn rate compared to human-written code**, indicating **technical debt acceleration rather than quality improvement**.
   - **Action**: Your metrics should map to anecdotes about product quality. If they don’t, the anecdotes are correct.
7. **Do we need to pivot or prepare better?**

   - **Why Ask**: Persistent failures often signal inadequate prep (e.g., no cultural audit). Pausing to fix foundations can salvage adoption.
   - **The Stakes**: A 2025 government study noted 95% of AI pilots failed due to skipped audits or vague use cases. Zenvanriel’s framework cut failures by 30% with pre-adoption guidelines (e.g., RAG for context). X posts from CTOs describe pausing pilots to document one system, boosting AI accuracy by 25%.
   - **Action**: Be willing to take a different approach where your root cause points to a real issue.


## TLDR

Data confirms that disciplined teams see 20-55% productivity gains with AI coding assistants, but undisciplined ones face 10-20% more debugging or debt. The difference lies in preparation and integration. Use these questions to build a culture worth amplifying, whether you’re starting fresh or fixing a stalled rollout. Pilot small, measure rigorously, and iterate—because no AI, not even GPT-5-Codex, can create discipline where none exists.

Start with auditing your discipline, not your code. Don't analyze your codebase—analyze your practices. How many architectural decisions are documented versus tribal knowledge? What percentage of code follows consistent patterns? How often does code review result in educational discussions? When did you last update documentation without being forced?

This isn't a technical audit—it's a cultural one.

The real question isn't which AI tool to choose. It's whether your engineering practices are solid enough to benefit from amplification in the first place.

Most aren't. And that's the work that needs to happen first.

[![](https://substackcdn.com/image/fetch/$s_!7ccK!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4d7387c2-4522-4b03-a4fd-437bfd4cb627_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!7ccK!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4d7387c2-4522-4b03-a4fd-437bfd4cb627_1024x1024.png)


# Sources


## **1. GitHub Blog - Official Copilot Productivity Research**

**URL:** <https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/>
**Why Essential:** Official GitHub study showing 55% faster task completion with Copilot, based on controlled experiments with 95 professional developers. This is the primary source for the most cited productivity statistic in your newsletter.


## **2. METR - AI Impact Study on Experienced Developers**

**URL:** <https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/>
**Why Essential:** The most significant counterpoint study showing AI tools actually make experienced developers 19% slower, despite their belief they're 20% faster. This contradicts many productivity claims and represents the strongest evidence against AI productivity benefits.


## **3. Veracode - 2025 GenAI Code Security Report**

**URL:** <https://www.veracode.com/resources/analyst-reports/2025-genai-code-security-report/>
**Why Essential:** The definitive source on AI code security vulnerabilities, showing 45% of AI-generated code contains security flaws. This validates your security claims and provides specific statistics on Java (70% failure rate) and cross-site scripting (86% miss rate).


## **4. arXiv - METR Academic Paper**

**URL:** <https://arxiv.org/abs/2507.09089>
**Why Essential:** The peer-reviewed academic version of the METR study, providing detailed methodology and statistical analysis showing the 19% slowdown effect with confidence intervals and controls for experimental artifacts.


## **5. GitHub Blog - Enterprise Impact with Accenture**

**URL:** <https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-in-the-enterprise-with-accenture/>
**Why Essential:** Enterprise-scale validation of Copilot benefits showing 90% developer satisfaction improvement and 26% task completion increase, providing the enterprise context for your productivity claims.


## **6. Harvard Business Review - Hidden Penalty of AI at Work**

**URL:** <https://hbr.org/2025/08/research-the-hidden-penalty-of-using-ai-at-work>
**Why Essential:** Validates your 41% adoption rate claim and provides demographic breakdowns (31% female engineers, 39% over-40 engineers), supporting your training and buy-in arguments.


## **7. Fastly Blog - Senior Developers and AI Code**

**URL:** <https://www.fastly.com/blog/senior-developers-ship-more-ai-code>
**Why Essential:** Source for the 95% of developers spending extra time fixing AI suggestions, and the emergence of senior developers as "AI babysitters," supporting your code review rigor arguments.


## **8. Veracode Press Release - Security Vulnerabilities Detail**

**URL:** <https://www.veracode.com/press-release/continuous-protection-for-the-cloud-era-veracode-spotlights-latest-innovations-for-advanced-software-security/>
**Why Essential:** Additional detail on the security study methodology and specific vulnerability types, including the finding that GenAI models choose insecure options 45% of the time when given a choice.


## **9. GitHub Resources - Measuring Copilot Impact Framework**

**URL:** <https://resources.github.com/learn/pathways/copilot/essentials/measuring-the-impact-of-github-copilot/>
**Why Essential:** Official GitHub guidance on measuring AI coding tool impact using the SPACE framework, supporting your measurement and metrics recommendations with an established methodology.
