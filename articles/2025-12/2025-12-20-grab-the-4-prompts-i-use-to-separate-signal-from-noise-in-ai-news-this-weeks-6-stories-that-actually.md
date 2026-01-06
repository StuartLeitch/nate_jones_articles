---
title: "Grab the 4 prompts I use to separate signal from noise in AI news + this week's 6 stories that actually matter"
author: "Nate Jones"
published: 2025-12-20
url: https://natesnewsletter.substack.com/p/grab-the-4-prompts-i-use-to-separate
subtitle: "Watch now | This week: China hits an EUV milestone, the market admits implementation matters, and robots start learning from watching humans, plus! 4 prompts you can use on the news to separate sig..."
audience: everyone
scraped_at: 2026-01-05 19:09:41
---

I read more than 20 hours of AI news this week. Most of it was noise. But six stories cut through—and they share a pattern worth understanding.

I think one of them is the most significant story of the year—potentially worth trillions. And it wasn’t from any of the big model-makers.

The pattern is this: the gap between AI announcements and AI reality is finally becoming impossible to ignore. China claims a breakthrough on EUV lithography, but it’s light without mirrors—impressive engineering, but not chips. Meanwhile, CEOs tell Reuters they’re frustrated with AI deployments, but BCG data shows only 5% of companies are achieving real value. Also this week: Amazon reorganizes its entire AI org after years of watching Alexa become a punchline. And what we almost missed: A robotics startup discovers their models can learn from human videos—emergently, without anyone teaching them to.

Each of these stories rewards a different kind of attention. Some require zooming out to decade-long timelines. Others demand zooming in on who said what and why. The prompts I’ve included help you do both.

**Here’s what’s inside:**

- **China’s EUV Manhattan Project** — what the prototype actually achieved, why Zeiss lenses are the real chokepoint, and what to watch for next
- **The market admits implementation matters** — Forrester’s 15% profitability number, BCG’s 5% stat, and why vendor marketing is about to shift
- **Exa’s People Search launch** — how “find a person” is becoming an API primitive like “charge a card”
- **Meta ships SAM Audio** — why Zuck cares about audio separation and what it signals about the creative stack
- **Amazon’s AI leadership reshuffle** — the infrastructure-first pivot and what DeSantis’s appointment actually means
- **Physical Intelligence’s emergent transfer** — why robots learning from human video is one of the biggest stories of the year

Plus four prompts for processing news like a builder, not a spectator. Why four? Because this week we have to look at the news from multiple perspectives, and I want you to have the tools to do that.

- The Geopolitical Development Evaluator: a prompt specifically designed for evaluating the geopolitical implications of AI news
- The Vendor Claim and Market Report Reality Check: a prompt designed for one of the biggest stories of the week—vendor hype leading to buyers’ regret
- The Technical Breakthrough Assessment: a prompt to help you evaluate the impact of big technical breakthroughs for your business
- The AI News Weekly Synthesis: an evergreen prompt you can use with this week’s articles OR any other news article you want to dig into further
- Plus a Perplexity news report across 179 sources if you want to dive in more!

Lots of interesting longterm signal in the news this week, and I want to make sure you have the prompt tools you need to stay current. Read on for the news, the prompts, and my vote on why one of these stories is the story of the year!


## **[Grab the Prompts](https://www.notion.so/product-templates/4-News-Prompts-December-20-2025-2ce5a2ccb526802b854de2e838b302cb?source=copy_link)**

Most AI news is written to generate clicks, not to help you make decisions. China headlines are calibrated for maximum alarm. Vendor stats are funded by the vendors. Technical announcements are timed for fundraising.

The four prompts linked are my BS filters. I use them to stress-test geopolitical claims before assuming the sky is falling, to interrogate the methodology behind every "X% of companies" statistic, to figure out if a research result will matter in 12 months or just sounds impressive today, and to turn a chaotic week of headlines into a coherent picture of what's actually shifting.

Grab them. Run this week's stories through them. You'll be surprised how much noise falls away.

Now let’s get into it.


## **China’s “Manhattan Project” to Reverse-Engineer ASML and Break the Western Chip Chokehold**

**What happened:**

Reuters exposed China’s six-year, government-coordinated effort to build domestic EUV lithography machines—the $250M tools essential for advanced AI chips that ASML currently monopolizes. Key facts:

- Launched 2019 under Xi’s Central Science and Technology Commission; Huawei coordinates, CEO Ren Zhengfei briefs senior leadership personally
- Early 2025: prototype completed in high-security Shenzhen lab—larger than ASML’s 180-ton machines to boost power output
- Prototype generates EUV light but hasn’t produced functional chips; precision optics (typically from Carl Zeiss) remain a hurdle
- Target: working chips by 2028, though 2030 more realistic—still faster than Western estimates of a decade

IP theft is central: China recruits retired Chinese-born ASML engineers with 3-5M yuan bonuses ($420K-$700K) plus housing. Lin Nan, former ASML light source department head, filed eight EUV patents at a Chinese Academy of Sciences institute within 18 months of joining. ASML won an $845M judgment in 2019 against a former engineer for trade secrets theft; he continued operating in Beijing with government backing.

Political fallout: Republican lawmakers introduced legislation barring CHIPS Act recipients from purchasing Chinese-linked equipment for ten years after reports Intel tested tools from ACM Research (which has sanctioned China-linked subsidiaries). The State Department launched Pax Silica on December 12—a coalition with South Korea, Japan, Australia, Singapore, UK, Israel, and UAE to secure AI infrastructure supply chains and counter China’s 85-90% control of rare earth processing.

**Who’s involved:**

- **Chinese government/Huawei:** Coordinating via state resources, talent poaching, reverse-engineering
- **ASML/Western equipment makers:** Facing systematic IP theft; their lithography monopoly is the foundation of Western chip dominance
- **U.S. government/Pax Silica allies:** Responding via export controls, coalition-building, political pressure on domestic chipmakers
- **Foundries and cloud providers:** Watching whether China can field competitive EUV capacity that reshapes GPU availability and pricing

**Why it matters:**

If China fields EUV-class tools at production scale, Western export controls become a temporary speed bump, not a hard blockade. The prototype shows China’s approach—state coordination, talent acquisition, reverse-engineering—is progressing faster than Western intelligence estimates.

Hardware geopolitics now has two competing arms: Western alliances like Pax Silica securing minerals, lithography tools, and packaging vs. China’s parallel domestic stack racing to replicate all of them.

For builders: GPU availability and pricing over the next decade will depend as much on whether China achieves EUV independence as on NVIDIA’s roadmap. The chokepoint in AI is hardware manufacturing capability, not software or algorithms.

**What to watch:**

- Signs of pilot production: foundry partnerships with SMIC, volume announcements, performance benchmarks
- Pax Silica implementation: tightened export regimes on precision optics and rare materials
- Whether Republican legislation barring CHIPS Act recipients from Chinese-linked equipment passes

---


## **“You Can’t Just Plug These Guys In”—The Market Finally Admits AI Needs Implementation, Not Just Inference**

**What happened:**

Reuters published interviews with CEOs and board members capturing mounting consensus: AI will reshape business, but most deployments disappoint without heavy customization, integration, and workflow redesign. The data is stark:

- **Forrester Q2 2025** (1,576 executives): Only 15% reported improved profit margins from AI; analyst predicts 25% of planned 2026 AI spending will be delayed
- **BCG survey** (1,250 executives, May-July 2025): Just 5% achieving widespread value from AI
- **OpenAI’s enterprise report** claims mature deployments save 40-60 minutes/day—highlighting the gap between integrated systems and ad-hoc adoption

Real-world examples:

- **CellarTracker** (wine app): Spent six weeks tweaking prompts to get their AI sommelier to offer honest feedback instead of being overly polite
- **Cando Rail**: Spent ~$300K on an AI chatbot for safety reports; shelved it after models consistently forgot, misinterpreted, or invented rules
- **Klarna**: Walked back 2024 claims that AI replaced 700 agents. CEO acknowledged cost-cutting led to “lower quality”; now rehiring humans while AI handles ~850 agents’ worth of routine tasks

On X, @pingthebird captured builder frustration: “it cost more for Claude to do my dishes after 18 hours in agent mode than to hire a fucking maid”—136K views illustrating the gap between agent hype and cost-efficiency when systems aren’t designed properly.

**Who’s involved:**

- **Corporate leaders/boards:** Convinced AI is strategic but skeptical of quick wins without deep implementation
- **AI platform providers:** Being pushed by frustrated customers toward opinionated blueprints and hands-on implementation support
- **System integrators:** The critical translation layer between generic foundation models and messy domain-specific workflows
- **Builders:** Demonstrating in public—months before board-level consensus caught up—that software engineering skills and systems thinking are required, not optional

**Why it matters:**

The market is finally articulating what builders have been saying: you can’t just “plug in” models; you must build systems—data pipelines, tool integrations, guardrails, evals, change management.

BCG’s research shows the 5% of “future-built” companies achieving real AI value are investing in end-to-end capabilities—not just API access—and seeing 1.7x revenue growth, 3.6x shareholder return, and 2.6x EBIT margin vs. laggards.

Vendors that package end-to-end solutions (data pipelines, workflow templates, evaluation frameworks, governance) will outcompete raw-model providers in the enterprise segment. The “AI doesn’t work” complaints are almost universally “we didn’t implement it as a system” complaints.

**What to watch:**

- Vendor marketing pivoting from “magic copilots” to “reference architectures” and implementation playbooks
- Enterprises formalizing “AI platform engineering” teams in 2026
- Consulting firms shifting from “AI strategy” to “AI systems integration”

---


## **Exa Launches People Search—Turning “Find The Right Human” Into An API Primitive for AI Agents**

**What happened:**

On December 16, Exa announced people search as part of its “search engine for AIs,” with benchmarks evaluating precision, recall, and ranking quality for finding individuals by role, expertise, and contextual descriptions.

Specs:

- Indexes 1B+ profiles and web pages
- Fine-tuned embeddings with hybrid retrieval optimized for entity resolution and profile clustering
- Tens of millions of updates per week
- Natural language queries (e.g., “US-based founders of startups that have raised over $10M”)

Exa raised $85M Series B in September 2025 at $700M valuation. Builders are already wiring it into outbound sales, recruiting, and investor-discovery agents.

**Who’s involved:**

- **Exa:** Moving from generic neural web search to domain-specific “people infrastructure” for agents
- **Sales/recruiting tool builders:** Gaining drop-in API without building their own crawling, entity-resolution, and ranking stack
- **Agent framework authors:** Can wire people search as a first-class tool for prospecting, expert routing, advisory assembly
- **Competing data providers (ZoomInfo, Apollo, LinkedIn):** Pressured to open agent-friendly APIs or partner with retrieval vendors

**Why it matters:**

Most serious agents need to find and reason about people—customers, experts, decision-makers. Exa turns that into a standardized API primitive that builders can integrate in hours rather than months.

For B2B SaaS around SDR, recruiting, or partnerships, this collapses the infrastructure burden for “AI prospector” products, making them feasible for teams without dedicated data engineering.

Bottom line: people search is Exa’s bid to own a critical primitive in the agentic stack—”find a person” the way Stripe owns “charge a card.”

**What to watch:**

- Case studies where agents autonomously build outreach lists or match tickets to internal experts
- Whether Exa exposes higher-level abstractions (”find 20 similar prospects to this ICP”)
- Competitor response from ZoomInfo or LinkedIn with agent-friendly APIs

---


## **Meta Ships SAM Audio—Open-Source Multimodal Audio Separation for Any Sound**

**What happened:**

On December 16, Meta introduced SAM Audio, a unified multimodal model for audio separation that isolates any sound from complex mixtures using text prompts (”isolate the guitar”), visual cues (pointing to an object in a video), or time-span selections. Open-sourced with perception encoder, benchmarks, and research papers. Outperforms prior models on general sound, speech, music, and instrument separation benchmarks. The announcement garnered 6,200 likes and 1M views on X.

SAM Audio joins Meta’s Segment Anything family, integrable via the Segment Anything Playground alongside SAM 2 for video and SAM 3D for 3D scenes.

**Who’s involved:**

- **Meta:** Extending Segment Anything into audio; building developer mindshare via open-source even as it competes with OpenAI and Google on closed models
- **Creators and builders:** Gaining free access to audio separation that previously required expensive commercial plugins or extensive manual editing
- **Accessibility developers:** Can build real-time speech isolation for hearing aids, transcription, or assistive technology

**Why it matters:**

SAM Audio gives creators and builders an open-source tool for audio separation that previously required expensive, closed commercial plugins. Ideal for podcast producers, video editors, musicians, and accessibility applications like isolating speech from background noise.

Meta’s decision to open-source SAM Audio (like SAM 2 before it) positions the company as the “PyTorch of multimodal AI,” building ecosystem lock-in through developer adoption rather than API revenue.

**What to watch:**

- Adoption in creative tools (Adobe, DaVinci Resolve, Final Cut Pro plugins)
- Accessibility software integrations (real-time speech isolation for hearing aids or transcription)
- Whether OpenAI or Runway ship comparable audio editing models or partner with Meta’s open ecosystem

---


## **Amazon Reshuffles AI Leadership—DeSantis Takes Unified Command as Prasad Exits**

**What happened:**

On December 16, Amazon CEO Andy Jassy announced a major AI reorganization. Peter DeSantis, a 27-year AWS veteran who has led infrastructure, compute, applications, and networking, will now head a new unified Amazon AI organization spanning:

- AGI (artificial general intelligence) team
- Custom silicon development (Trainium and Inferentia chips)
- Quantum computing

DeSantis reports directly to Jassy.

Rohit Prasad—who built Alexa and led Amazon’s AI initiatives (including the Nova model family) for the past two years—is leaving at year’s end after Amazon lagged rivals like OpenAI in generative AI momentum. The move follows reports of Amazon’s potential $10B+ investment in OpenAI and signals AI’s elevated priority across AWS and company-wide operations.

The announcement received 88 likes and ~37K views on X, with replies criticizing Prasad’s leadership for missing the LLM wave and viewing the shift as treating AI as a core systems and infrastructure challenge rather than a product layer.

**Who’s involved:**

- **Peter DeSantis:** Now owns Amazon’s entire AI stack from silicon to AGI research
- **Rohit Prasad:** Departure marks end of Alexa-first AI strategy
- **Andy Jassy:** Elevating AI to infrastructure-level priority, potentially signaling partnership strategy (OpenAI investment) over pure build-it-yourself approach
- **AWS customers and competitors:** Watching whether unified leadership accelerates Amazon’s competitiveness against Microsoft (Azure + OpenAI) and Google (Vertex AI + Gemini)

**Why it matters:**

Amazon is treating AI as a core infrastructure and systems problem—silicon, training clusters, quantum integration—rather than just a model-serving API layer. This could accelerate competitiveness against Microsoft and Google.

Prasad’s exit underscores the cost of missing generative AI’s inflection point: Alexa, once a showcase for conversational AI, became a cautionary tale of pre-LLM architectures. Amazon is now rebuilding from the ground up with an infrastructure-first leader rather than a product-first one.

**What to watch:**

- DeSantis’s first major announcements: custom silicon roadmaps for Trainium 2/3, AGI team product launches, or quantum-AI integration demos
- Whether Amazon’s potential OpenAI investment materializes—marking a strategic shift from “build everything” to “partner for frontier models, own infrastructure”
- How quickly unified leadership translates to competitive AWS AI offerings

---


## **Physical Intelligence Discovers Emergent Human-to-Robot Transfer in Scaled VLA Models**

**What happened:**

On December 17, Physical Intelligence posted about discovering an emergent property in their vision-language-action (VLA) models (π0, π0.5, π0.6): as pre-training scales up on diverse robot data, the models automatically learn to align egocentric human videos (captured via wearable cameras) with robot demonstrations—enabling transfer from human videos to robotic tasks without explicit human-to-robot translation layers.

Key findings:

- Fine-tuning π0.5 with human videos doubled performance on depicted tasks compared to robot-only data
- Transfer improves with robot data scale and diversity
- In the latent representations, human videos “look” like robot demos to the scaled models—alignment emerges naturally

The post, including a 122-second demo video and technical charts, garnered 2,480 likes and ~980K views on X, with replies calling it a precursor to full “surrogate” learning where models internalize human intent without needing explicit action mapping.

**Who’s involved:**

- **Physical Intelligence:** Demonstrating emergent capabilities in VLAs analogous to LLM scaling surprises
- **Robotics research community:** Evaluating whether this transfers across other VLA architectures (Google’s RT-X, Tesla’s Optimus stack)
- **Data infrastructure teams:** Recognizing human video may become a critical training resource for robot policies

**Why it matters:**

This suggests robot foundation models may follow LLM-style scaling laws where emergent capabilities—like automatic human-to-robot transfer—appear as data volume and model scale increase.

The implications are significant: human video is vastly more abundant than robot demonstrations. If scaled VLAs can automatically leverage human video, it unlocks orders of magnitude more training data without expensive robot teleoperation or simulation.

For robotics builders, the path to general-purpose robot policies may look more like “scale a VLA on diverse data” and less like “hand-engineer domain transfer for every new task.”

> *This is my vote for the story of the year. If robots can start to learn from POV videos of humans doing activities, we have the potential to see a massive acceleration moment for robotics doing industrial applications that require hand movements.*
>
> *The fact that the LLM evolved this capability spontaneously is particularly encouraging, since it suggests positive cross-over effects on robotics driven by LLM intelligence gains. The accelerating LLM flywheel may jumpstart the robotics flywheel in 2026, and that leads to faster growth of a new $10-100T economy.*

**What to watch:**

- Whether human-to-robot transfer results replicate across other VLA architectures
- How quickly Physical Intelligence scales π0.6+ with large human video datasets
- Whether this enables step-change improvements in robot generalization and sample efficiency by mid-2026

---


#### [Want to dig in more? Grab the Perplexity for this week’s news](https://www.perplexity.ai/search/please-create-a-perplexity-rep-xV0DjupSTiW2yF7bFBIiVA#0)

[![](https://substackcdn.com/image/fetch/$s_!-jRH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25a3ab56-4717-41c1-93a7-5c0d8704cb4e_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!-jRH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F25a3ab56-4717-41c1-93a7-5c0d8704cb4e_1024x1024.png)
