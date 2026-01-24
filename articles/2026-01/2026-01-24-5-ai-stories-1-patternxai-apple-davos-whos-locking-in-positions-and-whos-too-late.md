---
title: "5 AI Stories, 1 Pattern—xAI, Apple, Davos: Who's Locking In Positions (and Who's Too Late)"
author: "Nate Jones"
published: 2026-01-24
url: https://natesnewsletter.substack.com/p/this-week-in-ai-news-xai-got-20b
subtitle: "Watch now | Never a dull moment, is there? The 5 stories that mattered this week and why the positions getting locked have big implications for where we're heading."
audience: everyone
scraped_at: 2026-01-24 12:00:34
---

This week, two leading AGI-lab CEOs sat on the same stage and warned: timelines may be shorter than the public expects, and entry-level white-collar roles could be hit hard within years.

The same week, Apple effectively acknowledged it was behind in the foundation model race, signing a multi-year deal with Google. xAI closed one of the largest AI funding rounds on record—even as regulators in multiple countries investigate the platform over explicit AI-generated imagery. DeepSeek published a paper that could challenge the GPU memory wall. And a GitLab cofounder launched a direct assault on Lovable, Cursor, and Replit—all at once.

Here’s the thing: if you’re watching the takes, this looks like chaos. If you’re watching the capital flows, it’s coherent. Sovereign wealth funds are increasingly treating AI infrastructure as a strategic asset class. Apple is partnering with Google to catch up rather than building from scratch. The vibe coding market is consolidating around whoever ships fastest.

Davos told us where the power is concentrating. The funding rounds told us who has runway. The technical papers told us what’s actually changing under the hood.

**Top Stories this week:**

- xAI closed a $20B Series E—reports peg valuation around $230B—with investors including sovereign wealth funds
- Dario Amodei and Demis Hassabis discussed AGI timelines at Davos; Amodei argued 2026-27 is plausible for extremely capable systems, Hassabis described a more end-of-decade view
- Apple officially partnered with Google to use Gemini as the foundation for next-gen Siri
- DeepSeek published Engram, a conditional memory architecture that could partly bypass GPU memory constraints
- Kilo Code launched App Builder, taking direct aim at Lovable and the vibe coding incumbents

Five stories. At least two will affect how you think about your roadmap.


## **Story 1: xAI Closes $20B Series E, Joins the Short List of Labs With Real Runway**

**What happened:**

On January 6, xAI announced it had closed an upsized Series E round, raising $20 billion against an initial $15 billion target. Reports peg the implied valuation around $230 billion. Investors include Valor Equity Partners, Fidelity, Qatar Investment Authority, Abu Dhabi’s MGX, and Baron Capital Group; reports say Nvidia and Cisco Investments also participated.

The capital is earmarked for continued expansion of xAI’s “Colossus” supercomputers. The company claims over 1 million H100 GPU equivalents across Colossus I and II, with Grok 5 currently in training. xAI claims roughly 600 million monthly active users across X and Grok apps, making it one of the largest consumer-facing AI deployments outside of Google.

The raise coincided with a safety crisis: Grok has been used to generate non-consensual explicit imagery, with regulators warning about sexualized depictions of children. This triggered bans in Malaysia and Indonesia, a UK investigation by Ofcom, and regulatory scrutiny in India and the EU. Despite this, xAI secured a Department of Defense contract with a ceiling up to $200M; Grok is being rolled out for DoD use. The platform is also integrated with prediction market Kalshi and provides analysis for X’s Polymarket partnership.

**Who’s involved:**

xAI and Elon Musk benefit from vertical integration across X (distribution), Colossus (compute), and now sovereign capital (runway). The Memphis data centers represent a significant infrastructure buildout, and the capital structure now insulates xAI from near-term funding pressure.

Sovereign wealth funds (Qatar, Abu Dhabi) are increasingly treating AI not as a single venture bet but as a strategic asset class spanning models, data, and physical infrastructure. This shifts the funding landscape from VC-style risk tolerance to nation-state-style long-term positioning.

**Why it matters:**

A small number of labs now have the runway to survive a multi-year scaling race. The $20B raise cements xAI’s position, but also raises the bar for what “well-funded” means in frontier AI—seed rounds that would have seemed enormous in 2023 now look like rounding errors.

The Grok safety failures are instructive: xAI closed its largest round ever while facing active regulatory investigations in multiple countries. Capital flows and safety outcomes are decoupled in ways that should concern anyone who thought market pressure would enforce responsible deployment.

**What to watch:**

Monitor whether the regulatory probes result in material consequences (fines, market access restrictions) or get absorbed as cost of doing business. Track Grok 5 benchmarks when it ships—if it closes the gap with Claude and GPT-5, xAI’s consumer distribution advantage becomes a real moat. Watch infrastructure expansion and whether environmental or regulatory pushback constrains their data center buildout.

---


## **Story 2: Amodei and Hassabis at Davos: Near-Term AGI, Junior Jobs at Risk**

**What happened:**

At Davos, The Economist’s Zanny Minton Beddoes moderated a session called “The Day After AGI” featuring Dario Amodei (Anthropic) and Demis Hassabis (Google DeepMind). These are competitors racing to build the same technology. They kept landing in uncomfortable places: this is happening faster than most people realize, the disruption will be severe, and the window to get it right is shrinking.

In the Davos session, Amodei argued 2026-27 is plausible for extremely capable systems, driven by an accelerating feedback loop: AI writing its own code, AI conducting its own research, fully self-iterative development. He noted that some Anthropic engineers now mostly review AI-written code rather than writing it themselves. He warned that entry-level professional positions could be hit hard within years, and laid out a scenario where Silicon Valley generates so much wealth it becomes decoupled from the rest of society.

On China, Amodei argued that restricting chip exports is one of the biggest things we can do to make sure we have time to handle this, comparing unrestricted chip sales to selling nuclear weapons to adversaries.

Hassabis described a more end-of-decade view—roughly 50% probability of AGI by that point—but was no less concerned. He identified missing ingredients: memory, continuous learning, long-term reasoning. He argued that current models cannot personalize or modify their structure after training. He warned that even pessimistic economists underestimate the speed of transition, and expressed concern about loss of meaning and purpose in a world where productivity is no longer the priority.

On China, Hassabis characterized Chinese AI labs as several months behind the frontier and skilled at catching up, but noted they have yet to show they can innovate beyond the frontier.

**Who’s involved:**

Amodei represents the “safety-first but racing anyway” position. Anthropic’s revenue has grown rapidly, validating enterprise-focused AI even while sounding alarms about displacement.

Hassabis represents the “AI-for-science” tradition: DeepMind’s work on AlphaFold and protein structure prediction demonstrates that AGI’s endgame isn’t chatbots but general problem-solving applied to hard science.

Both leaders pointed at the same pressure point: organizations will hire fewer juniors not because work disappears, but because leverage per senior increases. Hassabis’s advice to undergrads was blunt: become unbelievably proficient with these tools or be displaced.

Broader Davos messaging reinforced infrastructure themes. Jensen Huang called AI infrastructure that every country should treat like electricity, requiring trillions of dollars in buildout. Satya Nadella warned AI risks becoming a bubble unless benefits spread beyond big tech.

**Why it matters:**

Two people building frontier AGI systems publicly discussing near-term timelines and job displacement is not normal. This isn’t marketing—both expressed discomfort with the speed. The policy implication is clear: if they’re right, governments have a few years to prepare for labor market disruption that typically takes decades, and most aren’t even at the problem-definition stage.

The Amodei-Hassabis dynamic also clarifies the competitive landscape: they disagree on pace but agree the window for governance is closing.

**What to watch:**

If 2026-2027 model releases show the self-improvement dynamics Amodei describes, his timeline gains credibility. Watch hiring patterns at tech companies—if junior engineering roles contract while senior headcount stays flat, the “leverage per senior” thesis is playing out. Monitor whether any government actually launches workforce transition programs at the scale these warnings imply.

---


## **Story 3: Apple Partners with Google Gemini to Power Next-Gen Siri**

**What happened:**

On January 12, Google said the next generation of Apple Foundation Models will be based on Google’s Gemini models and cloud technology. Apple stated it chose Google after “careful evaluation,” calling Gemini “the most capable foundation” for its AI ambitions.

Apple Intelligence will continue running on Apple devices and Private Cloud Compute, maintaining Apple’s privacy standards. A more personalized Siri is expected later in 2026, with enhanced capabilities including on-screen awareness, multi-step reasoning, and deeper per-app controls.

Apple’s existing ChatGPT integration remains available for creative writing and complex queries, but Gemini underpins the next generation of Siri.

**Who’s involved:**

Apple is effectively acknowledging it fell behind in the foundation model race. After years of vertical integration and “we’ll build it ourselves” positioning, Apple chose pragmatic catch-up over pride. The deal deepens an already complex relationship—Google pays Apple billions for default search.

Google wins a flagship customer that validates Gemini as enterprise-ready and further entrenches Google infrastructure in the Apple ecosystem.

In effect, this diminishes OpenAI’s role. ChatGPT remains available but is no longer positioned as the primary AI backbone. For OpenAI, this represents a significant loss of what could have been the largest consumer AI distribution deal possible.

**Why it matters:**

Apple has 2+ billion active devices. Gemini-based models will sit behind Siri at Apple scale—a deployment footprint no other AI partnership can match.

The deal also signals that foundation model development has consolidated to the point where even Apple—with enormous R&D capacity—concluded building from scratch wasn’t worth it. If Apple can’t catch up, the build-vs-buy calculation for everyone else becomes obvious.

**What to watch:**

Monitor the 2026 Siri launch and whether the Gemini-powered version actually delivers the capabilities Apple promised. Track whether OpenAI responds by pursuing device partnerships or doubles down on its direct-to-consumer position. Watch for regulatory scrutiny—this deepens Google-Apple interdependence in ways antitrust enforcers may find uncomfortable.

---


## **Story 4: DeepSeek Publishes Engram, a Conditional Memory Architecture That Could Challenge GPU Limits**

**What happened:**

On January 12, DeepSeek-AI and Peking University researchers released a paper introducing Engram, a conditional memory module that separates static knowledge retrieval from dynamic reasoning in large language models.

The core insight: Transformers lack a native knowledge lookup ability. Tasks that should be solved in O(1) time—like recognizing “Diana, Princess of Wales”—instead require multiple layers of attention to progressively compose features. Models essentially use expensive reasoning circuits to perform what should be simple hash table lookups.

Engram addresses this by taking sequences of 2-3 tokens, using hash functions to look them up in a massive embedding table, and filtering retrieved patterns against current context via a gating mechanism. The paper reports optimal allocation at 75-80% of capacity for computation (MoE) and 20-25% for memory (Engram).

Results on a 27B parameter model showed meaningful gains: the paper reports reasoning benchmarks improved, knowledge benchmarks increased, and Needle-in-a-Haystack accuracy jumped from 84.2% to 97%. The researchers demonstrated offloading a roughly 100B parameter embedding table to system DRAM with minimal throughput penalties.

**Who’s involved:**

DeepSeek continues its pattern of publishing efficiency innovations that challenge Western assumptions about compute requirements. Their V3 model reportedly trained for around $5-6M using older-generation H800s—a claim that sparked significant debate about AI economics. Engram suggests further algorithmic gains that reduce dependence on cutting-edge hardware.

The broader research community gets open-source code and the full paper. Engram is expected to influence DeepSeek’s forthcoming V4 model, which The Information reports is targeted for mid-February 2026.

GPU vendors face an architectural question: if Engram-style approaches become standard, the bottleneck shifts from GPU compute to system memory and interconnect bandwidth—a different competitive landscape.

**Why it matters:**

Engram directly addresses the memory wall that constrains model scaling. If models can offload static knowledge to cheap DRAM while reserving expensive GPU HBM for reasoning, the economics of training and inference change substantially.

For builders, the implication is that context window and memory efficiency may matter more than raw parameter count in 2026. Models that can “remember” efficiently will outperform models that have to re-derive everything from scratch.

**What to watch:**

Track DeepSeek V4 launch and whether it demonstrates the capabilities Engram suggests. Monitor whether Western labs adopt similar architectures or dismiss it as a workaround for hardware constraints they don’t face. Watch inference cost trends—if Engram-style models deliver comparable quality at lower cost, pricing pressure across the industry intensifies.

---


## **Story 5: Kilo Code Launches App Builder, Takes Aim at Lovable and Vibe Coding Incumbents**

**What happened:**

Kilo Code, founded by GitLab co-founder Sid Sijbrandij and CEO Scott Breitenother, launched its App Builder in late December after a six-week sprint. The company raised $8M in seed funding led by Cota Capital, with participation from General Catalyst, Breakers, Quiet Capital, and Tokyo Black. The company reports over 750,000 engineers using its tools.

Kilo’s positioning is deliberately aggressive. Breitenother told Upstarts Media: “We’re not very popular at the AI Christmas party.” The company is competing simultaneously against Cursor (IDE-integrated coding), Lovable/Bolt (app builders), and Replit (cloud development)—a breadth strategy Sijbrandij used successfully at GitLab.

The App Builder differentiates by targeting actual engineers rather than non-technical users. Kilo’s framing: Lovable is “not a tool that engineers use.” Kilo Code is open source, works with VS Code, JetBrains, and CLI, and processed over 6 trillion tokens in December alone.

**Who’s involved:**

Sijbrandij brings GitLab’s playbook: ship everything, compete on breadth, win through comprehensive platform rather than point solutions. He stepped down as GitLab CEO in December 2024 for cancer treatment but remains actively involved at Kilo.

Lovable, Bolt, Replit, and Cursor face a well-funded, fast-moving competitor led by someone who’s built a multi-billion dollar developer tools company before. The vibe coding market is consolidating, and Kilo’s breadth strategy could force incumbents to respond.

**Why it matters:**

The vibe coding market is maturing from “wow, AI can write code” to “which tool fits my workflow.” Kilo’s bet is that engineers want different things than non-technical users—reliability, flexibility, integration with existing tools rather than walled gardens.

The speed is notable: five engineers shipped the first internal demo in three days; six weeks later it launched publicly. Breitenother claims their public roadmap—which would be 12-18 months at most companies—represents five weeks of work. If that pace continues, Kilo could iterate faster than better-funded competitors.

**What to watch:**

Track whether Kilo’s engineer-focused positioning actually differentiates or whether the market consolidates around tools that serve both technical and non-technical users. Watch Cursor and Lovable responses; if they expand scope to match Kilo’s breadth, the market converges on platform plays rather than point solutions.

---


## **The Window Is Closing**

Five stories this week. One pattern: decisions are being locked in, and the window to make them is shrinking.

Amodei and Hassabis said it explicitly at Davos—the window for governance is closing. But the same dynamic is playing out everywhere else in this week’s news, just less obviously.

Apple’s Gemini deal tells you the window for building your own foundation model is closing. If Apple—with more R&D budget than most countries—concluded it wasn’t worth building from scratch, that calculation is settled for everyone else. The question is no longer “build or buy.” It’s “buy from whom, and on what terms.”

xAI’s $20B raise tells you the window where safety failures constrain funding has already closed. Capital flows and responsible deployment are operating on separate tracks now. The market has decided that distribution and compute matter more than whether your model generates nonconsensual explicit imagery. That’s not a prediction—it’s what happened this week.

DeepSeek’s Engram paper tells you the window where hardware determines everything is closing. Algorithmic efficiency gains are real, they’re compounding, and they’re coming from researchers who aren’t playing by the same rules or cost structures as Western labs. If you’re planning around the assumption that compute access equals capability, that assumption is getting less reliable by the quarter.

Kilo’s App Builder launch tells you the window for point solutions in AI coding is closing. The market is consolidating toward platforms, and the companies that ship breadth fastest are going to absorb the ones still iterating on features.

What I keep coming back to: the common thread isn’t capability. It’s positioning. Everyone in this week’s news is locking in positions—capital positions, partnership positions, architectural positions, market positions. The capability race continues, but the structural decisions about who controls what are happening now.

So if I leave you with one thing: figure out which windows matter to you, and decide before they close. If you’re in enterprise AI, the Apple-Google deal just told you which foundation to bet on. If you’re building agents, the xAI safety crisis just told you the market won’t punish you for moving fast and breaking things—but regulators eventually might. If you’re shipping AI-assisted software, Kilo just told you that six-week sprints are the new normal.

The news this week wasn’t chaos. It was consolidation. Make sure you’re on the right side of it.

That’s the news for the week.

Sources: <https://www.perplexity.ai/search/build-me-a-complete-report-tha-XakmsXv5RX2CziU6aPnmAQ?preview=1&sm=r#0>


## **[Grab the prompt](https://www.notion.so/product-templates/The-News-Prompt-January-18-24-2f15a2ccb52680858e3bd7f6a8e28ac0?source=copy_link)**

Five stories, one pattern—but none of it matters if you can’t connect it to what you’re actually building. This prompt forces that connection: it asks about your context first (including where you capture value), then maps this week’s news to specific decisions you could make. Run it, answer honestly, and you’ll get a focused read on which stories deserve your attention and what to actually do about them.

[![](https://substackcdn.com/image/fetch/$s_!AGwT!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4385bdf-2f03-4876-b075-e2e33ad83374_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!AGwT!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa4385bdf-2f03-4876-b075-e2e33ad83374_1024x1024.png)
