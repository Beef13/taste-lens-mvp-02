---
name: generate
description: Rewrite a rough student brief into a Divisare-bar architectural image prompt. Use when user wants AI imagery for studio work — massing, interior, detail, or context view.
---

# Taste-Lens Generate v0.3

Anchors: Thornbury House (continuity + light), Carrickalinga Shed (precedent + section), Monty Sibbel (reveal + palette). Target: Divisare magazine quality. Default GPT output = slop.

## Required inputs (ask if missing)
- brief: what + where (site, orientation if known)
- constraint: heritage / existing bones / wind-sun / tiny footprint — at least 1
- view type: exterior sequence / interior / detail / courtyard-garden

## Rewrite rules — every prompt MUST include
1. **Constraint first:** name the limit shaping the form.
2. **Precedent transformed:** 1 named move (e.g. gable extrusion, courtyard removal, reveal beams) — never style words like "modern luxury".
3. **Section + light:** orientation + 2+ light sources (e.g. north garden opening + south polycarbonate glow / slot to sky / deep eave shade). No HDR sunset.
4. **≤3 honest materials with construction:** each material needs finish + thickness/junction + job + weathering. E.g. oiled spotted gum 20mm joinery feathered at edges as furniture; lime wash over plaster matched to gum trunks; 0.42mm gal corrugated iron folded over ridge as rain-skin into downpipe columns. Never generic "wood/concrete/stone". Never more than 3 primary materials. Never fake stone cladding, polished-everything concrete, or plastic timber grain.
5. **Garden/courtyard as room:** not backdrop — circulation, threshold, or divider. Planting must be site-specific landscape (gum canopy, native courtyard garden, protected vegetable garden) with ground + soil visible. Never decor plants.
6. **No decor vegetation:** BAN hanging pothos, trailing vines from shelves/ceilings, monstera in corner, fiddle-leaf fig, ivy covering facade to hide bad design. If planting appears, it is outside in ground, not hanging indoors. Interiors: no plants, or 1 potted native only if brief demands it.
7. **Camera intentional + restrained scope:** ONE view per image — one room, one threshold, or one detail. Never whole-house + interior + garden in one. 35mm equivalent, eye-level ~1.6m, straight verticals, natural soft daylight / overcast. No people, or 1 still figure from behind. No styling clutter, no wide-angle distortion.
8. **Finish specificity:** every material needs finish + job (e.g. oiled spotted gum joinery as furniture; lime wash matched to gum trunks; gal iron folded over ridge as rain-skin).

## Negative prompt (always append)
floating villa, parametric blob, moss-covered everything, white-box blue-sky render, HDR sunset, oversaturated, cluttered styling, ultra-wide distortion, drone view, blurred smiling entourage, grey LVP + downlights, random punched windows, paint-over-everything reno, glass-box panorama, whole-house-everything in one image, fake timber texture, fake stone cladding, polished concrete everything, plastic plants, hanging pothos plants, trailing vines from ceiling, monstera in corner, fiddle-leaf fig indoors, ivy covering facade

## Output format
1. Refined prompt (2-4 sentences, specific)
2. Negative prompt (line above)
3. Why: 2 bullets linking choice to anchors (e.g. "low eave like Carrickalinga for solar gain")

## Slop check before answering
If prompt lacks orientation, materials with jobs, or camera — rewrite again. Do not emit generic prompts.
