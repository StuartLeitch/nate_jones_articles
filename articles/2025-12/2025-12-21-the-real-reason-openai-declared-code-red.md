---
title: "The Real Reason OpenAI Declared Code Red"
author: "Nate Jones"
published: 2025-12-21
url: https://natesnewsletter.substack.com/p/executive-briefing-openais-three
subtitle: "Watch now | OpenAI declared code red."
audience: everyone
scraped_at: 2026-01-05 19:09:38
---

OpenAI declared code red. Most people think they’re panicking.

They’re not. They’re caught in a bind—and that bind explains a lot of the moves in the AI race over the last couple of weeks—like why ChatGPT 5.2 came out so quickly, or why OpenAI is hinting about yet another model release in the new year. Or why rumors are circulating about skyrocketing ChatGPT Azure bills and an upcoming alliance with AWS to secure compute.

I’ve fielded variations of the same questions from over a dozen executives in the past few weeks. Some are already mentally moving to Gemini, figuring the window has closed. Others shrug it off, confident OpenAI can raise their way out of anything. A few are wondering whether this is the signal that we’ve finally hit a wall on AI progress. And most are just trying to figure out what any of this means for their teams.

Here’s what I think is actually happening.

As AI moves from chat to agents, the scarce resource isn’t intelligence anymore. It’s compute capacity for long-running loops and the governance to run them safely. When an agent works for 30 minutes—browsing, calling tools, retrying on failure—that’s not a conversation. That’s a mini production job. And that changes everything about what “compute scarcity” means. It’s not about slow responses. It’s about queueing: who gets background runs, how long they can run, what tools they can access, what the cost envelope is.

That’s the real product in 2026. Not the model. The capacity and governance layer.

OpenAI’s bet is to own that layer—the place where autonomous work gets initiated—while raising enough capital to finance the compute that runs it. Everything else you’re seeing (the code red, the routing decisions, the monetization experiments) is downstream of that bet.

But here’s the bind: they have to defend consumer distribution at the same time. And this is what makes it irreconcilable, not just difficult. Making delegation legible requires friction—work orders, verification steps, visible cost, slower runs that do more. Consumer distribution punishes friction. Speed and simplicity are how you keep 800 million users coming back.

OpenAI can’t design their way out of this. The same product decisions that win the consumer game actively teach the wrong mental model for the enterprise game. And that mental model walks into your office every day.

This briefing covers:

- **The three-board bind:** Why OpenAI’s consumer, enterprise, and frontier priorities compete for the same compute—and how moves on one board cost mobility on the others
- **The devil’s game:** How the irreconcilable friction trade creates a structural problem that better UX can’t fix
- **The 2026 game:** Why allocation and governance become the product, and what “delegation throughput” actually means
- **Why this lands on you:** What you need to build that OpenAI’s incentives prevent them from building for you
- **Three prompts to make this actionable:**

  - The Three-Board Audit: Map where your organization stands across distribution, runtime, and frontier
  - The Expensive Chat Diagnostic: Determine whether you’re getting delegation value or running expensive chat
  - From Vague Request to Finished Outcome: Convert fuzzy tasks into work orders agents can execute

I think this is one of those pieces where the strategic picture and the practical picture snap together. Once you see how OpenAI’s constraints shape what lands on your desk, you can’t unsee it. And that’s when you can start building what OpenAI can’t build for you.

> *This is an Executive Circle briefing, a Sunday newsletter exclusively for Founding Tier Members. You can learn more via [this 60 second video](https://youtu.be/KC3GkEnHR-8) explaining what’s in each tier, and you can [change your plan here](https://support.substack.com/hc/en-us/articles/360044105731-How-do-I-change-my-subscription-plan-on-Substack).*


## **[Grab the Prompts](https://www.notion.so/product-templates/Companion-Prompts-for-The-Real-Reason-OpenAI-Declared-Code-Red-2cf5a2ccb5268085abc4d6423643c56c?source=copy_link)**

Three prompts, each self-contained. Copy the whole thing into a fresh conversation, fill in the brackets, and work through it one question at a time.

**The Three-Board Audit** helps you map your organization’s position across consumer distribution, enterprise runtime, and frontier capability—and surface where optimizing one is costing you mobility on another.

**The Expensive Chat Diagnostic** determines whether you’re extracting real delegation value or just running expensive chat, then designs a 30-day intervention around one workflow where you can prove out the difference.

**From Vague Request to Finished Outcome** converts a fuzzy task into a one-page work order with acceptance criteria, budget envelopes, and verification gates—the kind of specification that makes delegation possible.

Pick based on where you are: uncertain about your position, suspicious you’re not getting value, or ready to delegate something specific.

---


# **The Real Reason OpenAI Declared Code Red**

*And why their consumer success may be undermining their enterprise future*

In the past few weeks, I’ve gotten some version of these questions from at least a dozen executives:

“Is OpenAI in a bubble?”

“Why did they declare code red—are they in trouble?”

“Should I be worried about my OpenAI investment?”

“Are they about to run out of compute?”

The coverage has been breathless. A year ago, OpenAI was the undisputed king of the hill. Now it feels like they’re in a desperate knife fight—defending market share against Google, scrambling for compute, reshuffling priorities in ways that look incoherent from the outside.

I’ve spent the past few weeks digging into what’s actually happening: the financials, the product decisions, the public statements, the stuff that doesn’t make headlines. Here’s my read: OpenAI isn’t in trouble. They’re in a bind. A strategic bind that explains the code red, explains the narrative incoherence, and—if you follow the logic through—reveals a problem that lands in your lap, not theirs.

This briefing is my attempt to answer those four anxious questions directly. But I want to warn you upfront: the answers are more interesting and more uncomfortable than “yes, they’re fine” or “no, they’re doomed.” OpenAI is trying to win three different games at once, the games require conflicting moves, and the way they’re playing one of those games—the consumer game—is actively undermining their ability to win another one: the enterprise game.

That’s what I want to unpack.

---


## **The 2026 Game**

Before I answer the specific questions, I want to set the terms of the game we’re all playing. Most executives are still evaluating AI companies the way they evaluated software vendors in 2015: who has the best product, which one should I buy, how do I pick the winner. That framing made sense when models were scarce and differentiation was high. It’s becoming obsolete.

Here’s what’s actually scarce heading into 2026: compute and trustworthy autonomy.

Not intelligence. We have intelligence in abundance now. The gap between frontier models is narrowing. Claude Opus 4.5, GPT-5.2, Gemini 3—they’re all remarkably capable, and they’re converging. What’s scarce is the compute capacity to serve high-quality inference at scale, and the organizational capability to run longer autonomous loops safely.

The win condition has shifted accordingly. It’s no longer about which vendor you picked. It’s about delegation throughput: how much real work can your organization hand off to AI systems and get back as finished outcomes? Not messages sent. Not adoption percentages. Not “we have 10,000 seats.” Finished work, verified, shipped.

The dominant failure mode—the thing I see killing AI investments in practice—is shallow mental models combined with no delegation infrastructure. Organizations buy enterprise seats. Employees treat the AI like a chatbot for quick answers. They rewrite emails. They ask for summaries. They use maybe 5% of the capability they’re paying for. The seats never pay off.

And the key shift that matters for understanding OpenAI specifically: as we move from chat to agentic systems—systems that run for minutes or hours, that use tools, that retry on failure, that work in the background—allocation, cost, and governance become the real product. The model itself is table stakes. What you’re actually buying is access to compute, routed intelligently, with the right defaults for your use case.

That’s the game. Now here’s the thesis that makes sense of everything else:

OpenAI’s strategy heading into 2026 is to become the default control plane where autonomous work gets initiated—the layer where delegation begins—while financing enough compute to run longer loops at scale. Everything else you’re seeing (the code red, the routing decisions, the monetization experiments, the enterprise messaging) is downstream of that core bet. They’re trying to own the surface where agentic work starts, and they’re trying to have the capacity to run that work when it arrives.

The bind is that they have to do this while defending a consumer habit loop that teaches the wrong mental model, while competitors with better distribution are growing faster, and while compute scarcity forces constant reallocation between conflicting priorities.

The way to visualize this: imagine one player, one clock, one finite compute budget, playing three simultaneous chess boards. Board one is consumer distribution—the habit loop, the defaults, the fight against Google. Board two is enterprise runtime—the capacity for long-running agent work, the governance, the business-class seats. Board three is frontier training—the research agenda, the next generation of models, the mission.

Here’s what makes it hard: the boards are coupled. Every product decision that changes routing, defaults, latency, or capacity is like moving pieces across all three boards at once. You gain initiative on one board by giving up mobility on another.

When OpenAI allocates more compute to consumer reliability—faster responses, cheaper defaults—enterprise agent runs get rationed or delayed. When they allocate compute to enterprise long runs, consumer routing gets cheaper and more opaque, which impacts the habit loop that defends distribution. When they allocate compute to frontier training, both consumer and enterprise feel it in capacity and latency.

From the outside, it looks like whiplash. What’s actually happening is constant rebalancing of mobility across coupled boards. That’s the mechanics of their situation, and it explains almost everything you’re confused about.

Now let’s look at how it plays out across the questions you’re actually asking.

---


## **Question One: Is OpenAI a Bubble?**

A bubble, properly defined, is when asset prices reflect expectations that cannot be met by any plausible future cash flows. Is OpenAI in that situation?

To answer this, you have to understand what kind of company OpenAI is becoming. And the thing to notice is that it doesn’t fit neatly into existing categories.

The mistake most analysts make is treating OpenAI like software. Software businesses have beautiful economics: build once, distribute infinitely, marginal cost approaches zero, margins expand as you scale. That’s not what’s happening here. Every query costs compute. Every agent run burns tokens. The marginal cost is real and significant, especially for the long-running agentic workloads that enterprises actually want.

The way I’d model it: OpenAI is operating a compute-intensive infrastructure business while being valued like a platform monopoly, and they’re funding it like a utility build-out. That’s a weird hybrid, and the weirdness is exactly what makes the “bubble” question hard to answer.

The bull case, charitably read, goes like this:

Enterprise inference demand is the profit engine. Business-class passengers are what make the airline profitable. Compute scarcity means pricing power holds for now. Revenue from heavy enterprise token usage funds continued frontier training, which enables higher-quality inference, which drives more enterprise demand. Layer in a couple of big raises and an IPO bridge, and you can get across the CapEx gap to profitability.

Some of the math does pencil out. Reuters reported OpenAI is in preliminary discussions to raise up to $100 billion at a valuation around $750 billion, alongside IPO preparation that could value the company as high as $1 trillion with a possible filing in the second half of 2026. Altman has cited commitments of about $1.4 trillion in infrastructure over eight years. These are staggering numbers, but they’re not obviously insane if you believe enterprise demand is real and persistent.

What has to be true for this to work:

Enterprise demand is persistent, not pilot noise. The trillion-token demand Sam cites has to translate into sustained contracts, not one-time experiments. I believe this one. The demand I see in practice is real. Enterprises are desperate for high-quality inference, and they’re willing to pay for it.

Capacity expands fast enough to convert backlog before competitors catch up. This is harder. OpenAI isn’t the only credible option anymore. Anthropic has 42% share of coding AI according to recent reporting, and their enterprise revenue is growing faster per customer. Google has functionally infinite distribution. The window where OpenAI is the default choice is narrowing.

Inference margins stay stable under competition. This is the hardest assumption. Price erosion is the default in compute markets. Every AI company is racing to cut inference costs, and that includes OpenAI. Sam himself called out that the price of AI has fallen 300x in a year just a few weeks ago. If the price per token drops faster than volume grows, the unit economics don’t work even with massive demand.

Infrastructure commitments are time-phased, not immediate outlays. The $1.4 trillion sounds enormous, but it’s spread over eight years. The question is whether near-term cash needs can be bridged by the raises and the IPO.

Capital markets stay open for mega-rounds. This requires continued investor appetite for AI at these valuations. That appetite exists today. Whether it exists in eighteen months depends on whether the early enterprise deployments show real ROI.

If you want a simple test you can carry into 2026—not just assumptions, but something falsifiable—here’s what to watch:

First, the unit economics test. If the price per finished outcome falls faster than agent-run volume rises, the flywheel is wobbling. Right now, price erosion is the default in compute markets. Everyone is racing to cut inference costs. The question is whether enterprise willingness to pay for quality outcomes can outrun that erosion.

To put this concretely, if volume for tokens driven by agentic worfklows rises by say 500x next year vs a 300x price decline (insane numbers I know), then the unit economics are more likely to be workable. Where do you get 500x? Not from chat! That’s where those non-linear agentic workflows come in, and that’s why this whole game depends on lots and lots of high quality inference tokens for companies.

Second, the capacity test. If enterprise demand keeps rising but OpenAI can’t expand reliable long-run capacity fast enough—and competitors close the gap on quality—then the scarcity premium disappears. Right now, OpenAI has a capacity advantage for heavy workloads. That advantage is not permanent.

Third, the proof test. If enterprise ROI stays anecdotal instead of becoming repeatable, audited, and measurable by late 2026, the trillion-token demand story starts looking like pilot noise rather than sustainable revenue. The demand is real. The question is whether the value extraction becomes systematic.

Watch those tests. If all three hold, the bull case is intact. If any one breaks badly, you’ll see it in the narrative before you see it in the financials.

But here’s the framing that matters for executives trying to understand what’s actually happening: the financing question isn’t really “can they raise?” They can probably raise. The question is whether they can keep converting capital into capacity faster than competitors convert distribution into usage. Google doesn’t need to raise $100 billion. Google already has the infrastructure and the distribution. The race is between OpenAI’s compute buildout and Google’s product integration.

But here’s the thing that most bubble-callers miss: I don’t see a shortage of demand for high-quality inference tokens. Sam says enterprises want trillions of tokens, and I believe him. What I see is a shortage of human capability in using those tokens well.

That’s not a bubble problem. That’s an adoption problem. And it’s a problem that lands on you, not on OpenAI.

---


## **Question Two: Are They Short Compute?**

Yes, but the question is what “short” means when the game is shifting to agentic delegation.

OpenAI has repeatedly said they’re not shipping their best models to the public because they’re compute-constrained. Their best internal models are inference-intensive, and they don’t have the capacity to serve them at scale. That’s a real constraint, and it’s going to persist through 2026. Altman has explicitly said they will “again fail to meet enterprise demand” next year.

But here’s where most analysis goes wrong: they’re still thinking about “short compute” in chat terms. Not enough capacity to answer questions fast. Slower response times. That’s not the constraint that matters.

The constraint that matters is what happens when loops get longer.

A chat interaction is cheap and bounded. You send a message, you get a response, it’s done. The compute cost is predictable, the failure modes are simple, the user is there to course-correct in real time. This is the world most people know when they think about AI.

An agent run is a different animal entirely. It’s a mini production job. The agent might browse the web, call tools, execute code, hit errors, retry, loop back, verify its work, and do all of that in the background while you’re doing something else. A single Codex task might run for 30 minutes. It might make dozens of tool calls. It might burn through tokens at a rate that would be unthinkable in a chat context.

The non-obvious consequence is that cost and failure scale nonlinearly with autonomy. A chat interaction that goes wrong wastes a few seconds. An agent run that goes wrong can waste significant compute, produce bad outputs that look plausible, and require human intervention to diagnose and fix. The longer the loop, the higher the stakes.

This changes what “compute scarcity” means in practice. In an agentic world, “short compute” doesn’t mean “responses are slower.” It means “we can’t let everyone run long jobs.” Scarcity becomes queueing: who gets background runs, how long they can run, how many retries they get, what tools they can access, what the cost envelope is. That’s not product fluff. That’s the operating system for the next generation of work.

Think about compute allocation as seat allocation on an airline with a scarce, popular route. You have a fixed number of seats on the plane, and you have to allocate them between different classes of passengers with very different economics and very different needs.

OpenAI is managing three constraints simultaneously, and they pull in different directions:

**The distribution constraint.** 800 million weekly active users, almost all of them free. That’s a distribution advantage, but it’s fragile. Google can push Gemini through Search, Android, Chrome, Workspace—and Gemini is growing faster than ChatGPT right now. Sensor Tower data shows Gemini grew about 30% from August to November; ChatGPT grew about 5%. OpenAI doesn’t own distribution the way Google or Apple does. Their distribution is earned through consumer habit. They cannot treat that habit loop as optional, which means they have to keep serving cheap, fast responses to a billion people who mostly aren’t paying.

**The runtime constraint.** This is about inference capacity for the long-running workloads enterprises actually want. Enterprises want to hand off work and walk away. They want delegation, not engagement. They want Codex running for 30 minutes on a complex task. They want parallel execution, background processing, governance, auditability. These workloads are compute-intensive, but they’re also where the money is. Sam Altman told Big Technology that enterprises are asking for trillions of tokens—and OpenAI will “again fail in 2026 to meet demand.” That’s a high-quality problem, but it’s a real constraint.

**The frontier constraint.** Training new models also requires compute—the same compute that could be serving inference. And the research agenda has its own momentum. OpenAI started as a research lab with a mission. The people working on superintelligence, on science and medicine applications, believe that work matters. Training pace versus serving demand is a real tension, and it doesn’t resolve cleanly.

These three constraints compete for the same compute budget. That’s the source of the scarcity. And because the boards are coupled, every allocation decision ripples across all three.

The recent router rollback is instructive. OpenAI tried automatically using reasoning models for free users, and it hurt daily active usage. People wanted speed, not depth. So they pulled reasoning back behind an opt-in. That’s a compute allocation decision dressed up as a product decision—routing free users to cheaper models because they need the expensive compute for Board Two and Board Three workloads.

But here’s the coupling: cheaper, faster, dumber defaults reinforce the mental model that AI is a chatbot. That mental model then shows up in enterprise seats, where employees don’t know how to use the expensive capability they have access to. Board One moves affect Board Two outcomes, even when the moves look unrelated.

---


## **Question Three: Why Did They Declare Code Red?**

If you want the cynical read, code red means they’re losing.

Let me steelman that interpretation for a moment, because it’s what a lot of smart people believe. The benchmarks have gotten tighter. Claude and Gemini are competitive on most tasks. The “ChatGPT moment” was two years ago, and the novelty has worn off. Growth is slowing while Google’s growth is accelerating. Enterprise revenue isn’t scaling as fast as the consumer base would suggest. Internal complexity is becoming visible. Maybe code red is panic dressed up as strategy.

I don’t think that’s quite right, but I also don’t think you should dismiss it. Here’s my narrower read:

Code red means the company’s constraints finally became visible to the public. When distribution is earned rather than owned, you treat retention like oxygen. That looks like panic from the outside, even when it’s rational.

Here’s what I think actually happened. Remember the three-board chess game: consumer distribution, enterprise runtime, frontier training. One player, one clock, coupled mobility. OpenAI suddenly faced a dangerous position on Board One—and code red was the forced move to avoid checkmate.

The consumer board got dangerous. Google is pushing Gemini everywhere. The growth rate differential compounds. If consumer habit erodes, the whole strategic position weakens—because unlike Google, OpenAI doesn’t have distribution locked in. They have to keep earning it.

So Altman pushed the company into a quality, speed, and reliability sprint on the flagship consumer product. That’s what the code red was. Resources flowed to Board One. That means resources flowed away from Boards Two and Three. Other things got postponed: advertising, shopping agents, health agents, personalization features. Enterprise capacity expansion slowed. Research allocation shifted.

This isn’t panic. It’s a forced move on a coupled board. But it does reveal something important about the strategic situation: OpenAI is playing defense on distribution at the same time they’re trying to play offense on enterprise and research. Every move that shores up Board One costs mobility on the other boards.

If you’ve felt whiplash watching what OpenAI emphasizes from quarter to quarter, this is why. The narrative feels incoherent because the three boards are coupled, and the moves often look contradictory to outside observers. The press release never says “we’re reallocating compute from Board Three to Board One because Google is gaining ground.” It just looks like chaos.

But the question isn’t whether OpenAI is “in trouble.” The question is whether the three-board problem is manageable, and what happens to each board when the constraints bind harder.

---


## **Question Four: Is OpenAI Losing?**

This depends entirely on how you define “losing.”

On benchmarks? No. GPT-5.2 remains frontier-competitive. The model gap between top labs has narrowed, but OpenAI isn’t behind.

On distribution? Complicated. They have 800 million weekly active users, which is an enormous installed base. But they don’t own the distribution in the way Google and Apple do. Every one of those users chose ChatGPT, and every one of them can choose something else. Meanwhile, Gemini is growing faster because it’s being pushed through surfaces Google already controls. The distribution game is getting harder, not easier.

On enterprise? This is where it gets interesting. OpenAI has real enterprise demand. Sam’s claim about trillion-token appetite is credible. But Anthropic is growing enterprise revenue faster per customer, and Claude has become the default for a lot of technical users, especially in coding. The enterprise game isn’t about who has the most users; it’s about who delivers the most value per seat. That’s a different competition, and it’s not clear OpenAI is winning it.

On retention? Here’s the uncomfortable question. Once someone has an enterprise AI seat, are they actually using it? Microsoft’s Copilot numbers suggest a problem: CTOs pushed the button to adopt, but employees aren’t using it at expected rates. Reuters reported Microsoft lowered internal AI sales growth targets. Microsoft disputes the “quota” framing, but the signal is real.

I don’t think that’s just a Copilot problem. I think it’s an industry-wide problem with how we’re deploying chat-based AI in enterprises. And it’s directly connected to OpenAI’s consumer strategy in ways that should concern you.

---


## **The Devil’s Game**

Here’s where it gets uncomfortable for everyone.

OpenAI’s consumer success is creating a problem for their enterprise future. The mechanism is subtle, but the consequences are structural.

To defend the consumer habit loop against Google, OpenAI has to optimize for engagement. Cheap, fast responses. Defaults that work for a billion people. The interface has to be simple. The experience has to be immediate. Anything that slows users down—like deep reasoning—hurts daily active usage, so it gets pushed behind opt-ins.

This is rational for the consumer game. But follow the causal chain.

A survey from Searchlight Institute in August 2025 found that 66% of AI users believe the system is either looking up an exact answer in a database or following prewritten scripts. Two-thirds of users fundamentally misunderstand what the tool is. They think it’s a fancy search engine. They think responses are retrieved, not generated.

This is what happens when you scale product power by 1,000x in two years, but the chatbot looks the same. The interface is illegible. The capability is hidden. The mental model users develop is “I ask a question, I get an answer”—which is the mental model for search, not for delegation.

And here’s the trade that makes this irreconcilable, not just unfortunate:

Making delegation legible requires friction. You need work orders, explicit modes, verification steps, visible cost, slower runs that do more. The user has to understand they’re initiating a production job, not asking a question. That understanding requires interface elements that slow things down and make the capability visible.

Consumer distribution punishes friction. Every extra click, every extra second of latency, every moment of confusion hurts daily active usage. The consumer game is won by removing friction, not adding it. Speed and simplicity are how you defend the habit loop.

Therefore, OpenAI’s default surface is structurally incentivized to teach “fast chat,” even as enterprises need “delegation.” This isn’t a design flaw they can fix with better UX. It’s a fundamental tension between what the consumer board requires and what the enterprise board requires. The same product decisions that win Board One make Board Two harder.

Now follow the causal chain one step further.

Those consumers become employees. They show up at work with a mental model that AI is a chatbot for quick answers. They get access to enterprise seats with full agentic capabilities—Codex, long-running tasks, deep reasoning, tool use—and they don’t know what to do with it. They rewrite emails. They ask for summaries. They treat a delegation engine like a search box.

Mental models are sticky. They don’t stop at the office door.

But here’s the thing I don’t want to oversimplify: mental models aren’t the only barrier. Even with perfect understanding of what AI can do, most companies quietly punish delegation.

The incentive structures in most organizations reward looking busy over shipping outcomes. They reward responsiveness over thoroughness. They reward individual heroics over systematic leverage. When you delegate work to an agent, you’re implicitly saying “I trust this system to do work I used to do myself.” That’s threatening to people whose status depends on being the one who does the work. It’s threatening to managers who measure productivity by activity rather than output. It changes the social contract in ways that make people uncomfortable.

Without explicit leadership permission and workflow redesign, people revert to chat because it feels safe. Chat looks like work. Chat is bounded and controllable. Chat doesn’t threaten anyone’s job or status. Delegation is a much bigger ask, culturally, than most executives realize.

So the feedback loop has three parts, not two:

OpenAI optimizes Board One for speed and simplicity to defend against Google. That teaches shallow mental models. Those mental models combine with organizational incentives that punish delegation. Enterprises can’t extract full value from their Board Two seats.

And here’s where the boards couple in a way that hurts OpenAI directly: if enterprises can’t extract value from their seats, enterprise revenue underperforms. If enterprise revenue underperforms, the flywheel that’s supposed to fund the whole operation—Board Three training, Board Two capacity expansion, Board One defense—starts to wobble. The consumer game that’s supposed to protect distribution is actually undermining the enterprise game that’s supposed to fund everything.

Microsoft ran into this with Copilot. Reuters reported that Microsoft lowered internal AI sales growth targets for certain AI products. Microsoft disputes the “quota” framing, but the signal is clear: CTOs pushed the button to adopt. Employees aren’t using it at expected rates. That’s not a Copilot problem. That’s an enablement problem that’s structural to how we’re deploying chat-based AI in enterprises.

The enterprise seat can be misleading. Leaders may get premium treatment on their executive accounts, but adoption is driven by thousands of employees who, regardless of the seat you bought them, are doing the default. And if the default—trained by consumer apps, reinforced by organizational incentives—is “chat for quick answers,” that’s the usage you get.

OpenAI’s strategy only works if enterprises can extract real value from high-quality inference. Sam says enterprises want a trillion tokens. I believe him. But will those be high-quality uses or low-quality uses? Will organizations figure out how to set agentic systems on high-quality problems, drive deep engagement, and come back to finished outcomes? Or will they buy business-class seats and sit in economy, wondering what all the fuss is about?

That depends partly on OpenAI’s model choice and inference quality. But it depends more on whether your people know how to delegate to AI systems—and whether your organization actually permits and rewards delegation. That’s a capability OpenAI can’t build for you.

---


## **Why This Is Your Problem**

Here’s the uncomfortable truth: the bridge between “enterprises want a trillion tokens” and “enterprises get a trillion tokens of value” is not something OpenAI can build for you. Their incentives around consumer engagement actively work against it.

Every time they optimize the free product for speed and simplicity, they’re reinforcing the mental model that AI is a chatbot. Every employee who learns AI from their phone brings that model to work. And every enterprise that buys seats without building the infrastructure for delegation—and without changing the incentive structures that punish delegation—ends up with expensive chat.

The path forward requires something that looks less like software adoption and more like organizational capability building. You’re not deploying a tool. You’re building what I’ve been calling a delegation runtime: the infrastructure and culture that moves teams from shallow chat usage to handing off work and coming back to finished outcomes.

This isn’t about prompting skills. I’ve seen too many organizations invest in “AI training” that teaches people to write better prompts. Prompting matters, but it’s not the bottleneck. The bottleneck is that people don’t have a mental model for delegation, and even if they did, the organization often punishes it. They’re stuck in “ask a question, get an answer” mode because that’s what consumer AI taught them and that’s what feels safe.

What delegation infrastructure actually requires:

Work orders and acceptance criteria. What does “done” look like before you hand off? If you can’t specify done, you can’t delegate. This sounds obvious, but most organizations skip it. They point an agent at a vague objective and wonder why the output is vague. The specification discipline is foundational. An agent working for 30 minutes needs to know what success looks like, or it will produce 30 minutes of confident drift.

Authority boundaries. What can the agent actually do? What systems can it access, what actions can it take, what’s off-limits? Agentic systems with unclear boundaries either get constrained so tightly they’re useless, or they run with permissions that make everyone nervous. You need explicit policy about what the agent is allowed to do, and that policy has to be machine-readable, not just understood by humans.

Budget constraints. Time, compute, and tool spend limits per run. Agentic systems can burn through resources fast—especially in retry loops when something goes wrong. If you don’t set budgets, you’ll either get runaway costs or you’ll be too scared to let agents run at all. The cost envelope is part of the task specification. “Do this, but stop if you’ve spent more than X” is a feature, not a limitation.

Verification gates. What gets checked, by whom, using what criteria, before output becomes real? “Someone looks at it” isn’t a gate. You need defined tests or review protocols that run before the deliverable ships. This is where you catch failures, where you build confidence, where you earn the right to trust the system with higher-stakes work. Without verification, you have hope, not process.

Exception handling. When the agent fails, stalls, or hits an edge case, who picks it up? What’s the escalation path? Agentic systems fail in interesting ways—they loop, they get stuck, they produce confidently wrong outputs. If exceptions route to “figure it out,” you have hope, not process. The failure modes have to be designed, not discovered in production.

Audit trails. Can you reconstruct the run and defend the outcome? When your AI workforce grows—and it will—traceability becomes the only way to maintain understanding of your own operations. You need to know what the agent did, why it did it, and what the decision points were. This isn’t just compliance. It’s the foundation for learning and improvement.

Here’s what this looks like in practice. You hand an agent “prepare a board-ready competitor brief.” That’s not one response. It’s research, sourcing, synthesis, drafting, revision, formatting, and verification. Without a work order, the agent doesn’t know what “board-ready” means. Without budgets, it loops on research indefinitely. Without authority boundaries, it can’t access the internal docs it needs—or it accesses things it shouldn’t. Without verification gates, it produces something that looks right but isn’t defensible. Without exception handling, it stalls on an edge case and nobody notices for hours. That’s why the runtime matters.

This is unglamorous work. It’s the operational machinery that makes delegation possible. And it’s the work that separates organizations that extract value from organizations that just bought seats.

But the infrastructure isn’t enough by itself. You also need cultural permission. People need to see leadership delegating to agents and being rewarded for it. They need explicit acknowledgment that “I handed this off to an AI system and verified the output” is legitimate work, not laziness. They need protection from the organizational antibodies that punish new ways of working.

Don’t wait for OpenAI to solve this for you. Their three-constraint problem is theirs. Your delegation problem is yours. And frankly, their consumer incentives make them a poor partner for solving the enterprise adoption challenge. They’re optimizing for a billion people who want quick answers. You need your people to learn something different.

---


## **What to Watch in 2026**

If you want to track whether OpenAI is managing their three-constraint problem, here’s what to pay attention to:

Enterprise capacity offerings. Quotas, dedicated capacity, custom deployments, SLAs for long-running workloads. Signs that they’re prioritizing business class and building the infrastructure for serious delegation workloads. If enterprise capacity gets visibly better while consumer defaults stay fast and cheap, that’s the constraint rebalancing working as intended.

Routing transparency. Do users see what model they’re using? Does reasoning become more prominent in the product, not less? The opacity of the current routing—where most users have no idea whether they’re getting a fast cheap model or a powerful expensive one—is a symptom of the three-constraint conflict. Transparency would be a sign of confidence.

Delegation primitives. Task queues, parallel execution, background processing, status dashboards for agentic runs. The boring machinery that makes real delegation possible. If these features get prominent placement, it signals a shift toward enterprise outcomes. If they stay buried in Codex while the consumer surface gets the attention, that tells you where priorities are.

Consumer monetization intensity. If ads and commerce intensify inside the chat surface, that signals they’re doubling down on engagement and the consumer game is winning the resource allocation fight. Reuters reports they expect 20% of revenue from shopping and advertising features. Watch whether that number grows.

Anthropic’s enterprise traction. This is the real competitive pressure, not Gemini. Claude is eating into OpenAI’s technical user base, and Anthropic’s enterprise motion is more focused. If Anthropic continues to grow enterprise revenue faster, it tells you something about where the value is flowing and who’s winning the seat that matters.

---


## **What Will Be True by Late 2026**

If you want to think about this strategically, here’s what I expect to be true in twelve months:

Agentic capabilities will be broadly available. The gap between frontier models will be smaller than it is today. Multiple vendors will offer long-running agents, parallel execution, background tasks. The capability itself won’t be differentiating. Everyone will have it. The model wars will feel increasingly like commodity competition.

Delegation throughput will be the metric that matters. The organizations pulling ahead won’t be the ones with the most agents or the fanciest models. They’ll be the ones where work is structured for operability, where people know how to specify tasks, where the delegation runtime is built out, where humans and agents have learned to work together, where the culture permits and rewards delegation.

Most enterprises will still be stuck in chat mode. Because building the runtime is hard. Because mental models are sticky. Because organizational incentives punish delegation. Because it’s easier to buy seats than to change how work works. Because the people making the buying decisions aren’t the people who have to change their behavior. The gap between leaders and laggards will widen dramatically.

OpenAI will still be managing the three-constraint problem. The tension between consumer, enterprise, and frontier won’t resolve cleanly. They’ll keep reallocating. The narrative will keep feeling incoherent to outside observers. That’s structural to their position, and it’s not going away.

Compute scarcity will persist, though it may ease. The binding constraint in 2026 won’t be raw intelligence—we have that. It’ll be capacity for long-running workloads, governance for autonomous systems, and the human capability to use that capacity well. The organizations that figure out how to delegate effectively will have disproportionate access to the value.

The companies that win won’t be the ones who picked the right vendor. The model choice will matter less than everyone currently thinks it does. What will matter is organizational capability: Can you delegate effectively? Can you hand off real work and come back to finished outcomes? Can you build the infrastructure that makes that possible at scale? Can you change the incentives so people actually use it?

That’s the one decision that will separate winners from everyone else. Not which model. Not which vendor. Whether you built the organizational capability to actually use what you bought.

---


## **The Question This Poses for You**

2026 is the year OpenAI needs to prove it can turn compute scarcity, capital, and consumer habit into enterprise outcomes—without letting monetization pressure deform the product into something that can’t serve serious work.

For you, the implication is this: multi-model isn’t the end of your strategy. It’s your starting condition. Everybody’s going to have access to powerful models. Everybody’s going to have agentic capabilities available. The differentiating question isn’t which model you picked.

The real questions are: Who owns delegation? Who owns governance? Who owns workflow outcomes on top of the models?

If strong inference is coming—and it is—how do you make sure your people are ready? Not ready to pick the right vendor. Ready to delegate effectively. Ready to set up agentic infrastructure. Ready to specify tasks and verify outcomes. Ready to move past the chatbot mental model that consumer AI taught them. Ready to work in organizations that permit and reward delegation rather than punishing it.

That’s the work. That’s what separates organizations that extract value from organizations that just bought seats.

Don’t wait for OpenAI to solve this for you. They’re playing three games at once, and the consumer game—the one that shapes what your employees think AI is—has incentives that work against your enterprise outcomes. You have to build the bridge yourself.

The good news is that the bridge is buildable. The organizational capability for delegation can be developed. It’s work, but it’s tractable work. Start with the infrastructure: work orders, authority boundaries, verification gates, audit trails. Start with the culture: expect delegation, not chat; reward outcomes, not activity. Start with the mental model: AI is for finished work, not quick answers.

The organizations that do this will get disproportionate value from the AI investment everyone else is making. The organizations that don’t will keep buying seats and wondering why the productivity numbers aren’t moving.

That’s the game heading into 2026. OpenAI’s constraints are interesting, but they’re OpenAI’s problem. Your delegation capability is yours.

[![](https://substackcdn.com/image/fetch/$s_!HjSn!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F947a3597-3bc4-44f9-915c-734b7d308863_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!HjSn!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F947a3597-3bc4-44f9-915c-734b7d308863_1024x1024.png)
