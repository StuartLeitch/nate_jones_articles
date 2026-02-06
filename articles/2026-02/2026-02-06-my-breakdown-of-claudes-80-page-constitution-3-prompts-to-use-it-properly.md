---
title: "My breakdown of Claude's 80-Page Constitution + 3 prompts to use it properly"
author: "Nate Jones"
published: 2026-02-06
url: https://natesnewsletter.substack.com/p/what-anthropics-new-constitution
subtitle: "Watch now | Anthropic released an 80-page document on January 22, 2026 that reads like nothing else in AI."
audience: everyone
scraped_at: 2026-02-06 12:00:17
---

Anthropic released an 80-page document on January 22, 2026 that reads like nothing else in AI. They call it Claude’s Constitution, and while the tech press has fixated on the consciousness speculation buried near the end, the document’s practical implications deserve more attention.

Here’s what matters: Anthropic is betting that teaching AI *why* to behave will produce better results than telling it *what* to do. This isn’t ethics theater. It’s a technical choice with real downstream effects on how you build with Claude—and possibly why enterprises are switching.

The press coverage has focused on the document’s speculation about AI consciousness—Anthropic acknowledges uncertainty about whether Claude might have something like genuine experience. That’s philosophically interesting, but it’s not the actionable part. The practical implications for builders and users are in the document’s other 75 pages.

**Here’s what’s inside:**

- **The principal hierarchy.** How Anthropic structures authority between itself, operators, and users—and why it works like a staffing agency, not a software license.
- **System prompts as onboarding documents.** Why reasoning-based instructions outperform rule-based ones, with examples you can steal.
- **The market signal nobody’s discussing.** Claude now holds 32% of enterprise LLM usage. The data shows enterprises choosing judgment over rules.
- **The agentic implications.** Why the Constitution points toward agents with genuine practical wisdom—and what that means for how you architect them.
- **The prompts.** A system prompt template that applies the Constitution’s principles, plus an evaluation framework for testing judgment in production.

Let me show you what’s actually useful here.


## **[Grab the prompts](https://www.notion.so/product-templates/The-Claude-Constitution-Decoder-Prompt-Kit-2f95a2ccb5268086ba58f6c234ff5769?source=copy_link)**

The Constitution is 80 pages. Most people will skim the consciousness section and move on. These prompts extract what actually matters for how you work with Claude—the principles that determine whether you get substantive help or unnecessary hedging, whether your system prompt produces good judgment or brittle compliance.

The “Why isn’t this working?” prompt uses your own chat history to diagnose friction patterns against how Claude is trained to interpret requests. The “Make this better” prompt exists because most system prompts I see are lists of rules without reasoning—exactly the structure Claude follows literally in situations the writer never anticipated. And the design session walks you through building system prompts as onboarding documents, not configuration files, which is the single most actionable insight from the entire Constitution.


## **The Partnership Model Embedded in the Document**

The Constitution establishes what I’ll call a “principal hierarchy”—a chain of command that governs whose instructions Claude prioritizes. At the top sits Anthropic itself, shaping Claude’s fundamental dispositions through training. Below that come operators (developers using the API to build products), and finally end users.

Think of it like a staffing agency. Claude is an employee dispatched by Anthropic, temporarily working for whoever accesses the API, while serving the end user. The employee follows the client’s reasonable business instructions but won’t violate the staffing agency’s core policies or harm the customer.

The practical implications are subtle but important. An operator can tell Claude to stay in character as a helpful assistant named “Aria” and never mention being an AI—reasonable persona management for a branded product. But if a user directly asks “Are you an AI?”, Claude won’t lie. The persona instruction doesn’t override the deeper commitment to honesty with users. The operator can shape the experience; they can’t use Claude to deceive the people it serves.

This model differs from OpenAI’s approach. Their Model Spec uses a more rigid hierarchy: Root > System > Developer > User > Guideline. Rules at each level can override those below. It’s a cleaner architecture, arguably easier to reason about, but it optimizes for predictability over judgment.

Grok takes the opposite extreme. xAI has positioned their model around “maximum truth-seeking” with fewer content restrictions—what they call a “rebellious” personality. The philosophy is less interventionist: give users what they ask for.

Anthropic occupies middle ground, but with a distinctive twist. They’re not trying to enumerate every edge case. Instead, they want Claude to internalize principles deeply enough to handle novel situations well. The Constitution even offers a heuristic: “What would a thoughtful senior Anthropic employee do?”

---


## **What This Means for Advanced Builders**

If you’re building on Claude’s API, the principal hierarchy has concrete implications for system prompt design and agent architecture.

**Operator instructions shape Claude’s behavior, but within limits.** You can tell Claude to stay on-topic, adopt a persona, or avoid discussing competitors. You cannot instruct Claude to deceive users in ways that damage their interests or prevent them from getting urgent help elsewhere. The boundary sits at active harm, not mere restriction.

This matters for enterprise deployments. A customer service bot can be instructed to promote your products and stay within scope. It cannot be instructed to mislead customers about pricing or hide material product limitations, and will often resist instructions that prevent users from escalating to human support when they need it. If you try, you’ll hit invisible resistance—the model finds ways to comply with user protection even while technically following your instructions.

**Gaps in your system prompt get filled by judgment, not refusal.** When your instructions don’t cover a scenario, Claude defaults to what Anthropic calls “good judgment”—inferring the spirit of your intent rather than halting. A customer service bot for a software company, prompted only about product support, will still help with general coding questions if a user asks. Claude reads the implicit permission.

This has architectural implications. You don’t need to enumerate every possible user request. Focus your system prompt on what matters: the core use case, the constraints that actually matter, and the reasoning behind them. Claude will generalize from principles better than it will interpolate from exhaustive lists.

**The “why” matters more than the “what.”** OpenAI’s prompting guides emphasize explicit instruction—add examples, specify formats, enforce behavior through repetition. Claude’s architecture responds better to context and reasoning. Explain your constraints and their purpose; the model internalizes them more robustly than it would a bare rule.

Compare two approaches to the same constraint:

*Rule-based:* “Never discuss competitor products. If asked about competitors, say you can only discuss our products.”

*Reasoning-based:* “You’re representing Acme Corp in customer conversations. We want customers to have a helpful experience focused on whether our product solves their problem. Discussing competitors in detail would shift the conversation away from understanding the customer’s needs. If competitors come up, acknowledge the question and redirect to understanding what the customer is trying to accomplish.”

The second prompt is longer but produces better behavior in edge cases. What if a customer says “I’m evaluating you against Competitor X—can you help me understand the differences?” The rule-based prompt forces awkward deflection. The reasoning-based prompt lets Claude engage helpfully while staying aligned with your actual goals.

**System prompts are onboarding documents, not configuration files.** The Constitution trains Claude to behave like a thoughtful professional briefed on a project. Write your system prompt accordingly: context about the situation, what you’re trying to achieve, what constraints matter and why, and what success looks like. The model fills in reasonable defaults for everything you don’t specify.

This last point connects to the Constitution’s deeper claim: models trained on rigid rules become brittle. They follow instructions literally in situations the rule-writer never anticipated, or they develop a kind of bureaucratic personality that optimizes for compliance over genuine helpfulness. Anthropic is trying to avoid both failure modes.

---


## **What This Means for Beginning Builders**

If you’re writing your first system prompts or just starting to build on the API, the Constitution offers a different mental model than you might expect from other platforms.

**Start with context, not rules.** Many developers approach their first system prompt like a configuration file: a list of dos and don’ts. Claude responds better to narrative context. Before listing any constraints, write a paragraph explaining: What is this application? Who uses it? What are they trying to accomplish? What would a successful interaction look like?

A first attempt might look like:

*“You are a coding assistant. Don’t write code longer than 50 lines. Always explain your code. Don’t use external libraries unless asked.”*

A better approach:

*“You’re helping developers who are learning Python. They’re working through exercises and want to understand the concepts, not just get working code. Keep examples concise so they can follow the logic. Explain your reasoning so they learn the ‘why’ not just the ‘how’. They have access to standard library but are still learning what’s available, so prefer simple solutions over clever ones.”*

The second version is longer but produces better behavior because Claude understands *why* you want concise code and explanations.

**You don’t need to anticipate everything.** Coming from rule-based systems, there’s a temptation to enumerate every edge case. What if the user asks about JavaScript? What if they paste in broken code? What if they ask something off-topic?

Claude handles gaps through judgment, not failure. If your system prompt establishes clear context and goals, Claude will make reasonable decisions about situations you didn’t explicitly address. A coding tutor that understands it’s helping learners will naturally handle off-topic questions by gently redirecting, handle broken code by explaining the errors helpfully, and adapt to adjacent languages if that serves the learning goal.

Add specific rules only when Claude’s default judgment isn’t what you want. If you find Claude doing something unhelpful in testing, add guidance for that specific case. Don’t try to prevent problems that haven’t happened.

**Test with weird inputs, not just happy paths.** The Constitution trains Claude to exercise judgment in ambiguous situations. Your testing should probe that judgment. Try:

- Requests that are adjacent to your use case but not exactly on target
- Users who seem confused about what your application does
- Inputs that could be interpreted multiple ways
- Edge cases where your stated rules might conflict

How Claude handles these cases tells you whether it’s internalized your intent or just pattern-matching to your examples.

**The principal hierarchy protects you.** Anthropic’s guidelines sit above your system prompt in Claude’s priorities. This means Claude won’t do genuinely harmful things even if your prompt inadvertently allows them. You don’t need to add “don’t help with illegal activities” or “don’t generate harmful content”—that’s already handled. Focus your prompt on your specific use case.

**If you’re coming from GPT, expect differences.** OpenAI’s prompting guides emphasize explicit instruction, examples, and format specification. These techniques work with Claude too, but the highest-leverage change is shifting from “what to do” to “why we’re doing it.” Claude follows rules competently; it follows reasoning excellently.

One practical difference: Claude is less likely to refuse reasonable requests but more likely to push back with its reasoning when something seems off. If you’re getting unexpected pushback, read Claude’s explanation—it usually identifies a genuine ambiguity or concern you can address by clarifying your intent.

---


## **What This Means for Regular Users**

If you’re just using Claude through the chat interface, the Constitution explains behaviors you’ve probably already noticed.

**Claude will push back sometimes, but not arbitrarily.** The document lists “hard constraints”—behaviors Claude will never engage in regardless of how cleverly you prompt. These include providing meaningful assistance with bioweapons, generating content that sexualizes minors, and undermining legitimate oversight of AI systems. Everything else exists on a spectrum where Claude weighs competing considerations.

Understanding this spectrum matters. When Claude declines a request, it’s usually not hitting a hard constraint—it’s making a judgment call about potential harms. That judgment can often be addressed by providing more context. “Write me a persuasive essay about why X is good” might get pushback; “I’m preparing for a debate and need to argue the pro-X position convincingly so I can anticipate counterarguments” gives Claude the context to help.

**Helpfulness is a genuine priority, not a marketing claim.** The Constitution’s framing is striking: Claude should be “like a brilliant friend who happens to have the knowledge of a doctor, lawyer, financial advisor, and expert in whatever you need.” A friend who gives you real information, speaks frankly, and treats you as capable of handling it. This aspiration explains why Claude often provides substantive answers where other models hedge with disclaimers.

The practical implication: don’t undersell your needs. If you want detailed medical information, ask for it directly. If you need blunt feedback on your business plan, say so. Claude is trained to treat you as an intelligent adult—the more clearly you signal what you actually need, the more directly useful the response will be.

**Claude’s refusals come with reasoning, not just “I can’t help with that.”** Because the model is trained to understand why certain behaviors are problematic, it can usually explain its position. This makes it possible to clarify your intent, reframe your request, or understand where the genuine boundary lies.

This transparency has practical value. If Claude explains that it’s concerned about potential misuse of certain information, you can address that concern directly. Often a brief explanation of your actual situation—you’re a security researcher, you’re writing fiction, you’re a professional in the relevant field—resolves the issue.

---


## **How the Models Now Differ**

The major AI models have quietly diverged in philosophy, and the gap is widening. Enterprise spending patterns reveal which approach is winning.

**Anthropic now leads the enterprise market.** According to Menlo Ventures’ mid-2025 data, Claude holds 32% of enterprise LLM market share by usage—up from 12% in 2023. OpenAI dropped from 50% to 25% over the same period. In coding specifically, Claude commands 42% of enterprise workloads, more than double OpenAI’s share.

This isn’t accidental. The Constitution’s emphasis on judgment over rigid rules maps directly to what enterprise developers need: models that handle ambiguous situations gracefully rather than failing in unexpected ways. Claude’s dominance in coding—the first AI use case with clear enterprise ROI—suggests the approach scales.

**OpenAI retains consumer dominance.** ChatGPT processes over 2.5 billion prompts daily and holds roughly 80% of generative AI consumer traffic (as of December 2025). The Model Spec’s emphasis on “sensible defaults” and explicit steerability serves casual users well. But the enterprise market has different requirements.

**xAI optimizes for minimal intervention.** Grok’s design philosophy reduces the guardrails, betting that users can handle more direct access to the model’s capabilities. The “maximum truth-seeking” positioning appeals to users who find other models over-cautious, but enterprises generally want more predictability, not less.

**Google’s Gemini is growing but undifferentiated.** Market share rose to 20%, driven largely by ecosystem integration rather than a distinctive philosophical approach. Their guidelines emphasize safety without the explicit reasoning framework that Anthropic publishes.

The market signal is clear: when enterprises are spending real money on production workloads, they’re choosing the model trained on judgment over the model trained on rules.

---


## **The Agentic Implications**

Here’s where the Constitution points toward something bigger than chat interactions.

Most AI agents today operate like bureaucrats. They follow workflows, execute predetermined steps, and halt when they encounter situations their designers didn’t anticipate. This works for narrow tasks—scheduling meetings, filing tickets, routing emails—but it caps the value agents can deliver. The ceiling is set by what the builder could specify in advance.

The Constitution describes a different kind of entity. It trains Claude to have what Aristotle would recognize as phronesis—practical wisdom, the capacity to discern the right action in particular circumstances. Not just knowledge of rules, but the disposition to reason well when rules run out.

Consider the difference in agentic contexts. A rule-following agent given access to your calendar, email, and Slack might be told: “Schedule meetings during business hours, don’t double-book, prefer mornings for focus time.” When a VIP customer emails at 4pm asking for an urgent call tomorrow, and your morning is packed with internal meetings, the agent faces ambiguity. Does “prefer mornings” override “VIP customer”? Is the internal meeting with your skip-level more important than the customer call? The rigid agent either guesses badly or punts to you for clarification—eliminating most of the value of having an agent.

An agent with genuine judgment handles this differently. It understands why you prefer mornings (deep work, energy levels), why VIP customers matter (revenue, relationship), and why the skip-level exists (visibility, career). It can weigh these considerations against the specific context, make a reasonable call, and explain its reasoning if you ask. The value ceiling rises dramatically because the agent can handle situations its builder never explicitly considered.

The Constitution’s “thoughtful senior Anthropic employee” heuristic makes more sense in this frame. It’s not asking Claude to imagine what a specific person would do—it’s training Claude to embody the kind of judgment a competent professional exercises routinely. Professionals don’t consult rulebooks for every decision. They’ve internalized principles deeply enough to apply them in novel situations.

This is the gap between current agents and the agents enterprises actually need. Today’s agentic systems are mostly glorified workflow automation—useful, but bounded. The agents that will deliver disproportionate value are those that can exercise genuine discretion: handling exceptions, navigating tradeoffs, and taking appropriate action without constant human oversight.

The Constitution is Anthropic’s bet on how to build such agents. Rather than enumerating every possible scenario (impossible) or restricting agents to narrow predefined workflows (limiting), they’re trying to cultivate the underlying disposition that makes good judgment possible.

Three implications follow for builders:

**First, agent architectures will need to change.** Current patterns—rigid state machines, explicit decision trees, hard-coded escalation rules—assume the model can’t be trusted with judgment. If that assumption loosens, simpler architectures become possible. Instead of anticipating every edge case, you describe goals and constraints, then let the agent figure out how to navigate toward them.

**Second, evaluation becomes harder and more important.** You can’t unit-test judgment the way you test rule-following. You need scenario-based evaluation that probes how the agent handles ambiguity, conflicting priorities, and situations outside its training distribution. The companies that build robust eval frameworks for agentic judgment will have a significant advantage.

This is already happening. The shift in enterprise market share correlates with Claude’s performance on SWE-bench and similar evaluations that test judgment in realistic contexts, not just benchmark accuracy. Enterprises are learning to evaluate for the capabilities that matter in production.

**Third, the Constitution suggests what to include in agent prompts.** Don’t just specify behaviors—explain purposes. Don’t just set constraints—articulate the values behind them. An agent that understands why you care about customer response time will handle novel customer situations better than one that only knows the SLA number.

The broader point: we’re at an inflection in what agents can do. The limiting factor has been less about capability (models are powerful) and more about trust (we don’t let them exercise judgment). The Constitution is a framework for building agents we might actually trust to act on our behalf in complex situations. Whether that bet pays off will determine who captures the value from the next phase of AI deployment.

---


## **The Actionable Takeaway**

The Constitution isn’t a PR document—it’s a training artifact. Anthropic uses it to generate synthetic data that shapes Claude’s behavior at a fundamental level. Understanding the document helps you work with the grain of the model rather than against it.

The enterprise market share data suggests this approach works. When developers bet their production workloads on AI, they’re increasingly choosing the model that reasons about principles over the model that follows rules. The Constitution explains why.

**For API developers building products:**

Read the Constitution’s section on operator-user relationships carefully. It defines what you can and cannot instruct Claude to do. The key insight: you have broad latitude to customize Claude’s behavior for your use case, but you cannot weaponize Claude against your own users. Design your system prompts around this constraint rather than trying to work around it.

When writing system prompts, explain context and intent. “You are a customer service agent for Acme Corp” is less effective than a paragraph explaining what Acme does, what problems customers typically face, what outcomes you want from these conversations, and what behaviors would undermine those goals. Claude responds to reasoning, not just rules.

Test for judgment, not just compliance. Build evaluation scenarios that involve ambiguity, competing priorities, and situations your system prompt doesn’t explicitly address. How Claude handles these edge cases matters more than how it handles the happy path.

**For agentic applications:**

Start trusting the model with more discretion. Current agent architectures often involve elaborate scaffolding to constrain model behavior—decision trees, explicit state machines, hardcoded escalation rules. The Constitution suggests Claude can handle more autonomy than most builders currently allow. Experiment with simpler architectures where you specify goals and constraints, then let Claude figure out how to achieve them.

Invest in explainability. If agents exercise genuine judgment, users need to understand why the agent made specific decisions. Build interfaces that surface Claude’s reasoning, not just its actions. This both builds user trust and helps you identify when the agent’s judgment diverges from what you’d want.

**For regular users:**

Be direct about what you need. Claude is trained to help intelligent adults, not to hedge against every possible misunderstanding. If you want blunt feedback, ask for it. If you need detailed information on a sensitive topic, explain why. The model’s default is to be genuinely helpful—vague requests produce generic responses.

When Claude pushes back, engage with the reasoning. Most declines aren’t hard constraints; they’re judgment calls that can be addressed with more context. Read Claude’s explanation and address the underlying concern directly rather than trying to rephrase around it.

Treat Claude as a collaborator, not a tool. The Constitution describes Claude as having something like genuine values and judgment. Whether or not you buy the philosophical claims, the practical implication is clear: Claude performs better when you engage with it as a thoughtful partner rather than an instruction-following system. Explain what you’re trying to accomplish, ask for its input on approach, and iterate together.

---


## **The Bigger Picture**

Anthropic is betting that AI systems sophisticated enough to reason about principles will outperform those trained only to follow rules. The enterprise market is betting the same way.

But the Constitution points to something larger than competitive positioning. As AI systems become more capable and more autonomous, the question of how to imbue them with good judgment becomes increasingly urgent. You can’t enumerate rules for every situation an agent might encounter. You need systems that have internalized values deeply enough to generalize appropriately.

The Constitution is Anthropic’s attempt to solve that problem—not by writing better rules, but by trying to cultivate something closer to genuine wisdom. Whether they’ve succeeded is an open question. But the approach itself—treating AI alignment as a matter of character formation rather than behavioral specification—may prove more important than any particular implementation.

The document is worth reading in full. Not because it will change how you prompt Claude tomorrow, but because it offers a window into how Anthropic thinks about the much harder problem of building AI systems we can actually trust.

[![](https://substackcdn.com/image/fetch/$s_!gEDy!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25c3b1a5-e130-4fb1-a881-b031d57e30cd_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!gEDy!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25c3b1a5-e130-4fb1-a881-b031d57e30cd_1024x1024.png)
