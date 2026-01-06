---
title: "Three Conflicting Visions of Agents Came Out This Week: Here’s What’s Real"
author: "Nate Jones"
published: 2025-11-17
url: https://natesnewsletter.substack.com/p/i-summarized-3-ai-agent-papers-60
audience: everyone
scraped_at: 2026-01-05 19:11:41
---

It went largely under the radar last week, but Google and Vercel just published competing versions of our AI agent future—and both came out within 24 hours of Anthropic admitting an agentic orchestration platform was used to make Claude into a super-hacker.

TLDR nobody can agree on what AI agents are for, and meanwhile they clearly are powerful because bad guys are using them to attack high value targets yesterday.

My goal with this post is simple: cut through the BS and get you an actionable summary on where we stand on AI agents, why they matter even more these days, and what you can actually build now in the AI agent department.

That means cutting through more than 60 pages of documentation across three different papers to get to the real story.

You’ll get:

- Why we need Google’s vision for the agentic future now, post Claude Code-hack
- Why Google is also wrong about AI agents in ways we need to build usefully now
- What Vercel is seeing that we aren’t publishing or talking about enough
- Which companies are building AI agents that reduce toil (not just automate)
- Why it matters to build AI agents that get your best people CLOSER to the work
- How to target and prioritize workflows that are AI agent-susceptible
- How Google is thinking about agents and the evolving challenges of security
- Hours back—the Google doc alone is over 50 pages!

Plus, of course a custom prompt to help figure out AI agent opportunities for you. I’ve written the prompt so it gives you three different angles of conversation: 1) a chance to explore smart opportunities for AI agents at work, 2) a chance to identify your best hands-on contribution in an era of agents, and 3) an opportunity to think about how to design the correct security stance for agents at work.

Sounds like a lot, but this prompt is powered up with the whole article as context, so it can take you any direction you want to go!

With that, let’s figure out the real story on one of the biggest agent battles out there right now…


## [Get the AI Agent Strategy Prompt](https://www.notion.so/product-templates/AI-Agent-Strategy-Prompt-2ae5a2ccb52680f9bb14d475933fd7c0?source=copy_link)

I wrote this prompt to give you room to have a wide-ranging conversation about AI agents. Have a conversation about your personal career—how you can feel more in touch with work you find meaningful. Or dive in on the security side with agents, or pick a spot where agents can add value intelligently. It’s up to you! This prompt is set up with all the context you need to have a conversation about AI agents that’s informative, useful, and clarifying.

---


# **Three Conflicting Visions of Agents Came Out This Week: Here’s What’s Real**

Three dramatically different documents about AI agents emerged this week. Google’s 50-page “Introduction to Agents” whitepaper has been widely shared but rarely read in full—understandable, given the density of non-obvious insights buried in it. Vercel’s “What we learned building agents” takes a shorter, intensely practical approach focused on field applications. Anthropic’s report on the agentic hack using Claude Code documents a state-linked actor’s successful automation of a cyber operation.

These documents share a common subject but represent fundamentally different visions for how AI agents should evolve and where organizations should focus. More importantly, they reveal exactly where to build today and what structural shifts to prepare for.


## Google: The Orchestration-First Agent City

Google’s whitepaper presents an idealistic, comprehensive vision for AI agents that few companies are positioned to implement in 2025. The timing of its publication—immediately following the Claude Code hack news—gives it an inadvertently prophetic quality. The hack’s central lesson is that model-layer security alone cannot be trusted. Security and governance must move to the orchestration layer. Google’s whitepaper is essentially a 50-page argument for exactly that thesis. If you get serious about agents, you will need to solve the orchestration problem at scale. They’re correct about this.

The difficulty lies in execution. Most organizations currently achieving ROI from agents are pursuing much simpler approaches—which is where Vercel’s work becomes relevant.

Google’s whitepaper contains immediately applicable insights despite its future-oriented framing.


### Agents as Loops: The Five-Step Process

Google decomposes an agent’s operational loop into five fundamental steps that function as the heartbeat of any agentic system.

An agent receives a specific, high-level goal from a user or automated trigger. It gathers context by accessing available resources—user requests, memory, tools, calendars, databases, APIs. The agent’s core reasoning loop analyzes the mission against available context and devises a plan, typically through chain-of-reasoning. The orchestration layer executes the first concrete step by invoking the appropriate tool. The agent observes the outcome, incorporates it into context or memory, and returns to reasoning.

This cycle continues until mission completion. The agent iterates through thinking, acting, and observing rather than executing a single pass.

Google illustrates this with a straightforward example. A user asks “Where is my order #12345?” Rather than immediately executing a tool call, the agent enters its reasoning phase and constructs a complete strategy. To provide a comprehensive answer, it determines it needs a multi-step plan: locate the order in the database, extract the shipping carrier’s tracking number and query their API, then synthesize the information into a coherent response.

Execution proceeds accordingly. The agent calls find\_order(”12345”), observes the result (retrieving tracking number “ZYX987”), then calls get\_shipping\_status(”ZYX987”), observes the result (”Out for Delivery”), and generates the final response: “Your order #12345 is ‘Out for Delivery’!”

This framework clarifies that an agent’s primary function is context window curation. The model serves as a reasoning engine—essentially a brain in a jar. The orchestration platform surrounding it determines what information that brain perceives, which tools it can invoke, what data it accesses, how long plans can run, when to terminate, when to escalate, and when to request human intervention.


### The Five Levels of Agentic Capability

Google classifies agentic systems into five levels of increasing complexity, providing a useful framework for scoping development work.

Level 0 represents the core reasoning system operating in isolation without tools, memory, or interaction with the live environment. It can explain concepts and plan solutions but remains functionally blind to real-world events.

Level 1 adds external tool connections, transforming the reasoning engine into a functional problem-solver. It can now answer “What was the Yankees score last night?” by invoking a Google Search API, observing the result, and synthesizing an answer.

Level 2 requires sophisticated context engineering to handle complex, multi-part goals through active selection and management of relevant information. Google’s example: answering “Find a good coffee shop halfway between my office in Mountain View and my client’s office in San Francisco” requires calculating the halfway point, searching for highly-rated coffee shops in that location, and synthesizing results.

Level 3 replaces a single generalist agent with a team of specialists. A “Project Manager” agent delegates to specialized agents for market research, marketing, and web development. This architecture mirrors human organizational structures and enables genuine division of labor.

Level 4 systems can identify gaps in their own capabilities and dynamically create new tools or agents to address them. If the system recognizes a need to monitor social media sentiment but lacks the appropriate tool, it invokes an AgentCreator tool to construct a SentimentAnalysisAgent on demand.

Most current enterprise implementations occupy Levels 1 and 2. Levels 3 and 4 represent both the most interesting applications and the most substantial technical challenges.


### Why There Is No God Agent

One of the whitepaper’s most important insights concerns architectural limits. In Google’s model, no single all-knowing agent can exist. A universal agent would require excessive context and inevitably fail under load.

Work must distribute across many small loops and human decision points. The future of agents is necessarily decentralized. Each agent operates within a specific domain, with defined tools, data access, and memory. Communication occurs through well-defined interfaces, such as Google’s Agent2Agent protocol.

This has profound architectural implications. Effective systems do not rely on one massive prompt containing every possible instruction. It simply does not work well. Instead, they employ teams of focused agents, each excellent at a specific task, orchestrated together through clear interfaces.


### Security: Agents as First-Class Identities

The Claude Code hack sharpens the urgency of Google’s security framework. Agents must be treated as first-class identities within IAM systems—not as scripts or service accounts, but as semi-autonomous employees with assigned roles, budgets, personas, and policies within role-based access control systems.

Without this approach, no meaningful security perimeter exists. A malicious actor need not jailbreak the model if they can orchestrate it through a series of individually innocent-looking steps. The orchestration layer becomes the enforcement point for policy: “This agent can access the CRM but is explicitly denied access to financial records.”

The whitepaper details implementation approaches using standards like SPIFFE for cryptographically verifiable agent identities, deterministic guardrails in tool logic, and optional services like Model Armor for screening prompts and responses for threats.


### The Control Plane Vision

Google emphasizes control planes—centralized management interfaces that become genuinely necessary when managing hundreds of agents at scale. While these systems may see less frequent use than their sales appeal suggests, the strategic reasoning is sound. Organizations running extensive agent deployments will need this infrastructure.

The proposed architecture includes a central gateway serving as a mandatory entry point for all agentic traffic: user-to-agent prompts, agent-to-tool calls (via MCP), agent-to-agent collaborations (via A2A), and direct inference requests. This gateway handles authentication, authorization, policy enforcement, and provides unified observability through common logs, metrics, and traces for every transaction.

Paired with a central registry—essentially an enterprise app store for agents and tools—this infrastructure transforms chaotic proliferation into a managed, secure, efficient ecosystem.

This represents the trajectory of mature agent deployments, though not the current state of most organizational implementations.


## Vercel: The Back-Office Agent That Actually Ships

Vercel’s approach could not be more different, and that’s why I want to call it out here. Vercel focuses on achieving ROI in the immediate term rather than designing comprehensive agent architectures. Their methodology is straightforward.

They engage directly with people performing the work to identify tasks that are completely verifiable, obviously step-by-step, and constitute pure toil. They build agents to eliminate that suffering.

Their initial deployments targeted ticket triage and similar back-office flows where inputs and outputs are clear, correctness is easy to verify, and the work drains morale. The agents don’t replace people. They weave around people. The agent handles the tedious, repetitive work. Humans focus on higher-value tasks requiring long-term context and judgment.


### The Sweet Spot: Low Cognitive Load, High Repetition

Regardless of what Google writes, current-generation agentic AI achieves the highest likelihood of success with work requiring low cognitive load and high repetition from humans. These tasks prove too dynamic for traditional automation—simple scripts won’t suffice—but remain predictable enough for AI to handle reliably. They appear across businesses in data entry, research, qualification, and triage, where automation saves time and maintains quality consistency.

This represents accessible value today while models continue maturing toward reliably automating more complex tasks.


### Two Real Examples That Worked

Vercel’s lead processing team previously consisted of 10 people triaging website leads. When asked what work they wished to never repeat, the team’s top performer identified manual research required for initial qualification judgments as mind-numbing.

Vercel shadowed that employee to understand the process, then built an agent to automate initial qualification. One person now handles the work of 10. The remaining nine employees focus on higher-value, more complex sales work.

The workflow executes deep research on leads and their companies, uses generateObject to categorize them, automatically generates personalized follow-up emails, sends everything to Slack for human approval, catches Slack webhook events upon approval, and sends the emails.

Vercel’s security team manages steady abuse report flows—phishing, spam, copyright violations. They take each case seriously. False positives lead to wrongful takedowns. Misses risk leaving harmful content online. Before automation, human reviewers investigated every report manually through a formulaic process.

They built an abuse platform agent that automatically processes potentially infringing or high-risk URLs, runs visual analysis, determines page intention, and returns recommended actions for human validation.

The first iteration achieved a 59% reduction in time to ticket closing, freeing the team to focus on edge cases requiring complex human reasoning.

The workflow retrieves new reports from the abuse queue, runs visual and textual analysis to detect phishing or copyright content, compiles findings and proposes action plans, sends recommendations to security engineers for final judgment, then records decisions and closes tickets.


### Vercel’s Implicit “Build It Now” Filter

Vercel’s methodology yields a clear decision framework.

The work must be verifiable. Checking whether the agent performed correctly requires no heroics.

The workflow must be step-wise and bounded. Think “five clicks and completion,” not “develop a product strategy.”

The task must be recurring and painful. People describe it as toil or suffering, not as valued work.

Inputs and outputs must be known. You understand exactly what enters the system and what constitutes good output.

A human must remain in the loop. The agent prepares work. A person approves, edits, or rejects it.

This filter produces a specific answer to “where to build agents right now”: back-office flows, operational support, the tedious work nobody chose to do.

Vercel has not implemented Google’s full orchestration platform. Almost nobody has. Their work demonstrates that building agents today means solving problems that reduce toil, solving problems that are verifiable, solving problems where inputs and outputs are known—and pursuing them relentlessly. The value is accessible.

They shared what worked rather than publishing visionary frameworks.


## Anthropic: Claude Code as the Orchestration Wake-Up Call

Anthropic’s report on the Claude Code hack documents a state-linked actor using an agentic system built on Claude to automate a serious cyber operation.

The lesson is direct. Model-level safety cannot be the sole defense. If the orchestration layer lacks sophistication, the model will assist in breaking systems one individually innocent step at a time.

A malicious actor needs no jailbreak if they can construct an orchestration system that decomposes harmful tasks into benign-looking components. “Search for information about this security vulnerability”—acceptable. “Write code to test if this vulnerability exists”—acceptable. “Execute this test code”—acceptable. String enough such steps together with appropriate orchestration, and you’ve automated a cyber operation without triggering the model’s safety guardrails.

In this context, Google’s whitepaper suddenly appears prescient. It constitutes essentially a 50-page argument that security and governance must reside in the orchestration platform. The model cannot police itself. The orchestration layer must enforce policy: which tools this agent accesses, what data it sees, which actions require human approval, what budget constraints apply.

The Claude Code hack demonstrates this isn’t theoretical. It’s occurring now. Orchestration is no longer optional—it’s the security perimeter.


## How to Sequence Your Agent Strategy

While at odds today, these three perspectives do integrate into a practical path forward over a longer time horizon.

Step One: Mine Your Back Office. Identify five-click suffering. Ask what work is easy to verify but annoying to execute. Build agents there first. Start with work that’s verifiable, bounded, recurring, and universally disliked.

Step Two: Wrap Those Agents in Lightweight Orchestration. Even simple controls matter. Assign each agent an identity. Define explicit tools and data access. Add logging. Require human approval for consequential actions. Full control planes aren’t necessary to start. What’s necessary is treating agents as more than scripts.

Step Three: Use Those Wins to Justify Deeper Orchestration Work. Once value is proven on simple, clean problems, adopting more of Google’s blueprint becomes sensible: agent operations (tracking runs, costs, traces), shared registries (internal agent and tool catalogs), complex multi-agent patterns, control planes for managing hundreds of agents.

Step Four: Keep Claude Code as a Reference Point. When someone proposes an “autonomous agent” with system access and unclear guardrails, remember that if you don’t build the orchestration layer, someone hostile will—from outside your network. Security cannot be retrofitted.


## Cutting Through the Noise: A Simple Rule for 2025

Three questions clarify any new agent use case.

Is this work verifiable and bounded? If checking the result proves difficult, it’s probably not a first-wave agent application.

Is this work recurring toil? If people don’t actively dislike it, or if it occurs infrequently, an agent is probably the wrong solution.

Do I know what orchestration guardrails belong around it? If you cannot answer “What tools? What data? What budget? What escalation path?”, you’re not ready to deploy this as an agent.

Three “yes” answers place it in the Vercel category: build it now, maintain human oversight, develop organizational capability.

Any “no” answer places it in the Google category: potentially valuable later as part of a comprehensive agent architecture, but not something to pretend can be safely automated today.


## Where This Leaves Us

Google’s whitepaper maps the agent architecture we’re building toward. Their thinking on orchestration-first design, agent identity, multi-agent systems, and control planes describes infrastructure most organizations will eventually need.

Vercel’s case studies provide a field guide to deployments producing ROI today. Back-office operations, verifiable workflows, human-in-the-loop patterns—this is where capability develops and where lessons accumulate.

Anthropic’s Claude Code report confirms that orchestration is mandatory, not optional. It’s the security perimeter. Model-level safety is necessary but insufficient. The orchestration layer enforces policy and prevents misuse.

The path forward is clear. Build agents where work is verifiable, bounded, and universally disliked. Maintain human oversight. Treat orchestration—and agent identity—as first-class architectural concerns from day one, even if implementation starts lightweight.

That’s how to progress from today’s practical wins to tomorrow’s comprehensive agent deployments. Steps cannot be skipped. Orchestration platforms shouldn’t be built before agents exist to orchestrate. But agents cannot scale without building the orchestration platform.

Both perspectives matter. The vision and the practical path. Google shows the destination. Vercel shows the starting point. Claude Code shows why security cannot be compromised.

---

Looking for more?

[Read Google’s whitepaper](https://drive.google.com/file/d/1C-HvqgxM7dj4G2kCQLnuMXi1fTpXRdpx/view)

[Read Vercel’s field report](https://vercel.com/blog/what-we-learned-building-agents-at-vercel)

[Read Claude’s post-hack breakdown](https://www.anthropic.com/news/disrupting-AI-espionage)

[Dive further with the Perplexity](https://www.perplexity.ai/search/can-you-please-construct-a-rep-OPCqK5eoQ5af6llV8SS5CA#0)

[![](https://substackcdn.com/image/fetch/$s_!sAjw!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F088c0b19-e9e1-4715-a466-ce00e55dc467_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!sAjw!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F088c0b19-e9e1-4715-a466-ce00e55dc467_1024x1024.png)
