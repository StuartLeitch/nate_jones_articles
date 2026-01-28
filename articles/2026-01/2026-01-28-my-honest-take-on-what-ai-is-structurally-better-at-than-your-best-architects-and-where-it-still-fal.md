---
title: "My honest take on what AI is structurally better at than your best architects (and where it still falls short)"
author: "Nate Jones"
published: 2026-01-28
url: https://natesnewsletter.substack.com/p/my-honest-take-on-what-ai-is-structurally
subtitle: "Watch now | Even the best engineers (and marketers, and operators, and people doing HR or customer success) can only hold so much in their brains before things start to drift. Enter: AI-powered arc..."
audience: everyone
scraped_at: 2026-01-28 12:00:18
---

AI might be better at software architecture than humans.

Not because AI is smarter. Because humans are structurally incapable of the kind of vigilance that architecture actually requires.

That’s a strong claim, and it cuts against everything we’ve been told. The conventional wisdom is clear: AI is bad at architecture because architecture requires holistic thinking, creative judgment, wisdom accumulated over years. Architecture is supposedly the last bastion of human engineering—the domain where experience and intuition matter most.

But when engineers describe their architectural failures—the performance that degraded over months, the caching layer that silently broke, the technical debt that somehow accumulated despite everyone’s best intentions—the root cause is almost never bad judgment. It’s lost context. The information needed to prevent the problem existed. It was just spread across too many files, too many people, too many moments in time. No single human held it all in mind at once.

The original architectures were usually fine. The engineers were competent. The code reviews were thorough. But somewhere between the initial design and the daily reality of shipping features, the systems quietly rotted from the inside. Each individual change made sense. Each passed review. Each solved the problem it was meant to solve. And together, they created messes that no single person could see forming.

This is the story of most architectural failures. Not dramatic collapses, but slow rot. Not bad engineers, but good engineers operating under cognitive constraints that make certain failures inevitable.

What if we’ve been thinking about this backwards? What if there are specific dimensions of architectural work where AI isn’t just adequate—but structurally superior to humans? Not because of intelligence, but because of attention span, memory, and the ability to hold an entire codebase in mind while evaluating a single line change?

**Here’s what’s inside:**

- **The entropy diagnosis** — Why most architectural failures aren’t about bad engineers, but about context that accumulates faster than any human can track.
- **Where AI has structural advantage** — The specific domains where holding more context and applying rules consistently makes AI better than humans at the job: security review, API consistency, accessibility, compliance, infrastructure drift.
- **Where AI falls short** — Novel design, business trade-offs, cross-system politics, and knowing when good enough is good enough—the work that remains irreducibly human.
- **The failure modes** — Ossification, deskilling, gaming the system: what goes wrong when organizations automate enforcement without designing for it.
- **A framework for any domain** — How to apply this thinking to product, marketing, customer success, and operations—anywhere principles drift because the context can’t be held at decision time.

The implications go beyond “use AI for code review.” They touch hiring, team structure, how we document systems, and what it means to be an architect when pattern enforcement is automated. Let’s get into it.


## [Grab the Prompts](https://www.notion.so/product-templates/The-Anti-Entropy-Cathedral-Prompt-Kit-2f35a2ccb526809bb06fe8f0c06ca23b?source=copy_link)

The article makes the case that most quality problems aren’t people problems—they’re context problems, and humans structurally can’t hold enough context to catch drift through vigilance alone. These 8 prompts operationalize that insight.

The first half builds your enforcement infrastructure: diagnose where things keep breaking, turn those patterns into checkable rules, design the exception system so rules don’t become bottlenecks, and train people on the why so they don’t just follow blindly.

The second half gives you ongoing tools: weekly drift reports that force decisions instead of generating dashboards, pre-ship checks that surface downstream effects you’d otherwise miss, people-dependency audits that find where tacit knowledge is load-bearing, and a decision memo for the judgment calls that rules can’t make.

You don’t need all of them—grab the one that solves today’s problem. But if you’re tired of watching the same failures repeat despite good intentions, the full sequence builds a system that fights entropy without depending on attention that humans can’t sustain.


## **Why This Matters Beyond Engineering**

I’m going to spend a lot of time in the technical weeds here, but I want to be clear about why this conversation matters if you’re not an engineer.

The framework I’m developing—AI excels where tasks require holding more context than humans can manage, applying rules consistently at scale, and catching deviations from patterns—is not specific to software. It’s a general framework for thinking about human-AI complementarity in any domain.

Product teams have principles about how features should work, how user flows should be designed, how edge cases should be handled. Those principles get violated constantly, not because product managers are careless, but because the surface area is too large and the context is too distributed. The same entropy that degrades codebases degrades product consistency.

Marketing teams have brand guidelines, messaging frameworks, voice and tone standards. Those standards drift. Every individual piece of content makes sense in isolation. Over time, the brand fragments. The information needed to maintain consistency exists—it’s just not held in any single mind at the moment of creation.

Customer success teams have playbooks for handling different scenarios, escalation procedures, knowledge about what’s worked before. That institutional knowledge degrades as people leave. New reps make mistakes that veterans would have caught, not because they’re less capable, but because the context wasn’t transferred.

Operations teams have procedures, compliance requirements, quality standards. Those get violated in the gaps between documented process and daily reality.

The question I’m exploring in the technical domain—where do humans have structural cognitive limitations that AI can address?—is the question every department needs to ask in 2026. The specific answers will differ. The framework is the same.

So if you’re not technical, read this as a case study in how to think about this problem. Where in your domain do you have agreed-upon principles that don’t get followed? Where does context get lost? Where does institutional knowledge decay? Where do reasonable local decisions add up to systemic problems? Those are the places where AI enforcement might help—and where you need to think carefully about what remains uniquely human.

Now, into the technical details.


## **The Entropy Problem**

Shu Ding has spent seven years at Vercel doing performance work—opening roughly 400 pull requests focused on performance, about 1 in every 10 he’s submitted. Waterfalls eliminated. Bundle sizes cut. Cache keys fixed. Re-renders removed. The same categories of problems, appearing again and again.

He recently wrote something that crystallized the problem: “These are not technical problems. The same mistakes kept appearing. Different engineers. Different codebases. Different times. We have faster frameworks. Better compilers. Smarter linters. Performance still degrades.”

His diagnosis: entropy. Not a technical problem you can patch. A systemic problem that emerges from a fundamental mismatch between human cognitive architecture and the scale of modern software systems.

The argument goes like this. Every engineer—no matter how experienced—can only hold so much in their head. Modern codebases grow exponentially: dependencies, state machines, async flows, caching layers. The codebase grows faster than any individual can track. Engineers shift focus between features. Context fades. As the team scales, knowledge becomes distributed and diluted.

His framing: “You cannot hold the design of the cathedral in your head while laying a single brick.”

We tell ourselves a comforting lie: that if engineers “pay attention” and “write better code,” the application will stay fast, secure, maintainable. It doesn’t work. Not because engineers are careless, but because the system allows degradation. Entropy wins not through malice or incompetence, but through the accumulation of reasonable local decisions that nobody could see adding up to systemic problems.


## **Making It Concrete**

What does entropy look like in practice? Here are examples from production codebases, written by experienced engineers.

**Abstraction conceals cost.** A reusable popup component that looks perfectly clean. It adds a listener to detect when users click outside the popup—a standard UX pattern. But each instance adds its own listener. If you have 100 popup instances across your application—which isn’t unusual in a complex UI—that’s 100 functions firing on every single click anywhere in the document. The technical fix is easy: deduplicate listeners. The systemic problem is harder. Nothing in the codebase prevents this pattern from spreading. The engineer reusing the component has no way to know the cost until users complain about sluggish performance in production. The information needed to make a better decision exists—it’s just invisible at the point where decisions are made.

**Fragile abstraction.** An engineer extends a cached function by adding a parameter. Reasonable change—add a parameter, extend functionality. The code compiles. Tests pass. Everything looks fine. But the caching mechanism uses referential equality—it checks if the inputs are the exact same object, not just equivalent values. Every call with a newly-created object means the cache never hits. It’s completely broken, silently. The technical knowledge exists in the docs. The systemic problem is that nothing enforces this contract. The cache just quietly stops working, and nobody notices until someone profiles the app three months later.

**Abstraction grows opaque.** A coupon check gets added to a function that processes orders. The engineer is solving a local problem: “add coupon support.” They add a step that waits for coupon validation before continuing. Reasonable. But this function is 1000 lines long, built over months by multiple people. The coupon check now blocks everything below it—creating a waterfall where operations that don’t depend on each other run one at a time instead of simultaneously. The engineer adding the coupon check isn’t thinking about the global flow. They can’t see the flow because it’s spread across hundreds of lines of code written by people who no longer work there. The optimization is technically possible. But the information needed to see the opportunity exists only if you can hold the entire function in your head while understanding the performance implications of each step. Nobody can.

**Optimization without proof.** An engineer applies a performance optimization to a piece of code. They’ve learned that this technique—called memoization—speeds things up by remembering results instead of recalculating them. Good instinct. But the operation they’re “optimizing” was already instant. It’s like installing a complex caching system to remember that 2+2=4. The overhead of the optimization system now takes longer than just doing the original calculation. The engineer applied a best practice without checking whether it was needed. The system allowed optimization without proof of need, and the “improvement” actually made things slower.

These aren’t edge cases. They’re the normal failure mode of software at scale. Each individual decision was defensible. Each engineer was competent. The failures emerged from context gaps that no individual could bridge.


## **The Human Constraint**

Why do these context gaps exist? The answer lies in how human cognition actually works.

Humans have a fundamental constraint: working memory. We can only hold so much in active attention at once, and as the context we’re asked to consider increases—more files, more implications to trace, more history to remember—our performance degrades in predictable ways. This isn’t a training problem, and seniority doesn’t transcend it—it’s a structural limitation of human cognition.

This matters enormously for architecture because good architectural reasoning requires holding multiple concerns simultaneously: performance implications, security considerations, maintainability, the existing patterns in the codebase, the downstream effects on other teams, the long-term evolution of the system. Even a moderately complex architectural decision might involve a dozen relevant considerations. Humans can’t actually hold all of them in mind at once. We approximate by cycling through them, holding a few at a time, hoping we don’t miss interactions between concerns we’re not currently attending to.

When a human reviews code, they can either zoom in on the local change—checking logic, syntax, edge cases—or zoom out to consider architectural implications. They cannot do both at the same time with equal fidelity. This is why code review often catches bugs but misses architectural regressions. The cognitive bandwidth required to evaluate both simultaneously exceeds human capacity.

At organizational scale, the problem compounds. Large engineering teams are essentially distributed cognitive systems. Individual engineers hold fragments of the total system knowledge. Communication overhead tends to explode with team size. Context transfer between engineers is lossy. Institutional knowledge degrades as people leave. The engineer who knew why that weird caching pattern exists moved to another company two years ago. The documentation, if it ever existed, is out of date.

This creates a predictable failure mode: architectural regressions that no single engineer could have seen, because seeing them would have required synthesizing information that was distributed across multiple minds, multiple codebases, and multiple points in time.


## **The Machine Advantage**

Modern large language models have a different cognitive architecture than humans. They don’t have working memory constraints in the same way. They can hold a 200,000-token context window—roughly 150,000 words, or several hundred pages of code—in a form of attention that allows cross-referencing across the entire input simultaneously. Some models now support context windows of a million tokens or more.

This isn’t intelligence in the human sense. It’s something different: comprehensive pattern matching across a large context, with the ability to apply consistent rules without fatigue, distraction, or forgetting.

The examples I described—the component adding listeners, the cache breaking silently, the waterfall in the long function—are all cases where a human making a local change couldn’t see the global implications. An AI system with the entire codebase in context doesn’t have that constraint. It can check whether a component pattern is being instantiated hundreds of times. It can trace the referential equality implications of cache usage. It can analyze flow across an entire function to identify blocking patterns.

More importantly, it can do this consistently. Every time. Without deadline pressure causing it to skip the check. Without expertise variations between junior and senior engineers. Without the knowledge walking out the door when an engineer changes teams. Without the cognitive fatigue of reviewing the 47th pull request of the week.

This is the core insight: there are specific categories of work where AI isn’t just “helpful”—it’s structurally superior to human cognition because the task requirements exceed human cognitive constraints. Not because AI is smarter. Because the task is pattern-matching at scale, and humans aren’t built for pattern-matching at scale.


## **The Predictive Framework**

If this analysis is correct, it shouldn’t just explain React performance. It should predict where else AI will have structural advantages over humans in architectural work.

The principle: AI wins where the task requires (1) holding more context than humans can manage, (2) applying rules consistently across large surfaces, and (3) catching deviations from patterns that humans would miss due to fatigue, distraction, or context loss.

This predicts specific domains:

***Security review.*** Security vulnerabilities often emerge from the interaction between components that were each written correctly in isolation. SQL injection happens when input validation in one layer doesn’t match the query construction in another. Authentication bypasses happen when one code path checks permissions and another doesn’t. These are context problems—the information needed to see the vulnerability exists, but it’s spread across files that no single reviewer holds in mind simultaneously. An AI that can cross-reference the entire codebase can check whether every user input flows through validation before reaching a query, whether every protected route actually checks authentication, whether every API endpoint that should require authorization actually does.

***API design consistency.*** Large organizations end up with dozens or hundreds of internal APIs that should follow consistent patterns—naming conventions, error formats, pagination approaches, authentication mechanisms. In practice, they drift. Team A uses camelCase, Team B uses snake\_case. Service X returns errors as HTTP status codes, Service Y embeds them in the response body. Each individual decision was reasonable. Nobody was tracking the whole surface. An AI reviewing API changes against documented standards can catch drift at the moment it’s introduced, before it becomes entrenched.

***Accessibility standards.*** Web accessibility involves hundreds of specific requirements—ARIA labels, keyboard navigation, color contrast, focus management, screen reader compatibility. No human reviewer consistently remembers all of them while also reviewing business logic and performance. This is exactly the kind of checklist-at-scale work where AI can apply consistent attention that humans cannot sustain.

***Compliance enforcement.*** Regulated industries have codified rules about data handling, audit logging, retention policies, access controls. These rules map to specific code patterns. The patterns exist in the codebase, but verifying compliance requires checking every relevant location—every place where personal data is accessed, every logging statement, every permission check. Humans do this with sampling and hope. AI can do it exhaustively.

***Infrastructure drift.*** Infrastructure-as-code is supposed to prevent configuration drift, but the code itself can drift from standards. Resource naming conventions, tagging policies, security group rules, IAM permissions—all of these should follow patterns, and all of them tend to accumulate exceptions over time. Each exception was probably justified when it was introduced. Nobody tracks whether the exceptions have multiplied to the point where the pattern is no longer a pattern.

***Data schema governance.*** Database schemas evolve over time, and the evolution often violates principles that everyone agrees on but nobody enforces—normalization rules, naming conventions, indexing strategies, foreign key relationships. The violations accumulate silently until someone tries to do a migration or build a data warehouse and discovers that the schema is a mess of historical accidents.

The meta-question: how do you identify these domains in your own work? Look for anywhere you have (a) codified principles that everyone agrees on, (b) large surfaces where those principles should apply, and (c) historical evidence that the principles get violated despite agreement. That’s where the human constraint is binding, and where AI enforcement can help.


## **Where AI Still Falls Short**

The same first-principles reasoning that reveals AI’s advantages also exposes its limitations. These aren’t temporary gaps that better models will fix—they’re structural features of what AI systems are.

***Novel architectural decisions.*** AI systems are fundamentally pattern-matching engines trained on existing code and documentation. They excel at identifying when code deviates from established patterns. They cannot invent new patterns for genuinely novel problems. When you’re building something that doesn’t look like anything in the training data—a new category of distributed system, a novel approach to data modeling, an architecture that solves a problem nobody has solved before—AI assistance is limited to analogical reasoning from possibly-irrelevant prior examples. The creative leap that produces a new architectural paradigm is still a human act.

***Business context and trade-offs.*** Architecture isn’t just about what’s technically optimal. It’s about trade-offs between competing concerns: development velocity vs. maintainability, consistency vs. flexibility, near-term shipping vs. long-term evolution. These trade-offs are deeply contextual to organizational constraints, market pressures, and strategic priorities that exist outside the codebase. An AI can tell you that a pattern creates technical debt. It cannot tell you whether that debt is worth taking given your runway and competitive dynamics. It can identify that a microservices architecture would be more scalable, but it can’t weigh that against your team’s current expertise and your six-week deadline.

***Cross-system integration.*** Modern architectures involve multiple systems, often owned by different teams or organizations. The integration points—APIs, data contracts, operational dependencies—often aren’t fully documented in any single source the AI can access. The engineer who knows that “this service is actually maintained by a team that ships on a different cadence and sometimes breaks backward compatibility” has organizational context that no amount of code analysis can provide. The person who remembers that “we tried this integration approach before and it caused cascading failures during Black Friday” has historical context that isn’t written down anywhere.

***Judgment about “good enough.”*** Architecture involves knowing when to stop optimizing. The technically superior solution that takes six months isn’t better than the adequate solution that ships in six weeks if the business won’t survive the delay. The perfectly clean architecture doesn’t help if you run out of money building it. This kind of judgment requires understanding stakes, risks, and constraints that are fundamentally external to the technical system. AI can optimize toward a goal, but the meta-question of which goal to optimize toward is still a human judgment.

***The “why” behind existing decisions.*** Codebases are archaeological artifacts. They contain decisions made under constraints that no longer exist, workarounds for bugs that were later fixed, patterns that made sense for a team structure that has since changed, compromises with partner teams that no longer matter. An AI can see what the code does. It often can’t infer why it does it that way, and therefore can’t distinguish between load-bearing decisions and historical accidents. Refactoring guidance that treats everything as deliberate, or everything as accidental, will be wrong about half the code.


## **The Failure Modes**

If organizations adopt AI pattern enforcement without thinking carefully about the risks, they’ll encounter predictable failure modes.

***Encoding bad patterns at scale.*** AI enforces whatever patterns you give it. If your documented standards encode decisions that were wrong, or that were right once but are wrong now, the AI will enforce those wrong decisions consistently across your entire codebase. Bad patterns at scale is worse than bad patterns in pockets, because at least the pockets might contain local wisdom that contradicts the flawed standard. When you automate enforcement, you lose the escape valve of human judgment overriding bad rules.

***Over-standardization killing innovation.*** Not all deviation from patterns is bad. Sometimes the deviation is an experiment. Sometimes it’s a better approach that hasn’t been codified yet. Sometimes it’s a legitimate exception that doesn’t fit the general case. If AI enforcement creates too much friction for deviation, engineers will stop experimenting. The codebase will become consistent but ossified. The rules that exist will be enforced; the rules that should exist won’t emerge because nobody can try alternatives.

***Engineer deskilling.*** When AI enforces patterns, engineers don’t have to learn why the patterns exist. They just follow the AI’s suggestions. Over time, this erodes the team’s understanding of architectural principles. Engineers know what to do but not why. This is fine until they encounter a situation the rules don’t cover, at which point they lack the foundational understanding to reason from first principles. The AI created a dependency on itself.

***Rule conflicts across teams.*** Different teams have different standards, often for legitimate reasons. The backend team’s API conventions might conflict with the mobile team’s SDK patterns. The platform team’s security requirements might create friction with the product team’s velocity needs. When each team encodes their standards for AI enforcement, the conflicts become explicit and mechanical rather than implicit and negotiable. An engineer working at the boundary between teams might receive contradictory AI feedback that they can’t resolve without escalation.

***Ossification of historical decisions.*** Rules that made sense when they were written might not make sense anymore. But once encoded for AI enforcement, they tend to persist. Updating the rules requires someone to notice the rule is outdated, have the authority to change it, and actually make the change. In practice, this maintenance doesn’t happen reliably. The rules become a snapshot of past wisdom, enforced into the future even when the future has different needs.

***Gaming the system.*** When engineers are evaluated on whether their code passes AI review, some will optimize for passing the AI rather than for actual code quality. They’ll learn the patterns the AI checks for and write code that satisfies those checks without embodying the underlying principles. The letter of the law, not the spirit. This is the same dynamic that makes test coverage metrics perverse—when you measure the metric instead of the goal, people optimize for the metric.

These failure modes aren’t reasons to avoid AI enforcement. They’re reasons to implement it thoughtfully, with mechanisms for exception handling, rule evolution, and preserving space for experimentation.


## **The Organizational Shift**

If AI can enforce architectural patterns consistently, the role of the architect changes.

Traditionally, architects have done two jobs: identifying good patterns and enforcing them. They figure out how systems should be built, and then they try to ensure systems actually get built that way—through code review, design review, documentation, mentorship, and cultural influence.

When enforcement is automated, the architect’s job shifts toward pattern identification and encoding. The bottleneck is no longer “how do we get engineers to follow the standards?” It’s “what should the standards be, and how do we express them precisely enough for AI to enforce?”

This requires a different skill set. Enforcing patterns requires broad knowledge and patient attention. Identifying and encoding patterns requires precise articulation and explicit reasoning. An architect who has great intuition but can’t explain their intuition in words becomes less valuable, because the AI can’t learn from intuition. An architect who can take tacit knowledge and make it explicit becomes more valuable, because that’s the new bottleneck.

The organizational implications extend beyond the architect role:

***Hiring changes.*** The ability to articulate architectural reasoning becomes more important than the ability to catch architectural violations in review. You’re hiring for pattern recognition and documentation, not just pattern enforcement.

***Authority shifts.*** Whoever controls the rules controls the architecture. This might be the same people who previously had architectural authority, or it might not. The technical capability creates a power question that organizations will answer differently—sometimes explicitly, often by default.

***Design review changes.*** If AI is catching pattern violations, human design review can focus on the things AI can’t evaluate: business context, trade-offs, novel approaches, cross-team coordination. The review becomes higher-level and more strategic.

***Onboarding changes.*** New engineers can get AI feedback on their code immediately, which accelerates learning of team patterns. But they might learn the patterns without learning the reasoning, which creates the deskilling risk mentioned earlier. Effective onboarding will need to pair AI feedback with explanation of why the patterns exist.

Technical debt becomes more visible. When AI can identify all pattern violations, you can see exactly how much of your codebase doesn’t meet your standards. This is uncomfortable. Many organizations have implicit agreements not to look too closely at certain areas. AI enforcement makes that willful blindness harder to maintain.


## **The Second-Order Question**

If we know AI will be enforcing patterns, should we change how we work upstream?

Documentation becomes load-bearing. In a world without AI enforcement, documentation is nice to have. Engineers can succeed without reading it because they learn patterns through code review and osmosis. In a world with AI enforcement, documentation is the source of truth for what the AI enforces. If the docs are wrong or incomplete, the enforcement is wrong or incomplete. This changes the incentives around documentation quality.

Architectural decisions need explicit reasoning. It’s no longer enough to decide that “we use pattern X.” You need to document why you use pattern X, when it applies, when it doesn’t apply, and what the alternatives are. The AI needs this context to enforce appropriately. And if you can’t articulate the reasoning, maybe the decision isn’t as well-founded as you thought.

Codebases might be structured for AI-readability. If AI enforcement depends on being able to find relevant context, you might structure your codebase to make context easier to find. Explicit contracts at module boundaries. Standardized documentation locations. Naming conventions that make semantic search more effective. These are good practices anyway, but AI enforcement creates stronger incentives.

Exception mechanisms need to be designed. Every enforcement system needs an escape valve for legitimate exceptions. What does that look like for AI architectural enforcement? Comments that explain why a violation is intentional? Override annotations that suppress specific checks? A review process for approving exceptions? Without designed exception mechanisms, engineers will find informal workarounds, which defeats the purpose.

The feedback loop accelerates pattern evolution. When AI enforces patterns and surfaces all violations, you get faster feedback on whether your patterns are working. If the same exception keeps getting requested, maybe the pattern is wrong. If a rule produces constant false positives, maybe the rule is too broad. This feedback can drive faster iteration on standards—if you build processes to act on it.


## **What This Looks Like in Practice**

The Vercel team open-sourced a concrete example of how to structure architectural rules for AI agents. Their [react-best-practices repository](https://github.com/vercel-labs/agent-skills) contains 40+ rules across eight categories, and the format is instructive.

Each rule follows a template:

- **Title:** A clear name for the pattern or anti-pattern.
- **Impact rating:** CRITICAL, HIGH, MEDIUM, or LOW—so the AI knows what to prioritize.
- **Explanation:** Why this matters, written for an agent that needs to understand the reasoning, not just follow the instruction.
- **Incorrect example:** Code that demonstrates the problem, with a description of what’s wrong.
- **Correct example:** Code that demonstrates the fix.
- **When to apply:** The conditions under which this rule is relevant.

The categories are ordered by impact: eliminating waterfalls and bundle size optimization are CRITICAL; advanced micro-optimizations are LOW. This ordering matters because it tells the AI where to focus attention—don’t nitpick micro-optimizations when there’s a waterfall adding 600ms of latency.

The individual rule files compile into a single document that coding agents can query when reviewing code or suggesting optimizations. The rules are designed to be followed consistently, so teams can apply the same decisions across a large codebase without relying on every engineer to remember every principle.

To build your own version:

**Start with your failure modes.** What are the recurring problems in your codebase? The bugs that keep reappearing. The performance regressions that surprise you. The security issues that slip through review. The patterns that seem fine in code review but cause problems in production. Each of these is a candidate rule.

**Capture the reasoning, not just the rule.** “Don’t do X” isn’t enough. The AI needs to understand why, so it can recognize variations and edge cases. “Don’t do X because it causes Y, which manifests as Z” is better.

**Include concrete examples.** Show the wrong way and the right way. Agents learn from examples, and explicit before/after comparisons reduce ambiguity.

**Prioritize** ***ruthlessly*****.** Not all rules are equal. If you have 50 rules and they’re all marked HIGH priority, you effectively have no prioritization. The AI doesn’t know where to focus, and neither do the humans reviewing its suggestions.

**Design the exception mechanism.** How do engineers override a rule when they have a legitimate reason? Make this explicit rather than forcing engineers to find workarounds.

**Plan for evolution.** Every time you find a new failure mode, add a rule. Every time a rule produces false positives, refine it. Every time a rule becomes obsolete, remove it. The rule set is a living document that encodes your team’s accumulated wisdom, and wisdom should evolve.

The Vercel repository is available at github.com/vercel-labs/agent-skills. You can install their React best practices directly into Claude Code, Cursor, and other agents with a single command: `npx add-skill vercel-labs/agent-skills`. But the more interesting move is using their structure as a template for your own domain-specific rules—the patterns that matter for your codebase, your architecture, your failure modes.

Start with one category. If performance is your biggest problem, start with performance rules. If security keeps biting you, start with security rules. Get the feedback loop working on a small surface before trying to encode everything.


## **The Larger Point**

Most organizations are asking the wrong question. They ask: “Can AI do architecture?” when they should ask: “What aspects of architecture is AI structurally suited for, and what aspects require human cognition?”

The answer is nuanced. AI is structurally superior at maintaining context across scale, applying patterns consistently, detecting deviations from established principles, and educating at the moment of need. Humans are structurally superior at judgment under uncertainty, novel problem-solving, integrating business context with technical decisions, and making trade-offs that involve factors outside the codebase.

The organizations that will thrive are the ones who design their workflows around this reality—using AI for the high-volume pattern-matching work that humans can’t do well at scale, and preserving human attention for the high-judgment work that AI can’t do at all.


## **What Non-Technical Teams Should Take From This**

I promised at the beginning that this technical deep-dive would have broader relevance. Let me make good on that.

You just watched me work through a specific domain—software architecture—and identify exactly where human cognition hits structural limits. The limits aren’t about skill or effort. They’re about working memory, attention, and the impossibility of holding cathedral-scale context while laying individual bricks. Those limits create predictable failure modes: context gets lost, principles drift, entropy wins.

Then I identified where AI has structural advantages that address those specific limits. Not “AI is smart” but “AI can hold more context, apply rules consistently, and never get tired.” And I identified where AI falls short: novel decisions, business judgment, cross-system politics, knowing when good enough is good enough.

That analytical framework transfers to any domain. Here’s how to apply it:

***Step one: Identify your entropy.*** Where in your work do things degrade despite everyone’s best intentions? Where do principles that everyone agrees on somehow not get followed? Where does quality drift over time even though nobody made a bad decision? That’s your entropy. It’s probably not a people problem. It’s probably a context problem—the information needed to maintain quality exists but isn’t held in mind at the moment of decision.

***Step two: Map the cognitive constraint.*** What would someone need to hold in their head simultaneously to prevent that degradation? Is it too much? Is it distributed across too many people, documents, or moments in time? If a reasonable, competent person can’t realistically maintain that context, you’ve found a structural limit, not a training problem. Yes, your most experienced people will be better at this—but when the context required at decision time exceeds what any single mind can hold, expertise narrows the gap without closing it. Building your quality system around the hope that a hero is always in the room doesn’t scale.

***Step three: Ask whether AI can address that specific limit.*** Can the principle be articulated as a rule? Can the AI access the context needed to evaluate against that rule? Can it check consistently at scale? If yes, that’s a candidate for AI enforcement. If no—if the task requires novel judgment, business context, or understanding things that aren’t written down—that’s human work.

***Step four: Design the handoff.*** What does AI handle? What do humans handle? How do humans override AI when they have context the AI lacks? How do you prevent the failure modes—deskilling, ossification, over-standardization? This is the hard part, and it’s human work.

Let me make this concrete for a few domains:

***Product management.*** Your entropy: feature inconsistency, edge cases that don’t get handled, user flows that violate principles everyone agreed on. The context gap: nobody holds the entire product surface in mind while reviewing a single spec. AI can check specs against documented patterns—”every destructive action needs a confirmation step,” “empty states need clear next actions,” “error messages need to explain what to do next.” Humans decide which patterns matter, when to make exceptions, and how to handle genuinely novel features.

***Marketing.*** Your entropy: brand drift, messaging inconsistency, claims that can’t be substantiated. The context gap: nobody holds all the brand guidelines in mind while writing a single piece of content. AI can check content against voice guidelines, flag unsubstantiated claims, ensure messaging hierarchy is followed. Humans decide what the brand should sound like, make judgment calls about tone in sensitive situations, and handle creative work that’s intentionally breaking patterns.

***Customer success.*** Your entropy: inconsistent responses, playbooks that don’t get followed, institutional knowledge that doesn’t transfer to new reps. The context gap: nobody can hold all the troubleshooting knowledge and past resolutions in mind while handling a ticket. AI can surface relevant past cases, check that responses follow templates, ensure escalation criteria are applied. Humans handle the emotional intelligence, make judgment calls about when to go off-script, and deal with situations the playbook doesn’t cover.

***Operations.*** Your entropy: procedure drift, compliance gaps, documentation that doesn’t get maintained. The context gap: nobody can verify all the requirements against all the implementations all the time. AI can check configurations against standards, flag compliance deviations, verify that runbooks are complete. Humans decide what the standards should be, handle novel incidents that don’t fit procedures, and make risk judgments about when to deviate from protocol.

The framework is always the same: find the context gap, identify the structural cognitive limit, determine whether AI can address that specific limit, design the human-AI handoff.


## **The Work of 2026**

This isn’t about AI replacing people. It’s about AI addressing the specific cognitive limitations that cause predictable failures—and freeing humans to do the work that actually requires human judgment.

Every department in every organization is going to have to think at this level. Not “should we use AI?” but “where specifically do we have context gaps that exceed human cognitive capacity, and where do we have judgment calls that require human wisdom?” The answers will be different in every domain. The framework for finding the answers is the same.

The engineers who thrive will be the ones who recognize that enforcement is being automated and position themselves for pattern identification and encoding—the work that remains human. The same is true for product managers, marketers, operators, and everyone else.

The role isn’t going away. It’s splitting in two. One half is being automated. The other half—the half that requires judgment, creativity, business context, and the ability to know when the rules should be broken—remains human. Maybe becomes more human, because there’s finally time for it.

Software tends toward chaos. So do products, brands, operations, and organizations. Humans can’t fight entropy with willpower alone. We never could. But we can build systems that remember what we forget, that maintain context we can’t hold, that apply principles we believe in but can’t consistently enforce.

And then we can focus on the work that actually requires us. That’s the opportunity. That’s the work of 2026.

[![](https://substackcdn.com/image/fetch/$s_!SD6p!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4e39c4eb-dcaf-413b-a491-e6620096aa91_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!SD6p!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4e39c4eb-dcaf-413b-a491-e6620096aa91_1024x1024.png)
