---
title: "Executive Briefing: 33% of the world's helium supply just went offline. Your AI infrastructure plan doesn't account for it."
author: "Nate Jones"
published: 2026-03-29
url: https://natesnewsletter.substack.com/p/executive-briefing-33-of-the-worlds
subtitle: "Watch now | The largest debt-funded infrastructure buildout in history has an unpriced dependency on a noble gas."
audience: everyone
scraped_at: 2026-03-29 12:00:22
---

The largest debt-funded infrastructure buildout in history has an unpriced dependency on a noble gas.

The five largest US cloud and AI infrastructure providers have committed to spending between $600 billion and $700 billion on capital expenditure this year. Seventy-five percent of it is AI infrastructure. Google’s co-founders Larry Page and Sergey Brin have reportedly said they’d rather go bankrupt than lose the AI race. Goldman Sachs projects total hyperscaler capex from 2025 through 2027 will reach $1.15 trillion. Every dollar of that spending assumes the chips arrive on schedule. The chips come from fabs in South Korea and Taiwan. Those fabs require helium to operate their lithography machines, cool their wafers, and detect leaks in their vacuum chambers. There is no substitute for helium in any of these processes.

A third of the world’s helium supply came from a single industrial complex in Qatar. That complex was hit by Iranian missiles three weeks ago. It is offline. Parts of it are destroyed. The strait through which its output ships is closed. And the specialized containers that carry liquid helium vaporize their contents within 48 days. The clock is already running.

**This briefing covers:**

- **The three channels.** How a missile strike on a gas facility in Qatar reaches the GPU clusters training the next generation of AI models, through helium supply, LNG energy costs, and a geopolitical restructuring that favors Chinese compute economics.
- **The memory compounding effect.** Why the helium disruption arrives at the worst possible moment, into a semiconductor supply chain already in the grip of the most severe memory shortage in industry history.
- **The energy asymmetry and the oversupply that just evaporated.** Why the countries that fabricate the chips are not the countries that run the data centers, and why the LNG expansion that was supposed to make energy cheap by 2028 isn’t coming on time.
- **The geopolitical restructuring.** How Russia-to-China pipeline gas could structurally advantage Chinese semiconductor manufacturing over the US-allied fab ecosystem for the next decade.
- **The honest pushback.** The five strongest counterarguments to this thesis, addressed directly.

The full analysis follows, starting with what happened and ending with what to do about it.


## **LINK: [Executive Circle WhatsApp group](https://chat.whatsapp.com/LqpF3i5wDYv1EdraJYKplL?mode=gi_c)**

Join other senior leaders working through the same strategic decisions we cover here, sharing what’s actually working and what isn’t. No fluff, no LinkedIn energy. If you’re an Executive Circle member, we’d love to see you there.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

I’ve built a read-only MCP server that gives your AI — Claude, ChatGPT, whatever you use — direct access to my entire published content library. You connect once, and then the archive just *shows up* inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Think of it as a research assistant that’s already read every word we’ve put out — and it’s sitting inside the tool you’re already using. You can even paste in something you’re working on and ask it to surface the most relevant posts. It’s six read-only tools — search posts, read full posts, browse recent content, search prompt kits, read full kits, browse all kits. No write access, no drafts, no behind-the-scenes material. Just the published, finished work, available the moment you need it.

Setup takes about ninety seconds.

- Register once at [promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)
- Enter your access code (**executive\_circle**) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

This is, as far as I know, one of the first newsletters offering native AI integration as a subscriber benefit. Your subscription doesn’t just give you content anymore — it gives you that content embedded in your AI workflow, available the moment a question comes up. The way I think about it: your subscription now works inside your AI. Have fun!


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260325_r5y_promptkit_1)

This briefing identifies a structural problem. The prompt kit turns it into working tools for the decisions you’re actually making. The first prompt stress-tests your AI infrastructure capex against all three disruption channels and produces revised assumptions you can take into a budget review. The second audits your supply chain for hidden physical-input dependencies you haven’t mapped — the kind of concentration risk that helium represents, applied to your own vendor relationships. The third generates a procurement decision brief with a direct recommendation on whether to accelerate, hold, or restructure your compute purchases in the next 90 days. The fourth models three geopolitical scenarios for how the Eurasian energy restructuring plays out over one, three, and five years, and maps your strategic position against each. If your next step after reading this is a meeting where the same assumptions are still on the table, these are designed to prevent that.

Now, onto the briefing.


## **The situation**

On February 28, 2026, the United States and Israel launched strikes on Iran. Iran retaliated within hours, hitting US bases and energy infrastructure across the Gulf. On March 2, Iranian drones struck Ras Laffan Industrial City, the largest LNG production complex on Earth. Qatar halted all production and declared force majeure. On March 11, the Strait of Hormuz effectively closed. On March 18, after Israel struck Iran’s South Pars gas field, Iran hit Ras Laffan again. This time the damage was structural. QatarEnergy CEO Saad al-Kaabi confirmed that LNG Train 4 and Train 6 were damaged: 12.8 Mtpa of combined capacity offline, repair timeline of three to five years, $20 billion per year in lost revenue. Qatar’s North Field East expansion, 85 percent complete and targeted for late 2026, was suspended indefinitely.

As of this writing, the strait remains closed. The war is ongoing. No ceasefire is in place. And nobody can predict when this ends, which means nobody can predict when the rebuilding starts, which means the timeline for recovery is not just long but fundamentally uncertain.

That is the situation. What follows is the connection that almost nobody is making.


## **The wrong number**

Everyone is watching the LNG number. 12.8 Mtpa offline. $20 billion a year in lost revenue. Spot LNG prices up 60 percent. Brent crude over $100.

Those are the energy numbers. They’re the wrong numbers.

The right number is 35 to 48 days. That’s how long a specialized ISO container can hold liquid helium before it vaporizes. Qatar produced approximately a third of the world’s helium supply from three purification plants at Ras Laffan. All three have been offline since March 2. The containers that carry that helium to semiconductor fabs in South Korea, Taiwan, and Japan are either stranded in the Middle East or draining their contents into the atmosphere at a rate determined by the laws of thermodynamics, not the pace of diplomacy.

The helium story isn’t a footnote to the energy crisis. It is the mechanism by which a missile strike on a gas facility in the Persian Gulf reaches the GPU clusters training the next generation of AI models. And it reaches them through three independent channels that converge at the same time.

Channel one: helium supply to chip fabs, the physical input required at every critical step of advanced semiconductor manufacturing. Channel two: LNG prices and energy costs for the Asian fabs and data centers that produce and consume AI hardware. Channel three: a geopolitical restructuring of Eurasian energy flows that favors Chinese compute economics over the US-allied semiconductor ecosystem.

These channels don’t merely add. They compound. The result isn’t a temporary disruption. It’s a structural repricing of the physical cost of intelligence.


## **The gas that makes the chips**

Most people associate helium with birthday balloons. The semiconductor industry has a very different relationship with it.

Every advanced chip fabricated on Earth today passes through EUV lithography, the $200 million ASML machines that print transistor patterns at 3 nanometers. These systems generate enormous heat from their high-power laser sources. Helium’s thermal conductivity is six times higher than nitrogen’s. Because it’s chemically inert, it’s the only substance that can cool EUV optical elements without contaminating the process. The temperature stability requirement is measured in tenths of a degree Celsius, and tightening with each process generation.

Without helium, EUV scanners don’t run slowly. They stop. Completely.

That’s just one step. During plasma etching, when material is scraped away from a wafer to form transistor structures, fabs blow helium over the back of the wafer to draw heat away and maintain temperature uniformity. Georgetown University’s Center for Security and Emerging Technology researcher Jacob Feldgoise described the process to Fortune: you need to maintain constant temperature over the wafer being processed, and helium is the thermal conductor that makes that possible. Helium mass spectrometry is used for leak detection in vacuum chambers. Helium atoms are among the smallest in existence, capable of finding microscopic gaps that nothing else can detect. One undetected leak can destroy a wafer lot worth hundreds of thousands of dollars. Helium serves as an inert carrier gas in chemical vapor deposition, moving reactive precursors around without triggering side reactions.

In most of these applications, there is no substitute. No alternative gas. No workaround. The physics of the element, its thermal conductivity, its atomic size, its chemical inertness, are unique among all known substances. As Frost & Sullivan analysts noted this month: “Helium rarely features in boardroom discussions, yet it is non-substitutable in advanced semiconductor manufacturing.”

And the supply problem gets worse over time, not better: as chip geometries shrink and EUV adoption grows, per-wafer helium consumption is increasing. The most advanced fabs, the ones producing HBM memory chips and the logic chips that go into AI accelerators, consume the most helium. A 300mm EUV fab may consume 5,000 to 20,000 cubic meters per month, placing helium among the largest specialty gas line items in fab operating budgets. The purity requirement is 6N, 99.9999 percent. Only a handful of production sites worldwide can produce helium at that grade at commercial scale. Qatar’s Ras Laffan was one of them.

Now follow the chain.

Qatar’s three helium plants produced roughly 2.4 billion standard cubic feet per year. Combined: approximately 33 percent of global supply, according to the US Geological Survey. All three offline since March 2. QatarEnergy has confirmed that 14 percent of Qatar’s helium production capacity is permanently damaged, with reconstruction timelines of up to five years. The planned Helium 4 plant, targeting 1.5 billion standard cubic feet per year and slated for 2027, was over 50 percent engineered before the crisis. Its timeline is now unknown.

Helium is extracted from the natural gas stream during LNG processing by cryogenic distillation. It’s a trace component of North Field gas, physically inseparable from the LNG production process. When LNG production stops, helium production stops. You can’t run the helium plants without the liquefaction trains. They are the same facility.

That means the 12.8 Mtpa of LNG offline for three to five years isn’t just an energy story. It’s a semiconductor materials story. The LNG trains and the helium plants share the same timeline, the same reconstruction constraints, and the same dependency on shipping through a strait that is currently closed.

The issue isn’t whether this affects chip production. It’s which fabs, how much, and how fast.


## **Who’s exposed and how badly**

South Korea imported 64.7 percent of its helium from Qatar in 2025, according to the Korea International Trade Association. Nearly two-thirds of the helium supply for the country that produces roughly a quarter of the world’s memory chips came from a single industrial complex that is now offline and partially destroyed.

Samsung Electronics and SK Hynix, the world’s two largest memory chip manufacturers, operate their most advanced fabs in South Korea. These are the fabs producing HBM, the High Bandwidth Memory that goes into every NVIDIA GPU, every AMD AI accelerator, every Google TPU. HBM fabrication requires EUV lithography. EUV lithography requires helium. The dependency is direct and non-negotiable.

Taiwan’s exposure is different but no less severe. TSMC, which produces 90 percent of the world’s most advanced logic chips, imports the bulk of its energy as LNG and holds only 11 days of gas reserves. The country imports 97 percent of its energy. TSMC told reporters it doesn’t currently anticipate notable impact and is monitoring the situation. SK Hynix says it has diversified suppliers and secured inventory. The Korea Semiconductor Industry Association says short-term supplies are adequate.

Those are the public statements. Here’s the context underneath them.

Helium consultant Phil Kornbluth, probably the most cited independent voice in industrial gas markets, said at a Gasworld webinar that it is now hard to imagine anything less than a two-to-three month shutdown of helium production, with a four-to-six month period before the supply chain returns to normal. If the outage extends beyond roughly two weeks, he added, industrial gas distributors would be forced to relocate cryogenic equipment and revalidate supplier relationships, a process that could stretch over months regardless of when Qatari output resumes.

Helium spot prices have doubled. Contract surcharges are up over 30 percent. Roughly 200 specialized ISO containers are stranded. And the Seoul government has flagged 14 semiconductor supply chain materials with high vulnerability to the war. Helium is at the top of the list. Bromine, used in circuit formation with 90 percent of South Korean imports sourced from Israel, is number two.

Fitch Ratings put it plainly this week: “Asia’s semiconductor supply chain faces rising tail risk from helium tightness as the Iran conflict drags on and Qatar’s natural gas disruption persists.”

The question for anyone planning AI infrastructure deployment isn’t whether the fabs will shut down tomorrow. They won’t. Inventories provide a buffer measured in weeks to months. The question is what happens to throughput, yield rates, and delivery timelines over the next two to four quarters if helium supply doesn’t normalize. And the structural evidence says it won’t normalize quickly, because a third of global production capacity depends on infrastructure that takes three to five years to rebuild.


## **Memory was already the bottleneck**

I want to be careful not to overstate this, but the compounding here is what keeps me up. The helium disruption doesn’t arrive at a healthy semiconductor supply chain. It arrives at one that was already in the grip of the most severe memory shortage in industry history.

Before a single Iranian missile hit Ras Laffan, here is where things stood:

HBM capacity was sold out through 2026 across all three major suppliers: SK Hynix, Samsung, Micron. Not tight. Sold out. Every wafer allocated, every delivery slot spoken for. NVIDIA’s B300 GPU requires eight HBM modules, each containing 12 DRAM dies. That’s 96 dies per chip. A fully configured DGX B300 system with eight GPUs requires 768 DRAM dies just for HBM, not counting system memory.

A single silicon wafer yields roughly three times as much conventional DDR5 as HBM. Every HBM module produced means fewer commodity memory chips for laptops, phones, cars, everything else. The memory manufacturers made a rational business decision: HBM commands 3-5x revenue per wafer, and AI companies have locked up supply through multi-year contracts with guaranteed purchase orders. Samsung, SK Hynix, and Micron systematically reallocated manufacturing capacity toward HBM. Data centers now consume an estimated 70 percent of all memory chips produced globally.

TrendForce, the Taipei-based research firm that tracks memory pricing more closely than anyone, said the quarterly DRAM price increase in early 2026 was “unprecedented.” Prices up 50 to 55 percent in a single quarter. Bloomberg reported the memory industry has entered a structural shortage that multiple manufacturers say won’t ease before 2028. Intel CEO Lip-Bu Tan said at a Cisco conference in February: “There’s no relief as far as I know. There’s no relief until 2028.”

That was the baseline. Before helium.

Now compound it.

SK Hynix and Samsung are the primary HBM suppliers. They sit in South Korea. They imported 64.7 percent of their helium from Qatar. They are fabricating HBM at the most advanced process nodes, precisely the nodes that consume the most helium per wafer. If helium rationing forces even a modest reduction in fab throughput at Samsung or SK Hynix, the impact doesn’t land on commodity DRAM. It can’t. Those fabs are already prioritizing HBM and high-end server memory, the products that justify the capital expenditure. A throughput reduction tightens the supply of the exact memory that AI training clusters need most, at the exact moment when that memory was already the binding constraint on how fast those clusters could be built.

MS Hwang, research director at Counterpoint Research, pointed out that electricity accounts for about half of a data center’s operating expenses, and roughly half of that is used to power memory. Rising energy costs and rising memory costs arrive at the same budget line. They don’t offset each other. They stack.

The memory wall was already the binding constraint on AI scaling. Qatar just raised the wall. And the companies best positioned to address the shortage, by building new fabs, expanding capacity, ramping HBM4 production, are the companies most exposed to the helium disruption. The solution and the problem live in the same buildings, powered by the same gas.


## **The energy asymmetry**

The second transmission mechanism is energy cost, and the reason most analysis gets it wrong is that it assumes the impact is uniform. It isn’t. The asymmetry is the story.

European LNG prices rose more than 60 percent after the Strait of Hormuz effectively closed. European TTF gas prices followed, because Europe became structurally dependent on LNG imports after Russia cut pipeline supply in 2022. European electricity wholesale prices, set at the margin by gas-fired plants, rose proportionally. If you are planning or operating data center capacity in Europe, your energy cost assumptions from six months ago are already wrong.

In the United States, the impact is cushioned. The US is a net gas exporter. Its LNG export facilities are already running near capacity, which limits the price transmission from global markets to domestic supply. As Ken Medlock at Rice University’s Center for Energy Studies told Marketplace: the US simply cannot export more LNG than it already does, so the global price spike doesn’t fully propagate domestically. US hyperscalers operate most of their training clusters on domestic power at domestic gas prices.

But here’s the asymmetry that actually matters: the countries that fabricate the chips are not the countries that run the data centers. The US is insulated on energy. It is fully exposed on hardware. The chips come from South Korea and Taiwan. The memory comes from South Korea. These are energy-import-dependent economies sitting at the end of supply chains that run through the Strait of Hormuz. South Korea and Taiwan each account for 18 percent of global semiconductor production capacity. Taiwan imports 97 percent of its energy and holds 11 days of LNG reserve. When LNG import prices spike 60 percent in the countries where the chips are actually made, the energy cost increase flows directly into the price of AI compute.

For planners, the transmission lag matters. LNG spot prices have already spiked. Domestic gas prices in import-dependent countries start reflecting replacement costs within weeks. Electricity prices adjust over the following quarter. And the power purchase agreements being signed in the next 12 months for new capacity in Europe and Asia Pacific will be priced into a fundamentally different energy market than the contracts locked in during 2021-2023. That repricing hasn’t hit the capex models yet. It will.


## **The geopolitical restructuring**

There is a slower-moving dynamic here that may matter more than all three channels combined. It won’t show up in quarterly earnings. It will show up in the energy map of Eurasia over the next decade.

China held 27-year LNG contracts with Qatar through Sinopec and CNPC, the longest in the industry’s history, worth a combined 11 million tonnes per year. Those contracts are now under force majeure. China sources roughly 28 percent of its LNG from Qatar and up to 5 percent from the UAE, with cargoes routed through the Strait of Hormuz. One-third of China’s total LNG imports pass through a waterway that is currently closed.

Three weeks ago, China released its 2026-2030 five-year plan. The document calls for advancing preparatory work on “the central route of the China-Russia natural gas pipeline,” language widely interpreted as referencing the Power of Siberia 2, a 2,600-kilometer line from Russia’s Yamal Peninsula to China through Mongolia, carrying up to 50 billion cubic meters of gas per year.

The pipeline has been stalled for a decade on price disputes. China played hardball, reportedly pushing to pay close to Russia’s own subsidized domestic prices. Beijing slow-walked negotiations because it had leverage: abundant LNG supply from Qatar, Australia, and the US gave China options. The pipeline was a nice-to-have, not a necessity.

The Hormuz closure just destroyed that negotiating leverage.

As Erica Downs at Columbia’s Center on Global Energy Policy told RFE/RL: “The longer the disruption and the higher global LNG prices, the more attractive Power of Siberia 2 is going to look.” Aleksei Chigadaev at the New Eurasian Strategies Center called the five-year plan language “important signaling from the Chinese side,” the war in Iran highlighting how concentrated China’s gas security still is around maritime routes.

Follow the arithmetic. Power of Siberia 1 hit full capacity in December 2024 at 38 billion cubic meters per year. A Far Eastern Route delivers 12 billion cubic meters starting January 2027. Gazprom and CNPC signed an agreement in September 2025 to expand Power of Siberia 1 capacity from 38 to 44 bcm/year. Add Power of Siberia 2 at 50 billion cubic meters and total Russian pipeline gas to China approaches 100 billion cubic meters per year.

That is roughly what Russia used to send to Europe through Nord Stream.

The energy map of Eurasia doesn’t shift. It inverts.

The connection to AI is direct.

If China secures overland gas from Russia at below-market pipeline prices, Beijing solves two problems at once. Energy security for its industrial base. Energy cost advantage for domestic semiconductor manufacturing. China is pushing hard on domestic helium too. Guangdong Huate Gas has achieved mass production of 6N ultra-high-purity helium and secured ASML certification. China’s annual production capacity of ultra-high-purity helium has reached about 1.2 million cubic meters, small but growing fast, and growing specifically because the current crisis is accelerating investment.

The structural result, and I want to be clear-eyed about the uncertainty here since pipeline negotiations have stalled before, is that the countries most exposed to the Qatar disruption are US allies. South Korea. Taiwan. Japan. The country best positioned to insulate itself, through Russian pipeline gas, domestic helium production, and state-directed industrial policy, is China. This is not a conspiracy. It’s an emergent consequence of geography, alliance structures, and energy dependency patterns that predate the current conflict by decades. But the asymmetry is real and its implications for who can build AI infrastructure at what cost are concrete.

If you’re planning AI infrastructure and you’re not thinking about the divergence in physical-input costs between the US-allied semiconductor ecosystem and the Chinese one, you’re running models that assume a world that no longer exists.


## **The expected oversupply that just evaporated**

There is one more number most people aren’t tracking, and it may be the most consequential for long-range AI infrastructure planning.

Qatar’s North Field expansion was 85 percent complete before the conflict. Four new mega-trains producing 32 Mtpa of additional LNG, targeted for late 2026 startup. Behind that: North Field South, adding another 16 Mtpa by 2027-2028. North Field West, adding 16 Mtpa more by 2029-2030. Total planned new capacity: 64 Mtpa. Roughly a quarter of projected global LNG capacity by the end of the decade.

That expansion was widely expected to create oversupply in the global LNG market. Oversupply means lower gas prices. Lower gas prices mean cheaper electricity. Cheaper electricity means lower operating costs for every data center on Earth. Every capex model for AI infrastructure filed in the last two years assumed, explicitly or implicitly, that global gas prices would moderate as Qatar’s new capacity came online.

That assumption just died.

QatarEnergy CEO Saad al-Kaabi told Reuters the expansion could be delayed by over a year. The North Field East expansion has been suspended indefinitely. The war zone, the closed strait, the evacuated workforce, the multi-year equipment procurement lead times: all of it pushes the expected oversupply further into the future.

Every data center operator who built their multi-year energy cost projections around a gas-abundant 2028-2030 needs to revisit those projections, because the supply that was supposed to make gas cheap isn’t coming on time.


## **The honest pushback**

The skeptics on this thesis aren’t stupid. Let me address the strongest counterarguments directly.

“Samsung and SK Hynix say they’re fine.” They do. SK Hynix says it has diversified helium suppliers and secured sufficient inventory. TSMC says it doesn’t anticipate notable impact. These statements are probably accurate for the next four to eight weeks. The question is what happens at month three, month six, month twelve. Kornbluth’s estimate of a minimum two-to-three month production shutdown with four-to-six months to normalization is the most credible independent timeline I’ve seen. If he’s right, the “we’re fine” window closes sometime in May.

“The US has plenty of helium.” The US and Canada are significant helium producers. But the US Federal Helium Reserve ended crude helium sales in 2023, removing roughly 30 percent of historically stable supply. Russia’s Amur Gas Processing Plant, which was supposed to fill part of the gap, has been repeatedly knocked offline by explosions and technical problems. The available non-Qatar supply exists, but it cannot scale to replace a third of global production overnight. Qualification of new suppliers for 6N purity takes months, not days.

“China is building domestic helium capacity, so they’ll be fine too.” China’s current annual ultra-high-purity helium capacity is about 1.2 million cubic meters. That’s growing. Guangdong Huate Gas is ASML-certified. But 1.2 million cubic meters is a fraction of what China’s fab ecosystem requires. China imports 85 percent of its helium, with Qatar supplying 54 percent of those imports. China is less exposed than South Korea but more exposed than the public narrative suggests. The domestic push is real but measured in years of ramp, not months.

“Helium is a tiny fraction of chip cost. Fabs will just pay more.” This is true and largely irrelevant. As Georgetown’s Feldgoise noted, because helium is a small part of overall chip production cost, fabs will absolutely pay a higher price to secure supply. The problem isn’t cost. The problem is physical availability. You can’t pay more for helium that doesn’t exist. You can’t outbid a competitor for supply that is vaporizing in stranded containers in the Persian Gulf. Price is not the constraint. Molecules are.

“This will resolve in weeks, not months.” Maybe. The 2019 Gulf of Oman tanker attacks, a much smaller disruption, resolved in roughly 8-12 weeks. If the current conflict follows that pattern, Hormuz shipping could ease by late April or early May. But 2019 didn’t involve direct strikes on Ras Laffan. It didn’t permanently damage helium production capacity. It didn’t knock 12.8 Mtpa of LNG offline for three to five years. The shipping disruption might resolve in weeks. The production damage won’t.


## **What this means**

Let me be specific about what these converging channels imply for anyone deploying, financing, or planning AI compute in 2026 and 2027.

Memory costs will remain elevated through at least mid-2027, and the helium disruption makes the tail risk worse. HBM was sold out before this started. DRAM prices were already up sharply, 50 to 55 percent in the most recent quarter alone, on top of sustained increases through 2025. The fabs producing HBM are the fabs most exposed to helium rationing. Micron’s new Idaho fabs don’t produce until mid-2027. Samsung’s new HBM packaging line in South Korea is ramping into this headwind. The capacity relief the industry was counting on was already late. It is now later.

Energy costs for Asian fabrication will be structurally higher until either the strait reopens or alternative supply routes mature. PPAs signed in the next 12 months by TSMC, Samsung, and SK Hynix will reflect a fundamentally different gas price environment. That cost propagates into chip pricing, which propagates into server pricing, which propagates into the dollars-per-FLOP that every hyperscaler uses to model training economics.

US data center operators are relatively insulated on energy but fully exposed on hardware. Domestic gas abundance protects operating costs. It does nothing for the cost or availability of the chips and memory that go into the racks. The geographic mismatch between where compute is consumed and where compute hardware is manufactured creates a transmission mechanism that no domestic energy advantage can offset.

The expected LNG oversupply of 2028-2030, which was going to lower global gas prices and make AI infrastructure cheaper to operate everywhere, has evaporated. Every capex model filed in the last two years needs a structural revision to the energy price assumptions underlying the multi-year buildout plans that justify hundreds of billions in infrastructure spending.

The geopolitical restructuring favors China’s compute cost structure over the medium term. Russian pipeline gas, domestic helium production, state-directed industrial policy. The asymmetry isn’t decisive today. Over three to five years, it bends the cost curve.

And here is the number that contextualizes all of this: something like 0.5 to 1 percent of the world is currently a heavy AI user running agentic workflows. We are already maxing out available AI compute capacity at that adoption level. The forecasts call for a 10x to 100x increase in that number over the next few years. Where does the compute come from? The hyperscalers are willing to spend, but spending is not the constraint. The constraint is whether the chips and the data centers and the memory exist to absorb that spending, and this supply chain crisis puts a question mark on all three.

If you’re in IT procurement, the implication is concrete: buy compute this year. Don’t wait. Chip timelines are going to expand, memory costs are going to ratchet, and the structural cost envelope is not going to get friendlier later in the year. If you’re talking to hyperscalers about capacity, that conversation is about to get harder. Everyone is scrambling. You don’t want to be in a position where you’re stuck in the thick of the race, competing for chips and memory in a world where nobody knows the timeline for recovery.

And if you’re looking at this from outside the infrastructure layer entirely, if you’re not buying chips or provisioning data centers, understand that this reaches you too. Memory goes into your laptop. It goes into your phone. The same shortage that is constraining AI training clusters is the shortage that is raising the cost of consumer electronics across the board. This is going to be a price increase that nobody is happy with, and it will persist until new capacity comes online. That timeline just got longer.


## **The substrate of intelligence**

The machines that train the models that generate the revenue that justifies the capital expenditure that drives the chip orders that fill the fabs that consume the helium that comes from the gas that flows through the strait that Iran has closed. That entire chain is one sentence, and every link in it is load-bearing.

Helium cannot be synthesized. You cannot manufacture it. It is a noble gas. You extract it from geological formations where it has accumulated over billions of years, or you don’t have it. The EUV lithography machines that print every advanced AI chip on Earth require it. The memory fabs that produce every HBM module require it. There is no workaround. No software patch. No architectural innovation that routes around a noble gas that isn’t there.

A third of the world’s supply of that gas came from a single industrial complex on a peninsula in the Persian Gulf within range of Iranian missiles. The strait through which it ships is closed. The containers it ships in vaporize their contents within 48 days. The plants that produce it can’t operate without LNG trains that won’t be repaired for three to five years. The expansion that was supposed to increase supply by 60 percent is suspended indefinitely.

The AI industry has spent three years talking about scaling laws, parameter counts, context windows, and the race to AGI. It has spent three years arguing about whether we need more data, more compute, more parameters, or better architectures. It has not spent three minutes thinking about helium.

It should start now. Because the binding constraint on how fast you can scale artificial intelligence in 2026 is not the algorithm. It is not the training data. It is not even the capital, the hyperscalers have committed $650 billion and the checks are clearing.

It is a noble gas, produced as a byproduct of liquefied natural gas, from a single facility, on a peninsula in the Persian Gulf, that is currently on fire.

That’s the substrate of intelligence. And right now, the five-year timeline to rebuild it is the five-year timeline that determines how fast the entire industry can move.

Nobody on your Bloomberg terminal is showing you that chart. But the physics doesn’t care whether you’re watching.

[![](https://substackcdn.com/image/fetch/$s_!5FOc!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F36836414-e033-4ba2-a39d-0e163128ea8c_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!5FOc!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F36836414-e033-4ba2-a39d-0e163128ea8c_1024x1024.png)
