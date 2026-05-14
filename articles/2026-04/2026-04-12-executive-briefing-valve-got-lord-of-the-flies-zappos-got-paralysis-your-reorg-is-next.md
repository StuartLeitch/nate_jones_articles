---
title: "Executive Briefing: Valve Got Lord of the Flies. Zappos Got Paralysis. Your Reorg Is Next."
author: "Nate Jones"
published: 2026-04-12
url: https://natesnewsletter.substack.com/p/executive-briefing-44-of-companies
audience: everyone
scraped_at: 2026-05-14 14:33:44
---

Forty-four percent of U.S. workers say their employer cut at least one layer of management in the past year, according to Korn Ferry. The logic was sound: AI handles coordination, the hierarchy was overhead, flatten and move faster. Meta stripped out entire layers and the stock nearly tripled. Shopify told teams to prove AI couldn’t do the job before approving a hire. The direction is right. The execution, at most companies, is not — because it treats the management layer as one function when it’s actually three, each on a completely different automation timeline.

The three functions are routing (moving information between people and teams), sensemaking (interpreting what that information means for specific decisions), and accountability (telling people whether they’re on track and helping them grow). Routing is automatable now. Sensemaking is 18 to 36 months out. Accountability may never be fully automatable. Every company that removed all three at once — Valve, Zappos, Medium, GitHub — hit the same wall. The ones doing it today are reproducing those failures at vastly larger scale, and most won’t recognize the damage until the reversion is already underway.

Most companies that flatten misdiagnose what breaks. The symptoms of a sensemaking vacuum — six people read the same strategy memo, propose six incompatible responses, and nobody in the room has the authority or context to resolve it — look exactly like a communication problem. So the org does what orgs always do: more alignment meetings, another all-hands, a cross-functional Slack channel. That’s adding routing. Routing is the one function AI already handles. You’re spending leadership attention to manually do what software does better, while the thing that’s actually broken goes unaddressed.

Underneath that, the accountability gap compounds. Your best mid-tenure people — the ones with options — stop waiting for feedback that isn’t coming and start interviewing. By the time the attrition data surfaces, you’ve lost the people hardest to replace and spent six months solving a problem you didn’t have.

**This briefing covers:**

- **The three jobs inside every manager.** What the management bundle actually contains, why each component has a different shelf life, and the specific failure mode you get when you remove each one without replacement.
- **The flat-org graveyard.** Valve, Zappos, Medium, and the pattern that repeats with such consistency it should be treated as a structural finding — not a cautionary tale.
- **Three companies hollowing out right now.** How Kimi, Block, and Meta are each decomposing the management bundle differently, what’s working, what’s breaking, and what each model trades away.
- **What happens to the managers.** A direct answer to the question you’re actually asking, with a one-week audit you can run on your own calendar.
- **The sequence that works.** Replace routing. Protect feedback. Concentrate sensemaking. In that order — and why reversing any two produces a specific, predictable disaster.

The companies that diagnose which function they actually lost will fix this in a quarter. The ones that keep treating it as a communication problem will re-add layers within two years and call it “maturing the organization.”


## **LINK: [Executive Circle WhatsApp group](https://chat.whatsapp.com/LqpF3i5wDYv1EdraJYKplL?mode=gi_c)**

Join other senior leaders working through the same strategic decisions we cover here, sharing what’s actually working and what isn’t. No fluff, no LinkedIn energy. If you’re an Executive Circle member, we’d love to see you there.


## **LINK: [Executive Circle MCP Server](http://promptkit.natebjones.com/executive/mcp)**

A read-only MCP server that gives your AI — Claude, ChatGPT, whatever you use — direct access to my entire published content library. You connect once, and then the archive just *shows up* inside your normal AI conversations. You ask your AI a question during your actual work, and it pulls from everything I’ve published to answer it.

Think of it as a research assistant that’s already read every word we’ve put out — and it’s sitting inside the tool you’re already using. You can even paste in something you’re working on and ask it to surface the most relevant posts. It’s six read-only tools — search posts, read full posts, browse recent content, search prompt kits, read full kits, browse all kits. No write access, no drafts, no behind-the-scenes material. Just the published, finished work, available the moment you need it.

Setup takes about ninety seconds.

- Register once at [promptkit.natebjones.com/executive/mcp](http://promptkit.natebjones.com/executive/mcp)
- Enter your access code (**executive\_circle**) and email, and get a personal connector URL with a unique token.

  - In Claude, you go to Settings → Connectors → Add custom connector, paste the URL, and you’re done.
  - ChatGPT works the same way through Settings → Apps & Connectors.
  - If you use Claude Code, Cursor, or any other MCP-compatible client, the URL works there too.

The way I think about it: your subscription now works inside your AI. Have fun!


## LINK: [Grab the prompts](https://promptkit.natebjones.com/20260402_120_promptkit_1)

This briefing gives you the framework. The prompt kit turns it into four decision tools you can use this week. The Management Function Audit takes a specific layer in your org and decomposes it into routing, sensemaking, and accountability — with percentages, automation readiness scores, and a recommendation for what to automate, concentrate, or protect. Run it before you cut anything. The Reversion Risk Scorecard is for orgs that have already flattened: it takes the symptoms you’re seeing, scores them against the three failure modes from the graveyard section, and produces a one-page red/yellow/green assessment you can bring to your leadership team. The Selective Compression Sequencer builds the actual phased plan — which roles to compress in what order, who absorbs which function, what tooling to stand up first, and a reversion signal watchlist so you catch problems at week six instead of month six. And the Manager Career Repositioning Audit is the individual version: walk through your last five days of work, get an activity-by-activity breakdown of your routing/sensemaking/accountability split, an honest exposure score, and a 90-day plan to shift toward the functions that aren’t going anywhere. If you run the company, start with Prompt 1 or 2 depending on whether the restructuring has happened yet. If you’re a manager wondering where you stand, skip straight to Prompt 4.


## The three jobs inside every manager

If you watch what a decent manager actually does for a week, not what their job description says, what they actually do, you’ll find their time splits roughly across three functions.

**The first is routing.** This is the oldest function of hierarchy and the one that consumes the most time. Who needs to know what, when. A manager sits in the Monday leadership meeting and hears that the company is shifting priority from growth to retention. They go back to their team and translate: here’s what changed, here’s what it means for us, here are the three things that stay the same and the one thing that doesn’t. They sit in a cross-functional sync and notice that the infrastructure team is about to ship something that breaks an assumption the product team is making. They flag it. They write the weekly status email that rolls up eight people’s work into a paragraph their VP can skim before the Tuesday executive review.

This is information logistics. Aggregating from below, distributing from above, translating laterally. The Roman legions invented it: eight soldiers to a squad, eighty to a century, five thousand to a legion, each layer with a named commander whose job was to move information up and decisions down. The Prussian General Staff formalized it into a professional class of officers whose purpose was not to fight but to process information and coordinate across units. The American railroads turned it into org charts. McKinsey turned it into billable hours. Every management structure in history exists because human attention has limited bandwidth, and the only way to coordinate thousands of people was to build a relay chain of humans passing information to each other.

If you’ve ever been in a meeting whose sole purpose was making sure three teams had the same understanding of something decided two weeks ago, you were watching the routing function at work. It is essential. It is expensive. And as of about 2024, it is increasingly automatable.

**The second function is sensemaking.** This is subtler than routing and harder to see, because when it’s done well it’s invisible.

Raw information without interpretation is noise. A good manager doesn’t just *relay* that the company is shifting from growth to retention. They interpret what that means for their specific team. “Our roadmap doesn’t change, retention is already what we’re building.” Or: “We need to stop the migration project and pivot to churn analysis this quarter, here’s why.” Or: “This announcement is political, it won’t actually affect resource allocation, keep going.” The judgment call about what information means, not just what it says, is sensemaking.

When you lose this function, the symptoms are distinctive. Everyone has access to all the information. Nobody knows what any of it means for their specific work. You check Slack and there are forty threads about the strategy shift, each with a different interpretation, and no one with the authority and context to say which interpretation is correct. You sit in a planning meeting where six people have read the same memo and are proposing six incompatible responses, and there’s no one in the room whose job it is to resolve the ambiguity.

That’s not a communication problem. That’s a sensemaking vacuum.

**The third function is accountability and feedback.** This is the one that gets the least respect and matters the most.

Someone tells you whether your first two weeks at a new job were directionally correct. Someone notices you’re drifting before you’ve wasted a month. They catch the early signs of burnout, not from a dashboard, but from noticing that you’ve been quieter in meetings and your pull requests have gotten sloppy. With enough authority to be believed, they say: you’re doing well, keep going. With enough care to be heard: you’re off track, here’s what I’m seeing, let’s fix it.

This function is partly informational. But mostly it’s relational. It requires knowing a person, their patterns, their tendencies, their current state of mind. Trust that builds over time. The political capital to deliver hard truths. And emotional intelligence and timing that have nothing to do with information processing.

If you’ve ever had a great manager, the thing that made them great almost certainly wasn’t their status emails. It was that they saw you, your work, your growth, your struggles, and told you the truth about what they saw in a way you could hear.

Most people have had maybe two managers like that in their entire career. The function is rare and precious — and it is the one most likely to get destroyed when a company “flattens” without understanding what it’s flattening.


## The flat-org graveyard

Every flat-org experiment in modern business history made the same mistake. They treated the management layer as a single thing, “hierarchy,” “bureaucracy,” “the bosses,” and removed it all at once. Then they discovered, painfully, that the three functions are different, and that losing any one of them produces a specific kind of organizational failure.


#### Valve removed the accountability function and got Lord of the Flies.

The game studio behind Half-Life and Steam ran for over two decades on radical flatness: no management, no hierarchy, wheeled desks so employees could form teams by rolling toward interesting problems. The employee handbook was famous. Every hire, they said, should be capable of running the company.

For a long time it produced extraordinary creative output. But without anyone formally responsible for feedback, the function migrated to social status. A former employee described finding a “hidden layer of powerful management” that felt like high school: popular kids who had accumulated informal power, and dissenters who actually wanted to drive change. Other employees compared the workplace to Lord of the Flies. The flat structure was blamed for the company’s well-documented lack of diversity: without anyone accountable for pushing back on hiring bias, a company founded by two white men in an already-skewed industry became steadily less diverse while the rest of the games industry slowly improved.

The routing still happened, people talked, information flowed, teams formed around projects. The sensemaking still partially happened, senior employees informally guided direction. But with no one owning accountability and feedback, the organization’s quality control became a popularity contest. Technical brilliance without social capital got you nowhere. Social capital without technical brilliance could shape the company’s direction. That’s worse than hierarchy — at least hierarchy is visible.


#### Zappos removed the sensemaking function and got paralysis dressed up as process.

In 2014, CEO Tony Hsieh told 1,500 employees they would reorganize into self-managing circles with no managers, no titles, and no traditional org chart. Holacracy, the formal system they adopted, was supposed to distribute authority and unleash innovation.

Instead it replaced one kind of bureaucracy with another. The company’s 150 departments became 500 circles. Its 150 team leaders became 300 “lead links.” Employees spent five extra hours per week in governance meetings learning the new system. Internal satisfaction scores collapsed on 48 of 58 survey questions. The company fell off the Fortune Best Companies to Work For list for the first time in eight years. Twenty-nine percent of staff turned over in a single year.

Routing still worked, the governance system handled that, albeit clumsily. Feedback still partially existed, people had peers, and the intensity of the culture provided some signals. But sensemaking vanished. Nobody was translating the company’s evolving strategy into directional clarity for individuals. Fortune reported that survey scores cratered specifically on the question of whether management had “a clear view of where the organization is going and how to get there.” Everyone had access to all the circles and all the governance process. Nobody knew what it meant for their actual work on Monday morning.

By 2018, Zappos had quietly brought back managers while keeping the circles as decorative residue. The company survived. The model didn’t.


#### **Medium** lost the routing function and drowned in coordination cost.

The head of operations wrote publicly that Holacracy was “getting in the way of the work.” When a system designed to eliminate bureaucratic overhead creates more overhead than the bureaucracy it replaced, you’ve failed at the one thing you were trying to do. Medium abandoned Holacracy after about four years.


#### GitHub tried it and dropped it.

Tony Hsieh’s own Downtown Project, his Vegas revitalization initiative, couldn’t sustain it for more than a few months.

The pattern repeats with such consistency that it should be treated as a structural finding: **you can strip out one of the three functions and sometimes compensate. Strip out two and you’re in serious trouble. Strip out all three, which is what “go flat” means in practice, and you hit a wall somewhere between 300 and 500 people. The threshold shifts with structure and design, but the wall itself keeps showing up.**

The reason this history matters now is that the “unbossing” wave currently rolling through corporate America is about to reproduce these failures at enormous scale, unless the companies doing it understand that they’re not removing one thing. They’re removing three.


## Why this time could be different

So why am I writing this in 2026 rather than 2016? Because for the first time, the technology exists to actually replace one of the three functions, is getting usable at a second, and is advancing fast enough that we can see a path to the third.

**Routing is automatable now.** An agent can synthesize status across workstreams. It can detect when two teams are blocked on the same dependency. It can generate roll-ups from daily work artifacts. It can maintain a continuously updated picture of an organization’s state and make that picture available to everyone simultaneously. The status meeting, the alignment sync, the weekly report that exists only to shuttle information between people who could see it directly if the system were designed to let them. All of this can be done by software. Not perfectly, not in every case, but well enough that the human time spent on it can be cut by 60-80% at companies that instrument their work correctly.

**Sensemaking is partially automatable and improving fast.** An agent can take a strategic document and a team’s recent output and generate a first-pass interpretation: “Here’s what this priority shift likely means for your roadmap.” It can surface the three things you should probably focus on today based on company-wide context. It can translate between technical and business language. But it cannot yet reliably handle the hard judgment calls: sensing that a strategic shift is performative rather than real, recognizing that the CEO’s new obsession will pass in two weeks, reading the organizational politics well enough to know which initiatives have genuine backing and which are theater. Sensemaking requires a model of human intention and organizational dynamics that agents don’t yet have. They’re getting there, but they’re not there yet.

The pattern is clearer than the pace. I’d bet on sensemaking tools being broadly usable within two to three years, but I’ve watched enough automation timelines slip to hold that loosely.

**Accountability and feedback stays human.** Noticing someone is drifting. Delivering the hard truth that someone needs to hear. Catching the early signs of burnout. Building the trust that makes honest feedback receivable. These require relationship, emotional modeling, and judgment that operate on a fundamentally different substrate than information processing. An agent might flag that someone’s output declined. A human has to have the conversation about why.

Routing is ready now. Sensemaking is 18-36 months from being broadly usable. Accountability is years away, if it’s automatable at all.

Which means the right move is not “go flat.” It’s not “remove the management layer.” It’s **selective compression**: replace the functions that technology can handle, keep the humans for the functions it can’t, and be precise about the sequence. Companies that do this will be faster than companies that keep the full bundle *and* more resilient than companies that smash it.

There’s a piece of evidence from agent architecture that reinforces this. In my work on multi-agent architectures, I’ve studied how Cursor, the AI coding company that crossed $300 million ARR with fewer than 100 employees, then hit $1 billion ARR by late 2025 with roughly 150 people, structures its agent swarms for complex tasks. They tried flat coordination: agents self-organizing as equals. It failed. The agents became paralyzed by ambiguity and duplicated each other’s work. They tried three tiers: a planning layer, a coordination layer, and an execution layer. The middle coordination layer created bottlenecks. What worked was two tiers: planners and workers. No permanent middle layer.

Even agent swarms, operating purely in software with none of the social dynamics of human organizations, independently converged on compressed hierarchy. The routing function was automated. The sensemaking function was concentrated at the top. The middle, the coordination layer that exists solely to relay information, was eliminated.

That’s the same structure the most advanced human organizations are converging on. The result isn’t flat. It’s hollowed out.


## Three ways to hollow out

Three companies are currently running different versions of this experiment at meaningful scale. Each has made a different bet about how to decompose the management bundle. Comparing them tells you more than studying any one alone.


#### Kimi: Superbrains at the center

A Chinese magazine called Renwu recently embedded a reporter inside Moonshot AI, the company behind Kimi, for 100 hours. Thirty-plus employee interviews, meetings observed, full editorial independence. It’s the most detailed view inside an AI-native organization we’ve gotten.

Kimi is three years old. Roughly $18 billion valuation. Just over 300 employees, average age under 30, according to Renwu. No formal departments, no hierarchy, no titles, no OKRs, no KPIs.

Their decomposition: **agents handle routing, five co-founders handle sensemaking, and accountability is mostly left to self-selection.**

The routing piece is real. The piece describes a product manager who launches three agents before lunch: one scanning 3,000 user feedback items, one interpreting sentiment across languages, one monitoring competitors. The PM intervenes at three judgment points. By 11:30 a.m. the requirements document is done and a coding agent has generated 70% of the implementation. What used to take three people two days happens in two hours. That’s routing automation in production.

The sensemaking piece is concentrated in five co-founders, each interfacing directly with 40-50 employees. They translate strategy into direction through constant, direct communication. Yang Zhilin’s internal status message is two words: “Communicate directly.” This works at 300. But the reporter captured the strain: “Even these superbrains began to strain under the load.” Each co-founder carries a cognitive burden that would be distributed across three to five management layers in a traditional org. There is no buffer.

The accountability piece is where the model is most honest about its costs. It essentially doesn’t exist in formal terms. A former employee who returned to big tech said it directly: some mornings you walk in and don’t know what you should do. No one tells you whether you’re doing well. The company compensates with extreme hiring selectivity (they screen for what they call “generalization ability,” people who can self-direct without external validation) and with cultural intensity so high that people cry in meetings when projects fall short. More than 100 hires in the past year came through referrals, creating trust networks where informal feedback flows through personal relationships.

It produces extraordinary speed. It also produces real casualties. At least three mid-to-senior hires from major tech firms failed to land. One left the industry. Several employees described crying more at Kimi than at any previous company. The piece uses the word “weightlessness” to describe the personal experience of working there. It sounds liberating in a profile. Lived daily, for people who don’t have the specific psychological makeup the company selects for, it produces anxiety, isolation, and drift.


#### Block: Unbundled by role

Jack Dorsey and Roelof Botha published a piece on March 31 laying out Block’s approach. Same historical diagnosis: Romans, Prussians, railroads, the flat-org failures. Different structural answer.

Block’s decomposition: **a “world model” handles routing, Directly Responsible Individuals (DRIs) handle sensemaking, and player-coaches handle accountability.**

Routing: Block is remote-first. Everything produces machine-readable artifacts: decisions, code, designs, plans, progress. AI maintains a continuously updated picture of what’s being built, what’s blocked, where resources sit. That picture replaces the information the hierarchy used to carry. Not a set of individual agents that employees deploy (the Kimi approach) but a persistent, shared representation of the entire company’s state that everyone can query.

For sensemaking, Block relies on DRIs who own specific cross-cutting problems for defined periods. A DRI might own merchant churn in a specific segment for 90 days, with full authority to pull resources from multiple teams. The DRI doesn’t just execute: they interpret. They decide what the data means for the specific problem they own. They make the judgment calls about priority and direction within their domain. The time boundary prevents them from becoming permanent middle managers. The rotation builds cross-domain fluency. This is the sharpest structural innovation in the model: sensemaking isn’t concentrated in founders (Kimi) or distributed to everyone equally (Zappos). It’s assigned to the person closest to a specific problem, with explicit authority and an expiration date.

Accountability lives with player-coaches who combine building with developing people. They still write code or design interfaces, they’re practitioners, not full-time managers. But they also invest in the growth of the people around them. The world model handles alignment. The DRI structure handles priority. The player-coach handles craft and care. This is the most direct response to the failure mode that killed Zappos and threatens Kimi: it explicitly keeps a human in the feedback loop, but strips the routing and alignment overhead out of their role so they can focus on the part that’s actually irreplaceable.

Block says the transition is early and that parts of it will break. But the design maps cleanly to the automation timelines: agents do routing, DRIs do sensemaking (assisted by agents), humans do accountability. Each management function has a named owner. None of them is a traditional manager.


#### Meta: Compressed, not hollowed

Meta is the most interesting case because it’s the least ideological and the largest.

Zuckerberg’s “Year of Efficiency” removed entire management layers, offered remaining managers a choice between dramatically wider spans or conversion to individual contributor roles, and rebranded the whole thing as defragmentation. He directly oversees 25-30 senior leaders. Fifteen product divisions run through three executives. The hierarchy still exists. There are just fewer layers in it.

Meta’s decomposition: **agents assist with routing within the existing hierarchy, sensemaking stays human with fewer layers, and accountability is intensified rather than reduced.**

The key difference: Meta didn’t try to unbundle the management functions into separate mechanisms. It kept them bundled in the manager role but reduced the number of managers, gave each one a wider span, and supplemented them with AI tools. It’s compression, not decomposition.

And simultaneously, Zuckerberg intensified the accountability function. Cut the bottom 5% of performers. Raised the bar publicly. Jensen Huang runs a similar model at NVIDIA, roughly 60 direct reports, no recurring one-on-ones, but constant ad hoc communication and an expectation of extreme performance. The message is: we’re giving you fewer managers and more autonomy, but the feedback you do get is going to be sharper and the consequences for underperformance are going to be more immediate.

This is the most conservative approach and the one with the most evidence of working at scale. Meta’s stock roughly tripled from the efficiency push, and operational metrics suggest the company is shipping faster with fewer people. But it’s an optimization of the existing model, not a structural change. The management bundle is still bundled. The managers just have bigger portfolios and better tools.

The companies that actually decompose, that assign different functions to different mechanisms, matched to what technology can handle, will eventually move faster, because they’ll spend zero human attention on routing while Meta still spends some. But Meta has the advantage of not risking a catastrophic failure on any single function, because every function still has a human owner.


## It’s not span of control. It’s speed of control.

One more concept is needed to complete the picture. Everyone discussing AI-era organizations reaches for “span of control,” how many people can one leader oversee. Zuckerberg manages 30. Kimi’s founders manage 50. The question seems to be: how wide can the span get?

The better question isn’t how wide the span gets. What’s actually changing is how fast the loop closes between doing something and learning whether it was the right thing.

In a traditional org, the cycle looks like this: teams work for a week, synthesize it into reports, present in meetings, receive feedback, iterate. Information flows up through layers, decisions flow down. The time between action and feedback is measured in weeks. Sometimes months.

In an AI-native org, the cycle compresses to hours. Work produces its own record. Agents synthesize it in real time. The person with authority to evaluate sees the state of the work at any moment. Feedback is nearly instantaneous.

The coordination ceiling that kills flat orgs isn’t really about headcount. It’s about latency. When feedback takes a week, you need managers at every layer to hold context between cycles, to remember what was decided, track execution, notice drift. That’s routing. It scales linearly with the number of people and the number of cycles. At 500 people with weekly loops, you need a lot of human routers.

When the loop compresses to daily or real-time, the routing need shrinks dramatically. You don’t need someone to remember decisions if the system records them. Tracking execution becomes redundant when the work produces its own trail. Drift detection shifts to agents that flag anomalies automatically.

The coordination ceiling isn’t fixed at 500. It’s a function of feedback latency. Compress latency and the ceiling rises. That’s the actual mechanism by which AI changes organizational structure, not by replacing managers, but by compressing the time constant of the organization’s learning loop, which reduces the routing overhead that forced you to add managers in the first place.

Whether the ceiling rises from 500 to 2,000 or from 500 to 50,000 depends on how fast agent capability advances on the sensemaking and accountability functions. Routing is already there. Sensemaking is coming. Accountability is the long pole.


## What happens to the managers

I want to address this directly, because it’s the question most people reading this actually care about, and the unbossing discourse keeps skating past it with vague reassurances about “upskilling.”

If coordination and information routing consume the majority of the average manager’s time (research estimates range from 50% to 80% depending on role), and routing is automatable now, that’s the equivalent of millions of full-time roles worth of work being absorbed by software. Not next decade. This decade. These people won’t be fired en masse on a Tuesday. But the composition of their jobs is shifting under them, and most haven’t thought about it clearly.

**If you’re a manager whose time is mostly routing** — synthesizing status, relaying priorities, translating between teams, making sure everyone has the same context — you are the most exposed person in this transition. Your function is the one technology replaces first. Your path forward is to move toward the other two functions: either become a better sensemaker (the DRI path, own problems, make judgment calls, provide directional clarity in ambiguous situations) or become a better coach (the player-coach path, develop people, provide feedback, build the relational infrastructure that agents can’t).

**If you’re a manager whose time is mostly sensemaking** — interpreting strategy, making judgment calls, providing clarity when the situation is ambiguous — you have more runway, but it’s not infinite. Agents are getting usable at the simpler end of sensemaking: translating strategy documents, prioritizing task lists, flagging misalignment between stated goals and actual work. The hard end, reading organizational politics, sensing when a priority is real versus performative, knowing which rules to follow and which to bend, remains deeply human. Push toward the hard end.

**If you’re a manager whose time is mostly coaching** — developing people, providing honest feedback, maintaining team health — you are holding the single most undervalued and least automatable function in the modern organization. Every flat-org experiment destroyed this function accidentally and suffered for it. Every company that’s getting the transition right is investing more in it, not less. If this is your strength, the next five years will reward you disproportionately, but only if you shed the routing overhead and focus. A player-coach who’s also spending 40% of their time in status meetings is a player-coach operating at half capacity.

The practical move, regardless of which category you fall into: **audit your own time.** Literally. Track one week. How many hours were routing, how many were sensemaking, how many were feedback and development. Whatever the routing share is, that’s the share of your job that’s being automated. What fills it is up to you.


## What to do if you run the company

If you’re making the decisions about organizational structure rather than living inside someone else’s, the framework gives you a sequence.

**Decompose before you compress.** Before you cut a management layer, understand what each layer is actually doing. You will find that the same level does different things in different parts of your company. Your engineering managers might be 70% routing. Your sales managers might be 30% routing and 40% coaching. Compressing them uniformly, “everyone gets twice as many reports,” is how you reproduce the Zappos failure. Compress by function, not by level.

**Automate routing first.** This is the function agents handle best and the one consuming the most management time. Work that produces its own record feeding an agent-maintained picture of team and org state. Status synthesis. Anomaly detection. Dependency tracking. Every hour you free from routing is an hour that can go to sensemaking or coaching, the functions that are genuinely scarce.

**Invest more in feedback, not less.** This is the counterintuitive move that separates the companies getting this right from the ones about to reproduce the 1990s flat-org failures at massive scale. The fewer layers you have, the more deliberately you need to build feedback mechanisms. Block’s player-coach is one model. A dedicated mentorship role that persists even as reporting lines shift is another. A peer feedback system structured enough to be reliable but lightweight enough to actually get used is a third. The mechanism matters less than the principle: if you remove managers and don’t replace the accountability function, you will produce the “weightlessness” problem, talented people with access to all the information and no idea whether they’re on track. The result looks like freedom. It functions as organizational neglect.

**Create DRI-like roles for sensemaking.** The Block model of assigning cross-cutting problems to individuals with explicit authority and time boundaries is a structure that can coexist with your existing hierarchy while you transition. You don’t have to eliminate management to start concentrating sensemaking in the people closest to the problem. Identify the interpretive work that’s currently diffused across committees and alignment meetings. Give it a named owner. Give them a 90-day mandate and real authority. See what happens.

**Watch the reversion signals.** As you compress, watch for the specific symptoms of each failure mode. Senior people whose performance suddenly drops after a structural change: overfit humans whose skills were environment-dependent. Rising attrition among mid-tenure employees who aren’t failing but aren’t growing: feedback vacuum. Mushrooming Slack channels and the sense that “nobody knows what anyone else is working on”: coordination ceiling. Each symptom tells you which function you failed to replace. Diagnose by function, not by vibes.


## The bet

Every attempt to eliminate management layers wholesale has hit the same wall — because the layers were doing three things, not one.

Now, for the first time, the technology exists to replace the most time-consuming of those three functions. Routing, the aggregation, synthesis, and relay of information, can be done by agents. This doesn’t eliminate the need for management. It unbundles it. And unbundling, in every industry where it’s happened (media, financial services, telecommunications) produces the same outcome: the companies that understood the bundle outperformed both the ones that clung to it and the ones that smashed it.

The management layer is being unbundled right now, whether your company is doing it deliberately or not. According to Korn Ferry, 44% of U.S. workers say their employer cut management levels in the past year. Most did it as a cost play. A few are doing it as a structural redesign. The difference between those two approaches will compound over the next three to five years into one of the largest performance gaps in corporate history.

The companies that simply cut, that flatten without understanding the bundle, will reproduce the Valve problem (invisible hierarchies), the Zappos problem (sensemaking vacuums), or both. They’ll re-add layers within two years, call it “maturing the organization,” and lose the speed they were trying to gain.

The companies that decompose, that automate routing, concentrate sensemaking, and invest in accountability, will build something that doesn’t have a historical precedent — something more like a compressed organization where the human-to-human management layer has been reduced to its irreducible core: judgment, interpretation, and care.

We don’t have a good name for this yet. “AI-native” is too vague. “Flat” is wrong. “Unbundled” is accurate but doesn’t inspire anyone to change their calendar.

Maybe the name doesn’t matter. What matters is the sequence. Replace routing. Protect feedback. Concentrate sensemaking. In that order.

Everything else is overhead. And we’re eliminating overhead.

[![](https://substackcdn.com/image/fetch/$s_!-42m!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6eb331c2-105d-4141-9341-00e692548078_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!-42m!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F6eb331c2-105d-4141-9341-00e692548078_1024x1024.png)
