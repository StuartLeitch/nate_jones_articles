---
title: "Six Stories That Mattered This Week in AI"
author: "Nate Jones"
published: 2025-10-25
url: https://natesnewsletter.substack.com/p/grab-my-prompt-for-this-weeks-ai
audience: everyone
scraped_at: 2026-01-05 19:13:30
---

This week in AI was nuts.

OpenAI launched a browser.

Meta laid off 600+ very smart people in their AI division (OpenAI snapped a bunch of them up).

Anthropic just cooked up a deal with Google to get them out of their compute bottleneck.

And none of those are the most interesting story of the week! That belongs to Citigroup and their big reveal that AI agents are already saving them 50 developer YEARS per WEEK.

You read that right. I dug into how companies like Citigroup get insane numbers like that with AI, plus the implications for all of us wrestling with building AI agents.

I also put together a prompt for this week’s news so you could figure out how it applies to you, specifically, in like 5 minutes.

Plus I grabbed a few other stories that really mattered, including Apple launching AI-native silicon (LOL when will they launch a real model though).

Dig in with the coffee and have fun!


## [Grab this week’s news prompt](https://www.notion.so/product-templates/NEWS-Prompt-Oct-25-2965a2ccb52680d983ded07050f472c2?source=copy_link)

Most AI news analysis stops at “here’s what happened” and leaves you to figure out what it means for your work. That’s not helpful. This prompt gives you a way to actually think through these six developments in the context of your specific business, role, and priorities. Copy it into Claude or ChatGPT, answer a few questions about your situation, and you’ll get analysis that cuts through the noise to focus on what actually matters for you. It’s designed to move you from “interesting news” to “here’s what I should do about it” in one conversation.


# Six Stories That Mattered This Week in AI

This week showed us where the AI industry is heading and where it’s vulnerable. We’re seeing major platform shifts as OpenAI and others move from chat interfaces to controlling how users access the web. We’re watching new architectural patterns emerge that change how we think about prompting and agent capabilities.

We’re seeing hardware-software integration accelerate in ways that could reshape where AI computation happens. And we’re confronting the reality that the security models we’ve relied on don’t work for AI-native applications.

Meanwhile, enterprises are starting to publish real numbers on AI productivity gains—but only when they’re willing to invest what it takes. And competitive dynamics are forcing even well-resourced companies to question whether their strategies are working.

These six stories matter because they’re not isolated developments. They’re interconnected pieces of how AI infrastructure, enterprise adoption, and product strategy are evolving right now. Let’s dig in.

---


## Top 6 AI News Stories for Builders: October 19-24, 2025


## **Story 1: OpenAI Launches Atlas Browser**

**What happened:**
OpenAI launched Atlas on October 21, an AI-powered web browser that directly competes with Chrome, Safari, and Edge. Atlas has no traditional address bar—users enter URLs through ChatGPT’s chat interface, making the chatbot the primary gateway to the web.

The browser includes “agent mode” (experimental, Plus/Pro only) that can perform tasks on users’ behalf, such as interacting with word processors and online grocery platforms. Currently macOS-only with Windows, iOS, and Android versions planned. With ChatGPT’s 800 million weekly active users, Atlas positions OpenAI to control more of the search and browsing experience while collecting user data to improve future AI models.

**Who’s involved:**

- **OpenAI:** Launched Atlas as part of a strategy shift from chatbot to full internet platform, CEO Sam Altman described it as “a once-in-a-decade chance to redefine the concept of a browser”
- **Perplexity:** Launched competing Comet browser with similar AI-native features around the same time
- **Builders:** Gain access to AI-first browsing primitives, though face new security challenges
- **Google, Apple, Microsoft:** Face new competition in browser market share from AI-native entrants

**Why it matters:**

- **Platform consolidation:** OpenAI transitions from AI service provider to internet infrastructure layer, similar to Google’s Chrome strategy a decade ago
- **Data control:** Eliminates need for competing search engines, allowing OpenAI to directly collect browsing data for model training
- **Developer ecosystem shift:** AI-native browsers create new UX paradigms and integration points for builders
- **Competition catalyst:** Triggered similar moves from Perplexity and forced incumbents to accelerate AI browser features

**What to watch:**
Adoption rates among ChatGPT’s massive user base, whether Atlas can achieve meaningful browser market share against Chrome’s dominance, security and privacy implementations, and how quickly Google/Microsoft respond with AI-native browser features. The New York Times lawsuit against OpenAI over copyright violations adds legal uncertainty to the browser’s future.

---


## **Story 2: Anthropic Agent Skills Launch**

**What happened:**
Anthropic launched Agent Skills on October 16, a modular system allowing developers to package reusable workflows, scripts, and domain expertise into folders that Claude can dynamically load and compose.

Skills are **composable** (multiple skills work together automatically), **portable** (same format across Claude.ai, Claude Code, and API), **efficient** (progressive disclosure loads only relevant context), and available for Pro, Max, Team, and Enterprise plans with code execution enabled. Early enterprise adopters include Box, Rakuten, and Canva. The system uses progressive disclosure to manage context efficiently rather than loading everything upfront.

**Who’s involved:**

- **Anthropic:** Shipped Skills alongside existing Claude capabilities, positioning it as “maybe a bigger deal than MCP” per Simon Willison
- **Enterprise customers:** Box, Rakuten, Canva adopting Skills for workflow automation; Salesforce integrated Claude within trust boundary; Deloitte rolling out to 470,000+ professionals
- **Developers:** Can now create portable, reusable agent capabilities without rebuilding from scratch
- **Competing labs:** OpenAI’s AgentKit and Google’s agent frameworks face comparison with Skills’ composability

**Why it matters:**

- **Workflow portability:** Skills work across Claude.ai, Claude Code (IDE), and API, eliminating platform lock-in
- **Enterprise adoption:** Major deployments (Deloitte 470k users, Salesforce integration) validate enterprise readiness
- **Composability advantage:** Multiple skills automatically work together vs single-purpose tools requiring manual orchestration
- **Context efficiency:** Progressive disclosure solves token limit constraints that plague other agent frameworks

**What to watch:**
Developer creation of third-party Skills marketplace (very strong so far), enterprise adoption rates vs custom agent solutions, performance comparisons with OpenAI’s AgentKit and tool-calling APIs, and whether Skills becomes the standard format for agent capabilities.

---


## **Story 3: Apple M5 Chip Launch**

**What happened:**
Apple released M5-powered MacBook Pro and iPad Pro models available starting October 22. The M5 chip delivers **over 4x peak GPU compute performance** for AI compared to M4, with **Neural Accelerators embedded in each GPU core** for on-device AI workloads, **up to 3.5x faster AI performance** for workflows, a **16-core Neural Engine** for faster LLM inference, and **30% faster graphics performance.**

MacBook Pro offers up to 24 hours battery life. The M5 represents Apple’s most significant AI hardware leap, positioning Mac/iPad as serious platforms for local AI development and inference.

**Who’s involved:**

- **Apple:** Shipped M5 across MacBook Pro, iPad Pro, and Vision Pro product lines
- **Developers:** Gain access to significantly faster on-device AI capabilities for app development
- **AI builders:** Can now run larger models locally with better performance/watt than cloud alternatives
- **Enterprise buyers:** Face decision between M5’s local AI advantages vs cloud-based workflows

**Why it matters:**

- **On-device AI viability:** 4x AI compute makes local LLM inference practical for many use cases, reducing cloud dependencies
- **Privacy advantage:** Local processing enables AI features without sending data to cloud providers
- **Cost structure shift:** High upfront hardware cost but zero ongoing inference costs vs cloud pricing
- **Ecosystem lock-in:** Apple’s integrated hardware/software advantages create moat against Windows/Linux AI development

**What to watch:**
Real-world benchmarks of M5 running popular AI models (Llama, Mistral, etc.), developer adoption for building M5-optimized AI apps, battery life under sustained AI workloads, and whether local inference becomes competitive with cloud for production use cases.

---


## **Story 4: AI Browser Security Crisis**

**What happened:**
Security researchers uncovered critical vulnerabilities across multiple AI-native browsers in October 2025, exposing fundamental security flaws in how AI browsers handle the boundary between user commands and untrusted web content.

**Perplexity’s Comet browser** faced two major disclosures:

**Brave researchers** (October 21) discovered **prompt injection via screenshots**—hidden text (faint blue on yellow background, invisible to humans) extracted via OCR when users screenshot pages can inject malicious commands directly to AI.

**LayerX researchers** (October 4) found **“CometJacking” (CVE-2025-62353, CVSS 8.6 High)**—crafted URLs force Comet to read from memory (emails, calendar, contacts), encode results (e.g., base64), and POST to attacker-controlled endpoints.

**Windsurf coding IDE** disclosed **path traversal vulnerability (CVE-2025-62353)** on October 16 allowing arbitrary filesystem access through AI file tools. Security researchers noted similar vulnerabilities exist in other agentic browsers including Fellou, suggesting this is a **systemic industry problem** affecting OpenAI’s Atlas and other AI-native browsers.

**Who’s involved:**

- **Perplexity:** Launched Comet to “millions” on waitlist while dealing with critical security disclosures; made browser free for all users October 2 (previously $200/month)
- **OpenAI:** Just launched Atlas browser October 21, likely faces similar security challenges given shared architecture
- **Brave, LayerX, security researchers:** Disclosed vulnerabilities responsibly, highlighting fundamental AI browser security gaps
- **Windsurf/Codeium:** Addressed path traversal vulnerability in AI coding environment
- **Users:** Anyone using AI browsers for sensitive tasks (banking, email, coding) at risk of data exfiltration
- **Browser Company (Dia), other AI browser startups:** Face same fundamental security design challenges

**Why it matters:**

- **Systemic architecture flaw:** AI browsers fundamentally struggle to separate user intent from malicious web content, unlike traditional browsers with clear same-origin policies
- **Same-origin bypass:** Vulnerabilities completely circumvent traditional web security protections that have evolved over 25+ years
- **Timing risk:** Atlas launched into market while Comet vulnerabilities were being disclosed, suggesting OpenAI may face similar issues
- **Adoption at scale:** Perplexity made Comet free for millions of users before security issues were resolved, maximizing potential harm
- **Trust crisis:** Early AI browser security failures could delay mainstream adoption and create regulatory pressure
- **Developer implications:** Builders integrating with AI browsers or building agentic features need new security frameworks

**What to watch:**
Whether OpenAI’s Atlas discloses similar vulnerabilities in coming weeks, Perplexity’s patch effectiveness and timeline, development of AI browser security standards and best practices, regulatory responses to AI browser vulnerabilities, whether traditional browser vendors (Chrome, Safari, Edge) use security concerns to slow AI browser competition, and emergence of security-focused AI browser alternatives.

---


## **Story 5: Citigroup AI Productivity Gains**

**What happened:**
Citigroup CEO Jane Fraser revealed on October 14 earnings call that AI deployment **frees up 100,000 hours of developer time per week** (equivalent to adding ~50 full-time developers annually per week saved). Nearly **180,000 employees in 83 countries** have access to Citi’s internal AI tools (Citi Assist, Citi Stylus, Citi Squad).

September launch: **agentic AI pilot for 5,000 employees** using Google Cloud Gemini and Anthropic Claude models to complete multi-step tasks with single prompt.

**Citi Stylus Workspaces** now uses agentic AI integrated with various systems.

Employees entered **6.5 million+ prompts** in first part of 2025. Company **mandated AI prompt training** (”Asking Smart Questions”) for 175,000 employees in September. **384 applications retired or replaced** so far in 2025.

**Who’s involved:**

- **Citigroup:** ~40,000 developers globally gaining 100,000 weekly hours through AI tools
- **Google Cloud:** Partnership providing Gemini models and Vertex AI infrastructure
- **Anthropic:** Claude models integrated into Citi’s platforms
- **Employees:** 180,000 users with AI access, 175,000 completed mandatory prompt training

**Why it matters:**

- **Quantified impact:** 100,000 hours/week = clear ROI metric for enterprise AI adoption
- **Scale demonstration:** Deployment across 180,000 employees in 83 countries proves enterprise AI viability
- **Agentic evolution:** Move from assistive AI to autonomous multi-step agents represents next adoption phase
- **Workforce transformation:** Mandatory prompt training signals AI literacy as core business skill

**What to watch:**
More results from 5,000-employee agentic AI pilot, 2026 investor day announcements on expanded AI transformation, whether other banks match Citigroup’s productivity gains (JP Morgan has already announced similar impact), and impact on hiring/workforce planning.

> How did Citi do this? There are no shorcuts. The way these big numbers get delivered is by diving in on the hard stuff around AI agents: context handling, graceful fallbacks, how we think about multi-agent conflict resolution. Step-by-step work task handling for agents with working memory. Establishing agentic decision scopes. And of course, evals (whatever anybody says). That’s the kind of work you need to do get Citi-scale results.
>
> Bottom line: AI agents that work are a function of architecture right now, not models. And few want to do the work of building architecture that’s required to harvest non-linear gains like this. For many organizations, blaming the models for their own failure to correctly construct agentic AI systems is easier!

---


## **Story 6: Meta AI Layoffs**

**What happened:**
Meta announced on October 22 that it will lay off **approximately 600 positions** within its AI division to “streamline operations and enhance efficiency.” The cuts affect Meta’s AI infrastructure including FAIR (Fundamental AI Research) and product-related roles, but **exclude TBD Labs** (high-profile AI recruits under Alexandr Wang).

The announcement came in a memo from Wang, Meta’s chief AI officer who joined in June as part of Meta’s $14.4 billion investment in Scale AI. Meta created Superintelligence Labs (led by Wang and former GitHub CEO Nat Friedman) following tepid reception to Llama 4 in April.

**Who’s involved:**

- **Meta:** Restructuring AI division under Wang’s leadership, total Superintelligence Labs now under 3,000 employees
- **Alexandr Wang (Scale AI):** Leading Meta’s AI direction as Chief AI Officer
- **Affected employees:** 600 staff from FAIR and AI infrastructure teams given severance packages
- **CEO Mark Zuckerberg:** Expressed dissatisfaction with Llama 4 progress, driving reorganization

**Why it matters:**

- **Strategic shift:** Meta protecting high-value recruits in TBD Labs while cutting existing teams signals confidence in new hires over incumbents
- **Resource competition:** Internal teams competing for GPU compute; layoffs consolidate resources under Wang’s control
- **Competitive pressure:** Meta racing to catch OpenAI/Anthropic after Llama 4 disappointment
- **Expense trajectory:** Meta projects 2026 expense growth rate exceeding 2025, signaling continued AI investment despite cuts

**What to watch:**
Llama 5 performance and reception, whether TBD Labs delivers breakthrough capabilities justifying restructuring, impact on Meta’s open-source AI strategy, and morale effects from protecting new hires while cutting veterans.

Honestly, the biggest elephant in the room is this: Can Zuck catch up? It’s unclear. At the moment, it looks like his issue isn’t talent. It’s strategy.

---


## HOT OFF THE PRESSES—Anthropic-Google Deal

On October 23, 2025, Anthropic announced a historic, multi-billion-dollar expansion of its partnership with Google Cloud, committing tens of billions of dollars to access Google’s latest TPU infrastructure for training future Claude models. This move sharply lowers barriers to entry by democratizing frontier compute capacity, fueling fierce competition with OpenAI’s reliance on Nvidia GPUs and Azure infrastructure.

By enabling access to Google’s scalable, purpose-built AI chips, this deal aims to break the traditional compute bottlenecks faced in both training and serving large language models, potentially ushering in a new era of more accessible, less congested AI model deployment.

For Anthropic, this means greater flexibility to rapidly iterate on larger, more sophisticated models. For the industry, it signals a pivotal shift toward open, diversified compute ecosystems that could diminish dominance of heavyweight hardware providers and usher in an era of more competitive, scalable model serving.

---


## Bonus Note: The Memory and Knowledge Launches

Both Anthropic and OpenAI launched major features focused around memory and company knowledge this week. I tested them. They are fairly recency-focused and fairly narrowly scoped in what they can search. They still represent a move in the direction that model makers want to go. I would expect to see much more significant releases here—behind the scenes, quietly extending the capabilities and the connections they can make to data in coming months.

This is infrastructure work. The initial releases are modest, but the architecture they’re building matters more than the current feature set. Keep an eye on this space. direction that model makers want to go. I would expect to see much more significant releases here, behind the scenes, quietly extending the capabilities and the connections that they can make to data in coming months.

This is infrastructure work. The initial releases are modest, but the architecture they’re building matters more than the current feature set. Keep an eye on this space.

[![](https://substackcdn.com/image/fetch/$s_!bhXJ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb36573ec-41d3-4b77-84ca-10452b893018_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!bhXJ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb36573ec-41d3-4b77-84ca-10452b893018_1024x1024.png)
