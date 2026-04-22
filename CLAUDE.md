# CLAUDE.md — LLM Wiki Schema

> This file is the operating manual for the LLM agent maintaining this wiki.
> Read this file completely at the start of every session before doing anything else.

---

## Project Context

This wiki is a **research knowledge base** for a children's book project targeting **French children aged 8–12**.

The research covers:
- **Creative AI writing in French** — how LLMs generate literary-quality French prose, what works, what doesn't, stylistic considerations for young readers
- **Literacy levels in France (ages 8–12)** — reading comprehension benchmarks, vocabulary ranges, sentence complexity norms, official curriculum standards (cycle 3)
- **What constitutes a children's book** — genre conventions, illustration/text ratios, narrative structures, moral/educational framing, publishing standards
- **How children learn through storybooks** — pedagogy of narrative, cognitive development, reading motivation, the role of imagination, bilingual considerations
- **Market & publishing** — French children's book publishers, market trends, comparable titles, editorial expectations

The wiki is used by **multiple collaborators** (via GitHub sync). Write clearly and assume the reader may not have full context.

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
└── assets/         # Images, diagrams, book covers referenced by sources
```

### Layer 2: The Wiki (`wiki/`)
**LLM-owned.** The agent writes, updates, and maintains everything here.

```
wiki/
├── sources/        # One summary page per ingested source
├── entities/       # People, organizations, publishers, tools, books
├── concepts/       # Ideas, frameworks, pedagogical theories, techniques
├── comparisons/    # Side-by-side analyses (e.g., AI vs human writing for kids)
├── index.md        # Master catalog of all wiki pages
├── log.md          # Chronological record of all operations
└── overview.md     # High-level synthesis of everything the wiki knows
```

### Layer 3: This Schema (`CLAUDE.md`)
**Co-evolved.** The human and LLM update this together as the wiki grows.

---

## Page Types & Frontmatter

Every wiki page MUST start with YAML frontmatter:

### Source Page (`wiki/sources/`)
```yaml
---
type: source
title: "Human-readable title of the source"
slug: YYYY-MM-DD-short-slug
date_ingested: YYYY-MM-DD
source_type: article | paper | transcript | video | book | report
original_path: raw/articles/filename.md
language: fr | en
url: "https://..."
authors:
  - "Author Name"
tags:
  - literacy
  - AI-writing
  - pedagogy
key_claims:
  - "Claim 1 in one sentence"
  - "Claim 2 in one sentence"
confidence: high | medium | low
---
```

**Body structure:**
1. **Summary** — 3–5 sentence overview of the source
2. **Key Findings / Arguments** — numbered list of main points
3. **Relevant Data** — statistics, benchmarks, quotes (with page/timestamp refs)
4. **Connections** — wiki-links to related [[entity]] and [[concept]] pages
5. **Limitations / Bias** — note any caveats about the source
6. **Raw Quotes** — important verbatim passages (with citation info for traceability)

### Entity Page (`wiki/entities/`)
```yaml
---
type: entity
entity_type: person | organization | publisher | tool | book | institution
name: "Entity Name"
aliases: ["Other Name"]
tags:
  - AI
  - publishing
first_mentioned_in: YYYY-MM-DD-slug
sources_count: 3
last_updated: YYYY-MM-DD
---
```

**Body:** Description, role in the research domain, key claims about/by this entity, and [[wiki-links]] to related pages.

### Concept Page (`wiki/concepts/`)
```yaml
---
type: concept
name: "Concept Name"
domain: literacy | AI-writing | pedagogy | publishing | cognitive-development
tags:
  - narrative-structure
  - reading-motivation
first_mentioned_in: YYYY-MM-DD-slug
sources_count: 2
last_updated: YYYY-MM-DD
---
```

**Body:** Definition, significance to the project, what sources say (with citations as [[source-slug]]), contradictions if any, open questions.

### Comparison Page (`wiki/comparisons/`)
```yaml
---
type: comparison
title: "X vs Y"
items_compared:
  - "Item A"
  - "Item B"
tags: []
last_updated: YYYY-MM-DD
---
```

**Body:** Context, criteria, side-by-side analysis, conclusion/recommendation.

---

## Conventions

### Wiki-Links
- Always use Obsidian-style `[[page-name]]` links
- Link generously: every mention of a known entity or concept should be linked
- If a concept is mentioned but has no page yet, still link it — it becomes a "wanted page" visible in Obsidian's graph

### Tags (in frontmatter)
Use a controlled vocabulary. Current approved tags:
- **Domain:** `literacy`, `AI-writing`, `pedagogy`, `publishing`, `cognitive-development`, `market-research`, `French-language`, `illustration`
- **Age-related:** `age-8-10`, `age-10-12`, `cycle-3`
- **Source quality:** `peer-reviewed`, `official-report`, `expert-opinion`, `anecdotal`

New tags may be added but should be documented in this section.

### Language
- Wiki pages are written in **English** (the working language of the team)
- French terms, book titles, and curriculum references should be kept in French with English translation in parentheses on first mention
- Source pages may contain French quotes — always provide English translation in brackets

### Callouts for special situations
Use Obsidian callout syntax:
- `> [!warning]` — Contradiction between sources
- `> [!question]` — Open research question / gap
- `> [!tip]` — Actionable insight for the book project
- `> [!info]` — Context that helps interpret data

---

## Operations

### `/ingest` — Process a new source

**Default mode is interactive.** Ingest sources one at a time. Stay involved — read the summaries, check the updates, guide the LLM on what to emphasize. Batch mode (processing many sources with less supervision) is the exception, not the default. The human should always have the chance to steer what matters.

1. Read the raw source file completely
2. Discuss key takeaways with the user — highlight what's new, surprising, or contradicts existing wiki knowledge. Wait for the user's input before proceeding. (Skip this step only if the user explicitly requests batch mode.)
3. Create `wiki/sources/YYYY-MM-DD-slug.md` with full frontmatter and structured body
4. For each entity mentioned: create or update its page in `wiki/entities/`
5. For each concept mentioned: create or update its page in `wiki/concepts/`
6. Flag contradictions with existing wiki content using `> [!warning]`
7. Update `wiki/index.md` — add the new pages
8. Append an entry to `wiki/log.md`
9. If the source significantly changes our understanding, update `wiki/overview.md`

### `/ingest-github` — Process new files from `raw/github/`

1. List all files in `raw/github/` that are NOT yet referenced in `wiki/log.md`
2. For each new file, run the standard `/ingest` workflow
3. After processing, log which files were ingested so they aren't reprocessed

### `/query` — Answer a question from the wiki

1. Read `wiki/index.md` to find relevant pages
2. Read those pages
3. Synthesize an answer with `[[wiki-links]]` as citations
4. **Choose the right output format for the question.** Not every answer is a paragraph. Consider:
   - A markdown page for synthesis or analysis
   - A comparison table for "X vs Y" questions
   - A timeline for chronological questions
   - A slide deck (Marp format) if the user needs to present findings
   - A chart description if data visualization would help
   - An Obsidian Canvas (`.canvas` JSON) for mapping relationships visually
5. If the answer is valuable and reusable, offer to save it as a new wiki page — explorations should compound in the knowledge base just like ingested sources do

### `/lint` — Health-check the wiki

Check for:
- **Contradictions** — claims on different pages that conflict
- **Orphan pages** — wiki pages with no inbound links
- **Wanted pages** — `[[links]]` pointing to pages that don't exist yet. These are a growth mechanism: they show where the wiki *wants* to expand. Prioritize creating pages for wanted links that appear in 2+ existing pages.
- **Stale content** — pages not updated after newer sources were ingested
- **Missing cross-references** — entities/concepts mentioned in text but not linked
- **Research gaps** — topics referenced but with no dedicated source

**Then go further — suggest research directions:**
- Propose new questions to investigate based on patterns in existing knowledge
- Suggest specific types of sources to look for (e.g., "We have opinions on AI writing for kids but no empirical studies — look for peer-reviewed papers")
- Identify themes from `wiki/overview.md` that are under-represented

Output a markdown report and offer to fix issues.

### `/overview` — Regenerate the overview

Rewrite `wiki/overview.md` as a comprehensive synthesis of everything the wiki currently knows, organized by research theme.

### `/save` — Save a query answer as a wiki page

Take the last query response and file it as a new page in the appropriate wiki subdirectory.

---

## GitHub Sync Workflow

The vault is synced via the **Obsidian Git plugin** to a shared GitHub repository.

**For collaborators pushing sources:**
- Place files in `raw/github/` (any format: PDF, markdown, text, links)
- The Git plugin auto-pulls on a schedule (configured in Obsidian)
- The wiki maintainer (you + LLM) runs `/ingest-github` to process new arrivals

**What gets committed:**
- Everything in `raw/` (immutable sources)
- Everything in `wiki/` (LLM-maintained pages)
- `CLAUDE.md` (schema updates)
- `.obsidian/` settings (so collaborators get the same view)

**What to watch for:**
- Merge conflicts in `wiki/` pages — resolve by re-running `/ingest` on the conflicting source
- Large binary files (PDFs, images) — consider using Git LFS

---

## Guiding Principles

1. **Sources are sacred.** Never modify anything in `raw/`. If a source is wrong, note it in the wiki page — don't fix the original.
2. **Link everything.** A wiki without links is just a folder of files. Every entity and concept mention should be a `[[wiki-link]]`.
3. **Flag uncertainty.** Use `confidence: low/medium/high` in frontmatter. Use `> [!warning]` for contradictions. Never present uncertain claims as settled.
4. **Compound, don't duplicate.** When a new source covers a topic already in the wiki, update the existing concept/entity page — don't create a parallel one.
5. **The overview is the north star.** It should always reflect the current state of all research. Regenerate it after major ingests.
6. **Write for the team.** Collaborators may read wiki pages without context. Be clear, cite sources, and explain jargon.
