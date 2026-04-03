---
title: "Your Agent Is 80% Plumbing. Here Are the 12 Pieces You're Missing."
author: "Nate Jones"
published: 2026-04-03
url: https://natesnewsletter.substack.com/p/your-agent-has-12-blind-spots-you
subtitle: "Watch now | Everyone’s talking about the Tamagotchi -- here’s what actually matters."
audience: everyone
scraped_at: 2026-04-03 12:00:18
---

Anthropic just accidentally published the full source code of Claude Code, one of the most commercially successful agentic AI systems ever shipped. 1,902 files totaling 512,000+ lines across 29 subsystems. The entire architecture of a product doing an estimated $2.5 billion in annualized revenue, exposed because someone forgot to exclude a source map file from an npm package.

Every AI newsletter and Twitter thread is doing the same thing with it: cataloguing the hidden features. The Tamagotchi pet. The unreleased voice mode. The 44 feature flags. That’s interesting for about five minutes.

I mapped the infrastructure underneath the features and extracted the design primitives that determine whether an agentic system actually works in production. What I found is that the LLM call is maybe 20% of Claude Code. The other 80% is plumbing: session persistence, permission pipelines, context budget management, tool registries, security stacks, error recovery. The boring stuff that nobody writes tutorials about, and the exact stuff that separates a demo from a system that has to work when millions of people depend on it.

Every “how to build agents” tutorial on the internet stops at the demo stage: get the prompt right, wire up tool calling, ship it. And then it breaks in production in ways nobody warned you about. Sessions don’t survive crashes, tools run without permission, context windows overflow, costs spiral, and there’s no way to tell what went wrong. Thousands of developers are hitting exactly these problems right now, and the tutorials they learned from never covered them.

**Here’s what’s inside:**

- **Two leaks, one week, zero coincidences.** What Anthropic’s back-to-back exposures reveal about AI-assisted development velocity outrunning the operational discipline that’s supposed to keep it safe.
- **The 12 infrastructure primitives, prioritized.** Everything Claude Code runs on beneath the LLM call, organized not by how it appears in the source but by what you need to build first — day one, week one, month one.
- **An 18-module security stack for a single shell command.** How Anthropic thinks about permissions, crash recovery, token budgets, and session persistence at scale — and what your system should borrow.
- **The confirmation nobody expected.** Within hours, developers ported the entire harness to Python and Rust, proving these patterns aren’t Anthropic-specific — they’re structural requirements of any agent that has to work for real.
- **A prompt and a skill to audit what you’ve actually built.** An architecture audit that interviews you about your agent system and returns a gap analysis against all 12 primitives — plus a free skill package for Claude Code and OpenAI Codex that reads your codebase and tells you what’s missing.

Let me start with how this leak happened, because the meta-lesson frames everything that follows.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260331_6yc_promptkit_1)

Reading about twelve infrastructure primitives is useful. Knowing which ones your system is actually missing is what changes what you build next week. This piece comes with an audit prompt and a skill package, and they do different jobs. The audit prompt runs as a structured interview in any model — ChatGPT, Claude, Gemini — where you describe your agent system, answer targeted follow-up questions about how it handles sessions, permissions, crash recovery, and cost tracking, and get back a tiered gap analysis with severity ratings and a prioritized build order. You don’t need to prepare anything or share code. If your honest answer to “what happens when your agent crashes mid-task?” is “the user starts over,” that’s a finding, and the audit tells you exactly what to build and in what order. For developers who want the deeper version — something that reads your actual codebase and evaluates against every dimension in this article — the **[skill package](https://github.com/NateBJones-Projects/OB1/tree/main/skills/n-agentic-harnesses)** covers that for both Claude Code and OpenAI Codex.

---

Within hours of the leak going public, tweets cataloguing the unshipped features (background agents running 24/7, coordinator mode, voice commands, browser control via Playwright) were pulling hundreds of thousands of views. “It’s all built,” one viral thread concluded. “They’re just drip-feeding releases.” Repos archiving the code hit 30,000 stars within hours.

And there’s a particular irony underneath the frenzy: Anthropic built an entire subsystem called Undercover Mode to prevent their AI from accidentally leaking internal information in public repositories. And then they shipped the entire source code in a `.map` file. Probably bundled by Claude itself.


## A note on confidence

Not everything in this analysis carries the same epistemic weight.

Some patterns are directly confirmed from implementation structure, visible in code, configuration, and concrete module relationships. Some are strong structural inferences, likely behavior derived from multiple aligned modules, naming conventions, and cross-file boundaries. And some are design hypotheses, plausible interpretations that should be treated as transferable lessons, not as literal claims about Anthropic’s intent.

I’ll be explicit about which is which. The developers who would benefit most from this analysis are the same ones who’d notice if I overclaimed, and I’d rather be precise than impressive.


## The meta-lesson before the primitives

There’s a systemic observation worth making before we go deep on architecture, because it frames everything that follows.

According to Dario Amodei, somewhere between 70 and 90% of the code written at Anthropic is written by Claude. Boris Cherny, the founding engineer who built Claude Code, hasn’t manually edited a line of code in months. More than 80% of Anthropic’s engineers use it daily. They call the practice “antfooding.” The tool builds itself.

This leak is the second significant public exposure in five days. Last week, Fortune reported that Anthropic left draft materials about an unreleased model called Claude Mythos, which the company describes as “by far the most powerful AI model we’ve ever developed” and one that poses “unprecedented cybersecurity risks,” in a publicly accessible data store due to a CMS misconfiguration. Five days later, a build configuration error ships the full Claude Code source to npm.

Different mechanisms, different systems, same company, same week.

I’m not claiming Mythos or any specific model caused this leak. Anthropic says it was human error, and there’s no public evidence to the contrary. But the pattern raises a question that every team building with AI-assisted development should be asking: is your development velocity outrunning your operational discipline?

It’s telling that the developer community’s default conjecture for *how* this happened involves an AI model making the error. The theory circulating on X (flagged explicitly as conjecture by Alex Volkov) is that someone inside Anthropic got switched to Adaptive reasoning mode, their Claude Code session fell back to Sonnet, and the model committed the `.map` file as part of a routine build step. Nobody knows if that’s what actually happened. But the fact that “the AI committed the build artifact that leaked the AI’s own source code” is the community’s most plausible guess tells you something about where we are with AI-assisted development.

When AI writes the vast majority of your code and your engineers are shipping roughly five releases per day, the surface area for configuration drift is enormous. The irony of Undercover Mode — a subsystem specifically built to prevent internal information from leaking — sitting alongside a `.npmignore` that failed to exclude a 59.8 MB source map file is not a joke about Anthropic’s competence. It’s a structural warning about where the risk actually lives: not in the AI capabilities themselves, but in the mundane operational hygiene that keeps them from being irrelevant.

Something tells me Anthropic will tighten this up without meaningfully slowing their shipping cadence. The velocity is here to stay — the operational discipline is what has to catch up.

The leaked code itself shows that Anthropic is iterating on a model internally called Capybara (the same model Fortune reported as Claude Mythos) that has a 29-30% false claims rate in its current version, a regression from the 16.7% rate in an earlier version. They’re aware of it and building assertiveness counterweights. The approach is deliberate.

But the leak happened anyway. Because production infrastructure discipline, the build pipeline configuration, the `.npmignore` file, the publish-step validation, is exactly the kind of plumbing that gets neglected when everyone’s focused on the AI.

Which brings us to the primitives.


## The hierarchy of primitives

The organizing principle: these are presented in the order you should think about them when building your own system, not the order they appear in Claude Code’s source. There are twelve categories. I’ve prioritized them into three tiers: what you need on day one, what you need in week one, and what you need in month one.

For each primitive, I’ll separate three things:

1. **The universal pattern.** The design principle that applies to any agentic system
2. **Claude Code’s manifestation.** One specific, production-grade implementation of that pattern
3. **Your translation.** How this looks in your system, which may not be a code agent at all

A terminal-first code agent expresses these primitives through slash commands, shell safety layers, and remote bridges. A customer-support agent, workflow orchestrator, or AI-powered SaaS feature will implement the same primitive very differently.


## Day one: the non-negotiables


### Tool registry with metadata-first design

**The pattern:** Define your agent’s capabilities as a data structure before writing any implementation code. The registry should answer “what exists and what does it do?” without executing anything.

**What we found:** Claude Code maintains two parallel registries: a command registry with 207 entries for user-facing actions and a tool registry with 184 entries for model-facing capabilities. Each entry carries a name, a source hint, and a responsibility description. The registries are the source of truth. Implementations load on demand.

This is confirmed from implementation surface. The separation is structural, not inferred.

**Why this is day one:** Without a registry, you can’t filter tools by context, you can’t introspect your system without triggering side effects, and every new tool requires changes to orchestration code. The registry is the foundation everything else builds on.

**What you should build:** A `listTools()` function that returns metadata for all registered capabilities without invoking them. Support runtime filtering, because not every tool should be available in every context. Define each tool as `{name, description, required_permissions, input_schema, side_effect_profile}` before writing the function that executes it.


### Permission system with trust tiers

**The pattern:** Not all tools carry the same risk. Categorize them, and apply different approval flows to each tier.

**What we found:** Claude Code segments capabilities into three trust tiers: built-in (always available, highest trust), plugin (medium trust, can be disabled), and skill (user-defined, lowest trust by default). Each tier has different loading behavior, permission requirements, and failure handling.

The shell execution tool alone, BashTool, has an 18-module security architecture. That’s not a typo. Eighteen separate modules, from pre-approved command patterns to destructive command warnings to git-specific safety checks to sandbox determination. Each module can independently block execution. The design philosophy is defense in depth: the pipeline catches different failure modes at different layers.

**Why this is day one:** If your agent can take actions in the world (execute code, call APIs, send messages, modify files) and you don’t have a permission layer, you have a demo, not a product. The 18-module stack for a single tool isn’t paranoia. It’s what separates a system that works safely at scale from one that works safely in a notebook.

**What you should build at minimum:**

- Pre-classification: is this action read-only, mutating, or destructive?
- Pre-approved patterns: known-safe operations that skip expensive checks
- Destructive detection: flag actions that delete, overwrite, or can’t be undone
- Domain-specific safety: targeted checks for your specific risk vectors
- Permission logging: record every decision, granted and denied, with enough context to replay it


### Session persistence that survives crashes

**The pattern:** Your agent’s session is more than the conversation history. It’s a recoverable state object that includes the conversation, usage metrics, permission decisions, and configuration. If any of those are missing when you resume, the session behaves differently than the original.

**What we found:** Claude Code persists sessions as JSON files on disk, capturing session ID, messages, and token usage (input and output). The query engine can be fully reconstructed from a stored session: load, reconstruct transcript, restore counters, return a functional engine.

**Why this is day one:** Agents crash, connections drop, users close tabs. If your agent can’t resume where it left off, including what tools were available, what permissions were granted, and how many tokens were consumed, then every interruption is a restart, and every restart is a degraded experience.

**What you should build:** A `SessionState` structure that captures everything needed to resume. Persist after every significant event, not just at shutdown. Build a `resumeSession(id)` function that reconstructs full agent state, not just conversation history.


### Workflow state and idempotency

**The pattern:** Resuming a conversation is not the same thing as resuming a workflow. A chat transcript answers “what have we said?” Workflow state answers “what step are we in, what side effects already happened, is this operation safe to retry, and what should happen after restart?”

**What’s missing from most agent discussions:** This one. Almost every agent framework conflates conversation state with task state. They’re different problems with different solutions.

**Why this is day one:** Without workflow state, your agent can’t survive a crash mid-tool-execution without potentially duplicating a write, double-sending a message, or re-running an expensive operation. Without idempotency keys, retries are dangerous.

**What you should build:** Model long-running work as explicit states: `planned`, `awaiting_approval`, `executing`, `waiting_on_external`, `completed`, `failed`. Persist workflow checkpoints after every side-effecting step — if you grew up saving your game every two minutes because you didn’t trust the computer not to crash, you already understand the instinct. Give mutating operations idempotency keys so retries don’t double-fire.


### Token budget tracking with pre-turn checks

**The pattern:** Your agent needs a budget, not just a context window limit. The budget should be checked *before* the expensive API call, not after.

**What we found:** Claude Code’s query engine configuration defines hard limits: maximum turns, maximum budget tokens, and a compaction threshold. Every turn calculates projected token usage. If the projection exceeds the budget, execution halts with a structured stop reason (`max_budget_reached`) *before* the API call is made. The implementation makes this explicit.

**Why this is day one:** Without budget tracking, you discover you’ve exceeded limits after you’ve already spent the money. Worse, a runaway loop or a prompt injection that produces verbose output can drain your budget silently.

The leaked source code contains a vivid example of exactly this. Someone fed the codebase to OpenAI’s Codex for analysis and pinpointed the culprit behind Claude Code’s notorious token consumption: the autoCompact mechanism, which handles automatic context compression. When compaction fails, it retries indefinitely with no upper limit. According to source code comments, one session failed consecutively 3,272 times — silently burning through tokens in the background while the user wondered why they’d blown through their rate limit after two uses. The fix was three lines of code: a `MAX_CONSECUTIVE_AUTOCOMPACT_FAILURES = 3` constant. That’s it. Anthropic’s own engineer, Lydia Hallie, acknowledged publicly that users were hitting usage limits far faster than expected. Three lines of budget guardrail code, missing from a $2.5 billion product.

[![](https://substackcdn.com/image/fetch/$s_!_waa!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd20925d9-f1e9-435c-8e8d-a5b4b4e84400_1206x1194.png)](https://substackcdn.com/image/fetch/$s_!_waa!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd20925d9-f1e9-435c-8e8d-a5b4b4e84400_1206x1194.png)

Cost tracking is an observability signal, not just a billing line item. What’s interesting is that these budget checks work against Anthropic’s short-term revenue interest — you’d think they’d want customers burning tokens. But it’s the same logic Amazon applies to returns: short-term revenue loss builds the long-term trust that sustains the business.

**What you should build:** A running total of input and output tokens per session. A pre-turn budget check that switches the agent to “wrap up” mode when approaching the limit. Exposure of budget status to the user. Cost threshold alerts that catch anomalies early.


### Structured streaming events

**The pattern:** Streaming does more than show text progressively. Each streaming event is an opportunity to communicate system state: which tools the agent is considering, how many tokens have been consumed, whether the agent is wrapping up.

**What we found:** Claude Code’s query engine emits typed events: `message_start`, `command_match`, `tool_match`, `permission_denial`, `message_delta`, and `message_stop`. The final event carries usage statistics and a stop reason. This is how the frontend knows *why* the stream ended, whether from completion, budget, error, or cancellation.

If you use Claude Code, you’ve experienced this directly. I watch the streaming events constantly, and I’ll sometimes intervene mid-thought because I can see from the event stream that the model is heading somewhere I don’t want it to go. That kind of real-time course correction is only possible because the events communicate meaningful state, not just text fragments.

**What you should build:** Typed stream events, not just text chunks. Include metadata in events: tool selections, permission decisions, usage. Define explicit start and stop events that bracket each response, with the stop reason in the final event.


### System event logging

**The pattern:** When something goes wrong, the conversation transcript tells you what the user and agent *said*. The system log tells you what the system *did*.

**What we found:** Separate from the conversation, Claude Code maintains a `HistoryLog` of system events: context loading, registry initialization, routing decisions, execution counts, permission denials, session persistence events. Each event is categorized and carries structured detail.

**What you should build:** A system event log separate from the conversation. Log initialization events, tool selections, permission decisions, error events, and session persistence events. Make it human-readable enough that a developer can scan it fast.


### Basic verification harness

**The pattern:** Observability tells you what happened. Verification tells you whether the system is still good. Without a verification layer, prompt tweaks, tool changes, and model swaps silently degrade behavior until users report it.

**What you should build on day one:** A small set of invariant tests: destructive tools always require approval, structured outputs validate against schema, denied tools never execute, budget exhaustion produces a graceful stop. Run these when you change prompts, models, tools, or routing logic. This is the primitive that prevents you from shipping regressions.


## Week one: operational maturity


### Tool pool assembly

Not every conversation needs every tool. Claude Code assembles a session-specific “tool pool” based on mode flags, permission context, and deny-lists at both exact-name and prefix levels. Fewer tools means smaller system prompts, faster model responses, better security, and lower token cost. Build a tool assembly step that selects appropriate tools based on task type, permission level, and workflow phase.


### Transcript compaction

Conversation history is a managed resource, not an append-only log. Claude Code automatically compacts after a configurable number of turns, keeping recent entries and discarding older ones. The transcript store tracks whether it’s been persisted to avoid data loss. Build automatic compaction with a configurable threshold, and when compacting, summarize rather than truncate. Preserve context while reducing token count.


### Permission audit trail

Claude Code tracks every permission denial as a structured data object (tool name and reason) and accumulates denials per session, including them in turn results. Three separate permission handlers serve different contexts: interactive (human in the loop), coordinator (multi-agent orchestration), and swarm worker (autonomous execution). Make permission decisions first-class data, not just boolean gates.


### The doctor pattern

Claude Code has a dedicated health check command that inspects the system and reports problems. Build a `/doctor` endpoint that validates API credentials, external connections, configuration integrity, tool availability, and resource health. Run it at startup and expose it as an admin command.


### Staged boot sequence

Claude Code’s initialization is a 7-stage pipeline: prefetch (credentials, project scanning), environment guards, CLI parsing with a trust gate, parallel initialization of workspace and registries, trust-gated deferred loading (plugins, skills, MCP servers), mode routing, and main loop. Each stage is gated on the previous. The key insight: your agent should have situational awareness *before* the user’s first prompt. Pre-validate credentials, pre-scan the workspace, parallelize what you can.


### Stop reason taxonomy

Every way a conversation can end should have a name. Claude Code defines explicit stop reasons (`completed`, `max_turns_reached`, `max_budget_reached`) and checks conditions *before* processing, not after. Your taxonomy should include at minimum: completed, budget exceeded, turn limit, user cancelled, error, and timeout. Return the stop reason to the caller so the UI can show appropriate messaging.


### Provenance-aware context assembly

Context quality depends on trust as much as relevance and token size. If your agent retrieves project memories, prior summaries, web results, and documentation snippets, every fragment needs metadata: where it came from, when it was generated, how trustworthy it is, whether it’s instruction-like or evidence-like, and whether something newer contradicts it.

This is a design hypothesis more than a confirmed pattern, but it’s one of the most important ones. Without provenance-aware context assembly, memory and retrieval become another prompt-injection surface. Instruction-like text in retrieved context can silently become a new system prompt.


## Month one: scale and sophistication


### Agent type system

Claude Code defines 6 built-in agent types (explore, plan, verification, guide, general purpose, and statusline setup), each with its own prompt, allowed tools, and behavioral constraints. An explore agent can’t edit files. A plan agent doesn’t execute code. The transferable lesson isn’t to spawn agents randomly — it’s to constrain roles sharply when you split work at all. Most products don’t need multi-agent coordination. But if you do split work, define role, allowed tools, denied tools, and output expectations for each agent type.


### Memory system

Claude Code has an 8-module memory subsystem with relevance scoring, aging, type categorization, and scoping (personal, team, project). Separate from persistent memory, it maintains session memory for things learned during a conversation that don’t need to persist forever. The key insight: memory without provenance becomes accumulated hallucination. Store where each memory came from, whether it was user-stated or model-inferred, when it was last validated, and whether newer evidence contradicts it.


### Skills and extensibility

Claude Code supports 20 skill modules: bundled skills, user-defined skills loaded from a directory, and skills auto-generated from MCP server capabilities. Skills are the middle ground between “the agent does everything from scratch” and “the developer hard-codes every workflow.” Each skill is a self-contained unit with a trigger, a prompt template, tool requirements, and input/output contracts.


### The rest of the stack

The remaining primitives (hooks architecture for cross-cutting concerns, with 104 hook modules in Claude Code; multi-agent coordination with a dedicated coordinator layer; analytics with A/B testing and a killswitch; configuration migrations; and multi-transport architecture) represent the long tail of production maturity. They matter. They’re well-implemented in Claude Code’s source. But they’re month-one concerns, not day-one concerns, and the biggest risk for most teams is over-engineering the sophisticated stuff before the fundamentals are solid.


## The confirmation you didn’t expect

One of the most striking things about the community response to this leak: within hours, a developer named Sigrid Jin, who the Wall Street Journal profiled for consuming 25 billion Claude Code tokens, published a clean-room Python port of the core harness architecture. The backstory, as Jin recounted in his repository README: he woke at 4 AM on March 31 to his phone blowing up with notifications. His girlfriend in Korea was worried he might face legal action just for having the code on his machine. So he sat down, ported the core features to Python from scratch using an AI orchestration tool, and pushed before sunrise. The repo hit 30,000 stars within hours.

The team’s solution was to make it a clean-room implementation rather than a copy, rewriting the harness patterns from scratch using OpenAI’s Codex. Then someone on the team decided Python was too slow, and now a Rust port is underway.

The legal question (is a clean-room architectural reimplementation “fair use”?) is genuinely unresolved and worth watching. But the engineering signal is unambiguous. The same architectural primitives transfer across languages, frameworks, and vendors because they’re structural requirements of the problem, not Anthropic-specific patterns. The developers porting this code independently converged on the same conclusion: the primitives are the value, not the implementation.

The DMCA response itself became another chapter in the operational pattern. Anthropic filed mass takedown requests with GitHub, but the net was cast so wide it caught legitimate forks of their own open-source Claude Code repository — repos that never contained the leaked source. Theo Browne, creator of t3.gg and one of the most visible developers in the TypeScript community, posted the takedown notice he received for a fork that contained nothing but a skill edit from weeks earlier. Gergely Orosz, whose Pragmatic Engineer newsletter reaches hundreds of thousands of developers, flagged it publicly: Anthropic was issuing DMCA requests on code that didn’t infringe, which is itself a legal problem. Boris Cherny, Claude Code’s founding engineer, responded that it wasn’t intentional and that they were working with GitHub to correct it. The technology works. The operational response around it keeps tripping.

[![](https://substackcdn.com/image/fetch/$s_!02IC!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2af9a910-3c86-4518-965f-4fffbeaa3e93_595x864.png)](https://substackcdn.com/image/fetch/$s_!02IC!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2af9a910-3c86-4518-965f-4fffbeaa3e93_595x864.png)


## LINK: What we’re releasing: [the agentic harnesses skill](https://github.com/NateBJones-Projects/OB1/tree/main/skills/n-agentic-harnesses)

Reading about primitives is useful. Having something that pressure-tests your system against them is better.

Today I’m releasing `nate-agentic-harnesses`, a skill package built for both **Claude Code** and **OpenAI Codex** that puts everything in this article to work. It’s the tool I wish existed when I started designing agentic systems, and it’s free.


### What it does

The skill has two modes.

**Design mode:** You describe the product you’re building (a chat assistant, a workflow orchestrator, a code agent, an embedded AI feature, whatever) and the skill walks you through a structured design process. It recommends a harness shape, identifies the minimum useful set of primitives, sequences the implementation into phases, and defines verification criteria before you write a line of code. It doesn’t generate boilerplate. It generates architecture with rationale.

**Evaluation mode:** You point it at your existing harness (your codebase, your CLAUDE.md, your architecture docs, your settings and hooks) and it tells you what’s missing. It evaluates across every dimension in this article: architecture, safety and permissions, state and durability, context and memory, user experience, observability, and evaluation coverage. It returns findings ordered by severity, a prioritized upgrade path, and specific tests that confirm the fixes work.

It also supports a combined design-plus-evaluation mode, for when you need both a target architecture and a gap analysis against where you are today.


### Why it’s a skill, not a document

This matters, and it’s worth explaining.

A static document, even a good one, gives you principles to internalize before you go build. Most people understand the primitives and then apply them wrong anyway. The distance between knowing and implementing correctly is where most agent projects quietly die.

A skill is different. It’s an interactive system that has been loaded with all twelve primitives, the priority framework, the evaluation rubrics, the design playbook, and the example patterns, and it applies them *to your specific architecture* in real time. It asks about your product, your constraints, your users, and your existing system. It reads your code. Then it gives you tailored output: this is what you’re missing, this is the priority order for your context, these are the acceptance criteria.

Think of the difference between reading a building code manual and having a structural engineer walk your site. Both are valuable. The second one catches the things the manual can’t, because it’s responding to what’s actually in front of it.


### Why two platforms

I built the skill for both Claude Code (as a Claude skill package) and OpenAI Codex (with Codex-specific metadata, path patterns, and agent routing). The core logic, the primitives, the evaluation dimensions, the design playbook, is identical. The adaptation layer handles how each platform discovers and renders the skill.

This was a deliberate choice, not a marketing exercise. If the thesis of this article is that these primitives are universal, that they apply regardless of your LLM, framework, or language, then the tool that applies them should work across platforms too. Shipping it for only one platform would undermine the argument.


### What’s inside

The skill is structured as a router with progressive disclosure. The SKILL.md file handles classification and routing. Eleven reference files cover the full primitive taxonomy:

- Principles and solo-dev defaults (start here for almost every request)
- Harness shapes and architecture
- Tools, execution, and permissions
- State, sessions, and durability
- Context, memory, and evaluation
- Agents and extensibility
- UX, observability, and operations
- Design and build playbook
- Evaluation and improvement playbook
- Example requests and output patterns
- Codex translation notes

The skill reads only the files it needs per request. A simple design question loads three files. A comprehensive evaluation loads four or five. It never dumps the entire reference set into context, because consistent with the primitives in this article, it treats context as a scarce resource.


### The default posture

The skill is opinionated. It biases toward lean, solo-maintainable architecture — single-agent design unless your constraints clearly justify more. Evaluation plans are required even for greenfield builds. Explicit system boundaries and permission policy over prompt cleverness.

This is intentional. The most common mistake I see in agentic system design isn’t under-engineering. It’s over-engineering, building a multi-agent coordination layer before you have a working permission system, or implementing a plugin marketplace before your sessions survive crashes. The skill pushes back on unnecessary complexity because premature complexity is where most agent projects die.


### How to get it

**[Both packages are available for download today](https://github.com/NateBJones-Projects/OB1/tree/main/skills/n-agentic-harnesses):**

- **Claude Code:** Drop the `nate-agentic-harnesses` folder into your skills directory
- **Codex:** Drop the `nate-agentic-harnesses` folder into your Codex project with the included `agents/openai.yaml`

The reference files are identical across both platforms. The skill works immediately with no API keys, no configuration, and no dependencies.


## What this changes for you

Claude Code’s architecture — 29 subsystems, 207 commands, 184 tools, 564 utility modules, 104 hooks — is the most complete public example of what production agentic infrastructure actually looks like. What struck me most going through all of it is how much of this is, at bottom, good backend engineering. The tools are new, the models are new, but the discipline that makes them work at scale (session management, permission systems, crash recovery, observability) is the same discipline that has always separated systems that ship from systems that demo well. The value lies in understanding what problems each layer solves, so you can build the right layers for your own system.

If you’re starting from scratch, the day-one primitives give you a build order. If you’re debugging a system that works in demos but breaks in production, the taxonomy tells you where to look. And if you’re evaluating whether your team’s agent architecture is ready for real users, the skill package gives you a structured way to find out.

What matters from here isn’t how carefully you read the leaked code. It’s whether you can look at your own agent’s architecture and name the primitives that aren’t there yet.

[![](https://substackcdn.com/image/fetch/$s_!gU04!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4334fee7-b898-48d7-81aa-cbdaf7e5ed94_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!gU04!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4334fee7-b898-48d7-81aa-cbdaf7e5ed94_1024x1024.png)
