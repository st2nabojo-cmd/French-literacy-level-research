---
type: source
title: "NABOJO — AI Context Reference"
slug: 2026-05-07-nabojo-context
date_ingested: 2026-05-07
source_type: report
original_path: raw/papers/nabojo_context.md.pdf
language: en
url: ""
authors:
  - "Nabojo Team"
tiers_relevant: []
pipeline_stage: general
tags:
  - literacy
  - interactivity
  - choice-mechanics
  - reading-motivation
key_claims:
  - "Children aged 7–19 in France spend an average of 3h11/day on screens vs. 19 minutes reading."
  - "38% of 16–19 year-olds in France do not read for pleasure."
  - "OECD 2022 data shows 15-year-olds are nearly a year behind in reading compared to 2018."
  - "Reading difficulties at age 7 multiply dropout risk at age 15 by 4×."
  - "Nabojo's interactive mechanic is a modern choose-your-own-adventure format on a dedicated e-ink reader."
confidence: high
---

## Summary

Nabojo is a French EdTech startup building interactive digital books for children aged 6–12 on a dedicated e-ink reader (€119.99) with no internet, no notifications, and no advertising. The product is a modern choose-your-own-adventure: branching narrative fiction where child choices affect story outcomes, delivered at adaptive reading levels. The business model is publisher-based (€1–3/book or €10/month subscription), not ad-based, explicitly refusing attention-capture mechanics. The document provides foundational context for all pipeline decisions: who the reader is, what the device affords, and why literary quality is non-negotiable.

## Key Findings / Arguments

1. **Reading crisis is quantifiable and urgent.** French children 7–19 spend 3h11/day on screens vs. 19 minutes reading. 38% of 16–19 year-olds read nothing for pleasure. OECD 2022 data shows 15-year-olds are nearly a year behind in reading level vs. 2018.
2. **Reading difficulties compound over time.** Reading difficulties at age 7 multiply school dropout risk at age 15 by 4×. Early intervention (ages 6–8) is the highest-leverage moment.
3. **The product is a dedicated, distraction-free e-ink reader.** No blue light, no notifications, no internet, no other apps. Session duration 20 minutes to 1 hour. Designed for daily use.
4. **Interactive mechanic is branching narrative (choose-your-own-adventure).** Child choices affect story outcomes. Multiple paths encourage replayability. AI matches child input to pre-written story branches — content is human-authored and expert-validated.
5. **Difficulty adaptation is built-in.** The device assesses reading level and adapts vocabulary and content difficulty. This means the wiki's tier system must be crisp enough to be operationalised as an adaptive parameter.
6. **Target ages 6–12 map precisely to our four literacy tiers.** Tier 1 (6–7), Tier 2 (7–8), Tier 3 (8–10), Tier 4 (10–12).
7. **Multimodal delivery: text, images, sound.** Sound is part of the experience; pacing and rhythm of text matters beyond silent reading alone.
8. **Content library goals:** mysteries, fantasy, dungeon adventures, licensed universes, French and European literary heritage. Professional authors, pedagogical expert validation.

## Relevant Data

- Average French child screen time vs. reading: **3h11 vs. 19 minutes/day**
- Non-readers (pleasure reading) aged 16–19: **38%**
- OECD reading level decline: **~1 year behind in 5 years** (2018–2022)
- Reading difficulty at 7 → dropout risk at 15: **4× multiplier**
- Device price: **€119.99** (one-time); content: **€1–3/book** or **€10/month**
- Session design: **20 min–1 hour**, daily use intended

## Tier Implications

*This is a general context document. No tier-specific implications. It grounds all tier decisions.*

All tier page decisions should be evaluated against: *Does this make a 6–12-year-old French child want to read the next page?*

## Connections

- [[tier1-matter]], [[tier1-manner]], [[tier2-matter]], [[tier2-manner]], [[tier3-matter]], [[tier3-manner]], [[tier4-matter]], [[tier4-manner]]
- [[choice-mechanics]] — Nabojo's core interactive mechanic
- [[reading-motivation]] — the product exists to solve a motivation crisis, not a skills crisis per se

## Limitations / Bias

- Internal company document — presents Nabojo's own framing of the problem; statistics should be verified against primary OECD sources.
- No specific information about the French curriculum alignment or how tiers are operationalised technically.

## Raw Quotes

> "Children aged 7-19 in France spend an average of 3h11 per day on screens vs. only 19 minutes reading."

> "38% of 16-19 year-olds don't read at all for pleasure."

> "Reading difficulties at age 7 multiply dropout risk at 15 by 4x."

> "Content is pre-written; AI helps match child's input to most relevant story branch. All AI-generated content reviewed by humans for quality and safety."

> "Give pre-teens the desire to read, making them better readers, improving their language skills, and helping them succeed in school and life." [Mission statement]
