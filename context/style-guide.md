# Quix Style Guide

This guide defines writing conventions, formatting standards, and editorial guidelines for all Quix content.

## Reference Documents

This style guide must be read alongside:

- **`/Users/bugs/Claude/Claud GTM Project files/quix-terminology-glossary.md`** — Authoritative definitions for all Quix and industry terms. When in doubt about a term, consult this document first. Do not use alternative terms for anything defined there.
- **`/Users/bugs/Claude/Claud GTM Project files/AI_Writing_Anti-Patterns_to_Avoid.md`** — Full catalogue of AI writing tells to eliminate. The banned words and constructions sections below are drawn from this document; the source file is more comprehensive and should be consulted directly when reviewing content.
- **`/Users/bugs/Claude/Claud GTM Project files/AI_B2BWriting_AntiPatterns_LU_2026_02_23.xlsx`** — B2B-specific anti-patterns. Cross-reference when writing or reviewing any B2B-facing content.

---

## Grammar & Mechanics

### Capitalization

**Headlines & Subheadings**:
- Sentence case (Only capitalize first word and proper nouns)
- Example: "Why test data without configuration context is useless"
- Exception: Proper nouns and product names always capitalized (Quix, Python, Kafka, etc.)

**Product Names**:
- Quix: Always capitalized
- Quix Cloud: Always capitalized as two words
- Python: Always capitalized (it's a proper noun)
- Kafka, Kubernetes, Docker: Always capitalized

**Industry Terms**:
- test run (lowercase — the execution instance of a test)
- test rig (lowercase)
- configuration context (lowercase)
- MIL, SIL, HIL (always caps — standard engineering acronyms)
- DACQ (always caps)
- RSS (always caps)
- API (always caps)
- SQL (always caps)

### Numbers

**When to Spell Out**:
- Spell out: one through nine
- Use numerals: 10 and above
- Exceptions:
  - Percentages: Always use numerals (5%, 50%)
  - Money: Always use numerals ($5, $500)
  - Measurements: Always use numerals (5 GB, 50 MB, 30 minutes)
  - Statistics and benchmarks: Always use numerals for scannability

**Large Numbers**:
- Use commas: 10,000 not 10000
- Spell out million/billion: "1.2 million" not "1,200,000"
- Avoid rounding that removes meaning: "17 labs at capacity" beats "nearly 20 labs"

### Punctuation

**Oxford Comma**:
- Yes: always use (A, B, and C)
- Reason: Technical lists require precision; ambiguity is a cost

**Em Dashes**:
- Use sparingly — they have become an AI writing signature
- Prefer restructuring the sentence over reaching for an em dash
- When used: no spaces on either side (—)
- Reserve for genuine parenthetical asides where a comma or colon won't work

**Quotation Marks**:
- Use curly (smart) quotes in published content
- Use straight quotes in code and URLs

**Ellipses**:
- Three dots: ...
- No spaces before or after
- Use only for omitted text in direct quotes; avoid as stylistic devices

### Abbreviations & Acronyms

**First Use**:
- Spell out on first use, acronym in parentheses
- Example: "Model-in-the-Loop (MIL) simulation..."
- Exception: Terms the audience uses daily without thinking — MIL, SIL, HIL, DACQ, API, SQL — do not define these

**Common Engineering Acronyms**:
- MIL: Model-in-the-Loop
- SIL: Software-in-the-Loop
- HIL: Hardware-in-the-Loop
- DACQ: Data Acquisition
- ADAS: Advanced Driver Assistance Systems
- OBD: On-Board Diagnostics

**Latin Abbreviations**:
- Avoid e.g., i.e., etc. in body copy — use "for example", "that is", "and so on"
- Acceptable in parenthetical asides only where space is genuinely constrained

---

## Word Choice & Usage

### Technical Terminology

All Quix-specific terms, V-model terminology, data pipeline terms, and engineering acronyms are defined authoritatively in **`quix-terminology-glossary.md`**. Always check there before using a term. Key decisions:

- **test run** not "test" — a test is the definition; a test run is the execution instance
- **configuration context** not "metadata" — metadata is too generic; configuration context names the precise problem
- **MIL / SIL / HIL / DIL** — always caps, no need to spell out for this audience
- **DACQ** — always caps, no need to define
- **analytics-ready data** — the glossary term; prefer over "processed data" in product contexts
- **data pipeline** — for a specific sequence of processing steps; use "data infrastructure" for the full platform
- **Quix Cloud** — the managed platform; "Quix" alone for the company and product generally
- **environment** — has two distinct meanings in context: (1) test environment / test rig, (2) Quix dev/staging/production environments. Be precise about which sense is intended

### Preferred Terms

**Say This** → **Not That**:
- "engineers" → "users" (Quix audience are practitioners, not generic users)
- "configuration context" → "metadata" (too generic)
- "test run" → "test" (a test is the definition; a test run is the execution instance)
- "Python-native" → "Python-based" (native signals it's the foundation, not an afterthought)
- "R&D cycle time" → "development speed" (too vague for an engineering audience)
- "data pipeline" → "data infrastructure" (when referring to the full platform, not a specific pipeline)
- "analytics-ready data" → "processed data" (analytics-ready signals usability, not just storage)
- "production-grade" → "enterprise-grade" (production-grade is engineering language; enterprise-grade is sales language)
- "book a call" → "book a walkthrough" or "book a demo" (be specific about what happens)
- "data" (plural) → acceptable as singular in technical contexts ("the data shows")

### Words to Avoid

The complete list of banned words is in **`AI_Writing_Anti-Patterns_to_Avoid.md`**. The key categories:

**AI writing tells — never use**:
- delve, tapestry, paramount, meticulous, groundbreaking, game-changing, transformative, seamless, holistic, crucially, remarkably, exemplifies, comprehensive, intricate

**Banned verbs**:
- leverage, unlock, harness, revolutionise/revolutionize, elevate, captivate, underscore, highlight, showcase, evolve/emerge/shift (as in "shifting landscape")

**Gesture verbs** (describe emphasis without adding meaning):
- underscores, highlights, showcases, delves into

**Banned adjectives and adverbs**:
- swift, meticulous, adept (precision gestures)
- extremely, very, really, significantly, remarkably (vague intensifiers — if something matters, say why)
- groundswell, liminal (pretentious)

**Dramatic pain-point language** (be specific about what actually goes wrong):
- struggle, desperate, pain — replace with exact descriptions

### Banned Constructions

The complete list is in **`AI_Writing_Anti-Patterns_to_Avoid.md`**. The most common violations:

**Rhetorical patterns**:
- "It's not X, it's Y." / "This isn't X. It's Y." — get to the point
- "No X. No Y. Just Z." — same problem
- Short statement + colon: "The result: a 30% improvement." — write a full sentence
- Mid-sentence self-questioning: "The results were clear. And the implications? Even clearer."
- "Nobody talks about this" / "Here's an unpopular opinion" — counter-narrative clichés
- Chains of gerund-led sentences stacking pain points — pick one specific example, go deep
- Politician-style quote setups: "A systems engineer I spoke to recently said something that stuck with me..."
- Fake profundity: stacking short dramatic sentences for a TED-talk effect
- Excessive tricolons: listing things in threes constantly is an AI pattern; vary list lengths

**Comparative phrases to avoid**:
- "X falls short..."
- "X stands out as..."
- "This is where X becomes essential."
- "Play a significant role in shaping..."
- "Aims to explore..."

**Banned metaphor frames**:
- "A tapestry of..."
- "A treasure trove of..."
- "Embark on a journey..."
- "Master the art of..."
- "A testament to..."

### Banned Introductory Phrases

- "In the rapidly evolving landscape..."
- "In today's digital world / digital age..."
- "In the realm of..."
- "In the dynamic world of..."
- "In the quest for innovation..."
- "In the annals of..."
- "In this article/guide/blog post..."
- "It is important to note that..."

### Banned Transitional & Concluding Phrases

- "In conclusion..." / "In summary..."
- "Moreover" / "Furthermore" / "In addition" — if a thought follows logically, let it follow
- "It goes without saying..."
- "At the end of the day..."
- "Needless to say..."
- "But here's the kicker..." / "But there's a catch..."

### LinkedIn Content

LinkedIn posts for Quix have additional constraints — see **`AI_Writing_Anti-Patterns_to_Avoid.md`** for the full guidance and examples of what to avoid. Summary:

- No "hidden secret nobody talks about" framing
- No micro-rhetorical questions: "The result? A whole new world."
- No "Claim + Here's how:" patterns
- No "broetry" — dramatic single-line spacing, stacked fragments, tech-bro energy
- The audience is professional mechanical and systems engineers, not startup founders

### Inclusive Language

- Use "they" for gender-neutral singular references
- "Engineers" not "engineering teams" when referring to individuals
- Avoid idioms that may not translate globally (especially for automotive OEM audiences in Germany, Japan, US)

---

## Formatting Standards

### Text Formatting

**Bold**:
- Use for: Key concepts and terms on first introduction, important technical distinctions
- Avoid overuse — if everything is bold, nothing stands out
- Example: "**Configuration context** — the hardware state, software version, and calibration settings that produced a test run — is what makes measurement data trustworthy."

**Italics**:
- Use for: Titles of external publications, emphasis (sparingly), introducing a term being defined
- Avoid for decoration

**Underline**:
- Reserve for hyperlinks only

**ALL CAPS**:
- Acronyms only (MIL, SIL, API, SQL)
- Never for emphasis

### Lists

**Bulleted Lists**:
- Use for: Non-sequential items, features, requirements, options
- Capitalize first word of each item
- Period if complete sentence, no period if fragment
- Parallel structure throughout (all sentences or all fragments, not a mix)
- Three to six items: fewer usually works better as prose; more than six needs restructuring

**Numbered Lists**:
- Use for: Sequential steps, ordered priorities, installation instructions
- Same capitalization and punctuation rules as bullets

**Nested Lists**:
- Maximum two levels deep
- Use sparingly — complex nesting usually signals the content needs restructuring

### Links

**Anchor Text**:
- Descriptive: tell the reader exactly where they're going
- ✅ "See how configuration linking works in practice"
- ✅ "Read the Viessmann case study"
- ❌ "Click here"
- ❌ "Read more"
- ❌ "Learn more" (acceptable as last resort, not first choice)

**Link Formatting**:
- External links: open in new tab
- Internal links: same tab

### Code & Technical Elements

**Inline Code**:
- Use backticks for: code snippets, command names, file paths, specific parameter names
- Example: "Your pipeline runs in a `Docker` container managed by Quix."

**Code Blocks**:
- Use for: Multi-line code, configuration examples, pipeline definitions
- Always include language identifier for syntax highlighting

### Callout Boxes

**When to Use**:
- Genuine warnings or prerequisites that affect the outcome
- Specific technical constraints engineers need to know before proceeding
- Not for general emphasis or promotional messages

---

## Content Structure

### Article Introduction

**Standard Structure** (150–250 words):
1. **Open with the problem** (2–3 sentences): A specific, recognisable situation — not a landscape overview
2. **Name the consequence** (1–2 sentences): What it costs — time, lab capacity, decision quality
3. **State what this covers** (1–2 sentences): What the reader will be able to do by the end
4. No need for a credibility statement — the specificity does that work

**Keyword Placement**:
- Primary keyword in first 100 words, integrated naturally
- Do not force it into the opening sentence if it sounds awkward

### Section Length

- **Minimum**: 150 words per section
- **Maximum**: 400 words per section (break into subsections if longer)
- **Ideal**: 200–300 words per main section

### Conclusion

**Standard Structure** (100–200 words):
1. **What this means in practice** (2–3 sentences): The so-what, stated plainly
2. **One clear next step** (1–2 sentences): What the reader should do next
3. **One CTA** (1 sentence): Specific — "Book a 30-minute walkthrough" not "Get started today"

---

## SEO-Specific Style

### Meta Titles

- 50–60 characters including spaces
- Include primary keyword
- No ending punctuation
- Sentence case
- Lead with the problem or outcome, not the brand name

### Meta Descriptions

- 150–160 characters including spaces
- Include primary keyword
- Include a specific call-to-action
- End with a complete thought

### URL Slugs

- Lowercase only
- Hyphens between words
- Include primary keyword
- 3–5 words ideal
- Format: `/blog/primary-keyword-phrase`

### Alt Text

- Describe what the image shows, accurately
- Include keyword naturally if genuinely relevant
- 125 characters or less
- No "image of" or "screenshot of" (implied)
- For engineering diagrams: describe the system, not just "diagram"

---

## Dates & Time

**Date Format**: Month DD, YYYY — January 15, 2025

**Time**: 12-hour format — 3:00 p.m. (with periods in a.m./p.m.)

**Time Zones**: Spell out — "3:00 p.m. Eastern Time" not "3:00 p.m. ET"

---

## Statistics & Data

### Citing Sources

- Always cite statistics with named sources
- Format: "According to [Source], [statistic]."
- Link to original source when possible
- Include year: "In 2024, [statistic]..."
- Prefer named customers over anonymous ones: "Viessmann" beats "a leading European manufacturer"

### Presenting Numbers

- Round for readability, but not so far it loses meaning: "1.2 million" yes, "about a million" no
- Use % symbol: 17% not "17 percent"
- Use $ for money with no space: $500
- Always use commas: 10,000 not 10000

---

## Images & Media

### Screenshots

- Crop to show only the relevant interface element
- Add annotations (arrows, highlights) if the key area is not immediately obvious
- Alt text should describe what the screenshot shows, including the relevant UI element

### Diagrams & Architecture Charts

- Keep design clean — no decorative elements that add no information
- Label every component that is referenced in the surrounding text
- Alt text: describe the system and data flow, not just "architecture diagram"

---

## Quix-Specific References

### Product References

- "Quix" (not "the Quix platform" unless needed for clarity on first mention)
- "Quix Cloud" for the managed cloud offering
- "Quix pipeline" for a specific data pipeline built in Quix
- Do not say "our platform" in content intended to rank — use "Quix"

### Competitor References

- Name competitors directly when relevant and factually accurate
- Never disparage; describe what they do and where the fit differs
- Focus on genuine differences in capability or approach, not superiority claims
- Common comparisons: Siemens Polarion, Dassault Enovia, ETAS INCA, custom IT builds

### Customer References

- Always use the customer's actual name when they have agreed to be referenced
- Do not anonymise as "a leading OEM" if a named reference is available — specificity builds credibility
- Include role and organisation for quotes: "— Senior Systems Engineer, Viessmann"
- **Cleared for public reference**: Viessmann, Ju:niz, Cloud NC, Williams Racing, SMS Group, Fifer Vacuum, Alpine F1 Racing Team, Audi Formula 1 Racing Team
- **NOT cleared for public reference**: Gulfstream — do not name in any published content. Use "a major US aerospace OEM" if the evidence is needed

---

## Accessibility

### Screen Reader Friendly

- Descriptive link text always — never "click here"
- Alt text for all images
- Proper heading hierarchy (H1 → H2 → H3, no skipping)

### Plain Language

- Technical vocabulary is fine; jargon without context is not
- Define terms when introducing them in a new context (not for daily-use acronyms like MIL/SIL/HIL)
- Short sentences and paragraphs — dense text is a barrier, not a signal of depth

---

## Voice & Tone Reminders

### Core Voice

Engineer-to-engineer. Direct, technically fluent, no hand-holding. Like a senior engineer from the McLaren F1 data team having a straight conversation with an R&D engineer at an automotive OEM. Confident, knowledgeable, straight to the point.

### Tone by Content Type

- **How-to guides & walkthroughs**: Precise, methodical — "Here's exactly what you'll need before you start."
- **Strategy & industry content**: Authoritative, occasionally direct challenges to bad norms — "Data warehouses are where good decisions go to die."
- **Product & feature releases**: Benefit-led, technically specific — "Git integration means your pipeline code lives alongside your test configuration."
- **Company & culture**: Warm, personal, story-driven — but never fluffy

---

## Editing Checklist

Before publishing any content:

**Grammar & Mechanics**:
- [ ] Spelling checked (British or American — consistent throughout)
- [ ] Grammar checked
- [ ] Oxford comma used
- [ ] Em dashes used sparingly
- [ ] Numbers formatted correctly

**Voice**:
- [ ] No banned words or constructions
- [ ] No banned introductory phrases
- [ ] Specific over general throughout
- [ ] Active voice dominant
- [ ] No gerund chains stacking pain points

**Structure**:
- [ ] Opens with the problem, not the product
- [ ] Subheadings are statements, not labels
- [ ] One clear CTA at the end
- [ ] Conclusion is practical, not a summary of what was just said

**SEO**:
- [ ] Primary keyword integrated naturally in first 100 words
- [ ] Meta title 50–60 characters
- [ ] Meta description 150–160 characters
- [ ] Internal and external links included
- [ ] All images have alt text

**Quality**:
- [ ] Factually accurate — no unsubstantiated claims
- [ ] Sources cited for all statistics
- [ ] No broken links
- [ ] Provides genuine value to the reader

---

**Style Guide Version**: 1.1 (adapted for Quix)
**Last Updated**: March 2026

This is a living document. When you encounter a style question not covered here, make a decision, document it, and add it.
