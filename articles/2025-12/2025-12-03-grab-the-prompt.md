---
title: "Grab the prompt"
author: "Nate Jones"
published: 2025-12-03
url: https://natesnewsletter.substack.com/p/no-one-wrote-a-pro-grade-control
audience: everyone
scraped_at: 2026-01-05 19:10:40
---

*I’ve been chasing the same frustration for months with image generation apps. Even with Nano Banana Pro I could not get images to reproduce exactly how I wanted them–got excellent quality, but the control felt soft, like I was missing power steering.*

*My goal is to move you past vibes-based prompting for images so you get exactly what you want, and you have fine-grained control to change and adjust without messing up the rest of the design.*

*Because we’ve all been there.*

*You describe exactly what you want to an image generator. You get back something beautiful—but wrong. The product label is in the wrong spot. The lighting is flat when you asked for dramatic. The UI has four screens when you specified three.*

*You regenerate. Now the lighting is right but the composition changed completely. You weren’t trying to roll the dice on everything. You just wanted to fix the lighting.*

*This is the tax we pay for “vibes-based” prompting. You type something evocative, the model interprets it however it wants, and you hope for the best. Sometimes magic. Usually frustration. And zero reproducibility.*

*After Nano Banana Pro came out, I decided we had enough power in the image generation engine and we deserved power steering—but not one was teaching it properly.*

*People were marketing JSON on hype as a magic bullet for prompting. They weren’t describing where it does and doesn’t work, why it’s effective for images in particular (ironically), and most of all no one was talking about how you get to a JSON spec if you are NOT a coder.*

*JSON isn’t complicated in theory. It’s just giving the model structured specifications instead of prose descriptions. And while it sounds like something only developers would care about, the unlock is that you don’t have to write JSON yourself.*

*I built a translator prompt that does it for you. As far as I know it’s the only one out there.*

*You describe what you want in plain English (marketing image, UI/UX, or diagrams/infographics). The AI asks you questions to nudge you to get your intent clear, and then converts your description into a machine-readable spec. You pass that to the image model. And suddenly you have control—real control—over what gets rendered and what stays fixed when you iterate.*

*Here’s what’s inside:*

- ***Why vibes fail** — The fundamental mismatch between how we describe images and how precision-focused models like Nano Banana Pro actually work*
- ***Three schema types that cover most professional use cases:***

  - ***Product photography** — Marketing images where the product has to look exactly right: specific lighting, specific label placement, specific props. These are the images that sell things, and “close enough” doesn’t cut it.*
  - ***UI mockups** — App screens and dashboards where you need particular colors, particular components, particular layouts. The kind of work where changing your brand’s primary color shouldn’t mean rebuilding every screen from scratch.*
  - ***Data infographics** — Charts, diagrams, and posters where the numbers actually have to be accurate. If your graphic says the win-loss record is 567-197, it needs to say exactly that—not whatever the model hallucinated.*
- ***The handle concept** — How structured specs let you change one thing without regenerating everything else (this is the real unlock)*
- ***Concrete examples** — A beverage can product shot, an alien control panel UI, a SaaS dashboard, and a sports statistics poster—walked through field by field*
- ***The translator prompt** — The full system prompt that converts your natural-language briefs into render-ready JSON, so you never have to learn the syntax*
- ***A practical skill ladder** — How to build the one skill that actually matters here: reading structured data well enough to spot errors and make small edits, even if you couldn’t write it from scratch*

*The goal isn’t to turn you into a developer. It’s to give you a tool that makes image generation reproducible, iterable, and controllable—without changing how you think or work.*

*Below is the full breakdown: what JSON actually is, when it’s the right tool (and when it isn’t), and how to start using it today.*


# **[Grab the prompt](https://www.notion.so/product-templates/JSON-Prompt-Translator-A-Unified-Schema-for-UI-Diagrams-and-Marketing-Images-2bd5a2ccb5268054824cda1f5d7c66cf?source=copy_link)**

This prompting guide is more technical than what I usually share—but it’s worth the extra depth because the framework is immediately usable.

The core value is completeness. When you feed a brief into the translator, it doesn’t just give you a better prompt—it produces a full structured spec that captures everything: screens, components, relationships, constraints, brand rules. Nothing left to interpretation, nothing the AI has to guess at.

And you don’t have to write JSON yourself. The system asks clarifying questions, fills in required fields, and validates the output. You describe what you want in plain language; it handles the structure.

What makes this work as a framework: once your intent lives in structured JSON, you can swap rendering models, generate variations, or pipe the spec into different tools without losing the underlying architecture. Structure stays locked; styling stays flexible. It’s an operating system for prompt workflows rather than a one-shot approach.

**Turning Nano Banana Pro into a Tool, Not a Toy: A Practical Guide to JSON Prompting**

I want to let you in on something I’ve discovered. No one seems to be teaching this, and I think that’s a mistake—because it’s been a genuine unlock for getting reliable, precise results from Nano Banana Pro.

The technique is JSON prompting: giving the model structured specifications instead of natural language descriptions. And while I’m still exploring its full potential, I’ve seen enough to know this matters. For high-precision work—marketing images, UI mockups, data-heavy infographics—JSON gives you a level of control that vibes-based prompting simply doesn’t.

I started down this path when trying to recreate a marketing photograph using entirely JSON controls. I had my schemas put together and was hard at work on this article when I started seeing some JSON examples pop up in the Substack chat as one. As I read through the examples the thing that kept popping out at me was that Nano Banana Pro needs specifics, and JSON is a very clean and efficient way to get specifics to Nano Banana Pro.

After a couple of weeks of testing, I’ve found JSON consistently useful across three buckets: product and marketing photography, UI mockups and app designs, and data-heavy infographics and diagrams. Each has its own schema structure, but they share a common principle: when you know what you want and the stakes are high, structured specifications outperform loose descriptions.

But you don’t have to know JSON to take advantage of the power here! I built a translator prompt so you don’t have to learn JSON syntax yourself. You describe what you want in plain English, the translator converts it to a structured schema, and you pass that to Nano Banana Pro. You stay in your comfort zone while getting the benefits of machine-readable precision.

Let me walk through why this works, when it’s the right approach (and when it isn’t), and how to actually do it.


## **The Problem with Vibes**

Most people use image generators the way they use Midjourney. You type something like “neon cyberpunk city, moody, 35mm film” and hope for the best. The model vibes it out. Sometimes you get magic. Sometimes you get nonsense. Either way, you’re not really in control.

That works fine when you’re exploring. It breaks down completely when you need correctness.

Think about a marketing image where the product has to look exactly right—specific lighting, specific label placement, specific props. Think about a UI mockup where you need particular colors, particular components, particular layout. Think about an infographic where the numbers actually have to be accurate.

These aren’t vibes problems. They’re precision problems. And precision is where Nano Banana Pro shines—but only if you give it the right kind of input.


## **What Makes Nano Banana Pro Different**

Nano Banana Pro isn’t a vibes machine. It’s a renderer. It thinks about what it’s doing, and it tries very hard to match what you actually asked for. It lives and dies on correctness.

This is both its superpower and its limitation. If you give it vague instructions, it doesn’t have the same improvisational flair as models optimized for creative exploration. But if you give it precise instructions? It delivers.

JSON gives it that precision. When you structure your request as a JSON schema—essentially a detailed spec with named fields—Nano Banana Pro has something concrete to honor. Subject, environment, camera angle, lighting, components, colors. Each important element gets a clear definition the model can respect.


## **What JSON Actually Is**

Let me demystify this for anyone who hasn’t worked with structured data before. JSON stands for JavaScript Object Notation, but forget that immediately. All you need to know is that JSON is a fancy list with keys and values.

Imagine you’re filling out a really detailed form. There’s a field for “subject,” a field for “background color,” a field for “lighting direction,” a field for “font style.” You fill in each field with what you want. That’s JSON.

Here’s the entire structure in plain English. A JSON schema is built from just a few patterns:

**Key-value pairs.** A label followed by a value. Like “background\_color”: “#003b47” or “font\_family”: “clean\_sans”. The label tells the model what property you’re setting. The value tells it what to set it to.

**Nested groups.** You can put key-value pairs inside other key-value pairs to organize related things together. So you might have a “lighting” group that contains “key\_light\_side,” “key\_light\_intensity,” and “fill\_light\_side” all bundled together.

**Lists.** When you have multiple items of the same type—like three screens in an app, or five props in a photo—you put them in a list using square brackets.

That’s it. No loops, no conditionals, no functions. Just structure. A rigid shopping list for a computer.

Models like JSON because it removes ambiguity. When you write “I want the lighting to be dramatic,” that could mean anything. When you specify that your key light comes from the right at high intensity with no rim light—that’s unambiguous. The model knows exactly what you’re asking for.


## **When JSON Is the Right Tool (And When It’s Not)**

I want to be direct about something: JSON is not a universal magic rune. I’ve seen people on Twitter claiming it’s the only correct way to prompt models. That’s not true. Models are trained on many languages and formats. They prompt well in lots of different ways.

JSON is specifically valuable when you know what you want and the stakes are high. It’s a tool for a particular job, not a replacement for all other approaches.

**Use JSON when:**

- You’re creating marketing images with exact product specifications
- You’re designing UIs with defined layouts, components, and color systems
- You’re making infographics or charts where the data must be accurate
- You need reproducibility—”give me the exact same screen but with this one change”
- You want to iterate on one element without regenerating everything else
- You’re building something that will go through multiple revision cycles

**Don’t use JSON when:**

- You’re exploring and want the model to surprise you
- You don’t yet know what the important variables are
- You’re doing loose creative ideation
- A single natural-language prompt would capture what you want

The rule of thumb: exploration happens in natural language, execution happens in JSON.


## **The Three Schema Types That Matter**

Nano Banana Pro spans multiple visual domains—photos, UIs, diagrams. Each domain has its own schema structure. Here’s what the key fields are for each one and what they control.


### **Photo Schema**

When you’re generating product shots, marketing images, or any photographic content, your schema breaks down into five main areas:

**Subject.** This is what the image is *of*. For a product shot, you’d specify the product type (can, bottle, device), brand name, dimensions, label or logo asset, and material finish (matte, glossy, metallic). For a portrait, you’d specify the person’s general appearance, clothing, pose, and expression.

**Props.** Objects that appear alongside your subject. You specify what they are (lime slices, ice cubes, flowers, devices), how many, and where they’re positioned relative to the subject (foreground, around base, background left). Being explicit about position prevents the model from scattering props randomly.

**Environment.** Everything that isn’t your subject or props. The surface the subject sits on (material, reflectivity), the background (color, whether it’s solid or has texture or bokeh effect), and the overall setting if relevant (studio, outdoor, abstract).

**Camera.** Your virtual camera setup. Angle (front, three-quarter, overhead, low), distance (close-up, medium, wide), and focal length (lower numbers like 24mm give wide-angle distortion, higher numbers like 85mm compress and flatten). This is where you control perspective.

**Lighting.** Where light comes from and how intense it is. You specify key light (your main light source—which side, how strong), fill light (secondary light that softens shadows—which side, how strong), and whether you want rim lighting (light from behind that creates edge highlights). The combination determines mood and dimension.

When you define all five areas, you’ve given Nano Banana Pro a complete specification for a photograph. It knows what to render, what context to put it in, and how to light and shoot it.


### **UI Schema**

When you’re generating interfaces—apps, dashboards, websites—your schema has a different structure:

**App metadata.** The foundational context: what platform (mobile, tablet, desktop, web), what fidelity level (wireframe, low-fi, high-fi), and viewport dimensions if relevant.

**Design tokens.** The visual system that applies across the entire interface. Colors (primary, secondary, background, surface, text colors with specific hex values), typography (font families for headers and body, sizes, weights), and spacing values if you want precise control. Tokens ensure consistency—when you change your primary color in the tokens, it changes everywhere.

**Screens.** Each distinct view in your app. Every screen gets an ID (so you can reference it), a name (what it’s called), and a layout definition. The layout specifies what containers exist on that screen and how they’re arranged.

**Layout containers.** The structural bones of each screen. A container might be a “top\_nav” (horizontal strip at the top), a “sidebar” (vertical strip on the left), or a “main\_content” area (the primary space). You specify each container’s ID, type (horizontal stack, vertical stack, grid), and position. This is how you control information architecture independently from what’s *in* each area.

**Component instances.** The actual UI elements: buttons, text fields, cards, charts, tables, navigation lists. Each component specifies which screen it belongs to, which container it sits in, what type of component it is, and its specific properties (label text, icon, variant like “primary” or “secondary,” data it displays).

**Interactions.** What happens when users do things. You can specify that tapping a button navigates to another screen, or that a toggle changes state, or that pulling down refreshes content. This makes your mockups feel like real apps rather than static images.

The power of this structure is that you can change your visual design (tokens) without touching your information architecture (containers) or functionality (components and interactions). They’re separate concerns that you control independently.


### **Diagram/Chart Schema**

When you’re generating infographics, data visualizations, or technical diagrams:

**Viewport and grid.** The overall canvas: dimensions (24”×36” for a poster, 1920×1080 for a presentation slide), orientation, and grid system (12-column grid with specific margins). This controls how everything else gets positioned.

**Design tokens.** Same concept as UI—your color palette, typography choices, and any texture or pattern specifications that should apply consistently.

**Sections.** The major areas of your infographic. Each section has an ID, a height or proportion of the total canvas, and a layout type. A header section might be full-width. A statistics band might use a five-column layout. A charts area might be split into left and right halves. Sections are how you control the overall composition.

**Chart components.** The individual visualizations. Each one specifies which section it belongs to, what type of chart (bar, line, pie, scatter, treemap), what role it plays (like “career\_points\_leaders” or “daily\_traffic”), and its data configuration. If you’re being precise, you can embed the actual chart specification in a format like Highcharts or Chart.js JSON.

**Data constraints.** The numbers that must appear exactly as specified. If your infographic needs to show that a team’s record is 567-197, you encode that as a constraint. This gives you something to verify against—did the rendered image actually include the correct number?

**Production specifications.** Technical requirements for final output: resolution (300 DPI for print), bleed area, export formats needed, and accessibility requirements like minimum contrast ratios.


## **The Power of Handles**

Here’s where JSON gets genuinely powerful, and it’s something I didn’t fully appreciate until I’d been experimenting for a while.

When you define your image or UI as a JSON schema, every important element gets what I call a “handle”—a stable identifier you can grab onto later. Your subject is separate from your environment. Each component in a UI has its own ID. Each section of an infographic is named.

Once those handles exist, you can make scoped changes.

**Scoped edits.** You say “regenerate this, but only touch the background.” Or “same layout, new color theme.” Or “keep the chart structure, update the data.” The model changes what you specified and leaves everything else alone. This is fundamentally different from normal image generation, where every regeneration turns the whole scene over to the model again.

**Camera moves.** You keep every element of a scene fixed—subject, props, lighting setup—and vary only the camera angle and focal length. Same scene, different perspective, completely controlled. You’re not asking the model to reimagine the scene; you’re asking it to re-render from a different viewpoint.

**Themed variants.** You’ve designed an alien control panel UI. You love the layout, the components, the information architecture. Now you want to see it as a clinical medical dashboard instead. You swap the theme tokens—colors and typography—while leaving the structural definition untouched. Same bones, new skin.

**A/B testing visual approaches.** You create two versions of a schema that are identical except for one variable: lighting direction, or primary color, or layout variant. You render both and compare. Because everything else is controlled, you’re seeing the true effect of that one change.

The handle concept is what turns Nano Banana Pro from “an image generator” into “a controllable rendering engine.” You’re not hoping the model remembers what you wanted. You’re pointing at specific named fields and saying “change this one.”


## **The Practical Workflow: English to JSON to Image**

Let me walk you through exactly how this works, step by step.


### **Step 1: Describe What You Want in Natural Language**

You start by writing what you’d naturally say to a designer. Don’t worry about structure yet. Just capture your intent.

“I need a mobile habit tracker app with a dark theme. Three screens: a home dashboard showing today’s habits, a calendar view for the month, and a stats screen with charts. I want it to feel like Notion meeting Duolingo—clean and minimal but with personality and satisfying micro-interactions. The main color should be a warm purple.”

That’s messy. It mixes concrete requirements (three screens, dark theme, warm purple) with vibes (feels like Notion meets Duolingo, satisfying). That’s fine. You’re not writing the schema yet.


### **Step 2: Feed It Through the Translator**

You pass your natural-language brief to an LLM along with my translator prompt (included below). The translator’s job is to:

- Extract concrete requirements from your description
- Make reasonable design decisions for anything you left unspecified
- Fill out a complete JSON schema in the appropriate format

What you get back is a fully structured spec. The model has interpreted “dark theme” as specific background and surface colors. It’s turned “three screens” into three screen definitions with IDs and layout containers. It’s translated “clean and minimal but with personality” into typography choices and spacing values. It’s made decisions about what components each screen needs.


### **Step 3: Review the JSON**

This is where learning to read pseudocode pays off. You don’t need to have written the JSON—you just need to be able to scan it and catch problems.

Look at the screen names. Do they make sense? Look at the components listed for each screen. Are the ones you care about present? Look at the color values. Are they in the right family? Look at the layout containers. Does the structure match what you had in mind?

You’re not checking syntax. You’re checking intent. Did the translator understand what you wanted?

If something’s wrong, you have two options. You can edit the JSON directly—just change the value that’s wrong. Or you can give the translator feedback in natural language: “The calendar screen should be the first screen, not the second. And I want the habit cards to show streak counts, not just checkboxes.” The translator will revise.


### **Step 4: Render with Nano Banana Pro**

Once your JSON looks right, you pass it to Nano Banana Pro. You can include a short instruction alongside the JSON—something like “Render this UI specification as a high-fidelity mobile mockup”—but the JSON is doing the heavy lifting.

Nano Banana Pro reads the structured spec and produces an image that honors it. Screen names appear as labels. Components show up in their specified containers. Colors match your tokens. The layout follows your container structure.


### **Step 5: Verify and Iterate**

Look at what you got. Does it match the spec?

For UIs, check that the components you specified are present and in the right places. Check that the color scheme matches your tokens. Check that text labels match what you specified.

For product photos, check that your subject looks right, props are positioned correctly, and lighting is coming from the direction you specified.

For infographics, check that the data is accurate. If you specified that a number should be 567, is it actually 567 in the image? If you specified five sections, are there five sections?

If something’s wrong, you iterate. And here’s the beauty of JSON: you don’t regenerate everything. You change the specific field that’s wrong and re-render. If the lighting is too harsh, you adjust the key\_light\_intensity value. If a button label is wrong, you change that one prop. The rest stays fixed.


## **Concrete Examples**

Let me show you what these schemas look like in practice, and what control they give you.


### **Example 1: Product Photo (Beverage Can)**

**What you want:** A hero image for a seltzer brand. 12oz can of “Aurora Lime” on a reflective surface, lime slices in foreground, ice cubes around the base, strong side lighting from the right, dark teal background with soft bokeh.

**How the schema captures it:**

Your subject block specifies: product type is “can,” brand name is “Aurora Lime,” volume is 12oz, label asset points to your logo file, finish is matte.

Your props block lists two items. Foreground contains lime slices—you specify 3 of them, positioned front left. Surroundings contains ice cubes—12 of them, region is “around base.”

Your environment block specifies the surface is glossy with reflection strength of 0.7, background color is #003b47 (that’s your dark teal), effect is “bokeh\_soft.”

Your camera block specifies angle is three-quarter front, distance is medium-close, focal length is 50mm.

Your lighting block specifies key light from right at high intensity, fill light from left at low intensity, rim light is off.

**What this controls:** You’ve locked the product geometry and label—Nano Banana Pro can’t turn your can into a bottle or improvise a different logo. You’ve specified exact prop placement—no random lime slices floating in the background. You’ve defined the lighting setup—if you want to try different lighting, you change only those values while keeping everything else fixed.

**Iteration example:** The first render comes back and the lighting is a bit flat. You increase key\_light\_intensity from “high” to “very\_high” and decrease fill\_light\_intensity from “low” to “very\_low.” Re-render. Now you have more dramatic contrast. Everything else—can, props, background—is identical.

[![](https://substackcdn.com/image/fetch/$s_!IVh0!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1d40ee72-6c9e-46fa-9fb2-dbabdcfc5a40_2752x1536.png)](https://substackcdn.com/image/fetch/$s_!IVh0!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F1d40ee72-6c9e-46fa-9fb2-dbabdcfc5a40_2752x1536.png)


### **Example 2: App UI (Alien Control Panel)**

**What you want:** A creative, unusual UI concept. An alien operating system or control panel. You want it to feel otherworldly but still be a coherent interface.

**How the schema captures it:**

Your app metadata specifies: platform is desktop, fidelity is high-fi, theme is “alien\_control\_panel.”

Your tokens specify colors: primary is #19ffb3 (neon green), background is #050016 (deep space near-black). Typography: font family is “condensed\_sci\_fi,” headline style is all-caps with wide letter spacing.

Your screens block lists three screens. First is “command\_bridge” with containers for left nav, main panel, and status bar. Second is “star\_map” with a full-bleed visualization container. Third is “bio\_scan” with a split view for data and visualization.

Your components block lists the specific elements. A button with ID “btn\_first\_contact” goes in the command\_bridge’s main panel, label text is “INITIATE FIRST CONTACT,” variant is “primary\_glow,” icon is “antenna.” A data visualization panel with ID “panel\_star\_map” is a hologram type showing local sector data. A gauge cluster shows system status metrics.

**What this controls:** You’ve given the model creative latitude within structure. It can decide exactly what an “alien” visual style looks like—the specific shapes, textures, and details. But it has to respect your screen structure, component inventory, and color system. It can’t randomly decide to make a two-screen app or ignore your neon green primary color.

**Iteration example:** First render comes back tilted at a weird angle, feels more like concept art than a usable UI. You keep the exact same JSON but change your instruction to Nano Banana Pro: “Render this as a clean, professional wireframe, straight-on angle, suitable for a design review.” Same spec, different rendering interpretation. The structure is preserved; the presentation style changes.

[![](https://substackcdn.com/image/fetch/$s_!FNhH!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F195c2812-fa1a-4743-8f84-b8705c3d18cb_2752x1536.png)](https://substackcdn.com/image/fetch/$s_!FNhH!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F195c2812-fa1a-4743-8f84-b8705c3d18cb_2752x1536.png)


### **Example 3: SaaS Dashboard**

**What you want:** A web dashboard for a marketing analytics tool. Top nav with logo and user avatar, left sidebar with navigation, main area with KPI cards, a traffic chart, and a campaigns table. Light theme, blue accents, professional.

**How the schema captures it**

[![](https://substackcdn.com/image/fetch/$s_!lQCb!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb9c5ab51-6b9a-43f6-9bcb-45844b045d37_2752x1536.png)](https://substackcdn.com/image/fetch/$s_!lQCb!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fb9c5ab51-6b9a-43f6-9bcb-45844b045d37_2752x1536.png)

**:**

Your app metadata specifies: platform is web, fidelity is high-fi, viewport is 1440×900.

Your tokens specify colors: primary is #2563EB (a medium blue), background is #F9FAFB (light gray), surface is #FFFFFF (white). Typography: font family is “system\_sans,” headline size is 20px, body size is 14px.

Your screens block has one screen, “dashboard\_main.” Layout containers: “top\_nav” (horizontal stack), “sidebar” (vertical stack), “content” (grid layout).

Your components are specific and concrete. The navbar component in top\_nav has logo text “Acme Analytics.” The avatar menu in top\_nav shows initials “NJ.” The nav list in sidebar has items Overview, Channels, Cohorts, Settings with Overview as active. The KPI grid in content shows three cards: Sessions (124,983), Signups (3,942), Conversion (3.2%). The line chart in content is titled “Daily Traffic (Last 30 Days).” The data table in content has columns Campaign, Spend, Clicks, CPC.

Your constraints specify: minimum tap target is 44 pixels, layout is locked.

**What this controls:** This is a boring but important example because it’s what people actually build. The schema ensures your information architecture is preserved. If you want a dark mode variant, you change only the tokens—swap background and surface to dark values, adjust text colors for contrast. The layout, components, and data all stay identical. You’re testing a visual variant, not rebuilding the screen.

**Iteration example:** Design review feedback says the KPI cards should be more prominent. You adjust the content container to give the KPI grid more vertical space, maybe change the KPI component variant from “standard” to “large.” Everything else stays fixed. The change is scoped and traceable.

[![](https://substackcdn.com/image/fetch/$s_!DMNW!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F38733004-6fdd-4d98-b73e-2be50ac634bd_2752x1536.png)](https://substackcdn.com/image/fetch/$s_!DMNW!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F38733004-6fdd-4d98-b73e-2be50ac634bd_2752x1536.png)


### **Example 4: Data Infographic**

**What you want:** A vertical poster showing 20 years of statistics for a sports team. Multiple sections with different chart types, strict team color palette, specific numbers that must be accurate.

**How the schema captures it:**

Your viewport specifies: 24 inches wide, 36 inches tall, portrait orientation, 12-column grid with half-inch margins.

Your tokens specify the team color palette—let’s say Carolina blue (#7BAFD4), navy (#13294B), gold (#C4A052), plus neutral grays. Typography: headers use a bold condensed sans, body uses a clean readable sans, numbers use a condensed bold style for impact.

Your sections block divides the poster: header section (3 inches, full width), big numbers band (3 inches, five-column stat layout), championship timeline (3 inches, full width), career leaders charts (6 inches, left half), defensive stats (6 inches, right half), footer (2 inches, full width).

Your chart components specify each visualization: a horizontal bar chart for career points leaders in the career leaders section, a line chart showing wins per season in another section, a comparison bar chart for rivalry records. Each chart specification includes its data or points to a data source.

Your data constraints list the numbers that must appear exactly: overall record is 567-197, win percentage is 74.2%, total points is 61,808. These are your verification targets.

Your production specs: 300 DPI, 0.125 inch bleed, export to PDF and PNG, minimum contrast ratio 4.5:1 for accessibility.

**What this controls:** The structural schema means you could swap in a different team by changing the data and tokens—same layout, different content. The data constraints give you something to verify against: after rendering, you can check whether the infographic actually shows 567-197 or if the model hallucinated a different number. The production specs ensure the output is usable for print.

**Iteration example:** Client wants to add a 20th-year highlight section. You add a new section to the sections block, position it appropriately, define what content it should contain. The rest of the infographic is unaffected. Your change is additive and contained.

[![](https://substackcdn.com/image/fetch/$s_!SVCB!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fff7ec551-e669-4502-83c7-2d839dfad304_1696x2528.png)](https://substackcdn.com/image/fetch/$s_!SVCB!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fff7ec551-e669-4502-83c7-2d839dfad304_1696x2528.png)


## **Learning to Read Pseudocode**

I want to spend a moment on this because it matters beyond just using Nano Banana Pro.

JSON is pseudocode. It looks like programming, but it isn’t. There’s no logic to execute—it’s just structured data. The skill you need is pattern recognition: understanding what the structure means, not how to run it.

Here’s a practical ladder for building this skill:

**Level 1: Recognition.** You can look at a JSON schema and understand that it’s organized into sections, that fields have values, that some things are grouped together. You recognize the structure even if you couldn’t write it yourself.

**Level 2: Mapping.** You can look at a rendered image and trace elements back to their schema definitions. “Oh, that button is btn\_first\_contact from the components list. That’s why it says INITIATE FIRST CONTACT.” You understand the correspondence between spec and output.

**Level 3: Spotting errors.** You can scan a schema and notice when something’s missing or wrong. “Wait, there’s no component for the search bar I wanted.” “This color value doesn’t look right—it’s yellow but I wanted blue.” You catch problems before rendering.

**Level 4: Small edits.** You can change individual values in a schema. Swap a color code, change a label, add an item to a list. You’re not restructuring anything—just tweaking.

**Level 5: Structural edits.** You can add new sections, create new components, reorganize containers. You understand how the pieces relate and can modify the architecture.

**Level 6: Template creation.** You can design schemas from scratch for new use cases. You decide what fields exist and how they relate.

You don’t need to reach Level 6 to get value from JSON prompting. Level 3 or 4 is enough for most practical work. The translator prompt handles the initial generation. You just need to be able to review and tweak.

And here’s the career point: this skill transfers. JSON is everywhere. APIs use it. Config files use it. Data feeds use it. The ability to read and understand structured data makes you someone who can work at the boundary between human intent and machine execution. That boundary is where a lot of the valuable work happens now.


## **Turning Nano Banana Pro into a System Component**

Once you’re working with JSON schemas, something important shifts. Nano Banana Pro stops being a toy you play with and starts being a component you can integrate into real workflows.

**Reproducibility.** The same JSON spec produces the same render, within normal model variance. You can hand a spec to a colleague and they’ll get essentially what you got. You can re-render something from six months ago and get the same result. “It worked when I tried it yesterday” becomes “here’s the exact spec, render it yourself.”

**Diffability.** You can compare version 3 and version 4 of your design and see exactly what changed. “Added a sidebar navigation item. Changed primary color from #2563EB to #1D4ED8. Increased header font size from 20px to 24px.” No more prompt archaeology—the changes are explicit in the JSON.

**Governance.** You can encode rules in your schema. Accessibility requirements: minimum tap targets of 44 pixels, contrast ratios above 4.5:1. Brand requirements: only these approved colors, only these approved fonts. Data integrity requirements: these specific numbers must appear exactly as specified. The rules become part of the spec, not verbal instructions that might be ignored.

**Verification.** Because your spec is explicit, you can verify whether the render honored it. Did the component labeled “btn\_first\_contact” actually appear with that label? Does the chart show the correct data points? Is the primary color actually the hex value you specified? This enables quality checks that go beyond eyeballing.

**Version control.** JSON files are text. You can put them in git. You can track history, branch for experiments, merge changes, roll back mistakes. Your design specs get the same rigor as your code.

**Team collaboration.** A JSON spec is shareable in ways that “the prompt I typed into Midjourney” isn’t. Designers, developers, and stakeholders can all look at the same spec and understand what’s supposed to be rendered. Disagreements become concrete: “This field should be X, not Y.”

This is what it means to use Nano Banana Pro for real work instead of playing with it. You’re building a system, not generating one-offs.


## **Common Patterns**

A few patterns that work well once you’re comfortable with the approach:

**Spec once, reuse many.** Build a schema template for a specific type of output—a product photo setup, a SaaS dashboard layout, an infographic structure—and reuse it across projects. Your template becomes a design system encoded in data. When you need another product shot, you don’t start from scratch; you start from your template and modify the product-specific fields.

**Lock and vary.** The power move is freezing most fields while exploring one variable. Lock the layout and components, vary only the color tokens. Lock the composition and lighting, vary only the camera angle. Lock everything about the subject, vary the background. This gives you controlled experimentation—you’re seeing the true effect of one variable instead of confounding changes.

**Progressive specification.** Start loose, then tighten. Your first pass might leave many fields unspecified or set to reasonable defaults. You render, evaluate, and then add specificity where the model made choices you don’t like. Over multiple iterations, your spec gets more precise in the areas that matter and stays loose in the areas where you’re happy with model discretion.

**Schema families.** Maintain related schemas for different contexts. A photo schema, a UI schema, and a diagram schema might share a common tokens section (your brand colors and fonts) but diverge in their domain-specific structures. Consistency where it matters, specialization where it’s needed.


## **Common Pitfalls**

And some traps to avoid:

**Over-specification.** It’s possible to lock things down so tightly that you’re essentially describing every pixel—at which point you might as well just build the thing directly. Leave room for the model to contribute where appropriate. If you don’t care about a particular field, leave it unspecified or set to “default.”

**Under-specification.** The flip side: if you leave critical fields vague or null, the model fills them in however it wants, and then you’re frustrated that it didn’t read your mind. Be explicit about the things that matter to you. The translator prompt helps with this by forcing you to think through the important fields, but you still need to review.

**Schema drift.** If you edit your templates ad hoc without tracking changes, you lose the benefits of reproducibility and diffability. Treat your JSON files with the same discipline you’d apply to code. Version them. Document changes. Don’t let them mutate randomly.

**Wrong tool for the job.** Remember that JSON prompting is specifically valuable when you know what you want and need precision. If you’re exploring, if you want to be surprised, if you’re in early ideation—just prompt in natural language. Don’t force structure onto a creative process that benefits from looseness.


## **Getting Started: Your Minimal Setup**

Here’s what I recommend for getting started:

**Use the translator prompt.** I’m including it below. You write your brief in plain English, pass it through the translator, and get JSON out. You don’t have to learn JSON syntax—you learn to read and review it.

**Start with one schema type.** Pick the domain you’re most likely to work in. Product photos if you’re doing marketing content. UI if you’re designing apps. Diagrams if you’re building presentations or infographics. Learn that schema structure first before expanding.

**Do a reconstruction exercise.** Take something simple that already exists—a basic app screen you use daily, a product photo you’ve seen, an infographic you liked—and try to reproduce it via JSON and Nano Banana Pro. This builds your intuition for how schema fields map to visual outputs.

**Practice scoped edits.** Once you have a working render, deliberately change one field at a time and re-render. Swap a color. Move a component to a different container. Change the lighting direction. Watch how the output changes. This builds your intuition for what each field controls.

**Build your template library.** As you create schemas that work well, save them as templates. Over time, you’ll have a collection of starting points for different types of projects. Your “product photo with side lighting” template, your “SaaS dashboard” template, your “vertical infographic” template.


## **The Translator Prompt**

Here’s the prompt that converts natural-language descriptions into JSON schemas. You can use this with Claude or another capable LLM.

---

**System prompt for the JSON translator:**

You are a translator that converts natural language design briefs into structured JSON schemas for Nano Banana Pro.

When given a description of a desired image, UI, or infographic, you will:

1. Identify what type of output is being requested (photo, UI, diagram/chart)
2. Extract all concrete requirements from the description
3. Make reasonable design decisions for unspecified elements
4. Output a complete JSON schema in the appropriate format

For PHOTO requests, your schema should include:

- subject (type, details, materials, key identifying features)
- props (list of items with counts and positions)
- environment (surface, background, setting)
- camera (angle, distance, focal length)
- lighting (key light, fill light, rim light specifications)

For UI requests, your schema should include:

- app metadata (platform, fidelity, viewport)
- tokens (colors with hex values, typography, spacing)
- screens (list with IDs, names, and layout containers)
- component\_instances (specific UI elements with screen assignment, container assignment, component type, and props)

For DIAGRAM/INFOGRAPHIC requests, your schema should include:

- viewport (dimensions, orientation, grid)
- tokens (colors, typography)
- sections (list with IDs, sizes, layout types)
- chart\_components (visualizations with section assignment, chart type, and data)
- data\_constraints (specific values that must appear accurately)

Always output valid JSON. Include comments (as a “\_comment” field) explaining non-obvious decisions. When the user’s description is ambiguous, make a reasonable choice and note what you assumed.

---

**To use it:** Pass your natural language brief as the user message. The model will return a filled-out JSON schema. Review the schema, make any needed adjustments, and then pass the JSON to Nano Banana Pro for rendering.


## **What I’m Still Exploring**

I want to be honest about where I am with this. JSON prompting works—I’ve seen it work consistently across dozens of experiments. But I’m still discovering its boundaries.

I don’t yet have a clear answer for how much specification is too much. There’s a point where you’ve described the image so completely that you’ve removed any value the model could add. I haven’t found that line precisely.

I’m still learning which fields matter most in each domain. Some fields seem to have strong effects on the output; others seem to be mostly ignored or have subtle impacts I can’t reliably predict. More experimentation needed.

I’m curious about combining JSON prompting with other techniques—like verification loops where a second model checks whether the render matches the spec, or automated pipelines that generate variants systematically. These feel like promising directions, but I haven’t built them out yet.

What I can say is that for the use cases I’ve described—product photos, UIs, infographics—JSON prompting has meaningfully improved my results. It’s given me control I didn’t have before. And it’s made iteration faster and less frustrating.

If you try it and discover something useful, I’d love to hear about it. This is a technique that deserves more attention than it’s getting.


## **Takeaways**

Here’s what I want you to take away.

Nano Banana Pro is at its best when you treat it like a renderer that respects specifications. It’s not trying to be a vibes machine. It’s trying to be correct. JSON schemas are how you write specs in a way that both humans and models can reason about.

You don’t have to change how you think or work. Keep describing things in paragraphs or bullets or however feels natural. The translator handles the conversion into the structured world Nano Banana Pro cares about.

What you end up with is a controllable, composable visual engine instead of a one-off toy that occasionally gets lucky. You get reproducibility: the same spec yields the same output. You get scoped iteration: change one field, see one change. You get governance: encode your requirements as data, not hope. You get collaboration: share specs, not prompts.

Don’t be afraid of the JSON. It’s not really code—it’s structured data, fancy lists, pseudocode. The translator will help you. And once you see what’s possible when you give a precision-focused model precise instructions, you won’t want to go back to pure vibes.

[![](https://substackcdn.com/image/fetch/$s_!6dNF!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F237370f3-e779-49bd-b807-89c54c468b70_5632x3072.jpeg)](https://substackcdn.com/image/fetch/$s_!6dNF!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F237370f3-e779-49bd-b807-89c54c468b70_5632x3072.jpeg)

[![](https://substackcdn.com/image/fetch/$s_!RP0T!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943305c2-20f6-47c8-9e34-a41d0322abe3_512x512.png)](https://substackcdn.com/image/fetch/$s_!RP0T!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F943305c2-20f6-47c8-9e34-a41d0322abe3_512x512.png)
