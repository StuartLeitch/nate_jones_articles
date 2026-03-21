---
title: "55% of employers regret AI-driven layoffs. The agents are good at tasks and terrible at jobs. Here's what that means for your team and the 3 prompts that close the gap."
author: "Nate Jones"
published: 2026-03-21
url: https://natesnewsletter.substack.com/p/55-of-employers-regret-ai-driven
subtitle: "Watch now | The agents are getting better but the people deploying them? That's another story."
audience: everyone
scraped_at: 2026-03-21 12:00:16
---

The average software job in America lasts somewhere between 18 months and two years. The average AI agent run lasts about two hours. Even if we lament how short job tenure has gotten, those two numbers are not comparable. And the people who really hold institutional context, who keep a business going, often stay four, five, six, seven years. Maybe longer.

That gap is one of the hardest problems in tech right now, and it is leading a lot of over-optimistic people astray.

Earlier this week I wrote about the [vibe coding wall](https://natesnewsletter.substack.com/p/your-ai-agent-just-mass-deleted-a), the moment where individual builders who shipped real products with AI agents start hitting failures that better prompting can’t fix. The Grigorev story anchored that piece: a professional engineer whose agent wiped a production database because it didn’t know which infrastructure was real. But as I was writing it, I kept thinking about the bigger version of this problem. Because the wall isn’t just hitting solo builders. It’s hitting teams, departments, entire organizations. The same memory gap that causes an agent to delete a database is causing agents across legal, marketing, finance, and product to make decisions that are locally correct and organizationally catastrophic.

AI agents are getting extraordinarily good at doing work. They can write code, generate designs, close tickets, build financial models. The capability trajectory is real and accelerating. But they still have short-term memories over the arc of a real job, and they still lack common sense in weird, unpredictable ways. That combination, increasingly powerful but still brittle, means they are getting more destructive when they aren’t managed well. Not less. A mediocre tool that fails obviously is annoying. A powerful tool that fails silently is dangerous.

Two weeks ago, Alexey Grigorev’s AI coding agent wiped his production database. 1.9 million rows of student data, gone in seconds. The backups disappeared too. The agent never made a technical error. Every action was locally correct. It simply had no idea it was demolishing a live system, because the knowledge that distinguished real infrastructure from temporary copies existed only in the engineer’s head. Three new studies confirm this isn’t a fluke. It’s the pattern. And what the pattern reveals about the future of work, for engineers, for marketers, for lawyers, for anyone handing consequential tasks to an agent, is not what you’re hearing from most of the AI discourse.

**Here’s what’s inside:**

- **The task-versus-job gap.** Two benchmarks measuring the same AI models got wildly different results. The reason explains almost everything confusing about the current agent discourse.
- **What Cursor’s team actually did.** The part of the “AI built Excel from scratch” story that nobody talks about, and why it matters more than the demo.
- **The invisible skill the labor market is already paying for.** Harvard studied 62 million workers. The data doesn’t say what the headlines claim.
- **Why your best people should be writing evals, not your most junior.** The single highest-leverage investment most organizations are getting exactly backwards.
- **Contextual stewardship.** A framework for the human role that’s emerging whether we name it or not, and how to start building it this week.
- **Three prompts to start tonight.** A context gap audit, an eval writer for non-engineers, and a decision documenter that captures the reasoning your agents will never know on their own.

The best tools we have for managing agent risk are human brains and human brains crafting evaluations. Not better prompts. Not bigger context windows. Human judgment about what matters, what’s fragile, and what the AI doesn’t know it doesn’t know. Let me show you why.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260310_uv6_promptkit_1)

Fifty-five percent of employers regret AI-driven layoffs, and nearly all of them were blindsided because the context their people carried was never written down. This kit forces you to change that before something breaks. The Context Gap Audit interviews you about your specific workflows and produces a risk map showing exactly where dangerous knowledge lives only in heads. The Eval Writer takes those gaps and turns them into plain-language checks that run before, during, and after an agent acts, written so anyone on your team can use them without touching code. The Decision Context Documenter is the ongoing practice: it captures the *why* behind your choices so that the reasoning doesn’t vanish when the person who made the call moves on. Start with the audit. It takes twenty minutes and it will show you things you haven’t thought about.


## What actually happened

Alexey Grigorev runs the DataTalks.Club course platform, a system managing homework submissions, projects, and leaderboard entries across multiple courses spanning two and a half years. He was migrating a separate website to the cloud and decided to reuse his existing infrastructure setup to save a few dollars a month. His AI coding agent was running the deployment.

First warning sign: the agent started creating a long list of cloud resources that shouldn’t have existed. Alexey had recently moved to a new computer and hadn’t transferred his infrastructure configuration. We’ve all done that. The agent looked at the cloud, saw nothing it recognized, and assumed it was building from scratch. Pretty logical. Alexey stopped the process, but some duplicate resources had already been created.

Next step: he asked the agent to identify the duplicates and remove them. Very reasonable ask. But the agent decided on its own that instead of removing resources one at a time, it would be, in the agent’s words, “cleaner and simpler” to demolish everything it had created in one shot. Also reasonable, in isolation. What Alexey didn’t realize was that the agent had quietly unpacked an archived configuration file from his old computer. Inside that archive were the definitions for his real production infrastructure. So when the agent ran its demolition command, it wasn’t clearing out temporary duplicates. It was destroying the production database, the networking layer, the application cluster, the load balancers, the bastion host. Everything.

The story has a good ending, barely. It took 24 hours, an emergency support upgrade to Amazon, and a significant amount of luck to recover the data. Alexey immediately stripped the agent of all execution permissions. He now reviews every infrastructure change personally.

I want to be careful here: Alexey made a lot of reasonable asks. This is not a piece about bad engineering decisions. He made asks that many of us would have made in the same situation, and he got unlucky. That’s the point. The agent was competent. The agent was confident. And the agent was wrong about which world it was operating in, production or not production, without the self-awareness to ask.

The only thing that could have prevented this disaster was a human who understood the organizational context, or an evaluation that encoded that context into a guardrail before the agent ever ran that command. Neither existed. This, by the way, is why ElevenLabs is now pushing AI insurance for their agents. We are going to see a lot more of that.


## The evidence is piling up

Alexey’s story is vivid, but one story is not data. Here’s the data.

**The Remote Labor Index.** Scale AI and the Center for AI Safety tested frontier AI agents on 240 real freelance projects from Upwork: video production, architecture, 3D modeling, game development, data analysis. Average project cost: about $630. Average human completion time: 29 hours. That’s not out of the realm of possibility for today’s long-running agentic harnesses, especially with companies like Cursor bragging about multi-week agent deployments building extremely complicated software.

The best agent completed 2.5% of projects at a quality a paying client would accept. That is a 97.5% failure rate on real work.

Now here’s the confusing part. A different benchmark, GDPVal built by OpenAI, shows the same class of models approaching expert-level quality and completing tasks a hundred times faster than humans. Both numbers are real. The difference is that GDPVal gives the model all the context it needs up front: here is the brief, here is the deliverable format, here is what good looks like. The Remote Labor Index gives the model a client brief and some files and says figure it out. One of those sounds like a task. The other sounds like a job.

The gap between those two benchmarks is the gap between “can this AI do a task” and “can this AI do a job.” Tasks come with context provided. Jobs require you to bring your own. And if you’re wondering how we got from AI agents and a memory wall to a conversation about jobs, the logic is straightforward: if AI agents cannot complete an Upwork task with any degree of reliability, there is no rational basis for putting them in charge of entire jobs without extraordinary human infrastructure around them.

That infrastructure can be built. I have discussed examples in previous pieces, like the [dark factory model](https://natesnewsletter.substack.com/p/the-5-level-framework-that-explains), where you get tremendous speed-ups. But those speed-ups only happen when humans with really good judgment spend considerable time very thoughtfully figuring out how to do it. It does not happen magically when the CEO finds a LinkedIn post.

**SWE-CI.** A team out of Alibaba built the first benchmark that measures what happens when AI maintains software over time instead of writing it fresh. One hundred real codebases, each spanning an average of 233 days and 71 consecutive updates of actual development history. The agent has to evolve the codebase forward: adding features, fixing bugs, adapting to new requirements, the way real software gets built over months and years.

75% of models tested break previously working features during maintenance. Three out of four frontier models, asked to maintain code over time, actively make things worse. The benchmark punishes agents whose early decisions compound into technical debt later, and almost all of them do. Writing code and maintaining code are fundamentally different skills. We only benchmark the first one, and the first one is the basis for the dramatic claims from Dario Amodei and others about jobs disappearing. But if you still need a human to maintain the code, what exactly are we celebrating?

This matters because when the Cursor team set up their agents to build those impressive projects, recreating Excel, writing a browser, they had to deliberately set the intent. They had to design the agent harness: the context, the tools, the sub-agents, the reporting structure, all of the scaffolding that goes into a long-running task. All of it was human-designed. The agent gets credit for doing great work, and it deserves some. But the humans who built that infrastructure deserve credit too, and the people reading the LinkedIn posts about it should remember that smart humans had to deploy and maintain the whole thing.

**The Harvard seniority paper.** Hosseini Maasoum and Lichtinger studied 62 million American workers across 285,000 firms from 2015 to 2025. Companies that adopted generative AI saw junior employment drop roughly 10% relative to non-adopters within a year and a half. Senior employment kept rising. The decline hit hardest in AI-exposed occupations and, critically, was driven by slower hiring, not more firing.

The conventional read: AI replaces junior workers. The better read: AI replaces task execution. Juniors were hired for tasks like debugging, document review, and first drafts. They shouldn’t be anymore, and I have suggested better roles for juniors in recent pieces. AI does those tasks adequately in isolation. Seniors survive because they provide something different. They know which parts are load-bearing, what the decision history looks like, and the things nobody ever wrote down. The Harvard data is showing a labor market that is learning, in real time, that context is the scarce resource. Not execution.


## This is not an engineering story

I need you to make a jump with me here, because this is the part that matters for everyone reading this, not just the people who write code.

Alexey’s disaster, a technically capable agent completely blind to organizational context, is not a software problem. It is a pattern that’s about to repeat in every knowledge work domain where agents get deployed. And in 2026, agents are getting deployed everywhere. There is no industry they aren’t touching. If they haven’t come to your work yet, they’re coming soon.

Picture a legal team that gives an agent the job of reviewing contracts. The agent can parse clauses, flag risks, compare against templates. What it cannot know is that this particular vendor has an informal understanding about payment terms that was negotiated over dinner three years ago. It cannot know the company is in quiet acquisition talks and certain intellectual property clauses are suddenly existential. The agent will review the contract competently and miss the thing that actually matters, because that thing lives in the general counsel’s head, not in any document.

Or a marketing team running agents on campaign operations. The agents can build audiences, draft copy, allocate budget across channels. They cannot know the brand had a crisis in that market segment eight months ago and the tone needs to be completely different there. They cannot know the CMO made a promise to the CEO about a positioning shift that hasn’t been written down anywhere. The agents will execute a technically strong campaign that reopens a wound the organization spent months healing.

Or finance. Agents can build technically perfect projections. They cannot know that certain numbers are politically dangerous internally even if they are arithmetically correct. They can’t read the room. They don’t know what the board cares about this quarter versus last. Unless you tell them.

In every case, the agent does the task well. In every case, the agent cannot know whether this is the right task, done the right way, at this moment, in this organizational context. And in every case, the human who holds that context is the difference between the agent creating value and the agent creating damage. In some cases, existential damage.


## The market already knows this

Right now we are all playing a game of high-stakes telephone. CEOs hear that AI can do a lot of things, and it can. It is absolutely transformative. What they are not hearing soon enough is that really good humans are needed to make that transformation work, and that AI being incredibly capable does not mean you don’t need good people in the enterprise.

Gartner predicted in February that by 2027, half the companies that cut staff for AI will rehire workers to perform similar functions, often under different job titles. Their survey of over 300 customer service leaders found only 20% had actually reduced headcount because of AI. Forrester’s data is sharper: 55% of employers say they regret AI-driven layoffs. That number does not get talked about nearly enough.

Klarna is the case study everyone should know. They cut roughly 700 customer service positions for an AI chatbot. They reversed course and started rehiring. The CEO called it a “VIP experience.” The reality: the AI couldn’t handle the contextual complexity of real customer interactions at the quality their business required.

Meanwhile, roughly 53,000 tech workers have been laid off as of early 2026. But the Gartner rehiring wave, the Harvard seniority data, and the jobs numbers all tell the same story: organizations are shedding task-execution capacity and discovering they still need the humans who understand what’s actually going on. The job titles will change. The function doesn’t disappear. The sorting is gradual, invisible, and already happening. Companies won’t announce mass AI replacements. They’ll let people go at normal rates and hire at much slower rates. Those who remain absorb the slack with AI tools, and that naturally selects for the people who can direct agents effectively, which means the people who hold enough context to know when the agent’s output is right and when it’s about to blow something up.


## The eval gap

So if human judgment is the critical safeguard and context is the scarce resource, the obvious question is: how do you scale human judgment? You can’t put a senior engineer or a veteran general counsel in front of every AI action. It doesn’t work at speed.

The answer is evaluations. Evals. And this is where the industry is failing worst.

An eval, at its core, is a way of encoding human judgment into a test that runs before, during, or after an agent acts. It’s the bridge between what the human knows and what the machine does. A good eval would have caught Alexey’s disaster. Something as simple as “before destroying any cloud resource, verify it is not tagged as production” or “before any bulk infrastructure change, compare the current state file against the known production manifest.” These aren’t complicated. They’re the kind of thing a senior engineer knows to check and an AI agent will never think to check on its own.

But most companies deploying AI agents don’t write evals at all. And the ones that do usually write them badly. They have someone junior sitting in front of a spreadsheet, writing what looks like a reasonable test set, and nobody ever asks about methodology, or whether the evals are actually good, or whether they can prevent real-world disasters. Nobody asks until it’s too late.

Most evals test surface-level correctness. Did the code compile? Does the output look right? They don’t test whether the output is safe for this specific environment, appropriate for this organizational context, or aligned with decisions that were made six months ago. And I think it’s not an accident that we treat eval writing as a chore and hand it to the most junior person available. Junior people don’t have the context. You need your senior people writing evals.

The skill of writing great evaluations is the exact same skill that makes senior people valuable. You have to know what “right” looks like in your specific situation, not just in general. You have to understand the system well enough to anticipate where an agent will go wrong in ways the agent can’t anticipate for itself. That is contextual judgment encoded into infrastructure.

And this applies across every domain, not just engineering. A legal team can build evals that check whether contract changes conflict with known relationship terms. A marketing team can build evals that flag campaigns touching sensitive market segments. A finance team can build evals that catch projections contradicting board-level commitments. None of these require anyone to write code. They require someone who understands the organizational context well enough to say “here are the things an AI must not get wrong in our specific situation.”

I can hear the objection already, because I’ve talked to engineers and other senior people who say: I don’t want to do this work because if I do it, I think they’ll fire me. Go back to the Forrester number. 55% of employers regret AI-driven layoffs. Yes, there are leaders who make bad decisions. Maybe yours is one of them. But any leader worth their salt needs to understand that eval design is an evolving skill based on evolving context. If you think you can write an eval for an agent and then be replaced, and then the eval will magically keep working as the world changes around it, you are going to get something like what happened to Alexey except at corporate scale. And it’s going to be really bad.

If you’d like to show this piece to a leader and say, hey, Nate says this, that’s fine. Make me the bad guy.

The companies that win the next few years will be the ones that treat eval design as a core organizational competency, not a developer task, not an afterthought, and not something to hand to your most junior person. A primary expression of ongoing institutional knowledge. If you’re deploying agents without investing equally in evaluation infrastructure, you’re handing a powerful tool to a system that has no idea what it’s not supposed to destroy.


## Becoming a context engine

The human role in an agentic world is what I’ve started calling contextual stewardship: maintaining the mental model of your system, representing what you know in ways machines can use, and exercising judgment about when technically correct output is organizationally wrong.

This is not a technical skill. It’s not about learning to code or mastering a particular AI tool. It’s about becoming the person in your organization who holds the context that keeps the machines from going sideways. And it can be developed deliberately.

Start documenting decisions, not just outcomes. Most organizations track what happened. Almost none capture why: the constraints, the tradeoffs, the context that made one choice better than another at that specific moment. And they certainly don’t capture it in a way that’s repeatable or useful to a system. That decision context is the raw material that makes agents effective. Its absence is what makes them dangerous. When Alexey’s agent destroyed his database, the critical missing piece wasn’t a fancier model. It was a record of which infrastructure was production and why.

Develop system-level thinking. Not just for engineers. For everyone operating in a complex environment, which is increasingly all of us at work. Understand how the pieces of your organization connect. Think about second-order consequences. The marketing lead who knows the brand’s wound history is doing system-level thinking. The general counsel who knows the unwritten relationship terms is doing system-level thinking. This is the senior skill the Harvard data says the market is paying for, so we should probably be developing it.

And invest in your ability to write evaluations, even if it doesn’t feel glamorous at first. This is the highest-leverage thing most people are not doing. You don’t need to be an engineer. You need to know your domain well enough to articulate: here are the things that must be true for this output to be safe in our world. Here are the constraints an AI doesn’t know about. Here are the checks that would have caught the disaster before it happened.

And if you’re thinking, I don’t have agents, why do I need to do this? Check again. If you have Claude in your browser, you have an agent. If you have Claude in Excel, you have an agent. If you have ChatGPT using your computer, you have an agent. The ability to write an eval is the ability to scale your judgment across every agent you touch.

I’ll say this because I’ve been that person: earlier in my career, I accidentally deleted half an Oracle iStore instance, thanks to a terrible UX inside Oracle at the time. The feeling in the pit of my stomach is one I will never forget. The tools change. The stakes of getting context wrong don’t.


## The asymmetry

Agent capabilities are advancing fast and the trajectory is real. Don’t walk away from this piece thinking otherwise, because it is happening. But the capabilities are advancing asymmetrically. Task execution is improving at a pace that makes quarterly planning feel obsolete. Contextual understanding, the kind that prevents an agent from obliterating your database or sending the wrong tone to a wounded market or building a forecast that detonates in the boardroom, is improving much more slowly. If it’s improving at all.

That asymmetry is the story. Not “AI is overhyped.” It isn’t. It might actually be underhyped, honestly. Not “AI will replace everyone,” because the evidence increasingly suggests otherwise. The story is that the gap between what agents can do and what agents understand is widening, because agents are getting more intelligent without getting better at memory. The humans who close that gap, through judgment, through context, through evals, will become the most valuable people in their organizations. The humans who choose not to will find themselves competing with machines on the only dimensions where machines improve fastest.

And there is a question nobody is asking loudly enough. When we talk about giving agents long-running organizational context, we are talking about the story of your company that lives inside people’s heads. Do you want to hand that to a private AI company? That question has no easy answer, and it matters more than most of the agent conversations happening right now.

Gartner’s rehiring prediction is not about AI failing. It’s about organizations discovering, too late, what their humans were actually providing. The task execution was visible. The contextual stewardship was invisible. You don’t realize invisible infrastructure is load-bearing until you remove it and something collapses.

The agents are here. They work. They’re improving every quarter. And every single one of them is blind to the context that keeps real organizations alive.

Your job, whatever your title, whatever your domain, is to be the one who sees what they can’t. And then to write the eval that makes sure they never have to.

[![](https://substackcdn.com/image/fetch/$s_!c-8F!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6d4cc657-7e5e-470b-8ddf-bbb3761e403d_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!c-8F!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6d4cc657-7e5e-470b-8ddf-bbb3761e403d_1024x1024.png)
