---
title: "FINALLY: AI Can Do Excel and PowerPoint—Get Prompts, Demo, and Full Details on Claude Code Interpreter"
author: "Nate Jones"
published: 2025-09-11
url: https://natesnewsletter.substack.com/p/finally-ai-can-do-excel-and-powerpointget
audience: everyone
scraped_at: 2026-01-05 19:18:20
---

*When I got to dig into Claude’s latest release I had to check three times to make sure I wasn't hallucinating.*

*Yesterday, I watched Claude build an eight-tab Excel spreadsheet with working VLOOKUP formulas, conditional formatting, and a documentation tab explaining its methodology—in under three minutes. Not a CSV file I had to reformat. Not broken formulas I had to fix. An actual, professional spreadsheet I could send to a colleague without touching a single cell.*

*Powerpoint? Is that your thing? Claude has you covered there too. It can take complex financial data and turn it into a professional, scannable, properly formatted deck with good narrative flow and interesting business insights your Director would actually want to see. My jaw was on the floor, and you’ll see it in the video.*

*I went live on video for 40 minutes with my buddy Rod (an AI consultant) to stress-test it. We threw increasingly complex challenges at Claude, and you’ll see how shocked we were live as Claude handled everything we threw at it.*

***Curious? I packed this with what you need to get started with Claude Code Interpreter (terrible name I agree, but what is new?!):***

- ***The complete 40-minute video** where Rod and I discover capabilities we didn't know existed—watch us build pivot tables with heat maps and sparklines Claude adds without being asked*
- ***Master prompt templates** you can copy-paste right now to generate professional Excel models and PowerPoint decks (tested on financial models, data analysis, and business presentations)*
- ***The exact Perplexity → Claude workflow** that gets superior results—how to use Perplexity to package data, then Claude to build files, with specific examples*
- ***Side-by-side breakdowns** of Claude vs Agent Mode showing precisely why one produces usable work and the other produces garbage*
- ***What Claude does automatically** so you know what to expect—VLOOKUPs, conditional formatting, documentation tabs, centered text, proper spacing*
- ***Real prompts from real tests** including the Oracle valuation model and movie night pivot table, so you can see exactly how to structure requests*
- ***Time savings data**—Claude delivered minutes faster than Agent Mode while producing work you won't need to fix*

*Claude positioned this as a feature announcement and they’re wrong.*

*This isn't just another feature announcement. If you touch Excel or PowerPoint in your work, you now have templates and techniques to compress days of work into minutes. Actually usable work, not drafts you'll rebuild. It’s a MASSIVE step forward.*

*Alfred North Whitehead said civilization advances by extending the number of operations we can perform without thinking about them. (The idea being that you can save your thinking for what matters more.)*

*I feel like it’s a bit cheesy to apply that to AI, but on the other hand that is literally what I witnessed today, and this is going to be a literal 10x game-changer for anyone who works in Excel or PowerPoint for a living. I’m not exaggerating—I used to have to maintain marketing spreadsheets for a living and what I saw out of Claude in 3 minutes would have taken me at **least** a half day.*

*So let’s dive in and start figuring out how to use AI for spreadsheets and presentations!*

We’re going to do this one a little bit differently: the goal is for you to use this piece as a companion you can look through as you watch the video, complete with prompts and thinking on how to make the most of Claude’s new capabilities. You’ve got everything you need here to take advantage of the first AI to really do Excel and PowerPoint properly. Enjoy!


## First, what launched?

Claude's code interpreter launched with support for creating and editing **Excel spreadsheets, PowerPoint slide decks, Word documents, and PDF files** directly in the Claude.ai web interface and desktop app.


### Supported File Creation and Editing

- **Excel (.xlsx)**: Users can both create and modify spreadsheets, perform data analysis, and generate charts.
- **PowerPoint (.pptx)**: Claude can build and edit presentation decks, including transforming reports or summaries into slides.
- **Word documents (.doc/.docx)**: Creation and editing of formatted text documents is fully supported.
- **PDF files**: Claude can output finished reports, summaries, and other content as PDFs or edit existing ones.


### Additional Capabilities

- **Python and Node.js code execution**: Claude can run custom Python (and Node.js) code in a secure server-side sandbox to process, analyze, and generate files.
- **CSV/TSV and Advanced Data Analysis**: Users can upload and analyze CSV/TSV datasets, perform data science, visualize results, and output files accordingly.
- **Other file types**: Support extends to creating and analyzing files for data workflows, including generating images (like charts) in PNG format and handling various code and config filetypes in the code interpreter environment.


### Usage and Rollout

- Available now for Claude Max, Team, and Enterprise plans, with Pro users receiving access "in the coming weeks" and no announced date for free users.

  - *Yes, we don’t really know when Pro plans get this, and I know that’s painful!*


## What are the takeaways from my deep dive?


## Technical

**Claude vs. OpenAI**

- OpenAI's Agent Mode leans too far in and attempts sophisticated analysis but fails in file execution. Claude takes a conservative approach but is actually able to create complete quality files.
- Claude's architecture is optimized for production-ready outputs rather than demos. The spreadsheets it generates have working formulas, proper formatting, and professional standards. This seems like a low bar but it’s a BIG deal.

**Speed and Reliability Performance**

- The delay is real: Claude consistently delivered results minutes faster than ChatGPT Agent Mode while producing higher quality outputs. Claude's inference architecture seems to handle planning and tool calling with the file output in mind all the way through. Agent Mode seems to create the file as an output AFTER the analysis.

**Professional Standards (aka Does it look good?)**

- TLDR Claude cooks: It adding correct heat maps, proper text centering, documentation tabs, and README files without explicit instructions. It even knew how to handle spark lines in cells and could construct 8 tabs of proper formulas in one shot!
- Claude volunteers features like VLOOKUP formulas, IF statements, and conditional formatting automatically, but it can also follow prompts when you want advanced features like pivot tables and ask for them. The team at Anthropic has clearly figured out something special around tool calling + Opus 4.1 here.


### Prompting Approach

**Multi-LLM Workflow Optimization**

- Why work hard? I used Perplexity for comprehensive data gathering and prompt construction, Claude for document creation and formatting, and played with optional Agent Mode for initial analysis with Claude for final execution (Agent was good at analysis).
- I would NOT ask Claude to do research and build the file in one shot. The most effective approach uses Perplexity to create self-contained data packages rather than asking Claude to research and create simultaneously.

**Prompt Construction Principles**

- My most successful prompts were data-first, instruction-last structured with complete financial/business data followed by specific formatting and output requirements.
- This implies that if you use internal data you’re going to need to take some effort to package up the data with the prompt. I do think it’s fine to pull a prompt in and attach csv files (I played with that successfully and used multi-thousand row files).
- Asking matters! When I didn't explicitly tell Claude to create Excel files, it defaulted to text analysis.


### Practical Implementation

**Quality**

- The PowerPoint is good enough for everyday use across businesses, although I’d look at it twice before putting it in front of enterprise C-Suite (I’ve also seen worse PowerPoints in boardrooms, though so YMMV).
- The Excel work compresses days of work into minutes and I’m not kidding. If you value your time anywhere over $10 an hour and if you do Excel regularly, I think Max pays for itself really fast.
- I have not tried Excel edits, and I suspect it will be better creating new files.

**Cut Prep Time**

- Part of the time savings is iterativeness: rehearsing presentations within the AI interface before meetings. Having the conversation with Perplexity and Claude gets you in the mindset for a presentation and cuts prep time.

**Documentation**

- Claude is better than me at formula documentation. Claude automatically creates methodology documentation, explaining formulas, assumptions, and data sources without being asked. I was really blown away here. Takes the black box away and builds trust.


### Technical Architecture

**Tool Use vs Raw Intelligence Trade-off**

- Claude appears to have made an architectural choice: prioritize reliable tool execution over sophisticated analysis (remember Opus is technically not an inference model, it’s just a really big LLM). The payoff works: Claude produces usable, professional deliverables and Agent Mode…doesn’t.

**Cognitive Load**

- Claude's stepwise approach (analyze → code in Python → create spreadsheet → document) suggests a smarter underlying agentic framework. Claude Opus 4.1 clearly plans well and knows when how to invoke tools from natural language in a reliable manner.

**Professional Standards as Training Data**

- The automatic addition of heat maps, proper formatting, and documentation suggests Claude was trained extensively on professional document examples rather than just instructional data.


### Strategy Implications

**Wrapper Businesses Beware**

- Excel and PowerPoint were considered big barriers, and they fell today. If you’re betting on “AI can’t do this yet” make sure you check your assumptions.
- Just Claude Code and OpenAI Codex are eating Cursor, I’m thinking Claude’s skills here (which will only get better) will push hard on specialized tools like Gamma.

**Delegate More**

- We can delegate a substantial new chunk of work to AI as of today. It’s the biggest single jump in half a year, and it’s going to make AI-powered professionals even more powerful. Team implications are (as usual) much more complex and will depend on team workflows.


## Give me some prompts to get me started here…

Yes, with the insights gathered there is enough to construct master-level prompts for Claude to generate high-quality PowerPoint and Excel deliverables. These prompts harness best practices for clarity, structural specificity, and maximizing Claude's automated capabilities while reflecting the most recent successful usage patterns.


### Claude Master Prompt: Excel

```
You are a senior business analyst and expert Excel user. Create an Excel spreadsheet based on the following requirements:

1. Structure: - Include [describe tabs needed, e.g., "Input Data", "Analysis", "Summary Dashboard with charts"]. - Use proper table formatting, cell alignment, and color coding for readability. - Formulas: Use appropriate [basic (SUM, AVERAGE), or advanced (INDEX/MATCH, XLOOKUP)] formulas; explain unique formulas in a "README" or "Documentation" tab.

2. Data: - [Describe if sample data is required, e.g., "Populate with realistic sample data for a mid-sized tech company, 12 months, 6 expense categories"].

3. Automation: - Include automatic calculations, total summaries, or heat maps where helpful. - If relevant, add validation to prevent common input errors.

4. Documentation: - Add a "README" tab explaining data sources, calculations, and instructions for updating the file.

5. Constraints: - Ensure the file is usable by intermediate-level Excel users. - No macros unless explicitly requested; keep all features within native Excel capabilities. Requirements: [Insert project-specific, domain-specific requirements or upload relevant data if needed] Wait for my review of the structure before proceeding to populate data and complete the analysis.
```

Key points:

- Define structure, tabs, and formulas up front for clarity and best results.
- Explicitly request documentation and intermediate-level formulas for maintainability.
- Ask for iterative or staged delivery for large projects (structure first, then formulas/data).


### Claude Master Prompt: PowerPoint

```
You are a management consultant and expert presentation designer. Create a PowerPoint presentation for the following scenario:

1. Structure & Story: - Organize content into [number] sections: [list sections, e.g., "Executive Summary, Market Analysis, Key Recommendations, Financial Projections"]. - For each section, create slides with clear headlines and concise bullet points. - Include one data visualization (chart or graph) per major section [specify sources or require sample data as needed].

2. Visual & Formatting Guidelines: - Use a clean, professional theme with consistent fonts, color palette, aligned titles, and properly spaced content. - Add icons, callouts, or summary boxes to highlight key insights where appropriate. - Ensure slides are visually uncluttered—no more than 6 bullet points per slide.

3. Requirements: - Add a "Backup" section for any supporting detail slides or appendices. - Include slide notes summarizing the presenter’s message for each slide, where interpretation is critical. - For any tables or charts, ensure underlying data is included in an accessible format or worksheet.

4. Constraints: - Deck should be usable as a stand-alone readout (i.e., self-explanatory if shared without presenter). - Output as a PowerPoint file, ready for download. Input/Scenario: [describe business case, meeting objective, or presentation target] [Review and iterate on structure before finalizing full content if it's a large or high-stakes deck.]
```

Key points:

- Be explicit about structure, sectioning, data visualization, and formatting needs.
- Require slide notes/presenter guide for full context.
- Ask for a review checkpoint on structure for strategic decks.[anthropic+3](https://support.anthropic.com/en/articles/12111783-create-and-edit-files-with-claude)


### Best Practices for Claude Prompting

- Upload all relevant files and describe desired end state up front for maximal context.
- Explicitly state documentation, skill, and review/iteration preferences.
- For highly specialized decks or models, provide sample data and context, and incrementally build with Claude’s assistance.


## A few extra prompts

Want to go farther? I put together some additional prompts specific to using Claude’s interpreter for **Excel** and **PowerPoint** workflows. These pull in prompt best practices and give you options to tackle a variety of tasks with Claude Code Interpeter.


### Start with Data, End with Instructions

**Principle:** Place your data, scenario, or requirements upfront, then provide clear, specific instructions at the end. This structure dramatically improves Claude’s file generation quality.

**Prompt Template for Excel:**

```
<data> Financial results for FY25: - Revenue: 10M, Expenses: 6M, ... [paste data or describe] </data> <instructions> You are a corporate finance analyst. Build an Excel workbook with: • Tabs: Input Data, Calculations, Summary Dashboard. • Use formulas for all calculations, including year-over-year growth. • Add conditional formatting (heatmaps) to highlight top and bottom performers. • Include a 'README' sheet explaining each tab and assumptions. • Make it usable for a non-expert to update monthly going forward. Wait for my review of the structure before populating all data. </instructions>
```


### Set the stage

**Principle:** Set the context for what you’re looking for and explain your constraints, goals, and immediate ask.

**Prompt Template for PowerPoint:**

```
<scenario> You are a McKinsey-level management consultant. Task: Create a PowerPoint presentation for a board meeting on [topic]. </scenario> <instructions> • Sections: Executive Summary, Market Overview, Key Recommendations, Risks. • For each section, draft 1-2 slides with concise, insight-rich headlines. • Add a summary chart or visual per section using sample data. • Use a clean, professional layout, logical slide order, and speaker notes for key slides. • Include a backup/appendix section for data details. Present only the outline before drafting full slides. </instructions>
```


### Explicit Output Formatting and Modularization

**Principle:** Specify exact file structure, formatting (e.g., tables, visual highlights), and modular task breakdown in the prompt. For complex workbooks or decks, assign tasks stepwise and reference completed outputs as context.[iweaver+1](https://www.iweaver.ai/blog/claude-4-models-demystified-use-cases-prompt-tricks-and-avoiding-pitfalls/)

**Excel Prompt Example:**

```
Create an Excel file with three clearly separated tabs: 1. Raw monthly sales data, formatted as a table. 2. Calculated KPIs (gross margin, growth %, etc.), using cell formulas. 3. Dashboard with charts summarizing trends and highlighting outliers. Explain any advanced formulas in a dedicated 'Formula Notes' tab.
```

**PowerPoint Prompt Example:**

```
For each section, create a slide with: • Headline summarizing the main point. • 3-5 bullet points, each supported by data or visual (chart/graph). • Apply consistent color palette; ensure slides are easy to read. After all sections, generate an executive summary as the first slide.
```


### Chain-of-Thought and Quality Control

**Principle:** Ask Claude to walk through reasoning and perform a self-check on output validity, especially for formulas and visual elements.[anthropic+2](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices)

**Prompt Addition:**

```
Before finalizing, list any formulas, charts, or formatting details you're unsure about, and justify why you chose specific methods. Revise based on your self-assessment before outputting the final file.
```


### Iterative Prompts

**Principle:** For substantial, high-stakes artifacts (multi-tab Excel, board-level decks), require Claude to deliver structure/outlines first, then populate each with content in rounds.[walturn+2](https://www.walturn.com/insights/mastering-prompt-engineering-for-claude)

**Prompt Addition:**

```
Deliver only the file structure (tab names/slides, layout, summary of formulas) for my review first. Once approved, proceed to fill in details, data, and visuals step-by-step.
```

These practices—structuring with XML tags or labeled sections, assigning expert roles, breaking complex output into steps, and explicitly requiring explainability and review checkpoints—yield the most robust, production-ready Excel and PowerPoint files using the newest Claude interpreter abilities.


## The TLDR

> *“Civilization advances by extending the number of important operations which we can perform without thinking of them.” - Alfred North Whitehead*

This is a big moment. A substantial part of the workday got easier today, and it’s relatively easy for anyone to go and use.

We’re going to have more consistent and useful spreadsheets (the ones I show on the video are above average as far as fit and finish), and we’ll see the end of PowerPoint hell. Businesses that make their living making these manual tasks slightly easier are in trouble.

Longterm, even Microsoft should be worried about the value moving out of their tool into the AI. Chatbots continue to be a tremendously sticky interface!

One more note: Claude’s choice to release this for Pro plans first is reinforcing a pay-to-play format that’s starting to become a real pattern across model makers. You can literally pay to get twice or three times the work done now. People who can, will, and they’ll have a massive advantage.

> *Curious to learn more about Rod? [You can find his site here](https://fortylaunch.com/).*
>
> *If you’re like to be a guest for a conversation on a future podcast, shoot me an email with your pitch (chef@natebjones.com).*

[![](https://substackcdn.com/image/fetch/$s_!UjbD!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdf5b2e20-9d67-4b2c-885e-8f6baa02d1ca_1024x1024.png)](https://substackcdn.com/image/fetch/$s_!UjbD!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdf5b2e20-9d67-4b2c-885e-8f6baa02d1ca_1024x1024.png)
