---
title: "Cold applications have a <2% response rate now + the warm path system that replaces them (includes a guide and prompts!)"
author: "Nate Jones"
published: 2026-01-29
url: https://natesnewsletter.substack.com/p/cold-applications-have-a-2-response
subtitle: "Watch now | For twenty years, we’ve had a specific relationship with the platforms that hold our data: we log in, we scroll, we click buttons, and we accept whatever interpretation of our informati..."
audience: everyone
scraped_at: 2026-01-29 12:00:19
---

For twenty years, we’ve had a specific relationship with the platforms that hold our data: we log in, we scroll, we click buttons, and we accept whatever interpretation of our information the platform chooses to show us. LinkedIn shows us a feed. Spotify shows us a playlist. Our bank shows us transactions sorted by date. We are, in effect, passive consumers of our own data, seeing only what product teams decided we should see—and never questioning whether those decisions serve our interests or theirs.

That era is ending.

The unlock is simple to state and profound in implication: you can now export your data from almost any major platform and ask your own questions of it. Not the questions the platform wants you to ask, not the questions that optimize for their engagement metrics or premium tier conversions, but your questions—the ones they’d never build a button for. This capability changes everything about how individuals relate to the platforms that have, until now, held all the analytical power.

I want to show you what this looks like in practice, not as an abstract concept but as a working system you can deploy on your own data tonight. The example is LinkedIn, because professional networks are where the stakes are highest right now, but the principle extends everywhere. Once you see the pattern, you can’t unsee it.

**Here’s what’s inside:**

- **The warm path I’d never have found.** How I used my own LinkedIn data to surface a second-degree connection to a company where I had zero obvious ins—and why LinkedIn will never build this feature.
- **What LinkedIn won’t tell you.** The specific insights they could surface tomorrow but won’t: relationship decay, reciprocity imbalances, who would actually vouch for you, and dormant conversations with built-in re-engagement hooks.
- **Six analyses that change how you navigate 2026.** Relationship half-life, the reciprocity ledger, vouch scores, resurrection opportunities, network archetypes, and dynamic warm path discovery—each mapped to a concrete job-search action.
- **Cowork vs. ChatGPT for this work.** Why folder-level access and persistent state matter, plus lightweight prompts designed for ChatGPT’s constraints.
- **A quick guides, prompts, and a sample dashboard template.** Everything you need to run this analysis on your own data tonight.


## **A warm path I’d never have found manually**

A few weeks ago I decided to stress-test a methodology I’d been building. The question was whether I could find a warm path to a company where I had no obvious connection, so I picked Dactyl AI, a Series B robotics startup working on dexterous manipulation. I have no particular interest in working there—it was chosen specifically because it sits at the edge of my network, the kind of company where you could scroll through your LinkedIn connections for twenty minutes and come up empty.

The old approach would be to open LinkedIn, search for the company name, hope someone I knew worked there or had a relevant connection, and if not, resort to cold outreach. That approach has a success rate approaching zero for niche companies. The new approach looks different: export my LinkedIn data, run it through an analysis framework I built, and ask a question LinkedIn’s interface would never let me ask—who in my network is most likely to know someone at Dactyl AI or a similar company, weighted by both domain relevance and the actual strength of my relationship with them?

The system found a path I never would have discovered manually. Not a direct connection, because I don’t have one, but a second-degree path through someone I’d had substantive conversations with over the past year, who runs a company in an adjacent space, who likely shares investors and conference circuits with Dactyl’s founders. The combined relevance-plus-warmth score put him at the top of the list, and a warm introduction through him would be worth more than fifty cold applications.

LinkedIn has all the data to surface this kind of insight. They have my message history, my connection graph, the industry classifications, the company relationships. They could build this feature tomorrow. They never will—because if they did, you’d realize how little you need their premium tier. The value isn’t in their interface; it’s in your data, analyzed on your terms.


## **What LinkedIn knows but won’t tell you**

Let me get specific about what LinkedIn won’t tell you. This isn’t abstract criticism—these are concrete features they could build and have chosen not to.

Consider someone you connected with three years ago. Maybe you met at a conference, had a great conversation, exchanged contact info, connected on LinkedIn, perhaps even had a few message exchanges afterward. Then life happened, you both got busy, and the thread went quiet. LinkedIn shows that person as a “connection” with zero distinction between them and someone you talked to yesterday—both are just names in a list, blue dots, functionally equivalent.

But they’re not equivalent at all. The person you messaged yesterday is warm; the person you haven’t spoken to in three years is cold, maybe even colder than a stranger, because reaching out after years of silence carries an awkwardness that a fresh introduction doesn’t. Relationships decay over time—they have half-lives, and every week that passes without contact erodes the relationship’s strength a little more. LinkedIn has all the data to model this decay, including message timestamps, interaction frequency, and gaps in communication, yet they’ve never built anything that surfaces it. They could show you a relationship health score that updates in real-time, but they never will.

Here’s a simple accounting question: how many people have you endorsed on LinkedIn, and how many of those people have endorsed you back? LinkedIn knows the answer. They won’t tell you.

When I went through my own data, I discovered I’ve endorsed 47 people over the years, and only 12 have endorsed me back—a 25% reciprocity rate. Knowing that changes how I think about those relationships: the people who reciprocated are engaged and invested, while the people who didn’t might just be busy, or they might be takers. The same pattern holds for recommendations. I’ve written eight; I’ve received three. That imbalance tells me something important about who would actually go to bat for me versus who was happy to receive my support without offering anything in return.

This is basic relationship accounting, the kind of thing every sales team in the world tracks. LinkedIn has the data and hides it from you, probably because if you knew who actually reciprocated, you’d stop randomly endorsing people hoping for social proof—and endorsement activity is engagement they want to keep high.

The question that matters most if you’re job searching is who would actually vouch for you. Not who technically can, since anyone can write a recommendation, but who would—who would drop what they’re doing to take a call from a hiring manager asking about you? Answering that requires combining multiple data sources: Have they recommended you before? Have you had deep message conversations, or just surface-level pleasantries? How recently have you interacted? Did you work at the same company, meaning they’ve actually witnessed your work?

LinkedIn has all of this data and could compute a vouch likelihood score for every connection. Instead, they show you a list of skills with checkmarks from people you may or may not remember.

If you go through your LinkedIn messages right now, you’ll find conversations where you said “let’s catch up soon!” and never did, conversations where someone asked for your help and you said you’d look into it and then forgot, conversations where you asked for help and they said they’d check and then disappeared. These dormant threads are warm leads with built-in conversation starters—”Hey, we said we’d catch up six months ago, want to finally grab that coffee?” is infinitely easier than cold outreach. LinkedIn could surface these resurrection opportunities automatically, but they never will, because dormant relationships don’t generate feed activity, and feed activity is what they optimize for.


## **Why the stakes are higher in 2026**

Why does this matter more right now than it ever has before?

The job market in 2026 is fundamentally different than it was even two years ago. Cold applications have become nearly worthless: AI screening tools scan resumes in milliseconds, companies receive hundreds or thousands of applicants per posting, and the response rate for cold applications at competitive companies hovers below 2%. You’re not being rejected by humans anymore—you’re being rejected by algorithms before a human ever sees your name.

The warm path, meaning someone who can actually walk your resume to a hiring manager and say “I know this person, they’re good, you should interview them,” is worth more than ever. It’s not just valuable; it’s increasingly required to even get consideration. But warm paths decay. That person who would have happily made an intro for you last year might hesitate if you haven’t talked to them in twelve months, because the relationship has cooled and the social capital has eroded. If you’re not actively measuring your network health—if you don’t know which relationships are warm, which are cooling, and which have already gone cold—you’re navigating the 2026 job market with outdated information about your most valuable asset.


## **Six analyses LinkedIn will never build**

Network Intelligence runs six analyses that LinkedIn will never build for you, each designed to surface something the platform’s interface deliberately obscures.

The first is relationship half-life, which models decay using actual half-life mathematics—the same formula used for radioactive decay. Relationship strength at time T equals initial strength times 0.5 raised to the power of T divided by half-life, and the default half-life is set at 180 days, meaning a relationship with no recent activity loses half its strength every six months. But that’s just the baseline. The half-life gets modified based on behavioral signals: shared company history adds 90 days because you worked together and have shared context that decays more slowly, deep message threads with multiple back-and-forth exchanges add 60 days because real dialogue creates stronger bonds, and shallow interactions like “congrats on the new job!” actually subtract 60 days because they signal the relationship isn’t substantive. The output is a real-time relationship strength score for every connection, constantly updating based on your last interaction.

The reciprocity debt ledger applies simple accounting to your professional relationships. Every recommendation you’ve written earns 5 points given, every endorsement earns 1 point, and the same calculation runs for what you’ve received. Your net score with each person reveals the balance: positive means they owe you because they’ve received more from you than they’ve given, making them your “ask list,” while negative means you owe them and should give first if you want to strengthen the relationship before requesting anything.

The vouch score predicts who would actually advocate for you if asked by combining multiple signals into a single score from 0 to 100. Message depth contributes up to 40 points based on conversation length and substance, recency adds 20 points for interaction within the last six months or 10 points for six to twelve months, recommendations they’ve written for you add 20 points each, every three endorsements adds 10 points, and shared company tenure contributes 15 points. A score above 80 means this person would probably write you a reference letter tomorrow if you asked, while below 30 means they might not remember your name without checking your profile first.

Conversation resurrection uses pattern matching on your message history to find dormant conversations with specific re-engagement hooks, flagging threads where you said “let’s catch up” and never followed through, where someone asked for help and you didn’t respond, where you asked for help and they never delivered, or where a job change creates a natural re-entry point. Each of these represents a warm lead with a built-in conversation starter.

Network archetype classification sorts you into one of five types based on your connection patterns. Thought Leaders have high inbound connection rates and often work in content-creation or speaking roles. Insiders have dense connections within a few companies and deep institutional knowledge. Connectors spread wide across many unique companies with high bridging potential. Climbers show high senior-title density—VP, C-suite, Director. Builders concentrate in startups and early-stage companies. Your archetype determines your optimal strategy: a Climber should focus on executive referrals because they have access to decision-makers, while a Connector should trade introductions because their value lies in their bridging position. Knowing your archetype prevents you from following generic networking advice that doesn’t fit your actual network shape.

Warm path discovery is the dynamic feature that makes the rest actionable. Given any target company, it ranks your connections by combined relevance and warmth, where relevance scoring considers direct connections, domain keywords, work at adjacent companies, and founder or investor roles in the space, while warmth comes from the vouch score and relationship strength calculations. The key insight from real testing is that for niche companies, relevance matters more than warmth—if you’re trying to reach a robotics startup, someone warm but irrelevant can’t help you, while someone relevant but lukewarm is far more valuable. The combined score weights relevance at 70% for niche targets, shifting the balance for well-known companies where more paths exist.


## **Cowork vs. ChatGPT for this work**

If you want to run this analysis yourself, you’ll face a choice between Claude Cowork and ChatGPT. Both are capable tools, but they’re architecturally different in ways that matter enormously for this specific task, and understanding those differences will save you hours of frustration.

Cowork’s killer feature is folder-level access, which means I can point it at my entire LinkedIn data export directory—seven files containing thousands of records—and it sees everything simultaneously. This isn’t merely a convenience; it’s fundamental to the quality of analysis you can run, because the best insights come from combining data across files. Calculating vouch scores requires connections data, message data, and endorsement data in the same context. Finding warm paths means correlating relationship strength with company information and message history. Identifying resurrection opportunities requires cross-referencing conversation patterns with connection metadata. In Cowork, I write one prompt and it has full context across all of these sources, with no juggling, no uploading files one at a time, and no running out of context window because half of it got consumed by manually uploaded file contents.

Cowork also maintains state across a conversation, which transforms how you can work with the analysis. When I calculate vouch scores in message one, those scores persist, so when I ask “now find my warm path to Dactyl AI” in message two, it remembers everything we’ve already computed. I can iterate freely—saying “actually, let’s weight recency more heavily” triggers a re-run without re-uploading anything—and I can build complex analyses across multiple turns, with each turn building on the last. This persistence is the difference between a one-shot tool and an actual working environment where you can adjust parameters, refine the model, and explore different angles without starting over.

Cowork also handles heavy computation without timeout anxiety because it runs in a local environment. I can ask it to process 15,000 messages, which is what my LinkedIn export actually contains, and it won’t stop halfway through. It writes intermediate files, checkpoints its work, and can resume if something breaks. Heavy message analysis—parsing thousands of conversations for NLP patterns, extracting “let’s catch up” promises, identifying help requests—is computationally intensive, and in a cloud-based session with time limits, this kind of processing carries real risk of failure.

ChatGPT has genuine constraints for this use case. It requires individual file uploads, and each file competes for context window space, so if you upload all seven LinkedIn export files—connections, messages, endorsements, positions, recommendations, profile, skills—you’ve consumed a massive chunk of your context before you even ask a question. This forces strategic tradeoffs: which files are essential for this specific analysis, can you pare down the data before uploading, and are you willing to sacrifice context in some areas to preserve it in others?

I hit timeout issues myself while testing—perfectly good prompts with correct logic simply stopped partway through, returning partial results and forcing me to start over. The message-intensive analyses are especially risky because the computation takes longer than session limits allow. And every new ChatGPT conversation starts fresh: the warm path calculation from yesterday is gone, the vouch scores computed earlier aren’t available, and if you want to analyze a new target company today, you’re re-uploading files and re-parsing connections from scratch. What takes one session in Cowork might require three in ChatGPT.

None of this is a dealbreaker—it’s a design constraint to work within. For ChatGPT users, I built lighter prompts specifically around these limitations. Part 1 uses four core files instead of seven and runs four analyses: reciprocity, archetype, concentration, and senior contacts. Part 2 handles the message-intensive work separately: depth scoring, resurrection scanning, and vouch calculations. A standalone warm path prompt handles dynamic company queries with minimum required files. All three prompts avoid timeout by producing structured markdown instead of JavaScript visualizations, and they work within ChatGPT’s constraints while requiring more orchestration on your end.

If you have Cowork access, use it—one prompt gives you full analysis with persistent state and no timeout anxiety. If you’re on ChatGPT, the lightweight prompts are designed for the constraints and they work.


## **The real unlock is bigger than LinkedIn**

What we’re doing here—analyzing our own LinkedIn data to surface insights the platform won’t show us—is part of something much larger happening in 2026, a fundamental shift in the power dynamics between individuals and the platforms that hold their data.

The first principle is that your data should serve your questions. Every platform you use is sitting on information you generated and showing you their interpretation of it: LinkedIn shows a feed optimized for engagement, meaning optimized for keeping you scrolling rather than helping you leverage your network effectively; Spotify shows recommendations optimized for stream counts and licensing deals rather than for expanding your taste in directions you’d genuinely appreciate; your bank shows transactions organized by date, the laziest possible presentation, rather than by spending category or subscription pattern or comparison to your stated financial goals. These platforms have the data to answer your questions, but they choose to answer their questions instead. The ability to export your data and run your own analysis flips this dynamic completely, letting you ask the questions the platform would never let you ask. “Who in my network has the highest probability of actually helping me right now?” is not a question LinkedIn wants you to pose, because the answer might be someone you already know well who doesn’t need any premium features to reach.

The second principle is that the UI has always been the limitation. Traditional software UX is constrained by what designers anticipated you’d want to do—a finite number of buttons, filters, views, and dashboard configurations. Product teams make decisions based on what most users want, building X because it’s popular and skipping Y because it’s too niche, which means your specific question probably wasn’t anticipated and there’s no button for it. AI analysis has no such constraint. I can ask for everyone who works in AI robotics and who I’ve messaged in the last year and who has a vouch score above 50 and who has connections at YC-backed companies—a filter combination no UI in the world offers because the permutations are effectively infinite. But natural language has infinite permutations too, which means I describe what I want, the AI figures out how to query for it, and the constraint isn’t the interface anymore but my own imagination.

The third principle is that the export is the API. Most platforms now legally require a data export option under GDPR in Europe and CCPA in California, mandating that they give you access to your own data. LinkedIn has a “Download Your Data” button buried in settings, and so does Facebook, Google, Spotify, Apple, and Amazon. That export is your API—your access to the raw material, structured data in JSON or CSV format containing everything the platform knows about you. What you do with that export afterward is entirely up to you, and what you can do in 2026 is dramatically more than what you could do even two years ago. The export has always been there; the ability to meaningfully analyze it by asking natural language questions and getting structured answers is new. That’s the unlock.

The people who understand this dynamic have an asymmetric advantage that compounds over time, not because the technology is secret—Claude and ChatGPT are available to everyone, and data exports are legally mandated—but because most people don’t realize the question is even askable. They don’t know they can export their LinkedIn data, they don’t know they can ask an AI to analyze it, and they don’t know the insights sitting in that data, waiting to be extracted. Now you know, and that awareness is the edge.


## **What the output actually looks like**

Let me walk you through what you’re actually looking at when you run this analysis, using my own data with anonymized identities so you can see real metrics on real connections.

The network overview shows summary statistics at the top: total connections (mine is 1,922), unique companies represented, and the percentage of senior contacts (31% in my case, flagging significant access to decision-makers). The archetype classification emerges from these patterns—I come out as a Thought Leader, indicating high inbound connection rates and content-oriented network effects. This classification isn’t vanity; it determines strategy. A Thought Leader’s best move is broadcasting, because a single post about a job search could generate dozens of warm leads, while an Insider with dense connections at a few companies should work those internal networks instead, and a Climber with executive-heavy connections should focus on referrals from people who can make hiring decisions. Knowing your archetype prevents you from following advice designed for a different network shape.

The reciprocity ledger displays two columns. On the left are people who owe you—they received endorsements or recommendations from you without reciprocating, making them your “ask list” where requesting something back is socially appropriate because you’ve already invested in them. On the right are people you owe, relationships where you should start by giving rather than asking if you want to strengthen the connection. Looking at my own data, I can see several relationships where I’ve given significantly more than I’ve received, giving me standing to request favors, alongside relationships where I’m in debt and should contribute before making any asks.

The relationship health section shows current strength after half-life decay is applied, with each connection receiving a score that reveals how some relationships that felt strong a year ago have quietly faded. The connections marked “critical decay” haven’t been touched in over six months and are approaching cold. The insight here is prioritization: which relationships need investment this week, before they decay past the point of easy reconnection? That’s what the critical flags tell you—not someday, but this week.

The vouch score ranking shows who would actually go to bat for you, ordered by likelihood they’d advocate on your behalf based on combined signals. The top scorers have written recommendations, engaged in substantive conversations recently, and share institutional history. My highest advocate scores around 60, reflecting deep conversation history and recent contact, while someone near the bottom might sit at 25—we’re connected, but the relationship isn’t deep enough to ask them to vouch for me to a hiring manager. Not yet, anyway.

The resurrection opportunities surface dormant conversations with specific re-engagement hooks: “catch-up never scheduled” flags a coffee I proposed seven months ago that never happened; “help request unanswered” marks someone who asked if I knew anyone in a specific field and got my promise to look into it, which I never fulfilled; “you offered help” identifies cases where I volunteered assistance that was never taken up. These are relationships I’d completely forgotten about until the analysis surfaced them, and they represent the lowest-effort, highest-return reconnections available—people who already liked me and simply forgot. Five minutes to send a message, high probability of response. My data shows 211 resurrection opportunities, which is 211 warm leads sitting dormant.

The warm path calculator is the dynamic feature that brings everything together. When I enter a target company like Dactyl AI, the system scans my network for relevance (people in adjacent companies, people with robotics or AI in their titles, investors in the space) and cross-references with warmth scores from the vouch and half-life calculations. The top result isn’t someone who works at Dactyl, because I don’t have a direct connection there; it’s someone with high domain relevance—CEO of a similar company—combined with a warm relationship based on past conversations. That’s my best path in, and finding it transforms “I want to get into Company X” from random applications into strategic, warm introductions.


## **Mapping each analysis to action**

Each of these features maps to a specific action for navigating the 2026 job market.

Relationship half-life tells you who to invest in this week—not someday, but this week, before they cross from warm to cold. If you’re job searching, you should spend twenty minutes every week on targeted re-engagement with people approaching the decay threshold, and the half-life scores tell you exactly who those people are.

The reciprocity ledger reveals who you can ask for favors without awkwardness. If you’ve given more than you’ve received from someone, the social balance supports you requesting something, and “Hey, I’ve endorsed you a few times and really respect your work—would you be open to making an intro?” is a much easier conversation when you know the ledger is on your side.

Vouch scores tell you who to list as references. Before putting someone’s name down, check their score: below 50 means they might hesitate, give a lukewarm endorsement, or fail to remember your work clearly enough to advocate effectively. Your references should all be above 70, ideally above 80, and if they’re not, you have time to prime those relationships before you actually need them.

Resurrection opportunities are your quick wins—the lowest-effort, highest-probability reconnections in your network. These people already liked you, already had positive interactions with you, and have simply forgotten. Re-engaging takes five minutes and carries a high success rate, making it the best return on investment of any networking activity.

Network archetype determines the right strategy for your specific situation. Generic advice like “reach out to 10 people a week” means different things for different network shapes: if you’re a Connector, your value lies in introductions, so you should trade access rather than just asking for it; if you’re a Climber, you should target executive referrals because you have decision-maker access most people don’t; if you’re an Insider, your deep company knowledge is the asset, so you should position yourself as an expert rather than a generalist.

Warm path transforms how you approach target companies. When you identify somewhere you want to work, don’t cold apply—run the warm path analysis first. Find your highest combined-score connection, reach out to them rather than the company directly, and ask for an introduction or insight: “Hey, I’m interested in Company X and I know you’re connected to that space—any chance you could make an intro or tell me what you know about their culture?” That message, sent to the right person, is worth more than fifty cold applications.


## **What was always yours**

Everything I’ve described—the prompts, the methodology, the ChatGPT-compatible versions, the dashboard templates—I’m making all of it available. You can download your LinkedIn data tonight, run the analysis tomorrow morning, and by the end of the week you’ll understand your network in a way LinkedIn’s interface will never show you.

But here’s what I really want you to walk away with, and it’s bigger than LinkedIn or job searching.

For twenty years, we’ve been users. We’ve logged in, scrolled feeds, clicked buttons, and accepted whatever interpretation of our data the platform chose to show us. We’ve been passive consumers of our own information, which is a strange position when you think about it—we generated that data, those are our relationships and our histories, and yet we’ve had no real way to analyze them on our own terms.

That era is ending. You own your data, you own your relationships, you own your history, and for the first time you have tools powerful enough to analyze that information and extract insights the platforms themselves will never build for you.

The platforms will keep optimizing for their metrics—engagement, time on site, premium conversions—because they have shareholders and growth targets that fundamentally aren’t aligned with your individual outcomes. You can now optimize for your own metrics instead: relationship health, career progress, authentic connection, whatever actually matters to you.

The tools exist. The data is exportable. The only remaining question is whether you’ll spend two hours setting it up.

Your network is not your list of connections. Your network is your relationships—the actual strength of actual ties to actual humans who would actually help you. And now, for the first time, you can see them clearly.


## **Grab the prompts (links below)**

Before any of this works, you need your data. LinkedIn buries the export option, so here’s the path: Settings & Privacy → Data Privacy → Get a copy of your data → select “Download larger data archive” → request the archive. LinkedIn says it takes 24 hours; in my experience it’s closer to 15 minutes for the initial files, though the full message history can take longer. You’ll get a zip file with CSVs covering connections, messages, endorsements, recommendations, positions, skills, and profile data. That’s your raw material.

This isn’t a one-time analysis—it’s a workflow. First run gives you the full picture: dashboard, CSV action table, and a script you can re-run quarterly as relationships shift. On-demand, the warm path prompt answers “how do I reach this specific company?” whenever you need it. The Quick Start Guide walks through the full system, including how to set up your action table, common issues you’ll hit, and how to extend this work over time.

**LINK: [Quick Start Guide](https://www.notion.so/product-templates/LinkedIn-Network-Analysis-Quick-Start-Guide-2f75a2ccb5268049b4a7fba500156aa0?source=copy_link)**

Once you have the export, you’re choosing between two paths.

**If you have Cowork access:** Use the full analysis prompt. Point it at your unzipped LinkedIn folder and let it run. You’ll get all six analyses—relationship half-life, reciprocity ledger, vouch scores, resurrection opportunities, network archetype, and warm path discovery—in a single session with persistent state. When you want to query a specific company, just ask in the same conversation. The context carries forward.

**LINK: [Full Analysis Prompt (Cowork)](https://www.notion.so/product-templates/Network-Intelligence-Analysis-Cowork-2f75a2ccb5268065a488dfd4de2b0b1d?source=copy_link)**

**If you’re using ChatGPT:** Run the two-part sequence. Part 1 takes your connections, endorsements, recommendations, and positions files and returns your reciprocity ledger, network archetype, company concentration analysis, and senior contact mapping. Part 2 takes your messages file separately—this is the heavy lift—and returns conversation depth scores, resurrection opportunities, and vouch calculations. Keep both outputs; you’ll reference them when you run the warm path prompt for specific target companies.

**LINK: [Part 1 — Core Metrics (ChatGPT)](https://www.notion.so/product-templates/ChatGPT-Network-Intelligence-Part-1-Core-Metrics-2f75a2ccb52680639d33cbf8035e8f03?source=copy_link)**

**LINK: [Part 2 — Message Analysis (ChatGPT)](https://www.notion.so/product-templates/ChatGPT-Network-Intelligence-Part-2-Message-Analysis-2f75a2ccb52680aaab76c9862e3b7572?source=copy_link)**

The standalone warm path prompt works in either environment. Feed it a company name and it ranks your connections by combined relevance and warmth. For niche targets, relevance dominates the weighting. For well-known companies where more paths exist, warmth matters more. The prompt handles the math; you just need to know who to reach out to first.

**LINK: [Warm Path Query Prompt](https://www.notion.so/product-templates/LinkedIn-Warm-Path-Discovery-2f75a2ccb5268091a622c310c533cf1d?source=copy_link)**

The dashboard templates structure the output into something scannable—relationship health sorted by decay urgency, resurrection opportunities grouped by hook type, vouch scores ranked highest to lowest. If you’re running in Cowork, the full prompt generates these automatically. In ChatGPT, the Part 1 and Part 2 prompts include the formatting; you’ll just need to combine the outputs manually.

**LINK: [Dashboard Templates](https://network-intelligence.lovable.app/)**

One note on message analysis: if you have years of LinkedIn history, the messages file can be large. ChatGPT may timeout on the heaviest computations. If that happens, ask it to process in batches—first 1,000 messages, then the next 1,000—and aggregate the results. Cowork handles this natively without the timeout risk, which is part of why I prefer it for this particular workflow.

Everything above is copy-paste ready. Export your data tonight, run the analysis tomorrow, and by end of week you’ll see your network the way LinkedIn never wanted you to.

[![](https://substackcdn.com/image/fetch/$s_!_Nua!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4a08d23-6013-4c4d-8da6-0e8c6f794eb9_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!_Nua!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff4a08d23-6013-4c4d-8da6-0e8c6f794eb9_1024x1024.png)
