---
title: "GPUs Just Got 6x More Valuable. No New Hardware Required."
author: "Nate Jones"
published: 2026-04-11
url: https://natesnewsletter.substack.com/p/your-gpus-just-got-6x-more-valuable
audience: everyone
scraped_at: 2026-05-14 14:33:46
---

Everyone is watching the wrong race. Billions are flowing into faster chips and new fabs, on the assumption that whoever builds the most powerful hardware wins. But the variable that’s about to reshape the AI infrastructure stack isn’t silicon. It’s a compression algorithm. And it dropped two weeks ago.

On March 25, Google Research published a paper called TurboQuant. Within hours, the internet had renamed it: Pied Piper. As in HBO’s *Silicon Valley*, where a startup’s compression breakthrough threatened to restructure who controlled the internet. TurboQuant does the same thing to AI. It compresses the working memory that models use during every conversation by 6x, with zero accuracy loss. No retraining. No calibration. You drop it in.

The same GPU that served 9 concurrent users now serves 50.

If you’re a developer watching inference costs climb, that’s your bill shrinking. If you’re buying servers where the RAM now costs 172% more than eighteen months ago, that’s your existing fleet going six times further without a single new purchase. If you use AI every day, this is why your context windows are about to get dramatically longer and your tokens dramatically cheaper.

Most of the coverage stopped there — the efficiency gain, the cost savings, the spec sheet. But compression isn’t just a cost story. **It’s the fastest-moving force in the entire AI infrastructure war, and it changes who wins.**

**Here’s what’s inside:**

- **The two forces everyone knows about.** Why constrained memory supply and exploding agent demand only explain half the story.
- **The third body.** How 6x memory compression turns into a 5x increase in revenue per GPU, and why that changes the concurrency math.
- **Why compression moves fastest.** The three forces operate on completely different timescales, and that asymmetry matters more than the compression ratio itself.
- **The KV cache as RAM.** Why a startup just proved the transformer is a literal computer, and what that makes compression mean.
- **Who wins, who loses.** How this reshapes the competitive picture for Google, NVIDIA, the middleware layer, and enterprises running their own inference.

The third force is where the leverage is. Here’s how it works.


## LINK: [Grab the Prompts](https://promptkit.natebjones.com/20260326_o81_promptkit_1)

This piece covers a lot of ground, from compression math to competitive dynamics to the cognitive architecture of transformers, and the natural instinct is to file it under “interesting but not actionable yet.” These two prompts close that gap. The first is a **GPU Fleet Compression Calculator** that takes your actual inference setup (model size, GPU type, context length, concurrent users) and runs the before/after math across three compression tiers, from what’s production-ready in vLLM today to TurboQuant-level gains. It produces a full fleet economics table, a break-even analysis for compression vs. buying more hardware, and decision framing calibrated to whether you’re a developer, an executive, or someone trying to understand why token pricing is about to shift. The second is a **Memory Architecture Audit** that maps the other side of the memory crisis, the one that hits every AI user right now. It walks through your actual workflows, finds every point where you’re losing context (tool switches, session resets, chunked retrieval that severs connections), scores the cost in time, tokens, and output quality, and returns a prioritized fix list tiered by effort. The compression frontier will eventually deliver longer windows and cheaper tokens from the infrastructure side. These prompts help you act on both sides of that equation today.

---


## **The Two Forces Everyone Knows About**

If you’ve been following along for the last few months, you already know two of the three forces driving the AI memory crisis.

**Force 1: Supply is structurally constrained.** HBM, the high-bandwidth memory stacked onto AI accelerators, carries profit margins in the 50–70% range, compared to roughly 40% for commodity DRAM. Every wafer a memory manufacturer allocates to an HBM stack for an NVIDIA GPU is a wafer denied to the LPDDR5X module in your phone or the DDR5 in your laptop. And HBM is a glutton — it consumes 3x the silicon per bit of standard DRAM.

The math cascades from there. Samsung, SK Hynix, and Micron have signed multi-year supply contracts with hyperscalers extending three to five years. AI datacenters now consume an estimated 40% of global DRAM production. New fabs won’t help soon; Micron’s Idaho facility targets 2027–28, its New York fab approximately 2030. The supply side moves on fab timelines measured in years.

**Force 2: Demand is exploding.** Agents happened. When AI went from answering single questions to running multi-step workflows with tool use, persistent context, and continuous reasoning, memory consumption jumped by orders of magnitude. Jensen Huang stood onstage at GTC in mid-March and said the quiet part loud: “The inference inflection has arrived.” He described context as “a first-class data type” and announced that the Vera Rubin platform delivers 350x the token throughput of the Hopper generation, from roughly 2 million tokens per second to 700 million. He raised NVIDIA’s revenue guidance to $1 trillion in chip sales by end of 2027.

The enterprise numbers back him up. At organizations pushing hard on AI-native workflows, token consumption per developer is already measured in billions annually, and Jensen told the All-In Podcast that a $500K engineer should be consuming $250K worth of tokens a year. Scale that to 10,000 people and the infrastructure budget breaks. DRAM prices have surged 172%, and server memory is expected to double in cost by end of 2026. The demand side moves on adoption curves measured in quarters.

These two forces, constrained supply and exploding demand, produce the squeeze that everyone is writing about. If the story stopped here, the conclusion would be depressing: wait for more fabs, or use fewer tokens.

But the story doesn’t stop here.


## **The Third Body**

TurboQuant isn’t more supply or less demand. It’s making the same memory do radically more work.

The mechanism, without the math: traditional methods for compressing AI memory (vector quantization) come with a hidden tax. To keep the model from losing accuracy, you have to store extra “quantization constants” alongside the compressed data. That overhead adds 1–2 extra bits per number, partially defeating the purpose of compression. It’s like packing a suitcase by folding everything tightly, but then having to carry a separate bag for the folding instructions.

TurboQuant eliminates that overhead through two stages. First, PolarQuant rotates the data into a coordinate system (polar coordinates instead of the standard Cartesian grid) where the data’s structure becomes predictable enough that you don’t need per-block normalization anymore. Think of it as converting “go 3 blocks east and 4 blocks north” into “go 5 blocks at a 37-degree angle.” The radius captures the signal strength, and the angles capture the meaning. Because the angle distributions are concentrated and predictable, the model doesn’t need to carry that extra bag of instructions.

Second, a technique called QJL (Quantized Johnson-Lindenstrauss) takes the tiny residual error from stage one and corrects it using just a single bit. It’s a mathematical error-checker that eliminates bias in the attention scores. The combination: aggressive compression from PolarQuant, surgical error correction from QJL, zero overhead from either.

The result is a KV cache compressed to 3 bits per value, down from 16 or 32 bits, with no measurable accuracy loss across question answering, code generation, summarization, and (critically) needle-in-a-haystack retrieval at 104K tokens. The algorithm is “data-oblivious,” meaning it requires no knowledge of the specific model or dataset. It doesn’t need a calibration pass, retraining, or fine-tuning. It’s a mathematical property, not an engineering hack.

But the spec sheet isn’t the story. The story is what happens to the concurrency math.

When you compress the KV cache by 6x, you don’t just save memory — you change the number of simultaneous users a single GPU can serve. That’s the number that determines whether your inference deployment is profitable or hemorrhaging money.

I’ve been working through GPU fleet sizing for a large enterprise deployment. For a 70B-parameter model serving 32K-context sessions, each concurrent user’s KV cache eats roughly 16 GB of VRAM. On a pair of B200 GPUs with 384 GB total, after subtracting model weights and overhead, you get about 9–10 concurrent sessions. That’s the number people quote when they say “single-digit concurrency” for heavy inference.

Apply TurboQuant. That 16 GB per session drops to under 3 GB. Same GPU pair. Same model. Same context length. Instead of 9 sessions, you’re running 50+. That kind of concurrency gain translates to roughly a 5x increase in revenue per GPU.


## **Why the Third Force Moves Fastest**

The three forces operate on completely different timescales, and that asymmetry matters more than any individual compression ratio.

**Supply moves on fab timelines.** Years. A new DRAM fab takes 3–5 years from groundbreaking to volume production. HBM4, which NVIDIA is building the Vera Rubin platform around, won’t reach customers until second half of 2026 at the earliest.

**Demand moves on adoption curves.** Quarters to years. Enterprise agent deployment is accelerating but still constrained by organizational readiness, procurement cycles, and the usual human friction of changing how people work.

**Compression moves at the speed of math papers.** TurboQuant went from arxiv preprint to front-page coverage in one day. It requires no new hardware, no new manufacturing capacity, no organizational change management. Google’s official code is expected by Q2 2026, but five independent community implementations shipped within two weeks of the paper, including one running a 104B-parameter model on a MacBook. FlashAttention went through three major versions in two years. KV cache compression has been advancing through ShadowKV, KIVI, and now TurboQuant, each one pushing the quality-versus-compression frontier further out.

The third force is the fastest-moving variable in a system where the other two are structurally slow, and that makes it disproportionately underweighted by everyone focused on chip supply or agent demand.

I’ve been describing compression as if it’s just about cost, though, and that frame misses what’s actually at stake. The deeper implication is about what becomes *possible* when you expand the effective cognitive workspace of a model without changing the hardware. To see why, you need to understand what the KV cache actually is.


## **The KV Cache Is RAM. The Transformer Is a Computer.**

Most coverage of TurboQuant treats the KV cache as a cost center: bytes to be reduced, a billing line item. That framing misses what’s actually happening.

The KV cache is the model’s working memory in the literal computational sense. It’s the state the model holds while it reasons. Every token the model has ever seen in the current context gets stored as a key-value pair, and attention (the mechanism that gives transformers their power) computes over all of those pairs for every new token generated. The KV cache is what lets a model connect token 90,000 to token 3,000. It’s what allows the model to hold a conversation, follow an argument, track a codebase, or find a needle in a haystack of text.

In other words: if the model weights are the processor, the KV cache is the RAM.

Andrej Karpathy has described the transformer as “a magnificent neural network architecture because it is a general-purpose differentiable computer.” Not a metaphor. A description. And two weeks ago, a startup called Percepta showed just how literal that description is.

Percepta’s researchers compiled a WebAssembly interpreter directly into the weight matrix of a standard PyTorch transformer. Not as an external tool call, not as a code-interpreter sandbox running alongside the model. *Inside the weights.* The model executes arbitrary C programs through its forward pass, step by step, emitting a stack trace as tokens. It solved what’s been called the “world’s hardest” Sudoku puzzle by running an actual backtracking search algorithm, deterministically computing the answer with 100% accuracy rather than “reasoning” about the puzzle. It performed multi-digit addition without a single error. Over 30,000 tokens per second. On CPU.

I want to be careful not to overstate what this means in practice; the research is early, and production applications are a long way off. But the direction is striking. Today’s agentic ecosystem, from Claude Code to Codex to OpenClaw, is built on the principle of *surrounding* LLMs with external tools. The model writes Python, a sandbox executes it, the result comes back. The model is the brain, and the tools are the hands. Percepta demonstrated that the transformer itself can *be* the computer. The attention mechanism can implement arbitrary state transitions. The model doesn’t need to call out to a calculator, because it can *be* the calculator, running programs in its own weights.

And what constrains how complex a program that neural computer can run? What limits how long it can reason, how much state it can juggle, how many computational steps it can chain together?

The KV cache. The RAM.

Every step of Percepta’s internal WASM execution emits tokens that write to the KV cache. The longer the program, the bigger the cache. Their innovation, a technique called HullKVCache using 2D attention heads, reduced the attention complexity to O(log n), which is what made million-step programs feasible. But the *size* constraint remains. If you run out of KV cache space, the computer stops.

So connect TurboQuant to Percepta.

If the transformer is a computer and the KV cache is its RAM, then compressing that RAM 6x at zero fidelity loss is the equivalent of upgrading every GPU in existence from 80 GB to 480 GB of effective working memory, without buying a single new chip. That’s not a cost optimization — it’s a capability threshold.

The cognitive science framing is worth a brief detour. We distinguish between two types of thinking. System 1 is intuitive, fast, and prone to error, what current LLMs do when they predict the next token. System 2 is slow, deliberate, and logically rigid, what code execution does. The entire agentic ecosystem is built on bolting System 2 onto System 1 from the outside. The model reasons (System 1), writes code (System 1 producing System 2 instructions), ships it to a sandbox (external System 2), and incorporates the result (back to System 1). Every round trip through that loop costs latency, context, and tokens.

Percepta demonstrated that you can fuse both systems into a single substrate. The same transformer that generates language can also execute deterministic programs. But the fusion only works if the working memory, the KV cache, is large enough to hold both the linguistic context *and* the computational state simultaneously. Every System 2 operation the model runs internally writes to the same cache that holds the conversation. Compression isn’t just making the cache cheaper; it’s making room for both modes of cognition to coexist.

The things a model can do with a 600K effective context window are categorically different from what it can do with 100K. Not 6x more of the same stuff, but qualitatively new classes of computation: multi-step reasoning chains that would have exceeded memory limits, agent workflows that maintain state across thousands of tool calls, code analysis that holds an entire repository in working memory rather than chunking it into pieces and losing the connections between them. And if the Percepta direction matures (and I’m genuinely uncertain how far it goes), hybrid inference where the model switches between probabilistic reasoning and deterministic execution within a single forward pass, without ever leaving the transformer.

The Pied Piper parallel that actually matters isn’t the meme or the HBO reference — it’s the structural one. In *Silicon Valley*, middle-out compression didn’t just make files smaller. It enabled a “new internet,” decentralized, structurally different from what came before. The compression wasn’t the product. It was the *enabling condition* for a different architecture. TurboQuant plays the same role. It doesn’t just make inference cheaper. It expands what the model can think about. And at some threshold, maybe this one, maybe the next generation, that transforms the transformer from a language model into a general-purpose computational engine with enough working memory to do real work.


## **Your Brain Already Figured This Out**

There’s a reason this works, and it connects to something I’ve been writing about for over a year.

Recent neuroscience research, from Paul Frankland’s lab at the University of Toronto and a March 2026 study at the University of Nottingham using MEG imaging, has shown something fascinating about human memory. When you “forget” something, the memory isn’t erased. Your brain retains what researchers call a “memory key,” a pattern of neural activation that, if triggered again, reactivates the full memory. Optogenetic experiments in mice recovered “lost” memories across amnesia, infantile amnesia, and even Alzheimer’s models. The Nottingham study confirmed that brains reactivate memory signatures even when people fail to consciously recall them. Forgetting is a retrieval deficit, not a storage deficit. The information is still there; you’ve just lost the index.

PolarQuant, the first stage of TurboQuant, does something structurally analogous. Instead of storing every dimension of a memory vector at full precision, it rotates the data into a coordinate system where the *structure* matters more than the raw values. The radius captures the strength of the signal, the angles capture the direction of meaning, and because the angular distributions are predictable, you can represent them in far fewer bits without losing the relationships that the attention mechanism needs to compute accurately.

The brain stores a retrieval key that can reactivate a “forgotten” memory. PolarQuant stores a radius and angles that can reconstruct the full vector. Different substrates, same mathematical insight: **you don’t need to store everything if you preserve the right structure for recovering it.**

In December 2024, I calculated that giving 125 million ChatGPT users meaningful long-term memory would require 18.75 zettabytes of storage, roughly $468 billion just for the storage. That math assumed full-precision representation. What if full precision was always the wrong frame? What if the question isn’t “how do we store more” but “how do we represent the same information in less space without losing what matters”?

TurboQuant is one answer, and it’s not alone. A whole generation of compression research is converging on the same question from different angles: FlashAttention, ShadowKV, Mamba’s linear-time sequence modeling, Infini-attention’s 114x memory reduction.


## **Who Wins, Who Loses**

The three-body framing changes the competitive analysis.

If you only see two forces, supply constraint and demand explosion, the winners are obvious: whoever controls memory supply (Samsung, SK Hynix, Micron) and whoever can outbid competitors for that supply (hyperscalers with blank-check contracts). The losers are everyone else, from enterprises paying double for server DRAM to consumers watching PC prices climb to developers hitting token limits.

Add the third force, and the map shifts.

**Google wins twice.** They wrote TurboQuant, and they run Gemini. Google explicitly stated that a primary application is the KV cache bottleneck in Gemini. If they can compress Gemini’s inference memory by 6x in production, they effectively multiply their existing GPU fleet’s capacity without buying a single new chip — a compounding cost advantage against every competitor who hasn’t implemented comparable compression. The structural dynamic is identical to DeepSeek: that team showed you could *train* competitive models for a fraction of the cost. TurboQuant shows you can *serve* them for a fraction of the memory.

**NVIDIA’s narrative gets complicated.** Jensen spent GTC arguing that Vera Rubin’s 350x throughput increase solves the inference bottleneck. TurboQuant says you could also just compress the cache and get 6x more out of the GPUs you already have. NVIDIA sells more chips when memory is scarce and fewer when compression makes existing memory go further. The situation isn’t existential; inference demand is growing fast enough to absorb both more hardware *and* better compression. But it shifts pricing power. If your existing fleet goes 6x further, the urgency to buy next-generation hardware at premium prices drops.

**The middleware layer gets squeezed again,** which is a theme I keep coming back to. Companies sitting between model providers and enterprises are renting a position that the platform vendors are collapsing from above. Compression advantages accrue to whoever is closest to the metal. If Google implements TurboQuant in Gemini’s serving stack, that efficiency flows to Google’s margins, not to the orchestration layer sitting on top. The model providers are collapsing layers above them, and now they’re doing it from the infrastructure side too.

**Enterprises get a real option,** and it’s the most actionable piece of this whole picture. For anyone running self-hosted inference (and the DRAM price spike is making that increasingly painful), production-grade KV cache compression is the most immediate relief valve. It doesn’t solve the supply constraint or reduce your token consumption, but it multiplies the effective capacity of the GPUs you’ve already bought. Community implementations are already running, with active integration discussions in llama.cpp and vLLM. No procurement cycle, no new hardware — just math applied to your existing fleet.


## **TurboQuant Is Not a Silver Bullet. It’s One Front in a War.**

A few caveats before the hype cycle runs away with this.

TurboQuant only targets inference memory. It doesn’t address training, the fundamental DRAM shortage, or the wafer allocation problem. The official benchmarks used 8B-parameter models, though community implementations have since pushed the technique to 35B and 104B models with encouraging results. The speedup numbers are for attention logits specifically, not end-to-end inference. Google hasn’t released official code yet, but five independent implementations shipped within two weeks of the paper, and integration into llama.cpp and vLLM is actively underway. The gap between lab result and usable tool is closing faster than usual.

But TurboQuant isn’t alone, and that’s what makes the third force powerful. It isn’t any single paper; it’s the *breadth* of the attack on the memory problem. Smart people are hitting this from at least five distinct angles simultaneously, and each one compounds with the others.

**Quantization** is what TurboQuant does: representing the same vectors in fewer bits. Before TurboQuant, KIVI demonstrated 2-bit asymmetric quantization of the KV cache. ZipCache identifies “salient tokens” and applies mixed-precision quantization, keeping the important stuff at high precision and compressing the rest aggressively. vLLM already supports FP8 KV cache quantization in production today, not TurboQuant’s 3-bit zero-loss result, but real compression on the exact same bottleneck, deployable right now.

**Eviction and sparsity** takes the opposite approach: instead of compressing everything, throw away the tokens that don’t matter. H2O (”Heavy-Hitter Oracle”) keeps only the tokens that attention scores highest, evicting the rest. StreamingLLM keeps a sliding window of recent tokens plus a few “attention sink” tokens from the start of the sequence. The tradeoff is real: you can lose information that matters later. But for many production workloads, the tokens that matter are a small fraction of the total, and eviction works surprisingly well.

Those first two approaches work on existing models without retraining. The next three go deeper. **Architectural redesign** attacks the problem at the model level: DeepSeek-V2 introduced Multi-Head Latent Attention (MLA), which projects keys and values into a lower-dimensional latent space during training, shrinking the KV cache footprint by design rather than after the fact. Hybrid architectures like IBM’s Granite 4.0 and NVIDIA’s Nemotron-H replace most of the quadratic attention mechanism with linear-time state-space models, making the memory problem smaller by definition. These require training from scratch, which limits immediate adoption, but they represent where the architecture is heading. **Offloading and tiering** keeps the full cache but moves it strategically. ShadowKV stores compressed keys on GPU and offloads values to CPU, achieving 6x larger batch sizes and 3x higher throughput on A100s, treating GPU and CPU memory as a hierarchy the same way your computer treats RAM and SSD. And **attention optimization** makes the computation itself cheaper without shrinking the data: FlashAttention, now in its third major version, restructures how attention reads and writes GPU memory to minimize IO, reaching 75% of theoretical H100 performance.

The point isn’t that any one of these is “the answer.” Dozens of research groups and companies are attacking the memory bottleneck algorithmically, from multiple directions, and the results compound. TurboQuant’s 6x compression stacks with ShadowKV’s offloading. Eviction stacks with quantization. MLA stacks with FlashAttention. Each generation of improvement across all five fronts multiplies the effective memory of existing hardware, and new results are landing weekly.

The third force isn’t TurboQuant alone. It’s the entire compression and efficiency frontier, advancing faster than either silicon or demand.


## **The Three-Body Problem**

The AI memory crisis has three forces, not two. Supply is constrained by fab timelines. Demand is exploding from agents. And compression, algorithmic efficiency applied to the working memory of what is increasingly looking like a general-purpose neural computer, is the third body in the system, advancing faster than either of the others.

The three forces interact multiplicatively, not additively. A 6x compression gain combined with a 350x throughput increase from next-generation hardware combined with continued demand growth: these compound. And three-body problems are famously unsolvable in closed form. Small perturbations in the fastest-moving body produce outsized effects on the system. Compression moves at the speed of math, and it quietly reshapes who captures value at every layer of the stack.

In *Silicon Valley*, the breakthrough that threatened to reshape the industry wasn’t a new chip or a new business model. It was a compression algorithm, math applied to an infrastructure bottleneck. Pied Piper wasn’t building hardware. They were making existing hardware do things nobody thought it could.

TurboQuant just dropped from Google Research. Percepta just proved the transformer is a literal computer. And the KV cache — the RAM of that computer — just got 6x bigger without a single new chip being manufactured.

What to do with this depends on where you sit.

If you’re running inference at scale, start tracking the compression frontier the way you track GPU pricing. It moves faster, and the ROI compounds with every model you serve. Enable FP8 KV cache in vLLM today; it’s not TurboQuant, but it hits the same bottleneck and it’s production-ready now. Community TurboQuant implementations are already available, with Google’s official release and mainline framework integration not far behind.

If you’re making infrastructure investment decisions, factor compression gains into your fleet planning before you sign that next hardware contract. The GPUs you already own may be worth 6x more by Q3 than they are today, and the urgency to buy next-generation hardware at premium prices looks different when the efficiency frontier is moving this fast.

If you’re building agents, design for the world where 600K-token effective context windows are standard, not experimental. The architectural choices you make now about chunking, retrieval, and state management will look very different in that world.

And if you’re an individual, someone using AI every day but not running your own GPUs, the play is different but equally real. The compression frontier will eventually reach you as cheaper tokens and longer context windows from your provider. But the memory problem you face right now isn’t about KV cache quantization. It’s about the fact that every AI you use forgets you. Every new chat session starts from zero, every tool switch loses your context. The $468 billion memory problem I wrote about in December 2024 hasn’t been solved; it’s just been pushed down to the individual level.

That’s why I built [Open Brain](https://github.com/NateBJones-Projects/OB1). It’s a personal knowledge infrastructure: one Postgres database with vector search, one MCP server, any AI plugs in. Thirty minutes of setup, ten cents a month, zero coding required. It won’t compress your model’s KV cache, but it solves the *other* memory problem, giving your AI a persistent, cross-tool memory of who you are, what you’re working on, and what you’ve told it before. While the research labs fight the infrastructure war over bits per vector, you can fight the practical war over whether your AI actually remembers what you said last Tuesday.

The infrastructure war determines what’s *possible*. The personal memory war determines what’s *useful*. And the compression frontier is about to make a lot more possible, very fast.

The third body is moving.

[![](https://substackcdn.com/image/fetch/$s_!fa_H!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F70413045-a100-47b7-98bf-d70b74f1985b_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!fa_H!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F70413045-a100-47b7-98bf-d70b74f1985b_1024x1024.png)
