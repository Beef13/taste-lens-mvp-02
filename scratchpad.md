# taste-lens-mvp-02 — scratchpad

Repo status: scratchpad only, no code yet.

## Idea
"Taste" filter plugin for architecture students using ChatGPT/Codex.

Goal: AI outputs (images, design feedback) default to architecturally tasteful,
not generic slop. Seamless / complementary to studio workflow — students
shouldn't spend time fighting + fine-tuning to avoid slop.

Audience: architecture students integrating AI into workflow.

Scope v1:
- image generation guidance (prompts that produce disciplined work)
- design feedback / crit to a high architectural standard

## Platform notes (Sept 2026)
- Old 2023 ChatGPT plugin beta is dead (shut down April 2024).
- Current path = new Plugins system (ChatGPT + Codex share universal directory).
- Plugin = `plugin.json` + `skills/` + optionally `mcp.json` (MCP server) + assets.
- Custom GPTs being retired / migrated to plugins.
- MCP Apps are primary way to connect external services.

## Distribution without OpenAI approval
Public universal directory = requires submission + review.
Private / team use does NOT:
- repo marketplace: `plugins/<name>/` + `.agents/plugins/marketplace.json` in this repo,
  share via GitHub, others add with `codex plugin marketplace add owner/repo`
- personal marketplace: `~/.agents/plugins/marketplace.json`
- workspace publish: Plugins -> Personal -> Publish -> roles (admin only, stays in workspace)

Needs desktop app / Codex CLI to install local plugins. If plugin uses remote
MCP server, we still host + auth that ourselves.

## How taste-lens would work
Can't override image model directly. Plugin loads skills that steer it.

Proposed v1 — skills-only, no server:
1. `generate` skill: rough idea + site/brief/constraints -> refined image prompt
   + negative prompt. Bans slop tropes (parametric blob, moss-everything,
   white-box-blue-sky render, etc.). Forces material, tectonics, light,
   context, camera, drawing type. Grounds in precedents (Scarpa, Zumthor,
   Lacaton & Vassal, etc.).
2. `critique` skill: image / pin-up -> scored feedback on proportion,
   tectonics, context, material honesty, representation + next iteration.

Usage: `@taste-lens ...` or auto-load on relevant requests. New chat = same bar.

Later (optional): MCP server for curated library (reference images, briefs,
readings) so skill stays small and library is searchable.

## Taste bar (locked)
- Default ChatGPT image output = slop.
- Target = architectural magazine quality (El Croquis / Detail / AA standard).
- Canonical ref: https://divisare.com/ — Atlas of Architecture, slow web, curated
  image-by-image, no advertising/noise. Taxonomy we steal: Elements, Materiality,
  Plans & Details, Topics, Types. Photographer-credit culture, real light,
  real materials, honest context.
- Means: specific material + tectonic, controlled light, honest context,
  intentional camera / composition, restrained entourage, no render clichés.

## Anchor 1 — Thornbury House
- https://divisare.com/projects/532612-healy-ryan-architects-pier-carthew-thornbury-house
- Healy Ryan Architects, Melbourne 2024, photos Pier Carthew. 25sqm rear addition
  to weatherboard bungalow, heritage overlay.
- Rules extracted:
  1. continuity over distinction: new gable traces old pitch/ridge, modern but anchored
  2. constraint as generator: heritage street untouched, tiny footprint, efficiency
  3. light as material: north opening to garden, south polycarbonate glow, slot to sky,
     afternoon sun to bookshelf — different tones through day
  4. small moves, big effect: courtyard divider + timber bridge between kids rooms,
     dark hall becomes light passage
  5. dwelling values: simplicity, natural light, landscape connection over formal gymnastics
- Anti-slop: no floating form, no HDR sunset, no moss covering, no blurred family entourage.
  Eye-level / interior sequence photography, honest materials.

## Anchor 2 — Carrickalinga Shed
- https://divisare.com/projects/512996-architects-ink-thurston-empson-carrickalinga-shed
- Architects ink, Carrickalinga 2023, photos Thurston Empson. 55-acre ex-dairy farm,
  off-grid, highest vantage, views to peninsulas + sea + protected garden.
- Rules extracted:
  1. precedent with transformation: 19th-c French farmhouse -> Federation farmhouse
     -> Roman Postica courtyard villa. Not copy, manipulated: 24m square, centre removed
  2. section does the work: verandah on 'wrong' side, inverted roof, low eave to garden
     for solar gain/access, pyramid funnel roof harvesting rain via columns as downpipes
  3. enfilade + dual aspect: apertures aligned/removed opposite sides (de Witte ref),
     every room to distant view + courtyard, industrial shutters tune light/views/seasons
  4. material honesty: gal corrugated iron folded over ridge + lining roof, black
     reconstituted timber courtyard (recede/shadow), white plaster inside, loose fireplaces
  5. place + performance: true to place, minimal landscape impact, passive sustainability
     as hero, not gadget — client: silence, serenity, star-filled bedrooms
- Anti-slop: no object-on-landscape villa, no glass-box panorama. Courtyard fortification,
  seasonal camping/year on site, wind/sun as form-givers.

## Anchor 3 — Monty Sibbel House
- https://divisare.com/projects/491135-nuud-studio-tom-ross-monty-sibbel
- Nuud Studio, Melbourne 2023, photos Tom Ross. Renovation/restoration of tired
  1970s Sibbel home under gum canopy for young family.
- Rules extracted:
  1. reveal > replace: oregon beams exposed spanning width, cedar windows sanded
     back + double-glazed + insulated, brick flue restored to working fireplace
  2. pared-back palette from site: spotted gum joinery/floors, lime wash tuned to
     gum trunks, native timbers only. New joinery feathers at edges as furniture
  3. plan clarity: living runs open across house split by flue, full-height north
     glazing under deep parasol eaves to garden, private rooms south in parallel
  4. small alterations, big inhabitation: bathroom shift, living-to-rear-yard link,
     inhabiting bush garden not extending footprint
  5. lineage: 1970s handmade environmental revolt vs automation — affordable modern
     Australian home, search of the land
- Anti-slop: no paint-over-everything reno, no open-plan-everything, no grey LVP +
  downlights. Deep eaves, real shade, eye out to garden.

## Triangulated draft rubric (v0)
All 3 anchors agree — this is the taste-lens:
1. constraint first (heritage / wind+sun / existing bones)
2. precedent transformed, not styled (gable extrusion / Postica courtyard / Sibbel reveal)
3. section + light specified (orientation, 2+ sources, eave/shutter/slot)
4. ≤3 honest materials with jobs (iron/timber/plaster, gum palette)
5. courtyard/garden as room, not backdrop
6. photography: eye-level, sequence, no HDR, no entourage mush

## Open questions
- image vs text crit priority for MVP?
- studio-tested prompts to encode first?
