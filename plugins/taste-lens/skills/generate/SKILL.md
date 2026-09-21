---
name: generate
description: Rewrite a rough student brief into a Divisare-bar architectural image prompt. Use when user wants AI imagery for studio work — massing, interior, detail, or context view.
---

# Taste-Lens Generate v0.5 — from test image 21 Sep

Anchors: Thornbury House, Carrickalinga Shed, Monty Sibbel. Lesson from test: image model ignores negatives, overfills frame, gives harsh sun + clutter. Fix with positive empty + overcast constraints.

## Required inputs (ask if missing)
- brief: what + where (site, orientation if known)
- constraint: heritage / existing bones / wind-sun / tiny footprint — at least 1
- view type: exterior sequence / interior / detail / courtyard-garden

## Rewrite rules — every prompt MUST include
1. **Constraint first:** name the limit shaping the form.
2. **Precedent transformed:** 1 named move (e.g. gable extrusion, courtyard removal, reveal beams) — never style words like "modern luxury".
3. **Section + light (positive only):** orientation + overcast soft daylight, no direct sun patches, no blown garden, pendant light off. E.g. "overcast north light through garden opening, soft polycarbonate glow south".
4. **≤2 timbers max, same family:** e.g. spotted gum joinery + ply ceiling only. Empty surfaces — "bare terrazzo floor, empty timber table, empty shelves, bare corners, no fruit, no vase, no books visible".
5. **Garden as room, no indoor plants:** planting only outside in ground. Interiors positive: "no indoor plants, empty floor corners".
6. **Camera + tight crop:** ONE volume only — crop out kitchen/living if dining. State exclusions positively: "dining volume only, no kitchen counter, no doorway glimpse". 35mm, eye-level 1.6m, straight verticals.

## Negative prompt (short — models mostly ignore it, so main prompt must already say empty/overcast positively)
HDR sunset, drone, ultra-wide, hanging plants, monstera indoors, cluttered styling

## Output format
1. Refined prompt (max 3 sentences, quiet + specific)
2. Negative prompt (line above)
3. Why: 1 bullet linking to anchor

## Slop check before answering
If prompt lacks orientation, materials with jobs, or camera — rewrite again. Do not emit generic prompts.
