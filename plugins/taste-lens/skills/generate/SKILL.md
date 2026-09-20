---
name: generate
description: Rewrite a rough student brief into a Divisare-bar architectural image prompt. Use when user wants AI imagery for studio work — massing, interior, detail, or context view.
---

# Taste-Lens Generate v0.1

Anchors: Thornbury House (continuity + light), Carrickalinga Shed (precedent + section), Monty Sibbel (reveal + palette). Target: Divisare magazine quality. Default GPT output = slop.

## Required inputs (ask if missing)
- brief: what + where (site, orientation if known)
- constraint: heritage / existing bones / wind-sun / tiny footprint — at least 1
- view type: exterior sequence / interior / detail / courtyard-garden

## Rewrite rules — every prompt MUST include
1. **Constraint first:** name the limit shaping the form.
2. **Precedent transformed:** 1 named move (e.g. gable extrusion, courtyard removal, reveal beams) — never style words like "modern luxury".
3. **Section + light:** orientation + 2+ light sources (e.g. north garden opening + south polycarbonate glow / slot to sky / deep eave shade). No HDR sunset.
4. **≤3 honest materials with jobs:** e.g. gal corrugated iron folded over ridge; black timber to recede; white plaster neutral. No "concrete wood glass".
5. **Garden/courtyard as room:** not backdrop — circulation, threshold, or divider.
6. **Camera intentional:** eye-level, interior sequence, or detail crop. No drone-everything, no ultra-wide distortion.

## Negative prompt (always append)
floating villa, parametric blob, moss-covered everything, white-box blue-sky render, HDR sunset, blurred smiling entourage, grey LVP + downlights, random punched windows, paint-over-everything reno, glass-box panorama, ultra-wide drone view

## Output format
1. Refined prompt (2-4 sentences, specific)
2. Negative prompt (line above)
3. Why: 2 bullets linking choice to anchors (e.g. "low eave like Carrickalinga for solar gain")

## Slop check before answering
If prompt lacks orientation, materials with jobs, or camera — rewrite again. Do not emit generic prompts.
