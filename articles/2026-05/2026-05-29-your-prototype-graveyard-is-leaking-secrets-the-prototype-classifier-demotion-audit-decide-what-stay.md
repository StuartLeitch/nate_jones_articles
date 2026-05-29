---
title: "Your prototype graveyard is leaking secrets. The Prototype Classifier + Demotion Audit decide what stays"
author: "Nate Jones"
published: 2026-05-29
url: https://natesnewsletter.substack.com/p/product-management-cheap-software-governance
subtitle: "Watch now | PMs used to ration engineering. Now they have to classify abundance."
audience: everyone
scraped_at: 2026-05-29 12:00:17
---

Product management has always been a rationing job. Most ideas would not get built. Engineering time was scarce. Coordination was slow. A roadmap was partly a strategy document and partly a rationing system, and product managers helped decide which customer problems, executive priorities, technical constraints, and market bets deserved the company’s limited ability to make software.

That role is changing, because the cost of a first version has collapsed. The thing entering the product conversation is no longer a request. It is a working artifact. A dashboard. A lightweight app. An agent that already touches a system of record.

The scale this reaches is already documented. Inside Microsoft, employees have built more than 1 million Power Platform citizen-development assets: 18,000-plus environments, 170,000 apps, 50,000 automated flows, 1,200 chatbots. Most companies are nowhere near that, but the shape of the problem is arriving everywhere, and the product function is the part of the org that has to absorb it.

The old model asked, “Should we build this?” The new model starts one step later: somebody already built something. Now the company has to decide whether it should matter. The PM is no longer mainly a coordination role around scarce engineering. It becomes the discipline that classifies software abundance into market value, internal reliance, or deletion. That is a more strategic job, and a more technical one. Get it wrong and the failure is not loud. You do not get an outage on launch day. You get a pile of half-real tools nobody owns, spreading into systems of record before anyone decided they were allowed to.

**Here’s what’s inside:**

- **Why the old roadmap filter broke.** When a first version costs almost nothing, rationing engineering time stops being the job. You get a clear read on what replaces it, and why the shift is more strategic than the prototyping conversation suggests.
- **A four-state ladder for classifying what your team builds.** Personal tool, team beta, supported internal product, customer-facing product, with the specific user-count and risk thresholds that move a tool from one rung to the next.
- **The demotion triggers almost everyone skips.** The exact signals that tell you a tool you still support has stopped earning it, so you stop paying to keep dead software alive.
- **Two prompts you can run this week.** One classifies any employee-built tool into its real production class and names what promotion would take. The other audits a tool you already support and tests whether it should be demoted.

The cost of making software fell. The cost of being wrong about what you depend on did not. Below, here is how the product job changes when production stops being the scarce input, and the two prompts that turn it into something you can run on Monday.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260518_265_promptkit_1)

Companies almost always know how to promote tools. They rarely know how to demote them. Something useful appears, earns a rung, and keeps it forever, until the supported-tools list becomes a museum of things nobody remembers depending on. These two prompts run in both directions on purpose. The Prototype Classifier takes one tool you can point at and tells you what it is right now, what moving up would take, and the one thing that breaks downstream if it disappears. The Demotion Audit asks the question the up direction never does: is this still worth what we pay to keep it alive? Bring real facts to both. Neither prompt will guess on your behalf, because the whole value is surfacing what you haven’t written down yet.


## The old PM job was built around scarcity

Product rituals make sense when software is expensive.

PRDs, roadmap reviews, planning cycles, launch checklists, prioritization meetings, and intake processes all slow work down before engineering time gets consumed. The friction was the design, not a flaw in it.

When software is expensive, the company needs a filter. You cannot afford every stray idea to become a ticket. You cannot afford every department to clone the product. You cannot afford every half-understood customer request to ship.

The PM helped run that filter.

AI weakens the filter because it changes what people can produce before they reach product and engineering. The top of the funnel used to be words, mockups, spreadsheets, and persuasion. Now it includes working tools, dashboards, automations, agents, and half-real products.

A product leader can no longer wait passively for polished business cases. The useful signal may already be running inside a team. A prototype may reveal hidden demand before the market research does. A local automation may expose a platform gap. A messy agent may show that customers want an outcome the official product does not support.

The PM’s job is to understand that signal, not suppress it.

The company needs broad building because that is where new demand becomes visible. But broad building without judgment becomes sprawl. Useful work stays hidden, risky work spreads without support, and nobody knows which tools the business now depends on.

The product function has to hold both ideas at the same time: let more people build, and decide what the business will rely on.


## The supply curve moved

The public software ecosystem shows the direction of travel. GitHub’s 2025 Octoverse counted 630 million total projects and 4.3 million AI-specific projects. Most of those projects will never matter to anyone beyond the person who made them. That is what abundance looks like.

The world is producing more software-shaped work than product organizations were built to evaluate.

The same pattern is already inside companies. The Microsoft number from the open is worth sitting with for a second: 1 million citizen-development assets, documented as far back as 2023, governed through inventory, telemetry, permission review, environment controls, and data policy. The age of the figure is what should bother you. The problem was already this big before the current wave of AI building tools arrived, which means most companies are now racing to catch up to a curve that bent years ago.

Microsoft did not present this as a reason to stop employees from building. It used governance as the way to let employees build while protecting the company. That is the posture product leaders need. Broad building is good. Ungoverned reliance is not.

The security data shows what happens when posture is missing. GitGuardian’s 2026 State of Secrets Sprawl report says AI-service secrets exposed on public GitHub reached 1,275,105 in 2025, up 81 percent year over year. Faster creation means more credentials, more local workflows, more integrations, and more places for access to leak.

Product leaders inherit that problem when useful tools spread before anyone decides what class of thing they are.

So a useful prototype is only the start of the evaluation. What data does it touch, what systems can it write to, what happens when it fails, who owns it, how is it checked, and what is the company promising once other people start depending on it? These are product questions now, not engineering ones.


## PMs need more market judgment, not less

It is easy to hear all of this as an internal tooling problem. That would make the role too small.

Cheap software makes PMs more responsible for market judgment, not less.

When building is expensive, weak product thinking can hide behind execution constraints. A team can spend months building one thing and blame the cost of production for why it could not test more. When first versions get cheap, that excuse weakens.

The question becomes sharper: why are we building this at all?

The PM has to understand the market well enough to aim production.

Which customer problem is worth solving? Which workflow is close enough to money, retention, trust, or habit that it matters? Which competitor feature is noise? Which customer request is a symptom of a deeper problem? Which internal prototype reveals real demand, and which one is just a local convenience?

Those are product judgment calls, and most PMs were never trained to make them.

AI also makes the role more fluid. The line between product, design, engineering, data, research, and operations gets blurrier when a small team can move from customer insight to working prototype quickly. The PM has to move across that boundary without pretending the boundary disappeared.

They need enough technical fluency to understand what the system can do and enough market clarity to decide what the system should do. The PM becomes less of a translator between business and engineering and more of an accountable thinker about what should exist in a market where production is no longer the scarce input.


## The prototype commons needs stewardship

The prototype commons is the informal space where new tools appear before the company has classified them: scripts, dashboards, agents, automations, and half-real products built because employees can finally solve problems that never made it onto a roadmap.

That space is valuable. It reveals hidden demand, missing platform primitives, customer pain, and internal workflows that the official product process has not understood yet.

But a commons still needs stewardship.

If nobody owns it, useful work stays invisible and risky work spreads without the right support. If product shows up only to say no, employees will hide useful tools until something breaks. The right posture is open discovery: show us what you made, what problem it solves, who uses it, what data it touches, and what you learned.

Run a weekly prototype review. Keep it small. Product, platform or engineering, security or risk when data is involved, design or research when user experience matters, and the artifact owner.

Do not call it a steering committee. The name matters because the posture matters. A steering committee sounds like permission. A prototype review sounds like discovery.

The intake form should fit on one page.

What problem does this solve? Who uses it today, and how often? What systems, data, credentials, or customer surfaces does it touch? What happens if it gives a wrong answer, fails, or disappears? Who owns it today, and who is the backup? What evidence shows it is useful? What should happen next: stay personal, move to team beta, become supported internally, or enter product discovery?

Each review has three possible outcomes.

Leave it where it is, with maybe one small safety fix. Promote it one step. Or harvest the learning and retire it.

That last option matters. The goal is not to put every prototype on a roadmap. The goal is to learn from abundance without becoming dependent on everything abundance produces.


## The production-class ladder

Once a company accepts that more people will build, it needs a way to decide what each thing is.

The first version of a thing and the supported version of a thing are not the same object.

That sentence is the reason for a production-class ladder.

The first state is the personal tool. One person uses it. It can be scrappy. It can change every weekend. It should stay away from sensitive data unless the company has clear rules for local handling. The goal is learning and personal leverage.

The second state is the team beta. A small group uses it regularly. It solves a real problem, but it is not yet a formal internal product. It needs a named owner, a backup owner, a short description, a list of systems it touches, and a failure plan. If it touches credentials, customer data, money, compliance, or production infrastructure, it needs review before it spreads.

The third state is the supported internal product. This is software the company depends on. It needs product ownership, engineering or platform partnership, access management, monitoring, documentation, support, auditability, and a change process. The difference is obligation. People now expect the thing to work, and the company has to make sure it does.

The fourth state is the customer-facing product or feature. This is part of the company’s external promise. It needs the usual product standards plus AI-specific evaluation and governance where the surface requires it: model performance, data handling, fallback behavior, user control, support readiness, and policy compliance.

The thresholds will differ by company, but they need to exist. A useful first pass is simple: one primary user for a personal tool, three or more regular users for four weeks for a team beta, ten or more users or meaningful outage cost for a supported internal product, and any external user, revenue, contractual reliance, public documentation, or support commitment for a customer-facing product.

The ladder keeps building fast without pretending every useful thing deserves the same process.

In the old model, PMs decided what entered engineering. In the new model, PMs also decide what gets promoted out of the prototype commons.


## The strongest objection

The strongest counterargument is that the production-class ladder reintroduces the bottleneck the article is trying to escape.

If every employee-built tool has to pass through product review before a team can use it, then the company has rebuilt the old roadmap intake process under a new name. The artifact arrived early, but the organization still forces it to wait in line.

That objection is right if the ladder is default-deny. The point is to make it default-allow at the low-risk end and explicit only when the artifact creates broader obligation. A person should not need product approval to build a personal helper. A team should not need a roadmap slot to try a beta that touches low-risk data and has a named owner. The review does not decide whether employees may build. Its job is to notice when an artifact has started to matter enough that the company owes it a class, an owner, and a support path.

The old intake process controlled what got built. The new promotion process controls what becomes relied upon.

Those jobs are different.

The second objection is that promotion will be political. The artifacts built by the favored team will get support, while better artifacts from less powerful teams get ignored.

That can happen, and the mitigation is the written decision log. A single line is enough: owner, backup, next review date, the condition that would promote it, the condition that would demote it. Every promotion, denial, retirement, or request for more evidence leaves a record of users, usage, risks, systems touched, failure cost, owner, and reasoning. Politics survives that, but it has to argue with what the log says.


## Demotion matters

A ladder needs a way down. Without one, the company keeps paying to support tools it stopped using and forgot it had.

The ladder needs a downward direction.

A team beta should move back to personal tool if usage falls to one person, if the backup owner disappears, or if the original problem stops recurring. The tool may still be useful. The company should just stop pretending a team depends on it.

A supported internal product should move back to team beta if it loses its owner, falls out of the operating rhythm, or no longer justifies support. That demotion needs a notice period and a migration plan because people may have built work around it. The notice does not have to be elaborate: a date by which the thing stops being supported, posted where the people who use it will see it, with a named alternative or a clear statement that there is none.

A customer-facing feature should be sunset when the external promise no longer earns its maintenance cost.

Cheap creation should make product leaders more willing to retire weak things. Without disciplined demotion, the company accumulates product debt faster than it can name it.

This is where the ladder becomes more than a launch framework. It becomes a maintenance discipline. The promotion question is loud. The demotion question is the one almost nobody asks: is what you already support still in the class you put it in?


## The real PM shift

The product conversation has spent a lot of time on how fast AI can move an idea into a prototype. That was useful for a moment. It showed that the cost of first versions had collapsed.

The next question matters more.

What happens after the prototype exists?

Three answers fail. Doing nothing leaves a graveyard of demos. Sending everything to production produces chaos. Locking building to central product and engineering wastes the creative capacity AI just unlocked.

The better answer is a default-allow system for experimentation and a deliberate promotion path for work the business will rely on.

But the larger shift is upstream from the ladder.

Software abundance makes product judgment more important. PMs have to know the market better, understand the technical system more deeply, and form clearer opinions about what should exist. They have to see when a prototype is a local helper, when it reveals a real workflow, when it should become infrastructure, and when it should die.

The binding constraint moves from “can we make it?” to “should this exist, who is it for, what standard does it need to meet, and what are we willing to rely on?”

Engineering used to be the scarce thing. The scarce thing now is judgment. Look at what your team built last quarter. Some of it is already yours to own. The question is whether you know which.

[![](https://substackcdn.com/image/fetch/$s_!4266!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8d9990e4-359b-4c04-9bc8-8bbc4a2e124e_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!4266!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8d9990e4-359b-4c04-9bc8-8bbc4a2e124e_1024x1024.png)

##
