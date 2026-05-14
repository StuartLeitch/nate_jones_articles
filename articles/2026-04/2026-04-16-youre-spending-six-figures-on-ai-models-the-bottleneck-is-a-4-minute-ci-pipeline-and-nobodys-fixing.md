---
title: "You're Spending Six Figures on AI Models. The Bottleneck Is a 4-Minute CI Pipeline — and Nobody's Fixing the Right Thing."
author: "Nate Jones"
published: 2026-04-16
url: https://natesnewsletter.substack.com/p/your-ai-is-50x-faster-your-tools
audience: everyone
scraped_at: 2026-05-14 14:33:31
---

For fifty years, every piece of software was built for you. The compiler waits because you need time to read the output. The API paginates because that’s what fits on your screen. The test framework takes five seconds to start because you weren’t going to act on the results any faster. Every timeout, every rate limit, every login screen was calibrated to the pace of a brain that processes about 3 bits per second. Nobody decided to make it slow. You were always the slowest thing in the system, and everything else just had to keep up with you. Which wasn’t hard.

That’s not true anymore.

AI agents now operate at 10-50x human speed on reasoning tasks, and they’re running into a wall that has nothing to do with how smart the models are. Jeff Dean said at GTC that making a model *infinitely fast* would only get you a 2-3x improvement end to end. The tools eat the rest. We spent a trillion dollars teaching sand to think, and now we’re bottlenecking it on compilers, file systems, and authentication flows that were designed for human hands. The other 47x is just gone, absorbed by a stack that was built for your pace.

The software isn’t being built for you anymore. It’s being rebuilt for a consumer that doesn’t have eyes, doesn’t have hands, and doesn’t take breaks. This piece is about what that means — for the tools, for the organizations that depend on them, and for the humans who are moving from the center of the system to above it.

**What’s inside:**

- **The bottleneck shift and the three-layer rebuild.** What happens when agents hit 50x and the tools can’t keep up — and the faster tools, agent-native primitives, and infrastructure already replacing them.
- **What happens to the human.** The evidence hiding in the METR study and Jellyfish data, the upstream migration from execution to judgment, and the Amdahl math behind all of it.
- **What to do about it.** Concrete moves for engineers, leaders, platform buyers, and company builders — and where this goes from here.
- **Put it to work.** Four prompts — an Amdahl ceiling calculator, an agent-readiness audit, a trait self-assessment, and a taste encoder that turns the judgment in your head into constraints an agent can follow.

Let’s start with what happens when the fastest part of your system isn’t the part that matters.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260331_6ro_promptkit_1)

This article comes with a four-prompt kit that turns the frameworks into working tools. The Amdahl Ceiling Calculator maps your actual workflow, calculates your theoretical maximum speedup, and shows you which bottlenecks to fix first — most people find their binding constraint isn’t the model. The Agent-Readiness Audit takes your tool stack and grades each tool on whether an agent can actually use it at machine speed or just technically access it. The Upstream Value Self-Assessment maps your current skills and time allocation to the four latent traits and tells you honestly what’s appreciating and what’s depreciating. And the Institutional Taste Encoder — the hardest and highest-value one — helps you take the quality judgments living in your head and formalize them into constraint specs an agent can actually follow. That’s the “encoded judgment is a moat” idea made practical.


## What happens when the bottleneck shifts

The speed of inference is no longer the interesting problem. Coding agents write production code at volume. Google says over 30% of its new code is now AI-generated. Boris Cherny, the creator of Claude Code, said roughly 80% of Claude Code’s own code is written by Claude Code itself. Research agents synthesize papers, financial data, and competitive intelligence faster than any analyst. Enterprise agents are piloting across sales operations, compliance, and customer intelligence. Jeff Dean predicted at Sequoia’s AI Ascent in May 2025 that AI would perform like a solid junior developer working 24/7 within about a year. NVIDIA’s Bill Dally said inference is now 90% of data center power consumption and heading toward 10,000-20,000 tokens per second per user. The models are fast. That part worked.

The part that didn’t work is everything the models have to touch. And you can see it clearly when you trace an actual workflow. Watch what happens when a coding agent gets a task like “refactor this authentication module to use OAuth 2.0 with PKCE.” The agent doesn’t just write code. It enters a loop: read the existing code (file I/O), understand the project structure (directory traversal, dependency parsing), plan the refactor (model inference, fast), write the new code (model inference, fast), save the file (file I/O), compile (compiler startup plus compilation), run the tests (test framework initialization plus execution), read the output (file I/O), identify what failed (model inference, fast), fix the code (model inference, fast), compile again, wait for tests again, and around and around.

In that loop, the model’s thinking, the part everyone obsesses over, the part the entire infrastructure investment was built to accelerate, is a *minority* of the wall-clock time. The majority is tool interaction. Each tool carries startup overhead that nobody optimized because the human on the other side would never have noticed. A test framework doesn’t just run tests. It discovers files, builds a dependency graph, initializes a runtime, potentially spins up browser contexts or database connections, executes the actual tests, then tears down. For a human, the 3-5 second startup is invisible. For an agent iterating dozens of times per hour, the 200-millisecond test execution is dwarfed by 4 seconds of overhead. The fast part is fast. The slow part is everything.

Now scale this beyond coding. An agent doing quarterly business review preparation needs to pull sales data from Salesforce, financial data from the ERP, customer feedback from Zendesk, market data from a third-party API, and assemble a presentation. Each interaction isn’t just a query. It’s an authentication handshake, a session establishment, pagination through results designed for human-screen consumption, rate-limit throttling designed for human-paced requests, and response parsing through formats built for human readability. An agent that could do the analytical work in 30 seconds spends 15 minutes waiting for tools built for a species that thinks at 3 bits per second.

And this is where the conversation shifts from “interesting infrastructure problem” to “what does this mean for my career, my team, and the next decade of my professional life.” Because the entire software world is about to be rebuilt for a consumer that isn’t you. And the implications of that rebuild are deeper than anyone in the tool-optimization conversation is acknowledging.


## The three-layer rebuild

The rebuild is already underway, and it’s happening in three layers, each more radical than the last. And if you’re wondering whether this is optional, whether maybe we can just keep the tools we have and absorb the inefficiency: computing has a gravity well around efficiency. If something can be made faster, computing will figure out how to make it faster. That force is as reliable as anything in this industry. The rebuild isn’t a choice. It’s an attractor state.

**Layer one: make the existing tools faster.** The JavaScript ecosystem has spent five years rewriting its entire toolchain in Rust, Go, and Zig, not for AI, but because developers were tired of waiting. Rolldown runs 10-30x faster than Rollup. Oxc benchmarks at 30x Prettier’s speed. Turbopack is the default bundler in Next.js 16. TypeScript 7 is being rewritten in Go at 10x+ performance. Biome v2 ships type-aware linting using its own inference engine instead of the TypeScript compiler. Lee Robinson captured the arc: “When I wrote this in 2021, Rust replacing JavaScript tooling was my lofty prediction. In 2026, nearly every major JavaScript build tool now has a Rust-based alternative or has been rewritten in Rust.” Five years from prediction to reality.

There’s a detail here that connects two trends that look separate: Rust is also proving to be an excellent language for AI agents to *write*. Robinson built a Rust image compressor using only coding agents — 520 agents, $287 in compute, zero runtime dependencies. The strict compiler acts as natural verification: if it compiles, it’s much closer to correct. So the same language that makes tools faster for agents to use also makes code safer for agents to produce. The toolchain and the agent are co-evolving toward each other.

But this happened in *one ecosystem*, driven by web developers who were already frustrated with build times. Python, Java, Go, .NET have not undergone the same transformation. Enterprise middleware hasn’t started. Your Salesforce API still paginates at human speed. Your SAP calls still carry batch-processing overhead. Your SharePoint still requires human-speed authentication for every interaction. The JavaScript ecosystem accidentally built for the agent era by building for impatient humans. Everyone else needs to learn from this.

And I think MCP has actually blinded parts of the industry to how far behind they still are. The pattern I keep seeing: a company stands up an MCP server over a human-friendly API and declares itself agent-ready. The agent *can* use it, sure. Agents are flexible. They make do. But “making do” still means the agent is eating wall-clock time paging through your API’s pagination, waiting on your authentication handshake, parsing response formats designed for human readability. Wrapping a human-speed API in MCP does not make it agent-native. It makes it agent-accessible. Those are very different things, and the gap between them is exactly the Amdahl tax Dean is describing.

**Layer two: replace the tool abstraction entirely with agent-native primitives.** These tools are 10-30x faster. But they’re still recognizably tools for humans. The next layer of the rebuild is more radical. It replaces the human-tool interface with primitives that assume the consumer doesn’t have eyes, doesn’t have hands, and doesn’t take coffee breaks.

OpenAI shipped agentic primitives in February: a persistent container (Hosted Shell) where agents install dependencies once and never restart between turns. Server-side compaction keeps agents alive for hours or days. The concept of “starting up the compiler” doesn’t exist because the environment never shuts down.

Researchers published BranchFS, copy-on-write filesystem branching with sub-350 microsecond branch creation and sub-millisecond atomic commits. A proposed `branch()` syscall that generalizes Unix `fork()` for the agent era. Today, agents explore parallel approaches using Docker containers and git stashes, seconds of overhead per branch. BranchFS makes it microseconds. Speculative tool use (”try this compiler flag, see if it works, abort if it doesn’t”) goes from a workflow you plan around to something so cheap you do it reflexively on every iteration.

The Agent Primitives paper showed that multi-agent coordination through shared KV cache instead of text produces 3-4x lower latency with only 1.3-1.6x overhead versus a single agent. Not a faster way to pass messages. A new coordination substrate designed for consumers that don’t read.

**Layer three: the primitives replace the scaffolding.** This is the bitter lesson from AI research (general methods that leverage computation always beat clever human-engineered solutions) applied to the entire software stack. Aaron Levie connected this explicitly to Dean’s talk: every new model generation “pinches” your old scaffolding, forcing you to strip it down toward simpler, more general primitives. The tools you built for today’s model become drag on tomorrow’s model. The interfaces designed for human inspection become overhead when the consumer doesn’t have eyes.

And this creates a dynamic that makes the “just optimize existing tools” approach structurally insufficient. You can spend a year making your agent framework 3x faster. Then a new model ships that’s 5x faster at inference, and your framework’s overhead, which was 30% of total time, is now 60% of total time because the model portion shrank. You’re *losing ground by standing still*, because every model improvement shifts the Amdahl ratio against your scaffolding. The only durable response is primitives that operate at speeds where they become negligible relative to *any* model speed. Microseconds, not milliseconds. Memory-speed, not network-speed. Persistent, not episodic.

The pattern: make the substrate dumber and faster so the model can be smarter and faster. Don’t make the old thing faster. Make a new thing that was never slow, and wasn’t designed for human consumption in the first place.


## The evidence hiding in plain sight

The METR randomized controlled trial, 16 experienced developers working on their own repos, found that AI tools made them 19% *slower*. Not faster. Slower. And the developers didn’t believe it. They estimated AI had sped them up by 20% even as the clock said otherwise.

Everyone focused on the headline: AI doesn’t help experienced developers. But look at it through the lens of what Dean is describing and a different story emerges. Those developers weren’t slow because the models were bad. The models generated useful code. The developers were slow because the *environment* surrounding the model (context-switching between the AI interface and the codebase, re-reading generated code, managing tool interactions, integrating AI output into a human-speed workflow) consumed all the gains and then some.

The model was the fast part. The human environment was the slow part. And the slow part won.

Meanwhile, companies that had already rebuilt their internal toolchains for machine-speed interaction (Google, Anthropic, the teams showing up in Jellyfish’s adoption data) were seeing massive throughput gains. Jellyfish numbers showed PRs merged per engineer increasing from 1.36 to 2.9 as AI adoption went from 0% to 100%. Google has over 30% of its new code AI-generated. Boris Cherny said Claude Code writes 80% of its own code. Same models available to everyone. Radically different outcomes.

The difference? These companies had already invested in the environment. Persistent agent sessions. Fast build systems. Purpose-built verification infrastructure. Toolchains rebuilt for machine-speed consumption. They’d lowered their tool-latency fraction in the Amdahl formula, not by accident, but because they’re building the tools and dogfooding them simultaneously. The developers in the METR study had the same fast models plugged into an unmodified human-speed environment. Of course they were slower. The environment was fighting the agent at every step.

The METR study was measuring the Amdahl bottleneck a year before Dean named it. And the lesson isn’t “AI doesn’t work.” The lesson is: AI works *to the extent that the environment allows it to*. The model is rarely the binding constraint. The tool layer almost always is.


## So what happens to the human?

This is the question the infrastructure people aren’t asking and the career people aren’t equipped to answer, because it sits at the intersection of systems architecture and organizational design. And it’s the question this piece is actually about. The tool latency math is the diagnosis. This is the prognosis.

Here’s the honest answer: the human doesn’t disappear. The human moves.

When tool latency was the bottleneck, humans could sit comfortably in the workflow loop, prompting, reviewing, iterating in real time, guiding the AI step by step. That collaborative pair-programming model worked because the tools were slow enough that human cognition could keep pace. You’d prompt. Wait for the model. Wait for compilation. Read the output. Think. Prompt again. The rhythm matched your speed. It was almost pleasant, a call-and-response between you and the machine at a tempo you controlled.

As tools get rebuilt for machine speed and agents start running autonomously for hours or days, that rhythm breaks. You can’t pair-program with something that does 200 iterations while you’re reading the output of the first one. You can’t be “in the loop” when the loop runs faster than your ability to observe it. The Superset IDE already lets you run 10+ agents in parallel, and the honest developers who’ve tried it say the same thing: “You’re converting typing time into reading time, which is usually worse.” The agents finish faster than you can review what they did.

So the human’s role shifts from *in the loop* to *above the loop* — defining the problem, setting constraints, evaluating outcomes, making the judgment calls the system can’t make for itself.

This is the migration I’ve been writing about for a year: the scarcity moves upstream. When execution was hard, execution skills were valuable. AI made execution fast and cheap, and the bottleneck shifted to knowing what’s worth executing. Problem framing. Taste. The ability to look at twelve AI-generated approaches and know which one is actually good, not because you could have generated it yourself, but because you’ve developed the judgment to evaluate it. In a world where AI can generate infinite variations, the ability to choose, to discriminate between the valuable and the expendable, becomes the scarce resource.

But Dean’s Amdahl framing adds something important to this picture. It’s not just that the human moves upstream. It’s that the human becomes a *specific kind of bottleneck* in a *specific position* in the system, and the math tells you exactly where and why.

When tool latency is 60% of the workflow, the human’s review speed doesn’t matter much because the tools are the constraint. Fix the tools and suddenly the human’s review speed *is* the constraint. Those ten parallel agents finishing simultaneously? They’re now waiting for you. You’ve become the serial bottleneck in the Amdahl formula. Your reading speed, your evaluation capacity, your ability to make judgment calls — that’s the new f.

Then you solve that: better verification infrastructure, automated testing, type-checked generation, formal proofs that reduce how much the human needs to review. Now the bottleneck moves up again. The feature is built, tested, and verified, but nobody’s decided whether to ship it. Organizational decision speed becomes the constraint. Committee meetings. Approval chains. Strategy alignment. Politics.

Each layer is a serial bottleneck that caps the speedup of everything below it. And at every layer, the question is the same: what’s the human doing here that only a human can do?

The answer keeps shifting upstream. From writing code to reviewing code to evaluating approaches to framing problems to making strategic decisions about which problems matter. And the part that should make you pay attention rather than panic: at each level, the value of the human contribution *increases* even as the total time spent on it compresses. The person who defines the right problem for a machine-speed execution pipeline is worth more per minute than the person who was writing the code manually. The leader who can encode institutional taste (what “good” looks like in their specific domain) into constraints that agents follow autonomously is worth more than the leader who was reviewing every deliverable personally.

You become the most expensive component per unit of time in the system. Which is exactly what you want to be when everything else is getting cheaper.

But, and this is the hard part, it requires different skills than the ones that got most of us here. The knowledge that made you a senior engineer, the execution speed that made you a top performer, the technical depth that built your reputation: these are all things that are migrating from scarce to abundant. What’s becoming scarce is upstream of all of them. The problem framing, the taste, the judgment, the ability to evaluate rather than produce.

I talked to someone recently who captured this perfectly. He said: “90% of my skills became useless, but the remaining 10% became worth 1000x.” That math works out in your favor if you’re honest about which 10% matters. It doesn’t work if you’re clinging to the 90%.

So what does the 10% actually look like in practice? I think the answer cuts across job titles and always has. There are about four latent traits that were always present in good teams but got masked by the fact that everyone spent most of their time on execution. When execution compresses, these surface as the actual differentiators.

The first is the person who can activate fast and ship. Call it the tool-using generalist. This is someone who can pick up an AI tool, point it at a problem, iterate quickly, and drive something to completion. Think of today’s vibe coder, but evolving beyond prototypes into directing long-running agentic processes. They’re the spark on a team: the person who says “I can get that started right now” and actually does.

The second is the person who makes the infrastructure real. Everything we’re talking about here, agentic primitives, fast pipelines, persistent environments, requires someone who understands how to build stable systems, move data securely, keep things measured and running. This is where conventional engineering and SRE roles are evolving. The vibe coder ships the prototype. The infrastructure person makes sure it stays up at 3 AM and doesn’t leak customer data.

The third is the person other people want to work with. Sales is the obvious example, but it extends to anyone whose value is relational: CX, partnerships, people operations, community. We are not going to lose the handshake dinner. People like doing business with people. Try this thought experiment: picture an agent-run company that’s doing everything right operationally, great product, fast execution, except the close rate isn’t where it needs to be. The first hire that company makes is a really good salesperson. That’s how durable the relational roles are. Even a fully agentic operation needs a human face to close the deal.

The fourth is the grown-up. Someone with the maturity to say “no, not that direction” or “yes, this inefficiency is worth keeping.” A governor on an otherwise accelerating system. You find these people in legal, finance, executive leadership, anywhere the job is to pump the brakes when the system is optimizing for speed at the expense of something that matters more. As agentic processes get faster and more autonomous, the grown-up becomes more important, not less, because the cost of a wrong direction at machine speed is enormous.

These aren’t new roles. They’re latent traits that have always cut across titles and org charts. We just didn’t need to name them when everyone was spending 80% of their time on execution. When execution compresses, the traits are what remain. And if you’re reading this list wondering which one you are, that’s the right question. Most people are some blend, weighted by experience and temperament. The point isn’t to pick a lane. It’s to recognize that the skills that will matter most aren’t the ones on your resume under “technical proficiencies.”

The developer story is the most visible version of this, but it’s not the only one. Every knowledge worker who interacts with AI tools is experiencing some version of the same shift. The analyst who used to spend three days building a financial model now needs to spend three hours evaluating whether the AI’s model is right, a different skill, a different muscle. The marketer who used to write copy now needs to develop the taste to distinguish AI copy that sells from AI copy that fills space. The project manager who used to orchestrate human execution now needs to orchestrate machine execution, defining constraints clearly enough that autonomous agents produce acceptable output.

In every case, the execution portion is getting faster and the judgment portion is getting more important. The tools and workflows surrounding the AI are the bottleneck on how fast the execution can actually go. The human who develops upstream skills (problem framing, taste, judgment, constraint definition) is becoming more valuable, not less.

The question is how fast you make the transition. Because the tool rebuild and the skill shift are happening in parallel, and the organizations that align both will have a compounding advantage over the ones that treat them as separate problems.


## What this means for how you build

I want to be concrete about this, because “the bottleneck shifts upstream” is a nice framework but it doesn’t tell you what to do on Monday. And one of the things I’ve learned is that the distance between a correct observation and useful action is usually longer than people think.

**If you’re an engineer or operator**, your competitive advantage is no longer how fast you execute. It’s how well you set up the environment for agents to execute at machine speed, and how good your judgment is when you evaluate the output. Concretely: adopt the Rust-based build tools where they exist (Rolldown/Vite 8, Oxlint, Biome, Turbopack, these are mature enough to deploy now). Use terminal-native coding agents. Claude Code for hard architectural problems where the 200K token context window lets it hold an entire codebase in working memory, Codex CLI for high-volume tasks where throughput matters more than depth. Many teams are finding the right pattern is both, matched to the problem type. Invest in persistent execution environments where agents maintain state across turns: warm compilation caches, installed dependencies, loaded context. An agent that starts cold every interaction is paying the Amdahl tax on every turn.

Most importantly: calculate your actual ceiling. Time your workflow. Measure how much is model thinking versus tool interaction. Divide one by the tool-interaction fraction. That number is your maximum AI speedup regardless of model quality. I’ve seen teams do this exercise and discover they’d been spending six figures on model APIs and A/B testing prompts while the binding constraint was a 4-minute CI pipeline and an 800ms Salesforce API with mandatory pagination. Once they saw the numbers, the investment priority inverted overnight: from model optimization to environment optimization. That shift, from obsessing over which model to use to obsessing over the speed of everything the model touches, is the single most important strategic move most AI teams haven’t made yet.

**If you’re a leader**, your job is about to change shape in a way that’s both uncomfortable and exactly what the situation requires. When agents handle execution at machine speed, the bottleneck moves to problem definition and quality judgment, what I’ve been calling institutional taste. Can your teams define problems precisely enough that an agent can execute at machine speed without constant human course correction? Can they encode what “good” looks like in your specific domain into constraints that persist and scale, not in their heads, where it walks out the door when they leave, but in systems where it compounds?

The organizations winning right now aren’t the ones with the best models. They’re the ones that have figured out how to capture and encode the domain expertise that usually lives in senior people’s intuitions. The law firm that has codified its case strategy patterns. The manufacturer whose operational knowledge of how specific production lines behave under specific conditions is embedded in the system rather than in a retiring engineer’s memory. That institutional knowledge (taste, pattern recognition, quality standards) is the new strategic asset. Models are commodities. Encoded judgment is a moat.

And there’s an organizational design implication that goes deeper: you need to protect the pipeline that develops taste. The junior positions you’re tempted to cut because AI handles the grunt work are where recognition develops. You cannot build a deep bench of people with twenty years of domain judgment if you stop hiring people at year zero. The false economy of cutting junior roles to fund AI tools is real and it’s happening, and the companies doing it are eroding the human capital that makes their AI output actually good.

**If you’re making platform decisions**, tool latency is now a first-order strategic variable. The choice of CRM, ERP, document system, communication platform, CI/CD: every one of these determines your Amdahl ceiling for every agent operating in your environment. For each tool, ask: can an AI agent interact with this at millisecond latency, hundreds of times per minute, without human-speed authentication or rate limits? Where the answer is no, you’ve found your ceiling. The interim pattern that works: pre-fetch and cache enterprise data into a local store the agent can hit at memory speed, sync on a schedule, treat the slow enterprise API as a background data source rather than a real-time dependency. You’re building a fast read-replica of your enterprise state. It’s not elegant. It works.

The Slack vs. Teams decision isn’t a chat preference. Slack supports MCP, has real-time search APIs agents can query, and has native AI connectors from every major provider. Teams routes everything through Microsoft’s own toolchain. Choosing Teams forecloses an entire class of agent capabilities. That pattern applies to every platform decision you make from here forward.

**If you’re building a company**, the white space isn’t another model wrapper. The model layer is crowded and commoditizing. The opportunity is making everything the models *touch* operate at machine speed. Enterprise tools rebuilt agent-first. Middleware that turns 800ms enterprise APIs into microsecond agent-accessible stores. Protocol-level adapters that maintain persistent connections. The companies that crack this will sell ceiling expansion, the difference between a customer’s current 1.5x AI speedup and a potential 10x. That’s an enormous amount of value sitting in plumbing nobody’s fixed yet. And unlike model companies, tool-layer companies don’t need billion-dollar training runs to compete.


## Where this goes

Let me step back from the tactical and say clearly what I think is happening here, because the tool-latency story and the human-skills story and the organizational-design story are all the same story.

We are in the middle of the most significant shift in who software serves since the invention of the graphical user interface. The GUI made computers serve non-technical humans. The web made software serve anyone with a browser. Mobile made it serve anyone with a phone. Each of these was a shift in the consumer that rebuilt the entire stack (interfaces, protocols, infrastructure, business models) around the needs and constraints of the new consumer.

AI agents are the next consumer. And they are as different from human users as human users were from the mainframe operators who came before them. They don’t have screens. They don’t have hands. They don’t take breaks. They operate at speeds that make human-calibrated latency feel like geological time. And the entire stack, the same stack that was rebuilt for GUIs, then rebuilt for the web, then rebuilt for mobile, needs to be rebuilt again for them.

There’s a pattern in the history of computing that repeats every decade or so. CPU speeds exploded, then hit the memory wall. Processors were fast but starved for data. The industry had to rethink caching, memory hierarchies, data locality. SSDs replaced spinning disks and the bottleneck moved to network I/O. Networks got fast and the bottleneck moved to software overhead. Every time, the fast part got fast and the slow part became the only thing that mattered. And every time, the industry spent years making the fast part even faster before someone noticed the returns had moved elsewhere.

We are at the beginning of the most important iteration of this cycle in a generation. The fast part, model inference, has received over $700 billion in infrastructure investment. It worked. Inference is fast, heading toward free. Dally said inference is 90% of data center power now. The model speed problem is on a clear trajectory to being solved.

That investment exposed what comes next. Every tool, every API, every workflow, every enterprise system was designed for a consumer that operates at a specific speed. That speed is now wrong by a factor of 50 and widening every quarter.

But what makes this iteration different from every previous one: the previous bottleneck shifts happened inside the machine. Memory, disk, network. Those were all components that humans never directly experienced. The shift happened behind the glass. You kept using the same interface. The machine just got faster underneath it.

This time, the shift is happening *to the glass itself*. The interfaces, the tools, the workflows, the things humans actually touch every day, are being rebuilt for a consumer that isn’t human. That’s never happened before in the history of computing. We’ve always been the endpoint. The entire software industry existed to serve us. Now we’re moving to a position above the workflow: setting direction, defining quality, making the judgment calls that determine whether the machine-speed output is actually any good.

That’s not a demotion. I say this because a lot of people are reading the tea leaves of AI and seeing their own obsolescence. It’s a promotion into the hardest and most valuable job in the system, the one where your value per unit of time is highest because everything below you is getting cheaper by the month. But it requires honesty about which of your current skills are in the appreciating category and which are in the depreciating one. And it requires investing aggressively in the skills that appreciate: problem framing, taste, judgment, the ability to encode expertise into systems that scale.

The organizations that see all of this, that invest in their tool layer with the same urgency they brought to model selection, that rebuild their infrastructure for machine-speed consumers, and that simultaneously develop the human capabilities to direct and evaluate machine-speed work, will operate at 10x or 20x instead of 1.5x.

The ones that don’t will keep shopping for better models, wondering why the 50x-faster AI only makes them marginally faster, and concluding the technology is overhyped when the real problem was always the plumbing, and the human and organizational design above it.

Dean’s track record suggests you listen when he names an infrastructure problem. He’s been right about every major systems shift at Google for two decades. But this one isn’t just an infrastructure problem. It’s the first time in fifty years that the infrastructure shift changes the human’s position in the system rather than just the system’s performance beneath us. The tools are being rebuilt for a new consumer. The question is what we become, and what we build, now that we’re no longer the thing everything was designed for.

The AI is fast enough. It’s been fast enough for a while. Now the question is whether we’re ready, our tools, our organizations, and ourselves, for a world that’s no longer built for our speed.

[![](https://substackcdn.com/image/fetch/$s_!d0Pu!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe77d5d67-55a2-4493-8af2-2c0bfcf6c096_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!d0Pu!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe77d5d67-55a2-4493-8af2-2c0bfcf6c096_1024x1024.png)
