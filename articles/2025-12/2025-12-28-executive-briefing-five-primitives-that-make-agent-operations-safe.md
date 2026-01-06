---
title: "Executive Briefing: Five Primitives That Make Agent Operations Safe"
author: "Nate Jones"
published: 2025-12-28
url: https://natesnewsletter.substack.com/p/executive-briefing-the-human-throttlewhat
subtitle: "Watch now | We spent 20 years making software undoable."
audience: everyone
scraped_at: 2026-01-05 19:08:49
---

We spent 20 years making software undoable. Version control, code review, staging environments, canary deployments, rollback procedures—the entire culture of modern software delivery is one long project in making mistakes survivable. That’s the hidden reason AI agents are actually working in engineering. The environment was deliberately designed so that errors don’t have to be catastrophic.

The rest of your business wasn’t designed that way.

That’s why agents fail everywhere else—not because they aren’t smart enough, but because mistakes in most business operations can’t be recovered at machine speed. The gap between what agents can do in demos and what organizations are willing to let them do in production isn’t primarily an intelligence gap. It’s a reversibility gap. Demos happen in sandboxes where mistakes don’t matter much. Your business happens in a world where mistakes cost real money, real trust, and sometimes real careers.

This briefing explores what it would actually take to close that gap:

- **The zone of comfort**: A framework for understanding why some decisions feel safe to delegate and others don’t—and why the path to agent autonomy runs through reversibility, not intelligence
- **The civilization of undo**: How software engineering built the infrastructure for safe change over decades, and what that infrastructure actually consists of
- **The human throttle**: What informal safety system humans have been providing all along, and what happens when you remove it
- **Primitives for reversibility**: The specific mechanisms that would need to exist before agents could safely operate in domains beyond code

The organizations that figure this out won’t necessarily have the most sophisticated AI. They’ll have the most boring agent operations—predictable, bounded, recoverable. That boringness is the point.


## [Grab the Prompts](https://www.notion.so/product-templates/The-Reversibility-Audit-Kit-2d55a2ccb52680258adeca4ee507da2a?source=copy_link)

The difference between agents that draft forever and agents that actually act is reversibility infrastructure. Two prompts to help you build it: Decision Inventory maps where your recurring decisions sit on the consequence × reversibility grid and identifies which are closest to the zone of comfort. Reversibility Primitive Builder specs the exact infrastructure—draft states, previews, time windows, compensation contracts, ledger requirements—for the workflows you want to make agent-ready.


## **The Zone of Comfort**

Theory Ventures published a piece earlier this year that clarified something most people are missing about why AI agents haven’t taken over yet. The insight is simple enough to state but has implications that ripple outward: every decision you make lives on two axes. The first is consequence—how bad is it if you get this wrong? The second is reversibility—if you do get it wrong, can you undo it?

Plot these as a 2x2 and something interesting emerges. The upper-left quadrant—low consequence, high reversibility—is what they call the zone of comfort. This is where humans act without much anxiety. Transfer money between your own bank accounts? Fine, you can move it back. Pick the wrong time for a meeting? Reschedule it. These decisions don’t keep anyone up at night because even if you’re wrong, the wrongness doesn’t stick.

Move toward the lower-right—high consequence, low reversibility—and the texture of decision-making changes entirely. Wire your life savings to a stranger? Buy a house? Commit to a vendor contract that locks you in for three years? Now you’re in territory where mistakes are expensive and permanent, where the anxiety is appropriate because the stakes are real and the undo button doesn’t exist.

What makes this framework useful isn’t just that it categorizes decisions. It’s that it reveals something about how hard decisions actually get made. The conventional assumption is that you make hard decisions by getting smarter, by gathering more information, by thinking more carefully. And that’s true, to a point. But there’s another path that’s often more powerful: you make hard decisions by changing their position on the grid.

Think about buying a car, which sits somewhere in the middle of the consequence axis but toward the irreversible end. How do you actually get comfortable enough to do it? You don’t become a fundamentally smarter car buyer. You stack mechanisms that shift the decision toward the comfort zone. A dealership with a generous return policy makes the decision more reversible—suddenly it’s not quite a one-way door. Researching reliability ratings lowers the consequences of being wrong—if the car is likely to be dependable, the downside of choosing it shrinks. Test drives and inspections reduce uncertainty, which functions like lowering consequence because you’re less likely to be wrong in the first place. Each mechanism nudges the decision up and to the left until it crosses some threshold where you’re willing to act.

This reframes the entire conversation about AI agents. The default assumption in the industry seems to be that agents will take on more responsibility as they get smarter—that the path to autonomy runs through capability. If models can reason better, plan better, use tools better, they’ll be trusted with more. But the zone of comfort framework suggests something different. The path to autonomy runs through reversibility. An agent doesn’t need to be smarter to handle a decision that’s been made more reversible. It just needs to be good enough, because the cost of being wrong has been contained.

This is why tool calling standards like MCP, important as they are, don’t solve the deeper problem. MCP makes it technically possible for an agent to take an action across systems. It’s plumbing, and good plumbing matters. But plumbing doesn’t change where a decision sits on the grid. An agent with access to Carvana’s API could technically purchase a car. The technical capability exists. What doesn’t exist is any mechanism that makes that purchase more reversible or less consequential. The tool access just makes the action faster—which, for a decision that’s already in the danger zone, makes things worse rather than better.

This is also why every serious agent product stops at “confirm.” That pause before the point of no return—where the agent has done the work but a human has to click the button—isn’t timid product management. It’s an acknowledgment that the real world doesn’t have an undo button, and no vendor can take responsibility for mistakes that can’t be fixed.


## **The Civilization of Undo**

If the path to agent autonomy runs through reversibility, software engineering starts to look less like “the first domain AI conquered” and more like “the one domain that was ready.” And the readiness wasn’t accidental. It was built, over decades, by people who kept getting burned by irreversibility and decided to do something about it.

Version control seems obvious now—of course you’d want to track every change to code, see exactly what was different, and be able to return to any previous state. But Git took years to develop, and the practices around it took even longer to become universal. Before version control matured, developers were emailing files to each other, maintaining parallel copies with names like “final\_v2\_actually\_final,” and praying they could reconstruct which version was the working one if something went wrong. The ability to undo, to branch off and experiment without risking the main codebase, to see a complete history of how the code evolved—none of that was given. It was built, painstakingly, because irreversibility kept causing disasters.

Code review emerged from similar pain. Having another person look at your changes before they go live seems like common sense, but it required building tooling, establishing norms, and convincing organizations that the slowdown was worth it. The reviewer functions as a deliberate checkpoint—a pause between “I think this is right” and “this is now running in production.” It’s a human throttle, consciously inserted into the process because people learned that the cost of catching mistakes early was much lower than the cost of fixing them later.

Staging environments, canary deployments, feature flags, automated testing, observability platforms—each of these represents a hard-won lesson about making change safer. Canary deployments, for instance, are an admission that you can’t always know if a change will cause problems until it hits real traffic. So instead of deploying to everyone and hoping, you deploy to a small percentage of users, watch what happens, and roll back if something breaks. You’ve converted a potentially catastrophic mistake into a contained incident. The blast radius is bounded by design.

What’s easy to miss is how much cumulative investment all of this represents. We’re talking about tens of millions of human hours, probably more, spread across decades. The entire culture of modern software delivery—the CI/CD pipelines, the staging environments, the monitoring dashboards, the incident response procedures, the blameless postmortems—is basically one massive project in “how do we move fast without breaking everything.”

The DORA metrics that elite engineering organizations track make this explicit. “Change failure rate” measures how often deployments require remediation—how often you have to roll back or hotfix something you shipped. “Mean time to recovery” measures how fast you can restore service when something does go wrong. These aren’t vanity metrics. They’re an industry-wide acknowledgment that mistakes are inevitable, and that the measure of a mature organization is how well it handles them. Reversibility isn’t just nice to have. It’s the operational definition of competence.

Software didn’t become agent-friendly because code is inherently easy to work with, or because engineers are more willing to adopt new technology, or because language models happen to be good at text. Software became agent-friendly because the industry spent decades building a civilization of undo—an entire infrastructure designed to make change safe. Agents can operate there because mistakes are survivable there.

The corollary is uncomfortable: agents struggle everywhere else because that infrastructure doesn’t exist.


## **The Human Throttle**

If you look at the history of software engineering, there’s a clear arc toward making change less scary. But if you look at most other business operations, that arc doesn’t exist. Commerce, finance, HR, legal, customer operations, procurement—these domains have their own histories and their own tooling, but they weren’t shaped by the same pressure to make mistakes reversible. Why not?

Part of the answer is that they didn’t need to be. They had something else instead: humans.

Humans are slow. That’s usually framed as a limitation, but it’s also a form of protection. When a human processes a refund, they don’t just execute it—they read the request, check the account history, notice if something looks unusual. They might pause if the amount seems large, or if the request came through an odd channel, or if the customer’s tone feels off. They might ask a colleague. They might escalate. They might just sit with it for a moment and let some subconscious pattern-matching run in the background.

All of that hesitation and double-checking and social anxiety is doing real work. It’s catching errors. It’s detecting fraud. It’s creating an implicit checkpoint between “the system says do this” and “this is now done.” It’s what I think of as the human throttle—a natural rate-limiting that humans provide simply by being human.

The human throttle isn’t designed. It’s emergent, a side effect of how humans operate. We get tired. We worry about embarrassment. We feel accountable to colleagues who might ask why we did something. We have intuitions that fire when something doesn’t feel right, even when we can’t articulate why. And because we’re slow—because processing even a simple request takes minutes rather than milliseconds—there’s time for all of this to happen. There’s time to catch the mistake before it becomes permanent.

This informal safety system has been hiding the absence of more formal infrastructure. Organizations never had to build reversibility into their processes because human slowness was good enough. The cost of a bad decision was bounded by how many bad decisions a human could make in a day—which, given how long decisions take and how much friction exists in most workflows, isn’t actually that many.

Agents remove the human throttle. That’s the point of them—to operate at machine speed rather than human speed, to process in milliseconds what would take a human minutes. An agent doesn’t hesitate. It doesn’t feel anxiety. It doesn’t worry about whether a request feels off. It evaluates the request against its criteria and executes, because that’s what it was built to do.

This is where the reversibility problem becomes acute. If an agent can process a thousand decisions in the time it takes a human to process one, the error rate isn’t really the issue—even a very low error rate produces a lot of errors in absolute terms. What matters is what happens when those errors occur. In a world where decisions were slow and reversibility infrastructure didn’t exist, you could tolerate mistakes because there was always time to catch them and figure out how to recover. In a world where decisions happen at machine speed, that tolerance disappears. A mistake that would have been caught by a human’s hesitation becomes a fait accompli before anyone notices.

The forcing function is stark: if you want agents to do more than draft, you have to build the safety infrastructure that humans were providing informally. Either the process is redesigned so mistakes are recoverable, or the agent stays confined to the zone where a human can still catch errors before they become permanent. There isn’t really a middle ground.


## **The Commitment Curve**

One of the reasons reversibility is hard to reason about is that most business decisions aren’t cleanly one-way or two-way. They exist on a curve—reversible at the beginning, increasingly irreversible as you progress, finally permanent past some critical threshold.

Selecting a vendor, for instance, starts out highly reversible. You can add vendors to your consideration set, remove them, change your evaluation criteria, revisit earlier conclusions. But at some point you sign a contract, and now you’re committed. The commitment isn’t necessarily absolute—there might be exit clauses, there might be ways to renegotiate—but the texture has changed. What was a matter of preference is now a matter of legal obligation and switching costs.

Or consider changing your pricing. Early in the process, the change exists only in spreadsheets and discussions. You can model different scenarios, argue about strategy, change your mind repeatedly. But at some point the new prices go live—they appear on your website, they get quoted to customers, they show up in contracts. Now the change has become a public promise. You can still alter it, but you’re altering it in the eyes of customers and partners, with all the reputational and operational complexity that entails.

The commitment curve matters because it suggests where intervention is most valuable. Early in the curve, when reversibility is high, agents can operate with relative freedom—mistakes at this stage are cheap to fix. Late in the curve, when you’re approaching the point of no return, much more caution is warranted. The question of “can an agent handle this decision?” is really a question about where on the curve the agent is operating and what infrastructure exists to keep mistakes from propagating past the point where they become expensive.

This is also why the conversation about AI safety, as it applies to agents, often feels strangely disconnected from practical concerns. The philosophical questions about alignment and values are real and important, but the day-to-day challenge of deploying agents is more mundane: it’s about error recovery. In software engineering, error recovery is normal. It has names and metrics. Organizations measure how often they need to recover and how fast they can do it, and these measurements are treated as signs of operational maturity rather than failure. In most other business contexts, recovery is improvised—someone scrambles, someone escalates, someone does damage control. That works when humans are the throttle, when there’s time to figure out the response. It doesn’t work at machine speed.


## **What Would It Take?**

If you accept that the path to agent autonomy runs through reversibility—that the goal isn’t smarter agents but safer substrates—the question becomes what reversibility actually requires. What infrastructure would need to exist before agents could operate as freely in, say, finance operations as they do in software engineering?

The closest analogy is probably what software engineering itself built, but translated into domains that work differently. Five mechanisms seem to do most of the work.

The first is the existence of draft states. In software, nothing goes straight to production. Code goes through staging environments, changes go through review, deployments go through testing. There’s always a proposed state before there’s a committed state—a version of the change that can be examined and rejected before it becomes real. Most business operations don’t work this way. A refund is either processed or it isn’t. An access grant is either active or it isn’t. The action is binary, idea to done with nothing in between.

Creating draft states means building intermediate representations into your processes. A proposed refund that exists as an object in your system, with all the relevant data attached, waiting for approval. A proposed access change that can be reviewed, modified, accepted, or rejected. The agent does the work—gathering information, making the decision, preparing the output—but stops before the point of no return. You get most of the speed benefit without crossing the threshold into irreversibility.

The second mechanism is preview—the ability to see exactly what a change will do before it happens. Software engineering has diffs: before any change commits, you can see precisely which lines changed, what the old version said, what the new version says. This visibility is what makes code review meaningful. A reviewer can quickly scan what’s different rather than having to re-examine everything from scratch.

Business operations rarely have this clarity. When pricing gets updated, can you see exactly which products changed by how much? When customer records get modified, can you see what was there before? When permissions get granted, can you see what access is being added relative to what already existed? Usually the answer is no. Changes happen and you discover what changed by examining the result, or by waiting for someone to notice a problem. Creating previews means generating human-readable summaries of what will change—which records, which amounts, which permissions, what the before and after look like. The technical implementation varies, but the principle is consistent: no blind writes.

The third mechanism is time windows—manufacturing reversibility by introducing delay. Many actions feel irreversible because they become final instantly, but that instantaneity is a design choice rather than a constraint. Amazon, for example, deliberately delays order processing for about thirty minutes after you place an order. They could pick and ship immediately. Instead, they wait, giving you a window to cancel without consequence. What could be a one-way door becomes, for a brief period, a two-way door.

The same principle applies broadly. Customer communications can be queued with a recall window rather than sent immediately. Refunds can be held in a pending state before funds actually move. Access grants can be time-limited by default, expiring automatically unless explicitly renewed. You’re not preventing the action—you’re creating a buffer during which mistakes can be caught and corrected before they become permanent.

The fourth mechanism is what I’d call compensation contracts—formalized procedures for what to do when something can’t be undone. Perfect rollback is rare outside software. You can’t unsend an email that’s been read, or un-download data that’s been exfiltrated, or un-make a promise that’s been reported. Some one-way doors are genuinely one-way.

But even when you can’t undo, you can often compensate. Distributed systems have a pattern called Saga where multi-step workflows define compensating actions at each stage—if step three fails, here’s how to reverse step two, here’s how to reverse step one. There’s a pivot point past which only forward recovery is possible, but before that point, there’s a documented path back.

Translating this to business operations means writing down, in advance, what happens when things go wrong. If the wrong vendor gets onboarded, what are the specific steps? Disable the account, reverse any purchase orders, flag payments in process, notify the relevant teams. Who owns executing that sequence, and in what timeframe? Making this explicit—documenting it, assigning ownership, establishing expectations—is what turns improvised scrambling into predictable recovery.

The fifth mechanism is durable logging—a queryable history of what happened. In software, the commit log and the observability stack mean you can reconstruct what changed, when, and why. You can trace a bug back to the deployment that introduced it. You can see patterns in what kinds of changes cause problems. Six months later, you can still explain why a particular decision was made.

Business operations often lack this. Information about past decisions lives in scattered email threads, Slack messages, and memories. When something goes wrong, reconstructing what happened and why can take longer than fixing the problem itself. Durable logging means every agent action leaves a record: what it was trying to do, what information it used, what it changed, who (if anyone) approved. Not bureaucracy for its own sake—infrastructure for accountability and learning.

None of these mechanisms are technically exotic. The challenge is that they have to be built into systems that weren’t designed with them in mind, by organizations whose operational muscles were developed in an era when human slowness made them unnecessary.


## **What Should Be Reversible?**

Here’s where the story gets large enough to be uncomfortable.

For most of history, the question of what should be reversible versus what should be permanent was answered by default. Things were reversible if reversing them was easy—which usually meant they were small or informal or hadn’t yet been communicated outside a small group. Things were permanent once they crossed some threshold of formality or visibility or commitment, because at that point reversing them required more coordination than anyone could muster.

This wasn’t really a choice. It was just how the world worked given the constraints. Coordination was expensive, formal processes were slow, and human attention was limited. The allocation of reversibility to irreversibility emerged from these constraints rather than from any deliberate consideration of what the allocation should be.

Agents change the constraints. Machine speed means coordination costs drop. Automated processes mean formality isn’t necessarily slow. The question of what should be reversible—which has always existed but could mostly be ignored—now forces itself forward. If you can build reversibility infrastructure, the question of whether you should build it becomes live.

Some irreversibility is clearly essential. Contracts need to bind or they don’t mean anything. Transactions need to settle or commerce doesn’t work. Credentials need to be permanent or they lose their signaling value. There are domains where the whole point is that you can’t take it back—where irreversibility is a feature because it creates trust, deters fraud, and makes promises meaningful.

But much irreversibility is less defensible. It’s not that anyone designed it that way; it’s that no one designed it at all. Legacy processes that accumulated because changing them was hard. Paper-era institutions that digitized their forms without rethinking their assumptions. Coordination problems that were solved by just not coordinating.

Consider, for example, test scores. A student takes a test, does badly, and the score goes on their record. If they study more and take the test again, maybe the new score replaces the old one, maybe it doesn’t. The irreversibility of the original score isn’t really serving anyone—it’s not like the student’s ability at the moment of the first test is the thing anyone cares about. What matters is whether they can demonstrate mastery. But making test scores more reversible would require changing systems and policies and norms, and so mostly it doesn’t happen.

Or consider access decisions. Someone loses access to a system because of a policy change or an administrative error. Restoring that access involves tickets and approvals and delays, even when everyone agrees it should be restored. The irreversibility isn’t protecting anything valuable; it’s just friction that nobody built the infrastructure to eliminate.

The agent era forces attention to all of this because agents expose the costs of irreversibility that were previously hidden by human slowness. When an agent encounters a one-way door, it either has to stop (and ask a human) or risk making a mistake that can’t be fixed. The more one-way doors exist in a process, the more points where agent autonomy breaks down. If you want agents to do real work, you have to either accept a lot of stopping points or make the terrain more navigable—which means grappling with questions about reversibility that organizations have historically been able to ignore.


## **The Terrain Ahead**

I’ve been arguing that the path to agent autonomy runs through reversibility—that the real bottleneck isn’t intelligence but the absence of infrastructure that makes mistakes survivable. If that’s true, the implications extend beyond any particular organization’s automation roadmap.

Software engineering is a worked example of what happens when a domain invests heavily in reversibility. The investment took decades. It was driven by pain—by outages and lost work and catastrophic deployments that convinced people the old ways weren’t sustainable. The result is an environment where agents can operate relatively freely, because the environment was designed to make change safe.

Other domains don’t have that history. They have their own tooling and their own practices, evolved under different pressures. The question is how much of the reversibility infrastructure that software built is portable, and what it takes to port it.

Some things are probably easier than they look. Draft states are a design pattern; implementing them doesn’t require new technology, just willingness to add intermediate representations to existing processes. Time windows are mostly configuration—deciding that this action should have a delay before it becomes final, and building the UI to make that delay visible. Logging is a solved problem technically; the challenge is organizational, convincing people that the effort is worth it.

Other things are probably harder. Compensation contracts require thinking through failure modes in advance, which organizations are often reluctant to do. It feels like tempting fate, or like admitting that mistakes will happen. Preview systems require surfacing information that may be buried in databases or scattered across services. And cultural changes—shifting from “mistakes are failures” to “mistakes are expected and what matters is recovery”—can take longer than any technical implementation.

The organizations that move fastest will likely be those with the most control over their own systems. Back-office operations—finance, HR, procurement, IT—happen inside the enterprise boundary, in systems the organization owns and can modify. Adding draft states to an internal approval workflow is tractable in a way that adding draft states to a vendor’s API is not. This is probably why early real-world agent deployments are concentrated in these areas: not because they’re the most valuable applications, but because they’re the most controllable.

The harder cases involve actions that cross organizational boundaries—where your agent needs to interact with systems you don’t control, where reversibility depends on cooperation from counterparties with their own interests. An agent that could genuinely execute a procurement process end-to-end would need more than internal infrastructure. It would need vendors to support holds and cancellation windows and machine-readable contracts. It would need shared standards for how reversibility works across boundaries. That’s a coordination problem of a different order.

There’s a version of the future where this coordination happens—where markets and institutions gradually adopt the primitives that make agent commerce possible, driven by competitive pressure or regulatory mandate or just the accumulated weight of demand. And there’s a version where it doesn’t, where agents remain powerful tools within bounded contexts but the cross-boundary cases stay stubbornly manual.

Probably reality will be uneven, with some domains moving faster than others depending on how much pain the current irreversibility is causing and how concentrated the power is to change things. Financial services, where the cost of errors is high and the regulatory apparatus is already oriented toward risk management, might develop compensation infrastructure faster than, say, education, where decisions about students are dispersed across thousands of institutions with limited incentive to coordinate.

What seems clear is that the constraint isn’t going away. Agents will keep getting more capable. The pressure to deploy them will keep increasing. And every deployment will run into the same question: what happens when something goes wrong? Organizations that have good answers will be able to push agents further into production. Organizations that don’t will keep hitting the same wall, watching demos that seem magical and wondering why their own deployments feel so limited.

The answer isn’t a mystery. It’s just infrastructure—unglamorous, detail-oriented work to make mistakes survivable. The same work that software engineering did, compressed into a shorter timeframe and adapted to domains that work differently.

The agents are ready. The question is whether the terrain is.

[![](https://substackcdn.com/image/fetch/$s_!bHTp!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4b459a2-b8f3-4286-a347-28db5b505c01_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!bHTp!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4b459a2-b8f3-4286-a347-28db5b505c01_1024x1024.png)
