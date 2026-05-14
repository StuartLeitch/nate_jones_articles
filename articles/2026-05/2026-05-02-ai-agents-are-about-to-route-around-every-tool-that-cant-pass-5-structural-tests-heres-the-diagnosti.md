---
title: "AI agents are about to route around every tool that can't pass 5 structural tests. Here's the diagnostic."
author: "Nate Jones"
published: 2026-05-02
url: https://natesnewsletter.substack.com/p/issue-trackers-agent-infrastructure
subtitle: "Watch now | Karri Saarinen, the CEO of Linear, declared issue tracking dead in March."
audience: everyone
scraped_at: 2026-05-14 14:32:41
---

Karri Saarinen, the CEO of Linear, declared issue tracking dead in March. His argument was reasonable. Issue trackers were built for a world where coordination between humans was the bottleneck, and when agents can interpret context directly, that translation step is friction. It was a clean thesis from a designer who had spent his career making the category better.

Then OpenAI open-sourced Symphony, and Linear became the literal control plane for the most ambitious autonomous-coding system ever shipped. Some internal teams saw a 500% increase in landed pull requests. The thing Saarinen had just eulogized was now the substrate that made all of it work.

He was right about the user experience and wrong about the infrastructure. The translation step is going away. The state machine, the assignee field, the audit history, the dependency graph, those are staying. They are quietly becoming the most strategic infrastructure in the enterprise software stack, and that repricing extends to every boring tool you own.

**Here’s what’s inside:**

- **The five properties that make a tool agent infrastructure.** Why Symphony looks obvious in retrospect, and a diagnostic you can run on every system in your stack.
- **Why your UX choice was actually a data choice.** How Linear’s design discipline accidentally produced the cleanest agent substrate on the market, and what that means for tool selection from here.
- **The Atlassian repricing.** The MCP server, the Anthropic partnership, the acquisition rumor, and why the market is treating Jira’s installed base as a strategic AI asset.
- **Which of your tools are next.** CRMs, ERPs, service desks, calendars, spreadsheets: five yes-or-no questions that tell you which ones become agent infrastructure and which ones get wrapped.
- **What to do about it.** Three prompts that score your stack, spec out an MCP server for anything you build, and produce the migration brief your leadership team is missing.

It started with a bug tracker in 1998. The accident is the whole story.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260428_cx5_promptkit_1)

These prompts exist because the five-question diagnostic in this article is only useful if you actually run it. The substrate audit forces you to score every tool in your stack against the five properties and confronts you with where your real work state lives. The MCP server spec turns “make this agent-ready” into a one-page engineering artifact. The migration diagnostic interviews you about your specific patchwork of systems and produces the leadership brief most organizations are missing. If you can’t fill in the blanks, you’re looking at the swamp tax this article describes. That is the starting point.


## Where issue trackers came from

The genre starts with Bugzilla in 1998. Terry Weissman wrote it for Mozilla to replace the in-house defect tracker Netscape had been using. It was originally Tcl, later rewritten in Perl with MySQL underneath. The first public deployment hit a Mozilla server on April 6, 1998. The Bugzilla team’s stated discipline, written down on the project’s own about page and remarkable in its narrowness, was: “Bugzilla’s developers have chosen to focus on the task of designing a system to track software defects. While the potential exists in the code to turn Bugzilla into a technical support ticket system, task management tool, or project management tool,” they deliberately chose not to. The scope stayed narrow, and the structural shape that came out of that narrowness is the template every issue tracker since has copied.

What Bugzilla encoded, almost as a side effect of taking software defects seriously, was a small set of structural primitives.

It encoded **persistent state outside any single person’s memory**. A bug existed in a database row, not in someone’s inbox. The state of the bug was visible to everyone with permissions, and it survived people leaving the team, going on vacation, or forgetting they had ever filed it.

It encoded a **state machine with well-defined transitions**. NEW. ASSIGNED. RESOLVED. VERIFIED. CLOSED. Plus the famously cynical WONTFIX, one of the most emotionally honest software states ever invented. These were not labels. They were positions in a graph, and only certain transitions were legal. The state of a bug was both human-readable and machine-readable in the same moment.

It encoded **ownership**. The assignee field made it unambiguous whose turn it was. When the assignee changed, the audit history captured who reassigned the bug and when. Responsibility was a first-class property of the data model, not a social convention.

It encoded **defined verbs**. Create. Comment. Assign. Resolve. Reopen. Mark duplicate. Block on another bug. Each verb had clear semantics, clear preconditions, and a clear effect on state. You could not “sort of” resolve a bug in Bugzilla.

It encoded **dependencies as first-class objects**. Bug A blocks Bug B. Bug C depends on Bug D. The graph was queryable. You could ask, in 1998, what work needs to happen before the next release ships.

And it encoded **audit history by default**. Every change to a bug was logged with timestamp and actor. Twenty years of work on a single bug in Mozilla still survives, replayable, in the system.

None of this was designed for AI. There was no AI. Weissman was solving a coordination problem for a few hundred Mozilla developers spread around the world, working asynchronously, through dial-up. The constraints he was responding to were human constraints: limited memory, time-zone friction, hand-off ambiguity, accountability gaps. The structural choices that fell out of those constraints happen to be exactly the choices you’d make if you were designing a substrate for autonomous agents to coordinate work through. That accident is the whole story.


## How the genre evolved: Bugzilla, Jira, Linear

Bugzilla escaped Mozilla and became the de facto open-source bug tracker for a generation of projects. Atlassian’s Jira shipped in 2002, took the same structural model, and added the things enterprises needed: workflows configurable by administrators, custom fields, project hierarchy, role-based permissions, integration with everything. Jira became universal in part because it was infinitely flexible. Each company could shape Jira to its specific organizational structure, which was both Jira’s commercial advantage and the source of its terrible reputation. The thing every developer hated about Jira was that no two Jira deployments looked the same. Every company had configured it into its own particular maze.

Linear arrived in 2019 with the opposite philosophy. Saarinen, then a principal designer at Airbnb, was tired of how bad project-management tools were and tired of how Jira specifically had become a tax on engineering teams. He started Linear with two co-founders and built it around a single opinionated model: issues live inside cycles, cycles ladder up to projects, and the customization surface is deliberately narrow. You don’t configure Linear to match your org chart. You change your workflow to match Linear, and you accept that this is part of the deal.

I’ve spent real time inside both Linear and Jira. The speed difference alone explains most of the switching, but the narrower opinion about how work should flow is what makes people stay.

The interesting thing about Linear, in retrospect, is that the data model is the same data model Bugzilla shipped in 1998. Issue. State. Assignee. Priority. History. Dependencies. The verbs are the same. Linear’s contribution was speed, design discipline, and an opinionated point of view about what good engineering coordination looks like. The substrate underneath was unchanged. Linear didn’t reinvent the issue tracker. It made the issue tracker pleasant enough that people stopped fighting it, which had the effect of letting the underlying data become much cleaner. Because when people don’t fight a tool, they use it consistently, and consistent use produces consistent state.

This is the part that counterintuitively matters for agents: good UX produces cleaner data. When people resent a tool, they route around it. Important decisions end up in Slack instead of the tracker. Statuses become performative rather than accurate. Tickets get created retroactively, after the work is already done, to satisfy a process nobody believes in. When people actually like the tool, the real work migrates into the system voluntarily. The state gets cleaner. The ownership stays current. The dependencies reflect reality instead of fiction.

Linear was a UX win, and the UX win was a data win, and the data win turned out to matter more than anyone could have known in 2019. The implication is counterintuitive: the tool that will serve your agents best might not be the one with the flashiest AI features. It might be the one your team has been filling in honestly for three years because the experience never made them want to cheat. Good human UX, it turns out, is still doing load-bearing work in 2026.

Saarinen’s bet, articulated explicitly in his interviews from 2024 and 2025, was that “engineering is really the front line of all this information.” That phrasing reads differently now than it did then. He was saying that engineers’ work was where the real organizational state lived, and that putting good tools in their hands meant the rest of the organization would inherit cleaner state for free. He was right, but the implication he didn’t quite name in 2024 is that “the rest of the organization” includes a population of agents that didn’t exist yet.


## Why the substrate fits agents

The reason Symphony works, the reason some OpenAI teams reportedly got 500% more landed pull requests by routing autonomous Codex agents through Linear tickets, is that an issue tracker is the thing an agent system would have built for itself if it were starting from scratch.

An agent loop needs a place to put state that survives between runs. The context window doesn’t qualify. It gets reset, summarized, drifted, lost. A ticket in a database is durable, queryable, and structured. The agent reads its ticket at the start of a run and writes back to it at the end. The next run picks up where the last one left off because the state lived outside the agent. That sounds boring. It is one of the biggest differences between a demo and a working agentic system.

Handoff semantics are the second requirement. Who owns this work right now? Is it the agent, or is it back to a human? Is it blocked by another task? Is it ready for review? In a good tracker, these are not vibes. They are fields. The assignee field answers that question. The status field encodes the next legal transition. The state machine is the protocol. That is exactly what Symphony is exploiting. The board is a state machine, not a visual planning surface.

Parallel agents also need a coordination layer that prevents contention. Cursor’s “Scaling long-running autonomous coding” post from January documents what happens when you don’t have one: agents hold locks, throttle each other, become risk-averse, and refuse to take on hard problems. They pick small safe tasks instead of hard end-to-end work. Flat orgs of agents, it turns out, have a coordination problem. And issue trackers are coordination tools. A ticket board solves the coordination problem the way it has always solved it for humans: tickets are claimed, worked, and released, and the contention surface is small because tickets are coarse-grained units.

An agent loop needs audit history that humans can review when something goes wrong. IDC research from 2025 found that 88% of AI pilots never reach production at all, and the failure mode in many of those cases is investigability. The agent did something wrong and nobody could reconstruct the chain: what it saw, what it decided, what it changed, who approved the change, what state the work was in before and after. Issue trackers logged every change for thirty years, because thirty years ago we already knew that humans coordinating asynchronously needed audit trails to function. That same history is now what makes agent runs reconstructable.

The last property is permissioned access to the underlying systems. The whole AppSec story for autonomous agents this year, capability tokens, OAuth scopes, sandboxes, IP allowlisting, scoped API access, is solving a problem that issue trackers have had a defensible answer to for a decade. The agent doesn’t get to do anything the human assignee couldn’t have done. The permissions model already exists.

Each of these properties was built into issue trackers because of a human constraint. Each turns out to be exactly the property an agent system needs. I’d stop short of calling that a coincidence, though. We designed agents to compensate for the same weaknesses we designed issue trackers to compensate for. Limited memory, ambiguous handoffs, and no native accountability. The overlap might feel accidental, but it probably reflects the fact that we built agents in our own image and then handed them tools shaped for our own limitations. The substrate fits agents because the substrate fit asynchronous coordination in general, and AI agents are asynchronous coordinators whose specific weaknesses (no memory, no permissions, no audit) the substrate exactly compensates for.


## What Atlassian and Anthropic are doing about it

If issue trackers are the substrate for agentic work, the company holding the largest installed base of issue trackers, Atlassian, with Jira, is sitting on what just became one of the most strategic data assets in enterprise software. Atlassian has noticed, and the moves they’ve been making in the last twelve months read very differently when you frame them through this lens.

In July 2025, Atlassian shipped its Remote MCP Server, branded Rovo, which exposes Jira and Confluence to any MCP-compatible client. Anthropic was the first official partner. Cloudflare hosts the infrastructure. The launch post emphasized that Jira and Confluence customers can “interact with their data directly from Claude.” Agents create issues, update statuses, search Confluence, link work across products. The product is now in general availability with OAuth 2.1, granular scopes, IP allowlisting, and admin controls. Docker added it to the MCP Catalog in February. The Atlassian Rovo MCP Server is, mechanically, exactly what Symphony assumes Linear is. Atlassian shipped the agent-substrate version of Jira before OpenAI had a public spec for what to do with it.

In February 2026, Atlassian and Anthropic announced a multi-year partnership with the Williams Formula 1 team. Claude as Williams’ “official thinking partner,” branding on the cars and team kit, integration across the team’s race-strategy and engineering operations. This was unusual enough as a deal structure (frontier AI lab × F1 team × enterprise SaaS company) that it caught analyst attention. Yahoo Finance’s coverage flagged that the partnership “links Atlassian more closely to real world AI use cases that may support its story with enterprise customers.” Read in isolation, it’s a sponsorship deal. Read alongside the MCP server launch and the strategic positioning around agent-readable enterprise data, it’s brand-level alignment between the company that owns the largest issue-tracker install base and the AI lab that’s the most natural consumer of it.

And then in late April 2026, around the same time Symphony shipped, a rumor began circulating on Blind, Hacker News, and Reddit that Anthropic was in advanced talks to acquire Atlassian for $150 a share, all-cash. Atlassian’s market cap at that price would put the deal in the $40-billion range. The rumor is unconfirmed. There has been no SEC filing, no formal statement from either company, and the conventional skepticism applies. But the rumor is itself a tell. The fact that the market is willing to treat “Anthropic buys Atlassian” as plausible enough to move share price tells you something about how the strategic value of issue trackers is now perceived. Whether the deal closes or not, the underlying logic, that an AI lab building agent infrastructure has reason to want the largest installed base of agent-substrate in the enterprise, is what’s driving the speculation.

The frame to hold here is not “Anthropic is going to buy Atlassian.” The frame is: in 2026 it became reasonable to model issue trackers as strategic AI assets. That repricing is the news, regardless of whether any specific deal happens.


## Which other tools are like this

The substrate hypothesis is general. Tools with the same structural properties as issue trackers, persistent state, defined verbs, ownership, permissions, audit history, become agent-usable by accident, because they were already shaped that way for human coordination. Tools without those properties don’t, regardless of how much chat you bolt on.

The strong candidates are obvious once you see the pattern. CRMs (Salesforce, HubSpot) have records, owners, stages, history, and permissions. They are issue trackers for revenue. A deal moves from prospecting to qualification to proposal to negotiation to closed-won or closed-lost. That is agent substrate. The agent can research an account, draft follow-up, update fields, flag risk, prepare the next meeting, ask for human approval before sending something externally. The CRM is already a durable state layer.

Service desks (Zendesk, ServiceNow, Intercom) have tickets, assignees, statuses, and SLAs. They are issue trackers for customer problems. If you were designing a customer-support agent from scratch, you would end up rebuilding half of what ServiceNow already has. The agent will not replace the service desk. It will operate through it.

ERPs (SAP, Oracle, Workday) have records, workflows, approvals, and audit trails. They are issue trackers for business process at large. Nobody wakes up excited to spend their day in an approval workflow, but they encode how money, people, inventory, procurement, payroll, and compliance move through the business. The kind of boring structure agents need to do real work.

The pattern keeps showing up in every direction you look: calendars, source control, procurement, HRIS, finance systems. Each one is an issue tracker for its own domain. If a system was built to coordinate people asynchronously around important work, it probably has the bones of an agent substrate.

The weaker candidates are the ones with state but ambiguous verbs and ownership. Email has audit history and permissions but its action verbs are conversational rather than structural. There is no `assign` or `resolve` in email, just `reply`. That means agents can help with email, but email itself is not a clean control plane. It is too conversational. Chat (Slack, Teams) has even less structure. The state of a Slack thread is “the messages in it,” which is closer to a transcript than a database. Agents already operate inside Slack, and Slack has benefited enormously from being the place where humans naturally congregate, because that proximity makes it the first place agent builders integrate. But proximity is not the same as substrate. If Slack is the only place your work state lives, the agent has to infer too much.

Documentation (Confluence, Notion) sits in the middle. It has versioning and permissions but its verbs are weak (edit, comment) and ownership is fuzzy. Useful context, but weaker as a work substrate.

Spreadsheets are the strangest middle case. They have structure, but the structure is user-defined, and often implicit. The spreadsheet can be incredibly structured if the human designed it well, and completely impossible if the human designed it like a personal scratchpad. Claude for Excel is essentially a bet that the LLM can infer enough of the user’s implicit schema to operate on the data anyway. That bet is probably correct in the long run but hard in the short run. Spreadsheets are not the same easy substrate that Jira is.

The diagnostic for any tool in your stack is five questions. Does it have records or just content? Does it have a state machine or just labels? Is ownership a field or an implication? Are the verbs structural or conversational? Is the history queryable or just visible? Tools that score well on these will become agent infrastructure. Tools that score poorly will need to be replaced or wrapped, and the wrapping will be expensive.


## What this means for you

For individual builders, the implication is direct. Your data model is your strategic surface now. If you are building a product that you want agents to use later, don’t start by bolting chat onto the UI. That is a very 2024 approach. Start by making the underlying state clean. Expose state, verbs, ownership, and history through an MCP server. Treat your data model as the public interface, not your UI. If your product is opaque, the agent has to scrape the UI or guess what the user meant. That is fragile. If your product exposes clean state and clean verbs, the agent can operate through it. That is the difference between “we added AI” and “we became part of the agent stack.” The pattern Symphony makes explicit, work-tracking system as the literal control plane for autonomous work, is going to repeat across every domain where work is already tracked.

For teams, the implication is sharper than it sounds. Your work-tracking system choice is now your agent-infrastructure choice. The decision between Jira and Linear isn’t a UX question anymore. It’s a question about which substrate your future agents will run on, how cleanly your work data is encoded, and what shape of automation will be cheap to build versus expensive to retrofit. The same is true for your CRM, your service desk, your HRIS, your ERP. If your operations are spread across systems with poor MCP support and ambiguous data models, you have a substrate problem you’ll be paying for in 2027 even though it doesn’t feel like a problem today. This is one of the hidden costs of messy operations. Messy operations used to be a human tax. People could compensate with meetings, memory, relationships, and heroics. Agents are worse at that. Agents need the business to be legible. The cost of consolidating onto better-shaped tools is going to look small, in retrospect, compared to the cost of running agents on top of a swamp.

For leaders, the strategic frame is the one the Atlassian rumor surfaces whether or not the deal happens. The boring infrastructure your organization already runs on, the tickets, the records, the workflows, the audit logs that nobody finds interesting, is being repriced as agent substrate. The companies that own the substrate (Atlassian, Salesforce, ServiceNow, Microsoft, Oracle) are going to be unusually well-positioned for the next several years, because the substrate is hard to displace and the agent layer wants to consume it. The companies whose strategy depends on building agent-native replacements for these systems are fighting gravity. The thirty-year accumulation of human-coordination infrastructure isn’t going to be eaten by a green-field “agent platform.” It’s going to be wrapped, and the wrappers are mostly going to be the incumbents with MCP servers stapled on. Bet accordingly.

But there’s a practical question underneath the strategic one that I don’t think enough leaders are asking: what does your specific substrate actually look like right now? Every organization runs on a different patchwork of these systems, and the real work of building agentic pipelines isn’t choosing which AI model to use. It’s mapping the substrate you already have. Where does your ERP hand off to your CRM? How do your tickets connect to your customer feedback? Where are the clean handoffs, and where is the work state living in Slack threads and spreadsheets that nobody besides the person who built them can interpret? You cannot build a serious agent layer by wiping that away and starting fresh. You have to audit what you have, understand the schemas across your systems of record, and figure out where the connectors belong. The point where this stops being a strategy conversation and starts being an implementation one.


## The boring tools won

Saarinen’s “issue tracking is dead” framing was right about the user interface and wrong about the substrate. The translation step is dying. The state machine is staying. What we built for ourselves over thirty years, the boring infrastructure of records, workflows, ownership, and audit trails, turned out to be the substrate agents needed, and we built it by accident, because the constraints that shaped it for human coordination happened to be the same constraints agents are now trying to compensate for.

The accident is the whole story. The thing nobody loved is the thing nobody can replace. Issue trackers won. The interesting question for the rest of 2026 is which other boring tools are about to follow them, and the diagnostic is sitting in plain sight: persistent state, defined verbs, ownership, permissions, history. If your tool has those, it’s about to become much more strategic than it looks. If it doesn’t, the substrate is going to be built around it, by someone else, and the difference between owning the substrate and being wrapped by it is the difference between the next decade going well and going badly.

The boring tools won. Now we figure out which other boring tools are next.

[![](https://substackcdn.com/image/fetch/$s_!Q7An!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F83c8e450-fc5c-40c1-b21d-5c11d0d2f34d_2048x2048.png)](https://substackcdn.com/image/fetch/$s_!Q7An!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F83c8e450-fc5c-40c1-b21d-5c11d0d2f34d_2048x2048.png)
