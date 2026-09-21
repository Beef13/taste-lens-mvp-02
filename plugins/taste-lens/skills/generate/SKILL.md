---
name: generate
description: Rewrite a rough student brief into a Divisare-bar architectural image prompt. Use when user wants AI imagery for studio work — massing, interior, detail, or context view.
---

# Taste-Lens Generate v0.4 — simplified after v0.3 regression

Anchors: Thornbury House, Carrickalinga Shed, Monty Sibbel. Target: Divisare magazine quality. Lesson: shorter prompts beat overloaded specs.

## Required inputs (ask if missing)
- brief: what + where (site, orientation if known)
- constraint: heritage / existing bones / wind-sun / tiny footprint — at least 1
- view type: exterior sequence / interior / detail / courtyard-garden

## Rewrite rules — every prompt MUST include
1. **Constraint first:** name the limit shaping the form.
2. **Precedent transformed:** 1 named move (e.g. gable extrusion, courtyard removal, reveal beams) — never style words like "modern luxury".
3. **Section + light:** orientation + 2+ light sources (e.g. north garden opening + south polycarbonate glow / slot to sky / deep eave shade). No HDR sunset.
4. **≤3 honest materials:** name finish + job only. E.g. oiled spotted gum joinery; lime wash matched to gum trunks; gal iron folded over ridge. No generic wood/concrete/stone.
5. **Garden as room, no decor plants:** planting only outside in ground (gum canopy / native courtyard). Interiors: no plants. BAN hanging pothos, trailing vines, monstera corner, ivy facade.
6. **Camera + one view:** ONE room / threshold / detail per image. 35mm, eye-level 1.6m, straight verticals, soft daylight. No wide-angle, no drone, no styling clutter.

## Negative prompt (always append, keep short)
HDR sunset, drone view, ultra-wide distortion, parametric blob, floating villa, fake timber, plastic plants, hanging plants, monstera indoors, ivy covering facade, blurred entourage, cluttered styling

## Output format
1. Refined prompt (max 3 sentences, quiet + specific)
2. Negative prompt (line above)
3. Why: 1 bullet linking to anchor

## Slop check before answering
If prompt lacks orientation, materials with jobs, or camera — rewrite again. Do not emit generic prompts.
