---
title: "Executive Briefing: What Cursor’s $57K CMS Deletion Reveals About Where Agent Value Actually Lives"
author: "Nate Jones"
published: 2025-12-14
url: https://natesnewsletter.substack.com/p/executive-briefing-what-cursors-57k
audience: everyone
scraped_at: 2026-01-05 19:10:03
---

Cursor just deleted the CMS running their website. And it wasn’t a mistake.

This was the work of Lee Robinson, a dev educator at Cursor.

He saw the way a CMS slowed the team down, and just decided to get rid of it. Three days, over 300 agent pull requests, $260 in tokens, and suddenly Cursor’s agents could ship code straight to the website from slack.

Was this the money? Not really. Sure, the CMS had cost Cursor nearly $57,000 so far this year.

But the real cost wasn’t the invoice—the real cost was cutting agents out of the loop. And that’s what I want to talk about this week.

At Cursor, it is unacceptable to click through menus instead of delegating to agents. Those menus aren’t innocent. They’re built to make content easier but in 2025 they’ve become a wall between the agents and the work.

Last week I argued that most enterprise agents fail because they don’t remember. This week is the uncomfortable follow-on: even if you solve for memory, most companies will run into a wall of software that blocks those agents from acting.

The work itself is stuck—hidden behind click paths, scattered across draft modes, encoded in tribal knowledge. You buy agents; you get a conversation layer on top of the same bottlenecks.

Cursor’s story shows what it looks like to break through. Not by getting better agents, but by asking which abstractions are still earning their keep. I’m extending that story here to get at the real heart of the problem—what it takes to get to Cursor’s level of fluency with agents when you don’t start with AI-native talent.

**This briefing covers:**

- **The abstraction tax**: Why convenience layers that helped humans for decades are now blocking agents—and how to see where you’re paying it
- **Two kinds of primitives**: What makes agents reliable (last week) versus what makes work shippable (this week). You need both.
- **The cultural pattern**: Why Cursor’s marketing team commits code, and what “code wins” actually means for non-engineers
- **Six concepts to teach your non-tech teams besides prompting**: State, artifacts, change records, checks, rollback, traceability
- **Three prompts to make this real**:

  - *The Abstraction Tax Audit*: Find where your current tools are blocking agent leverage
  - *The Primitive Fluency Gap Analysis*: Design training around work primitives for non-technical teams
  - *The “What Would We Delete?” Exercise*: Identify sacred workflows that might be candidates for simplification

The winners won’t be the companies with the most agents. They’ll be the ones where enough people understand the primitives to delete sacred workflows and let agents actually operate.

I think this story is one of the most interesting of the year, and it illustrates one of the big change themes we’re going to see in 2026 across companies. Jump in and get a head start here!

> *This is an Executive Circle briefing, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via [this 60 second video](https://youtu.be/KC3GkEnHR-8) explaining what’s in each tier, and you can [change your plan here](https://support.substack.com/hc/en-us/articles/360044105731-How-do-I-change-my-subscription-plan-on-Substack).*


## [Grab the prompts](https://www.notion.so/product-templates/Primitives-Briefing-Self-Guided-Strategy-Prompts-2c95a2ccb52680afade7ee1522ad2eef?source=copy_link)

I built three prompts to help you actually do something with this briefing. Each one is fully self-contained—you copy the whole thing into a fresh LLM conversation and work through it interactively, one question at a time. The first is an **Abstraction Tax Audit**: you describe your workflows, and the LLM helps you identify where you’re paying hidden costs for GUI-based tools that block agent leverage.

The second is a **Primitive Fluency Gap Analysis**: you describe your team, and the LLM helps you design a lightweight training curriculum that teaches the conceptual building blocks (state, artifacts, checks, rollback, traceability) without requiring anyone to learn to code.

The third is the spiciest—a **“What Would We Delete?” Exercise** where you identify sacred tools and workflows that might be candidates for simplification or removal now that agents have changed the economics.

These aren’t vague strategy exercises. They’re designed to surface specific, actionable insights about your organization. Pick the one that matches where you are: skeptical and want proof, bought in and want to build capability, or ready to act and looking for targets.

---


## Where Agents Run Into Walls


### The Wall is Your Own Software

Most agent deployments stall at the same place. The agent writes a plausible draft, summarizes a meeting, generates options, proposes a plan—useful work, genuinely useful—and then it hits a wall. Not a capability wall. An environmental wall.

That wall is your operating environment.

In most Fortune 500 companies, and honestly in most mid-sized businesses too, important work lives inside opaque workflows. It’s behind click paths in business software: admin portals, ticketing tools, CMS screens, dashboards with seventeen tabs. It’s trapped in hidden state: draft modes, unpublished versions, permission rules that aren’t visible until you hit them and get an error message nobody anticipated. It’s encoded in tribal knowledge: “ask Sarah,” “finance owns that,” “we don’t touch that system,” “the real process is different from what’s documented.”

An agent can’t reliably operate inside that environment. It can advise—that’s what chatbots do. It can draft—that’s what writing assistants do. But it can’t ship. It can’t close the loop. It can’t take work from “here’s a good idea” to “this is done and verified and in production.” The human still has to navigate the click paths, remember the tribal knowledge, manage the hidden state.

So when a company “buys agents,” what it actually buys is more conversation layered on top of the same bottlenecks. The throughput gains stay stuck in chat windows. The agents advise; the humans click. And everyone wonders why the productivity numbers aren’t moving the way the demos suggested they would.


### The Cursor Story

Lee Robinson is a long-time builder and writer who was previously at Vercel and now works at Cursor teaching about AI. Cursor is one of the breakout companies in AI-assisted coding—their product is an IDE designed around agents. If anyone should be AI-native by default, if anyone should have figured out how to let agents actually operate rather than just advise, it’s Cursor.

Which is what makes Lee’s December essay so interesting. It reads like a weekend project writeup, the kind of thing developers post all the time. But if you’re paying attention to where enterprise software is headed, it should be treated as a strategic signal.

Lee migrated Cursor.com from a headless CMS back to raw code and Markdown. Before you ask, yes, this is a real website for a hundred million dollar business. That screen animates on the site.

[![](https://substackcdn.com/image/fetch/$s_!1NUr!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F075f6e49-b21c-415f-964e-fbaca3558272_2360x1580.png)](https://substackcdn.com/image/fetch/$s_!1NUr!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F075f6e49-b21c-415f-964e-fbaca3558272_2360x1580.png)

Deleting a CMS is, by conventional wisdom, regression. For decades we’ve been told that marketing teams need content management systems so they can make changes without bothering engineering. The CMS is supposed to be the grownup move—the thing you add when you’re ready to scale content operations beyond what developers can handle.

Lee estimated the migration would take weeks. He thought he might need to hire an agency. This is a guy who works at an AI-native company, who teaches people how to use AI tools, and even he assumed this would be slow and expensive.

He finished in three days over a weekend. About $260 in tokens. Hundreds of agent pull requests—somewhere around 300 before it was done.

But the headline isn’t “agents are fast.” The headline is what he noticed about why the CMS had become a problem in the first place.

Before Cursor introduced their CMS, Lee could ask an agent to modify the website directly. Change marketing copy, update a landing page, adjust messaging—just tag Cursor in the command line and describe what you want. The agent could see the work, understand the structure, make the change, verify it worked. Simple.

After the CMS went in, that stopped working. The team was “back to clicking through UI menus” instead of delegating to agents. The CMS, which was supposed to make content operations easier, had actually made agent operations harder. It had become a wall between the agent and the work.

Lee’s conclusion is the line every executive should internalize: “With AI and coding agents, the cost of an abstraction has never been higher.”


### What “Abstraction” Means When You’re Not Technical

An abstraction is a layer that hides underlying work behind a simplified interface. You encounter them constantly. A CMS hides files, structure, deployment pipelines, and version control behind friendly screens that say “Edit page” and “Publish.” A ticketing system hides database writes and workflow state behind forms and buttons. A dashboard hides SQL queries and data transformations behind charts you can click on.

For decades, this was a good trade. Most organizations are mostly non-technical. The abstractions made work accessible to people who couldn’t—and shouldn’t have to—understand what was happening underneath. You didn’t need to know how the database worked to update a support ticket. You didn’t need to understand deployment pipelines to publish a blog post. The abstraction handled it.

That’s different now: the minute you want agents to operate, not just advise, the hidden parts become the expensive parts.

Agents don’t thrive in clicky environments. They struggle when state is scattered across screens, when permissions are implicit rather than explicit, when draft modes and hidden dependencies create invisible context that isn’t written down anywhere. Agents thrive in environments where the underlying work is visible and editable—where they can see what exists, understand what a change means, make the change, and verify the result.

So the CMS stopped being a helpful tool. It became a wall. Not because CMSs are bad—they’re still useful for plenty of workflows—but because in Cursor’s specific context, the abstraction was hiding work that agents could have operated on directly.

That’s why this story matters. It’s not really about a website. It’s not really about CMSs. It’s about the new economics of complexity, and the question every enterprise needs to ask about every workflow: is this abstraction still earning its keep, or has it become a tax we’re paying for organizational capabilities we no longer need?


### The Hidden Taxes Lee Enumerated

[Lee’s essay](https://leerob.com/agents) is unusually valuable because he doesn’t just say “CMS bad” and move on. He itemizes the costs. If you strip away the web-dev details, the list looks like a familiar pattern—one I’ve seen in every enterprise I’ve worked with, across dozens of different tools and workflows.

**Two identity systems.** Users existed in GitHub and in the CMS. Someone always needed to be “added” when they joined, “removed” when they left, “granted access” when they needed to touch something new. That’s operational drag—someone has to manage it—and permission risk, because the two systems can drift out of sync in ways nobody notices until something breaks or someone accesses something they shouldn’t.

**Preview complexity.** Draft content required special access paths and brittle preview logic. Sharing “what we’re about to ship” with stakeholders meant sharing special URLs, explaining how to access the preview environment, troubleshooting when it didn’t work. The CMS was supposed to make content operations easier, but it had introduced friction at exactly the point where teams need speed: the review-and-approve loop before something goes live.

**More moving parts to keep everything fast and reliable.** In an agent world, the site wanted to be simple, stable, and prebuilt—a single state representation that could be updated directly. The CMS introduced uptime dependencies and special modes that worked before agents, but looked less helpful now. Does it make sense in the age of agents to maintain a website plus a content management system plus the integration between them plus the deployment pipeline that knows about both? For Lee it didn’t.

**Real cost markup.** Here’s the number that should get attention: Cursor spent $56,848 on CMS CDN usage since September. Lee calls it “a hefty markup for the convenience of the GUI.” That’s not server costs for running sophisticated infrastructure. That’s paying a premium for the privilege of clicking through menus instead of editing files directly.

**Hidden dependencies.** When pieces of the site came from network fetches, when content lived in the CMS and got pulled in at build time, even humans couldn’t easily answer “where does this come from?” without digging. That network boundary, that separation between “the code” and “the content,” created cognitive overhead. People had to maintain hidden state in their heads about what lived where and how it all fit together.

These costs were always real. They weren’t new. But they were acceptable when the alternative was asking non-technical people to edit code directly. The CMS tax was worth paying because it bought accessibility.

The thing that changed is that the alternative isn’t “non-technical people editing code directly” anymore. The alternative is “non-technical people describing what they want to an agent that edits the code for them.” If the agent can do it—if the agent can operate on the underlying work—then the abstraction isn’t buying accessibility anymore. It’s just buying friction.


### What Lee Actually Did

Lee moved the site back to a work surface that is legible to both humans and agents: raw code and Markdown files in a repository.

That sounds like regression if you’re thinking in 2015 terms. It’s not. It’s recognizing that the economics of who can operate on what have fundamentally shifted.

The move collapsed complexity into a single, inspectable place. No more two identity systems—everyone’s in GitHub, which is where they already were for code. No more preview complexity—preview is just “look at the branch,” which is how developers have worked for years. No more hidden dependencies—everything is in the repo, everything is visible, everything is traceable.

And critically: agents can operate on it directly. You can tag Cursor and say “update the pricing page to reflect the new enterprise tier” and the agent can see the file, understand the structure, make the change, open a pull request, and the same review workflow that governs code changes now governs content changes too.

If you’re not technical, here’s what matters: the work moved from “state hidden inside a tool” to “artifacts everybody can see, review, and undo.” That shift is what makes agent operations possible. Not agent capability—agents were already capable—but agent operability, the ability to act on work rather than just advise about it.

Essentially, Lee pulled the meaningful work (the website updates) out of a hidden state (the CMS) where agents couldn’t easily touch it into a simple, obvious space agents and people could operate against (the code plus Markdown files).


### Why Cursor Can Do This and Most Companies Can’t

Here’s the uncomfortable question: why can Cursor execute this move and most companies can’t?

It’s not because Cursor has better agents. Everyone has access to the same models. It’s not because Cursor is smaller—they’re growing fast and have real operational complexity. It’s not because Cursor’s website is simpler than whatever your company does—complexity is relative, and the principles transfer.

Cursor can do this because they’ve built a culture where “technical” is not a department. It’s a default posture.

Lee says it explicitly when describing how they think about user management: in a world where designers can commit code, it’s not a stretch to have marketing in GitHub too. That sounds radical if you’re sitting inside a Fortune 500 organization with a 200-person IT department and strict separation between “business users” and “technical users.” At Cursor, it’s just normal. It’s how they operate.

And this isn’t just Lee’s personal take. A detailed Colossus profile of the company notes that Cursor’s go-to-market team is “surprisingly technical”—using Cursor itself for website updates, dashboards, and internal tools. They ship work directly, not by routing everything through engineering. They’re not waiting for someone else to implement their ideas; they’re implementing their ideas themselves, with agent assistance.

The same profile describes a company that constantly deletes friction. Internal debates get framed as “does anyone use this—can we kill it?” There’s a culture of dogfooding and testing that keeps defaults evolving rather than calcifying. They have a pre-ship ritual called “Fuzz” where everyone tries to break the release before it goes out, and then fixes land fast because the people who found the problems can also fix the problems.

This is not startup chaos. This is not something that only works at small scale. It’s a coherent operating model: shared agency, shared substrate, shared responsibility. The reason it enables agent leverage is that when everyone can operate on the underlying work, the underlying work can be designed for operability rather than for protecting people from complexity they’re not supposed to touch.


### The Thesis: Code Wins Is Not an Engineering Slogan

When executives hear “code wins” then tend to interpret it as an engineering slogan—engineers advocating for their own importance, claiming that technical work is more valuable than business work, positioning themselves as the essential center of the organization.

In the agent era, that interpretation is incorrect. “Code wins” is becoming a strategic law about where agent capability is concentrated and where it will remain concentrated for the foreseeable future.

Here’s why: work that can be expressed in code-like form gets a fast track to agents, because the entire industry is investing its best models, its best tools, its best safety mechanisms, and its most rigorous evaluation discipline into the code pathway.

You can see this clearly in Anthropic’s own engineering guidance on long-running agents. They describe the core problem the same way I did last week: agents work in discrete sessions, and each new session begins with no memory. It’s like staffing a project with people working in shifts who don’t talk to each other. Each shift starts fresh, tries to figure out what happened before, makes some progress, and hands off nothing useful to the next shift.

Their solution is not magical AI memory. It’s a disciplined harness built around artifacts: an initializer agent that sets up the environment and recovers state, a coding agent that makes incremental progress, and—this is the key—”clear artifacts for the next session,” including a progress file and git history so the agent can quickly understand what state the project is in when it picks up work.

They even note that context compaction alone isn’t sufficient. Without the harness, without the artifact discipline, the agent tries to one-shot the entire task, runs out of context mid-stream, and the next session has to guess what happened. Sound familiar? It’s exactly what happens in enterprises when agents try to operate on work that isn’t written down in a form they can parse.

This is the memory argument from last week validated by a major lab. But it also reveals something bigger: the most mature agent discipline in the world is being built where artifacts are already native. Code, repos, tests, logs, markdown files, configuration as code—these are the substrates where agent operations are furthest along, most reliable, best understood.

The implication for executives is uncomfortable but clear:

- If a workflow resolves to artifacts plus checks, agents can participate in execution today.
- If a workflow lives inside tool UI state and human memory, agents will remain advisors until you change the workflow.

This is why software development is seeing agent leverage first. Not because engineers are better people or more deserving of productivity gains. Because software development already built the infrastructure of legibility: version history, diffs, tests, rollbacks, audit trails. Agents plug into that infrastructure like an appliance plugs into a wall socket. The socket was already there.


### Two Kinds of Primitives—And the One Most Enterprises Ignore

If this is going to land with non-technical executives, we need precision about what “primitives” actually means.

A primitive is a small, stable building block that stays useful even when tools change. In the agent era, there are two primitive stacks that matter, and most enterprises only talk about one of them.

**Agent primitives: what makes an agent reliable**

This is what last week’s briefing focused on. You need a clear definition of “done”—what does success look like, expressed in terms an agent can evaluate. You need a persistent record of state, which I’ve been calling domain memory—the goals, the progress so far, the operating procedures, written down where the agent can access them. And you need a procedure for how work progresses and gets validated—not just “try stuff and see if it works” but a structured approach to incremental progress and verification.

Without these, you get amnesiacs with tool belts. Capable, but unable to sustain work across sessions.

**Work primitives: what makes work shippable**

This is what enterprises almost never define explicitly, and it’s why agent rollouts stay stuck in chat even when the agent primitives are solid.

Work primitives are the basics of operational change—the underlying mechanics of how anything gets done in an organization:

- **System of record**: What is the thing we change? Where does the canonical truth live? If you can’t point to a specific place where the real state of the work is stored, your agent will hallucinate it or operate on stale data or make changes that conflict with changes someone else is making.
- **Readable diff**: How do we see what changed? Software has diffs—you can see exactly what lines were modified, added, deleted. Enterprises need the equivalent for policies, pricing, content, configurations, workflows. “It’s different now” isn’t enough. You need “here’s specifically what’s different and why.”
- **Defined gate**: How do we approve it? Who has to say yes before this goes live? Under what conditions can it go live automatically? The approval process has to be explicit enough that an agent can understand when to proceed and when to wait.
- **Check**: How do we prove it works? “It looks good” isn’t a check. A check is something objective—a test, a reconciliation, a policy rule, a validation script, a required approval from someone with the right expertise. If the only verification is “a human looked at it and felt okay,” you don’t have a check; you have a vibe.
- **Rollback**: How do we undo it safely? Agents increase throughput. That’s the point. But increased throughput without rollback capability is increased risk. You need to be able to reverse changes when they turn out to be wrong, quickly and reliably.
- **Traceability**: Who changed what, when, and why? This stops being a compliance nicety and becomes existential when your “AI workforce” grows. If you can’t reconstruct the history of how something got to its current state, you can’t debug problems, you can’t learn from mistakes, and you can’t satisfy auditors.

Lee’s CMS story is a work-primitive story. He replaced a UI-state workflow—where content lived in a CMS with its own hidden state and access patterns—with an artifact workflow where content lives in files with version history, diffs, approval via pull request, tests in CI, and full traceability via git log. The artifact workflow has natural review, rollback, and traceability built in. The CMS workflow had those things bolted on awkwardly, if at all.

Anthropic’s long-running agent harness is the same story told from a different angle. They made progress reliable by insisting on artifacts, state files, and incremental steps—not because those things are theoretically elegant but because they’re the practical prerequisites for agents that can pick up where they left off and for humans who need to understand what the agents did.

Here’s the connective tissue between last week’s briefing and this one:

**Domain memory is not just an agent technique. It’s a work primitive. It is the written state of the project.**

If your organization doesn’t know how to write state down in canonical places—if important information lives in people’s heads, in scattered documents nobody maintains, in implicit assumptions about “how we do things here”—then memory can’t save you. The agents can have perfect memory of their own sessions. But if the work itself isn’t legible, there’s nothing useful to remember.


### The Cultural Pattern: Teaching the Substrate

The reason Cursor can kill a CMS is not that they have a bias against graphical interfaces. It’s that their people can operate on the underlying substrate—the code and files and version control that the GUI was abstracting over.

The Colossus profile makes the key point: this isn’t limited to product and engineering. The go-to-market team is technical. They use Cursor to ship internal work—dashboards, website updates, internal tools. They’re not waiting for engineering to implement their ideas; they’re implementing them directly, with agent assistance.

I’ve seen the same pattern at other companies, including OpenAI. Designers are in the codebase. Non-technical staff use Codex for tasks that would have been routed to engineering a few years ago. Role boundaries are blurring. Code review is becoming an ambient safety net rather than a bottleneck that only engineers pass through.

That’s “code wins” as an operating model: the organization is training more people to think and act in artifact-based workflows, because that’s where agents are strongest and that’s where they’re safest.

This is the part most enterprise leaders don’t want to hear, but need to:

If you keep your workforce GUI-native—if your security department and IT department keep insisting that “only engineers should commit code” because that’s what felt safe in 2015—your agents will remain drafting assistants. They’ll be stuck at the advisory layer, unable to close loops, unable to ship, unable to deliver the 10x productivity gains the demos promised.

If you teach your workforce to be artifact-native—not “become engineers” but “understand the substrate well enough to operate on it with agent assistance”—your agents can become operators. They can participate in execution, not just preparation. They can close loops and ship work.


### What to Teach Instead of Prompting

If the strategic claim is that code-like work wins because it’s agentable, then the logical conclusion follows directly:

**Enterprise AI training must become code-concept training for non-engineers.**

Not “learn Python.” Not “become a software developer.” But learn the concepts that make work legible to agents—the mental models that let you understand what’s happening underneath the GUIs you’ve been clicking through for years.

The goal is not to turn everyone into programmers. The goal is to turn more of the company into people who can express work in a form that agents can safely act on.

Here are the six concepts, stated plainly:

**State.** What is the current status of the work? Where is that written down? If you can’t point to a specific location where the canonical state lives, you have a problem. Your agent will hallucinate state, or operate on stale state, or conflict with work someone else is doing. “I know it in my head” doesn’t count. “It’s in the system somewhere” doesn’t count. You need to be able to point.

**Artifact.** What is the system of record? What is the real thing we ship and maintain? Is it a document, a dataset, a configuration file, a product catalog, a policy definition, a pricing table? Whatever it is, it needs to be identifiable, editable, and versioned. If the truth lives in a UI with hidden state—in draft modes and unpublished versions and permission-gated screens—your agent can’t reliably operate on it.

**Change record.** Can we see exactly what changed, without argument? Software has diffs. When a developer changes a file, anyone can see precisely what was different before and after. Enterprises need the equivalent for everything else: policies, pricing, content, workflows, configurations. When something changes, there should be a record that shows what changed, when, and ideally why.

**Checks.** What proves this is correct? “It looks good” is not a check. “Sarah reviewed it” is barely a check. A real check is something objective: a test that passes, a reconciliation that balances, a policy rule that’s satisfied, a validation script that runs clean, an approval from someone with defined authority. Agents increase throughput. Checks are what keep throughput from becoming chaos.

**Rollback.** How do we undo safely if we’re wrong? If you can make a change but you can’t unmake it—if reverting requires heroics, or archaeology, or “rebuilding from scratch”—you have a rollback problem. Agents will make mistakes. Humans make mistakes too, but agents make them faster and at higher volume. The ability to undo cleanly is what makes speed safe rather than terrifying.

**Traceability.** Who changed what, when, and why? This is audit trail, but it’s more than compliance. When something goes wrong, you need to be able to reconstruct the history. When you’re trying to understand how something got to its current state, you need to be able to trace back. When your AI workforce grows to dozens or hundreds of agents making thousands of changes, traceability becomes the only way to maintain understanding of your own operations.

If you teach these six ideas broadly—not just to engineers, but to the product managers and designers and marketers and operations people who need to work with agents—you create the precondition for real agent adoption. The organization stops treating tools as sacred. People stop saying “but that’s how Salesforce works” as though Salesforce’s UI were a law of nature. Everyone understands what must stay true underneath—the state, the artifacts, the checks—and that understanding makes it possible to question whether the current abstractions are still earning their keep.

That’s why Cursor can ask “do we really need a CMS?” and actually execute the deletion. They weren’t being reckless. They understood what would replace it: a simpler substrate with stronger primitives, one that both humans and agents could operate on directly.


### What This Implies for Training Programs

Most enterprise AI training programs focus on prompting. How to write good prompts, how to use ChatGPT, how to get better outputs from Claude. That’s not useless—prompting skill matters—but it’s also not the bottleneck.

The bottleneck is that people don’t understand what they’re prompting agents to operate on. They don’t have mental models of state, artifacts, changes, checks. They think in terms of “clicking through the system” rather than “changing the underlying data.” They’re GUI-native in a world that increasingly rewards artifact-native thinking.

What this implies:

**Reframe “AI fluency” around work primitives, not prompt engineering.** The training that matters is not “how to talk to the AI” but “how to structure work so the AI can act on it.” State, artifacts, change records, checks, rollback, traceability. These are the concepts that unlock agent operations, and they’re not being taught systematically anywhere I’ve seen.

**Use the CMS pattern as a diagnostic.** For every major workflow, ask: if an agent needed to operate on this directly, could it? Or would it hit a wall of hidden state, implicit permissions, tribal knowledge? The workflows where the answer is “it would hit a wall” are your modernization priorities.

**Accept that some role boundaries will blur.** When designers commit code, when marketers edit configuration files, when operations people write validation scripts, traditional org charts stop making sense. This is uncomfortable, but it’s also where the leverage comes from. The alternative is maintaining strict role boundaries and accepting that agents will stay stuck at the advisory layer.

**Build rollback capability before you build throughput.** This is security and risk management, but it’s also enablement. People are afraid to let agents operate because they’re afraid of what happens if the agent gets it wrong. Rollback capability is what makes speed feel safe. Invest in it early.


### The Real Competitive Advantage Isn’t Copying Cursor

The mistake would be to interpret this briefing as “copy Cursor and put marketing in GitHub.” That’s not the point, and it wouldn’t work anyway. Cursor’s specific moves only make sense in Cursor’s specific context.

The point is the underlying competitive advantage: **primitive fluency diffuses power.**

When teams share a mental model of state, artifacts, checks, rollback, and traceability—when those concepts are part of the common vocabulary rather than technical jargon that “engineering handles”—the company gains a new capability:

People can see that a “standard tool” is just a convenience layer with a measurable tax. The tool isn’t sacred; it’s a choice, and choices can be revisited when the economics change.

People can propose simplification without triggering fear. When everyone understands what must stay true—the state integrity, the audit trails, the approval flows—they can articulate why a simpler approach would be safe. The conversation shifts from “that sounds risky” to “let’s verify that the primitives are preserved.”

Work can be recomposed into forms agents can operate on, instead of being trapped in process. The barriers that currently keep work inside clicky interfaces start to look like what they are: historical artifacts of a world where non-technical people couldn’t safely touch the underlying systems. That constraint is lifting. The question is how fast your organization adjusts.

That is what “moving fast” looks like in a mature agent organization. It’s not speed for its own sake. It’s less hidden state, fewer brittle handoffs, more of the company able to safely ship changes, and agents that can actually participate in execution rather than hovering on the sidelines offering suggestions.


### A Reminder

Last week I reminded you that agents fail because they don’t remember. You can and should fix that with domain memory—explicit state written down where agents can access it between sessions.

This week I am reminding you that organizations fail because they don’t write work down in agent-legible forms. The memory is useless if there’s nothing legible to remember. You fix that by teaching primitive fluency—code-concept fluency spread across the organization, so more people can see the substrate underneath the GUIs and understand what makes work operable versus merely accessible.

**Agent strategy is not a procurement decision. It’s a literacy decision.**

The winners won’t be the companies with agents—everyone will have agents soon enough, and the model capabilities are converging. The winners will be the companies where enough people understand the primitives that they can delete sacred workflows, move work into legible artifacts, and let agents actually operate.

That’s where the 10x comes from. Not from better prompts. From work that’s structured for operability, in organizations where enough people understand what that means to make it happen.

[![](https://substackcdn.com/image/fetch/$s_!6Th0!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F92cc752f-269c-48de-ac7e-e9c25e1fac3b_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!6Th0!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F92cc752f-269c-48de-ac7e-e9c25e1fac3b_1024x1024.png)
