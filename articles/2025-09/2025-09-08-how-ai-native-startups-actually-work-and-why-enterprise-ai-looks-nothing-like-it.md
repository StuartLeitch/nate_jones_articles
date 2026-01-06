---
title: "How AI-Native Startups Actually Work (And Why Enterprise AI Looks Nothing Like It)"
author: "Nate Jones"
published: 2025-09-08
url: https://natesnewsletter.substack.com/p/how-ai-actually-works-at-startups
audience: everyone
scraped_at: 2026-01-05 19:18:31
---

*We’re all so busy trying to keep up with AI, we sometimes don’t stop to think.*

*As far as I know, no one has taken the time to study how AI adoption patterns are unfolding differently at small companies vs. large companies in detail—not with the goal of picking sides, but with the goal of understanding the underlying patterns and learning what it can tell us about where the AI revolution is going.*

*I've spent months looking for a thoughtful comparison of how AI actually works at small startups versus large enterprises. It doesn't exist. What we have instead are two parallel conversations that rarely intersect—startup founders describing their AI-native workflows as if enterprise constraints don't matter, and enterprise leaders discussing governance frameworks as if startup velocity isn't real.*

*The gap isn't from hostility; it's from living in different realities. When Dan Shipper at Every builds entire products through conversations with Claude, and Sarah at her 400-person SaaS company spends six months getting GitHub Copilot approved, they're both being rational. They're just optimizing for completely different things under completely different constraints.*

*I've been in both worlds. I've watched founders assign Linear tickets to AI agents that work overnight while they sleep. I've also watched enterprise teams build elaborate approval processes for AI tools while their developers secretly use ChatGPT through their browsers anyway. Both approaches make sense once you understand the context, but nobody's actually explaining that context or what each side could learn from the other.*

*What follows is that missing comparison. Here's what you'll find:*

1. ***How AI-native startups actually work** - Building through conversation, not code*
2. ***The enterprise reality** - Why 6 months for Copilot approval is sometimes the best option*
3. ***Technical stacks** - Specific tools, costs, and why they diverge*
4. ***Daily workflows** - From overnight AI agents to AI sprints*
5. ***Real costs** - $10-15K/month in credits vs. enterprise contracts*
6. ***5-minute quick starts** - What to do today, regardless of company size*
7. ***Culture shifts** - Code ownership, team dynamics, institutional memory*
8. ***Integration problems** - Greenfield vs. legacy from 2008*
9. ***What works** - Patterns that succeed everywhere*

*For enterprise readers who need more than quick starts, I've compiled an 88-page implementation guide that translates startup innovations into enterprise-ready approaches. It covers tools that pass security review, governance that enables rather than blocks, and change management that works with senior engineers who've seen every tech trend come and go. It's the detailed roadmap for organizations that can't just rebuild everything from scratch.*

*The reality is that both startups and enterprises have figured out important pieces of the AI puzzle. Startups understand velocity and possibility. Enterprises understand sustainability and scale. The future belongs to companies that can learn from both approaches. But first, we need to see clearly what's actually happening in each world, not the simplified versions we assume from the outside.*


## *[The Enterprise AI Implementation Guide](https://docs.google.com/document/d/1DVz6puGqp0NMw4UqwarnqQ9YGO1mYJ0wF7WB8-j1nZo/edit?usp=sharing)*

If you're reading this from inside a company with more than 50 employees, you know the reality: everything I described about AI-native startups sounds great until you remember you have SOX compliance, customer data that could sink the company if leaked, and a CTO who (rightfully) wants to know exactly what data is going where. You can't just cowboy your way into AI adoption when you have enterprise customers doing security audits and a board that expects predictable quarterly results. That's why I've put together this 88-page reference guide specifically for midsize and enterprise companies implementing AI.

It's not about moving fast and breaking things—it's about moving deliberately while nothing breaks. This guide covers the actual tools that pass security review, the governance frameworks that satisfy compliance without killing innovation, the change management approaches that work with senior engineers who've been burned by hype before, and the specific architectures that let you experiment safely while maintaining the stability your customers depend on.

Think of it as the translation layer between startup innovation and enterprise reality—taking what works from the AI-native world and adapting it to environments where "we'll fix it in production" isn't an option. Because the truth is, enterprises aren't slower at AI adoption because they're stupid or scared. They're slower because they're solving a fundamentally harder problem: transforming a flying airplane without crashing it.


# **How AI-Native Startups Actually Work (And Why Enterprise AI Looks Nothing Like It)**

I've been scrolling through endless articles on AI adoption, and they all seem to miss the same thing. They treat AI transformation like it's one phenomenon, as if a two-person startup in San Francisco and a 500-person company in Ohio are playing the same game. They're not. Not even close.

The gap hit me when I started comparing notes between founders building AI-first startups and product leaders trying to transform mid-market companies. The startups are running entire engineering workflows through Claude Code and Devin, treating AI agents like employees with Linear tickets and performance reviews. Meanwhile, the enterprises are... still debating whether to allow ChatGPT on the company network.

But here's what's interesting: both approaches make perfect sense once you understand the constraints they're operating under. The startup founder isn't being reckless, and the enterprise IT director isn't being overly cautious. They're responding rationally to completely different realities. And those realities shape everything—from the tools they choose to the way they think about what AI even is.

So I want to work through what I've been seeing, comparing these two worlds, because I think the lessons from each side are more nuanced than anyone's admitting. The startups have figured out things about AI velocity that enterprises need to learn. But the enterprises understand something about sustainable AI adoption that most startups are too rushed to notice.


## **The Reality of AI-Native Development**

Let me start with Dan Shipper, because his approach at Every captures something fundamental about how AI-native companies actually work. Every is technically a media company, but they've morphed into something more like an AI product lab. When Shipper builds features now, he doesn't open an IDE. He has a conversation with Claude Code about what he wants, and the feature emerges through dialogue.

This isn't him being lazy or cutting corners. It's a different philosophy of creation. He calls it "compounding engineering"—each feature you build with AI makes the next one easier, because the AI understands your codebase better, your patterns, your preferences. The code becomes a living thing that grows through conversation rather than keystrokes.

His team runs what they call Claude Code Camps. Non-engineers show up and ship production features. The head of marketing can now build product features. The operations lead creates internal tools. This would be unthinkable at a traditional company, but at Every, it's just Tuesday. They built their entire search product, Spiral, this way—using a stack of ChatGPT for initial coding, Clerk for authentication, Supabase for the database, Railway for hosting, and the Claude API for the AI functionality. Not a prototype—the actual product that customers pay for.

Claire Vo takes this even further at ChatPRD. She assigns Linear tickets directly to Devin, an AI agent that handles entire features autonomously. When I first heard this, I thought she was exaggerating. She's not. Devin works through the night, pushing code to staging for her review in the morning. When she finds issues, she doesn't fix them herself. She creates a new ticket explaining the problem and assigns it back to Devin or another agent.

Her stack is deliberately diverse: Cursor for backend API work and summaries, ChatGPT for quick conversions (like turning PDFs into .ics calendar files), Lovable for vibe-coding prototypes, and Gemini Flash specifically for video analysis in her podcast workflows. She uses MCP (Model Context Protocol) to connect these tools—her agents can query Segment data directly, bypassing Google Analytics entirely. The SQL queries happen through MCP connections, no dashboard needed.

The workflow looks bizarre from the outside. She'll check what Devin completed overnight, review the staging deploys, create tickets for issues, assign them to various AI agents, then move on to strategic work while the agents handle implementation. It's like managing a team, except half the team doesn't need sleep or salary negotiations.

This extends to how they validate ideas. Vo doesn't spend weeks on an MVP. She "vibe-codes" a prototype in Lovable or v0—describing the general vibe of what she wants and letting the AI figure out the details. An hour later, she has something real enough to show users. If they hate it, she's lost an hour. If they love it, she can build the real version, or more likely, just iterate on the prototype until it becomes the real version.

The code quality for a demo like that would horrify traditional engineers. Functions are too long. There's duplicate code everywhere. Abstractions are minimal. But when you can regenerate an entire component in seconds by describing what you want differently, code quality means something different. It's not about crafting perfect abstractions that will last for years. It's about solving today's problem as quickly as possible, knowing you can completely rewrite it tomorrow if needed.


## **The Enterprise Reality Check**

Now let me tell you about a product director I know at a 400-person B2B SaaS company. Let's call her Sarah. She's trying to integrate AI into their product, and her reality looks nothing like Shipper's or Vo's.

Sarah's first attempt was to get her team access to GitHub Copilot. Three months of security reviews. Another month of procurement negotiations. Two months of pilot testing with a small group. By the time it rolled out, half the team had already been using ChatGPT on their personal accounts anyway, copying and pasting code through their browsers, completely defeating the security review's purpose.

But here's the thing: Sarah's not being unreasonable. Her company handles healthcare data. They have SOX compliance requirements. They have enterprise customers who audit their security practices. One data leak through an AI tool, and they lose their biggest contracts. The stakes are fundamentally different from a startup that can pivot if something goes wrong.

When Sarah's team finally got AI tooling approved, it wasn't Devin or Claude Code. It was Azure OpenAI, locked down with specific data handling agreements, integrated through their existing Microsoft infrastructure. The developers can use it, but only through approved interfaces, with all prompts logged for audit purposes. It's AI with training wheels, guardrails, and a safety net.

The cultural challenge is even bigger than the technical one. Sarah's senior engineers have spent decades perfecting their craft. They've built sophisticated mental models of how software should be architected. Now they're being asked to delegate to an AI that makes mistakes they wouldn't have made as junior engineers. One senior developer told her, "I didn't spend 20 years learning to code just to become a prompt engineer."

She tried running AI workshops, bringing in consultants, creating innovation time for experimentation. But the adoption was sporadic. The junior developers loved it—they were shipping faster than ever. The senior developers used it occasionally, usually just for boilerplate code. Middle management was terrified it would make their teams redundant.

The successful adoptions in her company followed a pattern: they happened in pockets where there was already pain. The support team, drowning in tickets, embraced AI categorization and response drafting immediately. The QA team, perpetually behind, jumped on AI-assisted test generation. The documentation team, chronically understaffed, became AI power users within weeks. But the core product development team? Still debating whether AI-generated code meets their quality standards.


## **The Technical Stack Divergence**

The tool choices between these two worlds reveal their different priorities. Let me walk through the actual stacks I'm seeing, with the specific details that matter.

Startups are running what I call a "diversified chaos" strategy. They use routers—OpenRouter or Together AI—to dynamically switch between models. Claude Opus for deep research and complex reasoning (Shipper spawns parallel Claude agents for this), GPT-4 for quick coding tasks, Gemini Flash for anything multimodal, and open-source models like Llama 3.2 or Qwen for production where they need to control costs. They're not loyal to any provider; they're loyal to whatever works best for the specific task at hand.

The database layer is surprisingly consistent: Postgres with pgvector extension for vector embeddings, hosted on either Neon or Supabase. Not because it's trendy, but because it's pragmatic. You start with one database for everything, add vector search without a migration, and can scale pretty far before needing to specialize. Redis through Upstash handles caching and job queues. Media files go to AWS S3 or Cloudflare R2. As you scale, you might add Pinecone or Weaviate for specialized vector search, but most startups never need to.

The agent orchestration layer is where things get interesting. MCP (Model Context Protocol) has become the unexpected winner for connecting agents to tools and data. LangChain or Semantic Kernel handle the workflow orchestration and memory management. AutoGen comes in when you need true multi-agent collaboration. But here's the key: they start simple. Vo began with basic Linear integrations for Devin, then gradually built up to complex agent handoffs. Shipper started with single Claude calls, then evolved to spawning parallel agents with custom handoff libraries.

For observability, it's LangSmith and Helicone from day one. These aren't nice-to-haves; they're essential. When you're burning $10-15K per month in AI credits, you need to know exactly where every dollar goes. Which prompts are expensive? Which chains are inefficient? Which models are hallucinating? PostHog tracks user analytics, Sentry catches errors, and Braintrust provides deeper observability for complex chains.

The development stack is Next.js with TypeScript for full-stack apps, Tailwind with Shadcn components for UI, Prisma for database interactions. But the interesting part is how they build: Cursor for AI-assisted coding when they need control, Devin for autonomous feature development when they can specify clearly, Claude Code for complex refactoring and architectural work. For rapid prototyping, it's Bolt, v0, Lovable, or Replit—whatever gets them from idea to demo fastest.

Infrastructure runs on credits and simplicity. AWS Bedrock when they have startup credits, Vercel for Next.js hosting, Cloudflare for everything edge-related. Railway or Render for backend services. Supabase often handles auth, database, and real-time subscriptions in one package. Stripe for payments, always Stripe. The pattern is clear: minimize the number of services you need to understand and maintain.

Mid-market companies take the opposite approach: single-vendor depth. They pick Azure OpenAI or AWS Bedrock and build everything around it. Their database might still be Postgres, but it's probably on Azure Database or AWS RDS with enterprise support contracts. They add specialized vector databases like Pinecone not because they need the performance, but because it came as part of an enterprise AI platform bundle.

The development tools are more conservative: GitHub Copilot for code assistance (after those months of security review), existing IDEs with AI plugins rather than new AI-first editors. They might experiment with tools like Cursor in sandboxed environments, but production code still goes through traditional development workflows.


## **The Workflow Revolution**

The daily workflow differences between these environments reveal completely different philosophies of work. In AI-native startups, the boundary between thinking and building has essentially dissolved. When Shipper has an idea for a feature, he starts talking to Claude about it. That conversation becomes specification, which becomes code, which becomes the deployed feature—all in one continuous flow.

The specific workflow at Every looks like this: Shipper opens Claude Code, describes the feature he wants in natural language, references existing code patterns in their codebase, and lets Claude generate the implementation. He reviews it conversationally—"that's good but change X to Y"—rather than editing code directly. The feature gets deployed to Railway with a simple command. Total time from idea to production: often under an hour.

Vo's workflow with Devin is even more radical. She starts her morning by reviewing Devin's overnight work in Linear. The agent has been assigned tickets with detailed acceptance criteria and context about the codebase. Devin works through them, commits code to feature branches, and updates ticket status with implementation notes. When it gets stuck, it adds comments explaining what it tried and what's blocking it.

Her prompt templates for Devin are elaborate and worth understanding. They include: project context, codebase conventions, common patterns to follow, libraries to prefer, and even tone for code comments. She's essentially training Devin to be a team member who understands not just what to build but how to build it in a way that fits with everything else.

But this workflow depends on a tolerance for imperfection that most enterprises can't afford. The dashboard that founder built during a user call was functional but not production-ready. It handled the happy path perfectly but would probably break under edge cases. The database queries weren't optimized. The error handling was basic. For a startup with 10 customers, that's fine—they can fix issues as they arise. For an enterprise with 10,000 customers, that's a disaster waiting to happen.

The enterprise workflow remains more structured, and there are good reasons for this. They use AI to accelerate existing processes rather than replace them. A developer might use Copilot to write unit tests faster, but those tests still go through code review. A product manager might use ChatGPT to draft requirements, but they still go through stakeholder review. AI becomes a productivity tool rather than a transformation agent.

Sarah's team found a middle ground that's interesting. They created what they call "AI sprints"—one-week periods where they throw normal processes out the window and build like a startup. No code reviews, no lengthy specifications, just rapid building with AI assistance. At the end of the week, they demo everything, pick the best ideas, and then rebuild them properly for production. It gives them startup-style velocity in controlled bursts without sacrificing their production standards.


## **The Cost Reality**

Nobody talks honestly about the economics of AI-native development, so let me put some real numbers on the table. Vo's team burns through $10,000-15,000 per month in AI credits. Shipper's closer to $8,000. These aren't huge companies—they're small teams shipping products that compete with much larger competitors.

The breakdown is illuminating. About 40% goes to production inference—actual user-facing AI features. Another 30% goes to development—all those conversations with Claude Code, iterations with Devin, experiments that don't work out. 20% is pure experimentation and learning. The last 10% is usually "what the hell happened here"—runaway chains, infinite loops, that one time someone accidentally had GPT-4 analyze their entire codebase repeatedly for six hours.

At first glance, that seems insane. You could hire a junior developer for that. But that's the wrong comparison. That $10,000 is giving them the equivalent of 3-4 developers working 24/7, never taking breaks, never needing onboarding, never having bad days. The velocity math works out overwhelmingly in AI's favor.

But there's a hidden cost that startups don't talk about: the technical debt accumulation is massive. When you can regenerate any component in minutes, you stop thinking about long-term architecture. When AI can refactor anything instantly, you stop worrying about code organization. This works until it doesn't. I've seen startups hit a wall where the AI can no longer understand their codebase because it's become such a mess of AI-generated spaghetti.

One founder told me about hitting this wall at around 100,000 lines of code. The AI started making increasingly bizarre suggestions, unable to understand the patterns it had created. They had to stop feature development for a month and manually refactor with human developers to create some conceptual clarity. It was like the code had developed dementia.

Enterprises have the opposite problem. They're so worried about technical debt that they're barely accumulating any code at all. Sarah's team spent six months on an AI implementation that a startup would have shipped in a week. But their version handles edge cases, has proper error handling, includes comprehensive tests, and integrates with their existing monitoring. It's bulletproof where the startup version is held together with hope.


## **The 5-Minute Quick Action Guide**

If you're reading this and want to experiment with AI-native development, here's what you can do in the next five minutes to get started:

**For Startup Founders:**

1. **Right now:** Sign up for Claude Code (claude.ai) and OpenRouter (openrouter.ai). You need both—Claude for deep work, OpenRouter for model flexibility.
2. **First prompt:** Take your current biggest technical problem and describe it to Claude in plain English. Don't write requirements; have a conversation. "I need a dashboard that shows user activity over time, pulls from our Postgres database, and updates in real-time."
3. **First integration:** Connect one AI agent to your workflow today. If you use Linear, create a label called "AI-Ready" and write one ticket as if you're assigning it to a junior developer. Try assigning it to Devin (devin.ai) or continue the conversation with Claude.
4. **First measurement:** Install Helicone (helicone.ai) or LangSmith. Every AI call should be traced from day one. You'll burn money fast without visibility.
5. **First experiment:** Take your next feature request and try building it entirely through AI conversation before writing any code manually. Time it. Compare to your normal process.

**For Enterprise Teams:**

1. **Right now:** Create an AI sandbox—a separate environment with non-production data where your team can experiment without compliance concerns.
2. **First safe bet:** Start with your documentation. Have your best technical writer spend 5 minutes with ChatGPT turning meeting notes into technical specs. Low risk, immediate value.
3. **First integration:** If you have Azure, enable Azure OpenAI. If you have AWS, enable Bedrock. Use your existing vendor relationships—you probably already have credits you don't know about.
4. **First champion:** Identify your most overwhelmed team (usually QA or support). Give them a $500/month AI budget and freedom to experiment. They'll become your internal evangelists.
5. **First metric:** Track time-to-first-line-of-code for new features. Not time to ship, just time to start building. Watch how AI changes this number.

**For Everyone:**

The meta-action: Stop thinking about AI as a better autocomplete. Start thinking about it as a junior team member who never sleeps, never complains, and gets smarter every week. That mental model shift matters more than any specific tool.


## **The Cultural Transformation**

The cultural differences run deeper than just risk tolerance. AI-native startups have developed entirely new cultural norms around creation and ownership. At Every, nobody "owns" code anymore. The code is communal, constantly being rewritten by whoever needs to change it, with AI as the medium of change. There's no ego in implementation because implementation has become commoditized.

This creates interesting dynamics. Shipper told me about a feature that three different people had rewritten completely in the span of a week, each time to add their own functionality. In a traditional environment, this would cause conflicts—people would feel their work was being disrespected. At Every, it's just iteration. The code is disposable; the functionality is what matters.

The flip side is that institutional knowledge becomes fragmented. When I asked how they onboard new developers, Shipper laughed. "We point them to Claude and tell them to start asking questions." The AI has become the institutional memory, the documentation, and the onboarding process all in one. It works, but it's fragile. If they ever had to switch AI providers, they'd lose not just a tool but their entire organizational memory.

Enterprises can't operate this way, and honestly, they shouldn't try. They have different cultural strengths that AI can amplify rather than replace. Sarah's team has deep domain expertise in healthcare workflows that no AI currently understands. They have relationships with customers that span decades. They have hard-won knowledge about edge cases that only appear at scale.

The successful enterprise AI adoptions I've seen acknowledge these strengths. They use AI to amplify human expertise rather than replace it. A senior developer with 20 years of experience becomes even more valuable when they can implement their ideas 10x faster with AI assistance. A product manager who deeply understands customer needs becomes more powerful when they can prototype solutions in hours instead of weeks.

But this requires a different kind of cultural change. It's not about making everyone an AI user; it's about making AI invisible. The best enterprise implementations I've seen hide the AI entirely. The support team doesn't think they're using AI; they just notice their ticket system got smarter. The QA team doesn't prompt engineer; they just find their test coverage improved.


## **The Talent Equation**

The talent implications of AI-native development are profound and underdiscussed. Startups are hiring differently now. Vo told me she no longer looks for coding ability in junior hires. She looks for clear thinking and good taste. "I can teach anyone to prompt engineer in a day," she said. "I can't teach them to know what good looks like."

This is creating a new class of technical workers—people who can build software but can't necessarily code. They understand systems, architecture, user experience, but they implement through conversation with AI rather than through writing code. It's like the difference between an architect and a construction worker, except the AI is doing the construction instantly.

Traditional engineers often hate this. They see it as a devaluation of their craft. And they're not wrong—traditional coding skills are becoming less valuable in purely economic terms. But what's becoming more valuable is the ability to think systemically, to understand complex interactions, to debug at a conceptual level rather than a syntax level. The engineers who thrive in this new world are the ones who were always more interested in solving problems than writing code.

Enterprises face a different talent challenge. They have teams of engineers with deep technical skills who need to transform into AI orchestrators. It's not just a skill change; it's an identity change. Sarah described it as "asking Formula 1 drivers to become traffic controllers." They have the domain knowledge, but the job has fundamentally changed.

The successful transformations I've seen create hybrid roles. Senior engineers become AI architects, designing systems that AI implements. Junior developers become AI trainers, creating the examples and patterns that AI learns from. Product managers become AI conductors, orchestrating multiple AI agents to deliver features.

But there's also a talent exodus happening that nobody talks about. The most ambitious engineers are leaving enterprises for AI-native startups, not for better pay, but for the ability to build at AI speed. One engineer told me, "I can build more in a weekend at a startup than I built in a year at my last company." The velocity is addictive.


## **The Quality Question**

Let's address the elephant in the room: AI-generated code is often terrible. It's verbose, repetitive, and filled with subtle bugs. It confidently implements antipatterns. It occasionally hallucinates entire libraries that don't exist. Anyone who says otherwise is selling something.

But here's what I've learned: it doesn't matter as much as we think it does. The startups shipping AI-generated code aren't succeeding because the code is good. They're succeeding because they can iterate so fast that quality becomes an emergent property rather than a designed one.

Vo explained it this way: "We ship broken things quickly, see how they break, then fix them even more quickly. By the time a traditional team would have shipped v1, we're on v20." The broken versions that users never see don't matter. The rapid convergence on something that works does.

This is antithetical to enterprise software development, where the first version needs to work reliably for thousands of users. Sarah's team can't ship something that might break; their customers depend on their software for critical operations. So they use AI differently—for exploration and prototyping, but not for production code without significant human review.

The quality gap is closing though. Each new generation of AI models produces notably better code. Claude 3.5 writes code that's markedly better than Claude 3. GPT-4 understands architectural patterns that GPT-3.5 couldn't grasp. At the current rate of improvement, we're probably 18 months from AI-generated code being indistinguishable from human-written code for most applications.

But I think focusing on code quality misses the bigger point. The value isn't in the code; it's in the ability to explore solution spaces rapidly. AI allows you to try 20 different approaches in the time it would take to implement one traditionally. Most will be wrong, but you learn something from each failure. The winners aren't the ones who write the best code; they're the ones who find the right solution fastest.


## **The Integration Challenge**

One pattern I keep seeing: the hardest part isn't getting AI to work; it's getting it to work with everything else. Startups have it easy here—they're building greenfield, so they can design their entire system around AI from the start. Everything is API-first, documentation-light, AI-friendly.

Enterprises are trying to integrate AI into systems built over decades, with complex dependencies, undocumented behaviors, and fragile integrations. Sarah's team spent three months just figuring out how to get AI-generated code to work with their legacy authentication system. The AI kept suggesting modern patterns that were incompatible with decisions made in 2008.

The successful enterprise integrations I've seen take a strangler fig approach—they wrap existing systems with AI-friendly interfaces, then gradually replace the internals. One company built what they called an "AI translation layer"—a service that converts between their legacy systems and modern AI tools. It's not elegant, but it works.

The data integration is even messier. Startups design their data schemas to be AI-readable from the start. They use clear naming conventions, consistent patterns, extensive comments. Enterprises are working with databases that have columns named things like "custID\_v2\_final\_REAL" because of migrations from 15 years ago. The AI takes one look and hallucinates.

I've seen enterprises succeed by creating "AI views" of their data—cleaned, normalized, documented versions specifically for AI consumption. It's duplicate work, but it's the only way to make progress without rebuilding everything. One CTO told me, "We're essentially building a parallel universe where everything makes sense, then slowly migrating reality to match it."


## **The Practical Stack Details**

Let me give you the specific details of what's actually working in production, because the implementation details matter more than the high-level strategy.

**For voice and video work**, the stack is surprisingly consistent: Deepgram for speech-to-text (better accuracy than Whisper for real-time), ElevenLabs for text-to-speech (most natural voices), LiveKit for WebRTC streaming, and Twilio for telephony integration. Vo specifically uses Gemini Flash for video analysis in her podcast workflows—it can transcribe and summarize hour-long videos in seconds. For programmatic video generation, Remotion is the winner, letting you write React components that become videos.

**Authentication and payments** are solved problems: Clerk or Supabase Auth for authentication (Clerk if you want it done for you, Supabase if you want control), Stripe for payments (always Stripe, don't overthink this). The interesting part is how AI companies are using these—Shipper has Claude generate Stripe integration code that handles complex subscription logic he would have spent days implementing manually.

**For productivity and automation**, the stack depends on team size. Solo founders live in Notion with AI plugins, use Zapier or Make for automation, and manage everything through Linear (which has the best AI agent integrations). Larger teams add Slack with custom AI bots, Framer for marketing pages (AI can generate these directly), and increasingly sophisticated automations. Vo has entire workflows where Zapier watches for new Linear tickets, triggers Devin, which updates Slack when done.

**The development environment** is where the real innovation is happening. Cursor has become the default for AI-assisted coding when you want to maintain control—it's VS Code with deep AI integration. For autonomous development, Devin is the clear winner for complete features, while Claude Code excels at refactoring and architectural work. The low-code tools—Bolt, v0, Lovable, Replit—each have sweet spots. v0 for UI components, Lovable for complete apps, Bolt for interactive prototypes, Replit for full-stack applications with hosting included.


## **The Governance Gap**

The governance challenges are where the startup and enterprise worlds diverge most dramatically. Startups have essentially no governance. Vo admitted to me that she has no idea what data has been sent to which AI providers. "We probably should track that," she said, "but we're too busy shipping." This is terrifying from an enterprise perspective but liberating from a startup perspective.

Enterprises are building elaborate governance frameworks—prompt libraries, approval workflows, audit trails. Every AI interaction is logged, reviewed, and archived. They have committees to approve new use cases. They have training programs on responsible AI use. It's thorough, careful, and incredibly slow.

But unexpected governance patterns are emerging. Some startups are building in governance from the start, not because they have to, but because it makes the AI work better. Shipper showed me their prompt versioning system—every prompt is tracked, versioned, and measured for effectiveness. It started as an optimization tool but became a de facto governance system.

Meanwhile, some enterprises are creating "governance-free zones"—sandbox environments where teams can experiment without restrictions. Sarah's company has an "AI playground" where developers can try anything as long as it doesn't touch production data. It's become their most valuable learning environment.

The regulatory landscape is forcing everyone to think about governance differently. European companies are already adapting to AI regulations that American companies are just starting to consider. One founder told me they're building their entire AI system to be "regulation-ready"—able to comply with whatever rules emerge. It's constraining in the short term but might be an advantage long term.


## **What Actually Works**

After all this analysis, let me tell you what actually works. The successful AI adoptions, whether startup or enterprise, share some common patterns that transcend their differences.

First, they all start with pain. The teams that successfully adopt AI are the ones that have a specific, acute problem that AI can solve. Vo started using AI because she was drowning in product requirements. Shipper adopted it because he needed to ship faster than his competition. Sarah's successful adoptions happened where teams were overwhelmed. Without real pain, AI becomes a toy rather than a tool.

Second, they iterate in public. The successful teams ship their AI experiments where users can see them, get feedback, and improve quickly. They don't spend months perfecting things in private. Even enterprises are learning to do this—Sarah's team now has a "beta" section of their product where AI features appear first, with clear warnings about experimental status.

Third, they measure differently. Traditional metrics like code coverage or performance benchmarks matter less than velocity metrics. How fast can you go from idea to deployed feature? How quickly can you respond to user feedback? How many experiments can you run per week? The teams winning with AI optimize for learning speed over execution quality.

Fourth, they build AI-first workflows rather than AI-enhanced workflows. The difference is subtle but crucial. AI-enhanced means taking your existing process and adding AI to parts of it. AI-first means redesigning your process around AI capabilities. Vo doesn't write specifications that AI implements; she has conversations that become specifications and implementations simultaneously.

Fifth, they accept imperfection as a feature, not a bug. The successful teams have learned that 80% solutions shipped today beat 100% solutions shipped next quarter. They've internalized that perfect is the enemy of good enough, and AI makes good enough achievable in hours instead of weeks.


## **The Future State**

Looking forward, I see these two worlds—startup and enterprise—beginning to learn from each other in interesting ways. Startups are starting to realize they need some governance and structure as they scale. Enterprises are recognizing that their careful approach might be causing them to miss the AI revolution entirely.

The next generation of tools is being built for this convergence. I'm seeing AI platforms that combine startup-style velocity with enterprise-grade governance. They let you move fast while maintaining audit trails. They enable experimentation while ensuring compliance. They're trying to give you the best of both worlds.

But I think the bigger change is conceptual. We're moving from thinking about AI as a tool to thinking about it as a medium. Just as the internet wasn't just a faster way to send mail but became an entirely new medium for human interaction, AI isn't just a faster way to write code—it's becoming a new medium for creating software.

The companies that understand this shift will thrive. They won't just use AI to do their existing work faster; they'll reimagine what work means in an AI-saturated environment. They'll build organizations that are native to this new medium rather than adapted to it.

The startups have an advantage here—they're already native. But enterprises have their own advantages—resources, customers, domain expertise—that could be decisive if they can figure out how to leverage them in this new world. The winners won't be the ones who are most aggressive or most careful with AI. They'll be the ones who best understand their own constraints and opportunities, and design their AI adoption accordingly.


## **The Personal Reality**

Let me end with something personal, because I think it matters. I've been building with AI for the past year, and it's changed how I think about creation in ways I'm still processing. I used to take pride in crafting elegant code, in understanding every line of what I built. Now I often don't fully understand the code running in production—I understand what it does, but not always how.

This was disturbing at first. It felt like cheating, like I was pretending to be technical while actually being something else. But I've come to realize that I'm not becoming less technical; I'm becoming differently technical. I'm operating at a higher level of abstraction, thinking in systems and behaviors rather than syntax and functions.

The founders I've talked to describe similar transitions. They're not coding less; they're coding differently. They're not building less; they're building more. They're not less technical; they're technical in a new way that we don't quite have words for yet.

This transition is hard, especially for those of us who built our identities around traditional technical skills. But it's also liberating. I can build things now that I could only dream about before. I can explore ideas that would have taken months to validate. I can create at the speed of thought rather than the speed of typing.

The enterprise folks going through this transition have it harder in some ways. They have more to unlearn, more identity to reconstruct. But they also have something valuable—the wisdom to know what actually matters. They understand that technology is only useful insofar as it serves human needs. They know that the hardest problems aren't technical but organizational. They have the maturity to adopt AI thoughtfully rather than frantically.


## **The Real Lesson**

If there's one thing I've learned from comparing these worlds, it's that there's no single right way to adopt AI. The startup approach works for startups because they're optimizing for learning and velocity in an uncertain environment. The enterprise approach works for enterprises because they're optimizing for reliability and scalability in a complex environment.

The mistake is trying to copy the wrong model. I see enterprises trying to move at startup speed and burning out their teams. I see startups trying to implement enterprise governance and grinding to a halt. The successful adoptions happen when organizations understand their own context and design their AI strategy accordingly.

But there's also a meta-lesson here about technological change. We're in a moment where the old rules don't quite apply but the new rules haven't been written. The startups are writing those rules through experimentation. The enterprises are testing which rules can bend and which will break. Both are necessary for us to collectively figure out how to build in this new world.

The founders I've talked to aren't just building products; they're building the patterns that everyone will use in five years. The enterprise leaders aren't just being careful; they're establishing the governance frameworks that will keep AI development sustainable. We need both the cowboys and the shepherds, the explorers and the settlers.

What we don't need is more generic advice about AI adoption. We need specific, contextual, honest accounts of what works and what doesn't, for whom and under what circumstances. We need to stop pretending there's a playbook and start admitting we're all figuring this out as we go.

The AI-native startups have something to teach us about velocity and possibility. The enterprises have something to teach us about sustainability and responsibility. The future belongs to those who can learn from both, adapting the lessons to their own context rather than blindly copying either model.

We're not just adopting a new technology. We're developing a new way of creating, a new relationship with our tools, a new understanding of what it means to build. The companies that recognize this—whether startup or enterprise—are the ones that will define the next decade of software development.

[![](https://substackcdn.com/image/fetch/$s_!xuhp!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F21eea1de-916e-4d0e-8c81-e2b1861a71f4_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!xuhp!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F21eea1de-916e-4d0e-8c81-e2b1861a71f4_1024x1024.png)
