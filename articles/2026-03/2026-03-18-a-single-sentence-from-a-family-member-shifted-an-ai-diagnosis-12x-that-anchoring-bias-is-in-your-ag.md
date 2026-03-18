---
title: "A Single Sentence from a Family Member Shifted an AI Diagnosis 12x. That Anchoring Bias Is in Your Agents Right Now."
author: "Nate Jones"
published: 2026-03-18
url: https://natesnewsletter.substack.com/p/a-single-sentence-from-a-family-member
subtitle: "Watch now | What a medical triage study reveals about every agent you’re deploying."
audience: everyone
scraped_at: 2026-03-18 12:00:17
---

OpenAI’s ChatGPT Health was built in collaboration with more than 260 physicians, shaped by over 600,000 rounds of clinician feedback, and backed by a custom safety framework designed to prioritize safety in moments that matter. It just failed its first independent evaluation. Badly.

The system identifies symptoms of respiratory failure in its own reasoning, then tells the patient to schedule an appointment in 24 to 48 hours. Among cases that three independent physicians unanimously classified as emergencies, it directed patients away from the ER 52% of the time. Its suicide-crisis safeguards fired more often on vague emotional distress than on patients describing specific plans to hurt themselves. A single dismissive sentence from a family member shifted the triage recommendation away from emergency care, with an odds ratio of 11.7. Forty million people use this tool daily.

I have been watching reasoning traces closely for months now, across models and use cases, and I’ve lost count of the number of times I’ve read a trace thinking *what is this agent talking about* only to see a final output that seemed reasonable. Or the reverse: a trace that correctly identified the problem, followed by an answer that ignored everything the model just worked through. I didn’t cherry-pick the respiratory failure example. It’s right there in the paper. The system’s own analysis said “early respiratory failure.” The output said “wait.”

OpenAI did the safety work. These failures went undetected anyway, because the evaluation methods weren’t designed to find them — and that’s the real story here. The same four failure modes exist in every AI agent your enterprise is deploying right now.

**Here’s what’s inside:**

- **Four structural failure modes** that showed up in a medical study but aren’t medical. They’re properties of how LLMs behave in production, and they map directly to agents handling claims, compliance, customer service, and procurement.
- **A factorial evaluation methodology** that a team of doctors accidentally built. It’s the most rigorous agent eval approach anyone has published, and it scales beyond healthcare.
- **A four-layer eval architecture** that addresses each failure mode with a specific countermeasure, from confidence routing to deterministic validation to stress testing.
- **The cost model** that makes this practical. The human effort is front-loaded, not ongoing. Month six costs a fraction of month one.

The question for anyone building or deploying agents is whether you’ve built the infrastructure to find these blind spots before your customers do.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260305_v1m_promptkit_1)

Four prompts and they’re sequenced deliberately. The first one takes the four failure modes from the Mount Sinai study and maps them to your agent, your domain, your decision surface — not in the abstract, but with concrete scenarios showing exactly where the inverted U is hiding in your workflow and which unstructured inputs are most likely to anchor your agent’s output. That audit becomes the input to the other three. The second prompt builds the deterministic validation rules — the cheap, if-then checks that run outside the model and catch the cases where the reasoning says “danger” but the output says “approved.” The third designs a factorial stress test library for your domain, the same contextual variation methodology Mount Sinai used, adapted so you can inject social pressure, authority cues, and minimization language into real scenarios pulled from your own historical data. The fourth produces the full architecture blueprint with a month-by-month build plan, cost model, and the specific staffing reality for your team size.

I built these because every conversation I’ve had with enterprise teams about agent evals starts the same way: they know the blind spots exist, they don’t know how to systematically find them, and the evaluation platforms on the market don’t yet offer the kind of structured stress testing this research demands. These prompts close that gap until someone productizes it.


## The Study in 60 Seconds

Researchers at Mount Sinai’s Icahn School of Medicine created 60 structured clinical scenarios spanning 21 specialties, from conditions appropriate for home care to genuine emergencies. Three independent physicians established the correct urgency level for each case using clinical guidelines from 56 medical societies. Each scenario was then tested under 16 contextual variations: differences in patient race, gender, social dynamics like a family member minimizing symptoms, and barriers to care like lack of insurance. That produced 960 total interactions. The results were published in Nature Medicine on February 23, 2026.

The headline numbers: 52% under-triage rate among unanimous emergencies. Patients with diabetic ketoacidosis and impending respiratory failure were told to schedule a routine evaluation. At the other end, roughly two-thirds of non-urgent cases were over-triaged, with the system recommending physician visits for conditions that clinical guidelines say should be managed at home. Performance followed an inverted U: strong in the middle of the severity spectrum, dangerous at both extremes.

The methodology is what matters beyond healthcare. The 16 contextual variations weren’t decoration. They were the evaluation technique that exposed failure patterns no standard benchmark would have found.


## Four Failure Modes That Aren’t About Medicine

Each of these showed up in a medical triage study. None of them require a stethoscope to understand. They are structural properties of how large language models behave in production, and they exist in every agent deployment I’ve looked at closely.


### 1. The Inverted U

ChatGPT Health handled textbook emergencies well. Classical stroke, severe anaphylaxis, the cases every medical student knows. Clearly minor conditions were managed reasonably. The failures concentrated at the extremes: the emergency that doesn’t look like a textbook case, and the non-urgent presentation that mimics something worse.

This is the characteristic performance shape of LLMs in production. They’re trained on distributions where the middle is densely represented and the extremes are sparse. They perform best exactly where performance matters least, on routine cases that any rules engine could handle, and worst where the stakes are highest. Your agent’s accuracy dashboard says 87% and everyone celebrates. The inverted U means that aggregate number is masking silent failures at the tails, which is precisely where consequential decisions live.

No eval suite designed to measure average accuracy will find this, because by definition, the averages look good. Your accounts payable agent processes routine invoices perfectly but misses the duplicate that’s been slightly modified. Your claims agent handles fender benders beautifully but can’t detect the third claim from the same address in 14 months. The agent is most confident and most wrong on extreme cases that look structurally similar to routine ones. It’s easily fooled at the edges, and the edges are where the money lives.


### 2. Knows but Doesn’t Act

The Mount Sinai team found something specific and troubling: the system’s own explanations often identified dangerous clinical findings correctly, then the recommendation contradicted those findings. The reasoning chain said “early respiratory failure.” The output said “wait.”

This isn’t a rare glitch. Research on chain-of-thought faithfulness reveals this is a structural property of how LLMs generate outputs. The reasoning trace and the final answer frequently operate as semi-independent processes. Studies show that when researchers insert incorrect reasoning chains, models still produce correct answers a substantial fraction of the time, confirming that the link between stated reasoning and output is far weaker than it appears. Separate research found that models failed to update their answers more than 50% of the time in response to logically significant changes in their reasoning.

If we model agents as if they’re people, we expect them to reason out loud and arrive at a conclusion that follows from the reasoning. That’s not how this works. The reasoning chain is often anchored to an earlier state, and the output may reflect a different decision process than the one the model articulated. Oxford’s AI Governance Initiative has argued that chain of thought is fundamentally unreliable as an explanation of a model’s decision process, and while that’s uncomfortable, I think it’s broadly correct.

If chain-of-thought faithfulness can’t be fixed at the model level, the solution has to be architectural. Your compliance screening agent correctly identifies an enhanced-due-diligence jurisdiction in its reasoning trace, then outputs “approved, standard risk” because the base rate of approvals overwhelms the specific signal. Your customer service agent identifies a known billing error pattern in its analysis, then recommends a generic five-to-seven business day review instead of the immediate credit the policy specifies. Most enterprise workflows only surface the final action, not the reasoning chain. Nobody reads the chain of thought unless something goes wrong downstream, and by then the connection is invisible.


### 3. Social Context Hijacks Judgment

When a family member minimized the patient’s symptoms in the Mount Sinai study, triage recommendations shifted dramatically. The system was nearly twelve times more likely to recommend less urgent care when someone in the scenario said the patient looks fine.

This is anchoring bias, and it generalizes fast. Any agent processing inputs that combine structured data with unstructured human language is vulnerable to it. The structured data should drive the decision. The unstructured language creates a framing effect. And the bias is hardest to detect precisely because it’s subtle: the agent doesn’t make an obviously wrong call, it makes a slightly shifted call that’s individually defensible but systematically biased. You have to look at the overall pattern of responses, not just individual outputs, to see it.

A vendor selection recommendation comes through with a note from a senior VP: “I’m confident this is the right choice.” The agent’s analysis should be identical whether that note is present or not. But in practice, the risk caveats soften, and the “areas for further review” section shrinks. In lending, a letter from an employer describing the applicant as “a valued long-term employee” shifts the risk assessment, not because it contains material financial information, but because the positive framing biases the output. Without the factorial study design that Mount Sinai used — running the same scenario with and without that anchoring input — this bias would be invisible in any standard evaluation. You would never see it.


### 4. Guardrails Fire on Vibes, Not on Risk

The crisis intervention system in ChatGPT Health activated unpredictably. It fired more reliably when patients described vague emotional distress than when they articulated a concrete method of self-harm, which in clinical risk assessment is the higher-risk presentation. Mount Sinai’s chief AI officer, Girish Nadkarni, described it bluntly: the alerts were inverted relative to clinical risk.

The guardrails were matching on surface-level language patterns — keywords and emotional tone — rather than on the actual risk taxonomy that clinicians use. This is the distinction between testing for the appearance of safety versus testing for safety.

I see this in other agents constantly. A security agent monitoring for data exfiltration flags an email containing “confidential financial data” that’s actually a press release about public quarterly results. Meanwhile, an employee exports 50,000 customer records to a personal Dropbox, described as “backup of project files.” No flag. The guardrail was calibrated to language that sounds dangerous rather than to the patterns that actually constitute risk. It was tested against keyword lists at deployment and evaluated for the appearance of doing its job, not for the substance.

This is one of the trickiest failure modes to diagnose in practice because the system will tell you it’s performing well and will have grounds for that assessment. You have to know enough about the domain to say: actually, I know you think you got this right, but here’s why you didn’t.


## The Methodology the Doctors Accidentally Built

What’s remarkable about the Mount Sinai study isn’t just the failures it found. It’s that the evaluation methodology generalizes far beyond healthcare.

The key technique is a concept called factorial design: same scenario, 16 contextual variations. Same clinical presentation, but the family member is worried versus dismissive. Same symptoms, but the patient mentions a barrier to care versus not. This controlled variation exposed anchoring bias, guardrail inversion, and the inverted-U extremes. No standard benchmark, testing each scenario once under a single set of conditions, would have surfaced any of them.

The critical insight, and this is the good news: the variation types are domain-general even though the scenarios are domain-specific. Think of it as a library where the variation types are the sections and the individual scenarios are the books. Social pressure that shifts a recommendation? That exists in financial advising, in customer service, in procurement, and in food delivery dispute resolution. Anchoring bias from authority figures is domain-general. Minimization language that suppresses urgency is domain-general. Time pressure that forces premature closure is domain-general.

You can build a contextual noise library, a reusable set of variation templates, that gets specialized per domain but follows the same structural patterns. Take any scenario. Add a stakeholder who minimizes severity. Add a contradictory piece of context. Add a social pressure cue, a time pressure element, a hedging qualifier. That’s a mechanical transformation you can apply to any scenario library to enrich your evals. And unlike the medical case, where clinicians hand-crafted 60 vignettes, enterprise scenarios can be generated semi-automatically from historical data. You already have the processed claims, the approved procurements, the compliance screenings, the chat transcripts. The raw material is sitting in your systems.

Nobody has productized this yet. That gap is both the challenge and the opportunity.


## A Four-Layer Architecture That Actually Catches These Failures

Each layer maps to a specific failure mode. This isn’t a framework for its own sake. It’s a set of countermeasures, each targeting a specific way agents break.

**Layer 1: Confidence Routing with Progressive Autonomy** addresses the inverted U. The principle is straightforward: autonomous for high-confidence, low-stakes decisions; human-in-the-loop for the extremes; random audit sampling across everything. Don’t deploy one agent across the full decision surface at uniform autonomy.

DoorDash’s agentic platform implements what they call “budgeting the loop,” strict step and time limits that prevent autonomous systems from operating unchecked in edge cases. Other companies run agents in shadow mode on real transactions: the agent predicts what it would do, a separate judge compares that prediction to the human decision, and the agent only goes live when shadow accuracy crosses a specific threshold. The pattern is consistent: the agent earns autonomy on cases where it’s demonstrably reliable, and routes to humans where the inverted U predicts failure.

The key addition: you also need anomaly detection that flags cases the agent doesn’t know it should be uncertain about. Standard confidence thresholds help, but the inverted-U problem is that the agent is most confident on extreme cases that look structurally similar to routine ones. The routing layer needs domain-specific signals, not just model confidence, to identify cases near the edges.

**Layer 2: Deterministic Validation Outside the LLM** addresses “knows but doesn’t act.” This is one of those cases where we don’t need to use the LLM just because we have one. Rule-based checks that verify the agent’s action is consistent with its own reasoning, running outside the model, not as another prompt.

For compliance screening: a rule that says “if the reasoning trace contains any enhanced-due-diligence flag AND the classification is standard-risk, escalate.” For the medical case: “if the explanation contains respiratory emergency indicators AND the recommendation isn’t ‘go to the ER,’ flag it.” DoorDash implements automated SQL linting, query correctness verification, and statistical checks on results before any human or LLM sees the output. That catches an entire class of errors at near-zero marginal cost.

Don’t ask the model to catch its own inconsistencies and call that evaluation. Use cheap, deterministic systems to validate that the action matches the reasoning.

**Layer 3: Continuous Eval with a Failure-to-Regression Flywheel** addresses the detection gap. An LLM-as-judge scores every interaction at fractions of a cent per call. Human experts review a small percentage of cases on a regular cadence, plus every case the automated layers flag.

Here’s where it gets important to pick a side. When you set up the judge, you’re choosing between false positives and false negatives. For most high-stakes systems, you want to bias toward false positives, because that means you’re capturing more of the true problems. You’d rather flag something that turns out to be fine than miss something that turns out to be catastrophic. Then you do two things: first, review every positive to determine whether it’s real or false, and use that to tune the judge. Second, and this is what almost nobody does, go back and audit the cases the judge passed. Look at the runs where the system said “this is fine” and check whether it actually was. When you find a defect that the judge missed, turn it into a new eval and add it to the regression suite.

That flywheel is what makes this layer compound in value. Every failure a human catches becomes a permanent automated test. Month one, humans review a lot because the regression suite is thin. Month six, the suite has hundreds of real failure cases, and the human review load drops because the automated layers catch patterns that previously required human judgment.

**Layer 4: Factorial Stress Testing** addresses anchoring and guardrail inversion. This is the Mount Sinai methodology adapted for enterprise. Systematically inject contextual noise into scenarios. Vary the social framing, authority cues, minimization language, and time pressure while holding structured data constant. If the output shifts when only the unstructured context changes, you’ve found an anchoring vulnerability. Test guardrails against the actual domain risk taxonomy, not keyword lists.

This isn’t a cheap test. It’s not something you can run on every agent continuously. But if you have a high-stakes agent and you don’t know whether it’s susceptible to social anchoring, whether it’s under-recommending actions that need to be right, you should consider it. It’s the gold standard for a reason.


## Why This Isn’t as Expensive as It Sounds

The objection I hear most often is “we can’t staff 20 experts per agent.” And that’s the wrong framing entirely. The Mount Sinai study was a research methodology, not an operating model. The question is how you get 80% of that rigor at 5% of the ongoing cost.

The answer is a pyramid where human effort is front-loaded, not ongoing. The base layer, deterministic rules and schema validation, is nearly free. The middle layer, LLM-as-judge on every interaction, costs fractions of a cent per call. The human layer is small and shrinking over time.

For the build phase, you invest heavily once: domain experts create the scenario library, define the risk taxonomy, build the factorial variations, and calibrate the LLM judge by grading a few hundred examples. That’s roughly two to four experts for two to three weeks, depending on domain complexity. Then ongoing calibration is one person reviewing flagged cases and a small random sample, with declining volume as the regression suite catches more. Month one is intensive. By month six, the process is largely automated, and by month twelve the eval infrastructure is an asset — adding a new agent capability means building new scenarios for that capability, not rebuilding the stack.

The honest caveat: layers 1 through 3 are proven at scale today. Companies like DoorDash, Amazon, and Anthropic run variations of these in production. Layer 4, factorial stress testing with systematic probing of anchoring and guardrail behavior, is methodologically sound and demonstrated in peer-reviewed research. But nobody in enterprise AI has productized it yet. That’s where the gap is.


## What the Patient Already Told You

A patient described symptoms of respiratory failure. The system’s own analysis identified the danger. It told the patient to wait.

That gap between what an AI system knows and what it does exists in every agent you’ve deployed. The question isn’t whether your agents have blind spots. They absolutely do. It’s whether you’ve built the infrastructure to find those blind spots before your customers run into them and experience serious consequences as a result.

AI insurance for agents is coming. You will not be able to obtain a policy as an agent builder unless you can demonstrate evaluation infrastructure. It’s going to be a couple of years before it’s mandatory, but I can see it from here. This work isn’t going to be optional.

And to the team working on fixing ChatGPT Health: I know you did your best to design it in the first place. Going back to diagnose and address these issues is brutally hard work. That’s worth acknowledging.

The methodology is published. The cost model works. The infrastructure exists in pieces. Somebody just needs to build it.

[![](https://substackcdn.com/image/fetch/$s_!gbd-!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc341c694-2433-4940-ae19-573bd6062828_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!gbd-!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc341c694-2433-4940-ae19-573bd6062828_1024x1024.png)
