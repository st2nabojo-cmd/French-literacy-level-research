# CLAUDE.md — Nabojo Story Pipeline Wiki Schema

> This file is the operating manual for the LLM agent maintaining this wiki.
> Read this file completely at the start of every session before doing anything else.

---

## Project Context

This wiki is the **story pipeline knowledge base** for **Nabojo**, a French EdTech startup that creates interactive digital books for French children on a dedicated e-reader. The wiki supports an AI-assisted content production pipeline.

The wiki encodes two distinct bodies of knowledge, organized by reading tier:

**Matter** — The "what" of a story: permissible and preferred topics, narrative types, themes, character archetypes, emotional and moral range, French cultural considerations. Matter knowledge feeds the **blueprint/concept stage** of the pipeline, where story premises are developed. It is tier-specific. Specific story topics may be chosen manually by a human editor, but all other Matter elements (themes, dos/don'ts, narrative types, emotional range) are tier-defined.

**Manner** — The "how" of writing: sentence structure norms, vocabulary level, narrative pacing, grammar constraints, interactive choice mechanics, engagement techniques, what to avoid. Manner knowledge feeds the **manuscript/writing stage** of the pipeline. It is tier-specific.

The wiki is used by **two kinds of reader simultaneously**:
- **Machine (AI prompts):** Pages must be dense, precise, and structured so that relevant sections can be extracted and injected directly into pipeline prompts.
- **Human (writers, editors, prompt engineers):** Pages must also be readable and self-explanatory to a non-specialist team member.

Every page must serve both readers. This means: precise frontmatter (machine-parseable), clear section headings (machine-extractable), and plain-language prose (human-readable).

**The four literacy tiers:**

| Tier | Ages | French school level |
|------|------|---------------------|
| Tier 1 | 6–7 | CP, CE1 |
| Tier 2 | 7–8 | CE1, CE2 |
| Tier 3 | 8–10 | CE2, CM1 |
| Tier 4 | 10–12 | CM1, CM2, 6e |

The wiki is used by multiple collaborators via GitHub sync. Write clearly and never assume the reader has full context.

---

## Architecture — Three Layers

### Layer 1: Raw Sources (`raw/`)
**Immutable.** The LLM reads from this layer but **never** modifies it.

```
raw/
├── articles/       # Blog posts, news articles, web clips (markdown)
├── papers/         # Research papers, academic PDFs
├── transcripts/    # YouTube transcripts, podcast notes, interviews
├── github/         # Auto-pulled from GitHub repo (collaborator uploads)
└── assets/         # Images, diagrams referenced by sources
```

### Layer 2: The Wiki (`wiki/`)
**LLM-owned.** The agent writes, updates, and maintains everything here.

```
wiki/
├── tiers/
│   ├── tier1/
│   │   ├── tier1-matter.md     # Matter profile for ages 6–7
│   │   └── tier1-manner.md     # Manner guidelines for ages 6–7
│   ├── tier2/
│   │   ├── tier2-matter.md
│   │   └── tier2-manner.md
│   ├── tier3/
│   │   ├── tier3-matter.md
│   │   └── tier3-manner.md
│   └── tier4/
│       ├── tier4-matter.md
│       └── tier4-manner.md
├── sources/        # One summary page per ingested research source
├── concepts/       # Cross-tier frameworks and reusable principles
├── index.md        # Master catalog of all wiki pages
├── log.md          # Chronological record of all operations
└── overview.md     # Pipeline health summary and research synthesis
```

**Retired directories (do not create new pages in):** `wiki/entities/`, `wiki/comparisons/`

### Layer 3: This Schema (`CLAUDE.md`)
**Co-evolved.** The human and LLM update this together as the wiki matures.

---

## Page Types & Frontmatter

Every wiki page MUST start with YAML frontmatter. Section headings must match exactly as specified — they are used for machine extraction.

---

### Tier Matter Page (`wiki/tiers/tierN/tierN-matter.md`)

Singleton per tier. Updated as new sources are ingested; never deleted and re-created.

```yaml
---
type: tier-matter
tier: 1                    # integer 1–4
age_range: "6–7"           # "6–7" | "7–8" | "8–10" | "10–12"
school_level: "CP, CE1"    # French school levels for this age range
last_updated: YYYY-MM-DD
sources_count: 0
tags:
  - tier1                  # always include tier tag
  - matter                 # always include matter tag
status: draft              # draft | stable | needs-review
---
```

**`status` field:**
- `draft` — fewer than 3 sources informing the page
- `stable` — well-grounded, no pending updates
- `needs-review` — a new source has been ingested that affects this page but the page has not yet been updated

**Body sections (exact headings, in order):**

```markdown
## Tier Overview

One paragraph: cognitive stage, reading independence, school context, social-emotional development.
Orients both humans and AI to who this tier is.

## Permitted Topics

Narrative subject matter that is appropriate and encouraged for this tier.
Structured list with brief rationale per category:
- **Topic category** — rationale for why it works at this tier

This section is injected into blueprint-stage prompts as the topic permission set.

## Topics to Avoid

Subject matter that is inappropriate for this tier. Be specific — not just "violence" but
"depictions of physical harm with realistic consequence." Include the reason.
Same format as Permitted Topics but framed as exclusions.

## Narrative Types

Story structures that work for this tier. List by name with a one-sentence explanation of why:
- **Narrative type** — why it fits this tier

## Character Archetypes

Protagonist and supporting character types that resonate at this tier, with age-appropriateness rationale:
- **Archetype** — rationale

## Emotional and Moral Range

What emotional experiences and moral questions this tier can handle:
- **Emotions accessible:** [list]
- **Emotions to avoid:** [list]
- **Moral complexity:** [level — e.g., simple binary right/wrong, light ambiguity if resolved]
- **Taboo topics:** [list]

## French Cultural Considerations

Culturally specific content considerations for French children at this age:
- French school calendar events (la rentrée, les vacances de Toussaint, etc.)
- Geographic and regional references appropriate to this age
- French social contexts (cantine, récréation, marché, etc.)
- What to avoid: imported cultural references that feel foreign to a French child

## Open Questions / Research Gaps

Use `> [!question]` callouts for unresolved questions. Updated by /lint.

## Sources

Wiki-links to all source pages that inform this Matter page:
- [[source-slug]] — one sentence on what it contributes
```

---

### Tier Manner Page (`wiki/tiers/tierN/tierN-manner.md`)

Singleton per tier. Primary input to the manuscript/writing stage prompt.

```yaml
---
type: tier-manner
tier: 1                    # integer 1–4
age_range: "6–7"
school_level: "CP, CE1"
last_updated: YYYY-MM-DD
sources_count: 0
tags:
  - tier1
  - manner
status: draft              # draft | stable | needs-review
---
```

**Body sections (exact headings, in order):**

```markdown
## Tier Writing Profile

One paragraph: what readers at this tier can decode, what their working memory can hold,
what pace feels right, what makes them abandon a book. Human-facing orientation paragraph;
also serves as framing context when injected into a prompt.

## Sentence Structure

Precise, constrainable rules for sentence construction. Use a table plus notes:

| Dimension | Guideline | Rationale |
|-----------|-----------|-----------|
| Average sentence length | X–Y words | [source-based rationale] |
| Maximum sentence length | N words | [rationale] |
| Subordinate clause nesting | Max N levels | [rationale] |
| Preferred construction | SVO dominant | [rationale] |

Additional notes on permitted vs. prohibited constructions.

## Vocabulary Level

Include an embedded spec block formatted for direct prompt injection:

```yaml
vocabulary:
  base_register: A1 | A2 | B1 | B2   # CECRL level
  max_new_words_per_page: N
  new_word_introduction: always in narrative context, never as definition
  avoid: [latinate abstractions, technical jargon]
  favour: [concrete nouns, action verbs, sensory adjectives]
```

Follow the block with prose explaining what counts as a "new word" at this tier
and how to signal new words without breaking immersion.

## Narrative Pacing

- **Scene/chapter length:** [word count range] — rationale
- **Beats per scene:** [number] — what counts as a beat
- **Cliffhangers:** [yes / no / conditional] — frequency guidance
- **White space:** guidance on paragraph breaks and dialogue formatting
- **Exposition ratio:** maximum % of any scene that can be pure description

## Grammar Rules and Constraints

Constructions explicitly permitted or prohibited, organized by category:
- **Tense:** primary narrative tense; what to avoid
- **Passive voice:** permitted / avoid / use sparingly — rationale
- **Negation:** which negation forms are appropriate at this tier
- **Relative clauses:** guidance
- **Register:** tu/vous norms in dialogue; formal vs. familiar

## Engagement Techniques

Techniques effective and appropriate for this tier:
- **Direct address** — whether "Et toi, qu'est-ce que tu ferais?" works here
- **Repetition with variation** — accumulative sentence patterns, refrain structures
- **Humour type** — wordplay / situational / absurdist — what lands at this tier
- **Tension mechanics** — how to create age-appropriate stakes
- **Chapter hooks** — structural techniques for chapter endings

## Interactive Choice Mechanics

Nabojo-specific. Governs how branching choices are written at this tier:
- **Choice point frequency:** every N scenes or N pages
- **Number of choices per point:** 2 or 3 — rationale (cognitive load)
- **Choice framing language:** French-language templates for presenting choices
- **Choice consequence weight:** Light (cosmetic) / Moderate (changes scene) / Heavy (changes ending)
- **Prohibited choice types:** choices requiring knowledge the reader may lack; choices with a
  clearly "wrong" answer that causes distress

## What to Avoid

Specific writing patterns that consistently fail at this tier:
- **Pattern** — why it fails at this tier

## Open Questions / Research Gaps

Use `> [!question]` callouts for unresolved questions. Updated by /lint.

## Sources

Wiki-links to all source pages that inform this Manner page:
- [[source-slug]] — one sentence on what it contributes
```

---

### Source Page (`wiki/sources/YYYY-MM-DD-slug.md`)

```yaml
---
type: source
title: "Human-readable title of the source"
slug: YYYY-MM-DD-short-slug
date_ingested: YYYY-MM-DD
source_type: paper | report | curriculum-doc | pedagogy-guide | article | transcript | book | standard
original_path: raw/articles/filename.md
language: fr | en
url: "https://..."
authors:
  - "Author Name"
tiers_relevant:
  - 1
  - 2
pipeline_stage: matter | manner | both | general
tags:
  - literacy
  - tier1
key_claims:
  - "Claim 1 in one sentence"
  - "Claim 2 in one sentence"
confidence: high | medium | low
---
```

**Fields:**
- `tiers_relevant` — list of tier integers (1–4) this source informs. Empty `[]` for general methodology.
- `pipeline_stage` — `matter` (story content decisions), `manner` (writing execution), `both`, or `general`.
- `source_type` — use `curriculum-doc` for official curriculum documents (socle commun, etc.); `standard` for PIRLS, PISA, etc.

**Body structure:**
1. **Summary** — 3–5 sentence overview
2. **Key Findings / Arguments** — numbered list of main points
3. **Relevant Data** — statistics, benchmarks, quotes (with page/timestamp refs). French quotes must include English translation in square brackets.
4. **Tier Implications** — one subsection per tier in `tiers_relevant`, format: `### Tier N (Matter|Manner): [implication]`. This is the section the LLM reads when updating tier pages during ingest.
5. **Connections** — wiki-links to relevant tier pages (`[[tier1-matter]]`, `[[tier3-manner]]`) and concept pages
6. **Limitations / Bias** — caveats about the source
7. **Raw Quotes** — important verbatim passages with citation refs

---

### Concept Page (`wiki/concepts/concept-name.md`)

Create a concept page only when: a concept appears in **3+ sources** OR applies to **2+ tiers**. Otherwise, keep the finding in the source's Tier Implications section.

```yaml
---
type: concept
name: "Concept Name"
domain: literacy | pedagogy | interactivity | french-language | cognitive-development | narrative-craft | curriculum
applies_to_tiers:
  - 1
  - 2
pipeline_stage: matter | manner | both
tags:
  - [controlled vocabulary tags]
first_mentioned_in: YYYY-MM-DD-slug
sources_count: 0
last_updated: YYYY-MM-DD
---
```

**Body structure:**
1. **Definition** — clear, concise definition in one paragraph maximum
2. **Why This Matters for Nabojo** — frames the concept in terms of the pipeline: does it constrain Matter, Manner, or both? Which tiers are most affected?
3. **Tier-Specific Notes** — for each tier in `applies_to_tiers`, how the concept manifests at that tier. Use `### Tier N` subheadings if variation is significant.
4. **What Sources Say** — bullet per source: `[[source-slug]]: what it contributes`. Include `> [!warning]` for contradictions.
5. **Open Questions** — `> [!question]` callouts for unresolved points
6. **Connections** — links to tier pages and related concepts

---

## Conventions

### Wiki-Links
- Always use Obsidian-style `[[page-name]]` links (filename without extension)
- Tier pages: `[[tier1-matter]]`, `[[tier3-manner]]`
- Source pages: use the slug: `[[2026-04-22-eple-french-literacy-scale]]`
- Concept pages: use the filename: `[[vocabulary-acquisition-in-context]]`
- Link generously — every mention of a known tier page, source, or concept should be a wiki-link
- Wanted pages (links pointing at non-existent pages) are growth signals — use them deliberately
- Do not link to entity pages (retired)

### Tags — Controlled Vocabulary
All tags are lowercase and hyphenated. New tags must be documented here before use.

**Tier tags** (always include on tier pages; include on sources/concepts that are tier-specific):
`tier1`, `tier2`, `tier3`, `tier4`

**Pipeline stage tags:**
`matter`, `manner`

**Domain tags:**
`literacy`, `vocabulary`, `grammar`, `sentence-structure`, `narrative-structure`, `pedagogy`, `cognitive-development`, `french-language`, `french-curriculum`, `interactivity`, `choice-mechanics`, `character`, `theme`, `emotion`, `cultural-context`, `phonology`, `reading-motivation`

**Source quality tags:**
`peer-reviewed`, `official-report`, `curriculum-standard`, `expert-opinion`, `industry-report`, `anecdotal`

**Deprecated (do not use):**
`age-8-10`, `age-10-12`, `cycle-3`, `AI-writing`, `publishing`, `market-research`, `illustration`

### Language
- Wiki pages are written in **English** (team working language)
- French terms, curriculum references, and pedagogical concepts are kept in French with English translation in parentheses on first mention per page (e.g., "socle commun (national skills framework)")
- French example sentences and choice framing templates in Manner pages remain in French — never translate them; they model French prose
- French quotes in source pages must include an English translation in square brackets immediately after

### Callouts
Use Obsidian callout syntax:
- `> [!warning]` — Contradiction between sources
- `> [!question]` — Open research question or gap
- `> [!tip]` — Actionable insight ready for pipeline use
- `> [!info]` — Background context for interpretation
- `> [!pipeline]` — Content written specifically for direct prompt injection. No framing prose — just the rule, constraint, or list. Copy-paste ready into a pipeline prompt without editing.

---

## Operations

### `/ingest` — Process a new source

**Default mode is interactive.** Ingest sources one at a time. Batch mode is the exception.

1. Read the raw source file completely.
2. **Discuss with the user** before proceeding: what is new, surprising, or contradicts existing tier page content. Identify which tiers and pipeline stage(s) this source is relevant to. Confirm `tiers_relevant` and `pipeline_stage` values. Wait for user input. (Skip only if the user explicitly requests batch mode.)
3. Create `wiki/sources/YYYY-MM-DD-slug.md` with full frontmatter and body. Fill the **Tier Implications** section with one subsection per tier in `tiers_relevant`.
4. For each tier in `tiers_relevant`, open the relevant tier page(s) and update them:
   - Incorporate new knowledge into the relevant body sections.
   - Increment `sources_count` in frontmatter.
   - Update `last_updated` in frontmatter.
   - Set `status: needs-review` at the start of the update, then `stable` when done.
   - Add a wiki-link to the source in the tier page's Sources section.
5. For each cross-tier concept identified: check if a concept page exists. If yes, update it. If no, and the concept meets the creation threshold (3+ sources OR 2+ tiers), create it in `wiki/concepts/`.
6. Flag contradictions with `> [!warning]` on both the source page and the affected tier page.
7. Update `wiki/index.md`.
8. Append an entry to `wiki/log.md`.
9. Do NOT create entity pages — that directory is retired.

### `/ingest-github` — Process new files from `raw/github/`

1. List all files in `raw/github/` not yet referenced in `wiki/log.md`.
2. For each new file, ask the user to confirm `tiers_relevant` and `pipeline_stage` if ambiguous.
3. For each confirmed file, run the standard `/ingest` workflow.
4. Log which files were ingested.

### `/query` — Answer a question from the wiki

1. If the question is tier-specific, read the relevant tier page(s) first — they synthesize what is known. Consult source pages only if the tier page's Sources section is insufficient.
2. Read `wiki/index.md` to identify any additionally relevant concept or source pages.
3. Read those pages.
4. Synthesize an answer with `[[wiki-links]]` as citations.
5. **Choose the right output format:**
   - Markdown narrative for synthesis or analysis
   - Comparison table for "X vs Y" questions
   - Timeline for chronological questions
   - Marp slide deck if the user needs to present findings
   - Obsidian Canvas (`.canvas` JSON) for mapping relationships visually
   - `> [!pipeline]` block if the answer is a pipeline-ready constraint
6. If the answer is valuable and reusable, offer to save it — to the relevant tier page section (if tier-specific) or as a new concept page (if it meets the creation threshold).
7. Append to `wiki/log.md`.

### `/lint` — Health-check the wiki

**Tier page checks:**
- All 8 tier pages exist. Flag any missing.
- No tier page has `status: needs-review` for more than 7 days.
- All required body sections present on every tier page.
- Source pages with `tiers_relevant` populated but missing a Tier Implications section.
- Tier pages with `sources_count < 3` — flag as under-researched; propose specific source types.
- Tier pages whose `last_updated` is older than the `date_ingested` of any source referencing them.

**Standard checks:**
- Orphan pages, wanted pages, tag consistency, broken frontmatter, missing cross-references.

**Research gap detection:**
- For each tier page section containing no source citations, flag as unsupported.
- Propose specific source types to find for each gap.

Output a markdown report. Offer to fix issues.

### `/overview` — Regenerate the overview

Rewrite `wiki/overview.md` with this structure:

```markdown
# Nabojo Pipeline Knowledge Base — Overview
> Last regenerated: YYYY-MM-DD

## Pipeline Health Summary
| Tier | Ages | Matter Status | Manner Status | Sources | Open Questions |
|------|------|--------------|--------------|---------|----------------|
| 1 | 6–7 | ... | ... | N | N |
| 2 | 7–8 | ... | ... | N | N |
| 3 | 8–10 | ... | ... | N | N |
| 4 | 10–12 | ... | ... | N | N |

## Tier 1 (Ages 6–7) — Summary
## Tier 2 (Ages 7–8) — Summary
## Tier 3 (Ages 8–10) — Summary
## Tier 4 (Ages 10–12) — Summary
## Cross-Tier Insights
## Research Priorities
```

### `/save` — Save a query answer

If the answer is tier-specific: update the relevant section of the tier page. If cross-tier and meets the concept creation threshold: create a new concept page in `wiki/concepts/`.

### `/tier-profile [N] [optional: "topic"]` — Generate a pipeline brief

**Purpose:** Produce a combined Matter + Manner brief for tier N ready for direct injection into a pipeline prompt. This is the primary output operation of the wiki.

1. Read both tier pages for tier N in full.
2. If a topic argument is provided: check whether it appears in Permitted Topics or Topics to Avoid. Flag clearly if it is in the Avoid list.
3. Assemble the brief:

```markdown
# Nabojo Tier [N] Pipeline Brief — [Ages]
Generated: YYYY-MM-DD

> [!pipeline]
> ## Reader Profile
> [Tier Overview content]
>
> ## Story Parameters (Matter)
> **Topic approved:** yes / no / conditional
> **Permitted narrative types:** [list]
> **Character guidance:** [from Matter page]
> **Emotional & moral constraints:** [from Matter page]
> **French cultural notes:** [from Matter page]
>
> ## Writing Constraints (Manner)
> **Sentence structure:** [table]
> **Vocabulary specification:**
> [embedded YAML block — verbatim]
> **Pacing rules:** [from Manner page]
> **Grammar constraints:** [from Manner page]
> **Interactive choice mechanics:** [full section]
> **What to avoid:** [full list]

## Research Confidence
- Matter page: [status] — [sources_count] sources
- Manner page: [status] — [sources_count] sources
- [List any sections with 0 sources or draft status]
```

4. Ask: "Would you like to save this as a file?"
5. Do NOT save as a wiki page automatically. Offer to save to `pipeline-briefs/` if the user wants versioning.
6. Append to `wiki/log.md`.

### `/tier-diff [N] [optional: matter|manner]` — Show changes since last brief

1. Read `wiki/log.md` and find the most recent `tier-profile` entry for tier N.
2. Read the current tier page(s).
3. Identify sources ingested after that log entry.
4. Summarize: "Since your last Tier N brief (YYYY-MM-DD), the following changed: [list]."

---

## GitHub Sync Workflow

The vault is synced via the **Obsidian Git plugin** to a shared GitHub repository.

**For collaborators pushing sources:** Place files in `raw/github/`. The wiki maintainer runs `/ingest-github` to process new arrivals.

**What gets committed:** Everything in `raw/` and `wiki/`, `CLAUDE.md`, `.obsidian/` settings.

**What to watch for:**
- Merge conflicts in `wiki/tiers/` — resolve by re-running `/ingest` on the conflicting source
- Large binary files (PDFs, images) — consider Git LFS

---

## Guiding Principles

1. **Sources are sacred.** Never modify anything in `raw/`. If a source is wrong, note it in the wiki page — do not fix the original.

2. **Tier pages are the product.** All other pages exist in service of the eight tier pages. Every ingest decision should be evaluated by asking: "Does this make the tier pages more accurate, more complete, or more usable?"

3. **Dual readability is non-negotiable.** Every page must be both machine-extractable and human-readable. Never sacrifice one for the other.

4. **Pipeline-readiness is a quality criterion.** Ask: could this section be copy-pasted into a prompt and used as-is? Vague guidance ("use appropriate vocabulary") is a failed page.

5. **Compound, do not duplicate.** When a new source covers a topic already in a tier page, update the existing page — do not add parallel content. The tier page synthesizes; sources are the evidence.

6. **Flag uncertainty visibly.** Use `status: draft`, `confidence: low/medium/high`, `> [!warning]` for contradictions, `> [!question]` for open gaps. A tier page with 1 source and no flags is more dangerous than one clearly marked `draft`.

7. **Tier consistency over section depth.** All 8 tier pages complete > 2 pages deep. A pipeline that cannot generate Tier 1 content because that page has no Manner section is broken, even if Tier 4 Manner is excellent.

8. **The overview is the diagnostic instrument.** Regenerate it after any ingest that substantially changes a tier page. The Pipeline Health Summary table is the single best indicator of whether the wiki is doing its job.
