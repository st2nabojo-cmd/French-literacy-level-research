---
type: source
title: "MANULEX: A Grade-Level Lexical Database from French Elementary School Readers"
slug: 2026-05-07-manulex-grade-level-lexical-database
date_ingested: 2026-05-07
source_type: paper
original_path: raw/papers/Manulex for grades.pdf
language: en
url: ""
authors:
  - "Bernard Lété"
  - "Liliane Sprenger-Charolles"
  - "Pascale Colé"
tiers_relevant:
  - 1
  - 2
  - 3
  - 4
pipeline_stage: manner
tags:
  - tier1
  - tier2
  - tier3
  - tier4
  - vocabulary
  - french-language
  - french-curriculum
  - literacy
  - peer-reviewed
key_claims:
  - "MANULEX provides grade-level word frequency lists from 1.9 million words in 54 French elementary school readers."
  - "G1 (6-year-olds): 6,704 lemmas. G2 (7-year-olds): 10,400 lemmas. G3–5 (8–11-year-olds): 22,411 lemmas."
  - "51% of lemmas in G3–5 are not present in G1–2 readers — vocabulary approximately triples between early and mid-elementary."
  - "High-frequency words are recognised more quickly and accurately regardless of measure or task."
  - "Grade-based frequency norms better predict reading latencies than adult corpus norms."
confidence: high
---

## Summary

MANULEX is the foundational French-language lexical database for child reading research — the French equivalent of the American Heritage Word Frequency Book. It was built from 1.9 million words in 54 French elementary school readers, covering Grades 1–5 (ages 6–11). The database provides word frequencies at four levels: G1 (age 6), G2 (age 7), G3–5 (ages 8–11), and G1–5 (all). For Nabojo, MANULEX is the authoritative reference for vocabulary difficulty grading: a word present in G1 with high frequency and high dispersion (spread across many readers) is solidly Tier 1; a word appearing only in G3–5 belongs to Tier 3 or 4.

## Key Findings / Arguments

1. **Grade-based frequency norms outperform adult corpus norms for predicting children's reading performance.** Using adult-corpus frequency to grade vocabulary for children systematically underestimates difficulty. MANULEX corrects this.
2. **Vocabulary size grows dramatically across grades:**
   - G1 (6-year-olds): **6,704 lemmas**
   - G2 (7-year-olds): **10,400 lemmas**
   - G3–5 (8–11-year-olds): **22,411 lemmas**
   - G1–5 combined: **23,812 lemmas**
3. **51% of G3–5 lemmas are absent from G1 and G2 readers.** This means the Tier 3 vocabulary is almost entirely distinct from Tier 1–2 vocabulary — not a gradual expansion but a qualitative shift.
4. **Frequency × Dispersion = true difficulty.** The database uses both frequency (F) and dispersion index (D) to compute estimated frequency per million (U). A word appearing 276 times in G1 but all from one reader has D=0.24 and is not truly a G1 word. High-D words (present across many readers) are the safest Tier 1 vocabulary.
5. **Nouns dominate (45–52% of lemmas across grades); verbs ~14–18%.** Simple narrative action verbs are well-represented throughout; abstract nouns increase at G3–5.
6. **French-specific concern:** The most significant reading acquisition changes in French occur in G1 and G2 (more so than in English), because French orthography is more opaque. This makes G1 vocabulary control especially critical for Tier 1 Manner.

## Relevant Data

| Grade | Ages | Lemma count | Key change |
|-------|------|-------------|-----------|
| G1 | 6 | 6,704 | Entry point — decoding stage |
| G2 | 7 | 10,400 | +3,696 lemmas (+55%) |
| G3–5 | 8–11 | 22,411 | +12,011 lemmas — qualitative shift |
| G1–5 | 6–11 | 23,812 | Full elementary range |

- 31% of word forms and 23% of lemmas are hapax (appear only once) — normal for varied vocabulary; not a problem indicator.
- Closed-class items (conjunctions, determiners, pronouns, prepositions) are almost entirely shared across all grades — function words are universal.

## Tier Implications

### Tier 1 (Manner): G1 Vocabulary Constraints
- Target vocabulary from the G1 lemma set (~6,700 words)
- Prioritise high-D (high-dispersion) words — those appearing across many different G1 readers
- Avoid words that appear in only one G1 reader (D < 0.5)
- Maximum 2–3 new-to-tier words per page/screen
- Concrete nouns (school, house, tree, dog, cat) and common action verbs (aller, manger, voir, venir) are bedrock G1 vocabulary

### Tier 2 (Manner): G2 Vocabulary Expansion
- The G2 set adds ~3,700 lemmas — approximately a 55% expansion
- Tier 2 can introduce G2 lemmas that are absent from G1, but contextual support remains mandatory
- Compound sentences and relative clauses introduce new vocabulary requirements (connectives: *mais, parce que, quand*) — these should be checked against G2 frequency data

### Tier 3 (Manner): G3–5 Vocabulary Entry
- The G3–5 set nearly doubles the available vocabulary
- Abstract nouns and domain-specific vocabulary become available
- 51% of G3–5 lemmas are new — writers must be conscious that a word familiar to a 10-year-old may be entirely unknown to a 7-year-old

### Tier 4 (Manner): Full G3–5 Range
- Tier 4 (ages 10–12) can draw on the full G3–5 lemma set
- Approaching adult-level frequency distribution (LEXIQUE comparisons show G1–5 combined approaching adult database values)

## Connections

- [[tier1-manner]], [[tier2-manner]], [[tier3-manner]], [[tier4-manner]]
- [[manulex-vocabulary-grading]] — concept page
- [[chall-reading-stages]] — Chall Stage 1/2 aligns with G1/G2 vocabulary constraints

## Limitations / Bias

- Database built from 54 school readers (1990s–2000s era). Vocabulary in contemporary French children's books may differ.
- The database covers readers used *in school*, not fiction or interactive narrative — word frequency for storytelling vocabulary may differ.
- Does not include proper nouns encountered in popular culture (character names, brand names) which are common in children's fiction.
- The Manulex.pdf (full paper) was also present but the shorter "for grades" article provides the core practical data; the two sources present the same database.

## Raw Quotes

> "Grade-level frequency norms computed from child-targeted texts... emphasize the need for precise frequency norms to gain access to child language development."

> "51% are nonoverlapping, occurring in the G3–5 subcorpus only... This result shows that it is important to have a lexicon for grades below third grade, because half of the words found in readers for 8-year-olds and above are not present in first- and second-grade readers."

> "In French, more strongly than in English, the most significant changes in reading acquisition occur in the first and the second grades."
