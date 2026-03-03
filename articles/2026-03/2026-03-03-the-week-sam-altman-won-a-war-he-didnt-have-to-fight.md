---
title: "The Week Sam Altman Won a War He Didn’t Have to Fight"
author: "Nate Jones"
published: 2026-03-03
url: https://natesnewsletter.substack.com/p/openai-raised-110b-and-the-pentagon
subtitle: "Watch now | The Week Sam Altman Won a War He Didn’t Have to Fight"
audience: everyone
scraped_at: 2026-03-03 12:00:16
---

# The Week Sam Altman Won a War He Didn’t Have to Fight

Friday night, while Anthropic CEO Dario Amodei was still drafting his principled stand against the Pentagon, Sam Altman announced on X that OpenAI had signed a deal to deploy models in the classified network of the Department of War, as the Trump administration has renamed the Pentagon. Hours later, the United States and Israel began bombing Iran. By Saturday morning, Claude was the number-one app in the App Store and Anthropic was designated a supply-chain risk to national security — an action that legal analysts say is without public precedent for an American company.

These events are connected by a logic most commentary has missed. Dario Amodei misread the room. He played a principled hand at the wrong table, at the wrong time, with the wrong counterparties — and the result will reshape power dynamics across the AI industry for the next eighteen months. Sam Altman played a quieter game and walked away with the largest private funding round in history, a fat defense contract, and the structural position to make OpenAI the gravitational center of American AI infrastructure.

**Here’s what’s inside:**

- **The Iran strikes and the tool you can’t unplug.** Why Claude was too embedded in active combat operations to remove — even after a presidential order.
- **What Dario said vs. what the market heard.** The technical objection that got read as a political one, and why the defense establishment punished it.
- **The $110 billion round and the circular capital machine.** How the largest private financing in history actually works, who needs what from whom, and where the structural risk lives.
- **The hyperscaler hedging play.** Amazon, Microsoft, and Google are backing every horse — and what that means for anyone building on their platforms.
- **What builders should do with all of this.** Vendor risk, the 10x compression question, and the middleware margins that are about to get very thin.

Let me walk you through how these pieces connect — because the through-line is the part most coverage missed.


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260302_23t_promptkit_1)

The problem with an article like this one is that it’s dense enough to feel important and broad enough to feel paralyzing. You finish reading and think: *okay, but what do I actually do with this?* I’ve watched that happen with every piece I’ve written about industry power shifts — the analysis lands, but the personal translation doesn’t, because the distance between “OpenAI raised $110 billion” and “here’s what I should change about my vendor strategy on Tuesday” is real, and most people don’t cross it on their own.

This prompt kit exists to close that distance. Four prompts, each designed around a different decision surface: your career exposure, your AI vendor dependencies, whether your role or product survives a 10x intelligence jump, and whether your financial exposure to the AI capital cycle is more concentrated than you realize. The vendor risk audit in particular came from watching teams discover — after a procurement freeze, not before — that three of their “independent” tools all resolved to the same model provider on the same cloud platform. The prompts will ask you specific questions about your situation before producing anything, because generic analysis of a week like this one is worse than no analysis at all.


## Start with Iran

The Wall Street Journal reported that U.S. Central Command used Claude for intelligence assessments, target identification, and combat simulations during the strikes on Iran — just hours after Trump ordered all federal agencies to stop using Anthropic’s technology. The strikes were a joint U.S.-Israeli operation that killed Iran’s Supreme Leader, Ayatollah Ali Khamenei, at a government compound in Tehran. The model was too deeply embedded in operational workflows to rip out in real time, even after a presidential order.

This wasn’t new. Claude had been used in the January operation to capture Nicolás Maduro in Venezuela, deployed through Anthropic’s partnership with Palantir on Amazon’s Top Secret Cloud. The Pentagon had awarded contracts worth up to $200 million through the Chief Digital and AI Office for frontier AI prototyping. But the classified deployment — the sensitive work with real operational stakes — was running on Claude, the only frontier AI model then integrated into classified military networks.

An Israeli product manager named Yonatan Back built StrikeRadar — a real-time dashboard calculating the likelihood of U.S. strikes on Iran — using Claude to write the entire system in six hours. No coding background. The tool pulls flight cancellation data, military aircraft movements, and news feeds into a probability score. That’s the capability envelope we’re now operating in.

AI models are no longer supplemental to intelligence operations. They are load-bearing. They compress the observe-orient-decide-act loop so that real-time reactions are feasible where they previously took days of analyst work. A task that once required a team at Langley parsing satellite imagery for a week is now handled by frontier models in hours, with simulations of entire military campaigns running in parallel. Multiple reports confirm that Claude was integrated into classified networks via both Palantir and Amazon Web Services, and that it had been cleared for classified military and intelligence tasks well before the current controversy.

That acceleration drove the Pentagon’s demand for unfettered access. After the Maduro raid, an Anthropic employee reportedly asked a Palantir counterpart how Claude was used. That inquiry set off the chain of events we’re watching now. Defense Secretary Pete Hegseth gave Anthropic a deadline to allow unrestricted use for any lawful military purpose. Anthropic refused. Hegseth designated it a supply-chain risk and announced a six-month phase-out.

But the Iran strikes proved you cannot phase out a tool running inside active combat operations. Inc. magazine reported that observers say Claude’s use in the wake of the ban demonstrates that AI is so deeply embedded in military planning that disentangling it would take far longer than six months. The Pentagon has since reached deals with OpenAI and xAI for classified settings, but military officials and AI experts say fully replacing Claude across all systems could take months — and that assumes the replacements perform at the same level on the specific intelligence tasks Claude was optimized for.


## What Dario said vs. what the market heard

In his February 26 statement, Amodei wrote that he “believes deeply in the existential importance of using AI to defend the United States.” He said Anthropic supports 98–99% of Pentagon use cases and that partially autonomous weapons are “vital to the defense of democracy.” Then he said something that Sarah Shoker, former head of OpenAI’s geopolitics team, flagged as deeply significant: “Even fully autonomous weapons... may prove critical for our national defense.” His objection isn’t moral. It’s technical. He’s saying the models aren’t reliable enough yet.

This is not the principled anti-war stance Claude’s new App Store fans think they’re downloading. Amodei is openly signaling that his position on autonomous weapons is contingent and time-limited — a function of model capability, not ethics. When the models get reliable enough, the red line moves.

Shoker made another point that deserves emphasis: Anthropic’s demand for human-in-the-loop oversight on autonomous weapons is already codified in U.S. policy. DoD Directive 3000.09 requires “appropriate levels of human judgment” for autonomous and semi-autonomous weapons systems. Anthropic was asking for what the law already provides. So why did the Pentagon refuse to put it in the contract? Likely because writing it down gives Anthropic a legal basis to object to specific deployments. The ambiguity is the point. “All lawful purposes” preserves maximum optionality for the government; named carve-outs constrain it.

And we have no idea what technical safeguards actually exist on these models in classified environments. The drone swarm trial Bloomberg reported on — OpenAI models in a Defense Innovation Unit trial for autonomous drone coordination — illustrates the problem. OpenAI said the trial would comply with its usage policy, but the policy can be read multiple ways depending on whether you consider an AI tool in a kill chain to be “helping build a weapon” or merely an isolated software component. Google ran the same playbook with Project Maven in 2018, claiming their object detection software was “non-offensive.” That framing has never held up well — it misunderstands how distributed systems actually work in warfare. The AI component that processes sensor data, identifies targets, and recommends engagement decisions is not meaningfully separable from the weapon that fires.


## How Altman played it

OpenAI’s deal was announced Friday night, hours after Anthropic’s designation. Altman admitted the deal was “definitely rushed” and that “the optics don’t look good.” But the substance matters. OpenAI’s agreement includes three stated red lines: no mass domestic surveillance, no autonomous weapons, no high-stakes automated decisions like social credit systems. Nearly identical to what Anthropic was asking for.

The difference is implementation. OpenAI’s Katrina Mulligan, head of national security partnerships, argued that the deployment architecture — cloud-only, with OpenAI engineers embedded alongside the Pentagon — makes it structurally harder for models to be integrated directly into weapons hardware. Critics, including Shoker, dispute whether this distinction is meaningful in practice, since cloud inference can still feed targeting and command systems. At an all-hands, staff were told the government agreed to let OpenAI build its own safety stack.

Pentagon undersecretary Emil Michael responded to Amodei’s public statement by calling him a “liar” with a “God complex” who was “ok putting our nation’s safety at risk,” according to Axios. The tone confirmed what the defense establishment was signaling: this was personal.

Dario went public. Sam went private. The defense establishment rewards deference and punishes public defiance. Defense contractors operate on a simple social contract: you build what the government asks for, you comply with the law, and you handle disagreements privately. You do not go to the public to gain leverage in a contract dispute with the Department of Defense.

Sam played the institutional game. He negotiated behind closed doors, accepted the framework the Pentagon wanted, built in technical safeguards rather than contractual vetoes, and asked the government to extend the same terms to all AI companies — including Anthropic. Whether those technical safeguards are as robust as Anthropic’s contractual demands is a genuinely open question. But in the contracting world, the question that matters is: did you work with us or against us?


## The $110 billion round

On the same day as the Pentagon deal, OpenAI announced a $110 billion funding round — the largest private financing in history. The round values OpenAI at $730 billion pre-money, $840 billion post-money. For context, total U.S. venture capital investment across all startups in 2023 was $170 billion. OpenAI raised 65% of that in a single transaction.

Amazon committed $50 billion, though only $15 billion is unconditional; the remaining $35 billion is contingent on an IPO or an undisclosed “AGI milestone.” Alongside equity, the companies expanded their cloud agreement by $100 billion over eight years. AWS becomes the exclusive third-party distributor for OpenAI Frontier, the enterprise agent platform. They’re also co-developing a “Stateful Runtime Environment” on Bedrock — a persistent context layer for AI agents to maintain memory across sessions. The layered logic: Amazon invests equity to guarantee a cloud contract, the cloud contract locks in Trainium chip consumption, and chip consumption funds Amazon’s long-term silicon ecosystem bet.

Nvidia invested $30 billion, replacing an earlier $100 billion letter of intent that collapsed in January 2026. Jensen Huang had privately told associates the original figure “was never a commitment” and had privately criticized OpenAI’s “lack of financial discipline.” The $30 billion is paired with deployment of Nvidia’s Vera Rubin architecture at scale — three gigawatts of inference capacity and two of training.

SoftBank committed $30 billion, bringing total OpenAI investment to $64.6 billion. As chairman of the $500 billion Stargate project and majority owner of ARM, Masayoshi Son is assembling an integrated stack from chip IP to data centers to frontier models. To fund these investments, SoftBank has been liquidating positions aggressively: selling its Nvidia stake, leveraging its majority ownership of ARM for borrowing capacity, and exploring a public listing of its PayPay mobile payments unit. S&P Global Ratings has warned that the pace of investment is pressuring SoftBank’s creditworthiness. But Son’s conviction is unshakeable. In an interview with TIME, asked what AI will transform, he replied: “Everything, every industry. Even farming or fishing or fashion or media. This is not a bubble.”

Notably absent: Microsoft. The company that invested $13 billion and holds a 27% stake chose not to participate. Microsoft renegotiated its partnership in late 2025, removing its right of first refusal on new cloud workloads and committing OpenAI to paying a 20% revenue share through 2032. Microsoft traded exclusivity for a perpetual tax on OpenAI’s growth.

Bloomberg’s investigation published in January 2026 mapped the full circular financing structure. In the late 1990s telecom boom, carriers sold each other network capacity and booked the transactions as revenue, even when the deals largely washed out. Congressional investigators later examined this at Qwest and Global Crossing, both of which restated revenue tied to swap deals. Bloomberg’s analysis found structural parallels: Nvidia invests in OpenAI, which buys Nvidia chips, which Nvidia books as revenue. Amazon invests in OpenAI, which commits to consuming AWS infrastructure, which Amazon books as cloud revenue. SoftBank invests in OpenAI, which deploys on Stargate infrastructure that SoftBank co-owns. Each participant’s growth metrics are simultaneously inflated by the same underlying pool of capital. Whether you call it a flywheel or a house of cards depends entirely on whether end-user demand materializes at the scale these commitments assume.

Asset manager Janus Henderson called the arrangement a “virtuous circle” that helps line up suppliers, builders, and customers to meet exploding demand for computing power. Venture capitalist Paul Kedrosky, who covered the telecom boom as a technology analyst, said AI capital spending is climbing toward levels last seen at the peak of the late-1990s fiber-optic buildout, with the added risk that facilities using today’s chips could become obsolete before generating a return on investment.


## Stargate and the infrastructure buildout

Stargate — a joint venture with SoftBank, Oracle, and Abu Dhabi’s MGX — targets $500 billion in AI infrastructure and ten gigawatts of capacity by 2029. The Abilene, Texas campus is operational. Phase one delivered 200+ megawatts in September 2025. Phase two (roughly another gigawatt) is expected mid-2026. Oracle will deploy over 450,000 GB200 GPUs there under a fifteen-year lease.

Beyond Abilene, sites are announced or under construction in New Mexico, Ohio, Michigan, Wisconsin, and additional Texas locations. The Michigan Public Service Commission approved 1.4 gigawatts of power delivery for the Saline Township site in a 3–0 vote after DTE Energy filed an ex parte motion that bypassed public opposition hearings. Total planned capacity across all announced sites now exceeds eight gigawatts with more than $450 billion committed.

Separately, OpenAI has a deal with Broadcom for ten gigawatts of custom inference chips (”Titan”), committed to six gigawatts of AMD MI-series GPUs, and retains the Nvidia partnership at ten gigawatts. Total: roughly twenty-six gigawatts across three chip architectures plus custom silicon. For perspective, that’s the electricity consumption of a mid-sized country. Sam Altman noted that OpenAI went from two megawatts to 200 megawatts to just over two gigawatts by the end of 2025 — and said that even if they had thirty gigawatts today, demand would saturate it “relatively quickly.”

Reported cloud commitments are equally staggering: $250 billion to Microsoft Azure through 2032, $138 billion to AWS, and roughly $300 billion to Oracle. Combined: nearly $700 billion in contracted compute — figures that, if accurate, represent an unprecedented concentration of infrastructure spending.

Against this spending, OpenAI’s annualized revenue topped $20 billion by late 2025 (actual 2025 revenue: ~$13 billion). Projections show $100 billion by 2029 and $280 billion by 2030. Losses are projected at $14 billion for 2026, with cumulative losses of $44 billion through 2028 and profitability not until 2029. According to financial disclosures reported by The Information, gross margins have compressed from roughly 40% in 2024 to 33% in 2025 as inference costs exploded to $8.4 billion, projected to rise to $14.1 billion in 2026. HSBC analysts estimated OpenAI still faces a $207 billion funding shortfall to power its growth plans even after everything already committed. An IPO at a valuation approaching $1 trillion is planned for late 2026 or 2027 — the real endgame for the current capital structure. SoftBank’s 11% stake, Amazon’s equity position, Nvidia’s shares — all of them need public markets to realize their returns. The Pentagon contract, the infrastructure buildout, the revenue growth — everything is pointed at a single event: convincing public market investors that AI compute is the next electricity and OpenAI owns the grid.


## The hyperscaler hedging play

Amazon has invested $8 billion in Anthropic and $50 billion in OpenAI. It built Project Rainier, an $11 billion data center where Claude trains on Trainium2 chips. Anthropic’s AWS revenue is projected to grow from $3.9 billion in 2025 to $25 billion by 2027. Amazon doesn’t have a horse in the model race — it has a cloud to sell, and this is the hyperscaler playbook: don’t pick sides, sell infrastructure to everyone, and let the model layer commoditize while you own the compute layer. AWS holds 28% of the global cloud market — larger than either Microsoft at 21% or Google at 14% — according to Synergy Research Group.

Anthropic’s financial position is stronger than the supply-chain-risk narrative implies. Its reported $14 billion annualized revenue and tenfold year-over-year growth would be the envy of any startup. The November 2025 deal with Microsoft and Nvidia brought up to $15 billion in additional investment, pushed the valuation to $350 billion, and made Claude available on all three major cloud platforms — the only frontier model with that breadth of distribution. A $30 billion Azure compute commitment gives Anthropic access to Nvidia Grace Blackwell and Vera Rubin systems at scale. On paper, Anthropic has more cloud provider diversification than OpenAI. But revenue diversification is different from cloud diversification. Anthropic’s enterprise contracts — the recurring revenue that justifies the valuation — are the asset most directly threatened by the designation. And unlike OpenAI, which now has a defense contract anchoring a broader government procurement pipeline, Anthropic’s government business is being unwound. That pipeline doesn’t disappear. It flows to the company the Pentagon considers cooperative.

Microsoft holds a 27% OpenAI stake, takes a 20% revenue share, and has a $250 billion cloud contract — but also invested $5 billion in Anthropic, spends $500 million per year as an Anthropic customer, and told Azure salespeople that selling Anthropic models counts toward quotas at the same incentive rate as OpenAI models. Microsoft CEO Satya Nadella was explicit about the strategy: “We’re increasingly going to be customers of each other.” The relationship looks like an alliance from the outside, but it’s a platform play — Microsoft wants Azure to be the compute layer for every frontier model, just as AWS does, and it doesn’t particularly care which model wins as long as both burn Azure cycles. Microsoft distributes Claude through Microsoft Foundry alongside ChatGPT in GitHub Copilot, Microsoft 365 Copilot, and Copilot Studio. Google invested $3 billion in Anthropic for a 14% stake and provides Anthropic more than a gigawatt of compute capacity coming online this year, and dropped its pledge not to use AI for weapons. Every hyperscaler is structurally incentivized toward neutrality. Builders who assume their cloud provider’s loyalty to any single model are making a dangerous bet.


## Enterprise fallout

The supply-chain-risk designation requires all defense contractors to demonstrate their systems don’t rely on Anthropic products. Even if Anthropic prevails in court, the chilling effect on procurement is immediate. Fortune quoted analyst Shenaka Anslem Perera: “It will take years to resolve in court. And in the meantime, every general counsel at every Fortune 500 company with any Pentagon exposure is going to ask one question: is using Claude worth the risk?”

Amodei told CBS he thinks the impact will be “fairly small” and that the designation was “designed to create fear, uncertainty, and doubt.” He may be right about the intent. But FUD works. Enterprise procurement is governed by risk committees, not admiration.

On the consumer side, Claude is number one in the App Store. Daily signups have tripled since November. Paid subscribers have more than doubled in 2026. But the App Store chart is a snapshot of download velocity, not sustained usage. ChatGPT has surpassed 900 million weekly active users and 50 million paid subscribers. OpenAI counts more than nine million paying business users and one million business customers. Its Codex tool has tripled its weekly user base since January to 1.6 million. Consumer enthusiasm driven by a geopolitical controversy is not a durable competitive advantage. Enterprise seats drive predictable recurring revenue in a way that consumer subscriptions don’t. The enterprise contracts are where this fight will be won or lost.


## Why Amodei was right on substance and wrong on tactics

Amodei’s stated positions are substantively reasonable. Mass domestic surveillance is a legitimate concern — as he pointed out, it “isn’t illegal. It was just never useful before the era of AI.” Fully autonomous weapons without human oversight carry real catastrophic-failure risks.

But this wasn’t a seminar. This was a negotiation with a wartime administration that had just used Claude to capture a foreign leader and was about to bomb Iran. Amodei took the negotiation public, published a statement implying the Pentagon might misuse his technology, and framed his red lines as a check on government power. In the defense contracting world, this is so far outside norms it marked the deal dead on arrival. The Pentagon’s unprecedented escalation — designating an American company a supply-chain risk — tells you exactly how far outside norms his approach was perceived to be.


## What builders should do

The model layer is commoditizing. The infrastructure layer is consolidating at breathtaking speed. The regulatory layer is being shaped by defense contracts and executive orders, not legislation. If your product strategy only considers which model is best on benchmarks, you’re working with about 20% of the relevant information.

Cloud providers are playing every side. AWS backs Anthropic and OpenAI. Google backs Anthropic and has its own defense contracts. Microsoft backs both. They are allies of token volume, not allies of any single model provider. Build accordingly — and understand that your cloud provider’s partnership announcements are about their revenue, not your stability.

The Frontier distribution deal signals the next phase of consolidation. When your cloud provider also distributes the model and the agent layer, middleware margins get thin fast. The Stateful Runtime Environment creates lock-in at a depth that simple model swaps can’t undo. The more agentic your deployment, the harder it becomes to switch.

Anyone downstream of a hyperscaler, living off a shim between their infrastructure and the customer, should understand that the shim is getting thinner. Bridging providers with proprietary data or workflows is a stronger position — but only if the moat survives a tenfold gain in intelligence.

Government contracts are the most durable revenue in technology. Multiyear, sticky, and reinforced by security clearances that create switching costs no commercial contract can match. If OpenAI is the preferred vendor for classified AI, every adjacent procurement flows toward its ecosystem. Pentagon validation de-risks investment, investment funds infrastructure, infrastructure enables models, models win more contracts.

The circular financing structure carries real risk. OpenAI projects $14 billion in losses for 2026 and cumulative losses of $44 billion through 2028. The $280 billion revenue target by 2030 would be unprecedented from a $13 billion base. If revenue disappoints, the capital structure that funds the infrastructure begins to strain — and the market structure determining compute access and pricing could shift rapidly.

Ask yourself the ten-times question. If models get ten times smarter in the next eighteen months, does your integration layer become more valuable or less? Industries built on layers of human coordination — project management, consulting, staffing, compliance — face not just augmentation but compression of the organizational structures that justify their existence. The enterprise tools that thrive next will enable smaller teams to operate at the scale of larger ones, not help larger teams coordinate more efficiently. Monday.com, Asana, and their peers should be asking hard questions about what their product does in a world where the coordination problem they solve is getting smaller.

For teams building internal tooling or back-office automation, not every SaaS needs to be replaced just because it’s SaaS. The replacement calculus should account for the fully loaded cost of maintaining your custom solution — including the opportunity cost of the engineers sustaining it — against what those same people could be doing instead. Sometimes the best move is to keep paying Salesforce and point your team at a harder problem.

Watch the regulatory front. The FTC issued subpoenas to Amazon, Microsoft, Google, OpenAI, and Anthropic in early 2024 to examine AI partnerships, with particular attention to exclusivity arrangements. AWS’s exclusive Frontier distribution rights give regulators a concrete point of focus. The circular financing structures Bloomberg mapped are precisely the kind of arrangement that attracts antitrust scrutiny.

Expect a fast follow from OpenAI. Altman teased a “big upgrade” for Q1 2026. The release cadence — GPT-5 in August, GPT-5.2 in December, GPT-5.2-Codex in February — suggests GPT-5.3 is imminent. I wouldn’t be surprised if the model drop was deliberately held to ride this week’s momentum: Pentagon deal, $110 billion raise, Anthropic sidelined, Iran strikes validating AI in national security. This is the Altman playbook. Manufacture narrative gravity, then fill it with product.


## Where this leaves us

This week, Dario Amodei stood on principle and got designated a national security risk. Sam Altman played the quiet game and walked away with the keys to the kingdom. Amazon placed chips on every number. SoftBank bet the farm on superintelligence. And the Pentagon proved that AI models are now so embedded in American warfighting that even a presidential order can’t remove them in real time.

The numbers tell a story the narrative coverage misses: $110 billion in fresh capital, $700 billion in cloud commitments, twenty-six gigawatts of planned compute, and a revenue trajectory that needs to hit $280 billion by 2030 to justify any of it. Call it a funding round if you want, but the structure underneath is a bet that AI compute becomes as fundamental as electricity — and that OpenAI will own the grid.

The next move comes fast — and this is the kind of week he likes to build on.

[![](https://substackcdn.com/image/fetch/$s_!h_u5!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc70dc9cc-063a-4ac0-96fb-01b9de13a766_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!h_u5!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc70dc9cc-063a-4ac0-96fb-01b9de13a766_1024x1024.png)
