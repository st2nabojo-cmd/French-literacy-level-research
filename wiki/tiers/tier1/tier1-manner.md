---
type: tier-manner
tier: 1
age_range: "6–7"
school_level: "CP, CE1"
last_updated: 2026-05-07
sources_count: 5
tags:
  - tier1
  - manner
status: stable
---

## Tier Writing Profile

Tier 1 readers (ages 6–7, CP and early CE1) are in Chall's Stage 1: the decoding stage. The act of converting letters into sounds demands the vast majority of their cognitive bandwidth, leaving almost nothing for inferential comprehension, character tracking, or retention of complex sentences. Each sentence is effectively a separate processing event — there is no reserve capacity for holding the beginning of a sentence in mind while parsing its end. Working memory at this age supports approximately 3–4 chunks; a coherent sentence counts as 1 chunk. This means Tier 1 prose must be constructed with extreme economy: short sentences, familiar words, clear visual breaks. The page must never ask the reader to do two hard things at once. Paradoxically, children at this age have rich emotional lives and strong imaginative investment in story — they are not cognitively shallow, only cognitively occupied. The writing challenge is to deliver genuine narrative pleasure within severe formal constraints.

## Sentence Structure

| Dimension | Guideline | Rationale |
|-----------|-----------|-----------|
| Average sentence length | 5–8 words | Sits within the working memory chunk budget for Tier 1 (~3–4 chunks) |
| Maximum sentence length | 12 words | Above this, the end of the sentence overwhelms memory of the beginning |
| Subordinate clause nesting | 0 levels | A subordinate clause doubles the parsing demand — never appropriate at Stage 1 |
| Preferred construction | SVO dominant | Subject–Verb–Object is the most predictable and least demanding parse |
| Coordinating conjunctions | `et`, `mais`, `alors` only | These link two SVO clauses without embedding; `parce que`, `quand`, `si` are not yet appropriate |
| Sentence variety | Varied rhythm but constant simplicity | Alternate declarative, exclamatory, and one-word or two-word dialogue utterances to vary rhythm without adding complexity |

**Permitted constructions:**
- `Le chat mange la pomme.` — canonical SVO
- `Il court. Il saute. Il rit.` — staccato series; maximum rhythm variation within constraint
- `"Aide-moi !" cria Léa.` — short dialogue in direct speech; action verb as dialogue tag
- `C'est grand. C'est beau.` — attribute sentence; among the simplest in French

**Prohibited constructions:**
- Embedded relative clauses: *`Le chat que Léa aime mange...`*
- Temporal subordination: *`Quand il arriva, il vit...`*
- Indirect speech: *`Il dit qu'il voulait partir`* — requires tracking two time frames simultaneously
- Impersonal constructions: *`Il faut`, `Il s'agit de`* — abstract subject reference

## Vocabulary Level

```yaml
vocabulary:
  base_register: A1
  manulex_grade: G1
  manulex_lemma_pool: 6704
  max_new_words_per_page: 2
  new_word_introduction: always embedded in a concrete context with visual or narrative anchor
  avoid:
    - latinate abstractions (liberté, transformation, mystérieux)
    - words absent from MANULEX G1 without immediate contextual definition
    - polysemous words used in a non-primary sense (e.g., "battre" meaning to beat eggs vs. to hit)
    - anglicismes and loanwords without French anchoring
  favour:
    - high-frequency concrete nouns: maison, jardin, ami, chat, pomme, école
    - action verbs with visible referents: courir, sauter, manger, donner, prendre
    - simple sensory adjectives: grand, petit, rouge, chaud, doux
    - common discourse words: alors, voilà, oh!, non, oui, vite
```

A "new word" at Tier 1 is any word not in the MANULEX G1 high-dispersion set (words appearing across many different school texts, not just frequency within a single text). New words must be introduced with an immediate narrative or visual anchor — never as a definition, always as a demonstration. Two new words per page is the absolute ceiling; zero is often better. Repeated encounters with a small set of words build the MANULEX-level vocabulary faster than introducing breadth.

## Narrative Pacing

- **Scene length:** 150–300 words. Each scene is one event with one emotional beat. Do not combine two events or two emotional tones in a single scene.
- **Full story length:** 800–1,500 words. A Tier 1 story is the length of an early reader book (picture book chapter book crossover): 6–10 scenes maximum.
- **Beats per scene:** 1–2. A "beat" is a moment of emotional or narrative change — a decision made, a discovery, a surprise. One beat is the norm; two is the maximum.
- **Cliffhangers:** Yes, but micro-scale only. End a scene with a single intriguing sentence (`Mais alors, la porte s'ouvrit.`) — never a multi-paragraph buildup.
- **White space:** Short paragraphs of 2–4 sentences maximum. Dialogue lines are always their own paragraph. Never block paragraphs — visual breathing room is part of the decoding support.
- **Exposition ratio:** Maximum 30% of any scene can be pure description. Every scene must contain action. A child who is decoding cannot sustain pure description without narrative momentum.
- **Repetition with variation:** Deliberate structural repetition (refrain-style: same sentence each time a character appears, varied once at resolution) is a Tier 1 engagement technique, not a flaw.

## Grammar Rules and Constraints

- **Tense:** Présent de l'indicatif is the primary narrative tense. Passé composé may appear in dialogue for recent completed action (`"J'ai trouvé quelque chose !"`). Imparfait should be avoided as narrative tense — it requires temporal orientation Tier 1 readers are not yet managing.
- **Passive voice:** Avoid entirely. The passive requires a cognitively expensive parse-reversal (object-becomes-subject). Always rewrite as active SVO.
- **Negation:** `ne...pas` only (the canonical form). Never `ne...plus`, `ne...jamais`, `ne...rien` in embedded constructions. Spoken negation (`"C'est pas grave"` without `ne`) is acceptable in dialogue to match naturalistic register.
- **Relative clauses:** Not permitted. Replace with two short sentences: *`Il vit un chat. Le chat était petit.`* not *`Il vit un chat qui était petit.`*
- **Register — dialogue:** Always `tu` between child characters and with familiar adults. `Vous` only in ceremonial or comical contexts (a character being very formal). Child protagonists do not use formal register.
- **Pronouns:** Refer to characters by name or with clear pronouns only when the referent is unambiguous. At Tier 1 working memory, pronoun tracking across sentences collapses. When in doubt, repeat the name.
- **Questions:** Direct question form preferred (`Est-ce que tu veux venir ?` or inversion `Veux-tu venir ?` only in short utterances). Indirect questions (`Il se demandait si...`) are prohibited.

## Engagement Techniques

- **Direct address:** Use sparingly and only at choice points: `Et toi, qu'est-ce que tu ferais ?`. Outside choice points, direct address breaks narrative immersion without adding value.
- **Repetition with variation:** Accumulative sentence patterns (each scene adds one element to a repeating structure) are developmentally satisfying and reduce cognitive load. E.g., `Le lundi, Léo mange une pomme. Le mardi, Léo mange une poire. Le mercredi...` — variation highlights new vocabulary while structure remains constant.
- **Humour type:** Situational and absurdist. Physical comedy (a character falls into a bucket), comic role reversal (the small animal is the bravest), unexpected literal interpretation of a figure of speech. Wordplay (homophones, puns) should be limited to the most transparent examples — Tier 1 readers are not yet reliable metalinguistic thinkers.
- **Tension mechanics:** Raise stakes through simple obstacle accumulation. The reader must sense "what if it doesn't work?" without sustained dread. A tension beat resolves within 2–3 sentences.
- **Sound and rhythm:** French children's literature at this level uses alliteration, assonance, and rhythmic sentence patterns. These support decoding by making sounds predictable. Use them. *`Lili la lionne lèche son petit.`* is easier to decode than a sentence of equal complexity without phonological patterning.
- **Onomatopoeia:** Highly effective. `Plouf !`, `Crac !`, `Wouf !` — these are sight-readable, emotionally vivid, and cognitively free (no decoding stress). Use at emotional high points.
- **Chapter/section hooks:** End with a single sentence that promises the next event. Never a question that requires abstract reasoning. `Et c'est alors que Léo vit la porte.` — concrete and immediate.

## Interactive Choice Mechanics

> [!pipeline]
> **Tier 1 interactive choice specification:**
>
> - **Choice point frequency:** Once per story (short stories) or once every 3–4 scenes (episodic format). More frequent choices fragment the narrative without adding meaningful engagement — the reader needs to settle into the story before being asked to decide.
> - **Number of choices per point:** 2 only. A third option adds no engagement value and increases cognitive load. Choices must be visually and linguistically parallel.
> - **Choice framing language (French templates):**
>   - `Tu décides : est-ce que Léo va dans la forêt, ou est-ce qu'il rentre à la maison ?`
>   - `Qu'est-ce que tu choisis pour Léo ? La porte bleue, ou la porte rouge ?`
>   - `Et toi, tu aiderais qui ? Le chat ou le lapin ?`
> - **Voice at choice points:** Always 2nd person (`tu`). The narrator steps forward briefly to address the reader directly. Return to 3rd person immediately after the choice is made.
> - **Choice consequence weight:** Light to cosmetic only. The two paths rejoin within 1–2 scenes. A Tier 1 reader cannot hold the memory of a consequence across a long diverging narrative; choices must feel meaningful but not generate lasting divergence.
> - **Prohibited choice types:**
>   - Choices with a clearly "wrong" answer that causes the protagonist harm or distress
>   - Choices that require background knowledge the reader may not have
>   - Choices framed as moral dilemmas ("should Léo lie?") — moral reflection at this age requires unambiguous authorial framing, not reader-generated judgment

## What to Avoid

- **Sentences beginning with subordinate clauses:** *`Quand Léo arriva au jardin, il vit...`* — the subordinate clause delays the main actor and main verb; rewrite as two sentences.
- **Pronoun ambiguity:** If more than one character of the same gender has appeared in the last two sentences, always use the name, not `il` or `elle`.
- **Imperfect tense as primary narrative voice:** The imparfait (`il courait`, `elle chantait`) implies an ongoing state requiring temporal orientation. Use présent instead.
- **Abstract nouns as subject:** *`La tristesse de Léo...`* — abstract subjects are harder to track than concrete agent-subjects. Use `Léo était triste.` instead.
- **Irony and understatement:** These require holding two contradictory meanings simultaneously — a metalinguistic operation not available at Stage 1.
- **Foreshadowing across scene breaks:** Tier 1 readers do not reliably carry detail from scene to scene. Any planted clue must be restated at the moment of its payoff.
- **Ellipsis (...):** Evocative whitespace is a Stage 3+ technique. At Stage 1, unresolved trailing sentences create anxiety rather than intrigue.
- **Passive nominal phrases:** *`La capture du chat fut difficile.`* — nominal constructions compress information in ways that require syntactic unpacking; always rewrite as active verb constructions.

## Open Questions / Research Gaps

> [!question] What is the precise MANULEX G1 "safe list" for Tier 1 fiction? MANULEX provides frequency and dispersion data for G1 but no curated fiction-specific subset. A ranked list of the 500 highest-frequency, highest-dispersion G1 nouns, verbs, and adjectives would be the most valuable vocabulary resource for Tier 1 prompt engineering.

> [!question] How do Tier 1 French readers respond to interactive branching choices? No published research on choice-mechanic comprehension at ages 6–7 was found. Whether a 6-year-old reliably understands the concept of "choose your own path" — and whether the choice should be made verbally, by touch, or by a parent reading aloud — is unknown. This is a critical design gap for Nabojo's Tier 1 interactive mechanic.

> [!question] Does French orthographic opacity require even shorter sentences than English research suggests? French is more orthographically opaque than English at Stage 1 (inconsistent grapheme-phoneme correspondence). A French 6-year-old may need even more constraint than English research implies — but no French-specific sentence length data for early readers was found.

## Sources

- [[2026-05-07-chall-stages-reading-development]] — Stage 1 definition; all cognitive resources to decoding; familiar content essential
- [[2026-05-07-chunking-memory-working-memory-development]] — ~3–4 chunk capacity at age 7; each sentence = 1 chunk; no spare capacity for complex syntax
- [[2026-05-07-manulex-grade-level-lexical-database]] — G1 lemma pool (6,704); high-dispersion word selection; 2 new words per page maximum
- [[2026-05-07-picture-book-early-reader-chapter-book]] — Sentence-per-page constraint; 2–3 characters max; big typeface; ~800–1,500 word story length
- [[2026-05-07-eple-french-literacy-scale]] — French phonological awareness and letter knowledge; confirms decoding is the Tier 1 bottleneck (confidence: low — abstract only)
