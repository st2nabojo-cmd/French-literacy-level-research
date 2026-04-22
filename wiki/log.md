# Wiki Log

> Chronological record of all operations performed on this wiki.
> Each entry uses a consistent format for easy parsing:
> `## [YYYY-MM-DD] operation | description`
>
> Parseable with: `grep "^## \[" log.md | tail -10`

---

## [2026-04-22] init | Wiki initialized

- Created vault structure: `raw/`, `wiki/`, `templates/`, `.claude/commands/`
- Created `CLAUDE.md` schema (v1.0)
- Created `wiki/index.md`, `wiki/log.md`, `wiki/overview.md`
- Created templates for source, entity, concept, and comparison pages
- Created Claude Code commands: `/ingest`, `/ingest-github`, `/query`, `/lint`, `/overview`, `/save`
- Wiki is ready for first source ingestion

---

## [2026-04-22] ingest | 2 sources processed (batch mode)

**Files ingested:**
1. `raw/articles/Development of a French‐language early literacy scale_ structural analysis and links between the dimensions of early literacy.md`
   → `wiki/sources/2026-04-22-eple-french-literacy-scale.md`
   - Note: Raw file is truncated (abstract only, 2.2KB). Full paper text not available in vault.

2. `raw/articles/Paradoxes in French‐Language Instruction Recent Social and Historical Research on Literacy in France.md`
   → `wiki/sources/2026-04-22-paradoxes-french-literacy-instruction.md`
   - Note: Raw file is partial (first ~half of paper, 8.8KB). Cuts off mid-paper after Lahire section begins.
   - Duplicate copy also present at `raw/papers/Paradoxes in French‐Language Instruction...md` (same content, not reprocessed)

**Entity pages created (7):**
- `wiki/entities/aude-thomas.md`
- `wiki/entities/universite-de-lorraine.md`
- `wiki/entities/eple-scale.md`
- `wiki/entities/elsie-rockwell.md`
- `wiki/entities/bernard-lahire.md`
- `wiki/entities/andre-chervel.md`
- `wiki/entities/anne-marie-chartier.md`

**Concept pages created (5):**
- `wiki/concepts/early-literacy.md`
- `wiki/concepts/phonological-awareness.md`
- `wiki/concepts/scriptal-schooled-relation.md`
- `wiki/concepts/literacy-inequality-france.md`
- `wiki/concepts/culture-ecrite.md`

**Updated:** `wiki/index.md`, `wiki/log.md`, `wiki/overview.md`

**Key research themes activated:** Theme 2 (Literacy Levels in France) has its first sources. Themes 1, 3, 4, and 5 remain empty.

**Wanted pages flagged:** [[Forme Scolaire]], [[Schooled Literacy]], [[Raison Scolaire]], [[Pierre Bourdieu]], [[Jules Ferry]] — priority for future ingests or manual creation.
