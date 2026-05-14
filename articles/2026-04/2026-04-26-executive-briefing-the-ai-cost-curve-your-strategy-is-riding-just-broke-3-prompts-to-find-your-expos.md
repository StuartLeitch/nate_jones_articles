---
title: "Executive Briefing: The AI cost curve your strategy is riding just broke + 3 prompts to find your exposure"
author: "Nate Jones"
published: 2026-04-26
url: https://natesnewsletter.substack.com/p/executive-briefing-the-ai-race-youre
subtitle: "Watch now | The inference economics nobody is pricing in — plus the prompts to audit your own exposure."
audience: everyone
scraped_at: 2026-05-14 14:33:00
---

The Ternus pick is being read as continuity. Apple lifer, quiet succession, stable handoff, business as usual. That is the wrong read.

On September 1, the top two executives at Apple will both be hardware people. Ternus, the CEO, ran hardware engineering. Srouji, the newly elevated Chief Hardware Officer, built Apple’s chip organization. For a company that spent fifteen years running a functional model where no single discipline owned a product, putting two hardware engineers at the top is not a personnel decision. It is a structural break. The board looked at the AI race Apple was losing and, rather than try harder at the thing that was failing, changed which game the company plays.

This is not really an Apple story. One piece of it is. The rest is about a cost-structure problem running beneath the surface of the entire AI industry, one that most strategic planning has not yet priced in. The question it forces is not which model is best. It is who owns the inference layer your organization depends on, what happens when the economics of that layer stop being subsidized, and whether the thing in your pocket turns out to matter more than the thing in the datacenter.

**This briefing covers:**

- **The org-chart break.** Why Apple’s functional model, the structure that produced the iPhone, was specifically built to lose the AI race, and why putting hardware on top is the board admitting it.
- **The cloud economics nobody is connecting.** The structural cost problem in AI inference that makes Apple’s on-device bet defensible, not just defensive.
- **The Apple II pattern.** Why the company that moved computing off the mainframe fifty years ago is making the same structural move with AI, and what that predicts.
- **The segment already building this themselves.** The compliance-driven buyers improvising local AI out of retail Mac Minis because the product they need does not exist.
- **What this means for your decisions.** Concrete implications for leaders evaluating AI cost structures, builders choosing where to ship, and practitioners rethinking the cost of inference.

Start with the org chart, because that is where the real story begins.


## **LINK: [Executive Circle WhatsApp group](https://chat.whatsapp.com/LqpF3i5wDYv1EdraJYKplL?mode=gi_c)**

Join other senior leaders working through the same strategic decisions we cover here, sharing what’s actually working and what isn’t. No fluff, no LinkedIn energy. If you’re an Executive Circle member, we’d love to see you there.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

A read-only MCP server that gives your AI direct access to my entire published content library. You connect once, and then the archive just *shows up* inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Think of it as a research assistant that’s already read every word we’ve put out — and it’s sitting inside the tool you’re already using. You can even paste in something you’re working on and ask it to surface the most relevant posts. It’s six read-only tools — search posts, read full posts, browse recent content, search prompt kits, read full kits, browse all kits — available the moment you need it.

Setup takes about ninety seconds.

- Register once at [promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)
- Enter your access code (**executive\_circle**) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

The way I think about it: your subscription now works inside your AI. Have fun!


## What the functional model couldn’t do

The whole point of Apple’s functional org was that nobody could ship a phone alone. Hardware, software, and services had to converge before anything left the building.

Most large technology companies are organized the opposite way, by product or by business unit, because product orgs scale cleanly and make P&L accountability simple. Jobs killed the product divisions when he came back in 1997. He thought letting a Mac team own the Mac and a printer team own the printers was how you ended up with twelve incoherent products instead of three good ones. So he reorganized the whole company by function — one hardware group, one software group, one design group — and made them converge on every product together.

The logic is straightforward. If a phone team owns the phone, the phone gets optimized for whatever the phone team is measured on. If no phone team exists, the phone gets optimized for the intersection of what hardware, software, and services can each defend. What you get, if it works, is the iPhone. A device where the three layers feel like one thing because they were argued into coherence before they reached you.

I have watched other companies try this structure. It fails without Apple’s specific culture of cross-functional deference. The model is not portable. It worked at Apple because Apple made it work.

The price of that model is speed. A functional org cannot sprint. No single executive can ram a product through. Consensus has to assemble horizontally. The decision loops are longer because more people have veto. This was a worthwhile tradeoff for fifteen years, because the category Apple competed in rewarded integration over velocity. Phones, tablets, watches, earbuds, headsets. All of them are integration plays. The functional model was a perfect fit.

AI broke the fit.

Generative AI is not an integration product category. It is a capability race. The thing that matters is how fast you can train the next model, how fast you can ship the next feature, how fast you can close the gap to whoever is out in front. The company with the fastest OODA loop wins, because the ground keeps moving under everyone’s feet. This is the opposite of the integration game. It is the game Apple’s org chart was specifically built to lose.

You can see this in the shape of the Apple Intelligence failure. It was not a hardware failure. The Neural Engine is competent. It was not a distribution failure. Apple ships to more devices than any AI lab will ever reach. It was a shipping-cadence failure. The promised Siri slipped. The features arrived slow and underwhelming. The gap to frontier AI products widened every quarter. Every quarter the frontier labs shipped, because their orgs are structured to ship. Apple’s org is structured to integrate. Integration takes time it did not have.

The board looked at that failure and had a choice.

Choice one: pick a software-velocity leader from inside and try to force the software and services orgs into the cadence of a frontier lab. Break consensus by putting software in charge. Accept that the functional model bends for AI the way it did not bend for anything else.

Choice two: decide Apple was never going to win a software-velocity race, and change the game.

They picked choice two. They put hardware on top. They did not try to fix the functional model by making it faster. They abandoned the premise that Apple needed to be fast in the software-velocity sense at all. The Ternus pick is the board saying the race they were losing is not the race they are going to run.

That is the actual news.


## The backdrop nobody is connecting

Choice two is defensible, rather than just defensive, because of what is happening in the rest of the industry while everyone is distracted by model launches.

The cloud-AI business does not work at scale. Not yet. Probably not soon. And the reasons are baked into the economics, not cyclical.

Start with training. The capex cycle for staying at the AI frontier is now measured in tens of billions per year and climbing. Each generation requires more compute than the last, because the scaling laws are still rewarding scale. The labs that want to stay at the frontier are locked into a capex treadmill where the cost of staying at the front doubles roughly every model generation, while the performance gains per doubling continue to compress. This is a known problem inside every lab. It is why fundraising rounds keep getting bigger.

Now stack inference on top of that. Every token a model generates consumes GPU time. GPU time has a marginal cost made up of power, cooling, hardware amortization, and opportunity cost against higher-margin workloads. That cost is higher than consumer AI subscriptions recover at today’s heavy usage patterns. OpenAI’s public statements have acknowledged this. The labs lose money on their highest-tier consumer subscribers. The subscribers are not abusing the service. The models are just expensive to run, and serious usage costs more to serve than any consumer price point recovers.

The gap has been hidden by three things. Investor capital subsidizing inference at a loss. GPU supply that has been expanding roughly in pace with demand. And the comfortable fiction that per-token prices will keep falling fast enough to close the gap before the subsidies run out.

All three of those are becoming less reliable. Investor appetite is not infinite; the labs know it. GPU supply is constrained by power and fab capacity more than by Nvidia’s willingness to ship, and power is the harder constraint. Per-token prices are falling but frontier capability is moving up-market faster than the price curve is moving down. The math is getting worse, not better, on a per-serious-user basis.

Where this ends, if it ends naturally, is a two-class AI structure. The top class gets real intelligence. Enterprise contracts, agents running for hours, long context, dedicated capacity, seven-figure annual spend. The bottom class gets metered, throttled, consumer-grade access, priced at what the labs can afford to serve rather than what users would actually want to use. The things you can do with AI depend on which class you can afford to be in.

This is not speculation. It is what the unit economics are already drawing. You can see the shape of it in every consumer-tier rate limit that has tightened in the last eighteen months. The labs are not being stingy. They are losing less money. It goes in one direction.

The pressure accelerated sharply after December 2025, when long-running agentic workflows moved from demo to daily use and token consumption per serious user climbed accordingly. The demand curve for inference is steepening at exactly the moment the cost curve is not falling fast enough to absorb it.

And the direction is bad for a consumer hardware company whose customers’ AI experience is about to be bounded by what the labs can afford to serve them. Apple cannot build its ten-year product story on top of a capability pipe that is, underneath, a loss-making business with a customer-tier squeeze built into its future. They need an alternative. They have exactly one available. They have to move the inference off the cloud and onto the device.


## The bet against the meter

Local AI is usually framed as a privacy play. Your data stays on the device, Apple does not see it, regulators approve. That framing is not wrong but it is a second-order benefit. The first-order benefit is cost structure.

On-device inference has a fixed cost. You paid it when you bought the phone. Once the model is running locally, asking it a thousand questions costs what asking it one costs. The economics are the economics of electricity, which is to say essentially nothing per query at consumer scale.

Cloud inference has a variable cost. Someone pays every time. Today that someone is mostly the labs, subsidized by their investors. Tomorrow it has to be passed on, because the subsidies run out and the capex has to be justified. The cost starts showing up in ways users notice.

Apple’s silicon is the escape hatch from that meter. Not for the frontier. Apple is not going to beat the best cloud model on its own chips, and probably will not try. The bet is narrower and smarter than that. The bet is on the long tail of things most people actually use AI for. Summarizing, drafting, transcribing, translating, searching their own stuff, answering questions about their own lives, running routine agents against their own data. If those tasks happen on the device, they happen outside the meter, outside the two-class structure, and the only thing a cloud model can offer is capability on the tasks where capability actually matters.

The market is already signaling this preference. The popularity of open-weights models like OpenClaw, which are designed to run locally, and the persistent stock-outs of Mac Minis among developers and prosumers building local inference setups, are not disconnected trends. They are demand for exactly the escape hatch Apple’s silicon provides. People want models they own on hardware they control, and they are buying the hardware before the ecosystem is even built.

The envelope of what runs locally has been expanding faster than most people have tracked. Three years ago, the idea that a useful generative model could run on a phone was dismissed. Today, quantized models in the 3-billion parameter range run at usable latency on current Apple silicon, and the envelope is expanding toward larger models that do a respectable job on short-context reasoning, summarization, and structured output. The distance from there to a 2027 phone running a 15-to-20-billion parameter mixture-of-experts model at interactive speed is not a leap of faith. It is a chip generation and a half. The Neural Engine architecture was designed for exactly this curve. Srouji has been designing for it since before it was clear what it would be for.

If you squint at where this curve lands by 2028, what you see is a device that can handle roughly eighty percent of what a typical user would ever ask an AI to do, without the request leaving the chassis. The remaining twenty percent, the hard problems that genuinely need frontier capability, can hand off to the cloud, pay the meter for that specific query, and come back. The cloud becomes a specialist, not a default.

This is not a new pattern for Apple. In the 1970s, computing was a metered service. You rented time on someone else’s mainframe. The Apple II did not beat the mainframe on capability. What it did was move a useful amount of compute onto a device you owned, and the power users who could suddenly run the machine all night without a meter invented the uses that defined the category. VisiCalc was not a mainframe product. It was a product that could only exist when compute was owned. The company making that move again is the company that made it the first time, and the structural shape is identical: metered service where heavy users are a cost problem, device ownership that moves marginal cost to zero, and a bet that the unmetered user invents the future the metered model cannot afford to permit. If the analogy holds, the frontier labs keep doing frontier work, but the center of gravity of what AI actually does in people’s lives moves to the device.

A cost-structure bet, dressed up as a product bet, dressed up as a CEO pick.

The people who benefit most are not casual users. They are practitioners. Under cloud economics, the power user is a cost problem. They run agents, hold long contexts, parallelize. Every one of those behaviors is a line item. The subscription tiers punish it. The rate limits enforce it. There is a soft ceiling on how much AI leverage a person can accrue, and serious practitioners know this ceiling intimately because they hit it every day. Under local economics, the ceiling shifts from economic to cognitive. Run the agent all night. Keep the context forever. Nobody’s meter is moving. The shift transfers AI leverage from the people who can afford tokens to the people who know how to use the device, and that second population is larger, with an upper bound set by literacy rather than a billing threshold.


## The accidental democratization, with limits

This is the part where I want to be careful about claiming too much.

Apple does not intend to democratize AI. Apple intends to sell iPhones. But the iPhone sale may turn out to be the mechanism by which useful AI reaches the billions of people the lab economics cannot serve. A democratization outcome produced by hardware unit economics being different from cloud unit economics, and the math flowing where math flows.

Now the limits.

The democratization is bounded by what an Apple device costs. A flagship iPhone runs a thousand dollars. An iPad runs more. This is democratic relative to a dedicated enterprise AI contract, but it is not democratic relative to what a billion people in emerging markets actually buy. The real beneficiaries of Apple’s bet are the top quarter of global consumers, not the global median. The global median runs Android, often on devices priced at a hundred and fifty dollars, with silicon that is three generations behind Apple’s. If local AI is the future, the companies that bring it to the global median are Qualcomm, MediaTek, and whoever builds the small-model ecosystem for those chips. Apple proves the concept. Others carry it down the price curve. This is still a democratization story, but it is not an Apple story. Apple is the proof case and the catalyst. The scaled version is someone else’s product.

The democratization is also conditional on Apple not taxing it to death. Apple will tax AI the way they tax everything else that runs on their silicon. The App Store cut, the developer program fees, the restrictions on what models can ship and how. A free-at-inference model on a 30%-taxed App Store is not free to the practitioner. It is a different pricing layer. Apple’s historical instincts about platform control will collide, hard, with the practitioner-leverage case I made two sections ago. If they tax it the way they taxed apps, the leverage stays with Apple. If they leave it open, the leverage flows to developers and users. Which instinct wins inside Apple is a real question, and it is genuinely unclear which way Ternus will lean. His background is hardware, not services. He has not spent his career optimizing for the App Store rake. But the services business is a lot of revenue, and revenue is sticky.


## What the developers are about to see

A developer building for a local-AI device is building something closer to a native application than a cloud wrapper. They have a model that lives in the user’s device, runs against the user’s data, and can be reasoned about like a library. The capabilities are bounded and known. The latency is bounded and known. The cost is zero. The data never leaves. What this developer can build is a different class of product. Agents that run continuously in the background. Assistants that read the user’s entire history. Tools that can be invoked thousands of times per hour without a thought. None of these are economically sane on cloud APIs today. All of them become sane on a chip you already own.

If Apple wins this, the interesting developer opportunity for the next five years is building those native-AI products for iOS and macOS. If Apple loses this, or taxes it into uselessness, the interesting developer opportunity is the open-source equivalent on Android and Linux. Either way, the category exists now in a way it did not exist a year ago, because the silicon has arrived to run it and the economics of the cloud alternative are degrading in plain view.


## The segment already trying to build this themselves

Here is a piece of the story the Apple coverage is not telling, and I know it because I hear it from inside the buying conversations.

A category of serious SMB-scale buyers is already actively trying to solve for local AI, and their problem is not cost. It is compliance. Law firms. Medical practices. Accounting and tax firms. Financial advisors. Therapists. Any professional whose obligations include a high bar on data confidentiality, whether that is attorney-client privilege, HIPAA, fiduciary duty, or therapeutic confidentiality, and whose clients would be within their rights to walk if their confidential information turned up being processed by a cloud-AI model owned by a company two layers removed from the relationship.

For this population, cloud AI is not a preference question. It is a professional-liability question. The firms thinking clearly about this have already decided they cannot use a public cloud AI service against client work product. The firms that have not yet thought clearly about it are going to be forced to, either by their malpractice carriers, their regulators, or the first bad press cycle involving a practice whose confidential records ended up training somebody else’s model.

And yet these firms are watching competitors who are less scrupulous, or just less careful, pull ahead using cloud AI in ways that are genuinely productive. The pressure to catch up is real. The pressure to stay compliant is real. These pressures collide.

The solution some of them are converging on is a rack of Mac Minis.

I’m not kidding. The M-series chips have enough memory bandwidth and Neural Engine capacity to run useful generative models locally. A handful of Mac Minis clustered together can deliver meaningful inference throughput for a small firm. The total hardware cost is a few thousand dollars, sitting in a closet, under the firm’s physical control, on the firm’s network, not talking to anyone outside. The data never leaves the building. The privilege is preserved. The compliance posture holds.

Apple has a cloud AI offering called Private Cloud Compute, sometimes cited as the privacy answer. It is not the answer for this segment. PCC’s cryptographic attestation prevents snooping, but the problem for regulated professions is not snooping. The problem is “can I represent to my client, my regulator, or my malpractice carrier that this data never left my physical control.” No cloud service lets you say that.

What these firms need is what Apple has not built. A rackable, datacenter-ready form factor for Apple silicon. Clustering and load-balancing software. Admin tools for IT teams running managed local inference. An identity layer that mirrors iCloud but stays on-premises. Compliance positioning, HIPAA BAAs, a curated model ecosystem targeted at regulated professional workflows. None of the infrastructure a law firm IT contractor would expect from an enterprise vendor.

So the firms that want it are improvising. They are buying Mac Minis at retail, writing their own orchestration glue, running open-weights models fine-tuned for their domain, and hoping the whole thing holds together. They are doing this because the alternative, cloud AI with an acceptable compliance story for their use case, does not exist at their price point and may not exist at any price point.

This is a demand signal hiding in plain sight. The professional services economy in the United States alone is measured in trillions of dollars and employs tens of millions of people, almost all of whom touch confidential client information as their core work product. A meaningful fraction of that workforce has a permanent need for AI that is not metered, not cloud-based, not flowing anyone else’s data through someone else’s model. They know it. They are trying to buy a solution. Nobody is selling it cleanly.

This demand signal makes the on-device bet bigger than the consumer argument alone implies. The same chips that make local AI work for a prosumer on an iPhone make it work for a four-lawyer firm running a rack in a closet. And it identifies a product gap Apple has not filled: a rackable Mac-silicon form factor, clustering software, admin tooling, compliance certifications, a managed model ecosystem. Either Apple builds that enterprise stack, or a company wraps Apple hardware in the layer Apple will not build, the way third parties used to wrap IBM hardware. The timing window is probably two to three years before Apple builds the stack themselves or the Qualcomm ecosystem catches up. A narrow, interesting window, and it is wide open right now.


## One structural tailwind everyone is under-weighting

One more observation before the takeaways, because it strengthens the rest of the argument.

The Valley has shipped on Apple hardware first for a decade. Instagram was iOS-only for eighteen months. Vine was iOS-first. Clubhouse was iOS-only for a year. ChatGPT’s first mobile app shipped on iPhone before Android. Threads, Bluesky, every premium consumer app of the last decade launched on iOS and ported later. The reasons are mechanical and boring. iOS users pay more. The hardware is standardized enough that QA is tractable. The developer tooling is better. The demographic that tries new consumer software skews heavily to iPhone. These reasons are structurally independent of Apple’s AI bet. They predate it by a decade.

But they compound with it in a way almost nobody is connecting.

If on-device AI becomes the category, the consumer software industry is already pre-configured to build on Apple first. The developer momentum is already there. The launch-day install base is already there. The pattern of “new consumer software debuts on iOS, then ports” means the native-AI products that will define the category for the next five years will be tested, refined, and scaled on Apple silicon before they ever touch a Qualcomm device. Apple does not need to convince developers to build for local AI. They need to ship silicon worth building for, and let a pattern that has been in place for fifteen years do its work.

A compounding structural advantage the analysis has been under-weighting. It is not just that Apple could win local AI. It is that the industry’s default launch path is already pointed at them.


## The caveats, honestly

Four reasons this could still go wrong.

The gap between local and frontier could matter more than Apple thinks. If the frontier keeps pulling away, good-enough-on-the-glass eventually stops being good enough even for common tasks. Apple has to be right that small models close the distance fast, and that the things people actually do fit under that curve. If the frontier develops capabilities that are qualitatively out of reach for local models, the two-class structure re-establishes itself on a different axis.

Apple may not have the model talent. Silicon is half the bet. The other half is the software layer that turns the silicon into useful intelligence. Apple has hardware engineering in abundance and model-research depth that is widely considered to be a generation behind the frontier labs. They will need to either acquire aggressively, partner seriously, or make their internal model teams dramatically better than they have been. None of those are sure things.

The platform tax could strangle the democratization story in the crib. I covered this above, but it belongs in the caveats, not a footnote. Apple’s default behavior with every platform they have ever controlled is to extract rents. If they do it with AI, the accidental democratization stops being accidental and becomes another managed channel.

And the org-chart break might not actually solve the problem that triggered it. Apple Intelligence failed because Apple could not ship software at the velocity the competition required. Giving hardware people more power does not fix that directly. It only fixes it if the bet pays off that on-device AI does not need that velocity, that the feature set stabilizes, that the software work becomes slower and more integrated, that the race Apple could not win becomes a race they do not have to run. If that is wrong, the new org is worse at the thing the old org was already failing at. The retreat only works if the terrain they are retreating to is actually defensible. The terrain has to be there.


## Three audiences, three responses

Three audiences. Three different shapes of response.


### For leaders

**Watch for games you cannot win, and be willing to change which game you play.** Most boards respond to losing by trying harder at the thing they are losing at. Apple responded by changing the premise. The equivalent move in your own organization is harder than it sounds. Notice when you are optimizing a system whose premise is wrong, and be willing to restructure rather than push.

**Watch for structurally unprofitable business models being treated as temporary.** The cloud-AI unit economics case in this piece is not consensus yet, but it should be. The labs are treating a loss-making inference business as a capex-and-subsidy ramp to profitability. The curves suggest it might be a floor rather than a ramp. If you are making strategic decisions that depend on frontier-capability AI getting cheaper faster than it gets smarter, you are betting on a curve that is not currently bending that way. Plan for the alternative.

**The acquisition targets are on-device capability, not cloud wrappers.** If the thesis holds, the companies worth owning over the next three years are the ones with small-model research talent, quantization and inference-optimization expertise, and the ability to ship useful intelligence inside tight compute envelopes. The ones being valued highest right now are cloud-API wrappers, which are a squeezed middle layer in both the metered-cloud and local-AI futures. The right portfolio is weighted the other direction.


### For builders

**The iOS-first default compounds with the on-device bet.** If you are starting something now, the question is not whether to ship on iOS first. The question is whether the product you are building is native-AI enough to justify existing at all.

**The category is native AI, not AI-enabled.** The interesting opportunity is not “put GPT in my app.” It is the class of products that only makes economic sense on zero-marginal-cost inference: continuous background agents, assistants that read a user’s entire history, tools invoked thousands of times per hour. The companies that will matter in five years are building these now.

**The SMB compliance segment is a shippable startup thesis today.** The buyers already exist. They are already trying to hand over money. Nobody is taking it cleanly yet. Two-to-three-year window before Apple builds the stack or the Qualcomm ecosystem closes in from below.

**Architect for portability anyway.** Apple’s platform-tax history is not a reason to avoid building on their stack. It is a reason to design so the model layer is replaceable if the economics change. The application logic, the user data, the workflow design are yours. The model underneath is a component. Teams that entangle their product with one specific model or one specific runtime are making the same mistake cloud-API thin wrappers are making, at a different layer.

**Invest in the skills that matter for this world.** On-device deployment, quantization, small-model fine-tuning, Apple’s ML frameworks, local agent architecture. These are not glamorous skills right now. They will be in two years. The builders who are fluent when the category arrives at scale are the ones who will ship the products that matter.


### For prosumers

**Your ceiling is about to stop being your subscription tier and start being your literacy.** Everything in your current workflow that is shaped around preserving tokens, keeping contexts short, running one agent at a time, not reading big documents because the model will not hold them, is shaped by a constraint that is about to loosen a lot for common tasks. Unlearning those habits now is a real thing to do. Ask the model to read more, remember more, run longer. Train yourself out of the habit.

**Data hygiene gets more valuable.** A local model is most useful when it can read all your stuff. All your stuff is currently scattered across a dozen services, most of them hostile to export. The work of consolidating your personal knowledge, notes, calendar, messages, email, and documents into a form a local model can actually traverse pays compounding returns. The people who have been doing this already are about to have an absurdly good year.

**Hardware generation becomes a productivity variable again.** If the thesis holds, the Neural Engine generation you are on will matter for what you can actually do. The prosumer case for buying the flagship and upgrading more often gets stronger than it has been since the early iPhone era.

**Make your workflows model-agnostic.** If you are building your AI-adjacent workflows around a specific cloud product right now, you are building on a cost curve that is likely to tighten on you. Design your workflows so the intelligence underneath is swappable. This is the same architectural advice I gave builders, applied to a personal stack. The principle is the same. The intelligence is a utility, and utilities get cheaper or more expensive depending on who owns them.


## The retreat that might work

The Ternus pick is a retreat that might succeed. Apple broke its own company, a company that had worked for fifteen years, because the company it was could not win the AI race on the terms the industry set. The new company has a chance on different terms, because the hardware economics of AI are sharply different from the cloud economics of AI, and the industry has been quietly underpricing that difference.

The rest of the industry is running the other play. Bigger datacenters. More frontier capability. More compute, more capex, more per-token revenue. They might be right. Frontier capability matters, and someone has to build it, and the compute buildout is not wasted capital even if the consumer economics never close.

But the org chart at Apple just said out loud what most of them will not. The cloud is expensive. The meter is real. The thing in your pocket might be the thing that matters. And the company that figured out how to put useful computation in your pocket once before might be the company that does it again.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260422_noj_promptkit_1)

The argument above only matters if it changes a decision you make this week. Most readers will agree with the analysis, file it under interesting, and continue running an AI strategy that depends on a cost curve that isn’t bending. That’s the failure mode these prompts exist to interrupt. Three of them, run in sequence: the first inventories every AI dependency in your organization including the ones embedded in tools you don’t think of as AI purchases, the second classifies which of those dependencies have quietly become infrastructure you can’t easily exit, the third pressure-tests the premise your AI strategy is actually optimizing for against three structural shifts that are already underway. The output of the third prompt is a board-ready memo with a hold, hedge, or restructure recommendation. The work the prompts force is uncomfortable on purpose. You can’t pressure-test a strategic premise honestly until you’ve written down what you depend on, what you’re paying, and which of those dependencies you committed to without realizing you were committing.

[![](https://substackcdn.com/image/fetch/$s_!aAYs!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F96164978-e1f9-453c-9661-9da7495ab48e_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!aAYs!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F96164978-e1f9-453c-9661-9da7495ab48e_1024x1024.jpeg)
