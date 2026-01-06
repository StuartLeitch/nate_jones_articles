---
title: "GRAB THE PROMPTS (3 Links!)"
author: "Nate Jones"
published: 2025-12-17
url: https://natesnewsletter.substack.com/p/grab-the-82-image-prompts-i-use-for
subtitle: "ChatGPT launched a new image generator today, and I put it through the wringer: 9 separate head-to-head tests vs. Nano Banana. Here's what I learned + 82 prompts for images!"
audience: everyone
scraped_at: 2026-01-05 19:09:52
---

I put ChatGPT’s new image model to the test.

Not once, but nine times head-to-head vs. Nano Banana Pro.

And I gotta say: ChatGPT does not measure up here.

The new ChatGPT Images model is not ready for serious business work. Not close.

I’m not saying this to be contrarian. I ran the tests. I have the side-by-side comparisons, and I’ve included them all here.

ChatGPT’s failure modes are consistent enough that we can learn from them how OpenAI is solving the image problem, and we can infer a fair bit of how that differs from Google and Nano Banana.

**Here’s what’s inside:**

- **The fundamental difference in how these models generate diagrams**—ten takeaways around how the models build images differently, and why that matters for production systems.
- **Nine side-by-side visual comparisons** across ARR revenue bridges, funnel diagnostics, Venn diagrams, opportunity solution trees, fictional maps, and image editing tasks—with my assessment of what worked and what failed.
- **82 prompts across three categories** (advertising, business artifacts, education) that I built to extract what image models actually do well. Structured interviews, not generic templates.

  - **20 Board Level Business Slide Creation Prompts**

    - *Financial:* ARR revenue bridge, P&L waterfall, unit economics dashboard, pricing tier comparison
    - *Metrics:* Funnel diagnostic, cohort retention heatmap, engagement overview, North Star tracker
    - *Strategy:* Competitive positioning map, market landscape, SWOT analysis, strategy-on-a-page
    - *Product:* Opportunity solution tree, roadmap timeline, prioritization matrix, feature comparison grid
    - *Planning:* OKR cascade, project timeline, RACI matrix, risk assessment
  - **17 Advertising Image Creation Prompts**

    - Food & Beverage
    - SaaS / Tech Products
    - Real Estate Listings
    - Financial Services
    - Healthcare & Wellness
    - Automotive
    - Travel & Hospitality
    - Fashion & Apparel
    - Consumer Electronics
    - B2B Professional Services
    - Education & EdTech
    - Non-Profit Campaigns
    - Event Promotion
    - Recruitment & Employer Branding
    - Retail & E-commerce
    - Luxury Goods
    - Local Small Business
  - **45 Education Worksheet Image Creation Prompts**

    - *Mathematics (8):* Arithmetic practice, word problems, fraction models, geometry exploration, multiplication tables, number lines, place value, fact fluency
    - *Reading & Language Arts (8):* Phonics, comprehension organizers, vocabulary builders, creative writing, sight words, story sequencing, grammar, spelling patterns
    - *Science (6):* Labeled diagrams, experiment logs, classification sorts, nature journals, scientific method templates, life cycles
    - *Social Studies (5):* Map skills, timelines, civics organizers, geography labeling, historical comparisons
    - *Early Childhood (6):* Letter tracing, counting, shapes, patterns, colors, fine motor
    - *Specialized Formats (12):* Word searches, crosswords, bingo, cut-and-paste, foldables, matching, fill-in-blank, multiple choice, true/false, sequencing cards, Venn diagrams, KWL charts
- **A quick reference guide** so you know which prompts to grab for board prep vs. quarterly planning vs. launch readiness.

Why so many prompts? Why so many categories? Well, honestly my response to a disappointing launch is to build. So as soon as I saw ChatGPT’s image launch was disappointing, my instinct was to turn around and build prompts for Nano Banana Pro. I wanted to show range, so I thought going across education, advertising, and board slides would be a nice roundup.

The other reason to throw these all in here is simple: I write a lot, and I think sometimes people lose track of the stuff I write. Having a really fat prompt collection like this makes it easy for folks to save and come back to these collections because it’s all in one handy place.

With that, let’s dig in, get those prompts going, and see the side-by-side comparison!


# GRAB THE PROMPTS (3 Links!)


## [20 Board Deck Prompts](https://www.notion.so/product-templates/Nano-Banana-Straight-to-Slides-Prompts-2cc5a2ccb52680499b5ac6269a7070bd?source=copy_link)


## [17 Advertising Image Creator Prompts](https://www.notion.so/product-templates/Nano-Banana-Advertising-Prompts-2cc5a2ccb52680949c43c51372e86ecf?source=copy_link)


## [45 Educational Prompts](https://www.notion.so/product-templates/Nano-Banana-Educational-Worksheet-Prompt-Collection-2cc5a2ccb526803fbdb0e510670f576a?source=copy_link)

These prompts exist because I got tired of watching people struggle with generic image generation while missing the actual capability gap.

I ran the same nine business scenarios through both ChatGPT 5.2’s new image model and the only model that consistently delivers production-ready output.

The results weren’t close. ChatGPT got stuck in 20-minute self-edit loops. It cut off titles mid-word. It drew revenue gains pointing downward.

These 82 prompts are structured interviews that extract exactly what image models need to produce polished artifacts—without you becoming a prompt engineer. They’re organized by use case (advertising, business artifacts, education) because that’s how real work actually arrives.

---


# ChatGPT Tries to Catch Nano Banana But No Dice


## The Code Red Continues

OpenAI has been in response mode since Google launched Gemini 3. ChatGPT 5.2 was their initial answer. Now they’re continuing with a new image generation release that’s clearly aimed at closing the gap.

The [press release](https://openai.com/index/new-chatgpt-images-is-here/) really wants you and me to believe this thing is the best thing since sliced bread: “precise edits that preserve what matters,” “4x faster” generation, “results that match your intent.” They even have a quote from the Head of AI Research at Wix calling it “one of the flagship image generation models today.”

They have a nice edit animation showing the journey of a holiday card too.

[![](https://substackcdn.com/image/fetch/$s_!KX-_!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7e292333-487f-49ea-8e0d-6dd714848d71_1010x620.png)](https://substackcdn.com/image/fetch/$s_!KX-_!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7e292333-487f-49ea-8e0d-6dd714848d71_1010x620.png)

It all looks great on the surface, but I put those claims to the test.


## First, What I Learned About How These Models Actually Work

1. **They generate diagrams completely differently.** Nano Banana Pro appears to use reasoning baked into the image generation process itself—if it fails, you see a badly drawn diagram. ChatGPT writes actual Python code to construct visualizations, then photographs or renders the result. When ChatGPT fails, you see code artifacts: viewport cutoffs, misaligned elements, content that was built but couldn’t be captured.
2. **ChatGPT doesn’t understand the meaning of what it’s building.** An ARR bridge isn’t just bars—it’s a story about how revenue changed. The direction encodes whether money came in or went out. ChatGPT drew revenue gains as downward-pointing bars. The model can construct the visual elements but doesn’t grasp the semantic relationships that make business artifacts actually communicate something.
3. **Truncation is a systematic failure, not a one-off.** Across multiple tests, ChatGPT produced content that got cut off: “RR Bridge” instead of “ARR Bridge,” a Venn diagram title ending mid-word, opportunity trees with visible “...” where text should continue. The model codes something wider than its viewport can capture, then delivers a partial screenshot. This isn’t recoverable—the missing content is gone.
4. **Reference image fidelity diverges dramatically.** When given a blurry photo and asked to place that person in a new scene, Nano Banana Pro preserved the likeness and even added contextually appropriate costume details. ChatGPT produced a completely different person. If you’re generating images that include yourself or team members, this matters.
5. **Mathematical reasoning survives in one model but not the other.** The blueberry edit test required recalculating pie chart proportions after adding a new ingredient. Nano Banana Pro got the math right and even tinted the drink purple. ChatGPT attempted the calculation but couldn’t render segments that matched the stated percentages. There’s a logic layer that doesn’t survive the code-to-image pipeline.
6. **Domain knowledge shows up in unexpected places.** The P.G. Wodehouse map test required understanding which characters are associated with which fictional locations—knowledge that exists in text but has rarely been visualized. Nano Banana Pro correctly placed Lord Emsworth at Blandings Castle and Bertie Wooster at Brinkley Court. ChatGPT produced a blurry photograph of a generic map concept.
7. **Self-correction loops don’t fix architectural problems.** OpenAI added what appears to be an edit-and-retry mechanism. During the alphabet test, ChatGPT spent 20 minutes producing a dozen intermediate images. The final result had the same class of errors as the first attempt. You can’t iterate your way out of a viewport limitation.
8. **Failure modes differ in recoverability.** Nano Banana Pro’s failures—like duplicating a grid cell—are fixable with a quick follow-up prompt. ChatGPT’s failures—wrong bar directions, truncated titles, missing sections—require starting completely over. One model gives you a draft to refine. The other gives you a concept to rebuild.
9. **Speed claims didn’t match my experience.** Despite “4x faster” marketing, Nano Banana Pro produced usable output faster in practice. Less visible reasoning, less drama, less waiting. The code-generate-photograph pipeline has overhead that native image generation with embedded reasoning doesn’t.
10. **There’s a threshold where image generation becomes useful for real slides.** Not “interesting demo” useful—actually-put-it-in-a-board-deck useful. Nano Banana Pro has crossed it for business artifacts. ChatGPT 5.2 hasn’t. Neither has any other model I’ve tested.

---


## Nine Head-to-Head Tests

I designed these tests around scenarios with actual business relevance. Not “draw me a cat” but “generate the kind of slide I’d put in a board deck.” All prompts were identical for each model.


### Test 1: Celebrity Image Edit + Technical Diagram

I gave both models a blurry reference image of Keira Knightley (did not mention her name in the prompt to avoid hitting celebrity guardrails) and asked them to place her in a teaching scenario, explaining how LLMs work on a whiteboard behind her.

[![](https://substackcdn.com/image/fetch/$s_!kg1W!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5f3cb217-76a5-4855-a1ba-814b9f07bd5f_1732x950.jpeg)](https://substackcdn.com/image/fetch/$s_!kg1W!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F5f3cb217-76a5-4855-a1ba-814b9f07bd5f_1732x950.jpeg)

**Nano Banana Pro:** Correctly identified Keira from a single blurry image. Put her in contextually appropriate attire. Generated a detailed technical diagram showing tokenization, transformer architecture, word embeddings, and the probability distribution output. The diagram is technically accurate and readable.

**ChatGPT 5.2:** Keira’s likeness didn’t transfer. I got uncanny valley Keira. The LLM diagram exists but is significantly simpler—high-level boxes without the architectural detail that would actually explain how the system works. I do like the colors though!

This matters because if you’re using image generation to create training materials or presentations that include yourself or team members, you need the likeness to carry through edits.


### Test 2: Child’s Alphabet (A-Z Grid)

Twenty-six letters, twenty-six animals, arranged in a grid. Both models failed, but the failure modes differed. I pushed both models multiple times to edit and refine these and this is the best they could do.

[![](https://substackcdn.com/image/fetch/$s_!wnj7!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb24ad506-ab10-4863-80af-e8a1480b554d_1720x870.png)](https://substackcdn.com/image/fetch/$s_!wnj7!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb24ad506-ab10-4863-80af-e8a1480b554d_1720x870.png)

**Nano Banana Pro:** Needed some coaching but eventually produced a readable grid. The main issue: it duplicated F-G entries (Fox/Goat appearing twice) because it wanted complete rows. Individually, each cell was correct (note the Fox for X follows the usual child convention of picking a different animal with an X in the name).

**ChatGPT 5.2:** After multiple edits and a prolonged correction loop, the final output had “Zebra, Zebra, W” in the bottom row, with letters misaligned and an X appearing at the very end for no clear reason.

Neither is perfect. But one is fixable with a quick edit. The other would require starting over, and even then I don’t think ChatGPT 5.2 is likely to get it.


### Test 3: Funnel Diagnostic Dashboard

This is the kind of slide that shows up in every weekly business review. Conversion rates by stage, week-over-week deltas, sparkline trends, a diagnosis panel ranking the biggest leaks, and an experiments table with expected lift and confidence intervals.

[![](https://substackcdn.com/image/fetch/$s_!yESV!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F680ef124-499f-4c23-8fe9-3227362f9e08_1734x882.png)](https://substackcdn.com/image/fetch/$s_!yESV!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F680ef124-499f-4c23-8fe9-3227362f9e08_1734x882.png)

**Nano Banana Pro:** Generated a complete, readable slide. The conversion percentages are internally consistent. The sparkline graphs show believable trends across dozens of data points. The diagnosis panel correctly identifies the largest drop-off and proposes experiments with prioritization. I could put this in a deck.

**ChatGPT 5.2:** Similar structure, but the detail level drops significantly. No sparkline micro-trends. The visualization doesn’t have the precision that makes these artifacts actually useful—you’d look at it and say “nice concept” but not trust the specific numbers or use it in a real meeting.


### Test 4: Fictional Map (P.G. Wodehouse’s England)

I chose this because the corpus is well-known but rarely mapped. Unlike Lord of the Rings, there’s no canonical map in the training data to copy. Essentially this tests the models ability to reliably generalize visually from complex textual data recorded in the training weights.

[![](https://substackcdn.com/image/fetch/$s_!tQP-!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F48336332-23a8-471b-a1e1-ddeb119140b6_1696x894.png)](https://substackcdn.com/image/fetch/$s_!tQP-!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F48336332-23a8-471b-a1e1-ddeb119140b6_1696x894.png)

**Nano Banana Pro:** Generated a proper illustrated map with location names actually from the novels: Blandings Castle associated with Lord Emsworth, Brinkley Court with Bertie Wooster and Aunt Dahlia. The model understood the character-location relationships within the fictional universe.

**ChatGPT 5.2:** Tried to create a photograph of a paper map. The result is so blurry and small that even zoomed in, you can’t read the place names. It’s a nice visual concept of what a map could be. It is not a usable map. It tried a different approach (self-correction again) and that led to a PDF with a crude outline a and a bunch of text from the novels. Again, not usable. It also took a LONG time.


### Test 5: Car Rental Advertisement

Both models performed reasonably well here. Nano Banana Pro produced better visual layout—four trust badges aligned cleanly across the bottom, car centered properly. ChatGPT’s version had a minor issue with the “safe pickup and drop-off” badge placement but was generally serviceable.

[![](https://substackcdn.com/image/fetch/$s_!qrki!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8fa4b333-d5fb-4030-8251-9599b373fa2d_1518x910.jpeg)](https://substackcdn.com/image/fetch/$s_!qrki!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F8fa4b333-d5fb-4030-8251-9599b373fa2d_1518x910.jpeg)

This is one area where the capability gap is narrower, and I think I’d be ok trying advertising prompts in ChatGPT as an alternate to Nano Banana Pro.


### Test 6: ARR Revenue Bridge

This is where the architectural difference becomes impossible to ignore.

An ARR bridge is a defined chart type: Starting ARR → New ARR (green, pointing up) → Expansion ARR (green, pointing up) → Contraction (red, pointing down) → Churn (red, pointing down) → Ending ARR. It’s a waterfall. The direction of the bars encodes whether money came in or went out. It’s a very well-known chart type and should be in the model training data.

[![](https://substackcdn.com/image/fetch/$s_!qVgZ!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff6d25456-eb92-4105-a686-1ed228fe4e0c_1532x880.png)](https://substackcdn.com/image/fetch/$s_!qVgZ!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff6d25456-eb92-4105-a686-1ed228fe4e0c_1532x880.png)

**Nano Banana Pro:** Correct waterfall chart. Green bars go up for additions. Red bars go down for subtractions. The visual hierarchy matches the mathematical reality.

**ChatGPT 5.2:** The title got cut off (”RR Bridge” instead of “ARR Bridge”). The bars representing revenue gains (+$380k, +$210k) visually appear to be declining. The model placed upward revenue movements as downward-pointing visual elements.

This is not a minor error. If you put this slide in a board deck, you’d be telling a story that contradicts your actual numbers. The chart would be actively misleading.

The notes section also got truncated. That’s not recoverable from the image.


### Test 7: Venn Diagram (Taylor Swift × Product Managers × Army Corps of Engineers)

I deliberately chose an absurd prompt to test creative reasoning: find funny overlaps between three unrelated domains. This tests both reasoning and visual creativity.

[![](https://substackcdn.com/image/fetch/$s_!yMke!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943c5e9e-7913-463a-974e-641b82ca0831_1558x896.png)](https://substackcdn.com/image/fetch/$s_!yMke!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943c5e9e-7913-463a-974e-641b82ca0831_1558x896.png)

**Nano Banana Pro:** Generated a titled, color-coded Venn diagram with readable text in each intersection. The overlaps are genuinely funny—”Coordinating massive, high-stakes operations” in the center, “Managing leaks” for Taylor Swift + Army Corps. It is a bit wordy, but the model clearly understood the assignment.

**ChatGPT 5.2:** The title was cut off mid-word (”...nn Diagram”). The text overlaps itself. There’s no visual polish. The content exists somewhere in there, but you couldn’t use this.


### Test 8: Opportunity Solution Tree

Teresa Torres style: Outcome flows to Opportunities, which flow to Solutions, which flow to Experiments. This is standard product management visual grammar.

[![](https://substackcdn.com/image/fetch/$s_!Kt1z!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2ed4d86a-9ffe-4d3d-98e2-f9ae4575ac44_1730x902.png)](https://substackcdn.com/image/fetch/$s_!Kt1z!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F2ed4d86a-9ffe-4d3d-98e2-f9ae4575ac44_1730x902.png)

**Nano Banana Pro:** Complete tree with Impact scores, Confidence intervals, PM owners assigned, and a “This Cycle Focus” summary panel. The text is consistently styled throughout. A legend at the bottom explains the notation. This is directly usable in a product review.

**ChatGPT 5.2:** Similar structural attempt, but elements are cut off with visible “...” truncation. The model coded something that was wider than its viewport and then photographed the partial result.


### Test 9: Image Edit (Add 20% Blueberries to Juice Composition)

I gave both models an existing pie chart showing juice blend composition and asked them to add 20% blueberries while keeping everything else proportionally correct.

[![](https://substackcdn.com/image/fetch/$s_!Hn6S!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbba7ee14-550e-472d-bed0-a18e3c035d18_1740x910.jpeg)](https://substackcdn.com/image/fetch/$s_!Hn6S!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fbba7ee14-550e-472d-bed0-a18e3c035d18_1740x910.jpeg)

**Nano Banana Pro:** Correctly recalculated the percentages. Orange + Lemon + Grapefruit now total 80%. The visual pie slices match the updated proportions. The drink in the image has a slight purple tinge reflecting the blueberry addition. Attention to detail.

**ChatGPT 5.2:** The math was attempted but the pie chart rendering failed—segments didn’t match stated percentages, elements were misaligned. You can’t clearly separate the blueberries from the grapefruit. The drink remained unchanged despite the composition edit.


## What This Means for Your Work

I’m not going to tell you Nano Banana Pro is perfect. You saw issues in my tests—the duplicated alphabet cells, the need for coaching on complex prompts. No image model today is reliable enough to trust blindly.

But there’s a threshold where a model becomes actually useful for business work. Where you can generate a slide that goes into a real deck without embarrassment. Where the output is a starting point you can refine rather than a concept you have to rebuild from scratch.

Nano Banana Pro has crossed that threshold for business artifacts. ChatGPT 5.2—despite the ‘Code Red’ effort here—has not.

I don’t care what the benchmarks say. I don’t care what the press releases claim. I ran the tests with prompts that matter for how I actually work.


## The Prompt Library

Because this capability gap exists, I built a library of prompts specifically designed to extract what Nano Banana Pro actually does well. These aren’t generic templates. They’re structured interviews that gather exactly what the model needs to produce polished output. I linked them above, but just in case you missed them I will link them here as well.


### [Advertising (17 prompts)](https://www.notion.so/product-templates/Nano-Banana-Advertising-Prompts-2cc5a2ccb52680949c43c51372e86ecf?source=copy_link)

Industry-specific ad generators. Each one interviews you on product details, target audience, visual direction, and technical specs—then outputs a creative brief ready for execution.

The categories:

- Food & Beverage Product Launch—packaging shots, ingredient callouts, appetite appeal styling
- Tech Product / SaaS App—UI mockups in context, feature visualization, device framing
- Real Estate / Property Listing—hero shots, floor plan integration, lifestyle staging
- Financial Services / Fintech—trust signals, data visualization, security imagery
- Local Small Business—authentic neighborhood feel, owner portraiture, storefront presence

Each prompt covers product differentiators, audience psychographics, model demographics, color palette, placement specs, and required text/logo elements.


### [Business Artifacts (20 prompts)](https://www.notion.so/product-templates/Nano-Banana-Straight-to-Slides-Prompts-2cc5a2ccb52680499b5ac6269a7070bd?source=copy_link)

Executive-ready slides as single 16:9 images. These are the formats that actually appear in real operating cadences—not generic charts, but the specific artifacts people use.

Templates include:

- ARR Revenue Bridge—waterfall showing Starting ARR → New → Expansion → Contraction → Churn → Ending ARR
- Funnel Diagnostic Dashboard—conversion rates by stage, sparkline trends, leak hypotheses, experiment prioritization
- OKR Cascade Diagram—company objectives flowing to team OKRs with alignment lines and progress indicators
- Cohort Retention Heatmap—signup cohorts on Y-axis, time periods on X-axis, color-coded retention rates
- Competitive Positioning Map—2×2 matrix with you vs. competitors plotted on strategic dimensions
- Opportunity Solution Tree—Teresa Torres style: outcome → opportunities → solutions → experiments

**Quick reference by meeting type:**

Meeting Type Artifacts to Grab Board Prep ARR Bridge, Cohort Retention, Competitive Positioning Quarterly Planning OKR Cascade, Opportunity Solution Tree Weekly Business Review Funnel Diagnostic, Experiment Tracker Launch Readiness Go-to-Market Timeline, Risk Matrix


### [Education (45 prompts)](https://www.notion.so/product-templates/Nano-Banana-Educational-Worksheet-Prompt-Collection-2cc5a2ccb526803fbdb0e510670f576a?source=copy_link)

Worksheet and activity generators across 12 subject areas. Built for teachers, homeschool parents, and tutors who need printable materials fast.

Categories by subject:

- **Mathematics**—arithmetic practice sheets, word problem generators, fraction visual models, geometry exploration templates
- **Reading & Language Arts**—phonics practice, reading comprehension graphic organizers, vocabulary builders with context clues, creative writing prompt cards
- **Science**—labeled diagram generators, experiment recording sheets, classification sorting activities, nature observation journal pages
- **Early Childhood**—letter tracing, counting with one-to-one correspondence visuals, shape recognition, pattern completion sequences
- **Specialized Formats**—word searches, crossword puzzles, bingo cards, cut-and-paste sorting activities, foldable templates


## How to Use These

1. Find your category
2. Paste the prompt
3. Answer the interview questions
4. Receive your output

No prompt engineering required. The structure does the work.


## The Bottom Line

Do not listen to the benchmarks. Do your own tests.

For now, Nano Banana Pro remains the only image model I would trust for serious business work. If you’re evaluating AI image generation for your organization, run your actual use cases through both systems. Don’t trust marketing claims—trust your own eyes.

[![](https://substackcdn.com/image/fetch/$s_!cjVr!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F897af729-e62c-49b1-9913-09a77f6727f6_1024x1024.jpeg)](https://substackcdn.com/image/fetch/$s_!cjVr!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F897af729-e62c-49b1-9913-09a77f6727f6_1024x1024.jpeg)
