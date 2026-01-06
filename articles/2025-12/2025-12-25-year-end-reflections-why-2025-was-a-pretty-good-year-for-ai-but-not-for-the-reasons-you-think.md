---
title: "Year-end reflections: Why 2025 was a pretty good year for AI (But not for the reasons you think)"
author: "Nate Jones"
published: 2025-12-25
url: https://natesnewsletter.substack.com/p/year-end-reflections-why-2025-was
subtitle: "Watch now | All things considered, 2025 was a pretty amazing year for AI. What worked, what didn't, and what surprised me the most--in a good way (I promise this isn't corny!)"
audience: everyone
scraped_at: 2026-01-05 19:09:26
---

2025 didn’t deliver the science fiction version of AI that gets clicks—no robot butlers, no AGI breakthrough press conferences, no singular moment where everything shifted. The discourse was often exhausting. GPT-5 disappointed a lot of people. “Agents” became a word you couldn’t escape, attached to demos that broke the moment you asked a follow-up question.

And yet when I look back at what I actually watched people build this year—not the announcements, not the hype, but the work that shipped and held up under real use—I find myself more optimistic than I expected to be.

Yesterday I wrote about frameworks and audits, the structural stuff you can use to evaluate where you stand heading into next year. This is the companion to that piece. I want to talk about four things that genuinely shifted how I think—not predictions about where AI is going, but changes in what I pay attention to and why.


## **The Line Between “Technical” and “Non-Technical” Stopped Making Sense**

I spent years carrying around this mental model where there are technical people and non-technical people, and they operate in different worlds with different tools. The technical people build things; the non-technical people use things. The gap felt natural, almost permanent, like it was just a feature of how knowledge work gets organized.

2025 broke that model for me.

What broke it wasn’t a single moment—it was watching, again and again, people who would never have called themselves technical absolutely outrun teams of engineers. Not because they suddenly learned to code in some traditional sense, but because the definition of what “technical” means shifted underneath all of us while we were busy arguing about which model was best.

Here’s what I think is actually true now: everyone picks up the degree of technical skill they need to solve the problems they’re interested in. That’s always been true in some sense, but the threshold for what counts as “technical skill” just dropped through the floor. When an LLM can use code as a tool—when plain English becomes computer control—the barrier isn’t syntax anymore. It’s not knowing the right function names or remembering how loops work. The barrier is something else entirely: curiosity about the problem, willingness to iterate, comfort with ambiguity.

I have a daily coding review that runs at 6am now, catching things I missed and leaving notes in a file I check with coffee. A year ago, setting that up would have required me to either write the script myself or ask someone to write it for me. Now I just described what I wanted, adjusted it when it wasn’t quite right, and adjusted it again until it worked. That’s not “becoming technical” in any traditional sense—it’s the category itself dissolving.

I watched individuals out-execute entire development teams this year, and it wasn’t because they were secretly engineers all along. It was because they treated engineering as a workflow they could design rather than a priesthood they needed permission to join. They didn’t worship at the altar of any particular model. They were perfectly comfortable building low-tech things—templates, validators, retries—alongside high-tech things. They iterated aggressively and, crucially, they didn’t confuse “agentic” with “good.”

The market noticed faster than I expected. I saw quicker selection for people with strong creative problem-solving instincts than I would have predicted—not the dramatic headline stuff about mass layoffs, since there’s still not much evidence that AI is driving overall job declines whatever the newspapers say. But there’s been a lot of signal around the degree to which working well with AI is a creative, almost liberal-arts endeavor. Technical people who wanted to express their creative side finally could. Creative people who never felt they could be technical found out they were wrong about themselves.

I think one of the real opportunities heading into next year is for people who want to grow at the edges of their domain expertise. The world is genuinely more open than it was twelve months ago. You can stretch in directions that were blocked before, and the people who lean into that are going to surprise themselves.

---


## **Prompting Matters—But Measurement Is What Makes It Scale**

This one surprised me with how much it mattered.

I spent a lot of this year writing about prompting, and I stand by all of it—prompting well is a genuine skill, and it makes a real difference in the quality of what you get out of these models. But somewhere around mid-year, I started noticing that the teams getting the best results weren’t just the ones with the cleverest prompts. They were the ones who had figured out how to measure whether the output was actually good.

Here’s why that matters so much: when you can clearly define what “good” looks like—and check for it automatically—you can put an agent in a loop and let it iterate until it gets there. The agent doesn’t get tired. It doesn’t get defensive about its work. It doesn’t need encouragement. You tell it “this didn’t work because X, fix X,” and it tries again. And again. As long as you’re measuring the right thing, it will keep hammering until it succeeds or hits a genuine wall.

It’s like hooking a jet engine to an airplane. The speed of iteration becomes almost absurd.

Prompting gets you a good first attempt. Measurement is what lets you turn that attempt into something reliable at scale. The teams that got serious about both started pulling away from the teams that were still treating prompting as the whole game.

The insight for me was that I’d been underweighting half the equation. Prompting is how you communicate what you want. Measurement is how you know whether you got it. You need both, and the second one was the piece most people—including me—weren’t thinking about rigorously enough.

---


## **I think we’re framing the AI slop problem incorrectly**

Yes, the internet is drowning in AI slop. You know what it looks like. The generic blog posts. The hallucinated confidence and definiteness. The uncanny valley of almost-helpful content that leaves you more frustrated than if you’d gotten nothing at all.

I’ve spent a fair number of hours keeping an eye on that tide of slop and I’ve been wondering what the internet and communications look like with so much AI-generated content around. Have we traded quality for volume in such a way that there is no going back?

Then I started thinking about the printing press.

Universal literacy was one of humanity’s great achievements. But here’s the thing: most of what humans write isn’t the Count of Monte Cristo or the Lord of the Rings. I know I can’t write a work like that! Most of it isn’t even close. The printing press and universal education created an explosion of human output, and most of that output was—by definition—average. Mediocre memos. Forgettable letters. Reports nobody wanted to read. What we call in the archeology trade *ostraca*–scribbling on potsherds. We just didn’t have to confront it at scale because distribution was expensive and slow, and because most of our work was scribblings that disappeared within a few years (don’t get me started on the ephemerality of the internet).

AI amplifies this phenomenon. It turns out that when you give everyone a tool that produces written output at near-zero cost, you get a lot of average written output. This shouldn’t surprise us. It’s the same pattern we saw with every democratization of communication tools. The slop isn’t new—it’s just amplified.

What gives me hope is that the slop isn’t inevitable, and we humans have a pretty reliable history of finding great works (like Shakespeare) out of the sea of slop we ourselves have written. Good stuff rises to the top.

When you build actual systems—when there’s discipline around what gets generated and how it gets checked before it goes out—you can produce work that’s dramatically better than what most humans produce unassisted. I’ve seen marketing copy that people actually click on, emails that get responses, ad creative that outperforms what teams were producing manually. The difference isn’t the model; it’s everything around the model. Retrieval to ground the claims. Validation to catch the errors. Human checkpoints for edge cases. Taste applied at some point in the process.

Is the content information-dense? Is it something you can come back to? Does it respect your time? Those are the right questions, and AI can help you answer them well—if you build the systems to make it happen rather than just connecting a model to a publish button and hoping for the best.

I don’t want to live in a world of slop. But I’ve stopped thinking slop is the inevitable future. The builders, advertisers, and marketers who figure out how to produce quality at scale are going to eat the lunch of the ones who just shipped volume. Selection pressure is real, and I think humans are hungry for real stories and real dense content.

---


## **The Conversation Is Starting to Shift from Cost Cutting to Quality Lift**

This one matters most for how I think about the year ahead—but I want to be careful not to overstate it. This shift is emerging, not universal. Your mileage may vary. What I can say is that I’m seeing it happen, and I think the direction is clear.

Early 2025 was dominated by headcount conversations. “How many people can we replace?” I heard this question in every meeting with executives, and it was usually the first question they asked. AI as a cost-cutting tool. The pitch deck slide that showed current team size, projected team size with AI, and the delta framed as savings.

By the third quarter, the more sophisticated operators I talked to were starting to ask different questions.

Not “how do we do the same thing cheaper?” but “how do we do something we couldn’t do before?” How do we deliver best-customer quality to everyone, at scale, at a price point that works? How do we make unit economics viable for segments we couldn’t serve profitably before? How do we expand what we offer instead of just shrinking what it costs?

The reason I’m seeing this shift is that leaders are starting to see the value. They’re watching the early quality-lift experiments outperform the cost-cutting experiments. They’re realizing that cost cutting is finite—you cut once, maybe twice, and then you’re done, and if you cut too far you’ve just made yourself worse at a lower price point.

Quality lift compounds. New capabilities create new markets. New offerings create new customer relationships. Previously unprofitable segments become profitable. The ceiling is much, much higher.

There will still be plenty of people with what I’ve started thinking of as the brutalist mindset—dump AI in, cut costs, move on. I’m not claiming that’s disappeared. But I increasingly see leaders recognizing something important: the firms that win are the ones that treat their people’s attention as a precious asset. They design AI systems around humans in ways that let people put their expertise to work where it matters most, rather than designing systems that try to remove humans from the loop entirely. This is practical, since we need humans in these systems.

That’s a more hopeful vision than “replace everyone with bots.” And I think it’s more accurate to where this is heading, because the pure automation approach keeps running into the same wall: the last 20% of any real workflow is where all the judgment lives, and judgment is exactly what the models aren’t reliable at yet.

*Note: I’m not saying we won’t see job changes and job losses with the AI revolution. With a disruption this large, those stories are out there already. My note is more around the idea that many leaders are starting to see the huge upside of giving their teams “ironman suits” that they can use to multiply their impact. I think that’s hopeful and worth noting.*

---


## **WHAT THIS YEAR TAUGHT ME**

In January, the conversation was all about model releases and benchmarks—and reasonably so, since that’s where the action had been. Every few weeks brought a new capability jump, a new context window, a new reasoning breakthrough.

By summer, I started noticing something different. The model improvements kept coming, but they weren’t the thing that separated teams who shipped from teams who didn’t. The interesting gaps were showing up elsewhere—in what builders actually did with the models, which tools people kept using after the novelty wore off, how they handled the messy space between demo and production.

The technical/non-technical line dissolving. Measurement being the underappreciated complement to prompting—not a replacement, but the missing piece that makes prompting scale. Average work being average regardless of who produces it—but good systems making dramatic improvement possible. Quality lift starting to be noticed by leaders as a greater value driver than cost cutting. None of these showed up in benchmark announcements or model release notes. They emerged from watching what actually worked when people tried to build things that mattered.

That’s what I’ll be paying attention to next year. Not because the model race stopped mattering, but because it stopped being the bottleneck for most of the work I care about.

What shifted for you?

[![](https://substackcdn.com/image/fetch/$s_!NeeQ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F666de0ae-79d3-46be-be1a-ef561141cae8_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!NeeQ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F666de0ae-79d3-46be-be1a-ef561141cae8_1024x1024.png)
