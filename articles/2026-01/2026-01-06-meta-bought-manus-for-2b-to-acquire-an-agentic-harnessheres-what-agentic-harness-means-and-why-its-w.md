---
title: "Meta bought Manus for $2B to acquire an \"agentic harness\"—here's what \"agentic harness\" means and why it's worth $2B (yes really)"
author: "Nate Jones"
published: 2026-01-06
url: https://natesnewsletter.substack.com/p/meta-bought-manus-for-2b-to-acquire
subtitle: "Meta paid $2B for a team that divulged their secrets in engineering posts. Why? Here's why, and what that acquisition tells us about where models and AI agents are going in 2026."
audience: everyone
scraped_at: 2026-01-06 12:41:09
---

Meta just paid over $2 billion for a company whose core product is, technically, a wrapper around someone else’s models.

Not a breakthrough in reasoning. Not a new architecture. A wrapper—and that’s exactly why the deal makes sense.

The single most misleading idea in AI right now is that “agents” are a model capability. They’re not. What people experience as an agent that finishes is almost always a *harness*—a pile of engineering wrapped around a model that turns probabilistic text generation into a system that can take actions, remember state, recover from errors, and keep going until the job is done. Manus became the poster child for reliable finishing, and that’s what Meta bought: not the model underneath, but the production know-how that makes a model behave like a worker over time.

Think of it this way: an AI agent is the engine. A harness is the car. You don’t get your V12 engine very far down the road without a car!

[![](https://substackcdn.com/image/fetch/$s_!bg-d!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffb1fa3af-c8c2-444d-bf9f-3fb409a43254_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!bg-d!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ffb1fa3af-c8c2-444d-bf9f-3fb409a43254_1024x1024.jpeg)

In 2026, “agentic harness” becomes one of the core concepts that executives and builders have to learn, because it explains things that otherwise seem baffling. Why can one team ship reliable agentic workflows while another team—using the exact same models—can’t get anything to production? Why would Meta pay billions for a company that doesn’t train its own frontier model? Why does “just use a better prompt” fail as advice for serious agent work? The answer to all three questions is the same, and this piece is my attempt to make that answer clear enough to use.

**Here’s what’s inside:**

- **What an agentic harness actually is** — a plain-language definition that holds up under scrutiny, plus the components that separate demo-ware from production systems
- **Why finishing is hard** — the math of multi-step reliability, and why even small per-step errors compound into total failure over the course of 50 tool calls
- **Why harness innovation is a moving target** — and why you’d pay a premium to acquire a team that has already gotten good at it
- **The specific techniques Manus published** — not just what they do, but why each technique works at the level of attention and inference
- **Why Meta bought the team, not the tech** — and what their “standalone plus integrate” framing signals about how they view the asset
- **The trust boundary problem** — why agents that actually finish require real permissions, and what that means for governance
- **Three alternatives with a decision framework** — not just features and policies, but a way of thinking about which harness fits which kind of work
- **The handmade car problem** — why harnesses won’t standardize the way SaaS did, and what that means for build-versus-buy decisions in 2026
- **The Finishing Framework** — a 20-task diagnostic bank with 7-axis scoring for evaluating harnesses, Anthropic’s composable patterns and LangGraph primitives for building them, and power-user patterns for Claude Code including CLAUDE.md configuration, permissions tuning, and team workflows via slash commands
- **What this means for your work** — different implications depending on whether you’re an executive, a builder, or an individual user trying to get things done

Bottom line: this is a deep dive into why finishing matters for AI agents in 2026, what it actually looks for a team to be focused on building an agentic model harness that finishes, plus a look at how to find (and build) agents that finish work for you this year.

Because 99% of the value is in getting the job done, not starting it. Let’s jump in!


## **[GRAB THE FRAMEWORK](https://docs.google.com/document/d/1PkpWZxxqLXUzXiOd1_fdjP_U0s1DFmo_FTKuRo9l3bE/edit?usp=sharing)**

The single most misleading idea in AI right now is that “agents” are a model capability. They’re not. What people experience as an agent that finishes is almost always a harness—a pile of engineering wrapped around a model that turns probabilistic text generation into a system that can take actions, remember state, recover from errors, and keep going until the job is done.

The framework below has three parts.

**Part 1: Evaluating Harness Quality.** A 20-task diagnostic bank organized into five buckets—tool reality, long-horizon coherence, error recovery, verification discipline, and constrained knowledge work—each designed to trigger different failure modes. A 7-axis scoring sheet (0–4 per axis) that gives you shape, not just pass/fail: outcome correctness, autonomy, tool competence, recovery behavior, context integrity, verification discipline, and economics. A comparison protocol that controls for harness surface area so you’re actually comparing tools, not comparing your own standards.

**Part 2: Architecture Patterns for Builders.** Anthropic’s composable patterns that actually ship—orchestrator-workers, evaluator-optimizer loops, routing, parallelization—translated into harness primitives. The artifact spine for long-running work: PLAN.md, TODO.md, DECISIONS.md, STATE.json, NOTES.md. LangGraph’s production primitives: persistence and checkpointing, human-in-the-loop interrupts, checkpoint replay. The insight that makes it concrete: agents that finish are agents that can pause, be corrected, and resume without losing work.

**Part 3: Power-User Patterns for Claude Code.** The actual product mechanisms most users never learn. CLAUDE.md as a defined feature—where it lives, how /init generates it, how pressing # captures instructions into it. Four ways to configure permissions so you’re not trapped between constant interruption and unsafe autonomy. Team-scale workflows via .claude/commands with $ARGUMENTS support. The official explore→plan→code→commit loop. When and how to use separate sessions to preserve context. The real constraints on --dangerously-skip-permissions (container isolation isn’t enough if the repo is untrusted).

These aren’t tips. They’re operational frameworks for the finishing problem.

---


### The Most Misleading Idea in AI Right Now

There’s a concept that’s about to dominate AI conversations in 2026, and most people don’t have a name for it yet. The concept is “agentic harness”—or just “harness”—and once you understand it, a lot of things that seemed confusing start to make sense.

Why can one team ship reliable agentic workflows while another team, using the exact same models, can’t get anything to production? Why would Meta pay billions of dollars for a company that doesn’t have its own frontier model? Why does “just prompt it better” fail as advice for serious agent work?

The answer to all three questions is the same: agents are not a model capability. What people experience as an agent that finishes—that grinds through multi-step work, recovers from mistakes, and returns with something you can actually use—is almost always a harness. It’s a pile of engineering wrapped around a model that turns probabilistic text generation into a system that can take actions, remember state, recover from errors, and keep going until the job is done.

This distinction matters more than almost anything else in AI right now, because it determines where you should focus your attention, your hiring, your budget, and your strategic bets. The model is necessary but not sufficient. You can have the most capable model in the world and still build an agent that falls apart at step 12. Or you can have a harness so well-engineered that it makes a weaker model perform like magic. The model is the engine, and the harness is everything else—and “everything else” turns out to be where most of the work lives.


### What an Agentic Harness Actually Is

Let me give you the plain definition that holds up under scrutiny: an agentic harness is the runtime system that makes an LLM behave like a worker over time.

That’s the core of it. But “runtime system” is doing a lot of work in that sentence, so I want to unpack what’s actually inside a harness. Understanding these components matters because when an agent fails—and they fail constantly, in ways that can be maddening to debug—the failure almost always lives in one of these layers, not in the model itself.

The first component is the loop structure. An agent isn’t a single prompt-response exchange; it’s a loop that runs until the job is done. The agent observes its environment, decides on an action, executes that action, observes the result, and repeats. The harness defines how that loop operates: what triggers each iteration, what determines when to stop, how state flows from one step to the next, and what happens when a step fails. Should the agent retry? Skip ahead? Abort entirely? These are harness decisions, not model decisions, and getting them wrong means your agent either spirals forever or gives up at the first sign of difficulty.

The second component is the prompts and serialization layer—the system prompt, the format for presenting observations to the model, the structure for requesting actions. This is where most people think agent work lives, the “prompt engineering” layer that gets all the attention. But it’s actually a small fraction of what makes agents reliable. You can have a perfect prompt and still fail completely if the other layers are broken.

The third component is the tool registry and calling format. What tools can the agent use? How are they defined? What’s the schema for calling them, and what happens when a tool times out, throws an error, or returns garbage? How do you handle tools that require authentication, or tools that have rate limits, or tools that work differently depending on the time of day? The harness manages all of this complexity. And as we’ll see, tool management turns out to be one of the trickiest parts of production agent work—not because individual tools are hard to define, but because having too many tools, or changing which tools are available mid-task, creates reliability problems that aren’t obvious until you hit them in production.

The fourth component is action constraints—rules that limit what the agent is allowed to do at any given moment. Not every tool should be available at every step. Sometimes you want to force the agent to respond to the user before taking another action. Sometimes you want to prevent the agent from accessing certain capabilities until it has completed a prerequisite step. The harness decides what’s legal and enforces those constraints in ways the model can’t override, no matter how cleverly it tries.

The fifth component is the memory strategy, which answers the question of what stays in the context window versus what gets externalized to files, databases, or other storage. This is a crucial question because context windows are expensive—both in literal cost and in cognitive load on the model. Performance degrades as context fills up, not because the information isn’t technically “in there,” but because attention gets spread thin and the model has a harder time focusing on what matters. The harness decides what to keep in context, what to summarize, what to compress, and what to offload entirely. Get this wrong and you either blow your inference budget, degrade your model’s reasoning quality, or lose information the agent will need later to finish the job.

The sixth component is the execution environment—the sandbox where the agent actually takes actions. Is it a virtual machine? A browser session? A file system? A set of API connections? An email account? The harness sets up this environment, maintains its state across steps, cleans up when the task is done, and isolates one user’s agent from another’s. The more capable your agent becomes, the more complex this environment becomes, and the more the harness has to manage.

The seventh component is what I call the accountability layer: evals that check whether the agent is doing what it should, tracing that records every step, audit logs that let you reconstruct what happened, safety checks that catch dangerous actions before they execute, and rollback paths that let you undo mistakes. This is the governance infrastructure that enterprise deployments require, and it’s the layer that most demo-ware completely ignores. If your agent does something wrong, can you see what happened? Can you undo it? Can you prevent it from happening again? These aren’t model capabilities. They’re harness capabilities.

If you want a metaphor, think of it this way: if the model is an actor, the harness is the stage, the script, the director, the lighting crew, the props department, the costume department, and the stage manager who calls the cues and keeps everything on schedule. The actor’s talent matters—you can’t put on a great show with a terrible performer. But you can absolutely have a brilliant actor and still produce a disaster if everything around them is broken.

Or, if you prefer the automotive metaphor that the Manus team used in their own writing: the model is the engine, but you need the chassis, the steering, the brakes, the suspension, and the transmission to actually go anywhere. A powerful engine in a badly designed car is just a fast way to crash.


### Why Finishing Is Hard

Here’s the part that most people don’t think about carefully enough: the math of multi-step reliability.

Let’s say your agent is 95% likely to make the right decision at any given step. That sounds pretty good, doesn’t it? Ninety-five percent accuracy seems like a strong performance. But watch what happens as the number of steps increases.

After 10 steps, your probability of having made the right decision at every step is 0.95 to the 10th power, which works out to about 60%. After 20 steps, you’re down to 36%. After 50 steps—which Manus says is their average task length—even a 95%-accurate agent fails more than 90% of the time. You have less than a 1-in-10 chance of getting through the whole task without a single error.

That’s not a model problem; the model might be making great individual decisions at each step. It’s a system problem: errors compound, and without mechanisms to detect and recover from errors, the agent spirals into failure long before it reaches the finish line.

This is why finishing is hard. It’s not that models can’t reason. It’s that reasoning in a loop, over dozens of steps, without accumulated errors derailing you, requires infrastructure that the model can’t provide on its own. The harness has to solve this problem—or fail to—through several different mechanisms.

The first mechanism is verification loops. If you can check whether a step succeeded—if the code compiles, if the test passes, if the API returns the expected result—then you can catch errors before they compound. This is why coding agents often work better than general-purpose agents: the development environment provides a natural verification loop. The agent writes code, the tests fail, the agent sees the failure and tries again. That feedback mechanism resets the error accumulation because you’re catching problems as they happen rather than letting them propagate.

The second mechanism is goal recitation, and understanding why this works requires knowing something about how transformer attention functions. Attention in transformers is biased toward recent tokens; the model pays more attention to what came last than to what came first. As context grows over the course of a long task, the original objective—stated way back at the beginning—gets less and less attention weight. By step 40, the model is barely “seeing” the goal you gave it at step 1. Goal recitation fights this attention decay by constantly restating the objective near the end of the context, where attention is strongest. You’re pushing the goal into the model’s “working memory” over and over again, reducing drift.

The third mechanism is error preservation, which sounds counterintuitive but turns out to be essential. The natural instinct is to hide errors from the model—to clean up the context and not let the agent see its own mistakes. But Manus and other production agent teams have found that the opposite approach works better. When an action fails—API errors, browser crashes, malformed outputs—leaving the failure visible, including stack traces and error messages, updates the model’s priors within the run. The model learns, in real time, that approach X doesn’t work in this situation, and shifts toward alternatives. Remove the failures, and the model has no evidence that anything went wrong. It might try the same failing approach again.

The fourth mechanism is external memory, which addresses the fundamental tension between context limits and information needs. As context fills up, you face two bad choices: keep cramming more in, which degrades performance and explodes costs, or throw things away, which risks losing information you’ll need later. External memory—writing to files, databases, or structured storage—gives you a third option. You offload information the agent can retrieve later when it needs it. The key insight from Manus is that this offloading must be “restorable”: you drop the content but keep a pointer (a file path, a URL), so the agent can get the full information back if the task requires it.

These mechanisms aren’t tricks or hacks. They’re load-bearing infrastructure. Remove any of them and your agent’s reliability collapses, no matter how capable the underlying model is. The harness is what makes 50-step tasks possible.


### Why Harness Innovation Is a Moving Target

Here’s the part that makes harnesses hard *and* valuable: they’re not stable. Every new model capability, every new tool protocol, every new user interface pattern, and every new failure mode forces harness designs to evolve.

When Claude got better at long-context reasoning, harness designers had to rethink their memory strategies. Approaches that made sense with 32K context windows didn’t necessarily make sense with 200K. When MCP (Model Context Protocol) made it easy to attach hundreds of tools to a single agent, harness designers discovered the “tool explosion” problem—more tools means a more confusing action space for the model, and paradoxically, worse action selection even when the right tool is available. When users started running agents in browsers to automate web tasks, harness designers had to build browser automation that could handle dynamic pages, CAPTCHAs, authentication flows, and websites that change their layout without warning.

The target moves constantly. A harness that worked beautifully six months ago may be obsolete today—not because the code broke, but because better approaches emerged, or new model capabilities made old workarounds unnecessary, or new failure modes appeared in production that nobody had anticipated.

This is why harness work is so hard to outsource to a generic framework. Frameworks can give you the loop structure and the tool-calling format, but memory strategy, action constraints, verification logic, and error recovery all depend on your specific use case, your specific execution environment, and your specific tolerance for failure. The teams that are good at this aren’t just good at writing code. They’re good at empirical iteration—building something, watching it fail in the real world, figuring out exactly why it failed, and rebuilding with that knowledge. Over and over again, for months or years.

Manus says they rebuilt their agent framework four times. They call their development process “Stochastic Graduate Descent”—a joke, but also an honest description of what harness development actually looks like. You don’t prompt your way to a reliable agent. You iterate your way there by rebuilding the harness until it stops falling apart in real usage.

This is why you’d pay a premium to acquire a team that’s already good at harness work. You’re not buying a static asset that you can deploy and forget about. You’re buying a team that has demonstrated the ability to iterate, to discover what works through painful trial and error, and to stay ahead of a moving target. That capability is rare, and it’s valuable, and it’s exactly what Meta bought.


### The Acquisition Story

Let’s back up for a second. Manus is an AI startup that launched what it pitched as a “general” AI agent in early 2025—a system meant to autonomously execute tasks like research, analysis, coding, and creative work rather than just answer questions in a chat interface. The important part isn’t the feature list; plenty of products have similar feature lists. The important part is the reputation Manus developed: people who used it experienced it as unusually good at *reliable finishing*—getting all the way to a complete, usable output without constant babysitting.

Then, at the end of December 2025, Meta acquired Manus. Sources estimated the value in the $2–3 billion range, and Meta said it would integrate Manus into its products, including Meta AI, while keeping Manus running as a standalone subscription product operating from Singapore.

That “standalone” framing should jump out at you. It’s not how you talk when you’re buying a feature to absorb into your existing product. It’s how you talk when you’re buying a capability and a team—because you don’t want to break the thing that works, and you recognize that the value is in the system as it exists, not just in the ideas behind it.

Now, the remarkable part of this story: Manus told us what the real asset is. In July 2025—months before the acquisition—Manus published a candid engineering post called “[Context Engineering for AI Agents: Lessons from Building Manus](https://manus.im/blog/Context-Engineering-for-AI-Agents-Lessons-from-Building-Manus).” In it, they disclosed their core architectural philosophy and the specific techniques that make their agent reliable. This kind of transparency is unusual for a company that would later be acquired for billions, and reading the post, you start to understand why disclosure didn’t hurt them. The gap between understanding these ideas and implementing them at production scale is enormous.

Here’s what they said, and more importantly, why each piece works. And yes, I’m going into detail on how they built Manus because I want you to understand how far into the weeds good teams get to make sure their agents work well! There’s no substitute.


## How Manus Built Manus

The team made a deliberate decision to bet on context engineering instead of training their own models. This wasn’t a resource constraint—it was a strategic choice. They wrote that context engineering let them ship improvements “in hours instead of weeks” and kept the product “orthogonal to the underlying models.” Their metaphor captures it perfectly: “If model progress is the rising tide, we want Manus to be the boat, not the pillar stuck to the seabed.” A boat rises with the tide and benefits from every wave. A pillar just gets submerged.

This is a bitter-lesson bet. The bitter lesson in AI is that general methods leveraging computation tend to win over specialized approaches that bake in human knowledge. Applied to agents: instead of training a specialized agent model—which locks you into that model’s capabilities and takes months to update—you engineer the context that wraps around a general model, which lets you ride model improvements for free and iterate in hours instead of weeks.

They identified KV-cache hit rate as their single most important production metric, and understanding why requires knowing something about how inference costs work. Agents are massively skewed toward long context prefills and short outputs; Manus cites an average input-to-output token ratio around 100:1. You’re putting in a hundred tokens of context for every one token the model generates. KV-cache lets you reuse previously computed context instead of reprocessing everything from scratch on every step. With Claude Sonnet, cached tokens cost $0.30 per million versus $3.00 for uncached tokens—a 10x difference.

But here’s the trap that catches most teams: tiny, seemingly innocent changes to your prompt structure can invalidate the cache and destroy your economics. If you put a timestamp at the beginning of your system prompt—a natural thing to do, since you want the agent to know what time it is—you’ve just guaranteed that every single step will cache-miss on everything that comes after that timestamp. Your costs explode, your latency spikes, and you might not even realize why until you’ve burned through your inference budget.

The Manus team learned to obsess over keeping prompts stable and append-only. They don’t modify earlier parts of the context; they only add to the end. This maximizes the prefix that can be cached across steps.

They tried dynamic tool loading and found it made things worse, which surprised them. As agents gain capabilities—especially with MCP making it easy for users to attach hundreds of tools—the “action space explosion” becomes a reliability killer. The model has to choose among all available tools at every step, and more tools means more confusion, more hallucinated tool calls, and worse action selection even when the right tool is sitting right there.

A natural solution is dynamic tool loading: use RAG-style retrieval to pull in only the tools relevant to the current step, reducing the action space to something manageable. Manus tried this, and it backfired for two reasons. First, changing tool definitions invalidates the KV-cache, because tool definitions typically live at the front of the context right after the system prompt. Change them, and you’re recomputing everything. Second, when earlier steps in the context reference tools that have since “disappeared” (because you dynamically removed them), the model gets confused. The context contains actions that used tools that aren’t defined anymore, which leads to schema violations and hallucinated actions.

Their solution was elegant: mask, don’t remove. Instead of dynamically adding and removing tools, they keep tool definitions stable and use a context-aware state machine combined with constrained decoding to mask unavailable tools. The tools stay in the context—so the cache stays valid, and the model never sees inconsistencies between past actions and current tool definitions. But at decoding time, Manus uses logit masking to make certain tools unselectable. The model literally can’t generate tokens that would call a masked tool. Same behavioral result, much more stable infrastructure. This is a harness move, not a model move. You’re not asking the model to be smarter about tool selection; you’re engineering the runtime to constrain what the model can do.

They use the file system as external memory, treating it as the “ultimate context” that’s unlimited, persistent, and directly operable by the agent. Even 128K+ token context windows aren’t enough for real-world agentic tasks—web pages are huge, PDFs are huge, codebases are huge—and model performance degrades as context fills up. Their approach is what they call “restorable compression”: you can drop big observations from the prompt, like full web page content, as long as you keep the URL or file path. The agent knows the information exists and can retrieve it if needed. You’re trading context space for an extra retrieval step, and that’s often a good trade.

This is why Manus agents run in virtual machines with full file system access. The VM isn’t just an execution sandbox; it’s a memory expansion mechanism.

They prevent drift through objective recitation, which works because of how transformer attention functions. As I mentioned earlier, attention is biased toward recent tokens, so the original objective stated at the beginning of a long context gets less and less attention weight as the task progresses. A typical Manus task requires around 50 tool calls on average, and by step 40, the model is barely “seeing” the goal from step 1.

Manus combats this with a behavioral trick: the agent keeps and rewrites a `todo.md` file throughout the task, checking off completed items and restating what remains. This constantly pushes the global plan into the most recent part of the context, where attention is strongest. It’s attention steering without architectural changes—you’re manipulating where the model focuses by changing what appears at the end of the context.

They leave failures visible in the context, which goes against instinct but improves performance. When an action fails—API errors, browser crashes, malformed outputs—they keep the failure visible, including stack traces and error messages. Seeing its own failures updates the model’s priors within the run; it learns that approach X doesn’t work in this situation and shifts toward alternatives. Remove the failures, and the model has no evidence that anything went wrong. It might try the same failing approach repeatedly.

The blog post ends with a line that captures the whole philosophy: “Context engineering defines how fast the agent runs, how well it recovers, and how far it scales.” They say they learned these lessons “through real-world testing across millions of users,” and that’s not a throwaway line. It’s the moat.


### Why Meta Bought the Team, Not the Tech

That blog post is public. Anyone can read it, and now you’ve read a summary of the key ideas. So why couldn’t Meta just reproduce these techniques internally?

Because the scarcity isn’t ideas. The scarcity is production taste and implementation skill under real-world entropy.

You can read the Manus blog post and still fail to build Manus. The gap between “I understand the concept of KV-cache optimization” and “I have a system that maintains 95%+ cache hit rates across millions of diverse user tasks” is enormous. It’s cost control under load—making sure your clever architecture doesn’t blow up your inference budget when traffic spikes. It’s cache discipline when edge cases break your assumptions—handling the user who pastes a 50,000-token document into the first message, or the tool that returns 10MB of JSON. It’s tool governance when users connect weird MCP servers with unpredictable schemas, rate limits, authentication flows, and failure modes. It’s memory design when context windows fill with unexpected junk—the agent that browses to a page full of boilerplate, or the file that’s 99% irrelevant headers.

It’s error recovery when the browser automation hits a CAPTCHA, or the website changes its layout, or the API returns a 500 error on the third retry.

It’s the thousand tiny choices that decide whether the agent finishes or spirals—choices you only learn to make after your agent faceplants at step 37 in a real user’s workflow, and you have to figure out why, and you have to fix it without breaking something else, and then you have to watch it faceplant differently at step 41.

Manus says they learned these lessons “through real-world testing across millions of users.” That sentence describes years of iteration, failure, debugging, and rebuilding. Ideas are copyable. Production know-how is not.

Meta’s own LLM efforts have struggled publicly. Their Llama 4 release was criticized for benchmark issues, and they have a new team working on the next iteration. But they need agentic capabilities now—not in eighteen months. Building from scratch would mean a year of painful rediscovery, relearning lessons that Manus already learned the hard way. Buying Manus means buying people who already know what doesn’t work.

The wrapper is the product, and Meta bought the team that can build the car.


### The Trust Boundary Problem

Here’s something that doesn’t get discussed enough in the excitement about AI agents: agents that finish need real permissions.

If an agent is going to book a flight for you, it needs access to your credit card. If it’s going to send emails on your behalf, it needs access to your email account. If it’s going to manage your calendar, it needs to see your schedule. If it’s going to write code in your repository, it needs write access. The more capable the agent, the more sensitive the permissions it requires.

This creates a governance challenge that’s fundamentally new. With traditional software, you grant permissions to an application, and the application does exactly what its code tells it to do. The behavior is deterministic. You can audit the code. You know what will happen.

With agents, you’re granting permissions to a system that includes a probabilistic model making decisions in a loop. The behavior is not fully deterministic; you can’t audit “the code” because the behavior emerges from model inference, and you don’t know exactly what the agent will do in every situation. The same input might produce different actions depending on what the model attends to, what’s cached, what tool results came back in what order.

This isn’t a reason to avoid agents—the productivity gains are real, and the technology is going to improve. But it is a reason to think carefully about trust boundaries. What can the agent see? What data does it have access to? What actions can it take in the world? What happens when it makes a mistake—can you detect it, and can you undo it? Who is accountable when something goes wrong?

These are harness questions, not model questions. The accountability layer of the harness—the evals, tracing, audit logs, safety checks, and rollback paths—is what lets you answer them. A harness without a serious accountability layer might be fine for demos and experiments, but it’s not ready for work that matters.

This is also why data policy matters more for agents than for traditional AI tools. A chatbot that hallucinates is annoying. An agent that executes a hallucinated action on your email account, or your code repository, or your financial systems, is a real problem. The question isn’t just “does the vendor respect my privacy?” It’s “what happens when the agent acts on my behalf, and what audit trail exists if something goes wrong?”


### The Geopolitical Piece

The China angle in the Manus acquisition is real, but it’s not the soul of the story. It’s the compliance wrapper around the wrapper.

Manus was founded in China by the team behind Monica AI. They moved headquarters from Beijing to Singapore in mid-2025, amid U.S.–China tensions and in preparation for global expansion. The acquisition triggered immediate questions about regulatory approval and data security.

Meta addressed this directly in the acquisition announcement. According to multiple reports, Meta explicitly stated that the deal would “fully sever” Manus’s remaining ties to China: no continuing Chinese ownership interests, discontinuing services and operations in China, shutting down Monica AI, relocating relevant employees, and continuing to geo-block access to Meta’s AI models. Meta also stated that Manus employees joining the company would not have access to customer data.

That’s the compliance packaging, and it’s what made the deal defensible in Washington. But it’s downstream of the real driver. Meta is paying for a finishing-grade harness team. The geopolitical maneuvering is what made the acquisition *possible*; the harness capability is what made it *valuable*.


### What Happens to Your Data at Manus

If you’re using Manus or evaluating it, the data question matters. A finishing agent, by definition, has to persist state, store artifacts, and sometimes operate a browser environment on your behalf. What does Manus say about how they handle that?

Manus’s help center is unusually direct on several key points.

On training and improvement, they say they use only aggregated or de-identified information to improve services—product performance, diagnosing issues, abuse prevention—and they explicitly state they won’t attempt to re-identify that data unless required by law.

On deletion, they say that when you delete your account, your data is “permanently removed and cannot be recovered.” The same applies to deleting individual tasks: task-contained data, including files, websites, and spaces, is permanently removed and cannot be recovered.

On team access, and this is the enterprise reality that matters, they’re explicit that on a Team Plan, a Team Owner can access all session data of team members, including task steps and content, and can export that session data. A separate help article clarifies that tasks are private by default from peer teammates unless explicitly shared. Both statements can be true simultaneously—default peer privacy exists alongside owner override.

On browser automation, since agent finishing often requires web automation, they state that their cloud browser uses encrypted sessions and isolated environments and claim they don’t store passwords.

After the acquisition, the “what changes” that you can responsibly say is not “Manus will definitely do X with your data now.” It’s that Meta has publicly emphasized access separation as part of the transaction posture—employees joining Meta won’t have access to customer data. This is not being treated like a normal consumer acquisition; it’s being treated like a sensitive capability purchase, with explicit boundary-setting from day one.

If you use agents for sensitive work, the practical guidance is simple: treat any ownership change as a moment to re-check the vendor’s policies and controls, because the incentives and compliance pressures changed even if the user interface didn’t.


### Three Alternatives and How to Choose Among Them

If you’re worried about Manus falling under Meta’s data policies—and anecdotally, many users are already migrating—here are three alternatives worth evaluating.

But before I describe them, I want to give you the framework for thinking about this, because the worst thing you can do is treat these as interchangeable products that differ only in features and price. They’re not. They’re different harnesses, built by different teams, for different environments, with different philosophies about how agents should work.

The right question isn’t “which one is best?” The right question is “which one is best for the kind of work I need done?”

Start by asking yourself what your verification loop looks like. If your work has a way to mechanically check whether the agent succeeded—tests pass, code compiles, output matches a schema—then you can use a harness optimized for that tight feedback loop. If your work is open-ended with no clear, machine-checkable success criterion, you need a harness that can handle ambiguity and give you visibility into what it’s doing.

Then ask yourself what environment the work lives in. Is it a codebase? A productivity suite with documents and spreadsheets? A browser navigating arbitrary websites? Email and calendar? Each harness is optimized for a particular environment, and trying to use one outside its natural habitat means fighting against the design rather than working with it.

Consider how much you need to control each step. Some harnesses are “fire and forget”—you give a goal and wait for results. Others give you visibility and intervention points at each step. The right choice depends on how much you trust the agent with your particular task and how much you need to steer it along the way.

And think about your data sensitivity. All three alternatives I’m about to describe route through external model providers like Anthropic, OpenAI, and Google. If you need zero data retention or air-gapped execution, you need a self-hosted solution, and none of these will work for you.

---


#### Claude Code

Claude Code is Anthropic’s agentic coding product. It lives in your terminal and development environment, executing tool calls through your local system rather than in a cloud sandbox. It’s not trying to be a general life agent that handles everything; it’s a harness designed specifically for software work.

The reason it works well for finishing is that software development has something most domains don’t: an external source of truth and a built-in verification loop. The repository is the truth. The tests tell you whether the code works. The compiler tells you whether the syntax is valid. This constraint makes long-running behavior more stable because the agent can check its own work at every step. It writes code, the tests fail, it sees the failure, and it tries again. That feedback mechanism resets the error accumulation that otherwise dooms multi-step agents.

Claude Code runs locally, which changes the trust model compared to cloud-based agents. Your code doesn’t leave your machine and go to a VM somewhere; the agent operates on your system with your permissions. That’s more powerful—full file system access, local tool execution, direct integration with your development environment—and also more risky, because the agent can do whatever you can do.

The harness has absorbed many of the same patterns Manus published. It writes goals to markdown files. It has Skills, which are user-teachable capabilities that persist across sessions. It has eval loops that check whether the work is complete. The “Ralph Wiggum” pattern that circulated on Twitter over the holidays—a script that feeds back the output and asks the model whether it’s done, looping until it confirms—is exactly the kind of goal recitation trick that Manus uses.

On data policy, Anthropic is unusually explicit. Consumer users who opt into data use for model improvement have a 5-year retention period for that data in de-identified form; those who opt out stay at 30-day retention. Commercial API users have 30-day standard retention and can configure zero data retention with appropriate API keys. Before you point Claude Code at sensitive repositories, understand which regime you’re in and make a conscious choice.

Claude Code is best for work that lives in a codebase: fixing bugs, building features, refactoring, writing tests, anything where “done” means “the tests pass” or “the code compiles.” It’s less suited for open-ended research, document creation, or tasks where success is ambiguous. If there’s no verification loop, you’ll spend time shepherding that you wouldn’t spend on well-defined coding tasks.

---


#### GenSpark

GenSpark is best understood as a harness for producing business artifacts inside an AI workspace. Slides, sheets, docs, images, video—you give it a prompt, and the system orchestrates nine specialized models and over 80 tools to produce the output. They position it as “AI Slides, AI Sheets, AI Docs... One prompt, job done.”

The reason it works for finishing is that it’s oriented around artifact generation, where the success criterion is implicit and relatively clear. You asked for a deck, so did you get a deck? You asked for a spreadsheet, so did you get a spreadsheet? That clarity makes the finishing problem more tractable than open-ended “do research on X” requests, where it’s not obvious when you’re done.

The phone call feature, which they call “Call For Me,” is worth noting because it’s genuinely agentic in a way that artifact generation isn’t. The system makes real phone calls with AI voice, handling conversations in real time. It went viral in Japan for handling resignation calls to employers—something that’s culturally difficult to do directly in Japanese business culture. That’s the agent doing real work in the world, not just generating documents.

GenSpark achieved unicorn status in November 2025 after a $275 million Series B round, and they’re shipping features rapidly. Whether their finishing reliability matches Manus is something you’ll have to test empirically on your own tasks. Having run similar jobs through both systems, I found Manus slightly more consistent, but GenSpark has a fire lit under them now and that gap may close quickly.

On data policy, the iOS App Store listing points to MainFunc’s privacy policy. That policy states that queries may be transmitted to third-party model APIs like OpenAI and Anthropic. It explicitly affirms that while GenSpark may use Google Workspace APIs for specific services, those APIs are “not used to develop, improve, or train generalized AI/ML models.” Closed accounts have data deleted within 30 days. That’s a legible policy posture for a productivity suite that routes through multiple model providers.

GenSpark is best for business artifact creation when you have a clear goal: turn these notes into a deck, build a spreadsheet that tracks X, draft a document summarizing Y. The productivity suite environment is their home turf. It’s less suited for highly custom workflows that need fine-grained control at each step, or for complex multi-system orchestration that goes beyond the productivity suite environment.

---


#### DoAnything.com

DoAnything is the most ambitious of the three, and also the earliest-stage. It positions itself as a general execution harness that spans tools and environments, explicitly advertising access to 10,000+ tools across 2,700+ APIs. Their public tutorials showcase an agent toolkit that includes email, phone calls with AI voice, browser navigation, deep research, code execution, document and file handling, website building, image generation, subagents, and slides.

Unlike Manus, which frames itself as “complete this task,” or GenSpark, which frames itself as “produce this artifact,” DoAnything frames itself around ambitious, long-term goals. During signup, you’re prompted to set something like “start a business for me” rather than “build this slide deck.” Agents have names and email addresses. The philosophy is “work on this objective over an extended period,” not “finish this discrete task in the next hour.”

Where it struggles is that the finishing aspect isn’t solved yet. When I tested it with a large goal, what came back was thoughtful—lots of research, planning, structured analysis—but it still wanted me to do significant work myself. The promise is broader than the current execution.

My read on DoAnything is that the team is aiming at where the puck is going rather than where it is now. They’re betting on model improvements in 2026 that will make this scope of goal viable, and they’re building the harness infrastructure now so they’re ready when the models catch up. That’s a reasonable bet, but it means the product is ahead of its time in ways that affect reliability today.

On data policy, their privacy policy, updated in January 2026, is unusually transparent for a young startup. It explicitly lists what it collects—account information, messages and conversations, usage data, device identifiers—and names its third-party providers: cloud hosting through Vercel and Neon, AI models through Anthropic, OpenAI, and Google, and Twilio for SMS verification. Retention is stated as “as long as necessary” for service provision, legal compliance, disputes, and improvement, and users can request deletion.

The transparency is good. The tradeoff is that a harness this broad, routing through this many providers, means more surfaces where your data exists. The question isn’t whether they’re being honest—they clearly are—but whether the architecture itself matches your data sensitivity requirements.

DoAnything is best for exploration and experimentation. If you want to see what ambitious agentic goal-setting looks like and you’re willing to tolerate beta-level reliability, it’s worth testing. If you need something finished reliably this quarter, look elsewhere for now. Check back in six months.

---


### The Handmade Car Problem

Here’s the uncomfortable truth about agentic harnesses in 2026: we are in the handmade age of cars.

In the early automotive era, every car was artisanal. Each manufacturer had different approaches to steering, braking, transmission, and fuel systems. You couldn’t swap parts between makers. If your Ford broke down, you needed Ford parts and a mechanic who knew Fords. There was no standardization. You picked a car built by a specific team, with a specific philosophy, and you accepted its tradeoffs—because that was the only option available.

Agentic harnesses are in exactly that era right now.

Claude Code is not the same as GenSpark is not the same as DoAnything is not the same as Manus. They’re not interchangeable products with feature parity that you can swap based on price, the way you might swap between similar SaaS tools. They’re different teams’ answers to the finishing problem, built for different environments, with different philosophies about memory, tools, verification, and governance.

This is genuinely different from traditional software. In the 2010s, if one CRM got acquired and you didn’t like the new owners, you could usually find a near-identical competitor. The features had converged. The data models were similar. Migration was painful but conceptually straightforward, because the products had evolved toward the same shape.

Harnesses don’t work that way, at least not yet. Each one reflects hundreds of micro-decisions about context management, tool orchestration, error handling, and goal tracking. The path-dependence matters enormously. A team that iterated their way to a specific set of answers won’t converge to the same place as another team starting fresh. Some of their choices will be better, some will be worse, but they won’t be the same choices—and if you’ve built your workflow around one harness’s assumptions, you can’t just lift and shift to another.

This is partly what made Manus valuable enough to acquire for over $2 billion. The Manus team had arrived at a specific, battle-tested set of answers through four framework rebuilds and millions of users. Another team building from scratch might produce something good, might even produce something better in some dimensions, but they wouldn’t produce the same thing. The specific combination of techniques—the KV-cache discipline, the mask-don’t-remove tool management, the file-system memory, the objective recitation—isn’t obvious or inevitable. It’s the result of years of iteration.

Will harnesses eventually standardize? MCP is an attempt to standardize tool connections, and it’s working; MCP adoption is growing, and tools are becoming more portable across harnesses. That’s a real step toward interoperability.

But MCP doesn’t standardize memory strategy. It doesn’t standardize verification logic. It doesn’t standardize action constraints, error recovery, or governance. Those layers are still harness-specific, and I expect them to remain differentiated for some time, because they depend so heavily on the specific use case and execution environment.

My guess is that some layers will standardize—tool connection, basic loop structure—while others remain differentiated—memory, verification, governance. We’ll see harness “platforms” emerge that handle the commodity layers, with teams building differentiated products on top. But that’s 2027 or 2028. For 2026, expect harnesses to remain bespoke.

This changes the build-versus-buy calculus for enterprises. Building a harness from scratch is hard. It requires a team that can iterate through failure, that understands the production constraints, that can evolve the system as models and tools change. Most companies don’t have that team, shouldn’t try to build it, and should focus their engineering resources on their actual core competencies.

But buying a harness means accepting that team’s philosophy. Their memory model. Their tool format. Their verification approach. Their governance assumptions. If those don’t fit your needs, you’re fighting against the design, and that fight is exhausting and expensive.

The middle path—using a harness platform that handles the commodity layers while you build differentiated logic on top—is emerging but still immature. LangChain and similar frameworks offer this, but the reliability gap between “framework demo” and “production system” is still large.

For most companies in 2026, the right answer is probably: buy a harness that fits your primary use case, accept its constraints, and don’t expect to migrate easily. Choose carefully, because you’re making a commitment.


### What This Means for Your Work

The implications are different depending on who you are and what you’re trying to accomplish.

If you’re an executive, the main shift is in the questions you should be asking. Stop asking “which model should we use?” and start asking “what’s our harness strategy?” The model matters less than you think; your team can probably get 80% of the value from any of the top-tier models. The harness is where reliability, cost control, and governance live, and that’s where you should focus your attention.

When you’re evaluating agentic products, ask the vendor what verification loops the harness uses to catch errors before they compound. Ask how it handles failures—does the agent learn from its mistakes within a run, or does it just retry blindly? Ask what audit trail exists—can you reconstruct what the agent did and why? Ask about data retention policies and how they handle requests for deletion. Ask how costs scale as usage grows—is the architecture efficient, or will your inference budget explode when you move from pilot to production?

If the vendor can’t answer these questions clearly, they haven’t solved the finishing problem. They’ve built a demo, and demos don’t ship.

If you’re a builder, the model is the easy part. Integrating an API is a weekend project. The hard part is everything you build around it.

Most of your engineering time should go to the harness: memory strategy, tool governance, error recovery, eval loops, observability. That’s where you win or lose on reliability. A mediocre model with a great harness will outperform a great model with a mediocre harness, every time. The model provides the raw intelligence; the harness provides the discipline that makes intelligence useful.

Read the Manus blog post carefully, not to copy their solutions—your use case is different—but to understand the categories of problems you’ll face. KV-cache discipline. Tool explosion. Context degradation. Goal drift. Error compounding. These are universal challenges for anyone building agents, and knowing they exist means you won’t be blindsided when you encounter them.

Build observability in from the start. You need to see every step the agent takes, understand why it made each decision, and trace failures back to their root causes. Without that visibility, you’re debugging blind, and agentic failures are already harder to diagnose than traditional software bugs because the behavior emerges from model inference rather than deterministic code.

If you’re an individual user trying to get things done, the best advice I can give is to pick a harness that fits your primary use case and stop expecting it to generalize to everything else. If your work lives in a codebase—fixing bugs, building features, writing tests—Claude Code is built for that environment and will serve you well. If you spend your days producing decks and spreadsheets and documents, GenSpark understands that workflow in ways the others don’t. If you’re curious about what ambitious, long-horizon agentic work might look like and you’re willing to tolerate some roughness, DoAnything is worth experimenting with. And if you’ve been using Manus and you’re comfortable with Meta owning it, there’s no urgent reason to leave—just understand that the data governance will eventually align with Meta’s broader policies, and decide whether that’s acceptable for your use case.

Judge everything by whether it finishes. Not by demos, not by feature lists, not by what the marketing page promises. Run your actual tasks through the system, the messy real-world tasks that have edge cases and failures and ambiguity. Does it complete them reliably, or does it fall apart around step 30? If it finishes, keep using it. If it doesn’t, try something else.


### The $2 Billion Lesson

Meta just paid over $2 billion for a wrapper.

Not a model. Not a breakthrough. A wrapper—and that was the smart bet, because the wrapper is what makes the model useful.

The new AI race isn’t “who has the smartest model.” Models are converging; the top-tier options are all capable enough for most applications, and they’re improving every few months. The race now is “who can make an agent that finishes, inside a trust boundary that buyers, regulators, and users can live with.”

Manus built a finishing-grade harness through four framework rebuilds, millions of users, and a team that learned what doesn’t work the hard way. They published the ideas openly, and they still got acquired for billions, because production know-how can’t be copied from a blog post. The ideas are the easy part. The execution is the moat.

The model is the engine. The harness is the car. And Meta just bought one of the few teams that knows how to build cars that actually drive.

The question for 2026 is whether you’re building your own answer, buying someone else’s, or still waiting for the models to solve a problem they can’t solve alone.

[![](https://substackcdn.com/image/fetch/$s_!roVV!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0ca44e97-6ae7-475c-abdd-77629706cd62_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!roVV!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0ca44e97-6ae7-475c-abdd-77629706cd62_1024x1024.jpeg)
