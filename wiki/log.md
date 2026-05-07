# Wiki Log

> Chronological record of all operations performed on this wiki.
> Format: `## [YYYY-MM-DD] operation | description`

---

## [2026-05-06] init | Wiki repurposed as Nabojo Tier Pipeline Knowledge Base

Clean slate applied. All prior sources, entities, and concept pages removed. New structure:
- `wiki/tiers/` directory created with 4 tier subdirectories
- 8 tier page stubs created (tier1–4, matter + manner each), all `status: draft`
- `wiki/index.md`, `wiki/log.md`, `wiki/overview.md` reset
- `CLAUDE.md` fully rewritten with new schema (Matter/Manner/Tier framework)

Tiers defined:
- Tier 1: 6–7 (CP, CE1)
- Tier 2: 7–8 (CE1, CE2)
- Tier 3: 8–10 (CE2, CM1)
- Tier 4: 10–12 (CM1, CM2, 6e)

---

## [2026-05-07] ingest | Batch ingest of 15 sources

Batch mode (user-authorised). All 15 raw source files processed in a single session. No interactive discussion per source — emphasis decisions delegated to the LLM.

**Sources ingested (15):**
- [[2026-05-07-nabojo-context]] — Nabojo company/product overview (PDF, 6 pages); foundational context
- [[2026-05-07-chall-stages-reading-development]] — Chall's 5 stages; primary Manner constraint engine
- [[2026-05-07-chunking-memory-working-memory-development]] — Working memory chunk capacity by age; drives sentence length limits
- [[2026-05-07-manulex-grade-level-lexical-database]] — French grade-level vocabulary database; G1/G2/G3–5 lemma pools
- [[2026-05-07-theory-of-mind-middle-childhood]] — AToM longitudinal study; 3 factors; milestone at age 7
- [[2026-05-07-heros-journey-writing-guide]] — Vogler's Hero's Journey; 12 stages; 7 archetypes
- [[2026-05-07-propp-morphology-folktale]] — Propp's 31 narrative functions (intro + TOC only; Chapter III not fully extracted)
- [[2026-05-07-pov-examples-childrens-books]] — POV taxonomy; 2nd person = choose-your-own-adventure
- [[2026-05-07-picture-book-early-reader-chapter-book]] — Format specifications for early reader and chapter book
- [[2026-05-07-jinx-moral-ambiguity-middle-grade]] — Moral ambiguity appropriate at Tier 4; villain with valid truths
- [[2026-05-07-eple-french-literacy-scale]] — French early literacy 4-domain framework (abstract only; confidence: low)
- [[2026-05-07-paradoxes-french-literacy-instruction]] — French literacy history; scriptal-schooled relation; culture écrite
- [[2026-05-07-trustworthiness-llm-children-stories]] — LLM story quality criteria for children's content
- [[2026-05-07-art-of-storytelling-ai-models]] — Multi-agent AI storytelling; Propp + Freytag; model comparisons
- [[2026-05-07-words-per-minute-speaking]] — Speaking pace benchmarks (limited pipeline relevance; confidence: low)

**Tier pages updated (8/8):**
- [[tier1-matter]]: stable, sources_count: 6
- [[tier1-manner]]: stable, sources_count: 5 *(first write — was stub)*
- [[tier2-matter]]: stable, sources_count: 5
- [[tier2-manner]]: stable, sources_count: 5 *(first write — was stub)*
- [[tier3-matter]]: draft, sources_count: 4
- [[tier3-manner]]: stable, sources_count: 4 *(first write — was stub)*
- [[tier4-matter]]: stable, sources_count: 5
- [[tier4-manner]]: stable, sources_count: 4 *(first write — was stub)*

**Concept pages created (5):**
- [[chall-reading-stages]] — literacy domain; all tiers; manner
- [[working-memory-and-chunking]] — cognitive-development domain; all tiers; manner
- [[manulex-vocabulary-grading]] — french-language domain; all tiers; manner
- [[theory-of-mind-development]] — cognitive-development domain; all tiers; matter
- [[narrative-morphology]] — narrative-craft domain; all tiers; matter

**Known gaps from this ingest:**
- Propp Chapter III not fully extracted — 31 functions not enumerated in wiki
- EPLE source is abstract only (full paper paywalled) — confidence: low
- Paradoxes article had duplicate in both `raw/articles/` and `raw/papers/` — articles/ version used
- All Chall/working memory research is Anglophone — French-language validation missing
- No French-language Tier 4 exemplar novels identified
