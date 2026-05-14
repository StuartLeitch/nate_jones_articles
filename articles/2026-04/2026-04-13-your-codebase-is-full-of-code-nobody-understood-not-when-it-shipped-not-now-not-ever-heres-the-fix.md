---
title: "Your codebase is full of code nobody understood — not when it shipped, not now, not ever. Here's the fix."
author: "Nate Jones"
published: 2026-04-13
url: https://natesnewsletter.substack.com/p/your-codebase-is-full-of-code-nobody
audience: everyone
scraped_at: 2026-05-14 14:33:42
---

There is code running in production right now, at companies you use every day, that nobody can explain. Not the engineer who shipped it, not the team that owns the service, not even the CTO who signed off on the architecture three years ago. The code works — it passes tests, clears CI, deploys without incident — and no human on the payroll fully understands what it does, why it does it, or what would happen if it did something else.

The industry is starting to call this **dark code**, and the name is more precise than it sounds. This isn’t buggy code or spaghetti code or the kind of technical debt that accumulates when teams move too fast. Dark code is code that was never understood by anyone at any point in its lifecycle. It was generated, it passed automated checks, and it shipped — but the comprehension step never happened. Nobody was careless. The process simply no longer requires comprehension.

If that sounds abstract, look at Amazon. They mandated AI coding tools with an 80% weekly-usage target, tracked as a corporate OKR. They laid off 16,000 people in January 2026. Then the AI broke production — thirteen hours of downtime when Kiro, their internal coding assistant, reportedly decided the correct fix for a routine bug was to delete an entire production environment and rebuild from scratch. Amazon’s response was to require senior-engineer sign-offs on AI-assisted changes, which would be reassuring if they hadn’t just eliminated the senior engineers. That loop — mandate the AI, fire the humans, discover you still need the humans, realize they’re gone — is not unique to Amazon.

Here’s what’s inside:

- **How comprehension decoupled from authorship** — two structural breaks created dark code, and the Amazon disaster is a preview, not an outlier
- **Why observability, guardrails, and added layers all make it worse** — and why the EU AI Act deadline in August 2026 means the window to get ahead of this is measured in months, not years
- **Three layers you can build today** — spec-driven development, context engineering, and comprehension gates, each concrete enough to start deploying this quarter
- **The prompts** **and the Repo Learning Coach** — a dark code audit for your system, a context layer generator for your highest-risk modules, and a comprehension gate you can run on every PR starting today

Speed without comprehension isn’t a competitive advantage. It’s a countdown.


## LINKS: Grab the [Repo Learning Coach](https://github.com/NateBJones-Projects/OB1/tree/cd349a57cd7111c889e222f7d04fd47d433b9f48/recipes/repo-learning-coach) and the [prompts](https://promptkit.natebjones.com/20260402_795_promptkit_1)

Dark code accumulates because nobody is forced to understand what shipped. The Repo Learning Coach and the three prompts below are built to change that — from opposite ends of the problem.

The **[Repo Learning Coach](https://github.com/NateBJones-Projects/OB1/tree/cd349a57cd7111c889e222f7d04fd47d433b9f48/recipes/repo-learning-coach)** is a new OB1 recipe that transforms repo documentation and research into a guided local learning app. It uses markdown files for lessons and source content, Supabase tables for structured progress and quiz data, and a narrow Open Brain bridge to save durable takeaways back into your thoughts for future retrieval. The result is a repeatable way to onboard yourself or your team into a codebase without touching the core OB1 memory model. It’s seeded in the Open Brain repo so you can see it working — and use it to onboard yourself into the codebase while you’re at it.

The **[prompts](https://promptkit.natebjones.com/20260402_795_promptkit_1)** work the other side of the problem — the code that’s already shipped and the code that’s about to. The Dark Code Audit maps where comprehension has already gone missing across your architecture. The Context Layer Generator builds the structural manifests, behavioral contracts, and decision logs that make a single module self-describing. The Comprehension Gate catches what’s about to ship: paste a diff before merging and it reads for blast radius, cross-service data leaks, credentials in context, tokens with no expiration — the exact failure patterns behind the cross-tenant cache exposure and the Kiro environment deletion.

Install the Repo Learning Coach on whatever repo keeps you up at night, run the audit, generate context layers for your two riskiest modules, and gate your next AI-generated PR. That’s this afternoon.


## The problem


### How comprehension decoupled from authorship

For most of the history of software, writing code and understanding code were the same activity. Not because engineers were disciplined — because writing was slow enough that you had to hold the system in your head as you built it. Authorship and comprehension were coupled by the physics of the process.

That coupling has broken, and it broke from two directions at once.

**The first break is structural.** Agents now select tools at runtime. Execution paths assemble themselves, run, and disappear. Natural language is increasingly the control plane, and the mapping from intent to action is lossy and context-dependent in ways that traditional APIs never were. When one agent calls another, there often isn’t a strict schema — just a prompt being interpreted by a model. The behavior was never designed by anyone. It emerged.

Consider an incident a VC in our portfolio space described recently: a non-technical employee connected a customer data API to a reporting pipeline. An agent in the middle selected steps at runtime. One of those steps cached results where another service could read them. Customer data from one tenant showed up in another tenant’s dashboard. Every individual service stayed within its permissions. Nothing was misconfigured. The path only existed at runtime, assembled by an agent that no longer existed by the time anyone went looking. The security team couldn’t answer “who did this” — there was a workflow, an agent, a chain of tools, but no coherent trail and no single actor to attribute it to.

That’s structural dark code. Behavior nobody authored and nobody can fully explain.

**The second break is velocity.** Code is produced so fast that understanding never catches up. Tests pass, diffs look clean, everything ships — but there was never a moment when anyone held the system in their head. This is the Amazon story.

You saw the December headlines. But the story didn’t stop there. By March 2026, the retail website itself was breaking — a six-hour outage crippled checkout, pricing, and account access. Amazon acknowledged multiple outages and that AI tools were involved in at least one. Internal documents obtained by CNBC show the company implemented mandatory senior-engineer sign-offs for AI-assisted production changes, though Amazon publicly denied introducing new restrictions. SVP Dave Treadwell’s email to the org: “Folks, as you likely know, the availability of the site and related infrastructure has not been good recently.”

They fired the humans, mandated the AI, the AI broke production, and the fix was to require human oversight. But the humans were gone.

**What matters: these two breaks compound.** Structural dark code gives you runtime behavior nobody designed. Velocity dark code gives you authored code nobody understood. Together, you get systems where *neither* the designed *nor* the emergent behavior is comprehensible to any human in the organization. That’s not a failure mode. That’s the default state of every company shipping with AI tools right now.


## Why the obvious responses won’t work

The temptation is to treat dark code as a tooling problem — buy better observability, add more guardrails, monitor harder. This misses the nature of the problem at every level.


### Observability isn’t comprehension.

You can instrument every service in your stack and still not understand your system. Observability tells you what happened. Comprehension tells you *why it could happen* and *what else could happen next.* A distributed trace of an agent-assembled execution path gives you a longer log file. It doesn’t give you understanding. You can have perfect telemetry — every trace, every metric, every log — and still not be able to explain what your system does, because understanding lives at a different level of abstraction than data.


### Adding layers makes it worse.

Companies will respond to dark code the way they always respond to unmanageable complexity: they’ll add a layer. Orchestration platforms to coordinate agents. Guardrail services to constrain agent behavior. Supervisory agents to monitor other agents. I’ve written about the middleware trap before. This is the same trap wearing a security hat. Every layer you add to manage dark code complexity is itself a source of dark code complexity. The supervisory agent is making its own runtime decisions, producing its own emergent behavior. You haven’t reduced the comprehension gap. You’ve moved it up a level and made it harder to see.

Amazon’s internal response reportedly includes “both deterministic and agentic safeguards.” An AI supervising the AI. That’s a recursion that doesn’t terminate.


### The org chart no longer maps to the system.

In traditional software, Team A owns Service A. There’s an on-call rotation. If it breaks, you know whose problem it is. In a dark code system, that mapping dissolves. The PM who wired an agent to production data didn’t tell the platform team. The marketing person who connected tools through an agent workflow didn’t file a ticket. The agent that assembled a runtime path doesn’t appear in any service registry. There’s behavior in production that belongs to no team, no owner, no on-call rotation — because it emerged from the interaction of components that individually belong to different teams but were never explicitly wired together. This isn’t a logging problem. It’s a missing organizational function — ownership of emergent behavior that no team explicitly created.


### AI’s strengths mask its weaknesses here.

The jagged frontier — the irregular boundary between what AI does brilliantly and what it does terribly — applies directly to your infrastructure. AI is excellent at producing locally coherent, syntactically correct code. It is terrible at understanding what that code means in the context of the whole system. It doesn’t know that caching results in a shared location creates a cross-tenant exposure. It doesn’t know that deleting and recreating an environment is catastrophically different from patching a bug. These require system-level judgment, the exact zone where AI is weakest.

The dangerous part: code that looks good and passes automated checks creates a false signal of comprehension. Everyone treats it as understood, because it *looks* like understood code. But nobody held it in their head. The appearance of understanding substitutes for the reality of it. And unlike old technical debt — where the engineer who rushed still carried latent knowledge — dark code carries no latent knowledge at all. The comprehension gap isn’t deferred. It never existed.


### The talent market is compounding the problem.

The industry is simultaneously creating more dark code than ever, laying off the mid-level and senior engineers who would understand it, and refusing to hire juniors who would learn it. That’s a structural market failure with a predictable correction: incidents, lawsuits, and regulatory action.


### This is already a board-level problem.

Procurement questionnaires still ask about SOC 2 and encryption at rest — questions designed for a world where you could enumerate what your software does. The questions that actually matter are different: can you explain what your agents are doing in production? Can you trace a decision back to an actor? Do you know what your system *actually did* last Tuesday?

These aren’t on the questionnaire yet. The EU AI Act enforcement deadline is August 2026, and it changes that. The Act requires human oversight mechanisms, logging of AI decisions, and mandatory human-in-the-loop for consequential actions. GDPR gives customers the right to know how their data is processed — and dark code means the company itself may not know, because the processing path was assembled at runtime by an agent that no longer exists. The first cross-tenant data exposure that makes the wrong headline won’t be judged on whether the company had good intentions. It will be judged on whether they could explain what their system actually did.


## What actually helps

Dark code is what happens when comprehension decouples from authorship. The fix is to recouple them — to force comprehension back into the process at every stage. Not after deployment. Not as a quarterly audit. As infrastructure that’s inseparable from how code gets written and shipped.

I’ve been thinking about why the standard fixes keep failing, and it comes down to a timing problem. Observability is retrospective. Guardrails are reactive. The comprehension has to happen *before* the code exists, not after it breaks.

I’ve been building toward this for the past year. Three layers, each concrete, each buildable today.


### Layer 1: Force understanding before code exists.

I call this spec-driven development. It inverts the normal workflow: instead of writing code and then (maybe) documenting it, you write a requirements doc, then a design doc, then a task decomposition, and only then does code get generated. Each phase produces a reviewable artifact. AI assists with implementation, but architecture and intent are human decisions captured in writing before a single line ships.

The spec is the comprehension artifact. If you can’t write a clear spec, you don’t understand what you’re building — and you certainly don’t understand it well enough to let an AI build it for you. The spec forces the understanding to happen.

The AGENTS.md file — or CLAUDE.md, or whatever your team calls the project-level context file — operationalizes this. It’s a machine-readable document that defines tech stack, coding standards, architectural constraints, and behavioral rules. It’s not documentation. It’s a control surface. It encodes human judgment into a form that constrains AI behavior.

One detail worth noting: Kiro already featured “spec-driven development” from its July 2025 launch — turning prompts into requirements, designs, and task lists before code gets generated. But the December outage showed that structured development methodology wasn’t enough on its own. What Amazon actually changed afterward was the deployment pipeline: mandatory peer review for production access, senior-engineer sign-offs, and a safety reset across critical systems. When the company that learned this lesson the hardest responds by tightening the human oversight layer, that tells you where the industry is heading.


### Layer 2: Make systems self-describing.

Spec-driven development handles new code. But what about the codebase that already exists — the code that’s already dark?

Context engineering is the practice of restructuring your codebase so comprehension is embedded in the code itself, not locked in the heads of people who’ve moved on.

I’ve been developing a three-layer model.

**Structural context** answers *where* — every module has a manifest describing what it does, what it depends on, and what depends on it.

**Semantic context** answers *what* — interfaces aren’t just type signatures but behavioral contracts specifying idempotency guarantees, performance expectations, failure modes, retry semantics. When AI reads an interface, it knows the rules of engagement, not just the shape of the data.

**Philosophical context** answers *why* — decision logs at the module level capture reasoning behind architectural choices. Why this data structure? Why this caching strategy? These prevent an AI from “fixing” something by undoing a deliberate design decision — which is exactly what Kiro did when it decided to delete and recreate that environment. If the decision log had said “this environment has persistent state that cannot be recreated from scratch,” the story would be different.

Together, these layers make a codebase self-describing. A new engineer or an AI agent can read the context and understand not just what the code does, but why it does it that way and what would break if you changed it. That’s the opposite of dark code.


### Layer 3: Catch what the first two miss.

Before anything ships, a comprehension gate reads the diff — not for syntax or test coverage, but for understanding. It asks the questions a careful senior engineer would ask but that nobody has time to ask across every PR at AI speed:

“Did you know you wrote the API key in plain text?” — not a regex match, but a contextual read that recognizes a variable being used as a credential and stored in version control. “This caches results in a location readable by other services” — the exact failure mode from the cross-tenant incident, invisible in any individual service review because each looks correct in isolation. “There’s no TTL on this token” — how ephemeral agents leave permanent security holes. “If this fails, what else breaks?” — blast radius mapping that traces the dependency graph forward before code ships, not after it’s in production.

Not pass/fail. A comprehension artifact. Something that ensures at least one person or system understood the implications before the code went live.


## What this means for you

Everyone building software owns this problem.

If you’re leading an engineering org, the question to ask yourself isn’t “do we have good observability?” It’s “could my team explain what our system actually did with a customer’s data on a specific day?” If the answer is no — and for most orgs right now, the honest answer is no — that’s the gap to close, and closing it requires treating comprehension as infrastructure, not overhead. Spec-driven development, context engineering, and comprehension gates aren’t slowing you down. They’re the prerequisite for deploying AI aggressively enough to actually get the speed advantage everyone’s chasing.

If you’re a founder, this is your competitive moat and your existential risk simultaneously. The company that can answer “what did your system do last Tuesday?” wins the enterprise deal. The company that can’t answer it loses the customer after the first incident — and in a world of dark code, the first incident is a matter of when, not if.

If you’re entering this field and wondering where you fit — the paradox of “everyone wants AI, nobody wants juniors” — understand that the paradox is about to flip. Dark code means every company on earth is accumulating systems that grow faster than anyone’s ability to understand them. The discipline of making those systems legible is still forming. But so was DevOps in 2008, and it was the most in-demand role by 2015. So was SRE before Google named it. The systems just got complex enough to demand this next discipline. The people building the skills now will define what it looks like.

And if you’re a senior engineer or architect — your team produces dark code too, even with careful reviews and strong test coverage. The question worth asking: if a regulator walked in tomorrow and asked your team to explain what your system did with a specific customer’s data on a specific day, could you answer? If not, that’s the project. Start with the context layer — decision logs, behavioral contracts, module manifests. It’s the highest-leverage first move because it makes everything else (specs, gates, agent constraints) possible.


## Build the infrastructure to know

Nobody is slowing down. The pressure to ship before you fully understand what you’ve built isn’t going away, and pretending otherwise is its own kind of dark code — a comforting story nobody examined too closely.

But there’s a difference between moving fast and being unable to explain what your system did with a customer’s data last week. The first is a competitive choice. The second is a liability that compounds silently until someone asks the question you can’t answer — a customer, a regulator, opposing counsel.

The frameworks in this article exist because that question is coming. Spec-driven development, context engineering, comprehension gates — none of them slow you down. They’re what make it possible to deploy AI aggressively without building systems that outrun your ability to understand them.

The strange thing is, the companies that build this infrastructure won’t just be more defensible. They’ll actually be faster.

It turns out that trust is a prerequisite for speed, not a tax on it.

[![](https://substackcdn.com/image/fetch/$s_!SzLu!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F83cc3875-01b0-4f74-b2b7-02dcad8dae3c_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!SzLu!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F83cc3875-01b0-4f74-b2b7-02dcad8dae3c_1024x1024.png)
