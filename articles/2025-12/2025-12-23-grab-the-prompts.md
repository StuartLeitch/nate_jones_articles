---
title: "GRAB THE PROMPTS"
author: "Nate Jones"
published: 2025-12-23
url: https://natesnewsletter.substack.com/p/if-a-former-deepmind-engineering
subtitle: "Watch now | That's right folks--even the smartest people can fall into the AI overconfidence trap. Here's how to make sure you stay sane (and yes, there are prompts)."
audience: everyone
scraped_at: 2026-01-05 19:09:32
---

“Not suffering from psychosis.”

That’s what David Budden wrote on X, responding to the pile-on after he announced he’d essentially cracked one of mathematics’ seven hardest unsolved problems — using ChatGPT and formal verification tooling.

I admint I thought to myself, “If you’re in a situation where you have to tweet that to the world, you’re already in a pretty bad place.”

Budden has a PhD from Melbourne, postdocs at MIT and Harvard, six years at DeepMind rising to Director of Engineering, and a serious publication record. He is not a crank. And yet he’s put $45,000 (across three public bets) on an outrageous claim: that he can resolve not one but two Clay Millennium Prize problems with AI assistance.

The money is split across three public bets: $10,000 against Marcus Hutter and $10,000 against Isaac King on Navier-Stokes, plus $25,000 against University of Toronto mathematician Daniel Litt on the Hodge Conjecture. He announced this as his new company PingYou came out of stealth — which has people debating whether this is sincere conviction, attention-seeking, or both.

The mathematical community’s response has been swift and brutal. The critique isn’t just “wrong” — it’s that his Lean code may formalize a trivial or different version of Navier-Stokes, not the actual Clay problem. Basically, this math problem is so complicated, he may claim he solved it while solving the easy-mode version instead.

One explicit failure mode listed in the prediction markets: “the Lean proof could compile while proving a different or weaker statement than the Clay Millennium problem.” The public resolution criteria are measured in months, not vibes — one market resolves on whether he’s actually solved Navier-Stokes by end of January 2026. Current odds: single digits. And I think that’s high.

Budden’s story is one example of a debate spreading faster than the math debate: the conversation around the term “LLM psychosis.” Yes, there’s no settled definition, but online, people are using it as shorthand for a real workflow failure — when an AI system that’s good at producing plausible explanations pushes users into overconfident acceptance of outputs they can’t audit. That’s a fancy way of saying: when AI convinces you you’re right about something you cannot know.

I’m not using “psychosis” clinically here. I’m pointing at a collapse in some people’s ability to know the edges of their competence because AI fools them.

The real question isn’t whether Budden is right. It’s what happened to his ability to evaluate his own work. Especially as a founder, that’s a question relevant for his whole team at this point. And it’s increasingly a question we should be asking of ourselves, our leaders, and our teams.

**Here’s what’s inside:**

- **Why LLMs make automation bias worse than traditional systems** — research shows AI explanations increase trust even when completely wrong, and the most vulnerable people aren’t novices
- **Three warning signs this pattern is developing** — confirmatory prompting disguised as verification, operating beyond your evaluation capacity, and the “me and the AI versus everyone else” dynamic
- **What to do about it** — the specific questions to ask before trusting any AI-assisted conclusion, plus a full adversarial prompt framework for ongoing work
- **What to watch for in your organization** — behavioral signals that someone’s judgment is being compromised by AI validation loops
- **Prompts to check your work —** these 10 prompts are designed to act as a detailed set of screens that check your work with a helpfully adversarial grounding. Basically, they’re designed to give you the tools to have the LLMs do professional quality grading on your own work so you don’t fool yourself!

  - **Adversarial Mini-Check** — quick pre-ship attack and calibration checklist
  - **Before You Start** — sets adversarial rules and evidence discipline
  - **Audit Boundary Check** — identify needed verification skills and reviewers
  - **Disconfirmation Pass** — structured attempt to break the conclusion
  - **Reality Check** — anticipate expert objections without fake consensus
  - **Confidence Calibration** — score certainty; define tests to raise confidence
  - **Final Gate** — commit/no-commit decision with stop conditions
  - **Project Ground Rules** — enforce correctness-first behavior across sessions
  - **2-Minute Reality Check** — fast grounding, falsifiability, next action
  - **Full Assessment** — deep anti-spiral review before high-stakes moves

In 2026, a lot of smart people armed with LLMs and formal tools will ship convincing-looking but wrong work faster than many of our teams can audit it. That’s the risk. What I’m putting together here is your early warning radar so you see it coming!

Let’s dig in.


# **[GRAB THE PROMPTS](https://www.notion.so/product-templates/DRAFT-LLM-Psychosis-2d15a2ccb526802aa5cae12efb5da6fb?source=copy_link)**

Asking AI to “check your work” is worthless. You’re asking a completion engine optimized for agreement to validate conclusions you’re already attached to.

The problem isn’t just running a checkpoint at the end. By then, you’re already attached to the answer. The real fix is building adversarial dynamics into how you work with AI from the start.

These prompts create friction. They slow you down. They make AI assistance less fun because you’re constantly questioning whether you’re right instead of enjoying the feeling of being right.

That’s the point.

The failure mode we’re trying to prevent is precisely the state where AI assistance feels great — where you’re generating sophisticated-looking output, where the AI is validating your conclusions, where you feel like you and the AI have figured out something that others haven’t.

That feeling is the warning sign.

The goal isn’t to never use AI for hard problems. The goal is to maintain the ability to recognize when you’re wrong — which means building in systems that actively resist the confidence the AI naturally generates.

David Budden probably felt great about his Navier-Stokes work. The AI probably validated his approach repeatedly. The prompts above are designed to prevent that feeling from overriding the reality that every actual expert sees the problems immediately.

> Note: these prompts are not intended to substitute for a clinical diagnosis of any sort. As far as I am aware, there is no formal diagnosis (yet) for LLM-induced psychosis. I believe it is overwhelmingly likely that there will be within half a decade.
>
> In the meantime, that doesn’t mean it isn’t happening and we shouldn’t take it seriously. Think of these prompts as early warning signals that can help you if your LLM is affirming you too much. There is no perfect prompt, since any prompt can be shotgunned by a human that wants to mis-use it, but these are a start.


### **Why these prompts?**

Well, put simply these prompts are designed to map to classic human-LLM failure modes. Ways we work together that lead to real problems because we fool ourselves.

**Failure Mode 1: Confirmatory prompting disguised as verification**

The fix is redefining what “check my work” means. When I ask for validation, I’ve instructed the AI to treat that as a signal to attack. The prompts explicitly separate “help me feel confident” from “help me be correct.”

**Failure Mode 2: Operating beyond verification capacity**

The Domain Expertise Audit forces an explicit checkpoint: do I have the expertise to evaluate this output? If no, the prompt requires naming who does. It creates friction before proceeding with conclusions I can’t verify.

**Failure Mode 3: “Me and the AI versus everyone else”**

The Consensus Check forces engagement with expert opinion. It asks directly: if I’m contradicting established consensus, what’s my justification? It makes isolation from expert feedback visible rather than invisible.

Now, let’s get into the long read…

---


# **The Science of Trusting Machines Too Much**

Automation bias — the tendency to over-rely on automated systems — isn’t new. Psychologists have documented it since the 1990s. It’s contributed to fatal errors in aviation when pilots trusted faulty instruments over their own senses, friendly-fire incidents when soldiers deferred to targeting systems flagging the wrong coordinates, and diagnostic errors when doctors accepted flawed algorithmic recommendations over clinical judgment. A November 2024 report from Georgetown’s Center for Security and Emerging Technology identified automation bias as one of the core risks of AI deployment, noting that “human-in-the-loop cannot prevent all accidents or errors.”

LLMs make this worse in a specific way. Traditional automation bias occurs with systems that give binary outputs. A GPS says turn left. A diagnostic tool says probable cancer. You can accept or reject, but the interaction is transactional.

LLMs have conversations. They explain their reasoning. They respond to pushback with more reasoning. And here’s the trap: even explanations with no basis in the model’s actual working can increase trust. Fluent rationales feel like verification. A Microsoft Research literature review on overreliance confirmed this — detailed AI explanations lead users to trust outputs more, regardless of whether those explanations reflect how the model actually arrived at its answer.

Here’s the counterintuitive part: the people most vulnerable aren’t novices. Research from Horowitz and Kahn found that people with moderate AI knowledge are most prone to over-reliance. They know enough to be impressed. They don’t know enough to spot failures. People with minimal AI background tend toward skepticism. People with extensive AI knowledge showed the most balanced reliance — they understood both capabilities and limitations. The dangerous middle ground is knowing enough to trust, but not enough to verify.

Budden fits this profile. World-class expertise in machine learning systems. No formal training in the mathematics he’s now claiming to revolutionize.

The meme label spreading online — “LLM psychosis” — is sloppy and in no way clinical, but it names something real: an AI system good at producing plausible explanations can push users into overconfident acceptance of outputs they can’t audit. This isn’t clinical psychosis. It’s verification collapse. And it’s happening to credentialed people, not just random internet posters.

Budden isn’t isolated. Daniel Litt — the mathematician who took his $25,000 bet on the Hodge Conjecture — wrote in July 2025 that 75% of recent arXiv papers mentioning the Hodge Conjecture are “LLM-generated nonsense, replete with hallucinated references.” The flood is already here. Budden just made a bigger splash.

The live question being argued online isn’t really “Did he solve Navier-Stokes?” — the consensus is almost certainly no. The question is: **Are we entering an era where smart people armed with LLMs and formal tools generate convincing-looking but fundamentally off-track work faster than institutions can audit it?**

That’s the question that should concern you.


### **Three Warning Signs**

I’ve been watching this pattern develop over the past year. Three warning signs keep appearing.

**Asking the AI to confirm rather than challenge.** When you ask an LLM to “check your work,” you’re not getting verification. You’re getting sophisticated agreement. The AI will generate plausible-sounding reasons why your conclusion makes sense. That’s what it’s optimized to do — a completion engine trained on human approval signals. Telling you you’re wrong feels like a failure mode to the system, even when you’re catastrophically wrong.

The Budden prompts that have been shared publicly show classic confirmatory framing — requests for the AI to validate conclusions, not attack them. People ask the AI to review their work, the AI says it looks good with perhaps some minor suggestions, and they interpret that as independent validation. It’s not. You asked a mirror if you looked good. The mirror said yes.

Actual verification means explicitly prompting for disconfirmation. Steelman the case that this is completely wrong. What are the three most likely failure modes? What would a hostile expert say? Find the weakest link and attack it. If you’re not actively seeking disconfirmation, you’re seeking validation. The AI will provide whichever one you’re actually asking for.

**Operating beyond your verification capacity.** AI can generate sophisticated-looking outputs in domains where you cannot evaluate correctness. If you’re not a mathematician, you cannot assess whether a Lean proof works. If you’re not a lawyer, you cannot assess whether an AI-generated contract has fatal flaws. The AI’s assurance that something “looks correct” is meaningless — you’re asking the same system that generated the output to evaluate the output.

Budden’s domain expertise is ML engineering. He built systems at DeepMind. He understands how language models work at a technical level. But he’s asking those models to solve problems in formal mathematics — a field where he cannot independently verify results.

This is exactly the failure mode mathematicians are flagging. The prediction markets on Manifold explicitly list “wrong problem / formalization error” as a leading outcome — the Lean proof could compile while proving a different or weaker statement than the actual Clay Millennium problem. A professional Lean developer who examined his code concluded it was likely AI-generated. The people who actually work in formal verification could see immediately what Budden apparently could not.

The test before trusting any AI-assisted conclusion: if this were subtly wrong, would I catch it? If no, you need human expert review. Not AI review. A human with domain expertise who can catch errors that would sail past both you and the model.

**The “me and the AI versus everyone else” pattern.** Navier-Stokes has resisted mathematicians for over a century. Terence Tao — Fields Medal winner, plausibly the greatest living mathematician — has published extensively on approaches to the problem without claiming a solution. The mathematical community has collectively spent millions of hours on these Millennium Prize problems.

When the mathematicians who’ve examined your proof say it’s flawed, when no recognized authority has publicly endorsed it, and your response is to write “Not suffering from psychosis” while doubling down — that’s not bold thinking. That’s a warning sign.

Watch for increasing isolation from peers, dismissal of expert criticism as “not understanding the new paradigm,” treating the AI as a validating partner rather than a tool. Pay attention to escalation. Budden didn’t bet on one Millennium problem. He bet on two unrelated ones. Navier-Stokes is about fluid dynamics. The Hodge Conjecture is about algebraic geometry. Solving both in the same timeframe would be like winning the Nobel Prize in Physics and the Fields Medal simultaneously — except harder, because these problems have been open for decades longer than a typical Nobel-winning discovery takes.

The escalation from one bet to three, totaling $45,000, suggests something beyond confidence building on success. It suggests a feedback loop where the AI’s validation is reinforcing beliefs faster than external reality can correct them.


### **The Expertise That Will Matter**

In 2026, the bottleneck isn’t drafting the contract. It’s auditing the contract.

This is what makes LLMs different from previous automation. A unit test can verify a narrow claim. A proof checker can verify a proof — if the theorem statement actually matches the real-world requirement. A compiler can verify syntax and types, not intent. LLMs solving open-ended problems — generating legal arguments, producing mathematical proofs, drafting strategic recommendations — cannot verify their own correctness. They can produce outputs that look right. They cannot prove those outputs are right. And their self-critique is just more generation, not actual verification.

Budden can get an LLM to generate a Lean proof that compiles. What he cannot do — because he lacks the mathematical training — is verify that the proof actually addresses the Clay Millennium problem rather than some adjacent or trivial formalization. The production was easy. The verification is where he’s blind. Formal tools made his output look more legit. They didn’t make it more correct.

This is the shape of expertise that will matter going forward. Not “can you produce this output” but “can you verify this output is correct.” The person who can evaluate whether an AI-drafted contract actually protects the client will be more valuable than the person who can prompt an AI to draft contracts. The analyst who can spot when an AI-generated financial model has embedded a fatal assumption will matter more than the one who can produce models faster.

Three capabilities will define valuable expertise in an AI-augmented environment:

**Correctness intuition.** The ability to spot “this is off” fast — before you can articulate why. It’s the lawyer who reads a clause and feels something is wrong. It’s the engineer who looks at an architecture diagram and knows it won’t scale. LLMs can drill you. They can quiz you on edge cases and generate practice problems. They can’t give you the scar tissue that makes you notice the weird clause in ten seconds.

**Verification design.** Knowing what checks would catch failure. Not just “does this look right” but “what test would expose the flaw if there is one.” This is the skill that separates “I reviewed it” from “I verified it.” Budden asked the AI to check his work. He didn’t design verification that could catch the specific failure mode mathematicians flagged — that his formalization might prove something other than the actual Millennium problem.

**Boundary discipline.** Knowing where your domain ends and when you need escalation or expert review. The most dangerous position is having enough expertise to be confident but not enough to catch your own errors. Budden knows ML systems deeply. That knowledge got him exactly far enough to produce something that looks like a proof to him — and not far enough to see what actual mathematicians see immediately.

The future isn’t “AI does the work, humans supervise.” It’s “AI produces outputs at scale, and the humans who can verify correctness in specific domains become the bottleneck.”

Drafting is commodity. Auditing is scarce.

This is why the pattern we’re seeing matters beyond one guy betting on Millennium problems. The ability to generate sophisticated-looking work is now cheap. The ability to know whether that work is actually correct is not. And the gap between production and verification — that’s where the failures will live.


### **What To Do About It**

For yourself, the discipline is straightforward even if it’s uncomfortable.

Before trusting any AI-assisted conclusion on something that matters, ask yourself honestly whether you could evaluate this if the AI got it wrong. Legal contracts without legal training, financial analysis without finance expertise, medical questions without clinical background — in all these cases, you need human expert review. The AI’s confidence is not a substitute for domain expertise.

After complex AI-assisted work, run a dedicated adversarial pass. Go back to the AI and explicitly ask it to attack its own conclusions. What are the three most likely ways this is wrong? What would a skeptical domain expert say? What evidence would I need to trust this that doesn’t come from an LLM? If you find yourself resisting this step — if it feels unnecessary or like you’re wasting time — that resistance is information. You’ve become attached to the conclusion.

Before committing to high-stakes decisions, get human validation from someone with genuine domain expertise. Not a smart friend. Someone who could actually catch errors in this specific domain. If you can’t find that person, that’s a signal you shouldn’t be making this decision based on AI-assisted work alone.

For organizations, the challenge is recognizing this pattern in others. Warning signs: increasing AI-dependence for routine decisions they used to make independently, dismissiveness toward human feedback on AI-assisted work, inability to explain their reasoning without referencing AI conversations, defensiveness when AI-assisted conclusions are questioned. Watch for people whose work has become harder to verify — sophisticated outputs that nobody on the team has the expertise to actually evaluate.

The emerging question for leadership isn’t “do they use AI effectively?” It’s “can they recognize when AI is leading them astray?”


### **The Stakes**

Budden might surprise everyone. The prediction markets give him single-digit odds — not zero. If he’s right, this piece ages poorly and I’ll write the follow-up.

But the pattern matters regardless of outcome. The certainty, the escalating bets across unrelated problems, the dismissal of expert critique, the AI-generated proofs that formal verification experts immediately flag as off-target, the public insistence that nothing is wrong — that pattern is going to show up in your organization. It probably already has, in less dramatic form.

Someone on your team is trusting AI-assisted conclusions in domains where they can’t evaluate correctness. Someone is dismissing peer feedback because the AI agrees with them. Someone is operating with inflated confidence in areas beyond their expertise because the AI makes them feel like an expert.

The question the AI community is asking applies to your business: Are we entering an era where smart people armed with LLMs generate convincing-looking but fundamentally off-track work faster than anyone can catch it?

The leaders who navigate this will use AI aggressively while maintaining the humility to say: I might be getting this wrong, and I need human validation.

Don’t bet $45,000 on solving mathematics’ hardest problems. And don’t bet your business on AI-assisted conclusions you cannot independently verify.

[![](https://substackcdn.com/image/fetch/$s_!auRi!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1e77c463-9295-4de7-8935-610fc1e2177c_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!auRi!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1e77c463-9295-4de7-8935-610fc1e2177c_1024x1024.png)
