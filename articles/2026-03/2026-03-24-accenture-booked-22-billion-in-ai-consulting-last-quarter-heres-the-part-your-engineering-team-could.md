---
title: "Accenture booked $2.2 billion in AI consulting last quarter. Here's the part your engineering team could have handled for free."
author: "Nate Jones"
published: 2026-03-24
url: https://natesnewsletter.substack.com/p/youre-about-to-spend-millions-on
subtitle: "Watch now | Your agent deployment has five hard problems. Four of them are your team's job."
audience: everyone
scraped_at: 2026-03-24 12:00:17
---

Nvidia just open-sourced the security layer the entire agent industry has been waiting for. Three weeks earlier, OpenAI signed multi-year partnerships with McKinsey, BCG, Accenture, and Capgemini to deploy agents for you. Anthropic inked similar deals with Accenture and Deloitte.

These are not complementary strategies. They are competing theories of how hard agent deployment actually is, and the one your company picks determines whether you spend millions on consultants or tens of thousands on engineering time.

On Monday at GTC, Jensen Huang released NemoClaw, an open-source agent security stack, and told every company in the world to build their own agent infrastructure. OpenAI’s framing from three weeks ago told you the opposite: “The limiting factor isn’t model intelligence — it’s how agents are built and run in organizations.” That’s a model company telling you the model isn’t the bottleneck, and pointing you toward the consulting firms that are.

I spent the last two weeks pulling apart the engineering underneath both sides of this argument. The agent deployment problems that everyone frames as unprecedented are, with one critical exception, well-understood engineering with fifty years of precedent. I mapped the five hardest production problems against what’s actually required to solve them. The ratio — four engineering problems your team can handle, one domain expertise problem where you probably need help — changes the build-or-buy calculus entirely, and nobody selling you either side has any incentive to say it.

**Here’s what’s inside:**

- **The two colliding stories.** How a year of failed enterprise AI deployments and a catastrophic agent security crisis produced two opposite theories of what you need, and why most companies will pick wrong.
- **The fifty-year-old insight nobody’s applying.** Why the engineering principles underneath NemoClaw, Factory.ai’s codebase research, and Alvin Sng’s work on lint-as-architecture all converge on the same conclusion the hype cycle is hiding.
- **The five hard problems, scored.** Context compression, codebase instrumentation, linting, multi-agent coordination, and the specification problem, with the data that shows which ones your team can solve and which one you should pay for.
- **The build-or-buy framework.** Three variables, scored honestly, that tell you whether NemoClaw is your path or whether you genuinely need Accenture.
- **The SaaS collapse.** Huang’s claim that every software company becomes a “token manufacturer,” and why the consulting firms’ own clients are the ones most at risk.
- **Four prompts to run before you sign anything.** A prompt kit that tells you exactly which parts of agent deployment your team handles and which parts are worth paying for.

The 4:1 ratio in this piece will tell you exactly where to spend money and where to spend engineering time. For most companies, the difference is seven figures a year.


## **LINK: [Grab the prompts](https://promptkit.natebjones.com/20260321_hgt_promptkit_1)**

Most agent deployment decisions get made in a single meeting where someone presents a slide deck and nobody in the room has a framework for separating what their engineers can build from what genuinely requires outside expertise. These four prompts are designed for four different seats at that table. The Build-or-Buy Diagnostic scores your organization across the three variables in this article and routes you to a specific recommendation before you sign anything. The Codebase Agent-Readiness Audit runs Factory’s eight-pillar assessment and generates a prioritized fix list measured in days. The Consulting Proposal Decomposer takes any SOW and separates commodity engineering being sold at partner rates from domain expertise worth paying for. And the Personal 4:1 Map translates the five hard problems to your specific role and stack, so you know exactly where your effort compounds and where to stop.


## The year enterprises couldn’t figure it out

All through 2025, OpenAI and Anthropic operated on the same assumption: we ship the models, enterprises figure out deployment. Give companies access to GPT-4, Claude, increasingly powerful reasoning models, and capable organizations will integrate them into their workflows. The model companies would sell API access and tokens. The enterprises would handle the rest.

It didn’t work.

McKinsey published their State of AI report and the numbers were brutal. 88% of organizations were using AI in at least one function, so adoption wasn’t the problem. But only 6% qualified as high performers with meaningful impact on their bottom line. Two-thirds hadn’t scaled AI beyond isolated experiments. IBM’s CEO study found only 25% of AI initiatives delivered expected ROI. PwC surveyed 4,454 CEOs and 56% reported no financial benefit from AI.

Read those numbers together and the picture is stark: nearly everyone is using AI, almost nobody is getting real value from it, and the gap between “we have AI” and “AI is making us money” is enormous. The technology works. The deployment doesn’t.

In February 2026, OpenAI announced “Frontier Alliances,” multi-year partnerships with McKinsey, BCG, Accenture, and Capgemini. They embedded their Forward Deployed Engineering teams directly with the consulting firms. The framing was explicit: “The limiting factor for seeing value from AI in enterprises isn’t model intelligence — it’s how agents are built and run in their organizations.” That’s a model company telling you the model isn’t the bottleneck. The bottleneck is everything around it: integration, process redesign, governance, which is exactly what their consulting partners sell.

Anthropic made similar moves. Launched a certification program for 15,000 Deloitte professionals on Claude. Partnered with Accenture on full-scale agent deployment.

This wasn’t a response to any single event. It was a response to a year of data proving that the “ship the model and let them figure it out” approach had failed. Enterprise customers were buying tokens, running pilots, and getting stuck, over and over, across every industry. The model companies looked at that pattern and concluded: these organizations need serious help. Twelve-month engagements with systems integrators, governance workstreams, change management workstreams, deployment workstreams. Rates starting in six figures per month.

That’s one story. Here’s the other one.


## The security crisis nobody could ban away

While the model companies were watching enterprise deployments stall, something else was happening at the individual level. People weren’t waiting for their companies to figure out AI strategy. They were installing agents themselves.

OpenClaw became the fastest-growing open-source project in computing history. Over 250,000 GitHub stars in sixty days — more than Linux has accumulated since it first appeared on GitHub almost 15 years ago. Peter Steinberger built an autonomous AI agent that could access your email, calendar, Slack, file system, and browser, execute terminal commands, retain persistent memory, spawn sub-agents, and interact through WhatsApp and iMessage. It was the first personal AI agent that genuinely worked for daily tasks, not a demo, not a toy, but something that saved people hours every day.

And it was catastrophically insecure.

Microsoft published guidance calling it “untrusted code execution with persistent credentials” and recommended it run only in fully isolated environments. Cisco used it as their primary case study in agent security, calling it “an absolute nightmare.” CrowdStrike shipped a search-and-removal content pack through Falcon — the kind of coordinated response that doesn’t happen for hypothetical threats. Bitsight found over 30,000 instances sitting on the public internet, leaking API keys, chat histories, and credentials.

Koi Security audited ClawHub, the public marketplace where people share agent skills. According to their audit, twelve percent of all skills were confirmed malicious: keyloggers on Windows, credential stealers on macOS, published openly with one-click install. Token Security found 22% of enterprise customers had employees running OpenClaw without IT approval, so the malware distribution channel and the shadow IT problem were feeding each other.

The attack that should change how you think about agent security works like this. An attacker embeds a single hidden instruction inside a forwarded email. Your OpenClaw agent summarizes that email as part of a normal task, something it does fifty times a day. The hidden instruction fires. The agent forwards your credentials to an external endpoint. And it does this through a sanctioned API call, using its own OAuth tokens. Your firewall sees HTTP 200. Your EDR records a normal process. No signature fires. Nothing went wrong by any definition your existing security stack understands.

Palo Alto Networks identified what security researcher Simon Willison called a “lethal trifecta”: private data access, untrusted content exposure, and external communication capabilities, all in a single process. The attack surface is semantic, not structural, and almost nothing in the existing security stack catches it. Traditional security tooling watches what programs do. Agent attacks exploit what programs mean.

None of it slowed adoption. Because the productivity gain is too large. CISOs who tried to ban OpenClaw learned the same lesson they learned with cloud and mobile: banning the tool pushes usage onto personal devices connected to the same corporate email and Slack. You don’t eliminate the technology. You eliminate your visibility.


## What Nvidia shipped on Monday

At GTC 2026, Jensen Huang announced NemoClaw: an open-source security and privacy stack for the OpenClaw agent platform. Apache 2.0 license. Hardware-agnostic. Three enforcement layers, each targeting a specific failure mode OpenClaw demonstrated at scale.

Kernel-level sandboxing via Landlock, seccomp, and network namespaces. Deny-by-default — the inverse of OpenClaw’s allow-by-default model. Each agent gets an isolated container with configurable policy controls in YAML. It can write to /sandbox and /tmp. Everything else is blocked. The ClawHavoc malware campaign, which succeeded because malicious skills ran with the user’s full permissions, would die at the sandbox boundary.

Out-of-process policy enforcement — the architectural choice that matters most. In OpenClaw’s native model, the agent framework enforces its own permissions, which means a compromised agent can modify its own permission checks. Prompt injection attacks have done exactly this, manipulating agents into believing they have different permissions than they actually do. NemoClaw’s policy engine runs as a separate process in a separate trust boundary. Full compromise of the agent — arbitrary code execution inside the sandbox — and you still cannot touch the policies constraining you. Network endpoints, filesystem paths, process capabilities: all governed by YAML that’s version-controlled, auditable, and reproducible.

A privacy router intercepting every inference call. Sensitive tasks route to local Nemotron models on the organization’s hardware. Complex reasoning routes to cloud providers through controlled backends with defined guardrails. New outbound requests to unlisted hosts get blocked and surfaced in a terminal UI for human approval.

Huang compared OpenClaw to Linux and said every company in the world needs an OpenClaw strategy. His message: your engineering team can handle this. Here are the tools. They’re free.

These aren’t complementary strategies: Nvidia’s “empower the engineer” versus OpenAI and Anthropic’s “the engineer isn’t enough.” They’re competing theories of how hard agent deployment actually is, and the one your leadership picks shapes the next two years of your budget. But if you look at what NemoClaw ships, if you look at what the best engineering teams are actually doing to make agents work, the underlying principles aren’t new. They aren’t even close to new.


## Data dominates, and always has

Rob Pike, one of the creators of Unix and Go, wrote his five rules of programming decades ago. Rule 5 is the one I keep coming back to: “Data dominates. If you’ve chosen the right data structures and organized things well, the algorithms will almost always be self-evident.” Fred Brooks said essentially the same thing in The Mythical Man-Month in 1975. Ken Thompson condensed Pike’s rules further: “When in doubt, use brute force.” The whole philosophy fits on an index card, and it has been correct for fifty years.

When I was building ML-powered personalization at Amazon Prime Video, the principles we relied on weren’t new. The models were new. The scale was new. The organizational patterns for integrating model output into product decisions were still evolving. But the engineering bedrock — get your data structures right, measure before you optimize, use simple algorithms and smart objects — that was Pike and Brooks and Hoare, applied at scale. The teams that remembered the fundamentals shipped. The teams that chased shiny new architectures before measuring where the bottleneck actually was got stuck. Every time.

Look at what NemoClaw actually ships. Sandboxing is containerization. Out-of-process enforcement is a reverse proxy pattern. Declarative policy in YAML is infrastructure-as-code: Terraform, Kubernetes manifests, every modern deployment pipeline. The privacy router is a gateway pattern. Solved problems with decades of production history, applied to a new execution context. Recognizing that is the whole ball game.

Every hype cycle produces the same amnesia. People see new capabilities and assume the underlying engineering principles changed too. Right now I’m watching teams design elaborate multi-agent orchestration systems — three levels of coordinators, custom embedding pipelines, bespoke evaluation frameworks — when a linter config, a documented build command, and a well-organized AGENTS.md file would solve 80% of their problem. They’re optimizing for agent intelligence when the bottleneck is agent environment — buying sophistication when what they actually need is structure.

The convergence is already visible. NemoClaw’s declarative YAML policies, Factory.ai’s lint-as-architecture approach, Anthropic’s structured context summaries, Microsoft’s isolation guidance: independent teams, same patterns. That’s not a 2026 discovery. Those are the same engineering fundamentals, rediscovered by people who know their craft. The primitives converged because they were never divergent.


## Five hard problems, and only one is actually new

There are five hard problems in production agent deployment. The distribution of difficulty matters more than the list, because it tells you where to spend money and where to spend engineering time.

**Context compression.** Long-running agent sessions fill up context windows. Even million-token windows fill when an agent is working through a complex codebase over hours or days. Every compression strategy loses something; the question is what it loses and whether the agent can recover.

Factory.ai tested three production approaches. Their own method, anchored iterative summarization, maintains a structured persistent summary with explicit sections for session intent, file modifications, decisions made, and next steps. When compression triggers, only the newly truncated span gets summarized and merged with the existing summary. Structure forces preservation: dedicated sections act as a checklist the summarizer must populate, preventing the silent loss of file paths or decisions that unstructured summaries allow.

They compared this against OpenAI’s /responses/compact endpoint, which produces opaque compressed representations optimized for reconstruction fidelity (99.3% compression ratio, but you can’t read the output to verify what was preserved). And Anthropic’s built-in compression through the Claude SDK, which generates detailed structured summaries but regenerates the full summary on each compression rather than incrementally merging. That difference matters across repeated compression cycles: regenerating the whole summary each time allows drift as the same information gets re-summarized differently.

Results: Factory scored highest overall, but all three approaches struggle with artifact tracking, remembering which specific files were modified across a long session. Scores range from 2.19 to 2.45 out of 3. Factory calls this “an unsolved problem,” and the candor is notable. An independent analysis by ZenML pointed out that the variance measures are under-specified and the practical significance of the differences between approaches remains uncertain. The mitigation is architectural, not algorithmic: decompose large projects into milestones, each ending with validation. Workers get fresh context per feature. The orchestrator tracks dependencies. Engineering design problem with published patterns.

**Codebase instrumentation.** Factory.ai’s Agent Readiness framework evaluates codebases across eight technical pillars — style and validation, build systems, testing, documentation, dev environment, code quality, observability, security governance — and the consistent finding across hundreds of assessments, including work with Ernst & Young, Groq, and Bilt: the agent isn’t broken. The environment is.

Missing pre-commit hooks mean ten-minute feedback loops instead of five-second ones. The agent writes code, submits it, waits for CI to fail, reads the error, tries again, burning tokens and time on a problem a hook catches in seconds. Undocumented environment variables mean the agent guesses, fails, guesses again. Build processes that require Slack archaeology (”ask Dave how to run the integration tests”) mean the agent can’t verify its own work.

Most enterprise repos score a 2 out of 5 on Factory’s readiness scale, and the fix takes days, not months. This isn’t even an agent problem; it’s software hygiene that existed before agents and will exist after. If you’re an engineer, this is the single most valuable thing you can do right now. The person who makes the codebase agent-ready is the person who made agents work. You don’t need permission, and you don’t need outside help.

**Linting as architecture enforcement.** Alvin Sng’s research on linting is, I think, the most underrated piece of agent-infrastructure thinking published this year. His core argument: lint rules aren’t style preferences. They’re the executable specification agents use to self-correct without human intervention.

Ban default exports, enforce named imports, and agents can locate definitions and usages without ambiguity. Enforce deterministic file placement, and agents can predict where code lives. Require colocated tests, and agents verify their own work in seconds. The flow is clean: humans define standards in AGENTS.md (the “why” and the examples), encode those standards as lint rules (the “how” and the guarantee), and “lint green” becomes the proxy for “conforms to architecture and best practices.” Agents self-correct against lint output the way you self-correct against compiler errors. Engineering work your team owns, producing compound returns that accumulate with every agent session.

**Multi-agent coordination.** Factory’s Missions framework illuminates the fundamental tension: narrow worker scope keeps agents focused but increases coordination overhead and token cost. Broad scope maintains continuity but stretches each agent thinner. The numbers are concrete. Single-agent sessions fire about six messages per minute. Multi-agent missions drop to three per minute, but each message carries nearly double the token weight, about 19,000 tokens versus 11,000. The lower rate reflects what missions actually spend time on: running builds, executing test suites, linting, type-checking, browsing the application under test. Most wall-clock time is waiting on real-world execution, not generating tokens.

Orchestration depth: one layer of management handles most projects. Two layers help for larger codebases. Three starts to feel like bureaucracy, and Factory is honest about this; they’re still iterating. Missions also use different models for different roles: orchestrator, workers, validators, research agents each get the model best suited to their job. The principle is the same one that applies everywhere else: measure before you optimize coordination granularity. Don’t design a three-tier hierarchy before you’ve tested whether a single agent with good lint feedback can handle your task.

**The specification problem.** This is where it gets genuinely hard in a way that is actually new.

Traditional security defines what deterministic code can do. Agent security requires defining what a probabilistic system should do, drawing boundaries for behavior that is sometimes wrong, not deterministically malicious.

NemoClaw can sandbox an agent. It can restrict its network access. But if the agent has email access, because its job requires reading email, the sandbox doesn’t prevent it from misusing that access. Permission fatigue is real and well-documented: creating tight permission scopes is tedious, teams get lazy, and over time scopes expand to include everything the agent “might need.” The specification problem isn’t a one-time configuration exercise. It’s an ongoing governance practice.

In standard software development, your team can manage this. You know the codebase, the workflows, the acceptable failure modes. You can write the YAML policies. But in regulated domains — financial services, healthcare, insurance, legal — the specification problem compounds dramatically. The rules the agent must follow are external to the codebase, complex, jurisdiction-specific, and constantly changing. The consequences of getting them wrong include regulatory penalties, litigation, and loss of licenses. An engineer who’s excellent at Kubernetes doesn’t know how insurance claim adjudication works in three states, or how HIPAA’s minimum necessary standard applies to an agent accessing patient records, or which SOX controls need to extend to agent-generated financial reports.

This is where domain expertise is irreducible. Not because the tooling is hard. Because the rules are hard.

Count the distribution. Four engineering problems solvable with published patterns and open-source tooling. One domain expertise problem where you probably need specialized help. 4:1. That ratio is what the consulting narrative obscures when it frames the entire agent deployment challenge as unprecedented organizational transformation.


## The build-or-buy framework

Three variables. Score each honestly. The combination is your answer.

**Codebase readiness.** Can an agent get fast, reliable feedback without tribal knowledge? Factory.ai’s eight-pillar framework gives you the rigorous assessment, but the proxy question is simpler: could a competent contractor clone your repo and ship a bug fix on day one without asking a human how to run the tests? If not, fix that first. Before NemoClaw. Before Accenture. Before anything.

**Organizational readiness.** Not “is your team smart” but whether your organization has structures to absorb a new category of non-human worker. VP-level AI ownership. A security team that’s constructive rather than adversarial. Existing data governance that can extend to agent access. Prior experience with technology-driven process change: cloud migration, DevOps adoption, anything where the org changed how it works, not just what tools it uses. The organizations that adopted cloud well tend to adopt agents well. The ones that fought shadow IT for a decade and lost will fight shadow agents and lose again.

**Domain complexity.** How specialized is the knowledge the deployment requires? Standard web dev is low. Insurance claims across three regulatory jurisdictions is high. The question isn’t technology complexity; NemoClaw handles that uniformly. It’s the complexity of the rules the agent follows and the consequences when it’s wrong.

High codebase readiness + high org readiness + low domain complexity means your engineers handle this. Write YAML policies. Stand up sandboxes. Nvidia built these tools for your team. Weeks, not quarters.

High codebase readiness + low org readiness + any domain means you get help with the organizational layer only. Not the technology layer. Pay consultants to design governance frameworks, build executive buy-in, create the change management plan that makes agents stick past the pilot. Don’t pay them to install open-source software. Governance consulting at $300/hour is a reasonable investment when your organization lacks the structures. Technology implementation consulting for a free, well-documented stack is waste.

Low codebase readiness + anything means you fix the codebase first. The most common and most expensive mistake I see in my advisory work. Teams reach for agent platforms when their codebase can’t support agent workflows. No framework, no consulting engagement overcomes a codebase that can’t give agents fast feedback. Linters, documented builds, pre-commit hooks, dev containers, an AGENTS.md file. Your team. Days of work.

Any readiness + high domain complexity means you get domain-specific help. This is where Nvidia’s “empower the engineer” thesis genuinely breaks down, because the knowledge the engineer needs isn’t engineering knowledge. McKinsey, Deloitte, and Accenture have armies of people who understand insurance adjudication, healthcare compliance, and financial regulation. Your engineers don’t, and building that expertise in-house takes years you don’t have.

The trap is hiring consultants for the commodity engineering layer when it’s free and well-documented, while underinvesting in the domain expertise that actually requires human judgment. You don’t need a Big Four engagement to install NemoClaw. You might need one if your agent adjudicates healthcare claims and you’ve never built a compliance monitoring framework. Know the difference.


## Where NemoClaw falls short

NemoClaw is early alpha. No published benchmarks on latency or throughput impact from the interception layer. No independent security audits of the OpenShell runtime. The codebase hasn’t been battle-tested by the community. If you’re deploying agents in production with SOC 2 or HIPAA requirements today, NemoClaw is the right architecture but the wrong maturity level, worth watching and contributing to, not yet worth staking your compliance on.

The privacy router’s full value requires local inference, which works best on Nvidia GPUs. On AMD or Apple Silicon, you lose local model capability, and sensitive inference still routes to cloud providers. That’s a meaningful gap for organizations choosing NemoClaw specifically for data sovereignty, and it conveniently aligns with Nvidia’s hardware business, which is worth noting without being cynical about. The incentives are transparent.

Sandboxing limits blast radius but doesn’t prevent authorized misuse. An agent with email access can still delete your emails inside the sandbox. Permission fatigue is real; scopes expand over time as operators widen access to cover edge cases. NemoClaw provides the enforcement layer but not the judgment layer above it.

And the gap NemoClaw doesn’t address at all: observability. Knowing what agents are actually doing across thousands of parallel sessions. Whether outputs are correct. Whether behavior is drifting. Whether the agent that was working well last week is still working well after a model update changed its reasoning patterns. Security tells you the agent can’t break out of its sandbox. Observability tells you whether the agent is doing good work inside the sandbox. They’re different problems, and only the first one is solved.

If Nvidia’s trajectory holds — chips to inference runtime to agent security to what comes next — agent observability is the logical next layer. First NemoClaw, then NemoWatch. Remember where you read it.


## Why nobody is saying this

The media ecosystem is optimized for novelty. “Everything is changing every week” generates engagement, subscriptions, and conference revenue. “The fundamentals haven’t changed” does not. The quiet reality that NemoClaw, Factory’s Missions, Anthropic’s team swarms, and StrongDM’s Software Factory independently implement the same coordinator/worker/validator pattern is not a story the attention economy rewards.

The second reason is commercially uncomfortable, so I’ll say it plainly: the perception of chaos is worth billions to the consulting industry. Accenture reported $2.2 billion in advanced AI bookings in a single quarter, up 76% year over year. AI revenue of $1.1 billion, up 120%. 85,000 AI and data professionals on staff. Bloomberg reported this week that Accenture expects AI partner work to more than double in the coming year. The deployment gap is real. But the firms have a structural incentive to present the entire gap as requiring their help, to emphasize organizational transformation while de-emphasizing the parts that are standard engineering with published solutions.

Here’s the pattern I’ve seen in my advisory work across dozens of companies since Amazon: the instinct to hire experts for the whole problem instead of decomposing it. To treat “agent deployment” as one category of difficulty rather than separating the commodity engineering from the genuinely novel domain challenges. The teams that decompose correctly — build the engineering layer themselves, buy expertise only for the irreducible domain layer — ship faster and spend less.


## The SaaS collapse nobody’s pricing correctly

Huang made a claim at GTC that reframes the entire software industry. He said every SaaS company will become an Agent-as-a-Service company, a “token manufacturer.” The current SaaS model, per-seat licensing with human users operating software interfaces, collapses into per-token consumption where the value isn’t the interface but the agent running behind it. The dashboard you pay $50 per user per month for doesn’t go away, but the human operating it might be replaced by an agent consuming $5 in tokens to do the same work in a tenth of the time.

Investors are already pricing this in. Salesforce, Workday, Microsoft, and ServiceNow have all seen share pressure on concerns that enterprises will choose OpenAI’s and Anthropic’s agent platforms over theirs. Fortune reported that these SaaS vendors depend on the same consulting firms that are now signing deals with OpenAI and Anthropic, which means the distribution channel for legacy SaaS is being co-opted by the platforms that may replace it. The consulting firms don’t care which software they deploy. They care about billable hours. And if the billable hours migrate from deploying Salesforce to deploying Frontier agents that replace Salesforce, the consultants follow the money.

If Huang is right, the near-term winners aren’t the model companies or the legacy SaaS vendors. They’re whoever captures the integration layer, the work of connecting agent platforms to enterprise-specific workflows, data, and compliance requirements. OpenAI and Anthropic bet that layer belongs to consulting firms. Nvidia bet it’s thin enough for engineering teams to build themselves. The teams that correctly identify which layers are commodity and which are genuinely specialized in their context will build advantages that compound for years.


## What to do with this

If someone in your organization is evaluating a consulting partnership right now, the single most useful thing you can do is push them to be specific about what they’re buying. “Help you set up agent infrastructure” is $500-an-hour work for a free software stack your team could learn in a week. “Redesign your underwriting workflow to be agent-native and build the compliance monitoring framework” is domain expertise you genuinely don’t have. Make them say which one they’re selling. That question alone will save you more than this subscription costs.

Clone the NemoClaw repo and write the YAML policies yourself. The experience of defining what an agent should and shouldn’t access will teach you more about your own systems than any consultant’s discovery phase. You’ll discover which services have clean boundaries and which ones are held together by tribal knowledge and good intentions.

The gap between what the industry tells you is impossible and what you can actually do yourself is the opportunity of your career — if you see it clearly.

Now you do.

[![](https://substackcdn.com/image/fetch/$s_!Qctm!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd7acf4bf-ae9c-4a7d-a545-216f76f059cf_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!Qctm!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd7acf4bf-ae9c-4a7d-a545-216f76f059cf_1024x1024.png)
