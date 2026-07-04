# CONCEPT B — REFERENCE MATRIX

**Concept:** PPMD IN MOTION · Companion to `CONCEPT_B_BLUEPRINT.md` and
`CONCEPT_B_MOTION_STORYBOARD.md`.

How to read this: each reference is mined for **one or two load-bearing ideas**
that translate into a specific PPMD section, with the exact non-WebGL technique we
would use. Branding, layouts and assets are never copied — only interaction
grammar and storytelling structure.

Technical envelope for every "implementation without WebGL" row: semantic HTML,
SVG, CSS Modules, `motion/react` (`useScroll`, `useTransform`, `pathLength`),
`clip-path`/masks, `opacity`, `transform`. No canvas, WebGL, particles, Three.js
or new libraries.

---

## 1. Trionn

- **URL:** https://trionn.com/
- **Strongest relevant feature:** a confident, *bold interaction language* — every
  scroll gesture gets a decisive visual answer (scene-to-scene transitions, playful
  but tightly controlled motion, navigation that feels like part of the show).
- **How it applies to PPMD:** sets the bar for Concept B's transitions: sections
  never "arrive by fade" — the hero's four-way split, the pillar hub formation and
  the stream fan-out each answer scroll with one decisive gesture (Storyboard 1.5,
  2.0, 3.1). The NavRail's expand-on-focus behavior borrows Trionn's
  navigation-as-object attitude.
- **What must NOT be copied:** its Three.js/WebGL 3D showpieces, cursor gimmicks,
  agency tone, or its dark showreel aesthetic (Concept B is bright).
- **Implementation without WebGL:** decisive gestures = one scroll-linked
  `useTransform` chain per transition driving `transform` + `clip-path` on 2–3
  elements max; SVG state changes via pre-authored compatible paths (`pathLength`
  + opacity crossfade + group transforms; path-`d` morphing only between
  explicitly authored compatible point structures, per Blueprint §8 — never in
  the PoC); zero physics, zero 3D.
- **Relevant PPMD sections:** Hero exit, Four Pillars formation, NavRail,
  section-to-section transitions globally.

## 2. FacilPay

- **URL:** https://www.facilpay.io/
- **Strongest relevant feature:** *scroll-controlled storytelling* — content
  activates gradually under scroll control; sections **transform** into their next
  state rather than being replaced.
- **How it applies to PPMD:** the template for Concept B's sticky-stage sections:
  Hero acts 1–3 (draw → ignite → statement), the Pillars focus cycle and the
  Streams focus cycle are all "one stage, several scroll-scrubbed states"
  (Storyboard 1.1–1.4, 2.1–2.4, 3.2–3.4). Scrubbing backwards reverses the story —
  a FacilPay hallmark we adopt as a hard rule.
- **What must NOT be copied:** fintech/crypto visual identity, token imagery, its
  glow-heavy dark gradients, marketing-funnel CTAs.
- **Implementation without WebGL:** `position: sticky` stage inside a tall scroll
  container; `useScroll({ target })` + `useTransform` mapping local progress to
  `pathLength`, mask insets and transforms; all states reversible because they are
  pure functions of scroll position.
- **Relevant PPMD sections:** Hero, Four Pillars, Team Streams (the three big
  sticky stages).

## 3. TitanGate Equity

- **URL:** https://titangatequity.com/
- **Strongest relevant feature:** *oversized editorial typography* used as
  composition — masked text reveals, controlled tension between monumental
  headings and tiny labels, generous emptiness.
- **How it applies to PPMD:** defines Concept B's typographic register (Blueprint
  §7): monument numerals (the 10, journey years), chapter headlines revealed
  through `clip-path` bands, uppercase system labels as counterweight. The
  "typography behaves like an object" rule — headlines slide on bands, get sliced,
  sit in front of/behind the line — is TitanGate's editorial tension applied to a
  warm palette.
- **What must NOT be copied:** private-equity gravitas/coldness, its serif identity,
  near-monochrome palette, any literal layout.
- **Implementation without WebGL:** `clamp()`-scaled Geist Variable; `type-reveal`
  rule (`clip-path: inset` wipe + translate); SVG `<text>` with stroke for outlined
  numerals; masks via `clip-path` — no text effects libraries.
- **Relevant PPMD sections:** Hero name band, chapter headers everywhere, Journey
  year numerals, Closing statement.

## 4. ABVTEK

- **URL:** https://abvtek.com/
- **Strongest relevant feature:** *people presentation with dignity and rhythm* —
  large portraits, image transitions, varied framing that avoids the standard
  employee-card directory.
- **How it applies to PPMD:** shapes the Team Chapter roster (Storyboard 4.1):
  an editorial contact sheet with alternating placement around the team spine,
  varied crop heights, mask-expand portrait reveals, leadership expressed through
  scale/position *inside* the flow. The portrait-size floors (≥160px desktop /
  ≥120px mobile) and the "no repetitive grid" rule come straight from this
  reference's lesson.
- **What must NOT be copied:** its agency styling, hover distortion effects
  (WebGL-shader-based), specific crops or monochrome treatment of photos.
- **Implementation without WebGL:** `<img>` in a `PortraitFrame` with
  `clip-path`-masked frames (arch/rect variants), `portrait-activate` rule (mask
  inset expand + 1.03 scale), CSS `object-fit`/`object-position` for editorial
  crops, `loading="lazy"` + `srcset`.
- **Relevant PPMD sections:** Department Head block, Team Chapter roster, detail
  overlay imagery.

## 5. Jesko Jets

- **URL:** https://jeskojets.com/
- **Strongest relevant feature:** *full-screen pacing and journey feel* — one scene
  per viewport, strong scene-to-scene progression, confident typography, a real
  sense of travel through the page.
- **How it applies to PPMD:** the pacing model for the Journey exhibition
  (Storyboard 6.x): eleven full-viewport year scenes, snap-assisted, each with one
  monumental numeral + one statement, alternating composition so the eye travels.
  Also informs the global density rhythm — full scenes separated by breathing
  moments (Blueprint §5).
- **What must NOT be copied:** luxury-aviation imagery/tone, video backgrounds,
  dark glossy styling, any implication of exclusivity (this is an inclusive
  internal celebration).
- **Implementation without WebGL:** `scroll-snap-type: y proximity` on the
  exhibition wrapper; per-scene `useScroll` for the `year-transition` mask rises;
  numerals as SVG/text with `transform` + `opacity` handovers; no video.
- **Relevant PPMD sections:** Journey 2016–2026 (primary), overall page pacing.

## 6. SIMPAC

- **URL:** https://www.simpac.com/
- **Strongest relevant feature:** *corporate substance told as large thematic
  chapters* — a heavy-industry company presented through big visual scenes instead
  of dashboard-style corporate layouts.
- **How it applies to PPMD:** validates the core bet that serious internal content
  (disciplines, governance, quality) can live in large chapters with one message
  each. Directly shapes Four Pillars (a system map instead of feature cards) and
  the rule that team stats become numeral stations on the spine rather than KPI
  tile grids (Blueprint §9.2, §9.4).
- **What must NOT be copied:** industrial imagery, its literal chapter layouts,
  carousel patterns, corporate-blue identity.
- **Implementation without WebGL:** chapters as full-bleed `<section>`s with
  sticky stages; "thematic scene" = background band shifts (`--b-ground` ↔
  `--b-ground-2` ↔ `--b-dark`) driven by `clip-path` wipes and opacity, never
  image swaps.
- **Relevant PPMD sections:** Four Pillars, Team Chapter numbers, overall
  chapter architecture.

## 7. EternaCloud

- **URL:** https://www.eternacloud.com/
- **Strongest relevant feature:** **one continuous animated line** that travels the
  page, connecting otherwise different sections — abstract system visualization as
  flow-based storytelling.
- **How it applies to PPMD:** this is the load-bearing reference for Concept B's
  entire premise. The PPMD system line (Blueprint §8) does what EternaCloud's line
  does — but with narrative jobs per section: draws the 10, splits into
  disciplines, fans into teams, threads the people, carries the portfolio, walks
  the decade, closes the loop.
- **What must NOT be copied:** its cloud/infrastructure metaphors, glow/neon
  treatment, any canvas-rendered segments, its color world.
- **Implementation without WebGL:** the "one logical line, eight segments"
  architecture — per-section SVG `<path>` with scroll-linked `pathLength`
  (`stroke-dasharray` under the hood), a shared handoff contract (exit/entry
  anchors in vw + stroke state), ~12vh overdraw with `overflow: visible` to hide
  seams, gradient-stop animation for color morphs.
- **Relevant PPMD sections:** all eight — the global connecting element itself.

## 8. Mastercard Business Outcomes

- **URL:** https://www.mastercard.com/businessoutcomes/
- **Strongest relevant feature:** *immersive corporate storytelling of business
  impact* — outcomes presented as an experience in clear, outcome-oriented
  chapters rather than as claims in a grid.
- **How it applies to PPMD:** shapes how Concept B talks about *what the work
  achieves*: each Pillar focus states an outcome ("what A1 gets"), Hot Topics
  stations carry a stage + one outcome sentence, and Voices closes the loop by
  letting the rest of A1 state the impact in their own words (Storyboard 2.1–2.4,
  5.1, 7.1). One idea per scene, experienced in sequence.
- **What must NOT be copied:** its full WebGL/3D immersive complexity (explicitly
  out of scope), Mastercard branding, data-viz spectacle, marketing voice.
- **Implementation without WebGL:** outcome statements as staged `type-reveal`
  sequences bound to scroll; the "guided chapter" feel from sticky stages + snap;
  numbers as tabular-figure count-ups on `transform`/`opacity` only.
- **Relevant PPMD sections:** Four Pillars focus states, Hot Topics ribbon, Voices.

## 9. Hg — 25th Anniversary

- **URL:** https://25.hgcapital.com/
- **Strongest relevant feature:** **the anniversary narrative arc** — a milestone
  journey where history is continuously connected to future ambition, people and
  business growth carry the story together, and the site closes with a strong,
  resolved final scene. *Primary anniversary storytelling reference.*
- **How it applies to PPMD:** provides Concept B's dramaturgy end-to-end: open on
  the anniversary mark (the drawn 10), travel through what the organization is
  (disciplines → teams → people), show the present (hot topics), walk the decade
  (2016–2026 with hallmark bookend years), let others speak (voices), and close
  looking forward — "10 years of PPMD — the best is still ahead." The
  gold-hallmark treatment of 2016/2026 and the resolved, no-CTA ending are direct
  lessons from Hg's arc.
- **What must NOT be copied:** private-equity content framing (funds, returns),
  its visual identity, photography style, or its specific timeline UI.
- **Implementation without WebGL:** the arc is an information-architecture and
  choreography decision, not a technology: section order, the persistent
  DecadeMeter (`2016 ———●——— 2026`, position via `transform`), hallmark styling
  through stroke/fill tokens, and the closing loop as one final `pathLength`
  completion.
- **Relevant PPMD sections:** overall narrative arc, Journey, Closing (primary);
  Hero framing (secondary).

---

## Cross-reference summary by PPMD section

| PPMD section | Primary references | Secondary |
|---|---|---|
| Hero | EternaCloud (line), FacilPay (scroll control) | TitanGate (type), Trionn (exit gesture), Hg (anniversary mark) |
| Four Pillars | SIMPAC (thematic chapter), Trionn (formation gesture) | Mastercard (outcome focus), EternaCloud |
| Head & Streams | EternaCloud (flow), FacilPay (focus states) | ABVTEK (Head portrait) |
| Team Chapter / People | ABVTEK (portraits) | TitanGate (editorial rhythm), SIMPAC (numbers) |
| Hot Topics | Mastercard (outcomes), EternaCloud (ribbon = line) | Trionn (kinetic control) |
| Journey 2016–2026 | Jesko Jets (pacing), Hg (milestone arc) | TitanGate (year numerals) |
| Voices | Mastercard (impact told by others) | EternaCloud (branches) |
| Closing | Hg (resolved finale) | EternaCloud (loop), TitanGate (statement) |
| Navigation | Trionn (nav-as-object) | Hg (chapter orientation) |
