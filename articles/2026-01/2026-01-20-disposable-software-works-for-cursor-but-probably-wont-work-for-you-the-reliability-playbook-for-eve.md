---
title: "Disposable software works for Cursor, but probably won't work for you. + The reliability playbook for everyone else"
author: "Nate Jones"
published: 2026-01-20
url: https://natesnewsletter.substack.com/p/the-disposable-software-era-requires
subtitle: "Watch now | Disposable software is everywhere lately--but does anyone really know what that means? This is my take on how navigate this era, no matter where you sit."
audience: everyone
scraped_at: 2026-01-20 12:00:17
---

Everyone’s talking about disposable software, but almost nobody is thinking through what it actually implies.

The vibe coders treat it as liberation. The VCs treat it as a thesis. The AI-native startups treat it as an identity. And they’re all pattern-matching to a vibe without asking the harder question: what follows from the fact that generating code is now essentially free?

Because something does follow from it. The cost structure of an entire industry just inverted. That changes how we organize, what we build, and how we compete. But it changes those things differently depending on who you are and what you’re building—and the current discourse misses that completely.

The conventional framing says: software is cheap now, so ship faster, hire fewer engineers, vibe-code everything. That framing is wrong. It confuses the cost of generating code with the cost of directing attention toward a goal. The first collapsed. The second didn’t. And if you don’t understand the difference, you’re going to make expensive mistakes.

**Here’s what’s inside:**

- **The inversion that actually happened.** Why the cost of software was always the cost of engineering—and what changes when that’s no longer true.
- **The two kinds of disposable software.** Personal tools you build for yourself are unambiguously good. Disposable features in enterprise products are more dangerous than most people realize.
- **Why developers tolerate this and CIOs won’t.** The Cursor philosophy works for a narrow slice of the market. The rest of the business world is buying something different.
- **The attention problem nobody talks about.** Free software isn’t free when building it diverts your best people from your core mission.
- **What proactive AI actually requires.** The opportunity for enterprise software isn’t shipping faster—it’s earning the right to act autonomously on behalf of users.

The age of disposable software is real. But knowing which game you’re playing—and playing it all the way—is what separates the companies that win from the companies that get caught in the middle.


## [Grab the Prompts](https://www.notion.so/product-templates/Prompts-Disposable-Software-Decision-Kit-2ed5a2ccb5268084af1feb65ff8d2118?source=copy_link)

The frameworks in this article only matter if you can apply them to your specific situation—and the failure modes are different depending on which game you’re playing:

- If you’re shipping for developers, the risk is crossing from “fast” into “unpredictable nightmare” by treating features as disposable when they touch data, workflows, or trust.
- If you’re shipping for CIOs, the risk is trying to be proactive before you’ve earned it—terrifying customers instead of delighting them.
- And regardless of which lane you’re in, the attention trap is universal: “free” software that quietly consumes your best people’s time while your core mission stalls.

The prompts linked are designed to catch these specific mistakes before they compound. They produce artifacts—volatility budgets, trust ladders, maintenance contracts, opportunity cost memos—not generic advice. Fill in your context, run the prompt, get a decision.


## The Basic Premise

Here’s the thing that changed: the cost of software was always the cost of engineering. That’s it. That’s the whole story of Silicon Valley from the 1970s through about 2023. You needed a team of software engineers to build anything meaningful, and engineers were expensive. That expense is what made the entire venture capital model work—you needed capital to build software, so investors provided capital in exchange for equity, and the machine churned forward on that basic assumption.

That assumption is now false.

The cost of software is running to zero. Not trending toward zero over decades—collapsing toward zero right now. When you can describe what you want in plain English and get working code back, the engineering bottleneck disappears. The capital requirement disappears. The team requirement disappears.

And when something that was expensive becomes essentially free, it becomes disposable. That’s not a value judgment. It’s just economics. We don’t get precious about things that are cheap to produce and cheap to replace.

So “disposable software” isn’t a philosophy or a movement. It’s a description of what happens when the cost structure of an industry inverts. Software is now disposable the same way that digital photos are disposable—not because we don’t value them, but because the cost of producing another one is approximately zero.

Here’s a concrete example of what that inversion looks like.

Two weeks ago, Cursor’s CEO Michael Truell announced that his team had built a web browser from scratch using AI agents. According to Truell, they ran agents for one week straight and generated over three million lines of Rust code. He said simple websites render quickly and largely correctly.

Now consider the comparison. Google Chrome started development in 2006. The first beta shipped in September 2008—over two years later. Today, Chromium has over 36 million lines of code and hundreds of engineers committing around 800 changes per week. It took two years and a team of elite engineers to ship a beta. It took one week and a swarm of AI agents to produce something that “kind of works.”

That’s not a small change. That’s an inversion.

But here’s what the breathless coverage misses: it wasn’t free. Someone at Cursor had to decide to build a browser. Someone had to set up the task. Someone had to configure how the agents would coordinate. Someone had to run it for a week. And now, if they wanted this to be production software rather than a demo, someone would have to improve it, debug it, maintain it, keep it working as web standards evolve.

The cost of generating code collapsed. The cost of directing attention toward a goal did not. And that distinction is going to matter a lot as we work through what disposable software actually means.

That’s the basic premise. Now here’s where it gets interesting.


## What Disposable Software Actually Is

The first thing people get wrong: they treat disposable software as one thing. It’s two completely different phenomena that happen to share a name.

The first is obvious: throwaway software for throwaway use cases. A one-time dashboard. A travel app for your family’s upcoming vacation. A small video game you build over the weekend. This is personal software—a category that barely existed five years ago. I’ve done demos of this with Claude’s artifacts, with Lovable, with Claude Code. You can just build the thing you need. It would never have traditionally been software, but now it can be. Want to see a visualization? Build a widget for it. Want a tool that does exactly what you want? Just make it.

This category is unambiguously good. It represents genuine democratization. Replit CEO Amjad Masad has said that 75% of Replit’s customers never write a single line of code. They just describe what they want and get working software. That’s remarkable.

The second category is more interesting and more dangerous: disposable features within enterprise products.

Here’s the logic. If you can ship a hundred different features based on a hundred different customer requests—because your product team, your engineering team, everyone is contributing code through AI tools—then any given feature can be changed next week based on customer response. You ship and ship and ship and ship. You discover what works empirically with customers. You create a bunch of disposable features and only harden up what sticks.

This is the Cursor philosophy. They ship constantly, sometimes multiple times per day. When vocal users complain about the instability, Cursor has essentially said: we don’t care. Changing rapidly is how you keep up in the AI era. An AI-native company cannot hold its position in the marketplace without keeping up, and keeping up means shipping disposable software.

Their phrase for this is “code is reality.” If you’re not touching reality—if you’re in meetings, if you’re planning, if you’re designing—you’re not doing meaningful work. They’ve configured their entire team around this idea.


## What It Means for How We Organize

Here’s what disposable software actually kills: all the rituals that grew up around expensive software.

Product management. Design. Stakeholder alignment. User research. Roadmap planning. These processes existed because software was capital-intensive and you couldn’t afford to build the wrong thing. So you planned. You researched. You held meetings. You built consensus. Then you built software.

When software becomes disposable, you don’t need consensus. You just build it, ship it, see if it works. If it doesn’t work, you build something else. The planning layer becomes overhead rather than insurance.

Cursor’s head of design gave an interview where he said the roles between designers, PMs, and engineers at Cursor are “really muddy.” They don’t have a roadmap, he said, because “the world is changing faster and faster” and “there’s new models dropping every day.” The company doesn’t really have PMs—the PM jobs are “spread across the builders.”

This is a coherent philosophy. It’s the philosophy of code as reality. If shipping is what matters, then anything that isn’t shipping is waste. Design documents are waste. Product specs are waste. Stakeholder meetings are definitely waste.

This works in certain contexts. It absolutely works if you’re building an AI-native product for developers. Developers have an unusually high tolerance for software variance. They understand that things break. They understand versioning, regression, the tradeoffs inherent in moving fast. They accept instability as the price of innovation.

But even developers are getting stretched by this. Go read the Cursor forums. Users are frustrated by forced updates that wipe chat history. By UI changes that require reconfiguring keybindings every week. By features that work one day and break the next. One user wrote—in all caps—”UPDATES MAKE THE CURSOR EXTREMELY UNPREDICTABLE! WORKING WITH THIS PROFESSIONALLY IS A NIGHTMARE!”

A Cursor engineer acknowledged the feedback and said they’re working to minimize UI changes going forward. But the tension is structural. The disposable software philosophy demands constant iteration. Stability demands continuity. You cannot fully maximize both.


## What It Means for Product Strategy

Here’s what people miss about enterprise software: customers aren’t buying software. They’re buying reliability.

When a company buys Salesforce, they’re not buying a CRM. They’re buying peace of mind. They’re buying something they don’t have to think about because their core competency is somewhere else.

Your core competency is not CRMs if you’re buying Salesforce. That’s why you pay for it. Your core competency is not an HR information system if you’re buying an HR information system. That’s why you’re paying for it. Enterprise customers buy software precisely so they can ignore it.

This is why enterprise SaaS contracts are multi-year deals with extensive SLAs. It’s why vendors promise 99.99% uptime and staff 24/7 support lines. It’s why there are dedicated account managers you can call in the middle of the night and say “this has to be up, I have a deal that has to go through.”

Disposable software is the opposite of everything these customers want. They don’t want features that change every week. They don’t want interfaces that rearrange themselves between login sessions. They want a product that works the same way on Tuesday as it did on Monday, that will work the same way next quarter as it does this quarter.

They want a single ringable neck.

There’s a design implication here that I haven’t seen anyone talk about. Disposable software works better with simpler interfaces.

Part of what has made Claude Code successful is that it’s a terminal interface. The terminal doesn’t change when Claude Code gets better. You just get more capabilities. There’s no GUI to redesign, no keybindings to rearrange, no visual elements to rethink.

The simplicity creates a buffer between the product’s evolution and the user’s experience. Anthropic can ship massive release deltas—sometimes over a thousand commits at once—without stressing users out with visible change.

If you want to ship disposable features, you need an interface simple enough to absorb constant change without imposing that change on users. The terminal does that. A complex GUI does not. And that’s why Cursor—with its rich GUI—keeps running into user complaints about instability, while Claude Code—with its terminal—can ship just as aggressively without the same friction.


## What It Means for Builders

The usual response from disposable software advocates goes like this: “Nate, you’ve forgotten. Software is so cheap now. Salesforce won’t exist because we’ll all vibe-code our own Salesforce.”

This argument has a fatal flaw, and it’s not about software cost. It’s about attention.

Imagine you’re a company chasing a multi-billion-dollar market opportunity. You have highly paid, highly skilled builders focused on that opportunity. Every hour they spend on core product development creates asymmetric value—the kind that justifies venture funding, builds competitive moats, compounds over time.

Now imagine telling those builders: we want you to stop chasing the billion-dollar opportunity and instead vibe-code an internal CRM to save us a hundred bucks per seat per month.

The software is cheap to generate. The attention is not. Someone still has to specify what the tool should do. Someone still has to prompt the AI. Someone still has to keep an eye on the bugs the agent produces. Someone still has to maintain it when it breaks. It’s not completely zero.

You’re essentially saying that a hundred dollars a seat is worth your highly paid builder’s time, but chasing your core business opportunity is not. That math doesn’t work. The opportunity cost of diverting your best people from your core mission is incalculable, and no amount of cheap software changes that equation.

And there’s a second layer to this that people miss: the maintenance burden doesn’t go away just because the initial build was cheap. Vibe-coded software still accumulates technical debt. It still breaks when underlying APIs change. It still needs someone to debug it when it behaves unexpectedly. Veracode’s research found that AI-generated code introduces security vulnerabilities in nearly half of all coding tasks, and those vulnerabilities tend to be the deep, architectural kind that scanners miss and reviewers struggle to catch.

So you haven’t eliminated the cost. You’ve just shifted it from upfront engineering to ongoing maintenance and security remediation. And that ongoing cost gets paid by the same highly compensated people you were trying to free up for your core business.

The disposable software advocates want you to believe that software cost was the constraint. It wasn’t. Attention was always the constraint. Software getting cheaper doesn’t make attention more abundant.


## Who Can Actually Use This

Cursor’s customers are developers. Salesforce’s customers are CIOs.

That’s not a small difference. That’s a chasm.

Developers can fix things when they break. CIOs call their account manager. Developers understand why updates cause regressions. CIOs just see broken workflows. Developers get value from new capabilities and are willing to tolerate instability to access them. CIOs get fired if payroll doesn’t run on the 15th.

Developers chose a bleeding-edge tool knowing it would change constantly. CIOs chose a vendor with an SLA specifically so they wouldn’t have to think about the software. The whole point of buying Salesforce is that you’re not the kind of company that wants to be in the CRM business. You want someone else to handle it.

Cursor can ship disposable software because their customers are developers. Salesforce cannot because their customers are CIOs. This is not a temporary gap that will close as AI improves. It’s a fundamental difference in what the customer is buying.


## What It Means for AI Strategy

So if you’re in the reliability business—if you’re Salesforce, if you’re competing with Salesforce, if you’re trying to disrupt any enterprise category—what does disposable software mean for your AI strategy?

It means you can’t use it. But that doesn’t mean you ignore AI. It means you need a different approach.

I see most AI-native startups trying to disrupt enterprise markets by saying “we’re AI-native” like that’s enough. It’s not.

You have to be reliable first. You have to prove that your product works, that it will continue to work, that data is secure, that there’s a human being customers can call when something goes wrong. This is table stakes. Without reliability, nothing else matters.

Then—and this is where the opportunity is—you extend that reliability into proactive AI.

I don’t mean bolting a chatbot onto your product. A chatbot is reactive. It waits to be asked. That’s not impressive anymore. Every SaaS company in 2025 has a chatbot. The chatbot says “how can I help you?” and then you have to know what to ask it. That’s not transformation. That’s a help desk with a language model.

What’s impressive is proactive. If you’re building sales software, the agent in your product should be your customer’s most proactive BDR. It proactively analyzes calls without being asked. It proactively surfaces coaching tips before the rep realizes they need them. It proactively identifies high-value deals and takes appropriate action—maybe it updates the CRM, maybe it drafts a follow-up email, maybe it alerts the sales manager. You don’t wait to be asked. The agent sees something, understands what needs to happen, and does it.

This is a fundamentally different value proposition. Reactive AI saves time when you know what you need. Proactive AI creates value you didn’t know you were missing.

The key phrase is “proactively reliable.” You’ve earned trust through reliability—through months or years of the product working exactly as expected—which gives you the space to take autonomous action on behalf of users. That’s the two-step: reliability first, then proactive capability.

You cannot skip step one. If you try to be proactive before you’ve proven reliability, you will terrify your customers. An agent that takes autonomous action on behalf of users is only valuable if those users trust that the action is always correct. If they have to second-guess the agent, if they have to check its work, if they’re worried it might mess something up, then the proactive capability is actually a liability. It creates anxiety rather than value.

The companies that figure out how to be proactively reliable will win the next decade of enterprise software. The companies that think “we’re AI-native” is a strategy will wonder why customers won’t trust them with anything important.


## Where This Leaves Us

The age of disposable software is real. The cost of generating software has collapsed. That changes everything about how we organize, what we build, and how we compete.

But it doesn’t change everything in the same way for everyone.

If you’re building for developers—if your customers chose you because you’re on the frontier—lean into disposability. Ship constantly. Treat every feature as provisional. Accept that stability is not your product. The companies that win in this space will be the ones that fully embrace the philosophy.

If you’re building for CIOs—if your customers are buying peace of mind—lean into reliability and earn your way toward proactive AI. The opportunity isn’t to pretend you can ship like Cursor. You can’t, and your customers don’t want you to. The opportunity is to build toward proactive AI that creates value your customers didn’t know they were missing. Start with low-stakes autonomous actions. Build a track record of correct decisions. Earn the right to act on your customers’ behalf.

The discourse is wrong because it treats the developer-tools case as the general case. It’s not. Most software, by revenue, by users, by the number of people building it, is the reliability game.

Know which game you’re playing. Then play it all the way.

[![](https://substackcdn.com/image/fetch/$s_!wLWq!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5f270a22-112b-422b-80df-375ecefedb93_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!wLWq!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5f270a22-112b-422b-80df-375ecefedb93_1024x1024.png)
