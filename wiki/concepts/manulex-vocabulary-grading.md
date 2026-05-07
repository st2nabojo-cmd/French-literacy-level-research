---
type: concept
name: "MANULEX: French Grade-Level Vocabulary Database"
domain: french-language
applies_to_tiers:
  - 1
  - 2
  - 3
  - 4
pipeline_stage: manner
tags:
  - vocabulary
  - french-language
  - french-curriculum
  - manner
  - tier1
  - tier2
  - tier3
  - tier4
first_mentioned_in: 2026-05-07-manulex-grade-level-lexical-database
sources_count: 1
last_updated: 2026-05-07
---

## Definition

MANULEX is a French lexical database built from a corpus of 54 French school readers (manuels scolaires) across grades 1–5 (CP through CM2), containing approximately 48,900 different word forms. It provides, for each lemma in the corpus:

- **Frequency** — how often the word appears across the corpus
- **Dispersion** — across how many of the 54 readers the word appears (0.0 to 1.0 scale)
- **Grade-level stratification** — whether the word appears primarily in G1 (CP), G2 (CE1), or G3–5 (CE2–CM2) texts

The three grade bands produce distinct vocabulary pools:
| Band | School grades | Lemma count | Notes |
|------|--------------|-------------|-------|
| G1 | CP (age 6–7) | 6,704 | Core early vocabulary; high-frequency and high-dispersion |
| G2 | CE1 (age 7–8) | 10,400 | G1 extended; includes words entering reading from oral vocabulary |
| G3–5 | CE2–CM2 (ages 8–12) | 22,411 | Significant expansion; **51% of G3–5 words are absent from G1–2** |

The 51% gap figure is the most important single statistic for Nabojo pipeline design: more than half the words a CM1 or CM2 reader encounters in school texts were absent from the school texts used in CP and CE1. Tier 3 and Tier 4 represent a genuine vocabulary discontinuity, not a smooth gradient.

MANULEX is the only French-language empirical resource for grade-level vocabulary calibration. There is no equivalent to the American Dolch/Fry word lists for French. For Nabojo's pipeline, MANULEX grade bands serve as the vocabulary ceiling specification for each tier.

## Why This Matters for Nabojo

Every Tier Manner page specifies a vocabulary ceiling derived from MANULEX grade bands. Without this empirical grounding, vocabulary guidance would be impressionistic. With it, a pipeline agent can evaluate whether a drafted sentence's vocabulary is tier-appropriate by checking word frequency and dispersion against the relevant grade band.

Practical pipeline use:
- **Tier 1 stories** should draw exclusively from high-frequency, high-dispersion G1 words, with a ceiling of 2 new words per page (words outside the reader's expected G1 active vocabulary)
- **Tier 2 stories** operate primarily within G2, introducing words at the G1→G2 transition; 3 new words per page ceiling
- **Tier 3 stories** cross the G2→G3-5 threshold; up to 5 new words per page; contextual inference is the acquisition mechanism
- **Tier 4 stories** operate across the full G3–5 range including literary and abstract vocabulary; up to 8 new words per page

## Tier-Specific Notes

### Tier 1 (G1 — 6,704 lemmas)
G1 vocabulary is dominated by high-frequency concrete nouns, action verbs, simple adjectives, and basic discourse words. These are words that appear across many different school texts (high dispersion) — not just frequent in total but widely distributed. For Nabojo story generation: every content word (noun, verb, adjective, adverb) should be checked against G1 high-dispersion status. New words (absent from G1 high-dispersion) should be introduced at a maximum of 2 per page with immediate contextual anchoring.

**Practical guidance:** Favour *maison, ami, chat, jardin, pomme, école, courir, trouver, donner, grand, petit, rouge* (canonical G1). Avoid *mystérieux, aventure, liberté, transformation* (absent from G1 or very low-dispersion G1).

### Tier 2 (G2 — 10,400 lemmas)
G2 adds approximately 3,700 lemmas to the G1 base. Many of these words are already in the child's oral vocabulary but not yet in their reading vocabulary — Stage 2 fluency-building consolidates this transfer. The G1→G2 transition vocabulary (words newly appearing in CE1 texts but familiar from speech) costs less per-encounter than truly new words. A ceiling of 3 new words per page applies to words genuinely outside both the G1 base and the oral vocabulary; words entering reading from speech are treated as semi-new and do not count against the ceiling.

**Practical guidance:** G2 unlocks: interpersonal verbs (*promettre, deviner, espérer*), more complex emotional vocabulary (*jaloux, déçu, fier*), and words for common social situations (*récrée, cantine, maîtresse*). Still avoid: domain-specific technical vocabulary, abstract political or historical terms, Latinate abstractions.

### Tier 3 (G3–5 entry — first crossing of the 51% gap)
Tier 3 is where the vocabulary discontinuity hits. Readers entering CE2 encounter words that were entirely absent from their prior school reading. The Stage 3 mechanism — reading to learn — is the acquisition engine: contextual inference is now reliable enough that new words can be acquired through reading without explicit instruction. Up to 5 new words per page assumes each can be inferred from surrounding context.

**Practical guidance:** G3–5 entry vocabulary includes curriculum-aligned historical terms (*Gaulois, seigneur, château-fort*), beginning abstract psychological vocabulary (*hésiter, redouter, se méfier*), and formal connectors (*cependant, pourtant*). Literary vocabulary at the simpler end of G3–5 is accessible: *crépuscule, ombre, s'élancer*. Avoid the high end of G3–5 (low-frequency, low-dispersion vocabulary only appearing in specialist texts).

### Tier 4 (G3–5 full range — 22,411 lemmas)
Tier 4 has full access to the G3–5 range, including literary vocabulary, historical and geographic terms, beginning abstract conceptual vocabulary (*justice, trahison, ambiguïté*), and formal register markers. The ceiling of 8 new words per page reflects the reader's developing ability to infer and retain vocabulary at high rates through engaged reading.

**Practical guidance:** The Tier 4 vocabulary ceiling is a quality constraint (avoid gratuitous register elevation) rather than a developmental constraint. Any word from the G3–5 pool is usable; the question is whether the word serves the story's meaning precisely or whether a higher-frequency synonym would serve equally well. Literary quality at Tier 4 includes vocabulary precision — the right word, not the most available word.

## What Sources Say

- [[2026-05-07-manulex-grade-level-lexical-database]]: Primary source. Provides the corpus description (54 school readers), the three-band stratification (G1/G2/G3–5), the lemma counts per band (6,704 / 10,400 / 22,411), and the 51% gap statistic (51% of G3–5 words absent from G1–2). Also provides frequency and dispersion data for individual lemmas.

> [!warning] MANULEX is derived from *school readers* (manuels scolaires), not from children's fiction. The vocabulary profile of French children's literature (romans jeunesse, contes, albums illustrés) may differ from school text vocabulary. A word that appears frequently in fiction (e.g., *sorcière, dragon, chevalier*) may have low dispersion in MANULEX G1 despite being extremely familiar to French children through oral storytelling and cultural exposure. Pipeline calibration should account for this gap between school-reader vocabulary and cultural vocabulary.

> [!warning] MANULEX data was collected from the school readers in use at the time of compilation. The French school curriculum and its associated readers are revised periodically. The current G1–5 vocabulary distribution may differ from the MANULEX baseline.

## Open Questions

> [!question] What is the high-frequency, high-dispersion G1 word list for Tier 1 fiction? MANULEX provides the raw data but no curated "fiction-safe" G1 word list exists. The 500–1,000 highest-frequency, highest-dispersion G1 nouns, verbs, and adjectives extracted from MANULEX would be the most actionable vocabulary resource for Tier 1 prompt engineering.

> [!question] How does children's cultural vocabulary (words known from oral storytelling, TV, and cultural exposure but not from school readers) interact with MANULEX grade-level calibration? Words like *sorcière, château, dragon, fée* may be outside MANULEX G1 high-dispersion but extremely familiar to French children at age 6–7. A supplementary "cultural vocabulary" list that is not captured by MANULEX would improve Tier 1 and Tier 2 vocabulary specifications.

> [!question] Is there a French equivalent to the Lexile Framework or the American ATOS readability measure that incorporates MANULEX data? A readability score that combines sentence length, MANULEX grade level, and syntactic complexity for French text would make tier compliance verification automated rather than manual.

## Connections

- [[tier1-manner]] — G1 vocabulary ceiling; 2 new words per page ceiling; high-dispersion word selection
- [[tier2-manner]] — G2 vocabulary ceiling; 3 new words per page; Stage 2 oral-to-reading vocabulary transfer
- [[tier3-manner]] — G3–5 entry vocabulary; 5 new words per page; contextual inference as acquisition mechanism
- [[tier4-manner]] — Full G3–5 range; 8 new words per page; vocabulary precision as quality criterion
- [[chall-reading-stages]] — Chall's Stage 2 familiar-content constraint and MANULEX G2 ceiling are complementary; both derive from the same developmental period
- [[working-memory-and-chunking]] — Unfamiliar words consume more working memory chunks than familiar ones; vocabulary familiarity directly affects effective chunk budget
