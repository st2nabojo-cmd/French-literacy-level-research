# Nabojo Pipeline Knowledge Base — Overview

> Last regenerated: 2026-05-07
> Sources ingested: 15 | Concept pages: 5 | Tier pages complete: 8/8

---

## Pipeline Health Summary

| Tier | Ages | Matter Status | Manner Status | Sources (unique) | Open Questions |
|------|------|--------------|--------------|-----------------|----------------|
| 1 | 6–7 | stable | stable | 9 | 6 |
| 2 | 7–8 | stable | stable | 6 | 6 |
| 3 | 8–10 | stable | stable | 5 | 6 |
| 4 | 10–12 | stable | stable | 7 | 6 |

**Overall:** 7 of 8 tier pages are `stable`. Tier 3 Matter is `draft` — it is informed by 4 sources (above the 3-source threshold for `stable`) but was produced in a batch ingest without dedicated source review; a manual review pass is recommended.

---

## Tier 1 (Ages 6–7, CP/CE1) — Summary

**Reader profile:** Chall Stage 1 — decoding consumes all cognitive resources. Working memory ~3–4 chunks. AToM not yet reliably crossed. First year of formal schooling (*la rentrée*).

**Matter:** Stories must be set in familiar home/school/nature environments. Maximum 3 named characters. Transparent motivations only — no deception, secrets, or hidden agendas. Simple problem–solution arc or circular story. Narrative types: simple problem–solution, circular story, single-goal quest, day-in-the-life. Emotional range: joy, excitement, mild fear (resolved), curiosity. Every story must end with the protagonist in a restored or better state.

**Manner:** Average sentence length 5–8 words (max 12). No subordinate clauses — SVO only. Vocabulary drawn from MANULEX G1 (6,704 lemmas); maximum 2 new words per page. Primary tense: présent de l'indicatif. Interactive choices: 2 options, cosmetic consequences, once per story or every 3–4 scenes.

**Research confidence:** Solid across 5–6 sources. The largest gaps are French-specific: no French-language validation of sentence length norms; no curated MANULEX G1 fiction word list; no empirical data on interactive branching comprehension at age 6–7.

> [!tip] Tier 1 is the most constrained tier. The key discipline for the pipeline is resisting the urge to add complexity — every deviation from the minimum (longer sentences, less familiar settings, more characters) directly competes with the decoding process.

---

## Tier 2 (Ages 7–8, CE1/CE2) — Summary

**Reader profile:** Chall Stage 2 — fluency building on familiar content. Working memory ~4–5 chunks. AToM milestone recently crossed at ~age 7. CE1 begins silent reading; CE2 marks first autonomous reading for pleasure.

**Matter:** **Stage 2 paradox:** familiar settings only — the reader is NOT yet in the reading-to-learn stage. Simple mysteries, friendship challenges, light fantasy with clear rules. Maximum 5 named characters. Simple deception, secrets, and surprises now accessible (AToM milestone crossed). Beginning Hero's Journey (Acts 1 + simplified 2 + 3). Shape Shifter archetype now comprehensible.

**Manner:** Average sentence length 8–13 words (max 20). One level of subordinate clause permitted. MANULEX G2 vocabulary (10,400 lemmas); maximum 3 new words per page. Passé composé enters alongside présent. Interactive choices: 2–3 options, moderate consequences, every 2–3 chapters.

**Research confidence:** Solid, but the Stage 2 paradox constraint is based on Anglophone research only. French orthographic opacity may push the Stage 1/2 boundary later — a French 7-year-old may still be substantially in Stage 1.

> [!warning] The Chall Stage 2 familiar-content constraint is the most commonly violated principle at this tier. Content teams often assume that a reader who can read fluently is ready for new information. This is incorrect at Stage 2. Tier 2 stories may extend narrative structure but must keep settings and conceptual content familiar.

---

## Tier 3 (Ages 8–10, CE2/CM1) — Summary

**Reader profile:** Chall Stage 3 — reading to learn. Working memory ~5–6 chunks approaching adolescent capacity. AToM increasingly fluent across all three factors. CE2/CM1 introduces formal history, geography, and science.

**Matter:** New settings, new knowledge, and new vocabulary domains are now the story's opportunity. Historical France (*la Gaule, le Moyen Âge*), Francophone world, science and discovery all accessible. Single clear viewpoint required — multiple competing perspectives are Stage 4. Full 12-stage Hero's Journey accessible. Moral choices with clear authorial framing; antagonist with understandable motivation; Shape Shifter with delayed resolution.

**Manner:** Average sentence length 12–18 words (max 28). Two levels of clause nesting supported. MANULEX G3–5 entry vocabulary (22,411 lemma pool); maximum 5 new words per page. Passé simple + imparfait as the standard literary pair. Free indirect speech accessible (brief passages). Interactive choices: 3 options, moderate-to-significant consequences, every 2 chapters.

**Research confidence:** Draft status — 4 sources inform this tier but all are Anglophone. The Stage 3 single-viewpoint constraint, the passé simple automatisation timeline, and the CM1 prior-knowledge baseline all need French-specific research.

> [!question] Tier 3 Matter is marked `draft`. Priority sources needed: French school reading curricula (CE2/CM1 level), French-language research on reading comprehension at Stage 3, and empirical data on passé simple acquisition timeline for French primary school readers.

---

## Tier 4 (Ages 10–12, CM1/CM2/6ème) — Summary

**Reader profile:** Upper Chall Stage 3, approaching Stage 4. Working memory near-adult (~6–7 chunks). Full AToM competence across all three factors. Transition to collège (*6ème*) is a major life event.

**Matter:** Moral ambiguity is unlocked — the reader can leave a story without every question answered. Complex adventure with moral stakes, social and political dynamics, fantasy with world-building depth, historical events with moral complexity, identity and belonging. Full Hero's Journey with subversion; anti-hero; antagonist with valid argument; Shape Shifter with unresolved allegiance through the final act. Light romantic content (early friendship-becoming-more). La transition collège, la Résistance, la décolonisation as accessible story topics.

**Manner:** Average sentence length 15–25 words (max 40). Three levels of clause nesting supported. Full MANULEX G3–5 vocabulary range; maximum 8 new words per page. Full passé simple literary register. Extended free indirect speech; unreliable narrator signals comprehensible. Interactive choices: 3 options, significant consequences (4–6 chapter divergence), every 3–4 chapters.

**Research confidence:** Solid on cognitive and narrative frameworks. Primary gap: no French-language middle-grade exemplars identified; the craft benchmark is currently Anglophone.

> [!tip] Tier 4 is the only tier where the writing constraint is craft rather than cognitive capacity. The reader can handle almost any formal technique; the question is whether the technique serves the story. Pipeline prompts should emphasise precision and intentionality over constraint compliance.

---

## Cross-Tier Insights

### 1. The AToM milestone (age ~7) is the most important developmental event for Matter

The crossing of the AToM milestone at approximately age 7 is the single clearest demarcation between Tier 1 and Tier 2 in terms of story content. Before it: transparent motivations only. After it: secrets, surprises, simple deception, and dramatic irony all become accessible. This milestone gates more story elements than any other developmental event (it enables Shape Shifter archetypes, false heroes, surprise reveals, and dramatic irony — all of which are the primary engagement tools of Tiers 2–4).

Pipeline implication: any story element that requires the reader to hold a character's false belief — even briefly — must be tagged as Tier 2+ and cannot appear in Tier 1 content.

### 2. The Chall Stage 2 paradox constrains Tier 2 Matter more than any other rule

The most counter-intuitive finding across all ingested sources: Tier 2 readers who have become somewhat fluent are **not** ready for new information. Stage 2 fluency-building requires familiar content. This directly constrains Tier 2 Matter to familiar settings, known vocabulary domains, and previously-encountered conceptual content. It is violated constantly in practice by publishers and content producers who assume that a child who can read is ready to learn through reading.

Pipeline implication: Tier 2 story blueprints must specify settings that are recognisably familiar to French children (home, school, local nature, village). Any setting requiring the reader to build a new mental model (historical period, foreign country, invented world with complex rules) must wait for Tier 3.

### 3. The 51% vocabulary gap at Tier 3 entry is a design discontinuity

More than half of the words in MANULEX G3–5 (the vocabulary range of CE2–CM2 school readers) are entirely absent from G1–2. This is not a smooth gradient — it is a step change. Tier 3 is the stage where children first encounter large numbers of genuinely unfamiliar written words, and the Stage 3 reading-to-learn mechanism (contextual inference) is the acquisition engine. The pipeline's "5 new words per page" ceiling at Tier 3 reflects this: the reader can infer, but the inference budget is finite.

Pipeline implication: Tier 3 vocabulary specifications should prioritise words in the G2→G3-5 transition band — words entering the school corpus for the first time, which are often already in oral vocabulary. These cost less to acquire through reading than truly new words.

### 4. Working memory growth drives all Manner complexity scaling

The growth from ~3–4 chunks (Tier 1) to ~6–7 chunks (Tier 4) is the primary driver of every sentence length, subordination depth, and character count guideline across the four Manner tier pages. The practical formula: each sentence costs approximately 1 chunk; each named character held in active memory during a scene costs approximately 0.5–1 chunk; each level of clause nesting costs approximately 1 additional chunk. The tier system is essentially a budget system: what can fit within the working memory envelope at each age.

Pipeline implication: Sentence complexity violations (sentences that exceed the chunk budget) are the most common and most harmful Manner errors. A Reviewer agent checking generated content should prioritise sentence length and subordination depth before vocabulary checks.

### 5. Interactive choice mechanics scale from cosmetic to consequential across tiers

| Tier | Choices | Frequency | Consequence weight |
|------|---------|-----------|-------------------|
| 1 | 2 | Every 3–4 scenes | Cosmetic (paths rejoin in 1–2 scenes) |
| 2 | 2–3 | Every 2–3 chapters | Moderate (paths rejoin after 2–3 scenes) |
| 3 | 3 | Every 2 chapters | Moderate–significant (paths rejoin before climax) |
| 4 | 3 | Every 3–4 chapters | Significant (4–6 chapter divergence; moral weight) |

The scaling reflects both working memory (more choices require more tracking capacity) and emotional maturity (higher consequence weight requires the reader to tolerate sustained uncertainty about the "right" choice).

---

## Research Priorities

### Critical gaps (block pipeline for affected tiers)

1. **French-language validation of Chall stage boundaries** — All Chall research is Anglophone. The Stage 1/2 boundary may be shifted later in French due to orthographic opacity. Until validated, Tier 1 and Tier 2 sentence constraints should be applied conservatively (i.e., assume French readers may be at a less-mature stage than their English counterparts at the same age).

2. **MANULEX G1 fiction-safe word list** — MANULEX provides raw frequency/dispersion data but no curated fiction-appropriate G1 word list. A ranked list of the 500–1,000 highest-frequency, highest-dispersion G1 nouns, verbs, and adjectives is the highest-priority vocabulary resource for Tier 1 prompt engineering.

3. **Interactive branching comprehension at Tier 1** — No empirical data was found on whether 6–7-year-olds reliably understand the "choose your own path" mechanic. This is design-critical for Nabojo's core product at Tier 1. User testing or developmental psychology research on this specific question is needed before Tier 1 interactive choice mechanics can be finalised.

### Important gaps (inform tier quality but do not block)

4. **Propp's 31 functions — complete extraction** — Only the introduction and table of contents of Propp's *Morphology of the Folktale* were extracted during ingest. Chapter III (the definitive enumeration of the 31 functions) was not fully read. A complete extraction would allow precise Propp function mapping per tier.

5. **French-language Tier 4 exemplars** — The Tier 4 Matter craft benchmark is currently based on the Anglophone *Jinx* series. French-language middle-grade novels (*romans de jeunesse*) that exemplify ideal Tier 4 Matter and Manner would significantly strengthen both tier pages.

6. **Passé simple automatisation timeline for French primary readers** — Tier 3 introduces passé simple as the primary literary past tense, but no source specifies when it becomes "invisible" (automatically parsed) for French readers. If it is still cognitively costly in CE2, action sequences in passé simple at Tier 3 may over-tax the reader.
