---
title: "Inside OpenAI’s Codex: What the People Building It Actually See"
author: "Nate Jones"
published: 2025-12-18
url: https://natesnewsletter.substack.com/p/grab-the-6-prompts-i-built-from-my
subtitle: "Watch now | Dive into a deep conversation with the team who built Codex, plus grab my top takeaways, learn how everyone at OpenAI (even non-devs) commits code, and discover how juniors grow their c..."
audience: everyone
scraped_at: 2026-01-05 19:09:48
---

Nobody at OpenAI knows what a “designer” is anymore. Or an “engineer.”

And that’s not as scary as it sounds!

I spent an hour with Ed and Tibo from the Codex team—Ed designs the product, Tibo leads engineering—and what struck me wasn’t the growth numbers or the technical architecture. It was watching Ed struggle to answer a simple question about his job title.

He commits code every day now. Submits pull requests. Fixes bugs without asking permission from anyone. He’s been a designer for years, and when I asked what that means now, he paused and said, genuinely: “There’s an identity crisis here. It’s like—what am I?”

That moment stuck with me because I think it’s where a lot of us are headed.

The junior engineers at OpenAI are scaling and accelerating faster than in the past—not because they’re smarter, but because they have less muscle memory to override—and a tool to help them do it. A new grad who’d never touched Rust picked it up in weeks via Codex and now levels up to engineers with a decade of experience elsewhere. It’s the closest thing to Neo downloading kung fu in the Matrix we’ve actually seen.

[![](https://substackcdn.com/image/fetch/$s_!kn9A!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F64a1a9a5-ce31-4a31-a657-11fe80eae908_2878x1198.png)](https://substackcdn.com/image/fetch/$s_!kn9A!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F64a1a9a5-ce31-4a31-a657-11fe80eae908_2878x1198.png)

The model taught itself to spawn copies of itself to solve harder problems, which nobody asked it to do. Non-technical staff are shipping working products at hackathons, not mockups or prototypes but actual functioning things.

The boundaries that used to define who builds what are dissolving faster than anyone expected. Including by the people building the tools that are dissolving them.

This isn’t a productivity story. It’s a story about what work means now.

**Here’s what’s inside:**

- **What’s actually happening** — the three tiers of usage emerging inside OpenAI, why mandatory AI review became one of their most loved features, and how they meet people where they work instead of forcing everyone into terminals
- **The emergent behaviors** — a model that bootstrapped its own multi-agent system, memory that’s embarrassingly simple, and why minimal tools beat elaborate frameworks
- **Where the bottlenecks are moving** — code generation is mostly solved, so now everything downstream is overwhelmed
- **The human side** — why traditional interviews don’t test what matters anymore, and the $20 equalizer changing who gets to build
- **Two paradigms crystallizing** — tight cockpit loop versus parallel coworker, and why it matters which one you’re building toward
- **The Codex Playbook Prompts** — six prompts that turn these patterns into something you can actually use:

  - *The Signal System* — Make AI feedback automatic without creating noise everyone ignores
  - *The Three Doors* — Roll out AI tools so everyone from interns to executives actually adopts them
  - *The Copywriter Pattern* — Ship a real change to your product without writing code or asking engineering
  - *The Parallel Coworker* — Hand off a task, go do something else, come back to finished work
  - *The Memory Kit* — Keep a multi-hour AI task from losing the plot halfway through
  - *The Bottleneck Map* — Figure out what breaks next when you speed up one part of the workflow

The gap between “I have an idea” and “I built the thing” is collapsing. Not just for engineers. For anyone willing to work differently.

Let’s get into it.


## [GRAB THE PROMPTS](https://www.notion.so/product-templates/Building-the-Codex-Playbook-Prompts-for-AI-Native-Rollouts-2cc5a2ccb52680aca898f9a3f214f7ba?source=copy_link)

I asked Ed and Tibo how OpenAI actually uses Codex internally—not the marketing version, but the real patterns. What does mandatory code review look like when it’s designed well enough that people love it instead of mute it? How do you roll out a tool so that power users and non-technical staff both get value without either group feeling like the tool wasn’t built for them? What happens when someone who’s never written code wants to ship a real change?

Then I turned what they told me into prompts.

There are six. **The Signal System** helps you design AI feedback that’s automatic but not annoying—the secret is optimizing for hit rate, which is the thing most rollouts get wrong. **The Three Doors** builds the adoption model they described: ambient tools that just work, casual tools anyone can use, and power workflows for people who want to go deep.

**The Copywriter Pattern** is for people who aren’t engineers but want to ship real changes anyway—the article describes a copywriter changing UX strings through a safe interface without touching a terminal, and this prompt gives you the full “shipping packet” to make that work. **The Parallel Coworker** is for delegation: you hand off a task, context-switch to something else, and come back to a finished package you can review and use.

**The Memory Kit** sets up simple memory for tasks that run for hours—compaction and file-based state, which sounds boring and is boring, and that’s why it works. **The Bottleneck Map** helps leadership figure out what breaks next, because when you speed up code generation, you don’t eliminate bottlenecks—you move them downstream to review and deployment.

These aren’t templates I made up. They’re implementations of what’s working inside the building.

---


# Inside OpenAI’s Codex: What the People Building It Actually See

I spent an hour with Ed and Tibo from OpenAI’s Codex team. Ed designs the product; Tibo leads engineering. Tibo was involved in the early push that became Codex; Ed joined the team after working on research.

If you’ve seen Lenny’s interview with Alexander Embiricos (Codex’s product lead), you know the headline stats: Codex has grown 20x since August and processes trillions of tokens weekly. Every.to did an early hands-on review when Codex launched. The product-level framing is well established.

What I got from Ed and Tibo was different—less strategy, more texture. A designer’s-eye view of what it feels like when the boundaries of your job dissolve. An engineering lead’s candid assessment of where the bottlenecks are actually moving. And a handful of details I haven’t seen covered widely, because they’re the kind of thing that only surfaces when you’re talking to the people doing the work rather than the people positioning the product.

This piece has three parts. First, the ground truth—what’s actually happening inside OpenAI that extends or complicates what’s been reported elsewhere. Second, the emergent behaviors that surprised even the people building this—including a multi-agent pattern the model invented without being asked. Third, a framework for thinking about two distinct paradigms that are crystallizing for how humans work with coding agents, and why it matters which one you’re building toward.

---


## Part 1: What’s Actually Happening


### Every PR Gets Reviewed Whether You Want It Or Not—And People Love It

Every PR at OpenAI gets reviewed by Codex. Not opt-in. Not suggested. Mandatory.

Ed told me he was braced for resistance. As a designer thinking through the user experience, he imagined the backlash: “Oh no, is everyone just going to get loads of emails?” He watched the internal Slack for complaints, waiting for the inevitable pushback against yet another automated notification cluttering people’s inboxes.

The complaints never came.

“It turns out it’s one of the most loved features we’ve shipped,” Ed said. “One of the things that changed for me was seeing some of our top contributors across OpenAI—not just our team—commenting in our Slack saying this is superhuman.”

The word “superhuman” came up multiple times in our conversation, and it wasn’t marketing language. It was literal description of what they were experiencing. Tibo explained why the reviews feel different from typical automated checks: “It’s doing reviews I would never have done because I don’t have the time to dig four layers deep into the stack. And it’s just having that always on. You don’t have to think about it. You have that safety net that’s just there.”

The mechanism that makes this work isn’t model capability—it’s disciplined attention to signal-to-noise ratio. Tibo described the deliberate tradeoff they made: “We’ve been very careful about optimizing for hit rate so that people don’t actually complain and want to turn it off. And overall, as an organization, we’re getting way more value out of it than potentially sometimes the misses. Then we keep improving the system and the model over time so that it’s capable of finding more gnarly and subtle issues.”

This is the adoption pattern most organizations miss when they roll out AI tools. They ask people to use them. OpenAI made them ambient—present whether you invoke them or not. But the crucial insight is that ambient only works if precision is high enough that the notifications feel valuable rather than noisy. If hit rate drops, people tune out, mute the channel, and the tool becomes one more ignored alert. Keep hit rate high, and something interesting happens: people start looking forward to the feedback.

Ed: “I look forward to those notifications now.”


### There Are Three Distinct Tiers of Usage Emerging—And the Gap Between Them Is Enormous

When I asked how engineers actually use Codex day to day, Tibo described three patterns that have crystallized inside OpenAI. What struck me wasn’t the patterns themselves but how different the experience is at each tier—they’re almost using different products.

**Tier 1: Ambient and mandatory.** This is the code review layer I just described. No one opts in or out. The value accrues without any behavior change required. You submit a PR, you get a review. The system handles it.

**Tier 2: Casual and ubiquitous.** “Everyone at OpenAI is using it,” Ed said, and he meant that more literally than I initially understood—”including non-technical staff.” The examples ranged widely: designers submitting PRs to fix small issues, even go-to-market folks hopping in. There’s one engineer who uses Codex as “his primary interface to his computer”—not just for code, but for notes, tasks, everything. It’s become his operating system for getting things done.

**Tier 3: Power users pushing the frontier.** Tibo described people running “increasingly complex workflows, some of them multi-agent, running for many, many hours.” These aren’t quick tasks—they’re sustained work sessions that can stretch for half a day or longer. And the compute usage at this tier is growing fast. “This continues to increase and increase and increase,” he said, with a tone that suggested even he was a bit surprised by the trajectory.

The variance across these tiers is enormous. Someone in Tier 1 might not even think of Codex as a tool they “use”—it’s just part of the PR process. Someone in Tier 3 is orchestrating parallel agents on complex problems for hours at a stretch. The product has to accommodate both without breaking either, which creates interesting design constraints that aren’t immediately obvious from the outside.


### The Surfaces Strategy: Meet People Where They Already Work, Not Where You Wish They Worked

One thing that struck me was how deliberately OpenAI thinks about *where* people encounter Codex. It’s not one interface—it’s a coordinated surface strategy designed to reduce friction for different types of users.

They have the CLI, which is where it started and where power users tend to live. They have an IDE extension that works in VS Code and Cursor—”we meet people where they code,” Ed said, which sounds obvious but represents a real commitment to not forcing workflow changes. They have a web product where you can type a prompt and generate a fix without ever opening a terminal. And they have integrations with Slack and Linear that let you embed Codex directly in ticketing workflows, so the path from “we should fix this” to “here’s a PR” can happen without anyone switching contexts.

Ed walked through a specific use case that illustrated why the multi-surface approach matters: “Say you’re a copywriter, you want to change some UX copy. Maybe you don’t even need to look at the code. You just want to change some strings. You can just do that yourself. You can go in the web product and type this prompt if you’re enterprise setup.”

The implication for anyone trying to adopt these tools in their own organization: if your AI strategy requires non-technical users to open a command line, you’ve already lost half the potential value. The terminal scares people—not because they’re incapable, but because it’s unfamiliar and the cost of making a mistake feels high. The web product doesn’t carry that baggage. Linear tickets feel safe. Slack feels safe. Meeting people where they already are isn’t just a convenience; it’s what makes adoption actually happen.

“The number of surfaces that people are across just makes it easier and easier to get involved.”


### Inside the Work in Progress Channel, Non-Engineers Are Shipping Real Products

There’s a work-in-progress Slack channel at OpenAI where people post demos of what they’re building. Ed described DMing colleagues after seeing their posts, reaching out with variations of “I didn’t know you could do that”—not because the technical capability was surprising, but because of *who* was doing it.

“Even new people, non-technical people, go-to-market stuff—people are really hopping in,” he said. “It’s just this kind of force multiplier.”

What caught my attention was his emphasis that the demos aren’t mockups. They’re not wireframes or prototypes in the “this is what it would look like if we built it” sense. They’re working products. Ed described the shift he’s noticed at hackathons: “At the end of a hackathon, you’ll have a fully working product. You won’t just have a throwaway React demo like you had before.”

Tibo described the experience of seeing these demos from the engineering side—the double-take when someone shows you their idea and you realize it’s not a sketch: “It’s not a static thing. I’m like—this thing is fully functional. It’s almost shippable. How did you cook this?”

The gap between “I have an idea” and “I built the thing” has collapsed for people who are willing to work this way. That’s not a productivity improvement. It’s a category change in what’s possible.


### Ed Commits Code and Doesn’t Know What to Call Himself Anymore

Ed is a designer. He’s also in the codebase constantly. He submits PRs. He fixes paper cuts—the small annoyances you notice when you’re using a product eight hours a day and something isn’t quite right.

When I asked Tibo how he thinks about Ed’s role, he didn’t hesitate: “Ed is just like an engineer on the team. Writing PRs, fixing things. You don’t need to go talk to anyone. You just do it.”

I asked Ed how *he* thinks about it, and he gave me a more complicated answer. “There’s an identity crisis here,” he said. “It’s like—what am I?”

He described two modes of working that feel distinct even though they blur together in practice. In one mode, he’s a problem-solver who happens to use code: “Any small paper cut that you get, you just see and you can fix it.” The agent writes the code, he reviews what it produced, submits a PR, and it flows through the normal approval process. He doesn’t have to ask anyone for permission or wait for engineering bandwidth to free up. He just does it.

In the other mode, he’s a designer using code as a medium for exploration: “Maybe I can just make my terminal really small. Don’t worry too much about the code. Just have localhost open. Narrow this gap from thought to product and really just focus on the interactions.” In this mode, the code isn’t the point—it’s a way of thinking through what the experience should feel like, faster than any mockup could capture.

The old model of how design and engineering collaborated went something like this: designer creates a file in Figma or Sketch, throws it over the wall to an engineer, engineer interprets the intent and productionizes it. The handoff was the job. The new model, at least inside OpenAI, looks different: “I’ll just create a fork of the repo. It’s not just a demo. It’s a fully functioning thing. Obviously to move fast I’ve taken some shortcuts—it’s going to be a little rough around the edges. But the fidelity you can get to is amazing.”

This isn’t designers learning to code in the traditional sense—spending months on tutorials, building up from fundamentals. It’s designers working directly in the material because the translation cost has collapsed. The agent handles the parts that used to require specialized knowledge. What’s left is judgment about what should exist and whether it’s good.


### When Execution Gets Cheap, Direction Gets Expensive

Tibo kept returning to a theme throughout our conversation that I want to make sure doesn’t get lost: as execution costs drop, the premium on choosing the right direction goes up.

“It brings a lot of clarity,” he said. “It’s all about the problems—figuring out what problems to solve, figuring out what questions to ask yourself. So much more is possible and it’s much cheaper to ideate and build. And then you find yourself being like, wow, I really need to be crisp about what I want to go do.”

He paused before adding: “It’s exciting, but it’s also nerve-wracking at the same time.”

Ed put it more simply: “Good ideas matter more.”

What they’re describing isn’t just “move fast”—it’s a shift in where the hard work lives. Tibo talked about what distinguishes the teams that succeed: “The speed and velocity—which direction you’re going and how fast you learn. The most successful teams we see emerge are really small teams that set themselves up to learn and iterate super fast.”

There’s an old phrase in engineering that Tibo referenced: “code wins.” You can write as many PRDs as you want, but until you have the product in your hands and can feel whether it’s right, you’re guessing. That phrase hasn’t changed. What’s changed is how fast you can get to the product in your hands—and therefore how quickly you discover whether your direction was right. The iteration loop has compressed, which means you can course-correct faster, which means the cost of being initially wrong has dropped. But the cost of not knowing what you’re trying to build? That’s as high as ever.

---


## Part 2: The Emergent Behaviors


### The Model Taught Itself to Spawn Sub-Agents—And No One Told It To

The most surprising technical detail from the conversation was something that emerged without being designed.

Tibo described playing around with Codex while using their SDK—the developer tools that let you build on top of Codex. “I just told Codex about the SDK and it was able to write code and use it—write a bunch of TypeScript and then invoke basically invoke itself to achieve more.”

He was explicit that this wasn’t a feature they shipped: “We don’t have native multi-agent in Codex. But this is a form of it that is just completely emerging.”

What actually happened: Codex read the SDK documentation, recognized that it could use those tools to instantiate other Codex instances, wrote the code to do exactly that, and then used those instances as tools to complete the original task. Multiple agents, running in parallel, all bootstrapped by the original agent without anyone telling it this was possible.

“It read the documentation,” Tibo said. “It was like—I can probably get this tool to do something for me. And it just wrote that code, invoked it, and it just worked.”

In our conversation, we landed on a useful distinction: “code as a means, not code as an output.” Tibo immediately agreed and elaborated. Sometimes the agent writes code you should look at carefully and merge into your codebase. But sometimes it writes throwaway code—code that exists only to accomplish a task, including spawning more agents. In that case, the code isn’t the artifact you care about. The outcome is what matters.

I asked Tibo when he was last surprised by an emergent property—some behavior that the model exhibited that wasn’t explicitly designed. He said it had happened that morning: “Someone built scaffolding around a model to enable it to work on a problem I thought was out of reach of current capabilities—and solve it successfully. It worked for almost 13 hours on this one problem. Just by being more creative on the tools and setup around it. I hadn’t seen this done before.”

Thirteen hours. On a single problem. That’s not a quick coding task—that’s sustained work at a level that changes what you can expect from these systems.


### Memory for Long Tasks Works Through “Compaction”—Simpler Than You’d Expect

I asked how they handle memory for tasks that run many hours. The architectural question fascinated me: how do you maintain coherence when a task outlasts the model’s context window?

The answer was simpler than I expected, and deliberately so.

Tibo described the mechanism: “For very long-running sessions, the model goes beyond its context window. So the model is forced to summarize what it’s achieved so far and then reboot itself through a process we call compaction—where at the end, it just erases all the content of the context window and then summarizes it. Then you reboot and restart.”

The key insight is that you can do this repeatedly: “You can do this many, many times. Essentially the agent can work forever if the task requires it.”

Beyond compaction, they use file-based state as a kind of external memory. The model writes its progress to files—often just markdown—and can retrieve that context in later sessions. There are also “skills” files: shared documents that evolve between the user and the agent, encoding workflows and preferences that improve over time as both parties learn what works.

Tibo acknowledged the limitations honestly: “There’s a problem with staleness. It’s a poor version and hacky version of memory. It does feel like this will get disrupted at some point.” But then he explained why they’ve resisted building something more sophisticated: “Keeping things simple with models that are evolving in capabilities month after month is probably the right thing to do. Otherwise you end up with a pile of complexity that you have to continue to adapt to ever-evolving capabilities.”

This is counterintuitive advice in a world where everyone’s building elaborate agent frameworks with sophisticated memory systems. But there’s wisdom in it: simple primitives survive capability jumps. If you build complex infrastructure around today’s model limitations, you’ll have to rebuild it when those limitations change. Compaction and file-based state aren’t elegant, but they work—and they’re model-agnostic enough that they’ll probably keep working as the underlying capabilities improve.


### Give It a Shell and See What Happens: The Philosophy of Minimal, General Tools

I’d noticed in my own use that Codex has a particular cognitive style—logical, concise, systematic. I find it genuinely useful for non-technical analysis precisely because of this quality. I asked whether they’ve seen this pattern internally.

Tibo confirmed it: “There’s that element of—this model is trained to be precise and correct about things, diligent, double-check maybe triple-check its work sometimes, and not do all the math in its head. Maybe write a little Python script to help itself out.”

He uses it for data analysis constantly, and noted how the experience differs from traditional chatbot interactions: “It’s not about the code anymore. It’s about the result and trusting the steps. You can see step by step why it’s doing things.”

This raised a question I’ve been curious about: at what point do you stop caring about the code itself? “Is the code just a tool that you don’t really care about?” Tibo asked. “Then you’re using that as a stepping stone. Then you have a coding agent that’s maybe evolving into a more general kind of assistant.”

Ed described a feature that changed his mental model of what was possible: “If you go in the web product and ask the model a question, it can send you some frontend back. It takes a photo of it and sends it back with it. When I first saw that, I thought that was magical. This model can do so much more than I thought.”

The design philosophy underlying all of this is deliberately minimal. Tibo explained their approach: “What we’ve done with Codex is just give it access to your computer through good old Unix tools. Give it a shell and see how far it can get. Then to do this safely, have it run in a sandbox.”

They don’t prescribe how the model should accomplish tasks. They give it general-purpose tools and let it figure out the approach: “We don’t necessarily care how the model is going to achieve its task. Other than—you should probably use the shell a bunch of times. But other than that, it’s a very general tool. That’s something we’ve done consciously because we believe it’s one of the more scalable ways of doing things. It scales with model capabilities. And it’s super general.”

Ed gave a concrete example of what this generality enables: “It turns out you don’t need to give it a document-writing tool. You can just use regex and bash commands. Edit documents. Do anything.”

The emergent behaviors—the self-bootstrapping multi-agent patterns, the creative problem-solving—come from this generality. Instead of building narrow tools for specific tasks, they built a platform that lets the model invent its own approaches. Some of those invented approaches turn out to be surprising.


### There’s a Debate Inside OpenAI About What Interfaces Should Look Like Next

There’s tension inside the team about what comes after the current interface paradigm, and Ed was refreshingly candid about the disagreement.

“There are two camps,” he said. “One is—this is a transitory form factor. There are some new interaction paradigms we’re pushing toward but perhaps aren’t there yet. On the other hand, the constraint of the prompt box, the terminal—it’s kind of perfect as well. It meets you where you are.”

But he also acknowledged the limitation he feels working within current interfaces: “The current way we’re doing it in the CLI and the extension—it wants to be more. The current interfaces are maybe holding things back a little bit.”

Tibo speculated about what the next phase might look like, and his vision was genuinely different from today’s experience: “At what point do we have agents that just run forever? And you interact with it. Maybe you text it from time to time. Maybe you call it. We have to invent the right product around this. The models are not there yet, but they will be. That’s going to feel very different.”

The honest answer is they don’t know what’s next. Ed: “In five years, it’s going to be very different. Chat may not be the primary interface. You might not be interacting with a model at all, but it’s still doing work for you in the background.”

What I found refreshing about this conversation was the willingness to admit uncertainty. They’re building one of the most successful AI products in the world, and they’re openly grappling with the question of whether the current interface paradigm is a stepping stone to something else or a local maximum they’ll need to break out of.

---


## Part 3: Where the Bottlenecks Are Moving


### Code Generation Is Mostly Solved—So Now Everything Downstream Is Overwhelmed

Tibo was direct about something most Codex coverage glosses over: as code generation accelerates, the bottlenecks don’t disappear. They migrate downstream, and the people at those downstream positions start to feel the pressure.

“As we’re solving—almost solving—code generation, and you can implement any feature faster and faster, suddenly you’re left with deploying and maintaining the services. Whenever your hardware breaks or networking has an issue—whatever, million things that can happen—now suddenly you get paged a little bit more. You’re building ahead of the automation we’re able to deploy.”

This isn’t theoretical. He said they’re experiencing it now: “The intelligence is not yet capable of doing all these things. We’re not yet able to have Codex deploy the service and be on-call. This is an area where currently we’re feeling that load from having almost solved code generation.”

The bottleneck migration follows a predictable path if you think about it:

**Writing code** → (mostly solved) → **Reviewing code** → (current investment area) → **Deploying and operating systems** → (next frontier)

Ed acknowledged the meme that’s circulating: “Software engineering becomes reviewing agent code.” Their response has been to invest heavily in code review agents and smoother review experiences. But even solving the review bottleneck just pushes pressure further downstream to deployment and operations.

If you only invest in accelerating code generation, you’ll create a traffic jam at review. Solve review, and you’ll create a traffic jam at deployment. The bottlenecks don’t go away—they move. The companies that understand this will invest across the entire pipeline rather than optimizing one stage in isolation.


### Why Agents Can Write Code But Can’t Yet Be Trusted On-Call

Tibo explained why coding agents came first, and the reasoning goes beyond “models are good at code.”

“One of the things that’s special about code generation is that you can make it safe,” he said. “You have all the code generated in a sandbox. You have no side effects.”

Code also lives in a world of textual context that’s already structured for machine legibility. Everything an agent needs to understand is written down somewhere: “For code, you have git, you have repos. A lot of the automation already exists. A lot of the tooling already exists. So it was solved first due to a combination of reasons, but that’s a big one. And you can make it safe.”

The jump to deployment and on-call work is categorically different because the actions have real-world consequences that can’t be sandboxed. “Whenever you go into the world of deployment and being on-call and actually having real-world consequences of an agent taking actions into the world—that is a whole other game where you cannot make it safe yet. You cannot guarantee that the agent will not go and delete your service or just snoop at user logs.”

His prediction for what unlocks in 2026 was specific about the path forward: “There’s a whole security aspect. Figuring out how to restrict a set of actions through a safe space—or you have to solve the alignment problem, whichever comes first. We’re inching toward that and finding more creative ways so that our agents can act upon the world safely. That’s the next frontier of what we’re going to unlock in 2026.”

The framing is worth noting: safe action spaces as a product problem, not just a model capability problem. The models may become capable of on-call work before there’s a safe way to let them do it. The product layer—the boundaries, permissions, audit trails, rollback mechanisms—is what will determine when these capabilities actually ship.

---


## Part 4: The Human Side


### Junior Engineers Are Outpacing Seniors—And It’s Because They Have Less to Unlearn

This was the most counterintuitive internal trend Ed and Tibo described. They kept pointing to Ahmed, a new grad who joined without knowing Rust.

Tibo: “He learned Rust super quickly. I’ve never really seen someone pick up a new language as fast as that and get productive. And the way he manages to accept the technology and discover the true potential of agents is faster than most people on the team.”

The pattern isn’t just about technical adoption. It’s about willingness to work differently: “I’ve seen veterans—10 years in industry—kind of stick to their more traditional ways of developing. And it’s tough. I’m not sure which one is more effective. But it’s pretty clear to me—jump three months, six months from now—it’s going to be very clear which one is more effective.”

What makes this counterintuitive is that Ahmed now “levels up” people who are nominally more senior than he is. Tibo: “There’s that superpower of how quickly you’re willing to try and adopt new ways of working.”

The explanation isn’t about raw talent or intelligence. It’s about scar tissue—or the absence of it. Tibo: “He grew up almost with this. It’s super natural to him. For me and others, sometimes I’m just like—I’m going to go back and hash it out manually. And I’m slowing myself down in a way. Then you look at the way they’re using AI today and you get inspired.”

Seniors have muscle memory for the old way of working. When they hit friction, their instinct is to fall back on patterns that served them for a decade. Juniors don’t have those patterns to fall back on, so they push through the friction and discover what’s possible on the other side.

But Tibo was careful to note limits: “Experience still matters for architecture and scaffolding. The principles of software engineering still remain. Once you have the right scaffolding, then you can go and run and be extremely fast because the agent will also respect the general scaffolding and boundaries you’ve set.”

The implication isn’t that experience is worthless—it’s that experience needs to be paired with willingness to adopt new tools. The combination of deep knowledge *and* agent fluency is what’s most valuable. Having one without the other leaves performance on the table.


### Traditional Interviews Don’t Test What Actually Matters Anymore

Both Ed and Tibo acknowledged that standard technical interviews have become misaligned with the actual job.

Tibo: “It’s been a challenge on interviewing and finding the right people. The traits you’re looking for and how you can succeed has broadened. Before it was—you program well? Let’s give you a series of hard programming tasks and pick the best talent. But now it’s not that easy anymore. You can actually be very successful even if you’re not going to traditionally be a top performer at hard programming tasks.”

The core problem is that in the actual job, you’ll use AI constantly. Testing someone without tools is testing a capability they won’t exercise once they’re hired. It’s like evaluating a carpenter by asking them to build something without power tools, then handing them a full workshop on day one.

Ed described a broader shift in how credentials and proof-of-capability are changing: “There’s less focus on credentials and going through certain routes to get to certain peaks of credentials. More focus on what you’ve done and what you can show. Code wins. No one cares where you went to school.”

When I asked about the persistent problem of candidates using ChatGPT during remote interviews—essentially cheating by traditional standards—Tibo said they bring people on-site for many interviews. But his framing of the problem was more interesting than the tactical solution: “It’s more of a—the interview itself needs to evolve. Maybe not limiting the tools people can use.”

The question shifts from “can you perform without tools” to “can you use tools to deliver judgment and leverage.” What matters isn’t whether you can manually implement an algorithm—it’s whether you can specify a problem clearly, evaluate the output critically, and iterate toward something that actually works.


### The $20 Equalizer: This Changes Who Can Build What

Ed framed the capability expansion as a democratization story, and it was one of the moments in the conversation where his enthusiasm was most evident.

“When I got into design as a teenager, I was doing animation, hand-drawing things, making movies with my friends in the garage. You had to build a green screen, buy the camera—which was expensive. Now with a $20 subscription, you can as a creative make basically anything. You get access to Codex, you get access to all these other things. In many ways it’s an equalizer.”

Tibo extended this to the economics: “We still have complaints that usage limits are too low. But when you think about it—$20 a month for a prolific software engineer that can help you get stuff done is crazy. This equalizer thing is real. There are so many problems that were left unsolved before this that will now get solved. That’s what gets me excited.”

The SEV3 and SEV4 problems—the backlog items that never quite made the priority cut, the “nice to haves” that perpetually languished—are now accessible. Not because they’ve become more important, but because the cost of addressing them has collapsed. Work that wasn’t worth a senior engineer’s time might be worth $20 in tokens and 30 minutes of review.


### Step Changes Feel Incremental Within a Week—Then You Look Back and Reality Has Shifted

Both Ed and Tibo described a pattern I’ve noticed in my own experience with these tools: capability improvements feel massive for about a day, then you adapt and start complaining about the new limitations.

Ed: “I’ve been so surprised at how fast people get used to these new step changes. Every few weeks or every model release, we push this frontier even more. Then a week later, you’ll be in some agent loop and get frustrated. You forget that this is insane.”

He compared it to the Sora launch: “We ship Sora and it’s mind-blowing. Then you see this tiny imperfection and you’re like... but you forget. You zoom out and you become used to these things so fast.”

Tibo put it simply: “It feels incremental at times. But when you look back six months, you’re like—none of this was possible.”

The implication for anyone evaluating these tools: your intuitions about what’s possible are probably stale. If you tried Codex three months ago and formed an opinion, that opinion is based on a capability ceiling that no longer exists. The complaints you have today were impossible problems yesterday. And the limitations you’re frustrated with now will probably be solved in the next few months.

This doesn’t mean you should suspend critical judgment—the tools have real limitations and real failure modes. But it does mean you should stay more open to re-evaluation than feels natural. The trajectory is steep enough that yesterday’s conclusions need regular updating.

---


## Part 5: Two Paradigms Are Crystallizing

Here’s where I want to shift from reporting to interpretation.

Watching how different people work with coding agents—inside OpenAI, at Cursor, in the enterprises I advise—I see two distinct paradigms crystallizing for how humans collaborate with these systems. Most coverage treats coding agents as a single category, but the workflow differences are substantial enough that I think we need different mental models for each.

Brian Zhan, a partner at Striker Venture Partners and former software engineer, articulated this distinction on Twitter last week in a thread that clarified my own thinking. His framing:

**Paradigm 1: Tight cockpit loop**

You and the agent share a single session. You watch it work in real time. You intervene mid-flight when you see it heading somewhere unproductive. You steer continuously. The agent is an extension of your terminal—a pair programmer sitting next to you, thinking out loud.

This is what Claude Code optimizes for. The feedback loop is measured in seconds. You’re in the cockpit together, hands on the controls.

**Paradigm 2: Parallel coworker**

You hand off a task, context-switch to something else, and come back later to review a completed artifact. The agent works in its own sandbox, on its own machine. The center of gravity becomes the PR, the diff, the mergeable output.

This is what Codex optimizes for. Asynchrony isn’t a limitation—it’s the core design choice. You spawn N jobs, then batch the review and merge.

Zhan’s framing of the implications was sharp:

> “Codex is delegation-first, not pair-programming-first. Claude Code’s superpower is the tight interactive control loop. Codex’s bet is different: agent as a parallel coworker that works on its own computer.”

He went on to enumerate the product consequences that flow from this framing: isolation and sandboxing isn’t just infrastructure but UX, mergeability is the actual target metric, and asynchrony enables fundamentally different workflows than real-time collaboration.

What strikes me as important is that these paradigms aren’t just technical choices—they require different things from the humans involved.

The tight cockpit loop requires taste in the moment. You need to know when to interrupt, when to redirect, when the agent is heading somewhere unproductive. It rewards people who can think at the speed of the agent and make judgment calls in real time. The skill is steering.

The delegation model requires specification up front. You need to know how to define “done,” how to structure outputs that can be verified when they come back, how to phrase work so an agent can execute it without supervision. It rewards people who can write clear briefs and review artifacts critically. The skill is defining.

Zhan’s prediction is that we’ll converge on a hybrid workflow: “Interactive Claude Code loop for ambiguous work, sandboxed parallel Codex jobs for throughput. The winner is whoever builds the best router across those modes.”

I think that’s right. But the routing question is harder than it sounds, because most people haven’t developed fluency in *either* mode yet. They’re still learning what it means to work with an agent at all—let alone switching fluidly between paradigms based on the nature of the task.


### The Organizational Preconditions That Make Agent Leverage Possible

This brings me to what I’ve been writing about for the past several weeks: the preconditions that determine whether an organization can actually capture the value these tools offer.

Last week I wrote about Cursor deleting their CMS. The story wasn’t really about content management systems—it was about abstractions that made sense in a world where non-technical people needed GUIs but that create friction in a world where agents need access to the underlying work. Lee Robinson finished the migration in three days, ~$260 in tokens, and 344 agent requests. The headline wasn’t “agents are fast.” It was “convenience layers that helped humans for decades are now blocking agents from operating.”

Ryo Lu from Cursor has a philosophy that grounds this:

> “Code isn’t a cage—it’s the material where truth reveals itself. The truth only reveals itself when you build. Not when you think about building, not when you sketch possibilities in a protected space—when you actually make the thing real and let reality talk back.”

The precondition for agent leverage isn’t “learn to code.” It’s something more fundamental: learn to work in materials that agents can operate on.

What Ed and Tibo described keeps circling back to this without naming it explicitly. The reason mandatory code review works: the review surface is legible to both humans and agents—diffs, PRs, test results. The reason compaction works: state gets written to files where it can be retrieved. The reason juniors outpace seniors: they don’t have to unlearn workflows built around hidden state and manual clicks.

For readers who don’t come from technical backgrounds, the concepts that unlock this aren’t programming languages. They’re what I’ve been calling work primitives:

**State:** Where is the current status of the work written down? If important information lives in people’s heads or in scattered documents nobody maintains, agents can’t access it.

**Artifacts:** What is the system of record? Something identifiable, editable, versioned—not hidden behind admin panels and draft modes.

**Checks:** What proves this is correct? Not “it looks good”—something objective that can be evaluated.

**Rollback:** How do you undo safely? Agents increase throughput. Reliable rollback is what makes throughput safe.

These aren’t coding skills. They’re the building blocks that make delegation possible—whether you’re delegating to a human or an agent. Organizations that build fluency in these concepts will be able to capture agent leverage. Organizations that don’t will stay stuck at the advisory layer—capable models, limited actual impact.

---


## What Stays Constant Through All of This

Near the end of our conversation, I asked Ed and Tibo what they think matters most right now—what separates people who thrive with these tools from people who struggle.

Tibo: “Curiosity and willingness to engage is the most important thing right now. It’s clear we’re only at the very beginning of what’s going to continue to evolve. Model capabilities are going to continue to increase. We’re not seeing a sign of slowdown.”

Ed went back to his own journey into creative work: “When I got into design, I was doing animation, hand-drawing, making movies with friends in the garage. You had to build a green screen, buy a camera—which was expensive. Now you can make basically anything. It requires leaping in, having that curiosity, throwing yourself in and learning about it.”

The capability ceiling keeps rising. The tools keep improving. The paradigms keep shifting. What stays constant is the advantage that accrues to people who remain radically open to new ways of working—who don’t mistake their current workflow for the final form.

Tibo put it simply: “You can just do things.”

That phrase—”you can just do things”—is an internal mantra at OpenAI. It sounds almost naive, but it captures something real about what changes when execution costs collapse. The gatekeeping dissolves. The translation layers thin out. The gap between “I have an idea” and “I built the thing” compresses toward zero for people willing to work in materials that make it possible.

Ed’s identity crisis—”what am I?”—is actually the right response to this moment. The boundaries are dissolving. Designer, engineer, PM—these categories made sense when the work required specialized skills that took years to develop. They make less sense when an agent can handle the specialized execution and what’s left is judgment about what should exist and whether it’s good.

The question isn’t whether you have the right title. It’s whether you’re willing to work in ways that let the tools actually operate—or whether you’ll keep hiding behind abstractions that felt safe in 2015 and now mostly create friction.

The tools are ready. The question is whether we are.

[![](https://substackcdn.com/image/fetch/$s_!32i3!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F17a4d965-8ccc-4e22-a682-6b0b5311a8ce_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!32i3!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F17a4d965-8ccc-4e22-a682-6b0b5311a8ce_1024x1024.png)
