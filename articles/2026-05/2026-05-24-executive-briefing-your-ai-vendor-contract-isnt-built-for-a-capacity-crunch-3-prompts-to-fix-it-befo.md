---
title: "Executive Briefing: Your AI vendor contract isn't built for a capacity crunch. 3 prompts to fix it before your budget meeting"
author: "Nate Jones"
published: 2026-05-24
url: https://natesnewsletter.substack.com/p/ai-big-tech-industrial-business
subtitle: "Watch now | Microsoft plans to spend roughly $190 billion this year and still expects to run short on capacity."
audience: everyone
scraped_at: 2026-05-26 19:17:31
---

Microsoft plans to spend roughly $190 billion this year and still expects to run short on capacity. And Microsoft is not alone: across the four biggest hyperscalers, combined 2026 capital spending is on track to approach $700 billion, nearly double what they spent in 2025.

The fiscal third-quarter 2026 numbers fill in the picture: Microsoft reported $31.9 billion in capital expenditures for the quarter and guided to more than $40 billion in the next. About two-thirds of that quarterly spend went to short-lived assets, primarily GPUs and CPUs. Even after all of it, the company expects to stay capacity constrained at least through the year.

No classic software company looks like that. A classic software company writes code once and sells it many times, and its biggest worry is talent or distribution, not whether it can physically build enough capacity to meet demand. The cloud was supposed to make infrastructure someone else’s problem.

AI breaks that abstraction.

The most important thing to understand about the current AI buildout is that tokens are not magic. They are manufactured. Every answer from a model is the output of a physical production system that consumes chips, high-bandwidth memory, advanced packaging, substrates, optics, power, cooling, land, data-center construction, networking, and operations talent. When it works, a user sees a paragraph, a line of code, a summarized contract, or an agent completing a task. Behind the screen, a factory is turning electricity and silicon into intelligence.

This is why AI is turning big tech into an industrial business.

Calling AI industrial is not new. Mary Meeker [built a 340-slide deck around it](https://natesnewsletter.substack.com/p/i-summarized-mary-meekers-incredible). Jensen Huang says a version of it on every NVIDIA earnings call. What is new is what Microsoft’s number does to the contract sitting on your desk. Six months ago, an AI vendor agreement was structured like a software agreement. Now that the hyperscalers are spending at this scale and still rationing capacity, your AI vendor agreement is a supply contract in everything but name. It has allocation. It needs capacity terms. It needs a fallback. None of that was a line item a year ago.

If that sounds like a problem for the CFO and no one else, consider that my own token spend ran close to 500 million tokens last week. Multiply that across a team and the capacity question stops being abstract.

The visible product is still software. ChatGPT, Copilot, Gemini, Claude, Meta AI, and Bedrock all look like applications or APIs, but the constraint underneath them is physical. The strategic question is no longer only, “Who has the best model?” It is, “Who can operate the factory that produces intelligence at scale?”

**This briefing covers:**

- **The bill of materials behind every token.** Chips, memory, packaging, power, cooling, construction, and how to tell which one stops your vendor cold before it stops you.
- **Why your vendor contract is now a supply contract.** What to actually ask for when the cloud you buy from is competing with you for the same chips: allocation, fallback, reserved capacity, written down.
- **Your CFO is about to inherit a capital cycle.** Why utilization is suddenly the metric that matters, and why a 40% throughput gain beats a new data center.
- **Seats are the wrong unit, and almost every plan still uses them.** How to forecast in tokens instead, and why an agent that runs for hours belongs in a different budget line than a chatbot that answers questions.
- **The one question that decides whether AI helps your margins or wrecks them.** It is not whether tokens are expensive. It is something more specific, and most companies have never asked it.
- **Three instruments to run before the budget meeting.** A vendor audit that maps the supply chain under your contract and hands you the language to demand, a forecasting model that sizes demand in tokens instead of seats, and a routing diagnostic that finds the workflows burning premium inference on cheap work.

Microsoft has already put $190 billion behind this view of the world. Most companies have not put it into their AI plans at all. What follows is what changes once you do.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

A read-only MCP server that gives your AI direct access to my entire published content library. You connect once, and then the archive just shows up inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Setup takes about ninety seconds.

- Register once at **[promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)**
- Enter your access code (executive\_circle) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

Your subscription now works inside your AI. Have fun!


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260512_715_promptkit_1)

Most companies are about to discover that their AI vendor agreement was written for the wrong decade. It has a price and a seat count and a support tier, and none of that tells you what happens when the cloud underneath your vendor runs short and your workload is the one that gets throttled. These three prompts exist because the questions that decide whether AI helps your margins or wrecks them are not the questions on the contract. The audit forces the supply chain into the open and tells you whether your vendor controls its own capacity or is reselling someone else’s rationed allocation, because those are two completely different risks wearing the same logo. The forecasting model refuses to let you size demand in seats, since seats have never once predicted what an agent costs to run. And the routing diagnostic resists the easy answer of pushing everything to the cheapest model, because the real discipline is spending expensive tokens only where the work earns them. Run them with a thinking-capable model. They are built to reason through your actual situation, not to fill in a template.


## The old software model

The old software model was built around one very good economic pattern.

You spent money upfront to build the product. You wrote code once and sold it many times. You added customers without rebuilding the product for every customer. Your gross margin improved as revenue scaled. Your biggest constraints were engineering talent, product quality, distribution, customer acquisition, and, later, cloud costs.

Even cloud infrastructure did not fully change this logic. Cloud made infrastructure more flexible and easier to rent. A SaaS company did not need to own data centers. It could run on AWS, Azure, or Google Cloud. It could scale up when customers arrived, scale down when usage dropped, and keep physical infrastructure out of the core strategic conversation.

That was the promise of software. The physical world receded into the background.

AI pulls the physical world back into the center.

The reason is simple: AI usage is not just a user opening a web page or saving a record in a database. AI usage is computation at the moment of service. Every prompt, every agent step, every tool call, every reasoning loop, every generated image, and every long-context task consumes real-time compute. Training a model is expensive, but inference is continuous. Once AI becomes part of daily work, the factory never stops running.

That changes the cost structure.

In the old model, a marginal software interaction was often cheap. In the AI model, the marginal interaction may involve thousands or millions of tokens, multiple model calls, retrieval, tool use, verification, fallback logic, and retries. The business can still become very profitable, but the margin model is different. It depends on utilization, routing, caching, batching, model choice, output length, power cost, memory bandwidth, and hardware efficiency.

The capex numbers matter because they signal something deeper than spending scale. The unit of production has changed.


## The AI factory model

An AI factory is the physical and operational system that produces tokens.

That sounds abstract, so here is the literal version. An AI factory includes the accelerators that run the model, the high-bandwidth memory that feeds those accelerators, the package that connects the compute and memory, the substrates and interposers that make the package manufacturable, the network that moves data across the cluster, the optics that keep bandwidth from collapsing at scale, the power system that feeds the racks, the cooling system that removes heat, the data center that houses the system, and the software operations layer that keeps the whole thing utilized and reliable.

NVIDIA’s GB200 NVL72 is a useful example. Call it a chip and you miss the point. It is a liquid-cooled rack-scale system connecting 72 Blackwell GPUs and 36 Grace CPUs into a large NVLink domain, with 13.5 terabytes of HBM3E and 576 terabytes per second of memory bandwidth. NVIDIA describes it as infrastructure for real-time trillion-parameter inference. The product is an industrial module for an AI factory.

Microsoft is doing more than buying GPUs. The company is reducing the time from dock to live for new GPUs and bringing data centers online ahead of schedule because a data center that becomes live six weeks earlier can recognize revenue earlier. Inference throughput improvements across Copilot increase factory output without waiting for another power agreement or shipment. And deploying its own Maia accelerators and Cobalt CPUs reduces vendor dependence, which is both margin risk and capacity risk.

Amazon is doing the same thing through a different architecture. In its first-quarter 2026 results, [Amazon said](https://www.aboutamazon.com/news/company-news/amazon-earnings-q1-2026-report) it landed more than 2.1 million AI chips over the past 12 months, more than half of which were Trainium. It also described multi-gigawatt Trainium commitments from Anthropic and OpenAI and more than one million NVIDIA GPUs under agreement for deployment through 2027. The language sounds more like a capacity strategy than a software stack.

Meta’s capex guidance tells the same story. In April 2026, [Meta raised full-year capital expenditure guidance](https://investor.atmeta.com/investor-news/press-release-details/2026/Meta-Reports-First-Quarter-2026-Results/default.aspx) to $125 billion to $145 billion, citing higher component pricing and additional data-center costs to support future capacity. The important part is what the spending buys: components, data centers, future capacity. The inputs are industrial.

Meta’s Hyperion project makes this visible in one place. Meta [announced a joint venture with Blue Owl](https://investor.atmeta.com/investor-news/press-release-details/2025/Meta-Announces-Joint-Venture-with-Funds-Managed-by-Blue-Owl-Capital-to-Develop-Hyperion-Data-Center/) to develop and own the Hyperion data-center campus in Richland Parish, Louisiana, with Meta managing construction and operations for the project. No one would call that a software launch. It is land, financing, construction management, power planning, and a long-lived physical asset built to feed AI demand.

The point is not that every company should own a Hyperion-scale campus. The point is that the unit of competition has changed. A frontier AI product may live in a chat box, but the capacity behind it looks like a capital project, a supply chain, a power negotiation, and an operations system.

Every one of them is building the factory before they need it.


## The physical bill of materials for intelligence

The phrase “AI infrastructure” is now too vague. It hides the actual bottlenecks. Executives need a more concrete map.

Start with chips. The accelerator is the engine of the AI factory. GPUs, TPUs, Trainium chips, and custom ASICs provide the compute needed to train and run models. But a chip by itself does not produce intelligence at scale. It needs memory, packaging, networking, power, and a place to run.

High-bandwidth memory is often the next constraint. AI accelerators need extremely fast memory located close to the processor. If the model cannot move data fast enough, compute sits idle. HBM has become strategic for exactly this reason. A company can have theoretical access to logic dies, but if it cannot secure enough HBM, it cannot ship enough usable AI accelerators.

Then packaging, which gets even more physical. Advanced AI chips are not simple standalone parts. Logic dies and HBM stacks need to be integrated into a working package. Technologies such as TSMC’s CoWoS are critical because they connect compute and memory at the bandwidth AI workloads require. [Epoch AI estimates](https://epoch.ai/data-insights/ai-chip-supply-chain-constraints) that the four largest AI chip designers consumed around 90% of global CoWoS capacity and HBM supply in 2025, while consuming only about 12% of advanced logic die production. The distinction matters. The bottleneck was not “not enough chips.” It was not enough manufacturable, packageable, memory-attached accelerators.

SemiAnalysis tracks the same pressure from another angle. Its [AI Datacenter Model](https://newsletter.semianalysis.com/p/datacenter-model) follows thousands of data centers and the power-capacity constraints around accelerator deployments. You do not need to outsource the whole argument to an analyst to see the point: the scarce thing is live, powered, memory-attached, networked capacity — not the model alone.

Substrates and interposers are less visible, but they matter because they are part of what makes the package physically possible. They carry signals, hold components in alignment, and help determine yield. If substrate supply, quality, or scaling fails, the production line slows even if the chip design is excellent.

Optics and photonics matter because large AI clusters are communication machines as much as compute machines. GPUs need to move enormous amounts of data between each other. Copper has limits in power, heat, distance, and signal integrity. As clusters scale, optical communication becomes part of the factory’s nervous system. NVIDIA’s [Spectrum-X Photonics announcement](https://investor.nvidia.com/news/press-release-details/2025/NVIDIA-Announces-Spectrum-X-Photonics-Co-Packaged-Optics-Networking-Switches-to-Scale-AI-Factories-to-Millions-of-GPUs/) is one sign of this shift. The company positioned co-packaged optics as a way to connect AI factories with far better energy efficiency and resilience at scale.

Power is the obvious constraint, but it is often discussed too loosely. The issue goes beyond total electricity generation. The real constraint is firm power at the right location, on the right schedule, with the right interconnection, redundancy, and economics. The [International Energy Agency projects](https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai) global data-center electricity consumption will roughly double to about 945 terawatt hours by 2030. But the more important executive point is local. Data centers concentrate demand in specific places. A national grid may have enough power in the abstract while a specific site cannot get enough power soon enough to support an AI campus.

Heat comes next. Dense AI racks run at levels old data-center designs were not built to handle. Liquid cooling is not a facilities footnote. It is part of production capacity. If the cooling design cannot support the rack density, the company cannot deploy the hardware it bought at full value.

Finally, there is construction. A GPU on an invoice is not the same as revenue-ready capacity. Data centers require land, permits, substations, switchgear, transformers, backup power, cooling systems, fiber, mechanical and electrical contractors, commissioning, and operations staff. [CBRE notes](https://www.cbre.com/insights/books/us-real-estate-market-outlook-2026/data-centers) that traditional 12-to-18-month timelines for smaller data-center buildings no longer apply to 500-megawatt-plus AI campuses. These projects can move into multi-year schedules, and transmission or generation requirements can stretch interconnection timelines to 24, 36, or even 48-plus months.

A model release is software. Running that model for hundreds of millions of users and fleets of agents is industry.


## The bottleneck map

The useful question is not, “Who benefits from AI capex?” It is a market question, and it quickly turns into stock-picking. A better executive question: “Whose lateness stops the factory?”

If HBM is late, accelerators cannot be fully built. Late packaging means compute and memory never become usable systems. If substrates are late or yields are poor, packages cannot scale. Without ready optics, clusters hit bandwidth and energy limits.

And under all of those, power has to arrive, cooling has to scale with rack density, construction has to deliver on schedule, and operations has to drive utilization high enough to amortize the depreciation.

AI strategy becomes a dependency graph. The company has to know which station in the route from demand to tokens is most likely to constrain throughput.

Here is the executive version of the map: demand becomes model calls, model calls become accelerator load, accelerator load depends on HBM, packaging, substrates, optics, power, cooling, construction, and operations, and only then do tokens reach the user.


## The new capital cycle

The first executive implication is financial.

Software finance used to focus heavily on revenue growth, gross margin, sales efficiency, R&D intensity, retention, and free cash flow. Those still matter. But AI adds a harder capital cycle.

The CFO now has to think about GPU depreciation, data-center asset life, financing costs, power contracts, utilization, component inflation, capacity commitments, and hardware refresh risk. A GPU fleet may depreciate over three to five years. The data-center shell and power infrastructure may last much longer. The model and serving stack may need continuous refresh. These asset lives do not match neatly.

That creates a new question: can the company earn enough from this capacity before the next hardware generation changes the cost curve?

Utilization becomes the central operating metric. An AI factory with low utilization is financially dangerous. The depreciation clock runs whether tokens are being served or not. Power contracts, leases, operations teams, and maintenance do not wait for demand to mature. Below a certain utilization level, even a technically impressive facility becomes a margin problem.

But utilization cannot be solved by filling the factory with any workload. Latency-sensitive inference, batch inference, training, internal workloads, enterprise workloads, consumer workloads, and agentic workflows all have different economics. The margin model depends on routing the right task to the right model on the right hardware at the right time. Caching, batching, distillation, quantization, and model cascades are not technical polish. They are the operating margin model.

Microsoft’s comments about inference throughput illustrate the point. If software and hardware optimization produce 40% better throughput for commonly used models, that is equivalent to increasing factory output without building another data center. [Microsoft made that exact point on its Q3 FY26 call](https://www.microsoft.com/en-us/investor/events/fy-2026/earnings-fy-2026-q3), where Satya Nadella tied the 40% Copilot throughput improvement to software and hardware optimization. In AI, engineering efficiency is capital efficiency.

The bull case deserves to be stated fairly. AI serving costs have been falling quickly. [Epoch AI](https://epoch.ai/data-insights/llm-inference-price-trends) found that prices to reach the same performance thresholds have fallen at very different speeds across tasks, in some cases by orders of magnitude per year. Smaller models, distillation, caching, batching, quantization, speculative decoding, and better routing all make it possible to serve more work from the same capacity.

The cost improvements are real. They also do not repeal the industrial thesis. Cheaper tokens usually create more token demand. Economists have a name for this. The Jevons paradox describes how gains in efficiency, rather than reducing total consumption, tend to increase it. The cheaper a resource gets to use, the more uses people find for it. Coal in the nineteenth century, bandwidth in the broadband era, now tokens.

The same thing is happening with intelligence right now. Longer contexts, more agents, more retries, more verification passes, and workflows that were uneconomic last quarter. Some of the capacity pressure this year traces directly back to last year’s better agents. If efficiency gains outrun demand growth, the industrial conversion softens. If cheaper intelligence causes usage to explode faster than capacity becomes available, the factory still matters.


## Procurement becomes supply chain

Procurement also changes.

In the old enterprise software world, procurement negotiated SaaS contracts, cloud commitments, support terms, seat counts, and renewal protections. In the AI factory world, procurement becomes strategic supply-chain management.

The company needs to know where its AI capacity actually comes from: the model provider, the cloud, the chip vendor, the memory suppliers, the data-center region, the power source, the cooling design, the fallback route, and the contractual priority when supply is constrained.

This also changes who belongs in the room. Procurement decisions for AI tools are still being made by the same people who signed the SaaS deals, and engineers are usually not among them. That is a mistake. Only someone close to the workload can tell you whether the capacity a vendor promises is actually usable for the tasks you intend to run.

The complexity deepens because the cloud vendor may also be a competitor for the same capacity. Microsoft needs GPUs for Copilot and Azure customers. Google needs capacity for Gemini, Cloud, Search, Workspace, YouTube, and internal model work. Amazon needs capacity for AWS customers, Bedrock, Trainium commitments, and its own AI applications. Meta needs capacity for its own consumer AI and model ambitions.

The four hyperscalers are not exposed in the same way. Microsoft carries enormous absolute capex but also has committed enterprise demand through Azure and Copilot. Amazon has both NVIDIA supply and Trainium, which reduces single-vendor exposure if customers can use the stack. Google has its TPU lineage and a different internal-demand mix across Search, Cloud, Workspace, and Gemini. Meta has fewer customer-allocation questions because much of the demand is internal, but that means it has to underwrite the economics itself. Treating them as one block obscures the actual risk.

That does not mean enterprises should avoid hyperscalers. It means the contract has to be read differently. The question goes beyond price. It is allocation. When demand exceeds supply, does the customer have guaranteed capacity, a best-efforts promise, a queue position, or a vague roadmap?

The procurement team also has to understand substitution risk. Can the workload move from one model to another, or from one cloud to another? Does it degrade gracefully when premium inference is tight? Will a smaller model handle lower-priority tasks? And can the company preserve enough optionality without fragmenting the architecture into an unmanageable mess?

In the AI factory era, procurement is no longer a back-office function. It is part of product reliability.


## Vendor risk goes physical

Vendor risk becomes more physical and more concentrated.

A company may think it has a model-provider dependency, but underneath that dependency sit several others: NVIDIA or another accelerator provider, TSMC or another foundry, SK hynix, Samsung, or Micron for HBM, advanced packaging capacity, substrate suppliers, networking suppliers, data-center developers, utilities, and local regulators.

This creates a different kind of risk map. A vendor can be excellent and still be constrained by a supplier several layers upstream. A signed cloud contract does not guarantee timely interconnection. A model can improve and still become too expensive to serve at the desired latency. Even a completed data center may be limited by cooling, power, or network throughput.

The strategic move is not to panic or diversify blindly. Too much diversification can destroy operational leverage. The move is to identify the true bottleneck, understand the time to relief, and decide where optionality is worth paying for.

For some workloads, the answer is multi-model routing. Reserved capacity solves a different set. Custom silicon or on-prem deployment may fit others. And for many, the real answer is better degradation planning: what happens when the best model is unavailable, too slow, or too expensive for a given task?


## Forecasting tokens, not seats

Most companies still forecast AI demand in the wrong units.

They talk about seats, users, licenses, or projects. Those are useful, but they are not enough. AI capacity planning needs to forecast tokens per workflow, context length, number of model calls per task, agent loops, concurrency, latency tier, retrieval overhead, tool-call overhead, failure and retry rates, and output-token ratios.

A customer-support chatbot and an autonomous claims-processing agent do not consume capacity the same way. A coding assistant that sits beside a developer and answers occasional questions is different from an agent that reads a repository, writes code, runs tests, fixes failures, and repeats the loop for hours. A short email summary is different from a long-context legal review with citations, redlines, and risk scoring.

Most executive AI plans are still weak here. They estimate adoption instead of workload, users instead of tokens, vendor budget instead of physical capacity exposure.

The AI factory model forces a better discipline. If the business wants agents to run continuously, capacity planning has to treat agents as ongoing production load. If the product promise depends on low latency, the company has to reserve or build capacity for peak demand. If the workflow can run overnight, it can use batch economics. If the task is low value, it should not touch the most expensive model by default.

The question becomes: what is the cheapest reliable path to the required outcome?

AI capacity planning, done at that level, becomes an operating system for margin.


## Where the margin lives

The market keeps asking whether AI will be good or bad for margins. The honest answer is that it depends on factory operations.

AI can be a margin miracle if the company gets high utilization, strong demand, efficient routing, falling hardware cost per token, high-value workflows, and enough pricing power to capture the value created. AI can also be a margin trap if the company overbuilds capacity, pays inflated component prices, runs expensive models for low-value tasks, gets stuck with low utilization, or loses pricing power as model capability commoditizes.

Both can be true in different parts of the same company.

A high-value agentic workflow that saves a company millions of dollars can support expensive inference. A casual consumer assistant cannot. A batch analytics workload can be optimized for utilization. A real-time voice assistant has less room for batching and must pay for latency. A coding agent may justify premium reasoning tokens because the output has direct labor value. A simple classification task should be routed to a cheaper model.

The margin question is not, “Are tokens expensive?” The margin question is, “Are expensive tokens being spent only where the work justifies them?”


## The shape of the next decade

The largest technology companies are not becoming industrial businesses because they suddenly want to own concrete, substations, cooling loops, and supply-chain headaches. They are becoming industrial businesses because intelligence at scale now has a physical bill of materials.

This does not mean software stops mattering. It means software and infrastructure are merging into one operating problem. Model architecture shapes hardware demand, the serving stack drives utilization, product design determines token consumption, and the procurement contract governs reliability. Further down the chain, the data-center schedule affects revenue, the power agreement affects margin, cooling constrains rack density, and the finance plan determines how much risk the company can carry before demand catches up.

In the cloud era, the winning abstraction was elastic compute. Developers could build as if infrastructure were always available.

In the AI era, that abstraction is breaking. Intelligence is not infinitely elastic. It is constrained by the factory.

Microsoft’s capex number matters for exactly this reason. Look past the spending headline. It is a signal that the world’s most valuable software companies now have to think like industrial operators. They need supply assurance, throughput optimization, capacity scheduling, vendor diversification, depreciation discipline, and utilization management.

The executive takeaway is simple.

Do not look at AI infrastructure as a pile of GPUs. Look at it as a production line.

The line starts with demand and ends with tokens served. In between sit chips, HBM, packaging, substrates, optics, power, cooling, construction, operations, and finance. Any one of those can become the constraint. Any one of those can determine whether the AI strategy is a product advantage or a margin problem.

The companies that understand this will ask better questions.

First, what share of our AI vendor spend is reserved capacity rather than best-efforts allocation, and what happens if our default provider is supply constrained for thirty days?

Second, what is our concrete plan for routing low-value work to cheaper models, and how will we measure the savings without degrading the user experience?

Third, where in our top three AI workflows is hidden human supervision masking product failure, and how would we know if that supervision disappeared?

Those are not traditional software questions. They are factory questions.

AI is still software on the surface. Underneath, it is becoming the next great industrial system.

And tokens are what it manufactures.

[![](https://substackcdn.com/image/fetch/$s_!g-V1!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe1693649-0733-4f52-86bb-fdd4eb20e1c8_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!g-V1!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fe1693649-0733-4f52-86bb-fdd4eb20e1c8_1024x1024.png)
