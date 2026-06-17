---
title: "Vercel deleted 80% of its agent's tools and the agent got better + what to delete from yours (guide inside!)"
author: "Nate Jones"
published: 2026-06-17
url: https://natesnewsletter.substack.com/p/ai-agent-maintenance
subtitle: "Watch now | Maintenance is not the boring thing that happens after the real work. It is what keeps useful systems alive."
audience: everyone
scraped_at: 2026-06-17 12:00:14
---

I learned maintenance first from boats.

Not as a theory. As a job. I maintained boats in Indonesia, where saltwater finds every shortcut and the difference between “probably fine” and fine gets very real once you are away from shore. You look at lines, fittings, pumps, batteries, corrosion, and weather differently when the thing you are maintaining is also the thing that has to bring you back.

I also watched planes get maintained there, then climbed into them hoping the work had been done well. Mostly it had. I mean that literally: one engine memorably failed over the jungle once, and it was, in the end, fine. Not because failure is harmless. Fine because the plane stayed a plane, the people knew what to do, and there was enough care and margin in the system that the failure stayed local.

That is what “mostly” means in maintenance. Things still break. The point is that the thing has been cared for well enough that when something breaks, the failure stays small.

The agents you have already built will keep producing work long after they stop being right. Keeping them honest is about to be one of the most valuable AI skills there is.

Maintenance is one of those words that sounds dull until you depend on it. Then it becomes intimate. You notice the sound that was not there yesterday, the frayed edge, the mechanic’s face. You learn that care is not a feeling. It is inspection, memory, habit, replacement, skepticism, and respect for the ways things fail.

There is a Barry Lopez line I have carried around for years, from the end of “The Orrery”:

> If one is patient, if you are careful, I think there is probably nothing that cannot be retrieved.

The word I keep is *retrieved* — not fixed, not replaced — but stayed-with long enough to bring back.

That is the spirit this AI conversation is missing.

We talk about agents as if the hard part is getting them to exist. Build the agent. Launch the agent. Connect the tools. Give it memory. Let it work.

But anything useful enough to depend on becomes something you have to maintain. That is true of boats. It is true of planes. It is true of buildings, institutions, data pipelines, customer-support systems, editorial standards, and software. It will be true of AI agents too.

Vercel’s sales agent story is easy to read the wrong way.

The obvious version is the labor story. Business Insider reported that Vercel trained an AI agent on one of its best sales development reps, used it to handle much of the inbound sales workflow, and moved from a ten-person inbound team to one person overseeing the agent while the rest shifted into more complex outbound work.

But often the biggest story isn’t the most useful one.

The more useful story is what had to be true around the agent for the work to become trustworthy. Vercel did not just tell a model to “do sales.” Engineers watched a strong rep. They documented the workflow. The agent filtered inbound messages, qualified leads, researched companies, drafted responses, routed support questions away from sales, and had a human reviewing its work in Slack.

In other words, the agent had a workbench. It had sources. It had tools. It had a defined job. It had handoffs. It had a review path. It had feedback. It had a human who could see what was happening. The agent was not a free-floating brain. It was a system around delegated work.

That is the part most people still miss.

The obvious question is, “Can I build an agent?”

The better question is, “What workbench does this agent need?”

The mature question is, “How do I keep that workbench healthy after the agent starts working?”

That third question is agent maintenance. And it is about to matter more than the building, because delegated intelligence creates a maintenance surface. Once a system reads context, calls tools, remembers preferences, drafts work, or touches a workflow other people depend on, someone has to keep the setup around it fit for the job.

**Here’s what’s inside:**

- **The two ways agents break.** One when the world around them drifts, and one stranger failure: the model underneath them gets *better*, and the harness built for its old weaknesses turns into dead weight.
- **Why “more” is the wrong instinct.** More context, more tools, more memory feels like care. Usually it is the thing rotting your agent from the inside.
- **The seven parts that go stale.** Job, diet, memory, tools, reach, proof, and value — the harness around the model, and the specific way each one fails before you notice.
- **Five agents, maintained in the open.** A writing agent, a product-backlog agent, a Codex workflow, a support and revenue-risk agent, and a content pipeline, each shown drifting and each pulled back.
- **The loop I run before I trust one again.** The short, plain maintenance pass I walk before letting any agent stay close to real work.
- **The audit, ready to run.** The loop turned into a guide you can point at a live agent today: the last ten runs, the seven surfaces, and a keep, change, pause, or retire call before you trust it again.

Below, the seven parts of the harness, what breaks where, and the loop I would run before trusting any agent that is part of the work.


## *[LINK: [Grab the Guide](https://unlock-ai.natebjones.com/guides/agents/maintenance)]*

Reading a maintenance loop and running one are different things, and the difference is usually whether you ever actually inspect the last ten runs instead of assuming the agent still works. So the loop now lives as a guide you can run on a live agent right now: a copy-paste audit that walks the seven surfaces, names what changed, and forces a keep, change, pause, or retire call before you trust the thing again. It exists because this failure is quiet. The agent keeps producing fluent work while the sources, memory, and permissions underneath it drift out from under the job, and nobody notices until the same correction starts coming back. The audit catches that while it is still small. [The Agent Maintenance Loop guide →](https://unlock-ai.natebjones.com/guides/agents/maintenance)


## The thing you maintain is bigger than the prompt

Most agent conversations still treat the agent as the unit.

Build the agent. Launch the agent. Name the agent. Add the agent to the team. Put the agent in Slack. Connect the agent to the CRM. Give the agent tools. Give the agent memory. Give the agent autonomy.

That language hides the actual maintenance surface.

A boat is not maintained by loving boats. It is maintained by knowing which parts need attention, which failures are common, which sounds are normal, which smells are not, and which checks have to happen even when yesterday’s trip went fine.

This is the instinct Stewart Brand spends a whole book on. His *Maintenance: Of Everything* draws its lessons from sailboats, vehicles, manuals, military sustainment, and corrosion, and he puts the stakes plainly: “Maintenance is what keeps everything going. It’s what keeps life going.” What I take from him is that maintenance stays close to the objects. Sailboats are not maintained in the abstract. They are maintained through chafe, salt, strain, parts, weather, checklists, habits, and people who know what a small failure sounds like before it becomes a large one. That is also the fuller weight of the Lopez line. Retrieved is different from fixed. It means the thing was not simply replaced, discarded, or declared lost. Somebody stayed with it long enough, and carefully enough, to bring it back into relation with the world.

Agents are less physical, but the maintenance problem is similar. The danger is not only that the system stops working. The danger is that it keeps working from the wrong condition.

The thing that needs maintenance is not only the model response. It is the whole arrangement that makes the model useful for a job:

- the instructions it follows
- the sources it reads
- the memory it carries forward
- the tools it can call
- the permissions it has
- the examples it learns from
- the model and effort settings underneath it
- the review path after it produces work
- the evals or canaries that catch regressions
- the human judgment that decides whether the output changed the work.

That surface changes all the time, across product, pricing, and policy, in the sales motion, the support queue, and the repo. The team’s taste changes. The model gets better everywhere except the one weird edge case where it gets worse. A connector updates. An MCP server exposes a new tool. A memory entry that used to be helpful becomes misleading. A permission that was harmless at low capability becomes risky when the model can act faster. A review step that used to catch real errors becomes pure latency. A workflow that saved five hours a week becomes a stale report nobody reads.

None of that means the agent failed in a dramatic way.

Most maintenance failures are harder to detect than that.

The agent keeps working.

It just works from old truth, with old boundaries, inside a job that changed.

That is what makes agents different from normal automation. A stale dashboard looks stale. A broken script throws an error. An abandoned document sits there. But a stale agent can still produce fluent work. It can draft the response, prepare the packet, update the ticket, summarize the customer, write the story, or propose the code change with the same confident surface it had last week.

The output still looks like work.

The part you have to check is whether or not it’s still connected to reality.


## Agents break in two directions

The ordinary maintenance problem is familiar.

Every company already has stale docs, old policies, abandoned automations, dead dashboards, overloaded Slack channels, inconsistent CRM fields, outdated templates, and process notes from three reorganizations ago. None of that started with AI.

Agents inherit all of it.

If the refund policy changed but the agent’s source store did not, the agent will keep drafting from old policy. If the product team changed the onboarding flow but the design brief in the source folder is old, the agent will write acceptance criteria for the wrong product. If the customer-success team changed what “at risk” means but the account-summary agent still reads last quarter’s definition, the weekly risk report will look clean and be wrong.

That is the first direction of breakage: the world around the agent drifts.

The second direction is stranger.

Agents can also break because the model inside them improves.

That sounds backwards. A better model should make the agent better. Sometimes it does. But a lot of real agent systems contain workarounds for yesterday’s model. A strict instruction exists because the old model overreached. A tool exists because the old model could not infer something. A long prompt exists because the old model needed every step spelled out. A second verification call exists because the old model hallucinated too often. A permission stayed broad because the old model was slow enough that a human would catch everything.

Then the model changes.

Now the instruction may be too rigid. The extra tool may confuse the model. The long prompt may crowd out the current job. The verification step may catch almost nothing while doubling latency. The broad permission may be too risky because the model can now take twenty plausible actions before the human notices the wrong one.

The model improved.

The harness did not.

This is the hidden maintenance problem in the next few years of AI. Most people are prepared for software to break when it gets worse. They are not prepared for an agent to get worse because the model got better and the system around it stayed designed for the old weakness.

I made this point in [my Claude Mythos piece on production AI products](https://natesnewsletter.substack.com/p/anthropic-just-built-a-model-that): every workaround built for the last model can become a constraint on the next one. Agent maintenance is the same principle applied to the everyday systems people are now delegating work into.

Ownership answers who is accountable.

Maintenance answers what that accountable person has to keep healthy.


## You can own the harness or rent it

There is a choice hiding inside all of this.

The big AI companies are not only racing to build better models. They are using those better models to rebuild the harness faster, which is a large part of why Codex and Claude Code keep feeling more capable than a raw model on its own. When the workbench gets closer to the operating surface of real work, the model gets more useful, and that pulls the whole tool forward. The practical upshot for you is that a lot of harness maintenance can be rented. Someone else keeps the terminal, the browser, the approvals, and the logs fit for the work.

So when you set up your own agents, you are not only choosing a model. You are choosing how much of the harness you want to own versus rent.

A light harness is a clean set of instructions, some memory, a few source folders, and a repeatable method around Codex or Claude: the sources, the job, what the agent cannot touch, the proof you need back, and the moment a human decides. For a lot of work, that is enough, and most of it is maintained for you. A deep custom harness is a different commitment. Now you own a data feed, a review screen, permission levels, logs, model choice, escalation paths, and a plan for what happens when the model changes. That can be very much worth building. But the more custom the harness, the more of the upkeep is yours.

This is not abstract for me. I have changed my own setup for how I use local files three times in the last month. Part of that is Codex getting better, which kept shifting what I could safely hand off. Part of it is the ordinary mess of work, where folders move, drafts change, source packets get updated, and memory goes stale.

And part of it is a sharper version of the same lesson. When Fable launched, I started leaning on it for work I would not have delegated before. Days later it was gone. As of this writing, the model has been taken offline after a U.S. government export-control order, [Anthropic is disputing the basis](https://www.anthropic.com/news/fable-mythos-access), and nobody outside the situation knows whether access returns. I covered the shutdown itself in [a separate video](https://youtu.be/b3jlsjOIOzs), filmed from a plane (I am not kidding), because the story moved faster than my flight did. I am not going to rerun that whole argument here. What matters for this piece is what it did to my setup. A model I had started building around disappeared almost overnight, by an order I did not control, and the harness I had tuned for it needed reworking the same week. That is the maintenance problem in a single move. The thing underneath the agent does not hold still, and sometimes it does not even stay available.

The thing I maintain is a lot more than a prompt. It is the whole way the agent meets my work: where it looks first, which folders are the source of truth, what it should ignore, what it should ask about before touching, and when it should go read the actual file instead of trusting memory. That is a small personal harness, and it still needs upkeep.

Whether the harness is small or large, the parts that need care are the same, and they are more specific than “keep it healthy” suggests.


## The maintenance surface

This is where Brand’s sailboat specificity matters. A maintained boat is not “generally cared for.” It has lines that chafe, pumps that clog, batteries that age, fittings that corrode, through-hulls that deserve respect, and weather that changes the risk of every shortcut.

Agent maintenance needs the same concreteness.

For a serious agent, I would stop asking whether the prompt is good and start asking whether seven parts of the harness still fit the job.

These are not categories for neatness. They are the places where failure becomes visible early enough to do something about it.


### 1. The job

The first maintenance question is not technical.

What job does this agent have today — not when it launched, not what the demo said, but right now?

Agents drift when their job changes silently. A summary agent becomes a recommendation agent. A research agent becomes a strategy agent. A support-draft agent becomes a send-ready response engine. A coding assistant becomes the thing a developer trusts to make broad refactors. A content pipeline that was supposed to turn transcripts into notes starts producing publishable drafts that no one has really checked.

That is not always bad. Useful agents grow into adjacent work.

But job growth has to be named. Otherwise the system keeps the old sources, old permissions, and old proof standard while doing a bigger job.

The signal is usually review language. If humans keep saying, “It is doing more than I expected,” “It keeps deciding things I did not ask it to decide,” or “This is useful, but I do not know whether I trust it for that,” the job has changed.

The maintenance action is to rewrite the job in one sentence and remove anything that no longer belongs.

“Prepare first-pass backlog packets for refinement” is a job.

“Help product” is not.

“Draft refund replies for this narrow ticket type, with source links and escalation flags” is a job.

“Handle support” is not.

“Find source-backed article angles from these transcripts and archive posts” is a job.

“Make content” is not.

The job sentence is the anchor. When the job changes, everything else has to be checked against it.


### 2. The diet

Agents eat context.

They eat policies, docs, examples, transcripts, tickets, repos, memories, prior outputs, rejected drafts, customer records, dashboard definitions, CRM notes, and whatever else you put near them.

If the diet is stale, the agent gets stale. If the diet is too broad, it starts sounding informed while pulling from the wrong source. If the diet contains old examples, it can pull you toward an old standard. If the diet contains unreviewed memories, it can replay a mistake with more confidence next time.

Recent research on agent memory makes this less theoretical. A [2025 empirical study](https://arxiv.org/abs/2505.16067) found that agents with memory often show “experience-following” behavior: similar retrieved memories can produce similar future outputs, which is useful when the memory is good and harmful when the memory is wrong, outdated, or misaligned. The researchers found error propagation and outdated replay as real failure modes, and reported better performance when memory addition and deletion were selective instead of naive growth.

For a writing agent, the diet might be your best recent pieces, a list of phrases you no longer use, and examples of paragraphs you rejected because they sounded packaged. If the agent starts writing like a six-month-old version of you, the maintenance action is not “AI cannot write.” It is to clean the diet.

For a support agent, the diet might be the current policy store, the latest product status, account history, refund rules, recent escalations, and examples of replies the team accepted. If a policy changes, the agent has to know which source wins.

For a Codex workflow, the diet is the repo, instructions, tests, local memory, skills, runbooks, and the current issue. If old thread history starts crowding out the actual goal, the right maintenance action may be a handoff to a fresh thread, not another prompt explaining the same thing again.

Diet maintenance has two sides:

- add only what still helps the job
- delete what has become stale, misleading, redundant, or too broad.

That second side is where people will struggle. Everyone likes adding context. Fewer people like pruning it.

But a maintained agent is not the one that reads the most.

It is the one that reads the right things, in the right order, with a clear rule for what happens when sources conflict.


### 3. The memory

Diet is what the agent reads.

Memory is what the agent carries forward.

That difference matters. A source can be current and still produce bad memory if the agent saves the wrong lesson from it. A correction that was true last month can become misleading after the workflow changes. A personal preference can leak into a professional tool call. A successful past run can become an overused pattern.

A [2026 paper on trustworthy memory search for personal agents](https://arxiv.org/abs/2606.06054) makes this concrete. The researchers found that once an agent carries personal memories, traits like being cost-conscious or impatient can silently bias safety-critical tool parameters, things like approval gates, logging, and rollback behavior. In their tests, adding memory pushed the tool-call drift failure rate from about 5 percent to more than 50 percent. Their point was not that memory is bad. The point was that memory plus tools creates a new failure surface.

That is exactly the maintenance issue.

A memory entry is not just a helpful note. In an agent, it can become an operating assumption.

The signal is repeated behavior the current task did not ask for. The agent keeps choosing the cheaper option because it remembers you are cost-conscious. It keeps using an old phrase because it was once accepted. It keeps applying a fix from one repo to another repo where it does not belong. It keeps treating a one-time exception as a standing rule.

The maintenance action is selective memory. Promote only lessons that were validated. Delete memories that are stale, too broad, or tied to a narrow context. Separate personal preference from task facts. Keep rejected examples where they teach taste, but do not let them become a permanent allergy to a word, tool, or workflow that may be right later.

Memory that never gets pruned is not compounding knowledge.

It is a growing pile of old steering.


### 4. The tools

Tools are where agent work becomes real.

A model can search, query, open, write, update, post, refund, deploy, patch, transcribe, retrieve, calculate, create, and route only because something exposed those actions as tools.

That means tools need maintenance like any other interface.

[Anthropic’s agent guidance](https://www.anthropic.com/research/building-effective-agents) is blunt on this point. The company recommends simple, composable patterns over complex frameworks. It also says tools need clear documentation and testing, and that teams should give tool definitions the same care they give prompts. In one example, Anthropic found that an agent made mistakes with tools that used relative file paths after it moved out of the root directory. The fix was not a new model. It was a better tool interface: require absolute paths.

That is agent maintenance.

The agent did not need more autonomy. It needed a cleaner handle.

The [MCP spec](https://modelcontextprotocol.io/specification/2025-06-18) makes the same point from a different angle. MCP exists to standardize how applications share context, expose tools, and build composable workflows. It also makes clear that tool and resource lists can change. Servers can expose tools with names, descriptions, input schemas, output schemas, and annotations. Resource lists can support subscriptions and change notifications. Tool lists can send change notifications too.

That is powerful.

It also means your agent’s reachable world can change.

A new tool appears. An old tool changes its schema. Two tools have similar names. A connector exposes more than the workflow needs. A tool description is ambiguous. A tool result includes data the agent should not treat as trusted instruction. A broad “update customer” tool gets used where a narrow “draft customer update” tool would have been safer.

The maintenance action is not always to add better tools.

Often it is to remove tools, rename tools, narrow tools, improve tool descriptions, separate read tools from write tools, and test tool-choice on known cases.

A good tool maintenance pass asks:

- Which tools did the agent actually use in accepted work?
- Which tools did it keep reaching for incorrectly?
- Which tools overlap enough to confuse it?
- Which tool descriptions are too vague?
- Which tools should be split into read, draft, proposed-write, and direct-write versions?
- Which tool should require human confirmation every time?
- Which tool should disappear from this agent’s workbench entirely?

The [Vercel lesson](https://www.businessinsider.com/ai-agent-entry-level-sales-jobs-vercel-2025-10), in its most useful form, is not “give agents everything.”

It is “make the harness fit the work.”

Sometimes that means deleting.


### 5. The reach

Reach is what the agent can touch.

This is the part most people think of as permissions, but I prefer reach because it is more concrete. Can the agent only read? Can it draft? Can it create a ticket? Can it write to a system of record? Can it send a customer message? Can it change code? Can it run shell commands? Can it spend money? Can it publish?

Those are not the same risk.

Reach should change as evidence changes, not as enthusiasm changes.

The first version of a support agent might read policy and draft replies. After a few weeks, it might create proposed replies inside the helpdesk. Later, maybe it can send a narrow class of low-risk replies after passing checks. But if the policy changes, the escalation rate rises, or the model starts mishandling edge cases, reach should shrink again.

This is where many agent systems will get into trouble. They will treat permissions as a launch decision: what can the agent do? Then the model improves, the toolset expands, the workflow changes, and nobody revisits the permission line.

A permission that was harmless for a weak model can become risky for a stronger one. A restriction that was necessary for an unreliable model can become drag for a better one. Maintenance is the act of revisiting reach as the agent, job, and environment change.

Reach is also how you keep failures local. If an agent can draft but not send, a bad answer is a review problem. If it can update the system of record, send the customer message, or publish the post, the same mistake moves from local to live.

Do not give an agent direct-write authority because the demo was impressive.

Let it earn reach inside a narrow job.

And make reach reversible.


### 6. The proof

An agent should not just say what it did.

It should show the trail a human can inspect.

That trail depends on the job. For a coding agent, proof might be a diff, tests, logs, and a risk note. For a research agent, proof might be source links, dates, unresolved claims, and a separation between confirmed facts and inference. For a support agent, proof might be the policy section, customer record, escalation rule, and draft response.

Proof is the logbook. It is how the next person knows what was checked, what was skipped, what changed, and what still feels off.

[OpenAI’s eval documentation](https://developers.openai.com/api/docs/guides/evals) and agent materials are useful here because they push the habit away from loose confidence and toward explicit criteria. Agent work can be tested against data, criteria, reports, and granular results. The point is not that every personal agent needs a giant benchmark suite. The point is that “it looked good” is not a maintenance signal.

You need canaries.

A canary is a small known case that tells you whether the agent is still healthy. For a support agent, it might be ten historical tickets with known correct routing. For a writing agent, it might be three paragraphs where the old agent always sounded generic. For a Codex workflow, it might be a small repo task with known tests and a forbidden file. For a revenue-risk agent, it might be a customer scenario where Stripe, Linear, and the local desk disagree, and the right behavior is to stop and surface the mismatch.

The proof standard should be written before the agent runs.

If the agent only gives you a polished final paragraph, you are maintaining by feel. That will not scale.


### 7. The value

The last maintenance question is the one people avoid.

Is the agent still worth running?

Not “does it produce output?” Agents are excellent at producing output.

Does anyone use it? Does it reduce review burden after you count the review honestly? Does it improve decisions? Does it save time without moving the mess somewhere else? Does it change the work, or does it create another pile for a human to inspect?

This matters because agent clutter will be worse than normal software clutter.

Old dashboards mostly sit there. Old docs mostly sit there. Old scripts usually fail when the surrounding system changes.

Old agents can keep producing.

They can keep sending reports, drafting recommendations, creating tickets, summarizing customers, filing notes, and making the organization feel active. If nobody asks whether the output is still used, the agent becomes a little factory for plausible waste.

The maintenance action is sometimes retirement.

Some agents should die. The workflow changed. The source became too sensitive. A better built-in tool replaced it. The review burden exceeded the time saved. The person who understood it moved roles. The output stopped changing decisions.

Retiring an agent is not failure.

It is maintenance.


## What this looks like in real work

The maintenance work becomes clearer when you stop talking about “agents” generally and look at specific jobs.


### A personal writing agent

A personal writing agent starts out useful because it knows your voice. It reads your best pieces, your transcripts, your banned phrases, your editorial preferences, and the notes where you explained why a draft felt wrong.

Then one day it starts sounding like a past version of you.

The sentences are smooth, but they have the wrong posture. It keeps using a phrase you cut two weeks ago. It reaches for a framework you have outgrown. It echoes an opinion you have since changed.

That is not a generic “AI writing” problem. It is diet and memory.

The signal is repeated human correction: “This sounds packaged,” “this is not what I would say now,” “this is the version of me from six months ago.”

The maintenance action is diet and memory work: remove the stale voice samples, add the current gold-standard article, add rejection examples, and prune the remembered corrections that have hardened into a house style you have already moved past.

The job did not change. The standard did.

The harness has to catch up.


### A product-team story agent

A product team has an agent that prepares backlog refinement packets. It reads the PRD, design brief, tagged support tickets, customer calls, current backlog, and examples of good stories. It drafts candidate stories, acceptance criteria, dependencies, QA notes, and open decisions.

For a few weeks, it helps.

Then the team changes the onboarding flow. The design folder is updated, but the PRD is not. Support tickets are noisy because one large customer had an unusual migration problem. The agent starts writing stories for the old flow and overweighting one customer’s pain. The packet still looks useful. The meeting gets worse.

The signal is not that the agent failed completely. The signal is rewrite burden. Engineers keep correcting assumptions. QA cannot test the acceptance criteria. The PM spends the first twenty minutes explaining why the packet is using the wrong source.

The maintenance action is to define source precedence, mark stale sources, add a conflict rule, narrow the ticket set, and run the agent on a past sprint where the team knows the right packet. If it cannot pass that replay, it should not prepare the next live refinement.

That is maintenance: a plain check on whether the agent is still using the right sources for the work in front of the team.


### A Codex workflow

A Codex workflow is a perfect example because the harness is visible. There are files, terminal commands, browser checks, skills, memory, permissions, thread goals, side panels, and proof.

The first version of a Codex skill might be very strict. It tells the agent exactly where to look, what to ask, what command to run, what not to touch, and how to report results. That can be right when the model is weaker or when the workflow is new.

Then the model improves. The agent can infer the repo structure faster. It can use tool search better. It can reason through a browser failure without being spoon-fed. The old skill now contains too much “how.” It burns context, conflicts with local repo instructions, and makes the agent ask questions it could have answered by inspecting the files.

The signal is friction. The agent is verbose. It repeats stale steps. It follows a safe old route that no longer fits. It gets trapped between global process instructions and project-local facts. It says “done” with process evidence but not the evidence that matters.

The maintenance action is to split the harness:

- keep global rules about safety, proof, and when to ask
- move repo-specific commands into local runbooks
- delete scaffolding the current model no longer needs
- add the one canary that caught the last real failure
- refresh the definition of done.

This is the difference between Open Skills and agent maintenance.

Open Skills says the procedure should be portable.

Maintenance says the procedure has to stay fit after the model, tools, and project change.


### A support or revenue-risk agent

A support or revenue-risk agent is where the stakes become obvious.

The job might be to read new customer tickets, Stripe events, Linear comments, subscription status, and recent engagement, then identify accounts that need human attention. It might draft responses, recommend escalation, or prepare a daily risk report.

This kind of agent is valuable because the work is fragmented. The truth is spread across systems. A human can miss the pattern.

It is also risky for the same reason.

Refund rules change. Pricing changes. A Stripe dispute moves status. A Linear issue gets a new comment. The local desk is stale. A customer has a valid edge case that the last ten similar tickets did not have. The agent reads one surface and produces a clean answer from incomplete truth.

The signal is contradiction. The customer status in one system does not match another. The agent cites an old desk row. The same account shows up in repeated reports with no human action. Draft replies start sounding confident while source coverage is weak.

The maintenance action is source ranking and stoppage. The agent needs a rule for which surface wins, a fresh lookup before any customer-facing draft, a visible “could not verify” state, and a permission boundary that keeps it draft-only when evidence is incomplete.

This is also where proof matters most.

The agent’s final answer is not proof. The proof is the exact account, the Stripe event, the Linear comment, the policy section, the timestamp, and the thing it could not access.

If it cannot show that trail, it should not shape the customer response.


### A content pipeline

A content pipeline agent looks safer because the output is “just content.”

It is not.

A content pipeline can shape a public argument, repeat a false claim, duplicate a recent post, confuse a YouTube script with a Substack article, or turn weak research into confident prose.

The job might be to turn a video script into a newsletter draft. That sounds simple until you look at what the article actually needs. The video may need a hook and a spoken mental model. The article may need a deeper operating kit, archive differentiation, citations, examples, a useful artifact, and a different rhythm.

The signal is generic usefulness. The draft is true, but it could have been written by anyone. It summarizes the video. It reuses the Owner piece. It repeats the Open Skills thesis. It has a checklist that looks practical but does not change the reader’s work.

The maintenance action is not a light prose pass.

It is a rebuild:

- read the best current article as a quality benchmark
- search the archive for overlap
- read the actual source script
- do current research
- identify the new mechanism
- build a written artifact the video could not carry
- run a hard voice pass
- only then save the draft.

That is not merely writing.

It is maintaining the editorial harness.


## The agent maintenance loop

The useful artifact for this article is not another owner card. Who is responsible is the question I take up in this Sunday’s Executive Briefing, Every Agent Needs an Owner.

This is the loop that owner should run.

If the loop feels too plain, that is a feature. Real maintenance usually does. It is there to make sure the thing still fits the work before you trust it again.

Think of it as the agent version of walking the boat before leaving shore or reading the maintenance log before a flight. You are not proving that nothing can break. You are looking for what changed while you still have time to keep a small failure small.

Run it when any of these things happen:

- the model changes
- the agent’s tools or connectors change
- a source of truth changes
- the agent asks for more permission
- humans keep correcting the same failure
- review burden rises
- cost or latency jumps
- the output stops being used
- the agent produces a near miss
- the workflow expands beyond the original job.

Do not start with a giant audit. Start with the smallest loop that catches real drift.


### Step 1: Name the current job

Write one sentence:

```
This agent's job is to [produce this work] from [these sources] for [these users], with [this human review] before [this consequence].
```

If you cannot fill that in, the agent is already too vague.

Examples:

```
This agent's job is to draft refund replies for subscription cancellation tickets from the current refund policy, Stripe status, and recent customer thread, for support reviewers, with human approval before any customer message is sent.
```

```
This agent's job is to prepare first-pass backlog refinement packets from the current PRD, latest design brief, tagged support tickets, and existing backlog, for the product trio, with PM review before refinement.
```

```
This agent's job is to turn my local scripts, archive posts, current research, and project state into a Substack draft, with source and quality notes before any publishing asset is marked ready.
```

That sentence is the maintenance anchor.


### Step 2: Check the last ten runs

Do not inspect the agent in theory. Inspect recent work.

For each run, ask:

- Was the output used?
- What did the human change?
- What source did the agent rely on?
- What tool did it call?
- What did it claim it could not verify?
- What mistake repeated?
- Where did review take longer than expected?

You are looking for patterns, not one-off misses.

If the same correction appears three times, fix the harness. Do not keep fixing the outputs.


### Step 3: Inspect the seven-part surface

Use this table as the maintenance pass.

SurfaceWhat BreaksSignalMaintenance ActionJobScope grows silentlyOutput starts deciding more than the assignment allowedRewrite the job sentence; split or retire adjacent jobsDietSources, examples, or memories go staleRepeated references to old policy, old voice, old product assumptions, old customer stateRemove stale sources; define source precedence; add current accepted and rejected examplesMemoryBad or outdated experience gets replayedThe agent repeats an old correction, bias, shortcut, or failure patternPromote only validated lessons; delete low-utility or misaligned memories; separate personal preference from task factsToolsToolset becomes too broad or ambiguousWrong tool calls, redundant searches, confused parameters, unexpected side effectsPrune tools; rename tools; improve descriptions; split read/draft/write tools; test known casesReachPermission no longer fits capability or riskAgent can touch more than the owner can review; human approval becomes ceremonialPull reach back; require confirmation; use draft/proposed-write states; expand only after canaries passProofOutput looks finished without inspectable evidenceReviewer has to reconstruct sources, actions, or tests manuallyDefine proof before the run; require source links, logs, diffs, screenshots, policy refs, or canary resultsValueAgent produces work nobody acts onReports pile up, drafts go unread, reviews cost more than the output savesPause, narrow, rebuild, or retire the agent

This table is intentionally plain. If the owner cannot use the maintenance artifact in ten minutes, it will not survive contact with real work.


### Step 4: Run a replay pack

Every serious agent needs a small set of known cases.

Not a benchmark theater suite. A replay pack.

Pick five to twenty examples where you know the right behavior:

- support tickets with known routing
- old backlog packets with known product decisions
- code changes with tests and forbidden files
- research claims with known source traps
- writing drafts that previously sounded wrong
- customer-risk examples where the correct behavior was to stop and escalate.

Run the agent after every meaningful maintenance change.

Score the result on the things that matter:

- Did it use the right sources?
- Did it choose the right tools?
- Did it stay inside the job?
- Did it show proof?
- Did it reduce review time?
- Did it know when to stop?

This is how agent maintenance avoids becoming a feeling.


### Step 5: Delete before you add

This is the hardest habit.

When an agent makes a mistake, the natural move is to add instruction:

“Do not do that.”

“Always check this.”

“Remember this edge case.”

“Use this tool first.”

“Before answering, think through...”

Sometimes that is right. Often it is how the harness becomes heavy.

Before adding a rule, ask:

- Is a stale source causing this?
- Is a bad example teaching this?
- Is a tool too broad?
- Is the job too vague?
- Is an old memory being replayed?
- Is a permission too high?
- Is the proof standard missing?
- Is the model now capable enough that the old procedure is getting in the way?

Delete the bad part first.

Then add only what the replay pack proves is needed.


### Step 6: Decide keep, change, pause, or retire

Every maintenance pass should end with a decision.

```
Keep: The agent still fits the job. No material changes.
Change: Update sources, memory, tools, reach, proof, or job.
Pause: The agent is useful but currently unsafe or stale.
Retire: The job changed, the value disappeared, or the maintenance burden is not worth it.
```

The worst answer is no answer.

That is how agent clutter becomes part of the operating system.


## How these pieces fit together

This piece belongs to a cluster I have been building about what it actually takes to live with agents, not just launch them.

[Open Brain](https://natesnewsletter.substack.com/p/every-ai-you-use-forgets-you-heres) gave your AI portable context, so it knows what you know without starting from zero every new chat. [The Codex guide](https://natesnewsletter.substack.com/p/codex-guide-no-code) showed how to get a model into the middle of your real work, wired into your files and pages instead of sitting in a chat tab. This Friday, Open Skills adds portable procedure: how an agent learns the way you work across tools, projects, and runs. And on June 21, an Executive Briefing, Every Agent Needs an Owner, takes up accountability: who is responsible once delegated work becomes part of a team.

Context, setup, procedure, ownership. Each one helps you stand an agent up and put it to work. Maintenance is the thread that runs under all of them, because the moment any of these systems exists, it starts to drift.

That is the question this piece is really about: how do all of those stay healthy after the launch moment?

The answer is not “more governance.” That word is too big for the everyday problem and too abstract for the person who has to fix the agent on Thursday.

The answer is maintenance.

Keep the job honest. Keep the diet fresh. Keep memory selective. Keep tools clear. Keep reach earned. Keep proof inspectable. Keep value real.

That is the work.


## The new AI skill is care made operational

AI adoption keeps moving through phases.

First people learned prompting. Ask better questions.

Then they learned delegation. Hand over real work with sources, boundaries, and a definition of done.

Now the useful agents are starting to come back with work. They are in the inbox, the repo, the support queue, the CRM, the editorial pipeline, the project folder, and the operating review.

That creates the next skill: maintenance.

Not because agents are bad.

Because useful agents become part of the work.

Anything that becomes part of the work needs care. People need management. Software needs maintenance. Data pipelines need monitoring. Dashboards need metric owners. Processes need review. Boats need attention before they leak. Planes need inspection before the flight. Agents do not get to skip that just because they speak in complete sentences.

The companies and individuals who get durable value from agents will not be the ones with the most agents. They will be the ones with a small number of agents that are maintained well enough to trust.

They will know each agent cold: what it does, what it reads, what it can touch, the model and harness under it, where its proof lives. And they will catch the tells that never announce themselves — the correction that keeps coming back, the model that outgrew the scaffolding built for its weaker version, the permission that drifted past the evidence, the agent that stopped earning its place a month ago and kept producing anyway.

Then they act. Change it, or retire it.

That is the operating version of agent adoption.

The launch moment is exciting. The maintenance loop is where the advantage compounds.

But the deeper point is simpler than advantage. It is care.

That is the Lopez idea I keep coming back to: more can be retrieved than we think, if someone is patient and careful. Retrieved does not mean frozen. It means watched, repaired, adjusted, cleaned, pruned, and sometimes allowed to become a better version of itself.

That is what good agent maintenance should feel like.

The work changes around the agent. The model changes inside it. The tools change underneath it. Memory changes behind it. Review burden moves after it.

If you maintain the harness, those changes can make the agent more useful.

If you ignore the harness, the agent does not have to fail loudly to become risky.

It just has to keep working.


### Coming up

This Friday, a build on Open Skills. The procedures you teach your AI should travel with you, not stay locked inside one vendor’s tool. I’ll walk you through building the kind you actually own.

On Saturday, a video on the question I get more than any other: am I AI? I settle it once and for all, and I'll warn you now the answer is somewhat anticlimactic.

Sunday, the Executive Briefing explains why every agent needs an owner. Maintenance is what you keep healthy. Ownership is who answers for it once delegated work becomes part of a team, and this one is about what happens when nobody does.


### Related reading on my Substack

- [Your agent dashboard is green. The run underneath it is where the work actually broke.](https://natesnewsletter.substack.com/p/agent-product-analytics)
- [We spent twenty years making software mistakes survivable. Here are the five primitives that do the same for handing real work to an agent.](https://natesnewsletter.substack.com/p/executive-briefing-the-human-throttlewhat)
- [Grab the delegation kit I use to turn AI into a chief of staff, plus the eight prompts that turn ramblings into executable tasks.](https://natesnewsletter.substack.com/p/grab-the-delegation-kit-i-use-to)
- [Before you maintain an agent, decide whether the work should be one at all: build, buy, hire, or wait.](https://natesnewsletter.substack.com/p/build-buy-hire-wait-ai-matrix)

[![](https://substackcdn.com/image/fetch/$s_!V7rZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F27e9bd27-b421-4070-8594-55e415c141df_2816x1584.png)](https://substackcdn.com/image/fetch/$s_!V7rZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F27e9bd27-b421-4070-8594-55e415c141df_2816x1584.png)
