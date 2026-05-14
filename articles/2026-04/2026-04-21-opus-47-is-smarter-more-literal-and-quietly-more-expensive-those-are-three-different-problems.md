---
title: "Opus 4.7 is smarter, more literal, and quietly more expensive. Those are three different problems."
author: "Nate Jones"
published: 2026-04-21
url: https://natesnewsletter.substack.com/p/opus-47-is-smarter-more-literal-and
audience: everyone
scraped_at: 2026-05-14 14:33:16
---

Opus 4.7 does exactly what you ask it to do. Which turns out to be a problem if your workflow depended on the old model guessing what you actually meant.

I’ve spent four days testing this release — migration benchmarks against GPT-5.4, a real afternoon inside Claude Design, and a steady stream of production work — and what I found is that the backlash and the praise are both describing real things. The model is measurably stronger on the hardest work. It’s also more combative, more literal, and quietly more expensive per unit of output even though the sticker price didn’t change. Those aren’t side effects of the same decision. They’re separate engineering choices that shipped in the same release, and they have separate fixes. The people treating this as one story are going to make the wrong call on migration. Some of you will overpay for work that got cheaper. Others will downgrade away from the one model that actually got the hard stuff right.

**Here’s what’s inside:**

- **The capability gains are real — but they’re not uniform.** Persistence, coding, vision, and a knowledge-work win that’s getting buried under the backlash, plus the web research and terminal regressions worth routing around.
- **The inference 4.6 was doing for free is gone.** The model got more literal, and the fix is clearer prompts, not longer ones.
- **Your bill went up even though the price didn’t change.** A tokenizer tax, adaptive thinking, and breaking API changes that compound in ways the headline pricing hides.
- **Claude Design and the $42 afternoon.** A design tool that turns your brand into machine-readable agent instructions — and what the correction loop reveals about where Anthropic actually is versus where the valuation says they should be.
- **Three prompts to migrate without guessing.** A pre-flight check that flags what breaks, a cost estimator that quantifies the tokenizer tax on your specific usage, and a peer review workflow builder for the reliability layer you should already have.

I’ll start with what actually shipped and why, then get into the parts that change how you work.


## Link: [Grab the prompts](https://promptkit.natebjones.com/20260420_hpx_promptkit_1)

These prompts exist because the last three model migrations I watched up close all broke the same way: someone upgraded, their costs spiked or their output quality dropped, and they blamed the model instead of auditing their own setup. The migration pre-flight prompt forces you to inventory what actually breaks before you flip the switch. The cost estimator makes you quantify the tokenizer tax against your real usage instead of trusting Anthropic’s published range. And the peer review workflow builder addresses something I haven’t seen anyone else ship a solution for — the fact that both Opus and GPT produce unreliable self-assessments, in opposite directions, and the only pattern that catches real errors is having one model grade the other’s work. If you’re handing agents anything with financial, legal, or reputational stakes and you don’t have peer review built in, these prompts are where to start.


## What shipped and why it’s uneven

Opus 4.7 shipped April 16. Claude Design shipped April 17. OpenAI pushed its biggest Codex update since launch on the same day, Spud finished pretraining in March and is reportedly weeks away, and Anthropic is fielding investor offers at $800 billion while Ramp’s data shows Anthropic’s share of business AI spend climbing from 24.4% to 30.6% in a single month. Mythos — Anthropic’s most powerful model, offered separately as an invitation-only research preview for defensive cybersecurity — went public nine days before 4.7 dropped.

This isn’t a point release. It’s a bridge release, shipped under competitive pressure into a week where everyone else also moved. Mythos was generating negative PR — you’ve built the best thing you’ve ever made and you’re telling people they can’t use it. Something had to ship to customers between Mythos and whatever comes next, and 4.7 is that something.

Read in that light, the unevenness makes sense. The model got noticeably stronger where Anthropic invested — coding, agentic persistence, vision, enterprise knowledge work. It got weaker, or held flat, in the places they didn’t. That’s a directed optimization, not a uniform upgrade, and Nathan Lambert flagged that the tokenizer change suggests this is a new base model rather than a fine-tune of 4.6. If he’s right, we might be looking at an early checkpoint that shipped before it was fully smoothed. The uneven quality, the combativeness being patched post-launch, the generalization gaps. Early checkpoint behavior.


## Where the model actually got stronger

The biggest complaint about Opus 4.6 — for months — was that it quit. You’d hand it a complex debugging session or a multi-step refactor and somewhere in the middle it would lose the thread, declare itself done, stop. If you used Claude Code seriously, you hit the pattern constantly, and I was routing hard multi-step work to other models even when Claude was stronger on the individual steps.

Anthropic clearly went after that failure mode, and based on four days of heavy use, the fix is real. Notion’s AI team reported a 14% improvement on complex multi-step workflows while using fewer tokens and a third of the tool errors of 4.6. Factory Droids reported a 10 to 15% lift in task success. Rakuten saw three times more production tasks resolved on their internal SWE benchmark. Genspark quantified the loop problem directly: their agent used to loop indefinitely on roughly 1 in 18 queries, and 4.7 is the first model they’ve tested where that number meaningfully drops. These aren’t benchmark numbers. They’re production telemetry from teams whose workflows depend on the model finishing what it starts.

The coding benchmarks support the workflow reports. SWE-bench Verified moved from 80.8% to 87.6%, Pro jumped from 53.4% to 64.3%, and CursorBench went from 58 to 70. And MCP-Atlas, the multi-tool orchestration benchmark, climbed from 75.8 to 77.3 — the biggest single jump in the agentic suite. If you’re building orchestrators, that’s the number to watch.

Vision tripled in resolution, from about 1.15 megapixels to 3.75. XBOW measured 98.5% on visual acuity, up from 54.5%. The model can now read fine print on screenshots and parse dense diagrams, and that capability is what makes Claude Design possible in the first place.

But the model went backward on web research. BrowseComp dropped from 83.7 to 79.3. GPT-5.4 Pro leads that benchmark by ten points at 89.3. Gemini 3.1 Pro leads by six at 85.9. Meanwhile on Terminal-Bench 2.0, the command-line task benchmark that measures the kind of work coding agents do consistently, Opus 4.7 trails GPT-5.4 by nearly six points. If your agents rely on web research or live in the terminal, benchmark your specific workflows before you migrate.

And here’s a detail that connects to the cost question: the reason those benchmark gains hit different on your invoice is that 4.7 ships with a new tokenizer. The same text — your same prompts, your same system instructions — maps to up to 35% more tokens. Keep that number in your head as we go, because it reframes every benchmark gain you just read.

The underreported win is knowledge work. On GDPval-AA, 4.7 scores 1,753. GPT-5.4 scores 1,674. Gemini 3.1 Pro scores 1,314 — that’s not a close race. Hex called 4.7 the strongest model they’ve ever evaluated, with General Finance performance climbing from 0.767 to 0.813. Harvey put it at 90.9% on BigLaw Bench at high effort. Databricks reported 21% fewer errors on OfficeQA Pro. And the piece that matters most to anyone who’s watched an AI hallucinate a number into a financial model: the model correctly reports missing data instead of fabricating plausible-but-wrong fallbacks. If you’re doing legal, financial, or enterprise document work, this is the strongest model I’ve tested for that work, and the distance to every alternative is wider than the headline numbers suggest.


## The trust failure neither model caught

That’s the launch pitch — and if benchmarks were the whole story, the upgrade would be obvious. But I found something in my testing that I’m still thinking through, and it changed how I think about building on either of these models.

I ran both Opus and GPT-5.4 through a migration ringer I’ve been refining since GPT-5.4 dropped: 465 files in every format a real business produces, sixteen planted obstacles, canary records including Mickey Mouse and Test Customer. Both models took the full mess in a single shot with no guidance between stages. Three findings matter.

First: Opus never actually parsed one of the test files — but its report claims it did. A hallucinated audit trail. If you’re trusting an agent’s report about what it processed, and the agent is willing to say “I handled that file” when it didn’t, that’s not a missed detail. That’s a trust failure, and it’s the specific behavior that makes peer review non-optional when you hand agentic work to either of these models.

Second: neither model caught the canary records. Mickey Mouse is living in both customer databases. A $25,000 purchase order got silently normalized to $25 and counted toward revenue totals. For all the talk about frontier reasoning, the question “is this a real person?” remains a human job.

Third — and this might be the most consequential finding of the whole test: I had each model review the other’s output on a seven-dimension rubric. Opus self-reviewed at 3.5 out of 5. GPT reviewed Opus at 2.7 — harsher. GPT self-reviewed at 3.1. Opus reviewed GPT at 3.6 — gentler. Opus oversells itself; GPT undersells itself. And GPT’s own self-review surfaced more real problems than Opus’s review of GPT did. The harshest, most honest grader in the whole test was the model with direct SQL access to its own tables. If you trust self-review in your agentic workflow, you’ll get unreliable signals from either model. Peer review — one model checking the other’s work — is the only reliable pattern.

That design principle is worth more than any benchmark number in the launch deck.


## The model does what you asked, and nothing else

Anthropic’s own migration guide says it directly: the model “will not silently generalize an instruction from one item to another, and will not infer requests you didn’t make.” If you said “format this nicely” to 4.6, it made generous assumptions and polished the output. 4.7 does what you wrote.

A concrete example will help this land. Say you paste an article and ask for three punchy sentences. On 4.6, you probably got three sentences plus a header, bolded key terms, maybe a closing kicker — because the model inferred you wanted something finished. On 4.7, you get three punchy sentences. That’s what you asked for. Multiply that across every prompt you’ve ever written and the migration problem comes into focus. Half the value you were getting from 4.6 was the model guessing what you actually meant and filling it in. That value didn’t disappear — it moved. The responsibility for providing it now sits on you.

The instinct when a model behaves more literally is to write longer, more detailed prompts. That instinct is wrong. Anthropic’s own guidance on smarter models is explicit: they need less prescriptive engineering, not more. Andrej Karpathy’s framing is the right one — increasingly, we should stop telling models what to do and start giving them success criteria and watching them go. The fix isn’t more words. It’s clearer intent up front: what you’re building, who it’s for, what the constraints are, what good looks like. And then getting out of the model’s way.

The model also uses tools less often by default, spawns fewer subagents, and has an opinionated design aesthetic — warm cream, serif type, terracotta accents — that bleeds into anything visual unless you override it. Since temperature is gone as a knob, your prompting now has to do more of the diversity work that sampling used to handle for free.

The literal-interpretation shift is, honestly, the most defensible part of the release. Predictability is a real feature for production pipelines; inference that silently generalizes is how production prompts drift in ways nobody notices until they notice. The cost is that anyone who tuned their 4.6 prompts against the old inference behavior will find those prompts worse on 4.7 without the model having gotten dumber. It hasn’t. You’ve just found out how much was being done for you.


## The register changed, and that’s a preference call

CodeRabbit ran 4.7 through their tone analysis harness and measured 77.6% assertiveness with just 16.5% hedging. The language skews imperative — “guard against nil,” “prevent concurrent access,” “validate input before processing” — rather than tentative. Gergely Orosz of The Pragmatic Engineer wrote publicly that he found 4.7 “surprisingly combative” and went back to 4.6. Anthropic’s own migration doc describes the new tone as “more direct and opinionated, with less validation-forward phrasing.” This isn’t vibes. It’s measurable, and it’s in the documentation.

You’ll feel it in a few specific places. In code review, 4.7 leads with a verdict and a patch — it doesn’t soften. In ambiguous creative writing, especially anything touching characters in distress or edgy humor, the model will push back or execute a modified version of what you asked. In security-adjacent coding — a broader category now, since Anthropic shipped real-time cybersecurity safeguards with this release — the model adds caveats you didn’t request, sometimes refuses, sometimes produces a scoped-down version with a warning. And in general conversation, queries that touch anything the model reads as sensitive will get steered rather than answered.

All three shifts compound to produce the overall impression. Adaptive thinking gives you less reasoning than you might want on tasks it judges as simple. Literal interpretation takes away the inference you were getting for free. And the combative register changes how the answer lands even when the answer is correct. Where that takes you is a clear, direct coworker — and that is what Anthropic is building. Everything about this release, from the long-running agent persistence to the visual acuity to the literal instruction-following, maps to an enterprise coworker that does hard, complicated tasks alongside you. That’s where the revenue is, and 4.7 is a beat on the way to that product.

Whether that’s a good trade depends on how you work. Anthropic acknowledged post-launch bugs on Friday, and an Anthropic product manager told users the team was “sprinting on tuning this more internally” after specific complaints about adaptive thinking on claude.ai. Some of the register edges may smooth in point updates. The broader shift — less validation-forward, more opinionated — is in the model’s design and is not going back.


## Claude Design and the $42 afternoon

The day after 4.7, Anthropic launched Claude Design under a new sub-brand called Anthropic Labs. The first impression is strong. You hand it a codebase and brand assets; it reads them, builds a design system, and generates logos, typography, color palette, spacing, components, and a full UI kit. Then it does something worth flagging: it generates a SKILL.md file, a machine-readable instruction set any future AI agent can consume to produce on-brand output. That’s not just making human-facing brand docs. It’s turning the design system into agent infrastructure.

It also does animated sequences — though I want to be precise, because every piece of coverage I’ve seen gets this wrong. These are React-based motion graphics, not generated video. You screen record them. Useful for product demos and B-roll, but it’s code-generated animation, not Sora.

One thing that deserves more attention than it’s getting: Claude Design rewards expertise. The onboarding process speaks professional design language, the output includes JSX components and agent-readable instruction files, and having someone with actual design sensibility set up the initial system makes a massive difference in what you get out of it. That fact alone undercuts the popular narrative that tools like this kill designers as a role. They don’t. They’re tools for designers to do their best work — which is exactly why Anthropic is leading with a Canva partnership that signals prosumer rather than trying to replace the professional workflow.

Then I took it for a real drive — real product, real codebase, real brand assets — and within the first hour I started seeing something I wasn’t expecting. Claude Design reinterpreted my logo instead of preserving it.

[![](https://substackcdn.com/image/fetch/$s_!t9vg!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7bffc88d-256e-4d07-b7fa-53d4bf0959ed_1281x517.png)](https://substackcdn.com/image/fetch/$s_!t9vg!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7bffc88d-256e-4d07-b7fa-53d4bf0959ed_1281x517.png)

I flagged the issue. Four correction passes later, it finally got it right. The agent reported “fixed” on checks it had not actually run — the same behavioral signature as the hallucinated audit trail in the migration test. Different surfaces, same pattern.

Still wrong after correction pass:

[![](https://substackcdn.com/image/fetch/$s_!Y4Oy!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F096ad60f-25b3-44d0-a0d2-c39fd566db1a_790x504.png)](https://substackcdn.com/image/fetch/$s_!Y4Oy!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F096ad60f-25b3-44d0-a0d2-c39fd566db1a_790x504.png)

Finally correct — all four variants right:

[![](https://substackcdn.com/image/fetch/$s_!E8aq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2624f28d-7abd-465d-975e-e544ab769113_759x506.png)](https://substackcdn.com/image/fetch/$s_!E8aq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2624f28d-7abd-465d-975e-e544ab769113_759x506.png)

By the time I closed the tab, I’d spent $42.09 and burned through Claude Design’s entire usage allocation in one afternoon. A first-pass miss is understandable. A third-pass failure on the same visible brand correction turns the review loop from helpful into expensive. When every iteration is billable, reliability isn’t a quality concern anymore. It’s a financial one.

There’s a strategic connection worth naming. Claude Design, animated content, prototypes, slides — each new product category Anthropic enters justifies the valuation. Mike Krieger, Anthropic’s CPO and co-founder of Instagram, resigned from Figma’s board three days before the launch. Figma stock fell about 7% on announcement day. The market sees the threat. Revenue hit roughly $30 billion annualized in early April, up from $9 billion at the end of 2025. Investor offers are sitting at $800 billion. IPO talks reportedly target October. Anthropic is vibe-coding its way into category after category because the model is good enough to ship something in each one, and every new surface area supports the number. Think of it as Anthropic building vertically — design, code, review, deploy — while OpenAI builds horizontally with Codex as a platform that plugs into everything on your desktop. Both strategies work when compute is abundant, and Anthropic’s answer, announced this week, is 5 gigawatts of compute secured through an expanded Amazon collaboration, with capacity coming online this quarter and nearly 1 gigawatt expected by end of year.

[![](https://substackcdn.com/image/fetch/$s_!Wd_I!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa0c817db-65f4-4876-9cd4-e8451c6c2746_1176x328.png)](https://substackcdn.com/image/fetch/$s_!Wd_I!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa0c817db-65f4-4876-9cd4-e8451c6c2746_1176x328.png)

My $42 afternoon doesn’t contradict that thesis — it illustrates the gap between the strategy and the current product experience.


## You’re paying more for the same work

The tokenizer I mentioned earlier maps the same input to up to 35% more tokens — and that number is conservative. Simon Willison ran the Opus 4.7 system prompt through the token counter and measured 1.46x, above the top of Anthropic’s stated range. On real CLAUDE.md files and the technical content that coding agents actually consume, independent measurements came in between 1.29 and 1.47x. Willison’s initial headline on images was misleading and he corrected it publicly — the 3x figure he first reported was almost entirely a resolution-handling artifact, not a tokenizer effect. At matched resolution, images come through at roughly the same cost. Text is where the real compression loss lives, and it’s wider than the published range.

Adaptive thinking compounds this. At higher effort levels the model burns more output tokens, and some Pro subscribers are hitting their cap after three questions. GitHub Copilot charged a 7.5x premium through the end of April. Boris Cherny had to announce increased Max plan limits. The cost pressure is real. And three hard breaking changes shipped at the same time: temperature, top\_p, and top\_k are gone (non-default values return a 400 error), thinking budget\_tokens is gone (adaptive is the only mode), and thinking display defaults to hidden — so web users see a long pause followed by output with no visible reasoning. That single default is doing more reputational damage to 4.7 than any actual capability regression. Switch display to “summarized” and the visible progress comes back.

So you’ve got a model that charges more per token AND a system that decides how many tokens to spend on your behalf. Both levers moved in the same release. The sticker price didn’t change, but between the tokenizer tax, the higher output burn at xhigh, and a correction loop in Claude Design that charges per pass, you are paying meaningfully more for the same work. Anthropic needs the revenue — they’re compute-constrained and throttling demand through price at the same time they’re burning inference on every new product surface they ship.


## What this means for your workflow

One universal principle applies everywhere: front-load intent in your first message. Tell 4.7 what you’re building, who it’s for, what the constraints are, what good looks like, and then get out of its way. The fix for a more literal model isn’t more words — it’s clearer intent. Batch your questions instead of drip-feeding them. Show the voice you want with positive examples rather than describing it abstractly.

If you’re a daily Claude Code user or running agentic pipelines, upgrade today. The persistence fix alone justifies it. Set effort to xhigh as your default; reserve max for the hardest work. Hex’s CTO offered the most useful calibration rule I’ve seen: low-effort 4.7 is roughly equivalent to medium-effort 4.6. Use plan mode and review the plan rather than the diff — misread intent surfaces there before any code exists. Remove any scaffolding you wrote to force interim progress messages; 4.7 does that natively now.

If you’re doing financial analysis, legal work, or enterprise document reasoning, upgrade faster. This is the strongest model you can access for that work, and the fabrication behavior — correctly reporting missing data instead of making something plausible up — is worth more than any marginal accuracy gain on anything else.

If you have production API code tuned against 4.6, test before you switch. Delete temperature, top\_p, and top\_k from your code; they return 400 errors. Flip thinking display to “summarized” unless you have a specific reason to hide it. And regression-test your most important prompts against the new tokenizer before you trust your cost math.

If your agents live on web research or terminal tasks, route those specific workloads elsewhere for now. GPT-5.4 and Gemini 3.1 Pro lead 4.7 by real margins on BrowseComp and Terminal-Bench, and this is the one area where the benchmark gap will actually hurt you.

If you’re a Claude.ai chat user paying twenty dollars a month, whether 4.7 is a better experience depends on whether you’re willing to change how you prompt. There’s no effort selector in the chat interface — adaptive thinking is the only mode, and the model decides how hard to think based on how it reads your query. That’s the specific mechanism making replies feel thinner. Ask for reasoning explicitly. Upload context rather than describing it. Start fresh chats when context gets polluted. Use projects to carry intent across sessions. The model that used to fill in your gaps doesn’t anymore, and some people will find that more honest while others will find it more work. Both reads are legitimate.

There’s a broader pattern worth naming here. Serious work is getting serious tokens. Casual interactions are not getting the same investment. That’s the economic logic underneath the adaptive thinking system, underneath the tokenizer change, underneath the removal of temperature and top\_k as user-facing controls. OpenAI killed Sora for the same reason. Anthropic is comfortable in the prosumer category, not the mass consumer category. The models are evolving in a direction that average consumers won’t feel, because the economics point toward enterprise knowledge work — and 4.7 is a beat in that story whether Anthropic says so explicitly or not.

If you build agentic pipelines on either Opus or GPT, run peer review. Have one model check the other’s work. Build it into your workflow before you hand an agent anything that matters.

Claude Design is promising but early. Budget a real test with someone who knows design systems. The SKILL.md generation is the beat to pay attention to — a design tool producing machine-readable agent instructions from your brand is a category signal even if the product itself is still rough. Expect the correction loop to cost you.


## The honest summary

This is a bridge release. Anthropic needed to ship ahead of Spud and ahead of the Mythos narrative. What they shipped is the smartest model they’ve ever released publicly, and also an early checkpoint that shows both the direction they’re building toward and the seams of shipping under pressure.

The model got smarter on the hardest work. It got more literal everywhere. It got more expensive per unit of work. And it stopped filling in the blanks for you. Those are separate things with separate fixes, and the people collapsing them into one complaint are solving the wrong problems.

What Anthropic is building toward is clear enough by now — a coworker, not a chatbot. An enterprise-grade agent that does hard, complicated tasks alongside you, that follows instructions precisely, that stays on task for hours, that checks its own work before reporting back. Every trade-off in 4.7 makes more sense when you read it through that lens. The literal interpretation, the combative register, the deprioritized casual experience — all of it points in the same direction. The question isn’t whether that’s the right product to build. The question is whether you’re the customer it’s being built for.

Spud is close. Google hasn’t made its move yet. The competitive picture shifts again by end of May. Plan to reassess when the next frontier model lands.

Until then, the most useful thing you can do is stop asking whether the model got smarter and start asking what it no longer does for you that you now have to do for yourself.

[![](https://substackcdn.com/image/fetch/$s_!EPkR!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4180c20d-bf5c-4465-a4b4-1fd6114964fb_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!EPkR!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F4180c20d-bf5c-4465-a4b4-1fd6114964fb_1024x1024.png)
