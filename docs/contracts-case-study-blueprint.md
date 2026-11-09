# Case study blueprint: how "Contracts revamp" is structured and told (and how to adapt it for MBO)

This file breaks down the Contracts revamp case study (`v2/contracts/final.html`) so it can be used as a model for a new case study, like **MBO**. It covers:

1. A prompt you can give Claude, plus how to adapt the arc for a greenfield project (1b).
2. The story arc, section by section, with the real Contracts copy as the example.
3. The voice and writing rules.
4. The page building blocks (HTML classes) so the new page looks the same.

---

## 1. Prompt to give Claude for the MBO case study

MBO is a **greenfield project** (built from scratch, nothing existed before), while Contracts was a redesign. So the prompt asks Claude to keep the Contracts *storytelling and look*, but swap the "old vs new" parts for the greenfield arc in section 1b.

> Go through the MBO codebase (and any design files, PRDs, tickets or Figma links I share) and figure out:
> - what MBO is and who uses it
> - how people handled this before the feature existed (spreadsheets, other tools, manual work, or not at all)
> - what problems that caused, and why it was worth building
> - what had to be decided first (scope, what went into the first version, what was left out)
> - what was designed and built, step by step, in the order a user goes through it
> - the key design decisions and why they were made
> - what edge cases and empty, error or missing-data states were handled
> - what approaches were tried and dropped
>
> Then write a portfolio case study for it that follows the voice and building blocks in `docs/contracts-case-study-blueprint.md`, using the **greenfield arc in section 1b** instead of the redesign arc. Use `v2/contracts/final.html` as the reference implementation and create `v2/mbo/final.html` with the same markup and classes.
>
> Rules:
> - This is not a redesign. Don't write "old experience" vs "new experience" comparisons for the product itself. Compare against how people managed *before the feature existed* only where that's real.
> - Don't invent facts, numbers, customer quotes or outcomes. If something isn't in the code or what I give you, leave a clearly marked `<!-- TODO: ... -->` placeholder and list it for me at the end.
> - Use plain, warm, first-person language (I / we), short sentences, no jargon or buzzwords.
> - For each step, say what the user does, what I designed, and why.
> - Mark where screenshots or recordings should go with a placeholder and a one-line description of what they should show.
> - Before writing the page, give me a short outline (section headings plus one line each) so I can check the story first.

---

## 1b. Adapting the arc for a greenfield project

The *shape* stays the same as Contracts: set up the people and the problem, then the turning point, then a walkthrough, then edge cases, explorations, outcome and reflection. Only the redesign-specific parts change.

| Contracts (redesign) | MBO (greenfield) | What to write |
|---|---|---|
| Hero | **Hero** | Same: the outcome as the title, role and collaborators, a 2-paragraph intro (what it is, what I did and the key focus). Say it was built from scratch. |
| Who uses Contracts? | **Who uses it** | Same persona cards. |
| Understanding the problem (the old 5-step workflow) | **How people managed before** | How the job got done without the feature: spreadsheets, another tool, back-and-forth, or not at all. Use numbered steps only if there was a real process. End on the one key insight as a pull quote. |
| Bringing AI into the workflow (question blocks) | **Shaping the product / defining the first version** | The open questions at the start, as question blocks ("What did the first version need to do?", "How would ___ work?"). Then what went in, what was left out, and why. Include research or inputs from other teams if real. |
| How the experience changed (01–05, old vs new) | **Designing the experience** | Numbered parts 01–05 in the order the user goes through the product. Each part: one line on what the step is for → what I designed, with the key decision in **bold** → **why** → a recording or screenshot. **No old/new tags.** Use flow-steps, duo or step-label blocks for detail. |
| Designing for when AI falls short | **Designing for the messy cases** | The same "When ___" pattern for edge cases: empty states, missing data, errors, permissions, unusual setups, changes midway. |
| Some of the approaches we explored | **Approaches we explored** | Same. This matters even more for greenfield: show the early directions and why they changed. |
| What changed with the redesign (old → new table) | **What it made possible** (or drop the table) | One bold summary sentence. Only use the before/after table if there was a real "before" process; otherwise use a short duo or list of what users can now do. |
| What customers had to say | **What customers said / early adoption** | Only real feedback or adoption facts. Leave out if there are none. |
| What I took away | **What I took away** | Same. Reflect on building from zero: defining scope, making decisions without an existing product to learn from, and so on (only what's true). |

Building blocks to **skip** for greenfield: `phase old` / `phase new` and their `tag` labels, and `swap` (unless there's a real before process). Everything else carries over.

---

## 2. The story arc

The Contracts case study reads as one story:

> **What it is → who uses it → what was broken → the insight that changed the approach → the new experience, step by step (old vs new) → what happens when things go wrong → what we tried and dropped → before/after summary → proof (customer feedback) → what I learned.**

| # | Section (sidenav label) | Job it does | Contracts heading |
|---|---|---|---|
| 0 | Overview (hero) | Title, role, collaborators, 2-paragraph intro | *Simplifying contract management with AI* |
| 1 | Who uses it | Introduce the users before the problem | *Who uses Contracts?* |
| 2 | The problem | Show the old workflow and its pain, then one sharp insight | *Understanding the problem* |
| 3 | Bringing in AI (the key idea) | The turning point: the opportunity, framed as questions | *Bringing AI into the workflow* |
| 4 | The new experience | Walk through the product step by step, old vs new | *How the experience changed* |
| 5 | When AI falls short (edge cases) | Show the design thinking behind failure states | *Designing for when AI falls short* |
| 6 | Early approaches | Honest iteration: what we tried and why it changed | *Some of the approaches we explored* |
| 7 | What changed | One bold summary line plus an old→new table | *What changed with the redesign* |
| 8 | What customers said | Real feedback as proof | *What customers had to say* |
| 9 | What I took away | Personal reflection, ending on one big takeaway | *What I took away* |

Headings are short, sentence case, with no trailing full stop. Most read as a plain description ("Understanding the problem") or a question ("Who uses Contracts?").

---

### 0. Hero / overview

- **Title:** the outcome, not the feature. *"Simplifying contract management with AI."*
- **Facts row (2 items):** `My role: Product Design` · `Collaborators: Akkshaya Varkhedi (PM) · Engineers`. Up to 3 items fit in one row.
- **Intro, 2 short paragraphs:**
  1. What the product is, in one sentence.
     > Contracts helps companies create, send, and manage personalized sales compensation agreements.
  2. What I did, and the key focus.
     > I worked on redesigning the end-to-end experience, replacing a manual, DocuSign-based workflow with a simpler, AI-powered one. A key focus was reducing repetitive work while giving admins control over AI-fetched information.

### 1. Who uses it

Three persona cards, each with an icon, a name and one sentence about what they do.

- **Admins**: People who create contract templates, prepare and send contracts, and track their progress.
- **Salespeople**: Employees who receive contracts containing their sales targets, commissions, and other compensation details.
- **Other recipients**: People like reporting managers or compensation admins who may also need to review or sign contracts.

### 2. Understanding the problem

Flow: how I researched it → the old workflow as numbered steps → a visual of the old flow → **one pull-quote insight** → wider research → reframing.

- Opener: *"I started by reviewing the existing Contracts workflow and customer feedback to understand how contracts were created and sent."*
- Context, ending with *"…To send contracts, admins still had to:"*
- **Numbered steps (5)**, each a bold action plus one line:
  1. **Set up the contract in DocuSign.** Upload the document and add the required fields.
  2. **Download a spreadsheet.** Get a CSV containing all the fields to be filled.
  3. **Prepare the data manually.** Collect each salesperson's details, recipient emails, and email content.
  4. **Bring the data back into Everstage.** Import the prepared information and make it available as a Datasheet.
  5. **Load and send contracts.** Select the Datasheet and send contracts without previewing the completed documents.
- Animation of the old workflow, with the caption *"The old workflow: from DocuSign to spreadsheets and back to Everstage, with a lot of manual work in between."*
- **Pull quote (the core insight):**
  > The biggest problem was that much of this information already existed in Everstage, yet admins had to manually collect and re-enter it.
- Sub-heading *"Understanding how customers worked"*: input from customer-facing teams. It ends with the reframe: *"…simplifying how admins collected data wasn't enough. We needed to rethink the entire process."*

### 3. The turning point (the key idea)

A short section built from **question blocks**. Each block has a small lead-in line plus a big question.

- Context: *"Around this time, engineering was developing Eva, Everstage's AI assistant…"*
- Question block: *This opened up a new possibility:* → **What if admins could simply describe the information they needed instead of manually choosing where to get it?**
- One line on how it works.
- Question block: *But this raised another question:* → **How could admins verify the information and handle incorrect or missing values?**
- Closing line that sets up the rest of the story: *"A key part of the design was making AI useful while keeping admins in control."*

### 4. How the experience changed (the main body)

The product walked through as **numbered parts (01–05)** in the order the user experiences them. Each part has:

1. `01` plus a part title (e.g. *Creating a reusable template*).
2. One line on what this step is for.
3. **Old experience**, labelled with a tag: what it was, with the pain point in **bold**, plus a screenshot (the old UI, sometimes with the problem circled in red).
4. **New experience**, labelled with a tag: what changed and why, with the key change in **bold**, plus a recording of the new UI.
5. Optional extras: more recordings with one-line explanations, a small label like *"More ways to fill placeholders"*, numbered sub-steps, or a two-column "duo" for small features.

The Contracts parts:

| Part | Old (pain, in bold) | New (change, in bold) |
|---|---|---|
| 01 Creating a reusable template | had to manually add the actual recipients when sending contracts | we made this automatic ("Salesperson's manager") |
| 02 Building the template | they still had to manually prepare and upload the values for each salesperson | describe what each placeholder needs · choose from commonly used placeholders |
| 03 Previewing values before saving | manually fill in the values for each salesperson (CSV) | let Eva fetch the required information · preview the values for a few salespeople · preview how the actual contract looks |
| 04 Preparing and sending envelopes | manually prepare a spreadsheet | 4 numbered sub-steps: Select recipients → Review the values → Customize emails → Review and send |
| 05 Managing and tracking | (no old/new) | a duo: **Contracts page** / **Track sent contracts** |

Each old→new pair follows the pattern **"Previously, admins had to ___. Since ___, we ___."** The reason for the change ties back to the core insight ("Since Everstage already knows who each salesperson's manager is…").

### 5. Designing for when things go wrong

This is what makes the case study stand out: it shows thinking beyond the happy path.

- Framing: *"Eva won't always get it right. It may need more context, the data may not exist, or the lookup may fail. Instead of assuming AI would always work, we designed for each of these cases."*
- Numbered cases, each with a **"When ___"** title, the solution, and an optional example:
  1. **When Eva fetches the wrong value**: Admins can ask Eva to use a different source or recalculate the value. *For example, "Divide the variable pay by 10," then regenerate.*
  2. **When Eva can't fetch a value**: edit, paste from a spreadsheet, or look up from a Datasheet. A detail that shows rigour: *"Multiple matches are flagged instead of silently picking one."*
  3. **When values become outdated**: Missing and outdated values are flagged, with filters and a refresh option.
- Screenshots after each case.

### 6. Approaches we explored

Honest iteration. Each item is a **question title**, what we tried first and why it didn't work, then the decision (marked as the solution).

1. **One flow or reusable templates?** We first tried one combined flow. But a mid-year joiner would mean recreating everything. *So we kept templates separate…*
2. **How to fill contract details** Manual source mapping needed many filters and calculations. *The AI being built alongside the redesign opened up a simpler approach.*

Each one is backed by an early-exploration screenshot.

### 7. What changed with the redesign

- **One bold summary sentence**, then the payoff:
  > **Admins no longer prepare the same information every time they send contracts.** They set things up once, let Eva fill in the values, and stay in control when it gets something wrong.
- A **side-by-side table**: *Older experience: Manual and repetitive* vs *New experience: AI-assisted and reusable*. It has 5 rows matching the 5 old steps from section 2, so the story comes full circle.

### 8. What customers had to say

- One line of context: *"Here's some of the feedback we heard from customers after they started sending contracts with the new experience."*
- 2 screenshots of real feedback (Slack post, notes), with names and companies blurred and a caption saying so.
- If no real feedback exists, **leave this out**. Never write placeholder quotes.

### 9. What I took away

- 3 short paragraphs of personal reflection. Bold the key phrases:
  - *"This project changed how I think about designing experiences where AI is part of the product."*
  - *"What interested me most wasn't just what AI could do, but **what happens when it gets something wrong.**"*
  - Why it mattered in this domain: *"…**even a small mistake could matter.**"*
- A **closing statement** in a highlighted block, with 2–3 italic phrases:
  > My biggest takeaway was that designing AI-powered experiences isn't just about making things easier. It's also about helping people *understand what's happening*, *build trust*, and *stay in control.*

---

## 3. Voice and writing rules

- **First person, warm, plain.** Use "I" for my decisions and "we" for the team. Write as if explaining to a friend who's a designer.
- **Short sentences, short paragraphs** (1–3 sentences). No walls of text.
- **No jargon or buzzwords.** Avoid words like "leveraged", "seamless", "delightful", "robust", "synergy" and "empower". Explain product terms the first time (*"a Datasheet (a table of records)"*).
- **Concrete over abstract.** Use real examples in quotes (*"This salesperson's Q2 sales target"*, *"Divide the variable pay by 10"*).
- **Bold sparingly.** Bold only the one key pain or change per paragraph.
- **Every change has a reason.** Say why it was done, not just what was done.
- **Honest.** Show what didn't work. Don't overclaim impact. No made-up metrics.
- **Spelling and punctuation:** match the Contracts page (*customize*, *personalized*, *realise*). The body copy uses no em dashes; it uses commas and full stops instead.
- **Headings:** sentence case, no trailing full stop.
- **Captions and alt text:** describe what's actually on screen, in one sentence.

---

## 4. Page building blocks

Copy `v2/contracts/final.html` as the starting file. It uses `../style.css`, `../case.css` and `../final-case.css`, with `<body class="case blog neel">`. The blocks:

| Block | Markup |
|---|---|
| Section | `<section class="sec" id="…"><h2 class="cs-h2 reveal">…</h2>…</section>` (plus a matching link in `nav.sidenav`) |
| Body text | `<div class="prose reveal"><p>…</p></div>` |
| Sub-heading | `<h3 class="cs-h3 reveal">…</h3>` |
| Facts row | `<dl class="cs-facts"><div><dt>My role</dt><dd>…</dd></div>…</dl>` |
| Personas | `<ul class="personas"><li><span class="ps-ic">svg</span><h3 class="ps-name">…</h3><p>…</p></li></ul>` |
| Numbered steps | `<ol class="flow-steps"><li><span class="fs-n">1</span><div><b>…</b><p>…</p></div></li></ol>` |
| Pull quote | `<p class="q reveal">…</p>` |
| Question block | `<div class="qb reveal"><p class="qb-l">lead-in</p><p class="qb-q">question</p></div>` |
| Numbered part | `<div class="part reveal"><h3 class="cs-h3 part-h"><span class="pn">01</span>Title</h3>…</div>` |
| Old / new phase | `<div class="phase old">` / `<div class="phase new">` with `<p class="tag"><em>Old experience</em><span class="ln"></span><span class="tg-part"><b>01</b>Title</span></p>` |
| Key phrase | `<strong class="k">…</strong>` |
| UI screenshot or video | `<figure class="shot-ui"><img …> or <video autoplay muted loop playsinline …></figure>` |
| Small label | `<p class="step-l">…</p>` |
| Two features | `<ul class="duo"><li><b>…</b><p>…</p></li>…</ul>` |
| Edge case / approach | `<div class="case-row stack lite [appr] reveal"><h3 class="case-t"><span class="pn">01</span>…</h3><div class="prose"><p>…</p><p class="sol">solution</p><p class="eg">example</p></div></div>` |
| Old → new table | `<figure class="swap">` with `sw-head` and `<li><span class="sw-old">…</span><span class="sw-arrow">→</span><span class="sw-new">…</span></li>` |
| Feedback | `<figure class="quotes paper"><div class="q-card [dark]"><img …></div><figcaption>…</figcaption></figure>` |
| Closing statement | `<figure class="closer"><span class="closer-mark"></span><p>… <em>…</em></p></figure>` |
| Footer "Up next" | Point it to the next case study's `final.html`, and add the new page to the chain. |

Assets go in `assets/mbo/`: compressed `.webp` for screenshots, and `.mp4` plus a `-poster.jpg` for recordings.
