---
title: "Grab My Custom Prompt for This Week's AI News + 10 Minutes on the 7 Stories That Mattered"
author: "Nate Jones"
published: 2025-10-18
url: https://natesnewsletter.substack.com/p/i-read-17-hours-of-ai-news-this-week
audience: everyone
scraped_at: 2026-01-05 19:14:00
---

This week Google’s AI generated not one but TWO novel cancer therapy hypotheses—and both have been validated experimentally.

We’re past pattern matching. We’re past guessing whether AI can make breakthroughs.

AI is doing actual scientific innovation twice a week. That’s how fast we’re moving.

Meanwhile, Andrej Karpathy released the complete recipe to train your own ChatGPT for $100 in four hours. Students can now understand LLM training mechanics for less than a textbook costs.

And OpenAI committed $350-500 billion to custom chips with Broadcom. Ten gigawatts by 2029—the power consumption of 8 million households.

Stepping back from the rush, I think we’re seeing three shifts: AI moving from analysis to scientific discovery, compute infrastructure at national grid scale, and training democratization from black-box systems to reproducible education.

**Top Stories this week (plus a custom prompt to help you digest it all)**

- Google’s dual cancer AI breakthrough generating validated therapy hypotheses and detecting mutations

  - Useful for anyone in science / healthcare
  - Plus good for understanding how deep model innovation works
- OpenAI-Broadcom 10-gigawatt custom chip partnership through 2029

  - Understand Sam Altman’s grand strategy
  - Intel for leaders as we forecast token availability and cost curves
- Anthropic launched Claude Skills for modular agent customization

  - I did a [story on this yesterday](https://open.substack.com/pub/natesnewsletter/p/new-claude-just-made-prompting-10x?r=1z4sm5&utm_campaign=post&utm_medium=web&timestamp=513.7&showWelcomeOnShare=false)
  - This steps back in strategic context—why it’s one of the biggest releases of the year
- Microsoft shipped Copilot Actions for autonomous workflow automation

  - Dig into Microsoft’s strategy
  - Intel especially if you have CoPilot and are worried about surveillance
- Nvidia’s $3,999 DGX Spark brings datacenter AI to desktops

  - Nvidia’s play for engineers and a new compute form factor
  - Implications for software and non-tech as well
- Andrej Karpathy’s nanoChat: train ChatGPT from scratch for $100

  - Lots here for vibe coders and educators!
- Featured read: Building 300k+ lines with parallel AI agents

  - I LOVED this read—takeaways even if you’re not an engineer

I spent 17 hours reading these stories so you could catch up in 10 minutes. But reading without extraction is just information collecting.

I’m including a personalized analysis prompt designed for this week—a structured conversation that maps these stories to your role, constraints, and priorities.

No more “interesting, but what does this mean for me?” You get the stories that matter for your situation, plus a very structured prompt to enable you to develop custom applications for your role and problem space. The prompt helps you take the news and actually take the next step and make it useful for what you’re doing day-to-day.


## [Grab the Custom Prompt for This Week’s News](https://www.notion.so/product-templates/October-17-News-Prompt-2905a2ccb526803a80b5ea0e2980aa7a?source=copy_link)

Want an information snack? Just grab the link and run this prompt in a good thinking model like GPT-5, Claude Sonnet 4.5, or Gemini 2.5 Pro, and have fun!

---


## Strategic AI News Roundup: October 13–17, 2025


### Story 1: Anthropic Launches Claude Skills — The Agent Customization Platform

**What happened:** Anthropic released Claude Skills on October 15, introducing a new architecture that packages instructions, scripts, and resources into reusable folders that Claude loads on-demand when relevant to specific tasks. Skills work across Claude.ai, Claude Code, and API, with companies able to create custom Skills or use Anthropic-provided ones for Excel, PowerPoint, Word, and fillable PDFs. The feature makes Claude “faster, cheaper, and more consistent” by loading only minimal information when needed rather than repeatedly processing full context. Users create Skills via an interactive “skill-creator” skill that guides setup without manual file editing.

**Who’s involved:**

- **Anthropic:** Shipped Skills alongside documentation, marketplace integration via GitHub (anthropics/skills), and API endpoints for version management
- **Enterprise adopters:** Box (file transformation into presentations/spreadsheets with org standards), Canva (customizing agents for design workflows), Rakuten (management accounting that cuts day-long tasks to one hour), and Notion (faster question-to-action workflows)
- **Developers:** Can fork Skills from GitHub marketplace, install via Claude Code plugins, or build custom Skills through `/v1/skills` API endpoint

**Why it matters:**

- **Platform shift beyond prompts:** Skills represent Anthropic’s move from “smart chatbot” to modular agent platform—packaging organizational expertise into reusable components rather than forcing users to re-prompt context repeatedly
- **Efficiency architecture:** Token-efficient metadata scanning means Claude only loads what’s needed, reducing costs and latency while maintaining specialized capabilities
- **Composability advantage:** Skills automatically stack together—Claude identifies which combinations are needed and coordinates their use without manual orchestration
- **MCP comparison thesis:** Tech observers like Simon Willison argue Skills may be “a bigger deal than MCP” because they’re conceptually simpler, require no server infrastructure, and work immediately across all Claude surfaces

**What to watch:** Enterprise governance controls (currently two-tier org-level enablement plus individual opt-in, but lacking granular skill-level permissions), competitive response from OpenAI and Google, and whether Skills become the standard abstraction layer for agentic workflows. The code execution requirement raises security considerations that may slow adoption in regulated industries.

---


### Story 2: Google’s Dual Cancer AI Breakthrough — Scientific Discovery at Computational Scale

**What happened:** Google Research and DeepMind released two cancer AI models this week that demonstrate AI moving from data analysis to scientific hypothesis generation:

**DeepSomatic (October 15):** AI tool using convolutional neural networks that identifies cancer-causing genetic mutations more accurately than existing methods across all major DNA sequencing platforms. In benchmark tests, DeepSomatic achieved 90% F1-score on insertions/deletions with Illumina sequencing (vs. 80% next-best method) and >80% on Pacific Biosciences long-read data (vs. <50% for competitors). The model successfully identified key mutations in preserved clinical samples from pediatric leukemia and glioblastoma cases.

**Cell2Sentence-Scale 27B (October 14):** A 27-billion-parameter foundation model built on Gemma that generated a **novel, experimentally validated hypothesis** about cancer immunotherapy. The AI analyzed 4,000+ drugs via “dual-context virtual screening” and predicted that silmitasertib (CX-4945)—a CK2 kinase inhibitor with no prior documented connection to antigen presentation—would dramatically boost immune visibility of “cold tumors” when combined with low-dose interferon. Lab tests on human neuroendocrine cells confirmed a ~50% increase in antigen presentation.

**Who’s involved:**

- **Google Research & DeepMind:** Developed both models; C2S-Scale built on Gemma architecture, trained on over 1 billion single-cell profiles
- **Academic partners:** UC Santa Cruz Genomics Institute (DeepSomatic lead), Yale University (C2S-Scale collaboration), Children’s Mercy Hospital, Translational Genomics Research Institute (clinical validation)
- **Open-source release:** Both models and datasets released publicly via GitHub and Nature Biotechnology publication

**Why it matters:**

- **AI-generated scientific discovery:** This marks the first peer-reviewable case of an LLM generating a **novel cancer therapy hypothesis later validated in wet-lab experiments**—not pattern recognition but actual scientific reasoning
- **“Surprising hits” vs. known drugs:** Of the drug candidates C2S-Scale identified, 10-30% were known from literature; the remainder including CX-4945 were “surprising” with no documented mechanism
- **Scaling unlocks new capabilities:** Google’s research demonstrates that larger biological models don’t just improve accuracy—they acquire entirely new hypothesis-generation capabilities, validating biological AI scaling laws
- **Clinical acceleration potential:** DeepSomatic’s 10× speed improvement in genetic analysis could make genomic sequencing routine in cancer care rather than a specialty procedure

**What to watch:** Preclinical and clinical trial progression for the CX-4945 combination therapy (years away from human trials), whether competitors can replicate the discovery methodology, and if this establishes Google DeepMind as the leader in computational biology over traditional pharma R&D. Sundar Pichai called it “a milestone for AI in science”—watch for Google positioning in AI-powered drug discovery partnerships.

---


### Story 3: OpenAI–Broadcom 10-Gigawatt Chip Partnership — Custom Silicon at National Grid Scale

**What happened:** OpenAI and Broadcom announced a multi-year collaboration on October 13 to co-develop and deploy **10 gigawatts of custom AI accelerators**. OpenAI designs the accelerators and rack systems, embedding frontier model learnings directly into hardware; Broadcom develops and manufactures using its Ethernet and connectivity solutions. Deployments begin second half of 2026, completing by end of 2029 across OpenAI facilities and partner data centers. The partnership builds on 18 months of prior collaboration and represents an estimated **$350–500 billion buildout**—one of the largest hardware commitments in AI history.

**Who’s involved:**

- **OpenAI:** Handles accelerator and system design, aims to embed model development insights into custom silicon to “unlock new levels of capability”
- **Broadcom:** Provides chip development, Ethernet networking (ConnectX solutions for scale-up/scale-out), and manufacturing deployment
- **Deployment scale:** 10 GW equals power consumption of ~8 million U.S. households or 5× Hoover Dam output; industry estimates suggest $50B per 1 GW data center ($35B for chips alone at current Nvidia pricing)

**Why it matters:**

- **Vertical integration play:** OpenAI joins Google (TPU), Amazon (Trainium), Apple (Neural Engine), and Meta (MTIA) in controlling the full compute stack—critical for cost control and supply sovereignty amid chip shortages
- **Multi-vendor strategy:** The Broadcom deal adds to OpenAI’s existing commitments: ~10 GW Nvidia, ~6 GW AMD, plus Oracle cloud partnership—totaling roughly **26 GW across suppliers**
- **Ethernet vs. proprietary interconnects:** The deal uses Broadcom Ethernet-based networking rather than Nvidia’s NVLink, suggesting a bet on vendor-neutral, scalable datacenter architectures
- **Timeline signal:** 2026–2029 deployment window indicates OpenAI planning for post-GPT-5 model generations requiring dramatically more compute

**What to watch:** Whether custom silicon delivers the promised cost/performance advantages over Nvidia GPUs, how Broadcom stock (up 9.88% on announcement) performs as deployments ramp, and if this triggers an arms race with competitors building their own chips. The sheer power demand (10 GW) also raises questions about data center energy availability and OpenAI’s infrastructure partnerships to secure it.

---


### Story 4: Walmart × OpenAI — ChatGPT Becomes a Commerce Platform

**What happened:** Walmart and OpenAI announced a partnership on October 14 enabling customers to **shop and complete purchases directly within ChatGPT** using “Instant Checkout”. Shoppers can describe needs conversationally (”meal ideas for family of four,” “restock household essentials”), and ChatGPT curates Walmart products with one-tap checkout via Stripe payment integration. Walmart CEO Doug McMillon stated this shift marks the end of “search bar and long list of item responses” eCommerce, calling it “agentic commerce” where AI predicts customer needs proactively.

**Who’s involved:**

- **Walmart:** Second-largest U.S. retailer ($611B revenue, 2024), first major retailer to embed full transactional checkout within ChatGPT
- **OpenAI:** Expands ChatGPT from information tool to transactional commerce platform; partnership follows recent deals with Instacart and DoorDash
- **Stripe:** Powers payment processing; includes address pre-fill, payment verification, and order confirmation within ChatGPT interface

**Why it matters:**

- **Search to conversation:** Shifts retail paradigm from keyword search to conversational intent discovery—”what do I need?” rather than “what am I searching for?”
- **Distribution leverage:** OpenAI positions ChatGPT as primary interface layer across commerce verticals (food delivery, ridesharing, now general retail), threatening Google Shopping and Amazon Alexa
- **First-mover retail advantage:** Walmart gains exclusive positioning as ChatGPT’s general retailer while Target, Amazon, and others remain absent from the platform
- **Agentic commerce thesis:** McMillon argues AI agents will automate routine purchases (”I’m out of dishwasher soap”) without user initiation, fundamentally changing how consumers shop

**What to watch:** Transaction volume and conversion rates compared to Walmart.com’s traditional interface, whether OpenAI maintains retailer exclusivity or allows competing merchants, and how Amazon responds. Privacy advocates raise concerns about OpenAI storing shopping behavior across multiple verticals.

---


### Story 5: Microsoft October 2025 Update — Windows 11 as Agentic Operating System

**What happened:** Microsoft shipped sweeping Copilot upgrades on October 16 positioning Windows 11 as the first operating system built for agentic AI workflows. Major releases include:

- **“Hey Copilot” hands-free activation:** Always-listening voice assistant (opt-in) that triggers without key presses, similar to “Hey Siri” or “Alexa”
- **Copilot Actions:** Autonomous task execution where users define recurring workflows (summarize unread emails, generate morning briefings, reschedule meetings based on priorities) that run automatically on triggers
- **OS-level integration:** Copilot embedded across File Explorer, Settings, taskbar, and notification center—no longer isolated sidebar feature
- **Extended context:** Copilot can now reference “everything on your PC”—open documents, file history, browser tabs, and calendar—to provide contextual suggestions

Microsoft claims this makes “every Windows 11 PC an AI PC” regardless of hardware, though neural processing units (NPUs) accelerate performance.

**Who’s involved:**

- **Microsoft:** Positions Windows 11 update as “agentic computing” differentiator against Apple’s Intelligence and Google’s Gemini integrations
- **Enterprise adoption:** Copilot Actions specifically target knowledge workers spending hours on repetitive tasks; current preview available to commercial Microsoft 365 subscribers
- **Hardware partners:** NPU-equipped laptops from Dell, HP, Lenovo, Surface line get performance prioritization for Copilot features

**Why it matters:**

- **OS as agent orchestration layer:** Microsoft redefines the operating system from passive tool to active assistant that anticipates needs and executes tasks autonomously—significant UX paradigm shift
- **Privacy vs. productivity tension:** “Everything on your PC” context awareness raises questions about local vs. cloud processing and data retention policies
- **Competitive pressure on Apple/Google:** The release escalates the AI OS wars; Apple Intelligence (iOS 18) and Android’s Gemini integration lack comparable autonomous task execution
- **Enterprise workflow automation:** Copilot Actions could eliminate entire categories of administrative work, but also introduces new failure modes when AI misinterprets user intent

**What to watch:** User adoption rates for always-listening activation (disabled by default), enterprise IT policies around Copilot Actions permissions, and whether Microsoft’s aggressive integration drives switchers from macOS. Privacy advocates are already criticizing the expanded data access.

---


### Story 6: Nvidia DGX Spark — Datacenter AI on Your Desk for $3,999

**What happened:** Nvidia began shipping DGX Spark on October 15, a compact desktop computer designed to bring datacenter-class AI development to individual researchers and developers. The GB10 Grace Blackwell system features:

- **144 Arm Grace CPU cores** (72 Neoverse V3, 72 energy-efficient E cores)
- **64GB LPDDR5X memory** with 410 GB/s bandwidth
- **Dual M.2 SSD slots** supporting 16TB total storage
- **Under $4,000 price point** positioning it against Mac Studio and high-end workstations
- **Time Magazine Best Inventions 2025** honoree for accessibility impact

DGX Spark runs inference and fine-tuning for models up to ~13B parameters locally, with Nvidia claiming 100 tokens/second generation speed for 7B models. The system targets developers working on multi-agent systems, robotics simulation, and edge AI deployment who need realistic testing environments before cloud-scale deployment.

**Who’s involved:**

- **Nvidia:** DGX Spark extends the DGX brand (historically $100K+ datacenter systems) to accessible developer hardware
- **Developer community:** Initial reviews from AI researchers emphasize local inference for privacy-sensitive applications and rapid prototyping without cloud API costs
- **Comparisons:** Tech observers position Spark against Apple M4 Mac Studio (AI/ML optimized but macOS-only) and Nvidia’s own RTX 5000 series (gaming-focused, less optimized for transformer workloads)

**Why it matters:**

- **Democratization narrative:** Putting sophisticated AI development hardware at consumer price points accelerates innovation from individual researchers and startups without enterprise cloud budgets
- **Arm architecture statement:** Nvidia’s use of Arm Grace CPUs (vs. traditional x86) validates Arm’s push into AI compute beyond mobile devices
- **Local inference shift:** As models shrink through quantization and distillation, DGX Spark enables privacy-preserving AI applications that never send data to external servers
- **Edge deployment testing:** Developers building for robots, autonomous vehicles, or IoT can prototype on hardware matching deployment constraints

**What to watch:** Sales volume and developer community uptake, whether competitors like AMD or Intel launch similar developer-focused AI systems, and if Spark establishes a new product category between consumer PCs and enterprise servers. Early users report thermal management challenges during sustained inference workloads.

---


### Story 7: Andrej Karpathy Releases nanoChat — $100 DIY ChatGPT in Four Hours

**What happened:** Former OpenAI researcher and Tesla AI director Andrej Karpathy released nanoChat on October 14, a minimal end-to-end ChatGPT-style pipeline that anyone can train from scratch for approximately $100 in compute costs and complete in about 4 hours. The project demonstrates how to:

- **Pre-train a small language model** (561M parameters) on FineWeb-Edu dataset
- **Apply supervised fine-tuning (SFT)** using curated instruction-following examples
- **Implement reinforcement learning from human feedback (RLHF)** with reward modeling and PPO
- **Deploy a functional chatbot** with conversational capabilities

Karpathy released the full code, training scripts, and model weights via Hugging Face under permissive license. The project explicitly targets students, hobbyists, and researchers who want to understand LLM training mechanics without abstractions.

**Who’s involved:**

- **Andrej Karpathy:** Independent AI educator/researcher known for accessible technical explanations; previously built similar educational projects like micrograd and nanoGPT
- **Training infrastructure:** Model trained on single Nvidia H100 GPU using Modal cloud platform ($0.025/minute); total training cost ~$100-150 depending on optimization
- **Community response:** AI education forums and Reddit communities praised the project for demystifying LLM training; several developers already published variations and improvements

**Why it matters:**

- **Transparency counter-narrative:** While frontier labs increasingly black-box their training processes, nanoChat demonstrates that core techniques are understandable and reproducible
- **Education accessibility:** Computer science students can now train a working chatbot for less than a textbook costs, making LLM education practical at undergraduate level
- **Capability calibration:** The 561M parameter model performs poorly compared to production systems, giving users realistic intuition about why GPT-4 and Claude require billions in compute
- **Open research culture:** Karpathy’s pattern of releasing educational code (YouTube tutorials, GitHub repositories) helps maintain knowledge diffusion as AI research consolidates in private labs

**What to watch:** Whether universities adopt nanoChat into AI curriculum, if students use it as foundation for novel research directions, and whether industry researchers publish similar “from scratch” implementations for emerging techniques like sparse architectures or multimodal training. Some observers note the project’s pedagogical value may outweigh its practical utility.

---


## My Favorite Read This Week

**“[Just Talk To It: The No-BS Way of Agentic Engineering](https://steipete.me/posts/just-talk-to-it)”** by Peter Steinberger​

**Synopsis:** A brutally honest field report from an engineer building a 300k+ LOC TypeScript project entirely with AI agents. Steinberger runs 3-8 parallel instances of OpenAI’s `codex` CLI in a terminal grid, lets agents make atomic git commits, and spends 20% of his time on AI-driven refactoring. He’s moved completely away from Claude Code (despite early enthusiasm) due to language/UX friction, dismisses most agentic tooling as “thin wrappers with no moat,” and argues that the industry overcomplicates workflows with subagents, elaborate prompt engineering, and RAG when simple conversational iteration works better.

**Key technical details:** He uses GPT-5-codex as his daily driver for its 230k usable context (vs Claude’s 156k), efficient token use, message queuing, and superior file-reading strategy before making changes. His `Agents.md` file is 800 lines of “organizational scar tissue” auto-generated by the model itself. He rarely uses slash commands beyond `/commit` and `/automerge`, preferring natural language. Screenshots constitute ~50% of his prompts for faster context-sharing.

**Big Takeaway:** **Intuition beats infrastructure.** The best way to work with AI agents isn’t building elaborate scaffolding—it’s developing judgment about scope (”blast radius”), knowing when to intervene versus let it run, and treating AI like a collaborator you’re iterating with in real-time. The skills that make you effective with agents mirror what makes anyone effective managing people or projects: understanding when a task is getting off-track, breaking complex work into manageable chunks, and course-correcting quickly. Most tooling and frameworks are working around current limitations rather than leveraging AI’s actual strengths. As models improve, the ceremony disappears—just talk to it.

**Why it matters this week:** Steinberger’s workflow validates what the Claude Skills and Copilot Actions launches are pointing toward—agents work best when they’re **embedded in natural workflows with minimal overhead**, not wrapped in elaborate systems. His dismissal of most agentic tooling (”no moat”) aligns with the platform consolidation trend: Anthropic, OpenAI, and Microsoft are racing to own the agent layer directly, and middleware risks commoditization. The post cuts through vendor hype with a practitioner’s perspective: the infrastructure is already capable enough that productivity comes from using it well, not engineering around it. This applies whether you’re managing code, content, research, or business workflows.

---


#### *And that’s 17 hours of news in 10 minutes!*

[![](https://substackcdn.com/image/fetch/$s_!zqnR!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4476f2e-0f86-4135-9006-fbae504fa8ea_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!zqnR!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe4476f2e-0f86-4135-9006-fbae504fa8ea_1024x1024.png)
