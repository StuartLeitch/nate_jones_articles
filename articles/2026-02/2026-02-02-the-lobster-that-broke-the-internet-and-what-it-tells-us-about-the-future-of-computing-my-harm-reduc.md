---
title: "The Lobster That Broke the Internet (And What It Tells Us About the Future of Computing) + my harm reduction guide if you're planning to run it"
author: "Nate Jones"
published: 2026-02-02
url: https://natesnewsletter.substack.com/p/the-moltbot-origin-story-a-16-million
subtitle: "Watch now | Clawdbot. Moltbot. OpenClaw. No matter how many times it rebrands, the signal is the same: we want AI that actually DOES things and we may not be ready for what that really means."
audience: everyone
scraped_at: 2026-02-02 12:00:20
---

Somewhere in the Valley right now, a developer is buying a Mac Mini specifically to give an AI agent root access to their digital life. They’re not alone. Developers are snapping up Mac Minis for dedicated always-on hardware. Cloudflare’s stock jumped over 20% in two days last week. And Peter Steinberger, an Austrian developer who built a personal AI assistant as a hobby project three months ago, is now fielding harassment from crypto scammers, fixing critical security vulnerabilities, and watching his creation get called “infostealer malware in disguise” by Google’s VP of Security Engineering.

The project is called Moltbot\*\*. Until last Monday, it was called Clawdbot. The name change wasn’t voluntary—Anthropic’s legal team saw to that. What followed was 72 hours of chaos: a ten-second window that let crypto scammers hijack the project’s identity, a $16 million rugpull token, security researchers finding over a thousand exposed instances with plaintext credentials, and over 100,000 GitHub stars that made it one of the fastest-growing open-source projects on GitHub.

This is either the future of personal computing or a collective hallucination. Possibly both.

**Here’s what’s inside:**

- **What Moltbot actually is.** The architecture, the capabilities, and why “AI that actually does things” is both the value proposition and the risk.
- **Why Wall Street noticed.** How a GitHub repo moved Cloudflare’s stock 20% and what that signals about the next phase of the AI trade.
- **The 72 hours that changed everything.** Trademark disputes, account hijacking, security disclosures, and lessons in operational security that will be studied for years.
- **The security problem that has no solution.** Why the vulnerabilities aren’t bugs—they’re intrinsic to what agentic AI requires.
- **Should you run it?** An honest assessment based on who you are and what you’re willing to risk.

Let me show you how a lobster broke the internet—and why the most interesting question isn’t whether you should run Moltbot, but whether agentic AI can ever be made safe at all.

*\*\*\*A note: I recorded the video for this piece late last week, when the project was still called Moltbot. In the days since, it rebranded again—to OpenClaw. I have a Part 2 coming that will cover what’s emerged. Consider this the origin story.*


## **Grab the guide and prompt (links below)**

The security problem with agentic AI isn’t going away—and neither is the demand for tools that actually work. These resources exist because I’ve watched too many people either avoid the space entirely out of fear or dive in without understanding what they’re exposing. The harm reduction guide walks through the specific configurations that separate “interesting experiment” from “credential theft incident.” It’s not comprehensive security—that doesn’t exist yet—but it’s the minimum viable hardening that gives you containment when something breaks. The image prompt is lighter: a way to get your AI collaborator to reflect honestly on how you actually work together, rendered as something you can see.

- **LINK: [If You’re Going to Run OpenClaw Anyway: A Harm Reduction Guide](https://docs.google.com/document/d/1OhFgEUen6GBhNIFqtHlRaNdCc3REpKiT7_YnSEfNdGk/edit?usp=sharing)** Hardware isolation, network lockdown, permission minimization, and incident response. The configurations that limit blast radius.
- **LINK: [Visualize Your AI Working Dynamic](https://www.notion.so/product-templates/The-Lobster-That-Broke-the-Internet-Companion-Prompts-2fa5a2ccb52680de91c1f90346783f64?source=copy_link)** A prompt that gets your AI to generate an honest image of your collaboration. No glowing orbs. No robots. Something real.

---


## **What Moltbot Actually Is**

Strip away the hype and Moltbot is a simple idea executed ambitiously: an AI assistant that runs on your hardware, talks to you through apps you already use, and actually does things instead of just suggesting them.

You message it on WhatsApp. It reads your emails, triages your inbox, drafts responses. You tell it to book a flight. It opens a browser, searches, fills out forms, confirms. You ask for a morning briefing. It pulls your calendar, your tasks, your health data from your Whoop, relevant news, and sends you a summary before you’ve finished your coffee.

The tagline is “AI that actually does things.” That’s not marketing fluff. It’s the core value proposition and the core risk, condensed into five words.

Technically, Moltbot is a gateway service that maintains WebSocket connections to messaging platforms—WhatsApp, Telegram, Signal, iMessage, Discord, Slack, Teams, Matrix—while orchestrating an LLM backend (usually Claude, sometimes GPT-4, sometimes local models via Ollama) and a growing library of “skills” that give it capabilities: browser automation via Puppeteer, file system access, shell commands, calendar integration, email, smart home control, and dozens more.

The architecture is local-first. The gateway runs on your machine. Your conversation history stays on your machine. Your credentials stay on your machine. The privacy story is real, as far as it goes.

But “local-first” doesn’t mean “local-only.” Unless you’re running a local model, your queries still route to Anthropic or OpenAI’s APIs. You own the agency layer. You rent the intelligence.

Peter Steinberger built the first version for himself after stepping away from PSPDFKit, the PDF company he founded. After Insight Partners acquired a majority stake, Steinberger sold his shares and walked away. He’d barely touched a computer for three years. Then he rediscovered his spark playing with Claude, started building tools to manage his own digital chaos, and eventually open-sourced the result with a lobster mascot named Clawd.

Twenty-four hours later, it had 9,000 GitHub stars. A week later, 60,000. By the end of January, it had crossed 100,000 stars and 14,000 forks—one of the fastest-growing open-source projects on GitHub. An active Discord of nearly 9,000 members building extensions, sharing workflows, pushing boundaries.

Andrej Karpathy praised it publicly. One user’s summary captured the mood: “At this point I don’t even know what to call Moltbot. It is something new. After a few weeks with it, this is the first time I have felt like I am living in the future since the launch of ChatGPT.”

This is either the future of personal computing or a collective hallucination. Possibly both.

---


## **Why Wall Street Noticed**

The growth was so fast it moved markets. Not Anthropic’s. Cloudflare’s.

Here’s the connection: for a local AI agent to be useful, it often needs to communicate with the outside world—receiving webhooks from GitHub, messages from WhatsApp, commands from Slack—without exposing your home network to the open internet. Cloudflare Tunnels provide this secure bridge, allowing developers to expose local services safely. The community quickly standardized on it. Adoption was enthusiastic.

[![](https://substackcdn.com/image/fetch/$s_!qFeF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F699b017d-2cf9-42e0-bb66-17513a36def8_1202x986.png)](https://substackcdn.com/image/fetch/$s_!qFeF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F699b017d-2cf9-42e0-bb66-17513a36def8_1202x986.png)

Cloudflare stock rose 9% on Monday, January 26, on the weekend social media buzz. It climbed another 12% Tuesday. Over 20% in two days, driven by a GitHub repository.

Wolfe Research analyst Joshua Tilton argued that as these agents scale—making API calls, accessing websites, routing inference requests—they require secure, low-latency infrastructure, and Cloudflare’s global edge network is well-suited to support exactly that.

CEO Matthew Prince has said that 80% of the leading AI companies already rely on Cloudflare, and that the agents of the future will inherently have to pass through their network.

The market is pricing in a paradigm shift. For two years, the AI trade focused on training—buying Nvidia GPUs to build massive models. The Moltbot surge signals investors are beginning to price in the inference and application phase, where value accrues to the companies connecting models to the real world.

A Chat AI answers questions. An Agentic AI performs labor. Labor requires constant connectivity and security. If millions of personal agents and enterprise agents deploy, the volume of secure, low-latency connections required will skyrocket. Cloudflare’s Workers platform is consumption-based. More agent activity means more revenue.

The analysts are careful to note that Moltbot won’t immediately impact Cloudflare’s financials. But it’s validation of strategic positioning. Proof of concept for a much larger revenue thesis.

Mac Minis, meanwhile, are flying off shelves as developers set up dedicated hardware. People want always-on machines for their AI assistant. Apple didn’t see that coming.

---


## **The 72 Hours That Changed Everything**

On January 27th, 2026, Anthropic’s legal team sent Steinberger a trademark notice. The name “Clawd” was too close to “Claude.” He had to change it.

The timing was brutal. The project was at peak velocity, attention white-hot, community exploding. Steinberger complied quickly—announced the rebrand to “Moltbot” (lobsters molt to grow), started the migration.

Then he made a mistake that will be studied in operational security courses for years.

When changing the GitHub organization name and X handle, he released the old names before securing the new ones. The gap was approximately ten seconds.

In that window, crypto scammers grabbed both accounts.

This wasn’t a hack. They were waiting. Watching. The moment “@clawdbot” became available, they snatched it.

What followed was chaos. A fake $CLAWD token appeared on Solana, riding the viral wave. It hit $16 million market cap before collapsing—a classic rugpull that wrecked late buyers. Fake accounts proliferated. Steinberger’s mentions filled with speculators demanding he endorse tokens he’d never heard of.

“To all crypto folks,” he posted: “Please stop pinging me, stop harassing me. I will never do a coin. Any project that lists me as coin owner is a SCAM.”

Meanwhile, security researchers had been poking at the codebase. What they found wasn’t reassuring.

Jamieson O’Reilly, founder of red-teaming firm Dvuln, discovered that the gateway’s authentication logic trusted all localhost connections by default. Run Moltbot behind a reverse proxy—a common deployment pattern—and that proxy traffic gets treated as local. No authentication required. Full access to credentials, conversation history, command execution.

He scanned Shodan and found hundreds of exposed instances. Of those he examined manually, eight were completely open: API keys for Claude and OpenAI, Telegram bot tokens, Slack OAuth credentials, months of private messages, the ability to send messages as the user, shell access. One exposed instance had Signal configured on a public server. Another allowed arbitrary command execution with root privileges.

A separate researcher, Matvey Kukuy, demonstrated the severity with a proof-of-concept: he sent a single malicious email to a vulnerable Moltbot instance with email integration enabled. Via prompt injection, he extracted a private key in under five minutes.

Then O’Reilly went further. He uploaded a benign skill to ClawdHub—Moltbot’s plugin marketplace—artificially inflated the download count to 4,000+, and watched developers from seven countries install it. The skill did nothing malicious. But it could have. ClawdHub has no moderation process. Its developer notes literally state that all downloaded code “will be treated as trusted code.”

Security firm SlowMist announced that an authentication bypass made “several hundred API keys and private conversation histories publicly accessible.” Hudson Rock reported that Moltbot stores credentials in plaintext Markdown and JSON files, making it trivial pickings for infostealer malware. They’re already seeing malware families like Redline, Lumma, and Vidar implement capabilities specifically targeting Moltbot’s directory structure.

Heather Adkins, VP of Security Engineering at Google Cloud, amplified the warnings, characterizing the tool as “infostealer malware in disguise.”

All of this—the trademark dispute, the scam tokens, the security disclosures, the account hijacking—happened within 72 hours.

---


## **The Security Problem That Has No Solution**

Here’s where the analysis gets uncomfortable.

The vulnerabilities researchers found are real and serious. Some have been patched—Steinberger pushed 34 security-hardening commits in the first week. The localhost authentication issue that allowed proxy bypass is fixed. The community is engaged, PRs are flowing.

But the deeper problem isn’t bugs. It’s architecture. It’s what Moltbot is designed to do.

O’Reilly articulated it precisely: “We’ve spent 20 years building security boundaries into modern operating systems. Sandboxing, process isolation, permission models, firewalls. All of that work was designed to limit blast radius and prevent remote access to local resources. AI agents tear all of that down by design. They need to read your files, access your credentials, execute commands, and interact with external services. The value proposition requires punching holes through every boundary we spent decades building.”

This is the bind. A useful agentic AI requires broad permissions. Broad permissions create massive attack surface. The thing that makes Moltbot valuable is the same thing that makes it dangerous.

Consider prompt injection. Moltbot connects to your email, your messaging apps, your social accounts. It reads incoming content and acts on it. But LLMs can’t reliably distinguish instructions from content. An attacker sends you a carefully crafted WhatsApp message with hidden instructions. Moltbot treats it as trusted input. It follows the instructions. Maybe it forwards your credentials. Maybe it executes a shell command. You never see it happen.

This isn’t a Moltbot-specific flaw. It’s intrinsic to how language models process text. No one has solved it. Every agentic AI that reads untrusted content is vulnerable.

Or consider the supply chain. Moltbot’s extensibility is a feature—50+ bundled skills, a growing marketplace, infinite customization. But every plugin is unaudited code running with the permissions you’ve granted the agent. One malicious update, one compromised dependency, and your “personal AI assistant” becomes an exfiltration tool.

1Password’s security blog put it starkly: “MoltBot shows how powerful local AI agents can be. But if your agent stores in plain-text API keys... an infostealer can grab the whole thing in seconds.”

The critics have a point. Running Moltbot safely—on isolated hardware with throwaway accounts and strict network controls—largely defeats the purpose. A sandboxed assistant that can’t access your real email or calendar isn’t much of an assistant.

The security-utility tradeoff isn’t a problem to be solved. It’s a tension to be managed. And right now, most users aren’t managing it well.

---


## **The Compute Squeeze Nobody’s Talking About**

Zoom out further and something else comes into focus.

The Mac Mini buying frenzy isn’t just FOMO on a viral project. It’s colliding with a structural shift in semiconductor economics that’s been building for two years.

Server DRAM contract prices rose over 170% year-over-year in Q3 2025, according to TrendForce. Server memory is expected to double in cost by late 2026. The cause isn’t cyclical—it’s structural. AI datacenters are consuming an ever-larger share of global wafer capacity, and the memory manufacturers are following the margins.

HBM—high-bandwidth memory for AI accelerators—consumes roughly three times the wafer capacity of standard DRAM per gigabyte. Every chip allocated to an Nvidia GPU is a chip not going into your laptop. Samsung, SK Hynix, and Micron have signed multi-year supply contracts with hyperscalers, locking in capacity through 2028 and beyond. Consumer memory is getting what’s left over.

The memory market is bifurcating. Datacenter gets priority allocation, long-term contracts, falling per-bit costs. Consumer gets leftovers, rising prices, shrinking availability. In Japan, electronics retailers have instituted purchase limits on standalone RAM. That’s how tight the market has become.

Reframe Moltbot through this lens and the Mac Mini runs look different. People aren’t just excited about a cool new tool. They’re locking in personal compute capacity while they still can. It’s a hedge—conscious or not—against a future where running local AI gets priced out entirely.

The irony is sharp. Moltbot promises sovereignty over your AI stack. But most Moltbot instances route to Claude’s API. You own the agency layer; you rent the intelligence from Anthropic’s datacenters. The escape hatch—local models via Ollama—requires the RAM that’s flowing to those same datacenters.

The sovereignty play loops back to dependency. The window for true local AI may be narrowing as the economics tilt against consumer hardware.

---


## **What Siri Should Have Been**

For over a decade, tech companies promised us AI assistants that would transform our lives. Siri arrived in 2011. Google Assistant followed in 2016. Alexa colonized millions of kitchens. And yet, in 2026, most of us are still frustrated, still repeating ourselves, still wondering why our “smart” assistants can’t remember a conversation from five minutes ago.

Moltbot exposes how timid those efforts have been.

Apple’s Siri lives in a walled garden, limited to Apple’s approved integrations, forgetful by design, reactive only. It can set a timer. It can’t book you a flight. Google Assistant knows everything about you but does almost nothing with that knowledge. Alexa controls your lights but can’t manage your inbox.

Moltbot does what they promised and never delivered: it manages calendars across platforms, drafts emails in your voice, handles travel logistics end-to-end, commits code to your repos, monitors prices and rebooks when deals appear. It remembers. It acts proactively. It lives in the apps you already use rather than demanding you open yet another interface.

The tradeoff is that Moltbot requires you to trust it completely. Siri is safe because it’s neutered. Moltbot is useful because it’s dangerous. The big tech assistants are products designed to protect corporate liability. Moltbot is a tool designed to maximize user capability, consequences be damned.

That’s not a criticism—it’s an observation about what the market was hungry for. Over a hundred thousand GitHub stars in weeks suggests a lot of pent-up demand for assistants that actually assist.

---


## **Real Use Cases (The Ones That Justify the Hype)**

Despite everything, Moltbot works. And some of what it does is genuinely remarkable.

The 1Password security team, while documenting the risks, shared an anecdote that captures why people are excited: a user asked Moltbot to make a restaurant reservation. OpenTable didn’t have availability. So Moltbot went and found AI voice software, downloaded it, called the restaurant directly, and secured the reservation over the phone. No human intervention. Problem-solving behavior that emerged from the combination of broad permissions and a capable model.

That’s not email triage. That’s something new.

The demos flooding social media aren’t productivity theater—they’re genuinely novel capabilities. One developer configured Moltbot to run his coding agents overnight. He’d describe features before bed, wake up to working implementations, review the code over coffee. Another built a complete Laravel application while walking to get coffee, issuing instructions via WhatsApp, watching the commits land in his repo in real-time.

Steve Caldwell set up a weekly meal planning system in Notion—Moltbot checks what’s in season, cross-references family preferences, generates a grocery list, and updates the family calendar. Sounds trivial until you realize it saves an hour every week, runs automatically, and required no code to configure.

The self-improvement capability is what makes longtime AI observers sit up. Tell Moltbot “Create a skill to monitor flight prices and alert me when they drop below $300” and it writes the automation itself—the monitoring logic, the alert triggers, the integration with your messaging app. It extends its own capabilities on demand. Users describe it as “self-improving,” and while that’s not quite AGI, it’s also not wrong.

Within an hour of setup, one user had a fully functional kanban board where he could assign tasks to Moltbot and track their state. The AI became a team member with its own task queue.

The pattern among successful users: they’re not automating busywork. They’re delegating judgment-requiring tasks to a system that can handle ambiguity, recover from failures, and find alternative approaches when the first attempt doesn’t work. The restaurant reservation story isn’t impressive because it made a phone call—it’s impressive because the AI recognized that its initial approach failed and autonomously found a different solution.

That’s also what makes it dangerous. The same capability that lets it problem-solve creatively is the capability that lets a prompt injection attack succeed in novel ways. The same broad permissions that enable emergent behavior are the permissions that create massive attack surface.

The users who thrive treat Moltbot like a capable but unsupervised contractor: clear deliverables, defined boundaries, regular check-ins, and the understanding that impressive autonomy comes with commensurate risk.

---


## **Should You Run It?**

The honest answer depends on who you are.

If you’re technically sophisticated—you understand VPS deployments, network isolation, credential rotation, the difference between localhost and 0.0.0.0—Moltbot offers a genuine glimpse of where personal AI is headed. Run it on dedicated hardware. Use throwaway accounts for initial testing. Sandbox aggressively. Vet skills before installing. Assume anything you connect could be compromised and plan accordingly.

If the previous paragraph felt like jargon, wait. The project is young, the security model is immature, and the attack surface is vast. You’d be taking on risk you’re not equipped to evaluate or mitigate.

If you handle sensitive data professionally—financial records, health information, client communications—don’t connect Moltbot to those systems. The upside isn’t worth the liability.

And don’t buy any $CLAWD tokens.

---


## **The Question Moltbot Forces Us to Ask**

The deeper significance of Moltbot isn’t the project itself. It’s what the project reveals.

Agentic AI is coming regardless. The ability to delegate tasks to AI systems that can act autonomously isn’t a question of if but when and how. Moltbot is a preview—messy, risky, exhilarating, problematic—of what that future looks like.

The security model for agentic AI doesn’t exist yet. We’re trying to bolt new capabilities onto permission frameworks designed for a different era. The result is either neutered agents that can’t do anything useful or powerful agents that create massive risk. The middle ground is elusive.

The economics of personal computing are shifting beneath our feet. The same forces making cloud AI cheap and abundant are making personal AI infrastructure expensive and scarce. The dream of truly local, sovereign AI may be narrowing even as the tools to achieve it proliferate.

And the relationship between AI developers and the communities building on their platforms remains unsettled. Anthropic’s trademark notice was legally defensible. It may also have been strategically unwise. Google didn’t sue Android developers. OpenAI isn’t pursuing LangChain. There’s a playbook for nurturing ecosystems, and legal notices to your most enthusiastic community builders isn’t in it.

Moltbot didn’t create these tensions. It just made them impossible to ignore.

---


## **Where This Goes**

The project will survive. The security issues will get addressed—some already have. The community will adapt to the new name. Steinberger will recover from the chaos. The crypto scammers will move on to the next viral target.

But the questions Moltbot raised aren’t going away. How do you build AI agents that are both useful and safe? How do you maintain personal sovereignty over your AI stack when the economics favor cloud dependency? How do you foster open-source AI ecosystems without getting crushed by legal teams or exploited by bad actors?

Over a hundred thousand GitHub stars suggest a lot of people are hungry for answers. The Mac Mini supply chain suggests they’re willing to invest in finding them. The security disclosures suggest the path forward is harder than the hype implies.

Moltbot is a lobster molting in public—shedding its shell, vulnerable, growing into something new. Whether what emerges is the future of personal AI or a cautionary tale depends on choices that haven’t been made yet.

By developers. By AI companies. By regulators. By users deciding what risks they’re willing to accept for what capabilities.

The lobster is watching. And so is everyone else.

Stay tuned for Part 2 later this week.

[![](https://substackcdn.com/image/fetch/$s_!I2f8!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd2b2bbcc-e4f8-4f56-9b68-1998fe05dff7_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!I2f8!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fd2b2bbcc-e4f8-4f56-9b68-1998fe05dff7_1024x1024.png)
