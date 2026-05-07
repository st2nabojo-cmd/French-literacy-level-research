---
type: concept
name: "Narrative Morphology"
domain: narrative-craft
applies_to_tiers:
  - 1
  - 2
  - 3
  - 4
pipeline_stage: matter
tags:
  - narrative-structure
  - matter
  - tier1
  - tier2
  - tier3
  - tier4
first_mentioned_in: 2026-05-07-heros-journey-writing-guide
sources_count: 3
last_updated: 2026-05-07
---

## Definition

Narrative morphology refers to the structural regularities that underlie effective stories — the recurring functions, sequences, and character types that appear across cultures and genres. For Nabojo's pipeline, two complementary frameworks are operationalised:

**Vogler's Hero's Journey** (derived from Campbell, adapted for screenwriting): 12 sequential stages across 3 acts (Departure, Initiation, Return), accompanied by 7 character archetypes (Hero, Mentor, Herald, Threshold Guardian, Shape Shifter, Shadow, Trickster). This framework is generative — it provides a template for constructing a complete story structure tier by tier.

**Propp's 31 Narrative Functions**: Vladimir Propp's analysis of Russian fairy tales identifies 31 sequential narrative "functions" — actions defined by their role in the plot rather than by character. Functions are constant across stories; characters are interchangeable. This framework provides a fine-grained decomposition useful for AI-assisted story generation and quality-checking.

Both frameworks are computationally validated: [[2026-05-07-art-of-storytelling-ai-models]] demonstrates that Propp's functions can be used as story generation constraints in an AI pipeline (combined with Freytag's Pyramid). The Hero's Journey is the primary tier-differentiation tool; Propp provides additional granularity for the manuscript stage.

## Why This Matters for Nabojo

Narrative morphology is the Matter framework for story structure. When a Nabojo story brief is generated at a given tier, the permitted narrative types (from the Matter tier page) map directly onto sub-sets of the Hero's Journey stages. Tier 1 uses a 3-stage arc (Home → Problem → Home); Tier 4 can use all 12 stages with anti-heroic subversion. This framework allows the pipeline to generate structurally sound stories without requiring a human editor to verify basic narrative architecture.

Additionally, because Propp's functions are computationally operationalisable, they provide a quality-checking vocabulary: a Reviewer agent can verify that a generated draft contains the required functions (Villainy/Lack → Departure → Tests → Resolution → Return) at each tier level.

## Tier-Specific Notes

### Tier 1 (Ages 6–7)
**Hero's Journey subset:** Acts 1 + simplified Act 3 only. 3 stages: Ordinary World → Call to Adventure (simplified: a problem appears) → Return with Reward (resolution). No Initiation act — the tests and ordeals of Act 2 require working memory and emotional capacity beyond Tier 1.

**Propp functions applicable:** Absentation (something is missing or someone leaves), Villainy/Lack (the problem is defined), Departure (protagonist sets out), Resolution (problem is solved), Return (protagonist is home). Functions involving deception, false heroes, or recognition tests are beyond Tier 1 Theory of Mind.

**Character archetypes at Tier 1:** Hero (child or animal), Mentor/Helper (adult figure), simple Shadow/obstacle (non-threatening). Trickster accessible for comic relief. Shape Shifter, Herald not yet meaningful — require Theory of Mind for their narrative function.

### Tier 2 (Ages 7–8)
**Hero's Journey subset:** Full 3-act structure with simplified Act 2. Stages accessible: Ordinary World, Call to Adventure, Refusal of the Call (character hesitates), Meeting the Mentor, Crossing the Threshold, 2–3 Tests/Allies/Enemies, Approach to the Inmost Cave, Ordeal, Reward, Road Back, Return. The Resurrection beat (final climactic test) is accessible but must be concrete, not metaphysical.

**Propp functions:** Full set of departure, testing, and return functions. Recognition and unmasking functions (exposure of a false hero or villain) now accessible with AToM milestone.

**Character archetypes at Tier 2:** All 7 archetypes accessible in simple form. Shape Shifter is now comprehensible (a character whose allegiance is unclear, resolved by the end). Trickster used deliberately for humour and plot complication.

### Tier 3 (Ages 8–10)
**Hero's Journey:** Full 12-stage structure accessible. Ensemble hero (multiple protagonists with distinct arcs) now manageable with growing working memory. The Inmost Cave and Ordeal stages can carry genuine emotional weight — loss, sacrifice, moral failure — with authorial resolution.

**Propp functions:** Full 31 functions accessible in sequence. Dual hero arcs (a protagonist and a competing hero or false hero) are comprehensible. Complex recognition and unmasking sequences work.

**Character archetypes at Tier 3:** All 7 archetypes with greater complexity. Mentor with imperfect knowledge (doesn't have all the answers). Shape Shifter whose allegiance remains genuinely unclear until late. Antagonist with understandable motivation (not pure evil — driven by fear or misunderstanding).

### Tier 4 (Ages 10–12)
**Hero's Journey:** Full 12 stages with subversion. Accessible variants: reluctant hero (refuses the call longer than expected), anti-hero (morally compromised protagonist), hero who fails (the ordeal is not won on first attempt), ensemble with 4–5 distinct character arcs. The Resurrection beat can carry genuine moral ambiguity — the protagonist may emerge changed rather than victorious.

**Propp functions:** All 31 functions with complexity. The "villain with a valid argument" pattern (Propp's Villain function subverted) is now accessible and powerful.

**Character archetypes at Tier 4:** Morally complex protagonist (capable of cowardice and poor judgment, growth non-linear), Ambiguous Mentor (motivations not fully transparent), Antagonist with a valid argument (right about some things, wrong in methods), Shape Shifter with unresolved allegiance (reader genuinely uncertain until late), Mirror character (represents the protagonist's possible future self).

## What Sources Say

- [[2026-05-07-heros-journey-writing-guide]]: Primary source for the Hero's Journey framework. Provides the full 12-stage sequence and 7 archetypes with writing guidance. Confirms that the complexity of Hero's Journey usage is age-scalable.
- [[2026-05-07-propp-morphology-folktale]]: Primary source for Propp's 31 functions. Establishes that functions are sequentially constant across stories — the order matters even when individual functions are skipped. Note: only the introduction and table of contents were fully extracted; Chapter III (the full function enumeration) was not completely read.
- [[2026-05-07-art-of-storytelling-ai-models]]: Confirms computational operationalisability of both Propp's functions and Freytag's Pyramid for AI story generation. Demonstrates that LLM pipelines can use Propp functions as generation constraints.

> [!warning] Propp's functions were derived from a corpus of Russian fairy tales. Their universality is debated in comparative folklore research. However, for pipeline purposes, their computational tractability is the primary value — the question of cross-cultural universality is secondary to their usefulness as a generative scaffold.

## Open Questions

> [!question] Which specific Propp functions are most essential for each tier? The current tier notes use approximate function sets. A precise mapping of Propp functions to tier-appropriate story arcs would improve both the Matter guidance and the Reviewer agent's quality check vocabulary.

> [!question] How does the Hero's Journey map onto specifically French narrative traditions? The framework is derived primarily from Joseph Campbell's cross-cultural analysis and Vogler's Hollywood application. French literary tradition for children (contes de fées, fables, roman historique) may have different structural emphases. A French-literary analysis would sharpen the tier-specific notes.

> [!question] Can Propp functions be used as a real-time constraint in a Nabojo story generation prompt? The AI storytelling paper demonstrates this is possible in principle. The practical question is whether a Reviewer agent checking for Propp functions provides better quality control than human editorial review at each tier.

## Connections

- [[tier1-matter]] — 3-stage arc; simple Hero/Helper/Obstacle archetypes
- [[tier2-matter]] — Full Hero's Journey with simplified Act 2; Shape Shifter now comprehensible
- [[tier3-matter]] — Full 12-stage Hero's Journey; ensemble hero accessible; Antagonist with motivation
- [[tier4-matter]] — Subversive Hero's Journey; anti-hero; villain with valid argument; unresolved allegiance
- [[theory-of-mind-development]] — AToM milestones gate which archetypes (Shape Shifter, Trickster, false hero) are comprehensible
- [[2026-05-07-heros-journey-writing-guide]] — Source for Vogler's framework
- [[2026-05-07-propp-morphology-folktale]] — Source for Propp's 31 functions
- [[2026-05-07-art-of-storytelling-ai-models]] — Computational validation of Propp + Freytag
