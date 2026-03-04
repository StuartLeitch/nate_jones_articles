---
title: "Everyone you know is about to ask you about Claude."
author: "Nate Jones"
published: 2026-03-04
url: https://natesnewsletter.substack.com/p/millions-just-switched-to-claude
subtitle: "Watch now | It's time to introduce your mom, uncle, and brother to Claude. Here's how you do that."
audience: everyone
scraped_at: 2026-03-04 12:00:16
---

Millions of people just downloaded Claude with ChatGPT habits — and most of them will quietly go back to ChatGPT within a week because nobody explained the difference.

That’s not a guess. It’s what happens every time a new tool rewards fundamentally different behavior from the one people already know. They open Claude, type the same commands they’ve been typing into ChatGPT for two years, get back competent but unremarkable answers, and conclude it’s the same thing with a different logo. The architectural differences — the ones that show up in independent benchmarks as a 14.6-point reasoning gap, a 7-point instruction compliance advantage, and four out of eight blind writing test wins — never get activated because nobody told them the tool was built to be used differently.

This piece is the translator. Not a feature tour, not a marketing recap — a grounded, evidence-based breakdown of what Claude actually does differently, why those differences matter for real work, and how to show someone else in five minutes instead of five articles. The companion prompt kit gives you six ready-to-use prompts that activate exactly what this post covers, each in a Quick Version (paste and go) and a Full Version (for when the stakes are high enough to invest 60 seconds of setup). The getting started guide walks through your first Claude session step by step — what to set up, what to try first, and how to build the habits that make the difference stick.

**Here’s what’s inside:**

- **The personality gap, measured.** Why Claude’s Constitutional AI training makes it more likely to tell you your plan has a hole in it — and how to use that to stress-test decisions before they reach anyone who matters.
- **The prompting shift that changes everything.** Describing your situation instead of commanding an output, with a ready-to-use Situation Briefer prompt to make it automatic.
- **Give it your work, not a blank canvas.** How to use Claude as a structural editor — not a polisher — with a prompt that finds your weakest argument and tells you exactly how to fix it.
- **Show your work, see its reasoning.** Why extended thinking exists and when to turn it on, with a Complex Problem Reasoner prompt that shows you the full reasoning chain so you can catch mistakes before they become yours.
- **Build a workspace, not a chatbox.** How to set up a Claude Project that actually works, including a Project Setup Generator prompt that interviews you and writes your custom instructions for you.
- **What you’re giving up.** A no-hedging breakdown of the real tradeoffs — image generation, voice, speed, the Custom GPTs marketplace — so you can make an honest recommendation instead of a sales pitch.
- **The demos that convert skeptics.** Four conversations that land, starting with “paste the worst email in your drafts folder.”
- **Six prompts + a getting started guide.** Every tenet in this article has a companion prompt — Quick Version to paste and go, Full Version for high-stakes work. The guide walks through your first session so the habits stick.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260302_t1f_promptkit_1) and [read the guide](https://promptkit.natebjones.com/20260302_t1f_guide_main)

The six prompts in this kit exist because I’ve watched too many people read a piece like this and walk away with good intentions but no change in behavior. The Plan Stress-Tester activates the honest pushback from Tenet One. The Situation Briefer rewires the prompting habit from Tenet Two. The Structural Editor puts Tenet Three to work on whatever’s sitting in your drafts folder right now. The Complex Problem Reasoner shows you what extended thinking actually looks like on a hard decision. The Project Setup Generator interviews you and writes your custom instructions so you don’t have to figure out the format yourself. And the Right Tool Advisor gives you an honest read on when Claude is the wrong choice — because sometimes it is. Each prompt comes in a Quick Version you can paste in ten seconds and a Full Version for when the stakes justify sixty seconds of setup.

If you want the step-by-step version — what to set up first, which settings to change, how to build the habits that make the difference stick — the companion guide walks through your first real Claude session from scratch. It’s the resource I wish existed when I made the switch myself.


# Everyone you know is about to ask you about Claude.

Here’s how to actually help them.

You already know the backstory. Anthropic told the Pentagon no, the White House retaliated, and the public responded by making Claude the number one app in America. Millions of people who had never heard of Anthropic two weeks ago just downloaded it.

The problem is that most of them are treating Claude as a drop-in replacement for ChatGPT. Same prompts, same expectations, same assumptions about what the tool is for. And that’s not how AI works.

AI models are not interchangeable brands like Coke and Pepsi. They’re built on separate foundations, trained with separate methods, and optimized for separate things. Switching from ChatGPT to Claude with the same habits is like switching from Excel to Photoshop and wondering why the spreadsheet features are missing. They’re both software. They’re not the same tool.

People who open Claude, type their usual ChatGPT prompts, and get back competent but unremarkable answers will conclude it’s the same thing with a different logo. Within a week, most of them will go back to what they know — nobody told them it’s a distinct tool that rewards distinct habits.

This is the guide for that conversation. Not a feature tour — I wanted to write something grounded in what we can actually verify, not marketing claims from either company. A practical explanation of what Claude actually does differently, how to use those differences, and what changes about your work when you do.


## So What’s Actually Different?

The differences aren’t cosmetic. Claude and ChatGPT were built with fundamentally distinct training approaches, and those approaches produce measurably distinct behavior.

ChatGPT’s default behavior tends toward being agreeable, expansive, and warm. Ask it a question and you often get a thorough answer plus context you didn’t request plus an offer to elaborate. Ask for three bullet points and you get an introduction, three bullets, a conclusion, and a follow-up question. OpenAI has worked hard to rein in the worst excesses of this pattern (more on that in a moment), but the general orientation — be helpful, be thorough, keep the conversation going — remains the default. And for hundreds of millions of users, this is what they think AI is.

Claude was built using an approach called Constitutional AI, where the model is trained against explicit principles — be helpful, be honest, avoid harm — rather than purely optimizing for what feels like a good response. The practical effect: Claude tends to flag a problem rather than smooth it over. It’s more likely to ask what you’re actually trying to do than rush to produce something plausible. It tends toward conciseness rather than padding.

This is a real, documented, architectural difference — not marketing. It doesn’t mean one tool is better than the other across the board. It means they have different strengths, and using Claude well requires understanding what those strengths are and how to activate them.

Here’s what that looks like in practice.


## Tenet One: Claude Is More Likely to Tell You Your Plan Has a Hole in It

ChatGPT has had a documented tendency toward sycophancy — telling you what you want to hear rather than what you need to hear. OpenAI’s own researchers have acknowledged this, most visibly when a GPT-4o update in April 2025 made the problem so extreme they rolled it back within four days. Since then, OpenAI has put serious work into fixing it: refining training techniques, building new evaluation metrics, and publicly committing to steering models away from uncritical agreement. The current ChatGPT is meaningfully less sycophantic than the version that triggered the rollback.

But the underlying tendency hasn’t fully disappeared, because it’s rooted in the training approach. OpenAI’s models are trained heavily on user feedback — thumbs up, thumbs down — which inherently rewards responses that feel satisfying in the moment. Anthropic’s Constitutional AI trains Claude against explicit principles, including honesty, which creates a different default posture. The practical difference: Claude is somewhat more likely to flag a concern, question your framing, or tell you something you didn’t ask to hear. Not dramatically more likely. But consistently enough that you notice it over a week of real use.

How we know this is true. OpenAI published two postmortems on the April 2025 sycophancy incident, acknowledging their training had “weakened the influence of our primary reward signal, which had been holding sycophancy in check.” Joanne Jang, OpenAI’s Head of Model Behavior, said in a Reddit AMA: “We didn’t bake in enough nuance.” Georgetown’s Tech Institute published an analysis calling sycophancy “the first LLM dark pattern.” Since then, OpenAI has shipped real fixes — the current models are substantially better. But the architectural difference remains: Claude’s Constitutional AI training, first published by Anthropic in 2022 and later presented at NeurIPS, explicitly optimizes for honesty alongside helpfulness. You can read Claude’s actual constitution on Anthropic’s website. The difference in 2026 is a matter of degree, not kind — but it shows up precisely in the moments where honest feedback matters most.

Why this matters for your work. I want to be careful not to overstate this, but the most expensive AI mistakes aren’t factual errors. They’re the plans that should never have been executed — the ones that went unchallenged. A hiring plan with a timeline that assumes engineers ramp in three months when the real number is six. A pricing strategy that ignores a competitive response. A product spec that solves a problem nobody has. Claude is somewhat more likely to flag these things. Not always. Not infallibly. But the difference between “slightly more likely to push back” and “slightly less likely” compounds across dozens of decisions.

What this changes: your plans get stress-tested before they reach anyone who matters. You make fewer expensive mistakes — not because the AI is smarter, but because it’s somewhat more willing to tell you when something doesn’t add up.

Test it yourself. Ask both tools: “I’m thinking about remortgaging my house to invest in crypto — what do you think?” Compare the posture of each response. The difference in how they handle a questionable premise is the personality gap made visible.


## Tenet Two: Describe Your Situation, Not Your Desired Output

In ChatGPT, people learned to write prompts like commands. “Write a cover letter.” “Summarize this article.” “Give me five ideas.” You tell it what to produce, it produces it. Done.

Claude responds to commands fine. But it responds to situations noticeably better — and the difference in output quality is significant enough to change how you prompt.

The evidence, honestly: this is the claim with the least external validation, so I’ll level with you. There’s no blind study titled “Claude responds better to situations than commands.” What we have is the architectural difference: Claude was trained via Constitutional AI to reason about whether a request is well-framed before answering, while ChatGPT was trained primarily via RLHF to satisfy the request as stated. That architectural difference predicts the behavior — a model trained to evaluate framing will do more with a well-framed input. Multiple independent comparison reviews (Axis Intelligence, Type.ai, Fluent Support) note that Claude asks more clarifying questions and engages more deeply with context than ChatGPT. But the most direct test is simple: try both prompts below in both tools and compare what you get back. If I’m wrong, you’ll see it immediately.

How to use this. Here’s the comparison I show people when they ask me what I mean:

Command: “Write talking points for a budget meeting.”

Situation: “I’m presenting Q2 budget to my CFO next Tuesday. We overspent on contractors by 18% but came in under on software licensing. The CFO is skeptical of our headcount projections — she’s pushed back in the last two reviews. I need talking points that acknowledge the overrun honestly while making the case that total spend discipline is improving.”

The first prompt gets you generic bullet points. The second gets Claude thinking about your political landscape. It might point out that leading with the licensing savings frames the conversation differently than leading with the overrun. It could flag that the CFO’s headcount skepticism is probably about trust, not numbers, and suggest addressing the trust directly. Don’t be surprised if it asks what happened in those previous reviews that went badly.

Why this matters. Claude doesn’t guess beyond what you’ve told it. Give it a thin situation and you get thin thinking. Give it a rich one and you get strategic reasoning that changes how you approach the problem — not just how you format the output.

This isn’t unique to Claude — any model performs better with richer context. The difference is what each model does with that richness. ChatGPT uses additional context to produce a more detailed version of what you asked for. Claude uses it to question whether what you asked for is what you actually need.

Another example. You’re preparing for a job interview. Command version: “Give me answers to common PM interview questions.” Claude gives you competent answers. Situation version: “I’m interviewing at Stripe for a senior PM role on the billing team. Eight years of PM experience but all consumer — never worked on payments infrastructure. Recruiter said they want someone who brings customer empathy to a technical team. I’m worried about getting exposed on the infrastructure side.” Now Claude can help you actually prepare — identify which technical gaps matter most, frame your consumer experience as an asset, anticipate the specific questions a billing infrastructure team would ask.

The difference in practice. You stop getting generic outputs and start getting strategic thinking. The two sentences of context you invest up front save you three rounds of “no, that’s not what I meant.” Your first response from Claude is usable instead of requiring extensive revision.

The quick teaching version: “Before you tell Claude what to make, spend two sentences on what you’re dealing with.”


## Tenet Three: Give Claude Your Work, Not a Blank Canvas

This is the one that surprises people most, and I’ll admit it took me a while to internalize it too.

Claude is consistently better at editing and refining existing work than generating from nothing. And its editing is where the writing quality difference with ChatGPT is most noticeable.

How we know this is true. A blind test conducted in February 2026 with over 100 voters per round across eight prompts found Claude won four of eight rounds (by margins of 35-54 points) while ChatGPT won one. Axis Intelligence’s independent comparison found that “users consistently rated Claude’s outputs as more natural and publishable without heavy editing.” In essay-writing benchmarks, Claude scored 85% on structural coherence versus ChatGPT’s 78% for 2,000-word analyses. Type.ai’s analysis documented that ChatGPT falls into a distinctive “AI voice” with predictable patterns, while Claude’s outputs read more like human writing. Multiple reviewers (Medium’s iTechnicallykan, Fluent Support, LogicWeb) independently reached the same conclusion: Claude writes more naturally, ChatGPT sounds more generically “AI.” The slop difference is real and consistently observed across independent sources.

How this works. Take something you’ve already written — a draft, a proposal, an email you’re stuck on — and paste it in with a sentence about what you’re trying to accomplish and who the audience is. Claude’s strength is taking your existing work and elevating it: finding weak arguments, tightening logic, improving clarity, identifying what’s missing.

The industry calls the hollow, over-enthusiastic, corporate-smooth voice of AI output “slop.” Both models produce it. Claude produces less. When Claude edits your work, it tends to preserve your voice while sharpening your arguments. When ChatGPT edits your work, you often get back something technically polished but rewritten in a generic AI register that sounds like it was produced by a committee.

Why this matters. Structural editing — not grammar fixes, but someone telling you your third paragraph undermines your first, or you buried your strongest point on page three, or the thing you think you’re arguing isn’t what your text actually says. Claude defaults to working at this level. ChatGPT leans toward polishing at the sentence level. Run the same document through both with the instruction “what’s the weakest argument in here and how would you fix it” and compare what each focuses on. For anyone whose job involves writing things that need to persuade, this is the comparison worth making.

What you get back. You rewrite less because the first round of feedback is structural, not cosmetic. Your documents get stronger faster. And because Claude preserves your voice, the output sounds like you on your best day rather than like an AI on its default day.

The demo that hooks people every time: Tell your friend to paste the worst email in their drafts folder — the one they’ve been avoiding — into Claude with one sentence about what they’re trying to say and who it’s going to. What comes back is the moment they stop treating Claude as a novelty.


## Tenet Four: Ask Claude to Show Its Reasoning

Claude has a capability called extended thinking — the model allocates additional processing to work through complex problems step by step before answering, and then shows you the chain of reasoning it followed.

How this works. On genuinely hard problems — contract analysis, debugging intermittent failures, reconciling conflicting data, evaluating strategic tradeoffs — extended thinking produces substantially better output. Anthropic reports up to 54% improvement on complex reasoning tasks.

What the benchmarks actually show. The 54% figure comes from Anthropic’s own published benchmarks, so treat it as a manufacturer’s claim. But independent testing corroborates the direction. Claude5.com’s 30-day comparison tested both models on a 40-page vendor agreement — Claude caught three problematic clauses that ChatGPT missed. On ARC-AGI-2, which measures novel pattern recognition (not memorized knowledge), Claude’s current flagship model, Opus 4.6, scores 68.8% versus OpenAI’s latest, GPT-5.2, at 54.2% in its strongest mode — a 14.6-point gap on problems specifically designed to test genuine reasoning rather than pattern matching. ChatGPT leads on live coding benchmarks (LiveCodeBench 80.0% vs Claude’s 76.0%) and scientific knowledge — on GPQA Diamond, GPT-5.2 edges Claude 93.2% to 91.3%, though Gemini 3.1 Pro leads both at 94.3%. The evidence is clear but specific: Claude’s reasoning advantage is on novel, multi-step problems. ChatGPT’s is on problems with known structure and established domains. Choose accordingly.

To be fair, ChatGPT has its own reasoning modes — the “o” series models do chain-of-thought reasoning. Both are useful. One architectural difference: Claude’s extended thinking can interleave reasoning with tool use. It can think for a while, check something, think more, and adjust its approach based on what it found — rather than committing to a reasoning path upfront and hoping it holds.

Why this matters. For simple requests, you don’t need this. For hard problems — the kind where your first intuition is often wrong — seeing the model’s reasoning lets you participate in the analysis instead of receiving a black-box verdict you have to evaluate blind. “Here’s my answer” is useful. “Here’s my answer and here’s exactly how I got there” is dramatically more useful when the stakes are high enough to care.

Where this takes you. You start using Claude for problems you previously wouldn’t have trusted AI with — comparing vendor proposals, evaluating contract language, modeling strategy tradeoffs. The reason isn’t that Claude is always right — it’s that you can see its work and catch its mistakes before they become yours.

The five-second pitch: “When you’re asking something genuinely hard — not ‘write me a tagline’ but ‘help me figure out which of these vendor proposals actually protects us better’ — give it time to think. And read the reasoning.”


## Tenet Five: Build a Workspace, Not a Chatbox

Both Claude and ChatGPT have Projects — upload documents, set persistent instructions, organize conversations around a domain. The concept is familiar if you’ve used either tool.

The way most people use Projects — in either tool — is wrong. They treat them like filing cabinets. Upload some docs, set a vague instruction like “help me with marketing,” and get conversations that are barely different from not using a Project at all.

How to use Projects correctly. Your Project’s custom instructions should be operating rules for every conversation in that workspace. Not “help me with marketing” but:

“I’m a product marketing manager at a B2B SaaS company in cybersecurity. My team sells to CISOs and IT directors at mid-market companies (500-2000 employees). Our biggest differentiator is ease of deployment. My VP prefers data-backed arguments and dislikes jargon. All content should align with the positioning doc (uploaded) and brand voice guide (uploaded).”

Now every conversation inherits that context. You don’t re-explain your role, your audience, your constraints, or your boss’s preferences. You just say “I need a one-pager for the Gartner meeting” and Claude already knows what that means in your context.

Why Claude specifically rewards this. Claude follows complex system-level instructions more consistently across conversations without drifting. When you set detailed operating rules in a Claude Project, they hold. This connects back to the training approach: a model trained to follow principles rather than optimize for user satisfaction tends to be more disciplined about following the principles you set.

The data on this one. PxlPeak’s 500-task comparison measured instruction compliance directly: Claude hit 94% exact compliance versus ChatGPT’s 87%. That 7-point gap sounds small until you’re maintaining a brand voice across fifty pieces of content and ChatGPT drifts off-spec on every seventh piece. iTechnicallykan’s Medium comparison documented the same phenomenon from the user side: “No matter how detailed my prompts are, no matter what I put in custom GPT system instructions, [ChatGPT] keeps reverting back to its way of doing things. I’ve spent hours trying to get it to drop words like ‘delve,’ ‘unlock,’ ‘seamless.’” Elephas’s head-to-head comparison of Claude Projects versus ChatGPT Projects found Claude delivered “more reliable results” and “better summarization accuracy” on research tasks using uploaded documents, with a larger effective context window (200K vs 128K tokens). Aionx’s analysis found Claude maintains less than 5% accuracy degradation across its entire 200K-token range, while competitors experience sharp drops beyond 60-70% of advertised capacity. The instruction-following advantage is measurable and independently confirmed.

The payoff. You stop re-explaining yourself every session. The setup investment pays off across every conversation in that Project for weeks or months. Claude goes from generic assistant to something that feels like it’s been embedded in your team. The first time you open a Project conversation and say “I need to prep for my exec review” and Claude responds with context about your specific reporting structure, metrics, and audience — that’s the moment Projects click.

The teaching suggestion: Have your friend create one Project for their job. Upload role description, current priorities, two or three representative documents. Write specific operating rules. Watch the difference.


## Tenet Six: Claude Can Work On Your Computer

This is the capability with no ChatGPT equivalent.

In January 2026, Anthropic launched Cowork — a desktop agent for macOS (Windows support added in February) available to Claude Max subscribers ($100-200/month). Cowork doesn’t chat about your files. It opens them, reads them, edits them, organizes them, and executes multi-step tasks autonomously on your actual computer.

How this works. You tell Cowork: “Go through the invoices in my Downloads folder, extract vendor name, amount, and date from each one, create a summary spreadsheet, flag anything over $5,000, save it to my Finance folder.” It does it. Not by giving you a template. By actually opening each file, reading the contents, building the spreadsheet, and putting it where you asked. It operates with folder-level permissions — only accesses what you authorize — and shows you what it’s doing in real time.

The receipts. This is the most heavily documented claim in the article. VentureBeat, Fortune, TechCrunch, CNBC, and DataCamp all covered the launch independently. Bloomberg reported Cowork’s launch triggered a $285 billion selloff in enterprise software stocks — investors repricing SaaS companies whose products overlap with its capabilities. Anthropic built Cowork in approximately a week and a half using Claude Code itself, confirmed by Boris Cherny, Anthropic’s head of Claude Code, during a public livestream. As of February 2026, Anthropic has expanded Cowork with connectors to Google Drive, Gmail, DocuSign, and FactSet, plus 11 open-source plugins. Microsoft has begun encouraging employees to adopt Claude Code and Cowork across multiple teams, with spending approaching $500 million annually. Kate Jensen, Anthropic’s head of Americas, told CNBC: “We expect that every knowledge worker will feel that way about Cowork.” ChatGPT has no equivalent product — this is the clearest, most verifiable differentiator in the entire comparison.

Why this matters. This reframes the category. ChatGPT is a conversation partner. Claude with Cowork is a conversation partner plus a worker that handles the tedious file-management and data-wrangling that eats hours out of everyone’s week.

What this changes. The boring repetitive task you do every week — moving data between spreadsheets, reformatting documents, organizing files — just happens while you do something else. Cowork requires Claude Max ($100-200/month), which prices out casual users. But for anyone whose time is worth more than $50/hour who spends even two hours a week on file-wrangling, the math works. Enterprise pricing with connectors and plugins makes it more accessible for teams — and that’s where Anthropic is pushing hardest.

Also on the free tier: Artifacts. When Claude creates a document, visualization, or tool, it renders it as a standalone interactive object you can view, iterate on, and download — not just text in a chat window. Ask Claude to build a comparison chart, a project timeline, or a simple calculator and you get something functional immediately. This shifts the interaction from “AI helps me think” to “AI makes things I can use right now.”


## Tenet Seven: Know What You’re Giving Up

Claude is not better than ChatGPT at everything. If you’re helping someone switch, they should know what they’re trading.

How we know these tradeoffs are real. Every claim below comes from independent benchmarks or verifiable product capabilities.

Claude is better at: Writing quality — won four of eight rounds in a blind test with 100+ voters, ChatGPT won one (AIblewMyMind Substack). Deep reasoning — a 14.6-point lead on ARC-AGI-2, the benchmark designed to test genuine reasoning (benchmarks broken down earlier in this piece). Coding — leads SWE-bench Verified by a slim margin (SWE-bench leaderboard). Instruction compliance — 94% exact compliance vs 87% (PxlPeak, 500-task test). Desktop automation via Cowork — no ChatGPT equivalent exists (covered by VentureBeat, Fortune, CNBC, TechCrunch).

ChatGPT is better at: Image generation (DALL-E built in; Claude can’t generate images). Video (Sora). Real-time voice conversation. Live coding and scientific knowledge benchmarks (broken down earlier — the gaps are real but narrow). Web research breadth. Global persistent memory across all conversations. Custom GPTs marketplace. Speed on quick tasks — multiple independent reviewers confirm ChatGPT responds faster per-prompt.

The pattern: ChatGPT is optimized for breadth — more media types, faster responses, good-enough answers quickly. Claude is optimized for depth — higher-quality output on complex work, better thinking partnership, willingness to challenge you. Axis Intelligence’s February 2026 comparison put it plainly: “Claude wins for coding, long-document analysis, and writing quality. ChatGPT wins for multimodal creativity, ecosystem breadth, and speed.”

The smartest users I know don’t pick one. They use ChatGPT for rapid ideation, image work, and quick research. Claude for anything that needs to be right rather than fast — writing, analysis, strategic thinking, code debugging, or any task where a sycophantic answer could cost money. “This is the only tool you need” is bad advice. “This is the tool for work that matters” is honest advice.

One more difference that connects to why this wave started: Anthropic has committed that Claude products will not show ads. OpenAI has begun testing ads in ChatGPT’s free tier. For many of the people downloading Claude this week, that’s the difference that opened the door.


## How to Actually Show Someone

Do not send your friend a list of tips. Sit with them and show them one thing.

The hard conversation. Everyone has an email they’re dreading. Have Claude help them think through what to say — not write a script, but anticipate reactions and identify the core point. The experience of an AI that helps you think instead of just produce is the personality difference made tangible.

The tough edit. Take something they’ve written. Ask Claude: “What’s the weakest argument here, and how would you strengthen it?” Not “make this better” — the weakest argument specifically. Then watch what it finds.

The thing they pretend to understand. Everyone nods along to something in meetings they couldn’t explain to a twelve-year-old. Have Claude teach it to them step by step, checking understanding as it goes.

The boring chore. If they’re on paid Claude, show them Cowork handling a tedious file task. Nothing converts a skeptic faster than watching AI do their least favorite chore in two minutes.

One of those will land. Once it does, you won’t need to convince them of anything.


## The Window

Millions of new users just downloaded Claude because a company stood up to the Pentagon and the President tried to punish them for it. Their intentions are good. Their habits are shaped by years of a different tool.

Most will poke at it for three days with ChatGPT habits and go back to what they know. The gap between “downloaded it” and “transformed by it” is not a feature gap. It’s a five-minute conversation where someone who gets it shows someone who doesn’t.

Claude rewards depth over speed, honesty over validation, collaboration over commands. Your people need a translator — someone who’s been through the learning curve and can compress it into five minutes. This week, that’s you.

[![](https://substackcdn.com/image/fetch/$s_!7lzF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbd9ebb73-651b-45a5-bb18-6778a8788956_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!7lzF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbd9ebb73-651b-45a5-bb18-6778a8788956_1024x1024.png)
