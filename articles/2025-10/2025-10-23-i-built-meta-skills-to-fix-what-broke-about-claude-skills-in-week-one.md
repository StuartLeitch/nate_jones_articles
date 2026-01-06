---
title: "I Built Meta-Skills to Fix What Broke about Claude Skills in Week One"
author: "Nate Jones"
published: 2025-10-23
url: https://natesnewsletter.substack.com/p/i-watched-100-people-hit-the-same
audience: everyone
scraped_at: 2026-01-05 19:13:38
---

Everyone loves Claude Skills!

The problem is that with all that attention we’ve discovered lots of common teething issues, and that’s what this post is all about.

I went through my DMs and messages from the last week and found all the common issues with Claude Code:

- Skills that won’t trigger
- Issues with zip files
- Context window overflows
- Questions about security if Skills run code
- Questions about how to evaluate Skills

The list goes on, and I decided to do something about it. So I sat down and looked across the issues and realized what we need is really a building kit for Claude Skills.

A set of tools that we can go back to to build skills with confidence, to troubleshoot them, etc.

Plus, we needed a clear guide with common pitfalls and tips and tricks, grounded in hard and real experience.

I wrote both. I wrote a guide for the common pitfalls and and I wrote 10 quick Claude Skills tools to help you get the most out of this powerful new tool. (And if you’re still wondering what Claude Skills are, [check out my intro post on that](https://natesnewsletter.substack.com/p/new-claude-just-made-prompting-10x) from last week.)

Here’s what I built:

- **skill-debugging-assistant** - Fixes skills that won’t trigger
- **skill-security-analyzer** - Audits third-party skills for malicious code
- **skill-gap-analyzer** - Identifies missing skills from repeated explanations
- **skill-performance-profiler** - Shows which skills waste tokens
- **prompt-optimization-analyzer** - Catches bad descriptions before deployment
- **skill-testing-framework** - Runs automated tests after changes
- **skill-doc-generator** - Creates consistent documentation across your library
- **skill-dependency-mapper** - Shows how skills interact and bottleneck
- **learning-capture** - Identifies patterns worth turning into skills
- **token-budget-advisor** - Tackles context limits with chunking strategies

If this is looking a little familiar, it should. This is the so-called boring toolset that treats Skills like what they are: code we can read in plain English.

I’ve been saying for months now that we should treat our prompts as code. As I wrote last week, Skills are super-leveraged prompts. Well, they’re code too!

But I know we all don’t have a ton of time, and we really just need to be able to build our own Skills for what we need and be confident they work.

That’s exactly what this kit is for! It gives you everything you need to build the Skills you want with confidence—plus I show you two end-to-end examples in the video so you can see how I do it.

It has never been a better time to work using AI. Skills give us 10x leverage—I use them every day. I want you to have the same tools I have to build the Skills YOU want.

Have fun, and happy building!


## *[Grab the skills here](https://drive.google.com/drive/folders/1Nv6GHa8cHvN0EW3xoCqqSufGAbQihvqc?usp=sharing)*

These nine meta-skills solve a different class of problem than typical skills. Instead of helping you create presentations or analyze spreadsheets, they provide infrastructure for your entire skills ecosystem.

They debug why skills don’t trigger, audit security risks before you run community skills, identify gaps in your coverage, optimize token usage, automate testing, and generate consistent documentation.

The most interesting one—learning-capture—watches your work and identifies patterns worth formalizing into new skills, making Claude an active participant in its own improvement.

Together, they turn skills from a collection of tools into a self-maintaining system. You don’t need all nine immediately, but each one addresses a specific pain point that breaks at scale: routing failures, security concerns, version chaos, token waste, and the constant question of “what should I build next?” They’re the infrastructure layer most people aren’t building yet, but probably should be.

> Note: these are .skill files, which means they work natively with Claude, and if you tell ChatGPT they are zip files ChatGPT swears a bit and opens them up nicely.

---


## *[And grab the complete guide here](https://docs.google.com/document/d/1niP1CU4VoQByPII-JbC9rQ9bFb0mIJfJdApJAJh3vMM/edit?usp=sharing)*

This guide covers everything you need to know to use Claude Skills effectively across all platforms—Code, Web/Desktop, and API. It addresses the 10 most common mistakes people hit in the first week (from forgetting to enable Code Execution to version chaos across platforms), explains how to set up skills for each distribution method, and provides best practices that actually scale (treat skills like code, design for routing explicitly, automate testing).

It also introduces the meta-skills layer: infrastructure skills that debug other skills, analyze security risks, identify coverage gaps, optimize performance, and even capture patterns from your work to recommend new skills.

Whether you’re an individual developer using Code with git, a team manually distributing ZIPs, or a product team integrating skills via API, this guide provides the practical workflows, troubleshooting steps, and automation strategies you need. Bookmark this—it’s the reference you’ll come back to when something breaks or you’re setting up skills infrastructure for the first time.

---


# I Built Meta-Skills to Fix What Broke about Claude Skills in Week One

Skills launched last week and my DMs exploded. Not with excitement—with confusion. The same problems kept surfacing: “My skill won’t trigger.” “I uploaded it but nothing happens.” “Which version am I actually running?” “Is this safe to use?” People understood the concept but were hitting the same walls repeatedly. Instead of answering the same questions individually, I did what anyone with a pattern recognition problem does: I built infrastructure to solve it systematically.

I built 10 meta-skills—skills specifically designed to help you build, debug, test, and optimize other skills. They address the exact pain points I watched the community hit in week one. This isn’t about what skills *can* do in theory. This is about what actually broke in practice, and how to fix it.


## What Actually Trips People Up

After a week of DMs and watching people struggle in public forums, the failure modes are consistent. Here are the 10 things that keep breaking:

**Platform packaging confusion.** Skills have one format but three completely different distribution modes. Claude Code reads skills directly from folders on disk. Web and Desktop require ZIP files uploaded through Settings. The API uses `/v1/skills` endpoints with programmatic versioning. People expect one method to work everywhere—it doesn’t. You’ll write a skill once and then fight three different packaging workflows.

**Code execution isn’t enabled.** This is the number one silent failure. Your skill uploads correctly, shows up in your library, but nothing happens when you try to use it. The toggle wasn’t on. Settings → Features → Code Execution → On. Without it, skills are decoration.

**Skills don’t trigger when expected.** Claude decides which skill to invoke based on your description and context. Vague descriptions mean Claude picks the wrong skill or no skill at all. The first paragraph of your SKILL.md matters more than anything else—if the router can’t distinguish your skills in three seconds of scanning, you’re going to have invocation problems.

**Version chaos across surfaces.** You iterate fast in Code, forget to package a ZIP, then wonder why the web version isn’t working. Your local skills are ahead of your ZIP in the web app, and if you’re also using the API, you’ve got three versions of the same thing living in parallel. Without a source of truth, you’re constantly debugging “which version am I actually running?”

**Missing skill IDs from the API.** If you’re using `/v1/skills` endpoints, you need to save the skill\_id that gets generated. Otherwise you’re recreating the same skill over and over, wasting API calls and breaking references. The API gives you an ID—capture it, store it, use it.

**No team distribution.** There’s no “push to everyone” button. Each person uploads their own ZIP in Web/Desktop. For teams, this means either using Code with git-based distribution (everyone pulls and gets skills automatically) or using the API from your backend to attach skills consistently.

**Security assumptions.** Skills run in a sandbox through Claude’s code execution environment, but you’re still responsible for everything you put in them. Downloading third-party skills from GitHub without reviewing them means accepting code you haven’t audited. That code will run with whatever permissions Claude’s execution environment has.

**Marketplace misunderstanding.** When docs mention a “marketplace,” that’s Claude Code only. Web and Desktop don’t have a marketplace—you upload manually. People expect centralized discovery across all platforms. It doesn’t exist.

**Too many overlapping skills.** The router prefers narrow intent over flexibility. When you have one mega-skill trying to handle presentations, design templates, brand guidelines, and data visualization, the router has no idea when to use it. Better to split into focused skills: one for pitch decks, one for branded presentations, one for data-heavy slides.

**Documentation fragmentation.** Instructions for Code are in one place, Web/Desktop uploads in another, API details somewhere else. None of them cross-reference. People think features work across all platforms—they don’t. You end up re-googling the same URLs constantly.

These aren’t edge cases. These are the default experience for anyone building skills seriously.


## The Distribution Problem Specifically

The core confusion that trips everyone up: skills have one format but three completely different distribution modes. You write them once—a folder containing a SKILL.md file with your instructions—but getting them into Claude depends on which version you’re using.

Claude Code (the terminal tool for developers) reads skills directly from disk. Drop a folder into `~/.claude/skills` or your project’s `.claude/skills/` directory, and it’s live. This is by far the cleanest approach. If you’re working with a team and your skills are in git, everyone gets them automatically when they pull. No upload step, no manual distribution, just version control doing what it does.

> ***Side note for non-technical readers:** I need to use some technical terms here throughout the article. You can ask ChatGPT to explain it to you and that will help.*
>
> *For example, I asked ChatGPT to explain the technical paragraph above like I’m a non-technical 12th grader, and this is what it said:*
>
> *Claude Code is a command-line tool (like a text-based app for developers). It looks for “skills” — basically little programs or files that teach it new tricks — in a specific folder on your computer.*
>
> *If you drop a folder of skills into one of these spots:*
>
> - *your main ~/.claude/skills folder (the default place Claude looks), or*
> - *the .claude/skills folder inside your current project,*
>
> *Claude instantly sees and loads them — no setup needed.*
>
> *If you’re on a team and your code is stored in Git (a tool that tracks changes in shared projects), everyone automatically gets the same skills when they sync their work. That means you don’t need to upload anything or share files manually — Git handles it for you.*
>
> *In short: **put your skill files in the right folder, and they just work for everyone.***

The web app and Claude Desktop, though, require ZIP files uploaded through Settings → Capabilities → Skills. Every time you update a skill, you need a new ZIP and a new upload. This creates version drift immediately. Your local skills in Code are ahead of your ZIP in the web app, and if you’re also using the API (which has its own versioning system via `/v1/skills` endpoints), you’ve got three versions of the same thing living in parallel.

The single biggest mistake I made early on was not picking a source of truth. I’d iterate fast in Code, forget to package a ZIP, then wonder why the web version wasn’t working. Eventually I built a GitHub Action that packages ZIPs and registers skills with the API on every tag. It’s not glamorous but it prevents the “which version am I actually running” confusion that eats up way too much mental energy.


## So I Built Infrastructure

Instead of explaining these pitfalls individually in DMs, I built meta-skills to address them systematically. These aren’t task-specific skills like “create a pitch deck” or “analyze a spreadsheet.” These are skills about skills—infrastructure for debugging, testing, optimizing, and evolving your entire skills library.

I now have 10 meta-skills running. Each one solves a specific pain point I watched people hit repeatedly:

- **skill-debugging-assistant** for when skills don’t trigger or behave unexpectedly
- **skill-security-analyzer** for auditing skills before you run them
- **skill-gap-analyzer** for identifying what your library is missing
- **skill-performance-profiler** for tracking token usage and invocation patterns
- **prompt-optimization-analyzer** for reviewing skill descriptions before deployment
- **skill-testing-framework** for automated validation of skill behavior
- **skill-doc-generator** for standardized documentation across your library
- **skill-dependency-mapper** for understanding how skills interact
- **learning-capture** for identifying patterns worth formalizing into new skills

The last one—learning-capture—is the most interesting, and I don’t think anyone else is doing this yet.


## The Meta-Skills Layer

Here’s how each meta-skill directly addresses what breaks in practice:


### When Skills Don’t Trigger: skill-debugging-assistant

The most common DM: “I built a skill but Claude isn’t using it.” The debugging assistant analyzes your SKILL.md for trigger failures, parameter problems, and prompt conflicts. It checks YAML frontmatter, validates descriptions against routing best practices, examines progressive disclosure structure, and identifies absolute statements that might cause conflicts with system instructions.

It caught an issue with my vibe-coding skill (for building apps with Cursor and Lovable) getting invoked when I asked about Excel formulas. The description mentioned “development” and “tools,” which was enough to confuse the router. The debugging assistant flagged the overlap and suggested more adversarial specificity: not just “what this does” but “when to use this, when NOT to use this, what inputs it expects, what outputs it produces, and what it explicitly doesn’t handle.”


### When You’re Worried About Security: skill-security-analyzer

Third-party skills are code. You’re accepting arbitrary execution without review unless you explicitly audit them. The security analyzer runs comprehensive risk analysis: checks for dependency vulnerabilities, evaluates code execution patterns, assesses data handling, validates input sanitization, and flags potential malicious behavior.

I treat skills like dependencies now. Before I add one, I run it through the security analyzer. If it flags concerns I don’t understand, I don’t use it. I also maintain a SECURITY.md file for each skill documenting what capabilities it needs and what risks it introduces. This isn’t paranoia—it’s hygiene. The skills model is powerful precisely because it can execute arbitrary code. That power requires you to be deliberate about what you enable.


### When You Don’t Know What to Build: skill-gap-analyzer

“What skills should I even create?” The gap analyzer reviews your entire skills library and identifies coverage gaps based on common workflows. It analyzes patterns across your conversations, looks for repeated explanations that burn context window tokens, and recommends specific skills that would have high ROI.

It told me I was repeatedly explaining how to read research papers, walking through the same methodology each time. I formalized that into the research-paper-reader skill. It caught that I was re-explaining agentic development best practices constantly. That became the agentic-development skill. The gap analyzer doesn’t just identify holes—it quantifies the token savings you’d get by filling them.


### When You’re Burning Tokens: skill-performance-profiler and token-budget-advisor

The performance profiler tracks which skills are heavy on tokens and which get invoked frequently. It measures token consumption per invocation, identifies expensive skills that might need optimization, and detects skills that aren’t getting used at all (candidates for removal).

The token-budget-advisor goes further: it proactively assesses token consumption risk before you even start a task. When you’re uploading multiple large files or asking for comprehensive multi-document analysis, it evaluates whether the task will strain the context window and recommends specific chunking strategies.

I built the powerpoint-chunker skill in response to community feedback about hitting context limits on presentation-heavy tasks. Instead of creating a 40-slide deck in one shot and running out of tokens, the chunker breaks the work into phases: outline first, then 10 slides at a time, with reviews between chunks. The token-budget-advisor identifies when you need this approach before you waste tokens finding out the hard way.


### When Your Descriptions Are Bad: prompt-optimization-analyzer

Writing good skill descriptions is harder than it looks. The prompt-optimization-analyzer reviews new skills for token waste, anti-patterns, and trigger issues before you commit them. It identifies vague language, catches missing negative examples, flags overly broad descriptions, and suggests specific improvements with examples.

I learned to avoid the “mega-skill” temptation the hard way. When you have one skill trying to handle presentation creation, design templates, brand guidelines, and data visualization, the router has no idea when to use it. The prompt-optimization-analyzer caught this pattern and recommended splitting into focused skills: one for pitch decks, one for branded presentations, one for data-heavy slides. The router prefers narrow intent over flexibility.


### When You Need Quality Assurance: skill-testing-framework

“How do I know if my skill actually works?” The testing framework provides structured validation: unit tests for individual skill components, integration tests for multi-skill workflows, regression tests after updates, and input/output pair validation against expected results.

I have a small set of test prompts for each skill that should trigger invocation and produce expected outputs. These run in CI on every change. When a skill stops getting invoked correctly or produces wrong results, the tests catch it before I notice in production. This is especially important for skills with overlapping domains—the eval harness proves they’re distinct.


### When You Need Documentation: skill-doc-generator

Maintaining consistent documentation across my 19 skills is tedious. The doc-generator auto-generates standardized README files from SKILL.md frontmatter, validates consistency (terminology, structure, formatting), creates usage examples, and identifies documentation gaps.

Every skill in my library has standardized documentation now. The doc-generator ensures I’m not reinventing formats, catches inconsistencies, and makes the library navigable. When someone asks “what does your xlsx-editor skill do differently from complex-excel-builder?” the documentation is clear because it was generated from a consistent template.


### When You Need to Understand Dependencies: skill-dependency-mapper

As your skills library grows, understanding how skills interact becomes critical. The dependency mapper analyzes the ecosystem to visualize dependencies, identify workflow bottlenecks, and recommend optimal skill stacks for different tasks.

It showed me that six of my skills depend on outputs from the gap-analyzer, making it a bottleneck. If the gap-analyzer breaks, half my meta-infrastructure fails. That insight pushed me to add better error handling and fallbacks. The mapper also identifies skills that should work together but don’t—opportunities to improve integration.


### The Recursive Layer: learning-capture

This is the meta-skill that changes everything. Instead of manually deciding when to create new skills, learning-capture watches your work sessions and recognizes when you’ve solved something the same way twice or built up complex domain knowledge across multiple conversations.

When it sees high-ROI patterns (things that will save 500+ tokens per reuse across 10+ future conversations), it offers to formalize them into a new skill. I’ve created four skills this way that I would never have thought to write manually. It recognized my repeated explanations about requirements elicitation from product docs—that became a skill. It caught my pattern of walking through pitch deck narrative development—that became another skill.

The learning-capture skill makes Claude actively participate in its own improvement. Instead of just using skills, I’m curating and evolving an ecosystem. It’s the difference between having a collection of scripts and having infrastructure you maintain.


## What Actually Works at Scale

After building 19 skills and using them daily for just under a week, a few patterns have emerged that seem to generalize.

> I should note this is most helpfully applied to the practical skills you build with meta-skills such as those I’m sharing—if you’re building all this stuff into meta-skills you’re probably [shaving the yak](https://softwareengineering.stackexchange.com/questions/388092/what-exactly-is-yak-shaving). So think of these rules of thumb as more and more applicable as you build with skills more and more seriously.

**First, treat skills like code from day one.** Version them with semver, write changelogs, review changes before deploying. I keep all my skills in a monorepo with a `/skills/` directory containing one folder per skill. A simple GitHub Action packages ZIPs, uploads to the API, and writes back the skill\_id to a JSON map. This makes rollbacks trivial and gives me a clear history of what changed when.

**Second, design for routing explicitly.** Every skill needs negative examples in its description—not just what it does, but what it doesn’t do. “Do not use this for financial modeling, compliance documents, or multi-tab workbooks” isn’t fluff, it’s router guidance. Include concrete input contracts and examples of when the skill should fire. The router is pattern-matching against your description, so give it unambiguous signals.

**Third, build eval harnesses before you need them.** I have a small set of test prompts for each skill that should trigger invocation and produce expected outputs. These run in CI on every change. When a skill stops getting invoked correctly or produces wrong results, the tests catch it before I notice in production. This is especially important for skills with overlapping domains—the eval harness proves they’re distinct.

**Fourth, name skills by job-to-be-done, not by team or person.** “ppt\_brand\_apac” tells you exactly what it’s for. “marketing\_team\_helper” tells you nothing. Keep each skill single-purpose. If you need multiple capabilities, create multiple skills and compose them. The router handles composition better than you can handle mega-skills.

**Fifth, prefer the API for distribution if you’re working with a team.** Authoring happens fastest in Code (tight loop, local files), but publishing via the API gives you IDs, versions, and rollback capabilities. Your app or orchestrator can attach skills consistently across all users without manual uploads.


## The Compounding Effect

Here’s what I think gets under-sold: skills compound. Each new skill makes it easier to build the next one. The skill-doc-generator creates standardized documentation from my SKILL.md files, ensuring consistency across the library. The prompt-optimization-analyzer reviews new skills for token waste and anti-patterns before I commit them. The learning-capture skill identifies patterns worth formalizing while I work.

The token economics also compound. Each skill I add reduces the amount of re-explanation needed in future conversations. My context windows are cleaner because specialized knowledge lives in skills rather than being re-loaded every conversation. For tasks that used to require multiple back-and-forth clarifications, the right skill makes the first response correct.

I’m not claiming skills are transformative for everyone. If you’re mostly using Claude for one-off questions or casual conversation, the overhead isn’t worth it. But if you’re using Claude for recurring work—especially work that requires specialized knowledge or consistent methodology—skills shift the economics dramatically. The setup cost amortizes quickly when you’re no longer burning tokens re-explaining yourself.

The meta-skills ecosystem in particular feels under-explored. Skills for analyzing skills, for generating skills from examples, for testing skills, for documenting skills—this recursive layer turns skills from a collection of tools into a living system. I suspect the most valuable skills won’t be task-specific ones but the ones that make other skills better.


## Start Small

If you’re thinking about building skills, start small. Pick one task you do repeatedly and formalize it. Don’t overthink the infrastructure initially—just create a folder with SKILL.md and get it working in Code. The sophistication can come later, after you’ve felt the benefit of having one skill that actually makes your life easier.

Once you have two or three working skills, that’s when the meta-layer starts making sense. Add the debugging assistant when you hit your first “why isn’t this triggering?” moment. Add the security analyzer before you start using community skills. Add the gap analyzer when you’re wondering what to build next.

The rest compounds from there. Each meta-skill makes the next skill easier to build. The infrastructure becomes self-reinforcing. What surprised me most is how much clearer my thinking about AI usage became after building skills. Creating a skill forces you to formalize your mental model of a task. You can’t write good trigger descriptions unless you understand exactly when the skill should and shouldn’t apply.

I don’t know if my skills library is “good” in any objective sense, because we’re all writing the rules together. I think it’s useful. I think it’s needed now, and that why I’m sharing it here. For now, it works for how I think, and it makes Claude substantially more useful for my work. That’s enough for me, and I hope it helps you!


## Where can I learn more?

I have two great guides to recommend if you want to dig deeper:

[The Definitive Guide to Claude SKILLS: Code vs Web vs Desktop vs API

Finally, a clear explanation of what the hell is going on - add this post to your project instructions, or create a skill with it so you always have the right context! (I mean… until it changes…

Read more

2 months ago · 6 likes · 1 comment · Limited Edition Jonathan](https://limitededitionjonathan.substack.com/p/the-definitive-guide-to-claude-skills?utm_source=substack&utm_campaign=post_embed&utm_medium=web)

Enjoy!

---

[![](https://substackcdn.com/image/fetch/$s_!nD2u!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb63fade2-5106-4f1b-91b6-d27246ee4a9c_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!nD2u!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb63fade2-5106-4f1b-91b6-d27246ee4a9c_1024x1024.png)
