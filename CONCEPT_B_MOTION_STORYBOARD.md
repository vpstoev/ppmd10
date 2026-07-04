# CONCEPT B — MOTION STORYBOARD

**Concept:** PPMD IN MOTION · **Period:** 2016–2026
Companion to `CONCEPT_B_BLUEPRINT.md` (motion rules cited by name from Blueprint §11).

## Global scroll map

Approximate desktop scroll budget (~2 960vh ≈ 30 viewports). Positions below are
cumulative page scroll; each scene also states its **local** progress within its
section's scroll container.

| Section | Container | Cumulative range |
|---|---|---|
| 1 Hero | ~260–280vh, 280vh reference (100vh sticky stage) | 0 – 280vh |
| 2 Four Pillars | 260vh full build (100vh sticky stage) · **PoC: 180–210vh, hub + first focus only** | 280 – 540vh |
| 3 Head & Streams | 300vh (100vh sticky stage) | 540 – 840vh |
| 4 Team chapter (per team, on selection) | natural flow, ~250vh per team | interleaved after Streams |
| 5 Hot Topics ribbon | 140vh (100vh sticky) | ~1090 – 1230vh |
| 6 Journey 2016–2026 | 11 × 100vh snap | ~1230 – 2330vh |
| 7 Voices | 220vh | ~2330 – 2550vh |
| 8 Closing | 160vh | ~2550 – 2710vh |

**PoC scroll budget (Blueprint §22):** Hero (~260–280vh) + initial Pillars hub
(~180–210vh) — combined **≤ ~480vh**. The full Pillars four-node focus cycle
(Scenes 2.2–2.5) stays outside the first PoC.

Persistent elements: **NavRail** (all sections; ink inverts on dark scenes),
**DecadeMeter** (Journey only).

Conventions: `P` = local progress 0→1 within the section container. All animation
is scroll-linked (`useScroll`/`useTransform`) unless a duration is given (then it is
an activation animation using the named rule). "RM:" = reduced-motion fallback.

**SVG technique policy (Blueprint §8):** every "path morph" mention below is
constrained to the safe set — pre-authored compatible SVG paths + scroll-linked
`pathLength` + opacity crossfade between structural states + `transform` of SVG
groups. No runtime generation of complex path data. Path-`d` interpolation is
permitted only between paths explicitly authored with compatible point structures
and validated in the browser. **The PoC (Hero + Pillars hub) uses no path-`d`
morphing at all.**

---

## SECTION 1 — HERO · "The system comes to life" (Option H1, recommended)

### Scene 1.0 — Rest state (the first frame must land)
- **Scroll:** page top, `P = 0`
- **Visible:** the initial viewport already communicates **10-year anniversary ·
  PPMD · 2016–2026** — intentionally incomplete, not empty. On `--b-ground`:
  a monumental **ghost "10"** skeleton outline (`ghost-guide` rule) at **6–12%
  graphite opacity**, **~50–60vw wide**, off-center right — the destination
  suggested, never the completed state; the **active 2px graphite line** resting
  at the ghost's origin point (the pen); **`PPMD`** readable at statement-register
  scale near the numeral block (not a tiny decorative label) with
  **`2016 — 2026`** immediately readable beside it; small `A1` system label;
  NavRail node 1 active; a subtle scroll cue (`↓` + "scroll") bottom-center.
  Department full name still withheld (revealed on scroll).
- **Entering:** on load, the identity block + labels fade in (`section-enter`,
  opacity only); the resting line performs one 2s idle pulse
  (`scaleX 1 → 1.06 → 1`, `ease-system`) — the only timer-driven motion on the site.
- **Exiting:** —
- **Transform:** none yet.
- **Line/path:** live hero path at `pathLength 0` (only the resting tick shows);
  ghost 10 fully visible beneath — same authored geometry, second rendering. This
  point is the origin of the entire site line.
- **Typography:** `PPMD` at statement register; `2016 — 2026` at large
  system-label register; remaining labels uppercase, letterspaced.
- **Background:** `--b-ground`, static.
- **Interaction:** scroll; NavRail focusable/clickable from the start.
- **Mobile:** ghost ~80vw; `PPMD` + `2016 — 2026` stack at the top; same rest logic.
- **RM:** no idle pulse, no ghost; the full completed hero composition (drawn
  "10" + name + statement) is shown statically from load.

### Scene 1.1 — Drawing the "1" (act 1a)
- **Scroll:** `P = 0 → 0.20` (0–56vh)
- **Visible:** stage as 1.0; scroll cue fading (`opacity → 0` by `P=0.08`).
- **Entering:** the vertical stroke of the "1" draws upward, **directly over the
  ghost skeleton's "1"** — the ghost strokes fade out locally as the live line
  covers them.
- **Exiting:** scroll cue; the covered portion of the ghost.
- **Transform:** resting segment's endpoint becomes the pen; no element transforms,
  only the path extends.
- **Line/path:** `line-draw` scroll-linked — `pathLength 0 → 0.28` of the full hero
  path (the resting tick sweeps left-and-up into a single confident vertical stroke,
  ~46vh tall, tracing the ghost's "1" left-of-center of the numeral block).
- **Typography:** none new — `PPMD` + `2016 — 2026` persist from 1.0.
- **Background:** unchanged.
- **Interaction:** scroll only; scrubbing backwards reverses the draw (fully
  reversible throughout the hero).
- **Mobile:** same, stroke ~38vh tall.
- **RM:** n/a (static composition already shown).

### Scene 1.2 — Completing the "0" + the name begins (act 1b)
- **Scroll:** `P = 0.20 → 0.40`
- **Visible:** completed "1"; the pen continues over the ghost's "0".
- **Entering:** (a) the "0" as one continuous loop, drawn clockwise over the ghost
  skeleton; the numeral pair reads at ~55vw total width, off-center right;
  (b) **identity arrives early:** at `P 0.28–0.38` the department name band
  **"Project & Processes Management Department"** begins wiping in under the
  numeral via `type-reveal` (clip-path inset rise) — overlapping the 0's
  completion, so the visitor never scrolls through an unexplained screen.
- **Exiting:** the remaining ghost strokes (fully superseded by `P=0.40`).
- **Transform:** slight stage settle: whole SVG `y: 0 → -2vh` as the loop grows
  (keeps optical center); name band `y: 24 → 0` with its mask.
- **Line/path:** `pathLength 0.28 → 1.0` — the loop closes at `P=0.40`; stroke
  graphite 2px→3px (width via `strokeWidth` interpolation, not scale — keeps
  crisp joins).
- **Typography:** name at chapter-headline register — the first full-weight
  typography on the page; it must feel like an arrival.
- **Background:** unchanged.
- **Interaction:** scroll.
- **Mobile:** numeral ~80vw wide; name wraps to 2–3 lines.
- **RM:** n/a (static composition already shown).

### Scene 1.3 — Ignition + statement (act 2)
- **Scroll:** `P = 0.40 → 0.52`
- **Visible:** outlined "10" complete; name band settled.
- **Entering:** (a) color ignition: an SVG gradient stop sweeps along the path,
  graphite → **A1 red**, origin-outward over `P 0.40→0.50`; (b) the `PPMD`
  wordmark (visible since `P=0`) glides into the counter of the "0" and re-inks
  gold (group `transform` + color crossfade — no re-layout); (c) the supporting
  statement (≤2 sentences: growth, adaptability, customer focus, trusted
  delivery) rises via `type-reveal` below the name over `P 0.42–0.52`.
- **Exiting:** —
- **Transform:** `PPMD` group translate into the counter; statement mask rise.
- **Line/path:** fully drawn; stroke width 3→5px during ignition (hallmark moment).
- **Typography:** statement at section-statement register; `2016 — 2026` persists.
- **Background:** unchanged (light stays light; ignition is the color event).
- **Interaction:** scroll.
- **Mobile:** `PPMD` stays below the numeral (counter too small for the label).
- **RM:** static red "10" + name + statement shown from load; no sweep.

### Scene 1.4 — Composition completes + scale-down (act 3)
- **Scroll:** `P = 0.56 → 0.76` (`P 0.52–0.56` is a settle beat — composition
  holds complete)
- **Visible:** the complete hero composition: red "10", name band, statement,
  labels.
- **Entering:** nothing new — the composition *condenses*.
- **Exiting:** nothing yet.
- **Transform:** the whole hero group (numeral + name + statement) scales
  `1 → 0.82` and translates `y: 0 → -8vh`, scroll-linked — a controlled
  scale/position transformation making room and signalling "this scene is
  becoming an element".
- **Line/path:** unchanged shape; stroke 5→3px as it scales.
- **Typography:** unchanged; labels persist.
- **Background:** unchanged.
- **Interaction:** scroll.
- **Mobile:** acts 1.2–1.3 merge reveals (name + statement together at
  `P 0.3→0.55`); scale-down as desktop.
- **RM:** statement always visible; no scale.

### Scene 1.5 — The split (exit)
- **Scroll:** `P = 0.78 → 1.0` (hero's last ~62vh)
- **Visible:** condensed composition.
- **Entering:** four colored strands separate out of the "10"'s stroke at four
  anchor points (start of the 1, base of the 1, top of the 0, bottom of the 0):
  Delivery red, Process rose, Transformation blue-blend, Quality blue. The four
  strands are **pre-authored paths already present in the hero SVG**, revealed by
  scroll-linked `pathLength` + opacity crossfade from the numeral stroke — no
  runtime path generation, no path-`d` morphing (Blueprint §8 policy).
- **Exiting:** the graphite/red numeral outline thins to 1px and `opacity → 0.15`;
  name + statement exit upward (`section-exit`); labels persist into the next
  section (they are fixed-position chrome).
- **Transform:** the four strands extend downward past the viewport bottom edge,
  scroll-linked; their upper ends detach as the numeral fades.
- **Line/path:** the single hero path hands off to **four** pillar paths at
  documented anchors `20 / 40 / 60 / 80vw` (line contract §8) — both sections
  overdraw ~12vh so the strands are already visible when Pillars pins.
- **Typography:** hero type gone by `P=0.96`.
- **Background:** unchanged — continuity is the point.
- **Interaction:** scroll; NavRail transitions node 1 → node 2 (`nav-state`).
- **Mobile:** simplified — the numeral fades and a **single** stroke continues
  downward at 50vw; the four-way split happens at the top of the Pillars mini-map
  instead.
- **RM:** hard cut: hero composition ends, Pillars begins with paths pre-drawn;
  NavRail updates without animation.

---

## SECTION 2 — FOUR PILLARS · "One department, four disciplines"

### Scene 2.0 — Hub formation
- **Scroll:** `P = 0 → 0.22` (280–337vh cumulative). **PoC note:** the PoC builds
  only Scene 2.0 + Scene 2.1 (first focus) inside a **180–210vh** container;
  Scenes 2.2–2.5 are Phase 2, when the container grows toward 260vh.
- **Visible:** the four colored strands from the hero running down the stage.
- **Entering:** the **PPMD core node** (filled graphite circle, `PPMD` label) fades
  and scales in (`morph`-free: `opacity 0→1`, `scale 0.6→1`) at 42vw/50vh; the four
  strands' straight "falling" paths **opacity-crossfade into pre-authored
  connector paths** that dock into four **discipline nodes** placed asymmetrically
  around the core (two stacked authored path sets — no path-`d` interpolation,
  Blueprint §8 policy); chapter header "One department, four disciplines." wipes
  in top-left (`type-reveal`).
- **Exiting:** the strands' straight "falling" form (crossfaded out).
- **Transform:** node positions are static; the connecting paths swap via
  crossfade and finish drawing via `pathLength`.
- **Line/path:** four paths now core-to-node connectors; each keeps its discipline
  color at 2px; `pathLength` completes the final 15% of each connector as it docks.
- **Typography:** chapter index `01` + headline; node labels (Project Delivery,
  Process Excellence, Business Transformation, Testing & Quality) at small
  system-label size — not yet emphasized.
- **Background:** `--b-ground`; a very slight warm band (`--b-ground-2`) slides in
  behind the hub (`x: -8vw → 0`, opacity 0→1) to seat the composition.
- **Interaction:** all four nodes + core are focusable `<button>`s from the moment
  they exist; clicking a node jumps local scroll to its focus scene.
- **Mobile:** vertical mini-map forms instead — core node top-center, four nodes
  stacked down a winding single path.
- **RM:** hub shown complete and static; header plain-fades.

### Scenes 2.1 – 2.4 — Discipline focus cycle (one scene per node)
*(PoC scope: 2.1 only; 2.2–2.4 are Phase 2.)*
- **Scroll:** `P = 0.22 → 0.88`, quartered (~0.165 each): 2.1 Delivery,
  2.2 Process Excellence, 2.3 Business Transformation, 2.4 Testing & Quality.
- **Visible:** full hub at all times — inactive nodes never leave (interdependence).
- **Entering (per scene):** active node's description (1–3 sentences from
  `pillars.ts`) settles **along its connector path** (`section-enter`, 70ms
  stagger); active label scales to statement size.
- **Exiting (per scene):** previous node's description (`section-exit`, shortened
  to 240ms); its label returns to base size.
- **Transform:** `state-active` on the focused node (`scale 1 → 1.0`, full ink) vs
  `state-inactive` on the rest (35% opacity, `scale 0.96`); the **core pulses**
  once per focus change (`scale 1→1.12→1`, 480ms) — everything routes through PPMD.
- **Line/path:** active connector thickens 2→4px and re-draws (`line-draw`
  activation, 900ms) with a directional gradient core→node; inactive connectors dim
  to 35%.
- **Typography:** active label at statement register; description max ~34ch.
- **Background:** unchanged.
- **Interaction:** scroll steps focus; click/Enter on any node jumps focus (updates
  local scroll); arrow keys cycle nodes while the hub has focus; `aria-pressed`
  reflects the active node.
- **Mobile:** scroll focuses each stacked node in turn; description docks below the
  active node; same button semantics.
- **RM:** focus changes swap states instantly (opacity states kept); no pulse, no
  re-draw — connector color/width changes are instant.

### Scene 2.5 — Re-merge (exit)
*(Phase 2 — outside the PoC.)*
- **Scroll:** `P = 0.88 → 1.0`
- **Visible:** hub with last node focused.
- **Entering:** a single graphite path grows downward from the core at 50vw.
- **Exiting:** the four connectors retract into the core (`pathLength → 0`,
  reverse draw, scroll-linked); node labels fade; chapter header exits
  (`section-exit`).
- **Transform:** the core node translates toward top-center of the next section,
  scroll-linked — it will *become* the Department Head connector node.
- **Line/path:** handoff: single 2px graphite path exits at 50vw (contract §8).
- **Typography:** all pillar type gone by `P=0.97`.
- **Background:** unchanged.
- **Interaction:** scroll; NavRail → node 3.
- **Mobile:** mini-map path simply continues downward; core slides up-and-out.
- **RM:** cut to Streams with the connector pre-drawn.

---

## SECTION 3 — DEPARTMENT HEAD & TEAM STREAMS

### Scene 3.0 — The connector
- **Scroll:** `P = 0 → 0.2` (540–600vh)
- **Visible:** single graphite line arriving at top-center.
- **Entering:** the **Head node**: line docks into a gold ring; inside it the Head's
  portrait reveals via `portrait-activate` (mask expand) — generous scale (~28vh
  tall), never tiny; name + `Head of PPMD` label + one-line quote compose
  asymmetrically to the right of the node (`type-reveal`, staggered). Chapter
  header "Three teams, one direction." top-left.
- **Exiting:** —
- **Transform:** line-to-ring dock: preferred implementation is an opacity
  crossfade from the arriving path to a pre-authored docked path + ring
  (`pathLength` completing the circumference); path-`d` interpolation only if an
  explicitly authored compatible pair validates in the browser (Blueprint §8
  policy). Gold pulse once on dock (`scale 1→1.08→1`, 420ms).
- **Line/path:** stroke color graphite → gold over the last 10vh before the ring.
- **Typography:** name at statement size; quote at supporting size, real quotes
  from `people.ts` head entry.
- **Background:** `--b-ground`; warm band behind the Head block.
- **Interaction:** Head portrait is a button → DetailOverlay (`overlay-open`).
- **Mobile:** portrait ~35vw, text below it; same dock motion.
- **RM:** everything shown statically; overlay opens with plain fade.

### Scene 3.1 — The fan-out
- **Scroll:** `P = 0.2 → 0.35`
- **Visible:** Head block.
- **Entering:** three streams fan out downward from the ring's base:
  PM (red, to 25vw), PP (coral rose, 50vw), BPT (blue, 75vw). Each stream = an SVG
  path + a soft band fill that widens as it descends. Team codenames
  (`PM.module` / `PP.module` / `BPT.module`) ride the streams as small labels.
- **Exiting:** Head quote condenses (opacity → 0.6, stays legible).
- **Transform:** streams draw + widen; band fills scale via `scaleY` from their
  origin point.
- **Line/path:** one gold path splits into three colored paths (`line-draw`,
  scroll-linked, staggered 0 / 0.03 / 0.06 P-offsets so the fan reads as a gesture).
- **Typography:** codenames in system-label register; full team names appear in the
  focus scenes.
- **Background:** unchanged.
- **Interaction:** each stream is focusable/clickable from creation.
- **Mobile:** streams stack vertically (three slim horizontal bands); fan-out
  becomes a top-to-bottom cascade.
- **RM:** streams pre-drawn; no cascade.

### Scenes 3.2 – 3.4 — Stream focus cycle (PM → PP → BPT)
- **Scroll:** `P = 0.35 → 0.92`, thirds (~0.19 each).
- **Visible:** all three streams always on stage.
- **Entering (per scene):** focused stream expands to ~52vw (`stream-transition`:
  band `scaleX`, 480ms) and reveals: full team name (chapter-headline size, masked
  reveal), mission (1–2 sentences), 3 contribution labels as ticks **on** the
  stream line, live people count (`16 people` etc. — computed from `people.ts`), and
  an `Enter team →` affordance.
- **Exiting (per scene):** previously focused stream compresses to ~14vw
  (`stream-transition` reverse); its detail type exits via `section-exit` (fast,
  240ms).
- **Transform:** width changes are transform-driven (band `scaleX` with counter-
  scaled content container swap at midpoint — no text stretching); unfocused streams
  hold `state-inactive` (35% opacity) but their codenames stay legible.
- **Line/path:** focused stream's path thickens 2→4px; a slow directional gradient
  runs along it while focused (scroll-linked stop offset — "the stream flows").
- **Typography:** team name enters via `type-reveal`; contribution ticks stagger
  70ms.
- **Background:** a large ghosted team codename (e.g. `PM`) sits behind the focused
  stream at 8% ink, `x` parallax ±3vw, scroll-linked.
- **Interaction:** click/Enter on a focused stream (or its `Enter team →`) opens
  that **Team chapter** (Section 4) — the page expands in place below the streams;
  scroll and arrow keys move focus between streams; `aria-expanded` on stream
  buttons.
- **Mobile:** the focused band grows in height (not width); others compress to slim
  labeled bands; all three remain in viewport at the moment of focus change.
- **RM:** instant focus swaps; no flowing gradient; expansion is an opacity/state
  change with a single 200ms fade.

### Scene 3.5 — Merge toward the ribbon (exit, when no team chapter is open)
- **Scroll:** `P = 0.92 → 1.0`
- **Visible / Exiting:** the three streams bend toward center and braid into one
  tri-color path at 50vw; detail type gone; Head block released from sticky
  (scrolls away naturally).
- **Line/path:** three paths merge; the braid keeps three thin color strands
  running in parallel (2px each, 1px gap) — the department carries all three teams
  forward.
- **Background / Typography / Interaction:** unchanged; NavRail → next node.
- **Mobile:** bands collapse back into a single stroke at 50vw.
- **RM:** braid pre-drawn; cut.

---

## SECTION 4 — TEAM CHAPTER (entered by selection; one per team; natural scroll)

### Scene 4.0 — Chapter open
- **Scroll:** expands in place after the streams; ~250vh natural flow (no sticky).
- **Visible:** the selected stream's band widens to become the chapter **spine** —
  a vertical colored path down the whole chapter.
- **Entering:** chapter identity: codename, full name (headline, `type-reveal`),
  mission + story lines (from `teams.ts`), then the roster (4.1). `← All teams`
  return control pinned at chapter top and repeated at bottom.
- **Exiting:** the other two streams compress off-stage right/left (they remain in
  the DOM above, unchanged).
- **Transform:** open uses `overlay-open`-like inset expansion of the chapter
  region (`clip-path inset` + `opacity`, 380ms) — the chapter *unfolds* from the
  stream, no route change, no scroll jump.
- **Line/path:** the stream path re-draws as the spine (activation `line-draw`,
  900ms), team color, 3px.
- **Typography:** identity block at chapter scale.
- **Background:** `--b-ground` with a faint full-height band in the team color at
  4% behind the spine.
- **Interaction:** `← All teams` closes the chapter (reverse unfold, 280ms) and
  restores stream focus; focus management: opening moves focus to the chapter
  heading, closing returns it to the stream button.
- **Mobile:** chapter is full-width; spine hugs the left edge.
- **RM:** unfold = plain fade; spine pre-drawn.

### Scene 4.1 — The roster (contact sheet)
- **Scroll:** flows through the chapter.
- **Visible:** portraits on alternating sides of the spine, contact-sheet rhythm.
- **Entering:** portraits reveal as they enter the viewport, in spine order:
  `portrait-activate` mask expansion, 60ms stagger within a row band. Team Lead
  first and largest at the spine origin; PM chapter: the 2 Program Managers next at
  mid scale; then all members equal (order/tiers from `teamSections` +
  `sortOrder` — data-driven).
- **Exiting:** rows above simply scroll away (no forced exit animation — natural
  flow keeps the roster calm).
- **Transform:** each portrait's connector tick draws from the spine to the frame
  (`pathLength`, 240ms) as it reveals — every person is *on* the line.
- **Line/path:** spine `pathLength` tracks chapter scroll (fills as you meet the
  team); numeral stations (people count etc.) sit directly on the spine and count
  up ≤800ms when reached (tabular figures, no layout shift).
- **Typography:** names at supporting+, roles in system-label register; superpower
  line reveals on hover/focus (and is always visible on touch devices).
- **Background:** unchanged.
- **Interaction:** every portrait is a button → DetailOverlay (superpower, fun
  fact, contribution, quote; focus trap, `Esc`, restore). Overlay uses
  `overlay-open`.
- **Mobile:** single column; portraits ≥120px tall; spine on the left; superpower
  line always visible.
- **RM:** portraits appear without mask/stagger (plain, already-visible); counts
  render final values; overlay plain-fades.

### Scene 4.2 — Chapter close
- **Scroll / Interaction:** `← Back to all teams` (bottom) or `← All teams` (top).
- **Exiting:** chapter folds back into its stream (reverse of 4.0, 280ms); scroll
  position returns to the streams stage with the team still focused.
- **Line/path:** spine hands its `pathLength` state back to the stream band.
- **RM:** plain fade close.

---

## SECTION 5 — HOT TOPICS · the live portfolio ribbon

### Scene 5.0 — The turn
- **Scroll:** `P = 0 → 0.25` (~1090–1125vh)
- **Visible:** braided tri-color line arriving from the streams.
- **Entering:** the line **turns horizontal** across the stage and becomes the
  ribbon track — implemented as a crossfade between the vertical braid path and a
  pre-authored horizontal track path, with `pathLength` completing the turn
  (path-`d` interpolation only via an authored-compatible pair validated in the
  browser — Blueprint §8 policy); chapter header "What we're driving
  right now." (`type-reveal`); prev/next buttons + station dots fade in below.
- **Exiting:** braid's vertical form.
- **Transform:** the turn is one crossfade + draw; the ribbon's stations
  (initiative titles) slide in from the right at 40% opacity.
- **Line/path:** ribbon = the system line, now horizontal, 3px, graphite with
  team-color ticks at each station.
- **Typography:** station titles at statement size; stage tags (`In progress`,
  `Rollout`, …) as small chips; one-sentence detail under the active station only.
- **Background:** `--b-ground-2` band full-bleed behind the ribbon (slides up 8vh,
  opacity 0→1).
- **Interaction:** none yet (forming).
- **Mobile:** ribbon shows one station per view.
- **RM:** ribbon shown formed; header plain fade.

### Scene 5.1 — Riding the ribbon
- **Scroll:** `P = 0.25 → 1.0`; sticky stage; scroll advances stations one by one
  (scroll-linked `translateX` of the track with soft snap to station centers).
- **Visible:** ~2.5 stations; active station centered, full ink; neighbors ghosted
  40%.
- **Entering (per step):** next station slides to center (`translateX`, spring via
  scroll); its detail sentence rises (`type-reveal` at 80% scale); its team tick
  pulses once.
- **Exiting (per step):** previous station's detail collapses (opacity, 180ms);
  station ghosts.
- **Transform:** track `translateX` only; the line appears to slide through a fixed
  window.
- **Line/path:** the ribbon line translates with the track; station ticks in team
  colors (from Concept B `theme.ts`); variable item count (4–8) just extends the
  track.
- **Typography:** active title full ink graphite; stage chip in team color at AA
  sizes.
- **Background:** unchanged.
- **Interaction:** prev/next buttons (`aria-label`ed), left/right arrow keys when
  the region has focus, horizontal drag/swipe (pointer events → `translateX`,
  snapping on release), station dots as radio-style buttons. No autoplay. Scroll
  past the last station releases the sticky.
- **Mobile:** one station per view; swipe primary; buttons persist (44px targets).
- **RM:** stations advance with instant position swaps (no slide); scroll/buttons
  still step; detail appears without animation.

### Scene 5.2 — Drop to the decade (exit)
- **Scroll:** last 10% of the section.
- **Exiting:** ribbon chrome (buttons, dots, header) fades; the line detaches from
  the track at the final station and dives down-right (85vw) toward the dark.
- **Line/path:** exit anchor 85vw (contract); color returns to single graphite.
- **Background:** a graphite-dark wedge (`--b-dark`) begins rising from the bottom
  edge (clip-path polygon, scroll-linked) — the site's first dark transition.
- **RM:** hard background switch at the section boundary; line pre-drawn.

---

## SECTION 6 — JOURNEY · 2016–2026 exhibition (dark scene)

### Scene 6.0 — Entering the dark
- **Scroll:** first snap scene (2016), ~1230vh
- **Visible:** ground now `--b-dark`; the line arrives light (`--b-dark-ink`, 2px)
  from the top-right; NavRail + labels invert ink.
- **Entering:** chapter header "Ten years, told in motion." brief and exiting
  quickly; **2016** monumental numeral (~30vw, solid + gold edge — hallmark origin
  year) rises through a mask (`year-transition`); milestone title + one sentence
  settle right of it; **DecadeMeter** (`2016 ———●——— 2026`) fades in at the bottom
  edge and persists.
- **Exiting:** the light world (behind the rising dark wedge from 5.2).
- **Transform:** numeral `y: 80 → 0` with mask; statement staggers after (70ms).
- **Line/path:** the line bends behind the numeral and exits toward the next scene
  at an angle set by the alternating layout (layout A: exit lower-left).
- **Typography:** year at monument register (tabular); statement ≤ 2 lines.
- **Background:** `--b-dark`; no gradients — flat, exhibition-like.
- **Interaction:** natural scroll with `scroll-snap-type: y proximity` — snap
  assists, never traps; DecadeMeter is also a slider-like nav (each year a small
  anchor button).
- **Mobile:** year ~40vw; DecadeMeter moves to the top edge; snap retained.
- **RM:** snap retained; year/statement plain-fade ≤200ms; meter updates without
  easing; line static.

### Scenes 6.1 – 6.9 — 2017 … 2025 (nine scenes, alternating)
- **Scroll:** one 100vh snap scene per year.
- **Visible (per scene):** current year numeral (outlined stroke style for
  non-hallmark years), milestone title + sentence, DecadeMeter with `●` advanced,
  the line crossing the scene.
- **Entering:** incoming year via `year-transition` (mask rise + `y 80→0`, 520ms as
  the scene snaps in).
- **Exiting:** outgoing year `opacity → 0`, `y → -60` (520ms); its statement exits
  first (`section-exit`, fast).
- **Transform:** composition alternates three layouts (numeral left / right /
  center) cycling; the numeral of the *previous* year remains faintly visible for
  the first 15% of each scene (8% opacity) — years hand over, not hard-cut.
- **Line/path:** the line **bends direction** between scenes — each scene's segment
  enters at the previous exit point/angle (contract per scene); a small `●` travels
  the segment scroll-linked (the "now" of the story). 2020's scene may show the
  line briefly split and re-join (resilience note) — optional flourish, decided in
  implementation.
- **Typography:** outlined years for ordinary scenes; `major` years (from the new
  `journey.ts` data) get solid ink.
- **Background:** stays `--b-dark`; every third scene shifts value ±4% for
  breathing.
- **Interaction:** scroll; DecadeMeter year-dots jump-navigate; PageDown/PageUp
  work naturally with snap.
- **Mobile:** single layout (numeral top, statement below) with alternating
  numeral alignment only.
- **RM:** plain fades; previous-year ghost omitted.

### Scene 6.10 — 2026, the hallmark
- **Scroll:** final snap scene (~2230–2330vh).
- **Visible:** **2026** solid with gold edge (matches 2016 — the decade's
  bookends); statement is forward-looking (the next decade begins).
- **Entering:** 2026 via `year-transition` but 12% larger than other years; the
  DecadeMeter's `●` docks at its right end and the meter fills gold.
- **Exiting:** 2025 as usual.
- **Transform:** after the statement, the whole scene's ink warms slightly
  (`--b-dark-ink` → warmer white via color interpolation on a wrapper — done with
  opacity crossfade of two layers, not filters).
- **Line/path:** the line passes through the counter of the 0 in 2026 (echo of the
  hero) and exits bottom-center at 50vw, still light ink.
- **Typography:** year at maximum monument scale.
- **Background:** `--b-dark`, gold accents only in the meter + numeral edge.
- **Interaction:** scroll releases the snap region.
- **Mobile:** same, scaled.
- **RM:** plain fade; meter fills without animation.

---

## SECTION 7 — VOICES · the organizational chorus

### Scene 7.0 — Return to light
- **Scroll:** ~2330–2400vh
- **Visible:** the dark ground **wipes upward away** (clip-path polygon,
  scroll-linked) revealing `--b-ground`; the line converts light-ink → graphite as
  it crosses the boundary; NavRail re-inverts.
- **Entering:** chapter header "Voices from the organization." (`type-reveal`);
  thin branches begin growing off the main line (staggered `line-draw`
  activations, 600ms each).
- **Exiting:** the dark world.
- **Transform / Line / Typography / Background:** as above; background flat warm.
- **Interaction:** scroll.
- **Mobile:** identical, fewer branches (2).
- **RM:** hard light switch at the boundary; branches pre-drawn.

### Scene 7.1 — The chorus
- **Scroll:** ~2400–2520vh; soft-sticky stage; scroll (or buttons) advances the
  active voice.
- **Visible:** **one active quote** center-stage at statement scale with full
  attribution (name · role · department · relationship — `messages.ts` model);
  around it 3–4 **fragments** (short excerpts of the other quotes) at 30% opacity
  on the branch endpoints, each with a department context chip (Marketing,
  Technology, Customer Operations…).
- **Entering (per step):** the next voice's fragment travels its branch toward
  center (transform along the path — `offset-path` if supported, else interpolated
  x/y) while expanding to full quote via mask; attribution staggers in.
- **Exiting (per step):** the previous active quote contracts to a fragment and
  drifts to a free branch (reverse motion), staying visible in the chorus.
- **Transform:** center swap only ever moves two elements; the rest hold still.
- **Line/path:** branches pulse subtly (opacity 30→50%) when their fragment speaks.
- **Typography:** active quote may break to 3 lines max; fragments clamp to ~8
  words + ellipsis.
- **Background:** warm; a very light band behind the active quote.
- **Interaction:** prev/next buttons + dots (shared pattern with the ribbon);
  fragments are buttons (clicking one makes it the active voice); arrow keys when
  focused; no autoplay.
- **Mobile:** active quote full-width; 2 fragments stacked above/below; swipe
  advances.
- **RM:** instant swaps (fade ≤200ms); no travel motion; fragments still clickable.

---

## SECTION 8 — CLOSING · the loop

### Scene 8.0 — Gathering
- **Scroll:** ~2550–2630vh
- **Visible:** ground deepens to the second dark scene (`--b-dark`, or deep-warm
  graphite per PoC review) via a slow bottom-up wipe; the main line runs
  center-stage.
- **Entering:** the three team strands (red / rose / blue) converge from off-stage
  and **braid into the main line**, joined last by a gold strand from the Head —
  four colors running as one stroke.
- **Exiting:** Voices chrome.
- **Transform:** strand convergence scroll-linked (`pathLength` draws of
  pre-authored converging paths + opacity crossfades; authored-compatible morphs
  only per Blueprint §8 policy).
- **Line/path:** braided stroke 4px total, traveling toward center.
- **Typography:** none yet — the emptiest moment on the site (breathing before the
  finale).
- **Background:** dark, flat.
- **Interaction:** scroll.
- **Mobile:** identical, simplified to 2 visible strands + gold.
- **RM:** braid pre-drawn static.

### Scene 8.1 — The loop closes
- **Scroll:** ~2630–2710vh (page end)
- **Visible:** the braided line **curls into a closed loop** center-stage and
  reforms a compact "10" (~22vw) — the hero's numeral returned, now filled, gold-
  edged, complete.
- **Entering:** as the loop's last pixel closes (`pathLength → 1` exactly at
  `P=0.6`), the closing statement wipes in: **"10 years of PPMD — the best is
  still ahead."**; sub-line `Project & Processes Management Department ·
  A1 Bulgaria`; footer credit `Made by Valentin Stoev` in system-label register.
- **Exiting:** nothing — the page ends resolved; no CTA, no teaser.
- **Transform:** loop curl = `pathLength` draw of a pre-authored loop path,
  crossfaded from the traveling stroke (authored-compatible interpolation only if
  browser-validated — Blueprint §8 policy); statement `type-reveal`.
- **Line/path:** the site's line ends **closed** — no exit anchor. NavRail's final
  node fills gold.
- **Typography:** closing statement at chapter-headline scale, centered.
- **Background:** dark with the gold-edged 10 as the single light source (rendered
  with stroke color, not glow filters).
- **Interaction:** NavRail still allows jumping back to any chapter; end of scroll.
- **Mobile:** loop ~50vw; statement wraps to 2 lines.
- **RM:** completed loop + statement shown statically as the section scrolls in.

---

## Storyboard-wide fallback rules

- **Mobile (global):** every sticky stage uses `100svh`; hero 220vh, other pinned
  budgets ~-25%; four-way hero split deferred to Pillars; streams stack vertically;
  ribbon one-station; journey single layout; nav = chapter pill + overlay.
- **Reduced motion (global):** all `pathLength` lines pre-drawn; sticky stages
  collapse to natural flow where the pin exists only for animation (hero, pillars,
  streams, ribbon); every named rule falls back to ≤200ms opacity fade or instant
  state swap; snap and anchors remain; nothing auto-plays; content identical.
- **Reversibility:** every scroll-linked scene scrubs cleanly backwards; activation
  animations (900ms draws, pulses) are interruptible and never gate input.
- **PoC validation gate:** the PoC (Hero + initial Pillars hub) must pass the
  viewport/zoom/scroll acceptance matrix in Blueprint §22 — 1366×768, 1536×864,
  1920×1080 at 90/100/110% zoom; slow, fast and reverse scroll plus post-load
  resize; no Hero→Pillars seam, no clipped 10/name, no dead top state, no scroll
  lock or jump, and a complete, readable reduced-motion state.
