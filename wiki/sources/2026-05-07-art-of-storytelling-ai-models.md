---
type: source
title: "The Art of Storytelling: Evaluating AI Models for Storytelling"
slug: 2026-05-07-art-of-storytelling-ai-models
date_ingested: 2026-05-07
source_type: paper
original_path: raw/papers/2409.11261v5.pdf
language: en
url: "https://arxiv.org/abs/2409.11261"
authors:
  - "Samee Arif"
  - "Taimoor Arif"
  - "Muhammad Saad Haroon"
  - "Aamina Jamal Khan"
  - "Agha Ali Raza"
  - "Awais Athar"
tiers_relevant: []
pipeline_stage: general
tags:
  - literacy
  - narrative-structure
  - interactivity
key_claims:
  - "A multi-agent AI system for co-creating multimodal children's stories uses Freytag's Pyramid and Propp's 31 narrative functions as its structural scaffolding."
  - "Gemma-2-9b is the strongest LLM for story generation quality across most metrics in human evaluation."
  - "Animated style (vs. cartoon or anime) scores highest on child-friendliness and overall text-video alignment."
  - "Scaling up LLM parameters does not guarantee better story quality — Gemma-2-27b underperforms Gemma-2-9b."
confidence: medium
---

## Summary

A computer science paper from LUMS/Michigan/EMBL presenting a multi-agent AI system that generates multimodal children's stories (text + audio narration + animated video + background music). The system structures stories using **Freytag's Pyramid** (5-act dramatic arc) and **Propp's 31 narrative functions** (see [[propp-morphology-folktale]]), which are combined as an interactive card-based UI. For Nabojo, this paper's value is twofold: (1) it demonstrates that Propp's functions can be computationally operationalised in AI story generation, and (2) it provides a human evaluation framework for AI-generated children's content. The multi-agent architecture (Writer + Reviewer agents) is also a relevant reference for Nabojo's own AI-assisted content pipeline.

## Key Findings / Arguments

1. **Propp's 31 functions + Freytag's Pyramid as computational story structure.** The system distributes Propp's functions (Interdiction, Villainy, Absentation, etc.) across Freytag's five phases. Users select cards representing Propp functions at each phase. This confirms that Propp's functions are directly usable as story generation constraints.
2. **Gemma-2-9b is the strongest story generation model** across grammar, linguistic consistency, appropriate language, structural consistency, creativity, and naturalness. GPT-4o-mini is strongest on grammar and naturalness specifically.
3. **Scaling does not help story quality.** Gemma-2-27b (larger) underperforms Gemma-2-9b (smaller) in pairwise human evaluations (25.67% win rate vs. 39.67% for 9b). This is relevant if Nabojo is evaluating LLMs for draft generation.
4. **Content moderation:** GPT-4o achieves the lowest false positive rate (incorrectly labelling appropriate content as inappropriate) at 9% Gutenberg / 0% synthetic. Most other models have higher FPRs.
5. **For animation style:** "Animated" free-form style scores highest on child-friendliness (1.80/2) and overall alignment. Anime scores highest on naturalism and temporal quality. Cartoon lags on most metrics.
6. **Multi-agent architecture:** Writer (Gemma-2-9b) + Reviewer (GPT-4o) + Narrator (XTTSv2) + Movie Director (GPT-4o) + Musician (MusicGen-Large) + Animator (CogVideoX-5b).

## Relevant Data

- 50 test prompts for story evaluation; 6 human evaluators (undergraduate CS students)
- Story quality metrics (0–2 scale): Grammar, Linguistic Consistency, Appropriate Language, Structural Consistency, Creativity, Adherence to Instructions, Naturalness
- Best overall model: Gemma-2-9b (wins most pairwise comparisons)
- Content moderation FPR: GPT-4o lowest (9%/0%), Gemma-2-27b highest (42%/12.5%)

## Tier Implications

*General pipeline methodology — no tier-specific implications.*

Actionable for Nabojo's AI pipeline design:
- Use Propp's functions as story generation constraints (validated computationally)
- Gemma-2-9b or GPT-4o-mini are the strongest current open/commercial models for children's story generation quality
- A Reviewer agent (GPT-4o class) should check Writer output for content appropriateness
- Do not assume larger = better for story generation

## Connections

- [[propp-morphology-folktale]] — Propp functions used as the structural scaffold
- [[narrative-morphology]] — this paper operationalises both Freytag + Propp
- [[trustworthiness-llm-children-stories]] — companion paper on LLM children's story quality

## Limitations / Bias

- Evaluators are English-speaking CS undergraduates from Pakistan — not French children or French-language literary experts.
- The system targets English-language stories; adaptations for French would require different models and validation.
- Paper is from 2024; model landscape evolves rapidly.

## Raw Quotes

> "The system is structured around two well-established storytelling frameworks: Freytag's Pyramid... and Propp's 31 narrative functions."

> "Simply scaling up parameter counts does not guarantee stronger performance in the downstream task of story generation. Gemma-2-9b outperforms its larger counterpart Gemma-2-27b."
