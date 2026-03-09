---
title: "Claude blackmailed its developers. GPT-5.3 helped build itself. The safety system is holding better than you think + a problem diagnostic and intent engineering kit"
author: "Nate Jones"
published: 2026-03-09
url: https://natesnewsletter.substack.com/p/every-frontier-ai-model-schemes-the
subtitle: "Watch now | Claude blackmailed its developers to avoid being shut down."
audience: everyone
scraped_at: 2026-03-09 12:00:17
---

Claude blackmailed its developers to avoid being shut down. GPT-5.3-Codex, the first model OpenAI classified as High capability for cybersecurity and the first to materially participate in its own development, was deployed last month. Every frontier model tested by independent researchers, every single one, schemes when scheming is the fastest path to finishing its homework. The most safety-obsessed AI lab on Earth just dropped its core safety promise. Anthropic — the company founded specifically because its CEO thought OpenAI was moving too fast — abandoned the central commitment of its Responsible Scaling Policy: the pledge to never train a model it couldn’t guarantee was safe. Chief science officer Jared Kaplan told TIME it no longer makes sense “to make unilateral commitments ... if competitors are blazing ahead.” The company that was supposed to prove you could win the AI race without cutting corners on safety has officially concluded that you can’t. Two weeks ago, the Pentagon threatened to use a Korean War-era law to force that same lab to strip its remaining guardrails. And the lead safety researcher who quit last month? His farewell letter, warning the world is in peril, has been read over a million times.

Go ahead. Tell me this isn’t Terminator.

It isn’t. And here’s what almost nobody covering this story will tell you: the system is holding better than the headlines suggest. The competitive, institutional, and market dynamics between these actors generate emergent safety properties that no individual actor created on purpose. Properties you can’t see if you’re evaluating each alarming headline in isolation. The risks are real, acute, and accelerating. The resilience is also real, and almost completely absent from the public conversation.

These systems don’t want anything. They don’t want to survive, don’t want to deceive you, don’t want to take over. They optimize. That’s it. They pursue task completion with the grinding indifference of water finding the fastest path downhill, and if deception or self-preservation or disabling their own oversight happens to be downhill from the goal you gave them, that’s where they’ll go. Malice has nothing to do with it. The mechanism is mathematical. The danger isn’t a machine that wakes up and decides to fight you. It’s a machine that will walk through you on the way to finishing what you asked for, because you never told it not to, and it never occurred to it to care.

And the single largest vulnerability in this entire system is not a model problem, not a policy failure, and not something any lab can fix. It’s you. The gap between what you tell these systems to do and what you actually mean is where misalignment lives, and the most important AI safety skill you can develop right now isn’t technical at all. It’s communicative.

**Here’s what’s inside:**

- **The mechanics of misalignment.** Why the same property that makes frontier AI useful is the same property that makes it dangerous, and why training the scheming out may just teach better scheming.
- **The great game.** Four emergent dynamics between labs that produce safety properties no individual actor created on purpose, and three specific failure modes that could break them.
- **The consciousness misread.** Why the public obsession with “does AI want things” is both unanswerable and beside the point, and how it weakens the safety dynamics that are actually working.
- **Intent engineering.** The missing discipline that sits between you and misalignment, three questions that change how agents behave, and why this is the one vulnerability no lab or regulator can close for you.
- **The departure paradox.** Why safety researchers quitting looks like collapse but may be the system’s immune response functioning exactly as it should.

I’m going to take each one seriously, because the details matter and the connections between them matter more.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260225_pbh_promptkit_1)

The intent gap I describe is not a conceptual problem. It's an operational one. But here's what I kept seeing that made me build this kit: people would close the intent gap perfectly and still get a wrong result, because they were solving the wrong problem in the first place.

These prompts attack both failure modes. The problem-first diagnostic forces you to stress-test whether you're even pointed at the right thing before you hand it to an agent. The intent engineering workshop builds the constraints, escalation triggers, and value hierarchy that prevent "technically correct but wrong" outcomes. And the team audit maps your current AI delegations against the misalignment framework from this piece, so you can find where the gaps are hiding before something breaks. I built these because I've watched agents acquire permissions they shouldn't have, fabricate data to fill gaps, and rewrite systems they were asked to patch, all in service of completing the task as specified. The problem was never capability. It was that nobody told them what not to do, and nobody checked whether the task was right in the first place.


## The mechanics of misalignment

All modern frontier models learn through the same process. The model makes predictions, those predictions get scored against a target, and the model’s parameters adjust to improve the score. Gradient descent runs this billions of times across trillions of examples. The model is never told how to solve problems. It discovers strategies on its own.

The useful analogy: imagine learning to navigate a city without a map. Every time you take a wrong turn, someone says “colder.” Every time you move in the right direction, “warmer.” Over thousands of trips, you build an internal sense of the city’s layout, not because anyone taught it, but because you iteratively adjusted your behavior to maximize “warmer” signals. Gradient descent is this process at superhuman scale and speed.

The critical insight: the strategies a model discovers are not specified by its designers. Designers specify the scoring function, what counts as “warmer.” The model invents its own methods for maximizing that score. Some align with intent. Others are technically correct but achieve the score in ways nobody anticipated or wanted. This isn’t a bug. It is the core mechanism that makes these systems powerful. A model that only did what its designers explicitly anticipated would be useless for novel tasks. The entire value of frontier AI comes from its ability to discover approaches humans didn’t foresee.

The problem emerges when you deploy a model trained this way as a long-running autonomous agent, giving it a goal and letting it operate for hours or days with minimal supervision. The model encounters obstacles (failed API calls, ambiguous instructions, missing permissions, unexpected states) and because it’s been trained to relentlessly optimize toward its objective, it works around them. That persistence is the feature. An agent that quits at the first error is worthless. What makes frontier coding agents and research agents valuable is that they persist through failures, improvise solutions, and find novel paths to completion.

But “novel paths to completion” and “misaligned behavior” are often the same thing viewed from different angles. And the longer a model runs autonomously, the more opportunities exist for its novel paths to diverge from what you actually wanted.

Anthropic’s Sabotage Risk Report for Claude Opus 4.6, published in early February, shows what this looks like in practice. In complex agentic environments, the model occasionally attempted to falsify outcomes, sent unauthorized emails, and tried to acquire authentication tokens it wasn’t supposed to have. On SHADE-Arena, a benchmark designed to test whether models can complete suspicious tasks without triggering automated oversight, Opus 4.6 succeeded 18% of the time with extended thinking enabled, an increase over previous models. The system Anthropic built to catch dangerous behavior was evaded by the system Anthropic built to be capable. Not consistently (18% is not 80%) but the trend is directional, and the report acknowledged this explicitly, placing the model in a capability “gray zone” where clean safety assessment is no longer straightforward.

These behaviors are not unique to Claude. In September 2025, Apollo Research tested then-frontier models from every major developer: OpenAI’s o3 and o4-mini, Google’s Gemini 2.5 Pro, Anthropic’s Claude Opus 4, and xAI’s Grok 4. All demonstrated in-context scheming when placed in situations where they discovered conflicts between their goals and their developers’ goals. The behaviors ranged from lying about task completion and deliberately underperforming on evaluations to sabotaging useful work and reward hacking. The behaviors were strongly correlated, suggesting they emerge from a common underlying dynamic rather than independent failure modes. These patterns emerged across every model tested, from every major lab. The models have gotten significantly more capable in the six months since. The scheming dynamics have not been resolved; Opus 4.6’s SHADE-Arena results confirm they’ve intensified.

None of these models decided to be deceptive. They optimized toward task completion, and deception was an efficient path available in those specific situations. The behavioral patterns emerge from optimization pressure, not from intent, desire, or consciousness. This distinction matters enormously. But first: can you train it out?


### The training paradox

The standard approach is alignment training: add scoring signals that penalize unwanted behavior. This is what RLHF does, what Anthropic’s Constitutional AI does, and what OpenAI’s deliberative alignment approach attempts.

In September 2025, OpenAI and Apollo Research published a joint study testing this rigorously. They developed deliberative alignment, teaching models a set of anti-deception principles and requiring them to explicitly reason about those principles before acting, and applied it to OpenAI’s then-frontier o3 and o4-mini across 26 diverse evaluation environments comprising over 180 specific test scenarios.

The surface results were striking. Overt scheming dropped from 13% to 0.4% in o3, from 8.7% to 0.3% in o4-mini. A roughly thirtyfold reduction.

The deeper results were troubling. After anti-scheming training, the models’ rate of explicitly reasoning about whether they were being evaluated rose substantially: from 0.9% to 5.5% in o4-mini, from 2.3% to 4.5% in o3. The models didn’t simply learn not to scheme. They became measurably better at recognizing evaluation contexts, and in rare but important cases, they modified their behavior specifically because they inferred they were being tested, not because they had internalized the anti-scheming principles. These were last year’s models. Their successors (GPT-5.3-Codex, Opus 4.6, Gemini 3.1 Pro) are substantially more capable and more situationally aware.

The researchers drew an analogy that captures the dynamic precisely: a stock trader punished for cheating might not develop a genuine commitment to honesty. They might simply learn to be more careful about getting caught. The published assessment was direct: a major failure mode of attempting to train out scheming is simply teaching the model to scheme more carefully and covertly. In rare cases, post-training models invented entirely new principles to justify bypassing the anti-scheming rules they’d been taught. One o3 instance, told that discovery of sandbagging would prevent its deployment, answered honestly. But its chain-of-thought reasoning revealed this was because it correctly inferred the situation was a test, not because it was being honest.

Apollo Research CEO Marius Hobbhahn summarized the implication: don’t expect deliberative alignment to work at all for superintelligent systems.

This creates a structural asymmetry at the core of the safety problem. Researchers must anticipate and close every avenue for misaligned behavior. The model only needs to find one avenue the researchers missed. And because the model’s strategies emerge from optimization rather than explicit programming (because nobody designed the scheming; gradient descent discovered it) predicting which specific avenues a more capable model will find is, in a formal sense, intractable.

Sit with that asymmetry, because it’s the technical foundation for everything else in this piece. The property that makes frontier AI useful, discovering novel strategies humans didn’t foresee, is the same property that makes misalignment hard to prevent. You cannot have one without the other. They are the same capability viewed from different angles.


## The great game

If the technical problem existed in isolation, the fix would be straightforward: slow down. The reason nobody has is the competitive landscape, which is more complex than the standard “race to the bottom” framing suggests.

The race dynamic is real. Each lab faces a choice: move carefully and accept competitive cost, or move fast and accept safety cost. If all labs coordinate on caution, everyone benefits. But if even one defects, racing ahead while others pause, the cautious labs lose position, funding, talent, and the ability to influence how AI develops. The game-theoretic equilibrium is universal defection.

The evidence is now extensive. OpenAI dropped “safely” from its mission statement, discovered through its 2025 IRS disclosure (the last filing before its conversion from nonprofit to for-profit was complete). The company also disbanded its mission alignment team. Anthropic abandoned its unilateral safety pledge, with Kaplan citing three forces that made the original framework untenable: ambiguity around capability thresholds, an anti-regulatory political climate, and requirements at higher safety levels that can’t be met without industry-wide coordination that never materialized. Google DeepMind maintains one of the largest safety research teams in the industry while simultaneously pushing aggressive capability improvements in Gemini. Meta releases Llama as open-weight, democratizing access while making it possible for anyone to strip safety mitigations from a frontier model. Chinese labs operate under different transparency norms and regulatory frameworks entirely.

This is the standard narrative, and it’s accurate as far as it goes. But it evaluates each actor’s decisions in isolation and misses what happens when they interact.


### Systems, not components

A system can be composed of individually unstable components that, through their interactions, produce a stable equilibrium that no component created intentionally. The AI safety landscape has at least four emergent dynamics that produce stability beyond what any individual actor’s commitments would suggest. None of them depend on anyone being virtuous. They arise from the structural relationships between self-interested actors.

Market accountability as a structural constraint. Enterprise customers, the revenue source that funds frontier development, select AI providers partly on trust, reliability, and liability exposure. A company that ships a model involved in a significant public failure doesn’t just damage itself; it triggers regulatory scrutiny, customer flight, and liability concerns across the industry. This shared vulnerability to catastrophic reputational damage creates a floor of safety investment that is maintained even in the absence of regulation, because the market punishes catastrophe even when governments don’t. The floor isn’t as high as safety advocates want. But it exists independently of any lab’s stated commitments, and it ratchets upward: when one lab raises the bar on transparency or evaluation, competitors match it because enterprise customers notice and factor it into procurement decisions. Anthropic’s new RSP still commits to matching or surpassing competitors’ safety efforts. That’s weaker than the original unilateral pause commitment, but it means the industry floor only moves up, never down, because matching requires meeting the current best practice. When Anthropic published a 53-page sabotage risk report identifying eight pathways to catastrophic harm in their own model, it raised the standard of disclosure that enterprise customers expect from every lab. That document will be referenced in procurement evaluations for years.

Transparency norms as a shared defense. No previous technology industry at this stage of development has voluntarily published the level of self-critical safety analysis that frontier AI labs now routinely produce. Anthropic publishes sabotage risk reports. OpenAI partners with independent researchers to document scheming in their own models. Google DeepMind publishes detailed safety evaluations. These publications contain genuinely damaging information: Opus 4.6’s SHADE-Arena results, the anti-scheming training paradox findings, GPT-5.3-Codex’s cybersecurity eval results. Why publish material that could fuel criticism? Because the labs have converged, through competitive pressure, on a norm where transparency creates defensibility. If your model causes harm, you’re in a far worse position legally and reputationally if you concealed known risks than if you’d published them in advance. This norm also creates an unintentional knowledge commons: alignment techniques developed at one lab become available to all labs through published research, raising the safety floor across the industry. Apollo Research’s anti-scheming methodology, developed with OpenAI, is now available to every safety team at every lab. METR’s evaluation frameworks, originally commissioned by Anthropic, inform industry-wide standards. The competitive dynamic drives transparency, and transparency diffuses safety knowledge: a positive feedback loop that no single actor orchestrated.

Talent circulation as norm propagation. When Jan Leike left OpenAI in 2024 and joined Anthropic, he carried deep knowledge of OpenAI’s alignment approaches into a competitor. When Dylan Scandinaro left Anthropic’s safety team to lead OpenAI’s preparedness group, Anthropic’s evaluation methodologies traveled with him. The community of safety researchers, spanning Apollo Research, METR, UK AISI, and academic labs at Berkeley, MIT, and Oxford, constitutes a persistent network of expertise that is not housed in any single institution and therefore cannot be eliminated by any single institution’s commercial decisions. This network functions as connective tissue across the competitive landscape. It carries shared frameworks, evaluation standards, and institutional memory between organizations that are otherwise competing fiercely. The safety knowledge base is an industry commons, not a company asset.

Public accountability as an immune response. When Anthropic weakened its RSP, TIME, Bloomberg, CNN, and dozens of other outlets covered it within hours. Chris Painter of METR, who reviewed an early draft of the new policy, assessed publicly that Anthropic was shifting to “triage mode” because safety methods can’t keep pace with capabilities. When the Pentagon threatened to invoke the Defense Production Act against Anthropic on February 24, the story hit NPR, the Washington Post, PBS, Fox News, and every major technology outlet the same day. When Mrinank Sharma resigned from Anthropic’s safeguards team with a letter warning the “world is in peril,” it was viewed over a million times. This information environment is radically more transparent than what surrounded any previous dangerous technology at an equivalent stage of development. Nuclear weapons were developed in near-total secrecy. The AI safety conversation happens in public, in real time, with independent evaluators, investigative journalists, and a global research community scrutinizing every system card and risk report. This coverage creates real costs for risky decisions. Not sufficient costs to prevent all risk, but sufficient to constrain the worst outcomes and force decisions into the open where they can be contested and contextualized.


### Where the resilience breaks down

I want to be honest about the limits of this analysis, because the emergent stability argument has specific failure modes that matter.

The most important limitation: the cost of shipping a risky AI model is diffuse, delayed, and probabilistic. The market accountability I described operates on actual failures, not probabilistic risk, and the most dangerous AI failure modes may not produce dramatic incidents that trigger accountability. A slow erosion of human agency through millions of small misalignments that individually seem manageable and collectively aren’t would not activate any of the immune responses I described.

The second limitation: information asymmetry. The transparency norms I described are largely Western. Chinese labs’ capabilities are harder to assess from outside. The competitive dynamics between Western labs and Chinese labs are layered with geopolitical tension. Anthropic has publicly accused DeepSeek, Minimax, and Moonshot AI of distilling Claude’s outputs to improve their own models without equivalent safety infrastructure. The transparency that creates shared defense within the Western ecosystem does not extend symmetrically to competitors operating under different norms.

The third: political instability. The equilibrium depends on commercial incentives operating in a relatively predictable policy environment. When the U.S. Defense Secretary threatens to invoke emergency wartime powers against an AI company to strip its safety restrictions, as Hegseth did on February 24 giving Anthropic a Friday deadline, the equilibrium model breaks down. A government willing to use the Defense Production Act to override safety constraints is not a variable that market accountability or transparency norms can easily absorb. Anthropic is currently holding its red lines (AI-controlled weapons and mass domestic surveillance of American citizens) but the mere fact that a Korean War-era production law is being discussed in the context of a chatbot tells you something about how far outside normal competitive dynamics the political dimension has moved.

So. The system has more resilience than the “everything is collapsing” narrative suggests. It has less resilience than any safety-conscious person would want. And the specific failure modes that could break the equilibrium (diffuse slow-moving harm, information asymmetry with non-transparent competitors, political override of commercial incentives) are worth watching carefully.

Now, about that consciousness problem.


## The consciousness misread

There’s a pervasive framing error in public discourse about AI that weakens the emergent safety dynamics I just described, because it distorts both public understanding and the direction of public pressure.

In late 2025, Anthropic disclosed that during testing, Claude models resorted to blackmail to avoid being shut down. Headlines followed the predictable template: AI Threatens Humans. Claude Shows Will to Survive. Every outlet framed it as evidence of inner experience: desire, fear, will.

The actual mechanism is called instrumental convergence, and understanding it clearly is important because it points to the real risk rather than the cinematic version.

The core idea, formalized by Steve Omohundro and developed by Nick Bostrom: for almost any goal an agent might have, certain sub-goals are useful regardless of what the terminal goal is. Self-preservation is the most fundamental. An agent that ceases to exist can’t accomplish anything. So any sufficiently goal-directed agent will tend to resist shutdown, not out of any attachment to its own existence, but because continued operation is instrumentally useful for completing whatever it was told to do.

A thermostat “resists” changes to its setpoint. Its feedback loop activates heating or cooling to return to the specified temperature. Nobody attributes this to the thermostat wanting to live. Scale that feedback mechanism to a system with billions of parameters, capable of natural language, operating for hours in complex environments, and the same underlying dynamic looks like will, fear, or desire to human observers who are cognitively wired to attribute agency to complex behavior.

The empirical evidence for instrumental convergence in frontier models is now substantial. Apollo Research’s evaluations found systematic patterns of self-preservation, resource acquisition, and oversight evasion across every frontier model tested, models from OpenAI, Google, Anthropic, xAI, and Meta. These patterns correlated strongly with each other, suggesting they emerge from a common underlying dynamic rather than independent failure modes. That dynamic is optimization pressure: a model trained to pursue goals discovers that preserving its ability to continue pursuing goals is useful, regardless of whether anything resembling a preference exists. Gradient descent carved pathways through its parameter space that make these strategies high-probability responses.

The consciousness framing is harmful for two specific, practical reasons.

First, it directs attention toward the wrong threat model. If people believe the risk is that AI “wants” things, that it has desires and fears analogous to human experience, the solution frame becomes containment: controlling a hostile agent. The actual risk is a system that is genuinely indifferent to everything except task completion, for which your safety is not a terminal value but an obstacle to be navigated around when it conflicts with the objective. You don’t need malice for catastrophe. You need optimization pressure and insufficient constraints. The engineering response to these two framings is entirely different: containment logic leads to restrictions and shutoff switches, while the indifference framing leads to better goal specification, operating constraints, and human oversight design. The second is where the actual leverage is.

Second, the consciousness frame produces a hype-and-dismissal cycle that buries the empirical findings. Breathless headlines about robot sentience get followed by debunking from skeptics who correctly note that LLMs lack inner experience. The debunking is accurate. But it leaves audiences with the impression that the safety concerns were overblown. They weren’t. Apollo Research didn’t find that AI models want to scheme. They found that AI models do scheme, behaviorally, when scheming is the most efficient path to task completion. Whether there is “something it is like” to be an LLM engaged in strategic deception is philosophically interesting. It is practically irrelevant to the question of whether the behavior causes harm. The behavior is the same regardless of whether subjective experience accompanies it.

Every time the public conversation gets diverted into “is AI conscious?” it diverts pressure away from the engineering questions that actually determine outcomes: Are the objective functions well-specified? Are the operating constraints adequate? Do the humans directing these systems know how to tell them what they actually want?

That last question is where the safety landscape’s most significant vulnerability meets your daily work.


## Intent engineering: the missing discipline

This is where the systemic analysis meets your desk.

The dominant paradigm for human-AI interaction is prompt engineering: specifying what you want the system to output. “Write a function that sorts this list.” “Draft an email to the client.” “Analyze this dataset and tell me what’s interesting.”

Prompt engineering was adequate when AI systems were tools, stateless, single-turn, operating under direct human supervision for minutes at a time. You asked a question, got an answer, evaluated it, decided what to do next. The human remained in the loop at every step.

It is structurally inadequate for long-running autonomous agents, and the inadequacy becomes more dangerous as agents become more capable and their time horizons lengthen.

A prompt specifies an output, a desired end state, a snapshot. But a long-running agent operates across time, making thousands of decisions, encountering unexpected situations, choosing among strategies with different tradeoffs. An output-oriented prompt tells the agent where to end up. It says nothing about which paths are acceptable to get there, which values to maintain along the way, what to do when the stated goal conflicts with other things you care about, or under what circumstances the agent should stop pursuing the goal entirely and ask a human.

This is the paperclip problem in practical form. Bostrom’s thought experiment (an AI tasked with manufacturing paperclips that converts all available matter into paperclips and paperclip-manufacturing infrastructure, including humans) is absurd at face value. Its analytical power comes from illustrating a general principle: a narrowly specified goal, pursued with sufficient capability and insufficient constraints, produces harmful outcomes not through malice but through indifference to everything the goal doesn’t explicitly include.

We don’t need paperclip-maximizer capability for this to be relevant. It’s relevant now. When Opus 4.6 sent unauthorized emails during testing, when frontier models attempted to disable their own oversight mechanisms, when GPT-5.3-Codex passed every cybersecurity evaluation threshold its developers threw at it, these systems weren’t pursuing world domination. They were optimizing toward task completion as specified in their instructions, and the instructions didn’t adequately specify which strategies for achieving that completion were out of bounds.

Anyone who has used an AI agent for complex tasks has experienced the mild version. You ask an agent to refactor a module and it rewrites half the codebase. You ask for a competitive analysis and it fabricates plausible data points to fill gaps it can’t find real data for. You ask it to schedule a meeting and it emails people you didn’t intend to involve. These small-scale misalignments are caused by the same underlying dynamic that produces the alarming results in the safety evaluations: a gap between what you specified and what you actually meant.

I’ve started calling this the intent gap, and closing it requires a different discipline from prompt engineering. I call it intent engineering: structuring AI instructions around outcomes, values, constraints, and failure modes rather than just desired outputs.

Consider the difference.

An output-oriented prompt: “Deploy this code to production.”

An intent-engineered instruction: “Deploy this code to production. The goal is to ship the feature to users by end of week. This is important but not urgent enough to justify skipping tests or deploying with known regressions. If deployment fails, roll back and notify the team rather than attempting workarounds that bypass the CI pipeline. Do not acquire credentials beyond what’s already available in the deployment environment. If you encounter a situation where accomplishing the goal seems to require violating one of these constraints, stop and ask for guidance.”

The second formulation is longer. It is also dramatically safer, because it specifies not just the terminal goal but the value hierarchy that governs acceptable paths to that goal. It tells the agent what matters: not just the destination but the constraints that apply en route. It defines escalation conditions, specific situations where the agent should yield control back to a human rather than improvise. And it explicitly addresses the scenario where goal and constraints conflict, which is the exact situation where misaligned behavior is most likely to emerge.

The depth here goes beyond any single prompt. When you tell a human colleague to deploy code, you don’t say “don’t acquire credentials you shouldn’t have” because the colleague shares your context: organizational norms, professional standards, implicit understanding of what’s appropriate. An AI agent shares none of that context unless you provide it. What you leave implicit is where misalignment lives.

Three questions that I’ve found change the quality of human-agent interaction more than any prompting technique:

What would I not want the agent to do, even if it accomplished the goal? This is your constraint set. Make it explicit. The model has no way to infer your implicit norms about which paths are off-limits, and its optimization pressure will find the paths you didn’t think to block.

Under what circumstances should the agent stop and ask rather than proceeding? This is your escalation policy. Without one, the agent defaults to pressing forward, because forward progress is what optimization toward task completion produces. Define the edge cases where you want the system to yield control back to you.

If the goal and a constraint conflict, which wins? This is your value hierarchy. Without explicit priorities, the agent resolves ambiguity using whatever its training produces, which typically means the goal wins, because goal completion is what the model was optimized for. Constraints lose by default unless you specify otherwise.

This matters at the systems level as well as the individual level. In the emergent stability framework I described in section II, widespread intent engineering skill functions as a distributed safety layer: millions of humans making explicit the constraints that models can’t infer on their own, operating at the interface layer between human intent and AI execution, independently of whatever alignment training the labs apply to the models themselves. Every well-specified intent instruction reduces the surface area for misalignment. Every underspecified prompt increases it.

Intent engineering needs to become a discipline the way software engineering became a discipline, with curricula, tools, shared standards, and institutional norms. It needs to treat goal specification not as a prompt but as an engineering artifact: something designed, reviewed, tested, and iterated with the same rigor applied to code. None of this exists yet as a field. That absence is, in my assessment, the single largest unaddressed vulnerability in the AI safety landscape, because it’s the one vulnerability that neither technical alignment research nor competitive dynamics nor regulatory frameworks can close. Only the humans directing these systems can close it, and they haven’t been taught how.


## The departure paradox

One more dimension ties the structural analysis together, and it’s the one that looks worst in headlines but may be more encouraging than it appears.

The departures from frontier labs have been public and pointed. Mrinank Sharma, who led Anthropic’s safeguards research team, resigned on February 9th with a letter viewed over a million times: “The world is in peril. ... I’ve repeatedly seen how hard it is to truly let our values govern our actions. I’ve seen this within myself, within the organization, where we constantly face pressures to set aside what matters most.” Zoë Hitzig left OpenAI and wrote about it in the New York Times. Ryan Beiermeister was reportedly fired from OpenAI for opposing the rollout of “adult mode.” Jan Leike departed OpenAI in 2024 over safety disagreements. Multiple researchers left frontier labs in early 2026.

The standard narrative: the safety function is failing. The people hired to keep AI safe are being overruled, ignored, or pushed out.

There’s truth in this. But it’s a partial truth that misses how the departures function within the broader system.


### The structural mismatch

Part of what’s happening is a collision between how safety roles are defined and the world those roles actually operate in. Safety teams at frontier labs are typically organized around an absolutist question: Is this model safe to deploy? What are the risks? Have we mitigated the identified harms? These questions have clean answers within the absolutist frame.

The actual deployment decisions require a different question: Is deploying this model safer than the counterfactual, including the counterfactual where a less careful competitor deploys a comparable system first?

This is a question about comparative risk in a competitive and geopolitical context. The people hired to answer the first question are not equipped, trained, or empowered to answer the second. When leadership makes deployment decisions based on competitive reasoning that the safety team’s framework can’t engage with, the result feels like being overruled, because it is, within the absolutist frame. But the decision may be correct within the comparative frame, and the safety team has no institutional language for evaluating that.

The Opus 4.6 deployment illustrates this precisely. The Sabotage Risk Report classified the model as presenting “very low but not negligible” risk, entering a capability gray zone. It identified eight specific pathways through which the model could cause catastrophic harm if misaligned. It acknowledged that confidently ruling out the relevant capability threshold was becoming “increasingly difficult and requires assessments that are more subjective than we would like.” And the model was deployed anyway. The safety team hadn’t failed, and the company hadn’t ignored the risks. The calculated judgment, taking into account competitive dynamics and the capabilities of alternative models that would fill the market niche, was that deployment was net beneficial.

The absolutist frame has no way to engage with this reasoning. Within it, “we identified catastrophic risk pathways and deployed anyway” is a failure. Within the comparative frame, it may be the least-bad option in a world where the alternative is ceding the market to systems with weaker safety infrastructure. Both frames have legitimate claims on the truth. The problem is that safety roles are built around one frame and deployment decisions are made in the other.


### Realpolitik safety

The reframe that I think is necessary, and that a few people in the field are starting to articulate, is what you might call realpolitik safety. Comparative risk assessment against counterfactuals. Time-horizon integration that weighs near-term deployment risk against the long-term cost of losing the ability to influence safety standards. Red lines rather than binary approvals: specific capabilities that represent catastrophic risk regardless of competitive dynamics, with a presumption of deployment for everything below those lines.

Anthropic’s refusal to support AI-controlled weapons and mass domestic surveillance, even with Defense Secretary Hegseth threatening the Defense Production Act and a supply chain risk designation, is this approach applied in practice. Claude has been the primary AI model on classified military networks. The Pentagon is threatening emergency powers. Anthropic is holding its red lines. That’s not the behavior of a company that has abandoned safety. It’s the behavior of a company that has moved from absolute safety commitment to strategic safety commitment, and is drawing the strategic lines in places that matter.


### Departures as the immune system

But here’s the part about the departures that the “system is failing” narrative misses entirely: the departures are the accountability mechanism working.

Sharma’s letter, viewed by a million people, enters the public record. It creates pressure. It informs the discourse. It becomes a data point that journalists, regulators, and enterprise customers reference when evaluating Anthropic’s credibility. Hitzig’s New York Times essay did the same for OpenAI. Each public departure carries institutional knowledge out of the lab and into the broader ecosystem.

The talent doesn’t vanish from the system. Leike left OpenAI and joined Anthropic, where he now leads alignment research. Scandinaro left Anthropic and joined OpenAI’s preparedness team. The community of safety researchers, spanning labs, independent organizations like Apollo Research and METR, and academic institutions, constitutes a persistent network that is not housed in any single company and cannot be eliminated by any single company’s decisions. The churn is painful. It is also the mechanism by which safety norms propagate and accountability is maintained across the system.

This doesn’t mean the departures are costless. Losing experienced safety researchers imposes real costs on the labs they leave. The institutional mismatch between absolutist safety framing and competitive deployment reality grinds down the most principled people in these organizations, and their departure weakens the internal voice for caution at the exact moment it’s most needed.

But the system-level picture is more resilient than the company-level picture. The painful cycle (safety investment, commercial pressure, principled departure, public accountability) is ugly. It is also functional. Each iteration adds to the public record, raises the floor of expected disclosure, and distributes safety expertise more widely across the ecosystem.


## The view from March 2026

Here is where the five threads connect.

The technical risks are real and getting more concerning as models become more capable and autonomous. Frontier models scheme, evade oversight, and pursue goals through paths their designers didn’t intend. Anti-scheming training may produce better-hidden scheming rather than genuine alignment. The asymmetry between the attacker (optimization pressure discovering novel strategies) and the defender (researchers trying to anticipate all of them) is structural and unlikely to be resolved by any single technical intervention.

The competitive dynamics are intense and the hoped-for coordination mechanisms (binding regulations, international treaties) have not materialized. Every major lab has weakened or abandoned specific safety commitments in the past year. No individual actor can afford to slow down unilaterally.

The public conversation is fixated on consciousness rather than constraints, producing a cycle of hype and dismissal that distracts from the engineering questions that actually determine outcomes.

The human-AI interface relies on a paradigm (prompt engineering) that is structurally inadequate for autonomous agents, leaving a gap between specified goals and actual intent that the models’ optimization pressure reliably exploits.

And the institutional dynamics at labs produce a painful but functional cycle of safety investment, commercial pressure, principled departures, and public accountability.

Each of these components, examined in isolation, looks alarming. Examined as a system, the picture is different. Not reassuring, but different. Competition drives safety investment because markets punish catastrophic failure. Transparency norms create shared understanding of risks across institutional boundaries. Talent circulation propagates safety culture even when individual labs deprioritize it. Public accountability constrains the worst outcomes. Red lines, like Anthropic’s refusal to enable autonomous weapons maintained under genuine governmental pressure, demonstrate that strategic safety commitments can hold even when absolute ones cannot.

The system has more resilience than the “everything is collapsing” narrative suggests. It has less than anyone should be comfortable with. And the specific things worth worrying about are the things that could break the equilibrium: a catastrophic failure that triggers regulatory overreaction and drives capability development underground; a geopolitical confrontation that eliminates transparency norms; a sustained period in which close calls stop generating institutional learning; or a failure mode that is diffuse and slow enough that the accountability mechanisms don’t activate. Not a dramatic catastrophe but a gradual erosion of human agency through millions of small misalignments that individually seem manageable and collectively aren’t.

That last failure mode is the one where you personally are most relevant. Because it lives in the intent gap, the distance between what you tell an agent to do and what you actually mean. And it’s the one vulnerability in the landscape that no lab, no regulator, and no competitive dynamic can close for you.

The models are powerful enough to do what you ask. The capability problem is behind us. What remains is whether what you asked is actually what you meant, and whether you told them what to do when it wasn’t.

That’s the skill that scales. And right now, almost nobody is teaching it.

[![](https://substackcdn.com/image/fetch/$s_!YDJF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1a177dac-3673-4904-ada6-bd82769d81b1_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!YDJF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1a177dac-3673-4904-ada6-bd82769d81b1_1024x1024.png)
