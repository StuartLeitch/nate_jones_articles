---
title: "The Specification Gap: Why Your AI Produces Impressive-Looking Output With Fundamental Problems + The Prompt Kit To Help You Fix It"
author: "Nate Jones"
published: 2026-01-21
url: https://natesnewsletter.substack.com/p/tool-shaped-vs-colleague-shaped-ai
subtitle: "Watch now | Codex is better when you can define correctness. Claude Code is better when you can't. Either way, YOU need to know what situation you're in to choose the right path forward."
audience: everyone
scraped_at: 2026-01-21 12:00:17
---

Cursor ran a fleet of agents for close to a week in January 2026, and found GPT-5.2 best for extended autonomous work. When the experiment finished, the system had generated over a million lines of Rust code across a thousand files and built a browser rendering engine—HTML and CSS parsing, cascade, layout, text pipeline, paint, and JavaScript integration. The FastRender repo describes itself as “under heavy development,” and Simon Willison actually ran it and posted screenshots: it kind of works.

This experiment forced a question that every organization will have to answer in 2026: Is your AI shaped like a colleague, or is it shaped like a tool?

The conventional approach—comparing benchmarks, reading feature lists, picking whatever’s newest—misses what actually matters. Claude Code and Codex aren’t competing products in the same category. They’re built on fundamentally different philosophies about what AI should be and how humans should work with it. Senior engineers are reporting major productivity gains with Codex. Junior developers are struggling with the same tool and producing subtle bugs that compound into major problems. The difference isn’t skill. It’s fit.

**Here’s what’s inside:**

- **The CNC Machine Metaphor** — Why this distinction determines whether AI multiplies your output or multiplies your mistakes
- **Why Senior Engineers Are Flocking to Codex** — The specific capability that matters more than coding-specific training
- **Why Junior Developers Prefer Claude Code** — What looks like friction is actually the mechanism that catches errors early
- **The Self-Awareness Challenge** — Most people overestimate their ability to specify precise intent, and the consequences stay invisible until they’re expensive
- **The Non-Technical Frontier** — What “high-grade intent” looks like outside software, and why figuring this out will define competitive advantage in 2026

The question for 2026 isn’t which AI is better—that question doesn’t make sense. The real question is whether you’re honest with yourself about which situation you’re actually in.


## [Grab the Prompts](https://www.notion.so/product-templates/The-Tool-vs-Colleague-Prompt-Kit-2ee5a2ccb52680d6b996c7aa9b63f700?source=copy_link)

The prompt kit exists because the colleague-versus-tool decision fails silently. You send what feels like a clear specification to an autonomous agent, it executes faithfully on your incomplete instructions, and you don’t discover the problems until you’ve built three layers on top of broken foundations.

These prompts force the honest assessment most people skip:

- Prompt 1 makes you score your actual spec clarity and verification cost before you choose a shape, so you can’t lie to yourself about being ready for tool-mode.
- Prompt 2’s ambiguity list and “must not” acceptance criteria catch the scope creep and invention that cause most failures—not missing features.
- Prompt 3 turns expensive verification into cheap checklists by role, so a non-technical operator isn’t stuck running builder-level checks they can’t actually perform.
- The approval gate policy in Prompt 4 prevents the failure that sinks teams: autonomous execution straight into production on high-stakes work because nobody defined where the human checkpoint lives.

These prompts are structured around the specific ways delegation breaks when you mismatch tool-shaped AI with colleague-shaped problems, or vice versa. The Quick Version is there for when you’ve earned it; the full sequence is there for when you haven’t yet.


## **Two Products, Two Philosophies**

Claude Code launched in February 2025 as Anthropic’s command-line agentic coding tool, and it immediately changed how developers thought about AI-assisted programming. Unlike traditional autocomplete assistants, Claude Code operates as what Anthropic calls “an active collaborator”—it can search and read code, edit files, write and run tests, commit and push to GitHub, and use command-line tools while keeping you in the loop at every step. The key phrase is *keeping you in the loop*. Claude Code is built around fast feedback cycles. You assign a task. Claude works on it. A few minutes later, it returns with results, asks clarifying questions, or explains where it got stuck. Then you iterate.

This rhythm feels familiar to anyone who has managed a capable direct report. You delegate something, they come back with questions or a draft, you provide direction, they refine. The back-and-forth isn’t a bug; it’s the design. Claude Code can run on Opus 4.5—Anthropic’s most capable model—but the iterative philosophy has been consistent since launch. Anthropic has always emphasized that Claude Code completed tasks in early testing that would normally take 45+ minutes of manual work, but crucially, it did so through collaboration rather than isolation.

Codex emerged from a different tradition entirely. Where Claude Code emphasizes dialogue and iteration, Codex emphasizes delegation and completion. You can assign it tasks through a prompt or spec, and it will navigate your repository, edit files, run commands, execute tests, and come back with committed changes—often without any intermediate interaction at all. The product runs in isolated sandbox environments in the cloud, designed for extended work on complex multi-step tasks. OpenAI has reported that GPT-5-Codex worked independently for more than seven hours at a time during internal testing—iterating on implementations, fixing test failures, and delivering successful results without human intervention. This isn’t a conversational assistant that happens to write code. It’s something closer to a shift worker you can spin up in the cloud and point at a problem.


## **The CNC Machine Metaphor**

To understand why this distinction matters, consider how manufacturing works. A skilled machinist can sit at a lathe and shape metal through direct manipulation, adjusting their approach based on how the material responds, making micro-corrections in real time based on feel and observation. This is intimate, iterative work. The craftsperson and the tool are in constant dialogue.

A CNC machine works differently. You program it with precise instructions—exact coordinates, feed rates, tool paths—and then you step back. The machine executes those instructions with superhuman precision, cutting complex geometries that would be impossible to achieve by hand. But here’s the critical difference: if your program is wrong, the machine will faithfully execute your wrong program. It won’t ask clarifying questions. It won’t notice that something seems off. It will produce exactly what you specified, whether that’s a precision aerospace component or a pile of scrap.

Codex is CNC-shaped. It’s designed for developers who can define tasks precisely, who know exactly what they want, and who can specify correct intent upfront. When you give Codex a well-formed specification, it will execute that specification with remarkable fidelity over extended periods. The Cursor experiment demonstrated this at scale: hundreds of agents coordinating on the same codebase for close to a week, making thousands of commits, building complex systems—all with minimal human steering.

Claude Code is machinist-shaped. It’s designed for developers who want to think alongside their tools, who expect to evolve their intent through the process of building, who value the ability to catch mistakes early and adjust course. The tool surfaces its reasoning, asks questions when uncertain, and treats development as a conversation rather than a specification.

The deeper axis underneath this distinction is specification quality × verification cost. Tool-shaped AI wins when verification is cheap and the spec is crisp—you can check whether the output is correct quickly, and you knew what correct looked like before you started. Colleague-shaped AI wins when verification is expensive or when the spec is discoverable only through iteration—you need to see drafts to know what you want, or checking correctness requires deep engagement with the output. Senior versus junior is a downstream effect of this, not the cause.


## **Why Senior Engineers Are Flocking to Codex**

A pattern has emerged in developer communities over the past several months that illuminates this distinction. Senior engineers—people with decades of experience and deep architectural knowledge—have increasingly reported that Codex delivers substantially higher productivity than Claude Code for their workflows.

This makes complete sense once you understand the CNC metaphor. Senior engineers have the institutional knowledge required to define precise specifications. They know what correct looks like. They’ve debugged enough systems to anticipate edge cases and specify requirements that account for them. They can write the kind of detailed instructions that a CNC machine needs to produce quality output. And crucially, they can verify outputs quickly—they look at the code and know whether it’s right.

Cursor’s research findings illuminate the specific model behaviors that create this advantage. When comparing GPT-5.2 against Claude Opus 4.5 on extended autonomous tasks, they found that GPT-5.2 “follows instructions, maintains focus, avoids drift, implements things completely.” By contrast, Opus “tends to stop earlier and take shortcuts when convenient, yielding back control quickly.” For a senior engineer who has already done the hard work of specification, that constant yielding of control is inefficiency. For someone still figuring out what they want, it’s a lifeline.

The Cursor team also discovered a counterintuitive result: GPT-5.2 is a better planner than GPT-5.1-Codex, the model specifically trained for coding. This suggests that raw reasoning capability matters more than narrow training for long-horizon autonomous work. The ability to maintain coherent plans over extended periods, to adapt when approaches fail, and to keep working toward distant goals without losing focus—these general cognitive abilities turn out to be more important than specialized coding knowledge when you’re asking an AI to work independently for hours or days.

When a developer with this background sends Codex off to implement a feature, they’re not sending it into the unknown. They’re providing a specification that draws on years of accumulated wisdom about what works and what doesn’t. The result is that Codex can run for 20 minutes or an hour, and when it comes back, the work is done correctly—because the specification was correct.

One engineer described his workflow: “When I send Codex off to do a task that takes 20 minutes, I switch my focus entirely. I’ll open Figma to do design work, write my newsletter, or open another terminal and prompt Codex with some server work while the first terminal is chugging along on client work. I’d rather have everything take longer and generate results that I don’t have to fix than be involved in the process steering AI to success.”

This is the CNC advantage. If you have the expertise to program the machine correctly, you get compound leverage: the AI works while you work on something else, and when it’s done, the output is production-ready.


## **Why Junior Developers Prefer Claude Code**

But the same pattern that makes Codex powerful for senior engineers makes it frustrating for everyone else. If you can’t define tasks with precision—if you’re not sure what correct looks like, if you’re still developing intuitions about architecture and edge cases—then Codex’s autonomous execution becomes a liability rather than an asset. And if verification is expensive for you (because you’re still learning to read code critically), you can’t catch mistakes quickly even when they’re obvious to someone more experienced.

What Cursor characterized as a weakness in Opus—yielding back control quickly—is actually a feature for developers who need guidance. Claude’s tendency to check in, ask questions, and seek clarification means that misunderstandings get caught early rather than compounding into larger problems.

For a junior or mid-level developer, the Claude Code workflow provides something essential: scaffolding for learning. When Claude explains its reasoning, asks whether a particular approach makes sense, or flags potential issues, it’s teaching at the same time it’s building. The conversation itself has value beyond the code it produces. You’re not just getting output; you’re developing the intuitions you’ll need to become the kind of engineer who can use Codex effectively.

Anthropic’s internal research supports this. A survey of 132 Anthropic engineers found that while they use Claude Code frequently, more than half said they can fully delegate only 0-20% of their work to the tool. This isn’t a failure of capability—it’s a reflection of how the tool is designed to be used. Engineers work actively and iteratively with Claude, validating outputs rather than accepting them blindly. The relationship is collaborative rather than transactional.


## **The Philosophical Divide**

Underneath these product differences lies a deeper philosophical disagreement about the nature of work and the role of AI within it. OpenAI’s approach assumes that if you can instruct an AI correctly, and the AI can execute correctly, then the human in the middle is overhead to be minimized. The ideal workflow is specification followed by execution followed by review. Everything else is friction.

This philosophy has a certain elegance. It’s the vision behind the Cursor browser experiment—hundreds of agents working in concert, generating over a million lines of code, with humans providing initial direction and final review but absent from the middle. As AI capabilities improve, this approach scales. You can spin up more agents, run them for longer, and accomplish more without proportionally increasing human involvement.

The scaling dynamics are worth considering carefully. Cursor’s multi-agent experiment used a hierarchical structure: Planners that decompose tasks, Workers that execute implementations, and Reviewers that check quality. This mirrors the organizational design of human software companies, with roles analogous to product managers, architects, programmers, and quality assurance. The team achieved something remarkable: hundreds of agents collaborating on the same codebase for close to a week with minimal code conflicts. This suggests AI can develop the kind of collaborative understanding that human teams take years to build.

But the browser experiment also revealed limits. The FastRender repo explicitly describes itself as under heavy development, and critics have documented significant build and compatibility issues. Cursor consumed trillions of tokens over the experiment—meaning the economics of this approach depend heavily on assumptions about how token costs will evolve and whether the output is actually production-ready.

Anthropic’s approach assumes something different: that the process of building software involves evolving intent, that requirements change as you understand problems better, that the most valuable work happens in the dialogue between human judgment and AI capability. This philosophy treats the back-and-forth not as friction to be eliminated but as the mechanism through which good software gets made.

Here’s my position: Codex is the better answer when you can define technical correctness upfront. If you know what right looks like, if you can specify it precisely, if the success criteria are clear before you start—Codex will outperform Claude Code, often dramatically. The autonomous execution model wins when the specification is solid.

Claude Code is the better answer when intent needs to evolve through the work. If you’re figuring out what you want as you build, if requirements are ambiguous, if you need to discover correctness rather than specify it—Claude Code’s iterative dialogue is not a limitation but the entire point. This describes most junior technical work and nearly all non-technical knowledge work.


## **Cowork and the User Interface of the Future**

The distinction between tool-shaped and colleague-shaped AI extends beyond the terminal into how we’ll interact with AI agents more broadly. Anthropic’s recent launch of Claude Cowork—essentially Claude Code wrapped in a graphical user interface—suggests one vision of the future. The product operates as a desktop application that can read, edit, and organize files directly on your machine. It’s designed around scoped folder access and active user oversight, with Anthropic urging users to be selective about what files the agent can touch.

This is colleague-shaped AI taken to its logical conclusion: an inbox model where you assign tasks, receive results, provide feedback, and iterate. The interface metaphor is Slack or email—ongoing conversations with an intelligent entity that requires your input and values your judgment.

Tool-shaped AI will look different. If Codex-style products become the norm, the user interface might look more like a project management dashboard: you define specifications, assign them to agents, monitor progress at a high level, and review outputs when complete. The metaphor isn’t a conversation partner but a fleet of contractors you’re orchestrating.

Both interfaces will exist. The question is which one matches how you think about work and what kind of work you’re doing.


## **The Self-Awareness Challenge**

Here’s the uncomfortable truth embedded in all of this: most people don’t know which kind of AI they’re ready to use, and most people overestimate their ability to specify precise intent.

When you give Claude Code a vague instruction and it asks clarifying questions, that feels like friction. But when you give Codex the same vague instruction and it executes autonomously on your vague specification, you get output that looks impressive but might be subtly wrong in ways you won’t discover until later. The feedback loop that makes Claude Code feel slower is the same mechanism that catches errors early.

The developers who succeed with Codex are self-aware about their limitations. They know what they know, they specify carefully what they want, and they’re honest about when they don’t have enough clarity to delegate autonomously. They’ve developed the skill of writing high-quality specifications—what some are calling “high-grade intent”—that translate their expertise into instructions an autonomous agent can execute correctly.

The developers who struggle with Codex often don’t realize they’re struggling. They’re sending off tasks that seem well-specified to them but are actually ambiguous or incomplete. The AI faithfully executes their incomplete instructions and produces plausible-looking output that contains fundamental problems. By the time they discover the issues, they’ve built on top of broken foundations.


## **The Non-Technical Frontier**

Perhaps the most significant implication of this distinction is what it means for non-technical work. Right now, the colleague-versus-tool debate is playing out primarily among software developers, but the same dynamic will shape AI adoption across every knowledge work domain.

Consider the task of producing a 100-page business proposal. With colleague-shaped AI, you might work through the document iteratively—drafting sections, getting feedback, refining arguments, checking facts. The AI is a thinking partner throughout the process. With tool-shaped AI, you would need to write a comprehensive specification upfront that describes exactly what the document should contain, how it should be structured, what arguments it should make, and what evidence it should cite. Then you’d submit that specification and receive a finished document hours later.

Few non-technical professionals have the skill to write the kind of specification that would produce a good 100-page document on the first pass. They don’t know what they want until they see what’s possible. Their intent evolves through the process of creation. For these people, colleague-shaped AI will be essential—at least until they develop the specification skills that come naturally to senior software engineers.

But for people who can specify complex non-technical work precisely—experienced consultants, senior strategists, domain experts with deep knowledge—tool-shaped AI might unlock the same kind of productivity gains that senior engineers are finding with Codex. They could define a complex analysis, delegate it to an autonomous agent, and receive finished work product without having to shepherd the process.

The question of what high-quality specification looks like for non-technical work is almost entirely unexplored. We know what a good technical spec looks like. We know how to define requirements for software. We have very little idea what the equivalent looks like for strategy documents, market analyses, research reports, or creative content. Figuring this out will be one of the defining challenges of 2026.


## **Choosing Your Future**

The colleague-versus-tool question isn’t going away. If anything, it will become more acute as AI capabilities improve. Both approaches will get more powerful, which means both the benefits and the risks of each approach will intensify.

For individuals, the immediate task is honest self-assessment. Do you have the domain expertise to write high-quality specifications? Can you define correct outcomes before you start building? Are you comfortable delegating substantial work to autonomous systems and reviewing outputs rather than participating in the process?

If yes, tool-shaped AI offers extraordinary leverage. You can multiply your output by running parallel agents, delegating to cloud-based systems that work while you sleep, and operating more like an architect than a builder.

If no, colleague-shaped AI offers something equally valuable: a thinking partner that helps you develop clarity through dialogue, catches your mistakes early, and supports your growth toward the expertise that would eventually let you use tool-shaped AI effectively.

For organizations, the question is more complex. You probably have both kinds of people on your team: senior experts who can leverage autonomous agents and junior contributors who need iterative collaboration. The right answer isn’t one tool or the other; it’s understanding who needs what and deploying accordingly.

The meta-question—the one that will determine competitive advantage over the next several years—is how quickly you can develop the specification skills across your organization that make tool-shaped AI effective. Companies that figure out what high-grade intent looks like in their domain, and train their people to produce it, will gain access to a different order of AI leverage than companies still treating AI as a conversation partner.

But don’t mistake capability for readiness. The Cursor browser experiment produced over a million lines of code in close to a week—but there are serious questions about whether that code actually works, whether it can be maintained, and whether the experiment demonstrated anything more than the ability to produce impressive-looking output at scale.

The most sophisticated tool in the world doesn’t help you if you’re not ready to use it.

[![](https://substackcdn.com/image/fetch/$s_!RIKL!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6724b268-afcc-4a4e-a825-cf2336f56eae_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!RIKL!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6724b268-afcc-4a4e-a825-cf2336f56eae_1024x1024.png)
