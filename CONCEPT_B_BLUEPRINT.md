# CONCEPT B — BLUEPRINT

**Working title:** PPMD IN MOTION
**Branch:** `alternative-concept-v2` · **Status:** blueprint only — no implementation code exists yet
**Concept A remains untouched:** `src/AppPrototype.tsx`, `src/AppPrototype.module.css`, branch `archive/approved-ppmd-v1`, tag `approved-ppmd-v1`

---

## 1. Concept name

**PPMD IN MOTION** — *a living organizational system.*

## 2. Design narrative

PPMD is not five stacked chapters; it is one system in continuous motion. For ten years
(2016–2026), projects, processes, transformation, quality and people have moved together
to help A1 grow, adapt and deliver.

The whole site is carried by **one continuous line** — a graphite/red system line that:

1. **Hero** — draws and completes the anniversary "10"
2. **Four Pillars** — separates into four connected discipline paths
3. **Teams** — reconnects through the Department Head, then divides into three team streams
4. **People** — threads through the portraits and roles of every colleague
5. **Hot Topics** — becomes the live portfolio ribbon of what the department drives now
6. **Journey** — becomes the 2016–2026 decade path
7. **Voices** — carries the organization's feedback back into the system
8. **Closing** — closes the loop and reforms the "10"

Nothing "appears"; everything **transforms out of what came before**. The user never
enters a new section — the system evolves under them.

## 3. Comparison with Concept A

| Dimension | Concept A (approved, archived) | Concept B — PPMD In Motion |
|---|---|---|
| Atmosphere | Dark cinematic editorial, black/red, film grain | Bright kinetic system; warm off-white foundation; dark used only for 2–3 selected contrast scenes |
| Structure | Pinned dark hero, content panel slides over it; chapters stacked | One continuous scroll narrative; sections hand the system line to each other |
| Hero | Static monumental "10 YEARS" lockup, layered parallax depart | Line **draws** the 10 live under scroll control; the 10 then splits into the four discipline paths |
| Pillars | Featured card + selector tabs | Central hub / system map — four connected nodes around a PPMD core, no cards |
| Teams | Head card + three team cards in a row | Head as connector node; three colored **streams** (red / coral rose / blue) that expand on focus |
| People | Card roster grouped by role tier | Editorial portrait composition on connected lanes — no card wall |
| Hot topics | Conventional carousel | Kinetic horizontal portfolio ribbon riding the system line |
| Timeline | Vertical rail with milestone cards | Full-viewport scroll-snap exhibition, giant year typography, 2016–2026 |
| Voices | Three quote cards | One active voice + surrounding chorus fragments on the line |
| Color | Black, A1 red, warm team accents (red/magenta/coral), gold hallmarks | Warm architectural neutral + graphite ink; PM = A1 red, PP = coral rose, BPT = blue, Head = warm metallic gold-graphite |
| Shape language | Rectangles, cards, glows | Lines, bands, masks, paths; very few rectangles |
| Typography | Large display over dark | Typography as physical object: oversized editorial headings, sliced/masked reveals, monumental numerals |

**Deliberate continuity with A:** same data model, same accessibility bar, same
performance-safe motion vocabulary (`motion/react`, `useScroll`, `useTransform`),
same content template lineage — so content collected once serves both concepts.

## 4. Reference synthesis

Full per-site analysis lives in `CONCEPT_B_REFERENCE_MATRIX.md`. The synthesis:

- **Hg Capital 25** is the narrative spine reference: an anniversary told as one
  continuous story from origin to ambition, closing strong. Concept B borrows the
  *dramaturgy* (past feeds future, people carry the story), not the visuals.
- **EternaCloud** proves the core device: one continuous animated line connecting
  otherwise different scenes. We adopt the device with SVG + `pathLength` only.
- **Trionn + Jesko Jets** set the interaction bar: confident scene-to-scene pacing,
  playful but controlled motion, typography with physical presence — achievable
  without WebGL via transforms, masks and scroll-linked values.
- **FacilPay** contributes scroll-controlled *transformation* of sections (content
  activates gradually rather than appearing).
- **TitanGate** contributes the editorial typographic register: oversized headings,
  masked reveals, controlled tension between huge type and small labels.
- **ABVTEK** informs people presentation: large, dignified portraits with rhythm and
  transitions instead of an employee-card directory.
- **SIMPAC** informs how corporate substance becomes thematic chapters, not dashboards.
- **Mastercard Business Outcomes** informs outcome-oriented storytelling for the
  Pillars and Hot Topics chapters — impact as an experience, minus the WebGL.

## 5. Visual language

- **Foundation:** warm off-white, architectural — the site feels like a bright
  exhibition hall, not a screen.
- **The line is the protagonist.** Everything meaningful is connected to, revealed by,
  or transformed from the continuous system line.
- **Bands, not boxes.** Content sits on horizontal/vertical bands, lanes and paths.
  Rectangles with borders/shadows (cards) are the exception, reserved for the detail
  overlay only.
- **Masks over fades.** Typography and portraits reveal through `clip-path` wipes and
  layered masks — content feels *uncovered*, not faded in.
- **Density breathing.** Dense system moments (hub, roster, ribbon) alternate with
  near-empty breathing scenes (single sentence on warm ground) so the eye rests.
- **Selective dark.** Exactly two scenes flip to graphite-dark for contrast: the
  Journey exhibition (2016–2026) and the final loop-closing scene. Everything else
  stays light.

## 6. Color system

All tokens are **new and scoped to Concept B's root** (`AppAlternative.module.css`),
so nothing leaks into Concept A. Concept A's team accent hexes in `teams.ts`
(`accentHex`) are **not reused** — Concept B defines its own accent map keyed by `TeamId`.

| Token | Value (proposal) | Use |
|---|---|---|
| `--b-ground` | `#F6F2EC` | Warm off-white page ground |
| `--b-ground-2` | `#EFE9E0` | Secondary band / alternating scene ground |
| `--b-ink` | `#23262B` | Graphite typography & the neutral state of the line |
| `--b-ink-soft` | `#5A5E66` | Supporting copy, labels |
| `--b-red` | `#E2001A` | A1 red — Project Management stream, primary brand moments, hero accent |
| `--b-rose` | `#E4586E` | Coral rose — Process & Procedures stream |
| `--b-blue` | `#1F6FEB` | Blue — BPT & Testing stream |
| `--b-gold` | `#B08A4A` | Department Head identity (warm metallic, paired with graphite) |
| `--b-dark` | `#191B1F` | Ground of the two dark scenes (Journey, Closing) |
| `--b-dark-ink` | `#F3EFE8` | Ink on dark scenes |
| `--b-line` | `currentColor`-driven | The system line inherits scene context; morphs graphite → discipline color → team color → gold → back |

Rules:

- A1 red is **both** the PM stream color and the brand accent; in brand moments
  (hero, closing) it appears on the line itself.
- The four **discipline paths** in Pillars use: Delivery `--b-red`, Process `--b-rose`,
  Transformation a graphite-blue blend (`#3B5BDB` tint of `--b-blue`), Quality `--b-blue`.
  This foreshadows the team mapping (Delivery→PM, Process→PP,
  Transformation & Quality→BPT) without pretending there are four teams.
- Gold is reserved for the Department Head and the anniversary hallmark moments
  (the completed "10", the 2026 year scene) — never decorative elsewhere.
- Contrast: all ink-on-ground pairs must pass WCAG AA at their used sizes
  (`#23262B` on `#F6F2EC` ≈ 13.5:1; stream colors used for **large** type/graphics
  only, with graphite fallback for small text).

## 7. Typography system

Typeface: **Geist Variable** (already a dependency — `@fontsource-variable/geist`).
No new fonts in phase one; editorial character comes from scale, weight contrast,
tracking and composition, not from a new family.

| Role | Spec (proposal) |
|---|---|
| Monument numerals (hero "10", journey years) | `clamp(9rem, 28vw, 26rem)`, weight 650, tabular, tight tracking `-0.04em`; rendered as outlined SVG text or masked solid |
| Chapter headline | `clamp(2.8rem, 7vw, 6.5rem)`, weight 600, line-height 0.98 |
| Section statement | `clamp(1.6rem, 3.2vw, 2.6rem)`, weight 500 |
| Supporting copy | `1.0–1.125rem`, weight 400, max ~34ch measure |
| System labels (chapter index, year range, roles) | `0.75–0.8125rem`, weight 500, uppercase, tracking `+0.14em` |

Behavioral rules:

- Headlines are **objects**: they slide on bands, get sliced by `clip-path`, sit
  behind/in front of the line, change scale on scroll. They never simply fade in.
- Numerals (10, years, counts) always use tabular figures and are allowed to be
  cropped by the viewport edge — scale over completeness.
- No dashboard typography: no small dense stat grids, no data-table registers.
- Body copy is short by contract — the content template caps supporting text at
  1–2 sentences per scene.

## 8. Continuous-line system

**One logical line, eight segments.** A literal single SVG spanning an ~30-viewport
page is fragile (huge path data, one giant repaint region). Instead:

- Each section owns **one SVG segment** (`<LineSegment>` component) with its own
  scroll-linked `pathLength` draw.
- **Handoff contract:** every segment *exits* its section at a documented horizontal
  anchor (in `vw`) and stroke state (color, width), and the next segment *enters* at
  the same anchor and state. Anchors live in one shared constant
  (`src/alternative/lineContract.ts` — part of implementation phase, named here for
  the contract's sake) so the illusion of one continuous line is enforced in one place.
- Between sections, the line crosses the section boundary visually because both
  segments overdraw ~12vh into the neighboring section (SVG `overflow: visible`,
  `pointer-events: none`).
- Stroke width: 2px at rest, up to 6px in hero/closing hallmark moments.
- Color morphs happen **inside** segments via SVG `<linearGradient>` stops or by
  crossfading two stacked paths — never mid-handoff.

Evolution table:

| # | Section | Line behavior | Exit anchor |
|---|---|---|---|
| 1 | Hero | Draws/activates the "10"; graphite → red at completion | splits into 4 paths at `20 / 40 / 60 / 80vw` |
| 2 | Four Pillars | Four discipline paths orbit and connect to the PPMD core node | re-merges to single path at `50vw` |
| 3 | Teams | Passes through the Head node (gold pulse), fans into 3 streams | 3 lanes at `25 / 50 / 75vw` |
| 4 | Team chapter / People | Active team's lane threads through the portrait composition | returns to `50vw` |
| 5 | Hot Topics | Becomes the horizontal portfolio ribbon (the one horizontal moment) | drops down at `85vw` |
| 6 | Journey | Becomes the decade path; bends direction at each year scene | `50vw`, now light-on-dark |
| 7 | Voices | Carries quote fragments toward the active voice | `50vw` |
| 8 | Closing | Curls into a loop and reforms a compact "10" | closed loop — no exit |

Technical envelope (hard limits): semantic HTML, SVG, CSS Modules, `motion/react`
(`useScroll`, `useTransform`, `pathLength`), `clip-path`, masks, `opacity`,
`transform`. **No canvas, no WebGL, no particles, no Three.js, no new libraries.**

**SVG technique policy (anti-fragility):** the concept must not depend on
arbitrary interpolation of SVG path `d` data. Allowed techniques, in order of
preference:

1. **pre-authored compatible SVG paths** revealed by scroll-linked `pathLength`;
2. **opacity crossfade** between structural states (two stacked pre-authored paths);
3. **`transform` of SVG groups** (translate/scale/rotate of whole path groups);
4. **split/branch paths that already exist in the markup** and reveal
   progressively (e.g. the hero's four split paths).

**No runtime generation of complex path data.** Path-`d` morphing may be used
*only* where the two paths are explicitly authored with compatible point
structures (same command count and order) and validated in the browser before
being kept — and never in the PoC (§22).

## 9. Section-by-section composition

Scene-level scroll choreography is in `CONCEPT_B_MOTION_STORYBOARD.md`; this section
defines composition and information design.

### 9.1 Hero — "The system comes to life"

Radically different from Concept A: no pre-built "10 YEARS" lockup, no dark
full-screen composition, no bottom copy strip.

**Sticky stage:** hero is a `~260–280vh` scroll container (280vh reference value)
with a `100vh` sticky stage. (Reduced from 320vh after review — the hero must not
feel slow or scroll-hijacked; see the PoC scroll budget in §22.)

**Option H1 — "The Drawn Ten" (recommended)**

- Initial state (0 scroll) — **intentionally incomplete, never empty.** The first
  frame must already communicate: a 10-year anniversary, PPMD, 2016–2026, and a
  premium visual identity. On the warm off-white ground:
  - a **ghost "10"** — the full numeral's skeleton outline, pre-rendered at
    **6–12% graphite opacity**, occupying **~50–60vw** on desktop, off-center
    right. It suggests the destination without showing the completed state
    (`ghost-guide` rule, §11). Same geometry as the live hero path — one authored
    path, two renderings.
  - the **active 2px graphite line** resting at the ghost's origin point — the pen
    that will draw directly over the ghost structure.
  - **`PPMD`** visibly readable from the initial viewport, at statement-register
    scale near the numeral block — not an extremely small decorative label.
  - **`2016 — 2026`** immediately readable, paired with the PPMD wordmark.
  - small retained chrome: `A1` system label, scroll cue.
  - The department **full name stays withheld** until the scroll reveal —
    restraint lives in the name, not in the anniversary mark.
- Scroll act 1 (`P 0–0.40`): the line **draws the "1"** (`P 0–0.20`, single
  confident vertical stroke) then **completes the "0" as one continuous loop**
  (`P 0.20–0.40`) — always directly over the ghost skeleton, whose strokes fade
  out locally as the live line covers them. The 10 is outlined, monumental
  (~55vw wide), slightly off-center right.
- Scroll act 2 (`P 0.28–0.52`) — identity arrives early: the department name
  **"Project & Processes Management Department"** begins wiping in through a
  `clip-path` band at `P 0.28–0.38` (overlapping the 0's completion); the stroke
  ignites graphite→A1 red from the origin outward as the loop closes
  (`P 0.40–0.50`, gradient stop animation); the `PPMD` wordmark glides into the
  counter of the 0 and re-inks gold; the supporting statement (max 2 short
  sentences — growth, adaptability, customer focus, trusted delivery) rises
  through a mask at `P 0.42–0.52`. No empty screens between the mark and the name.
- Scroll act 3 (`P 0.56–0.76`): the completed composition scales down ~0.82 and
  shifts up in a controlled scale/position transform, making room.
- Exit (`P 0.78–1.00`): the "10" stroke splits at four points; four colored paths
  (red / rose / blend / blue) pull downward off-stage — directly becoming the Four
  Pillars paths. The four split paths are **pre-authored in the same SVG** and
  reveal progressively (`pathLength` + opacity crossfade) — no runtime path
  generation, no path-`d` morphing (§8 technique policy).

**Option H2 — "Sliced System" (alternative)**

- Initial state: a massive solid graphite "10" already occupies the right two thirds,
  but sliced into five horizontal bands (via `clip-path: inset()`), bands offset so
  the numeral is only *implied*. A thin red line threads through the gaps.
- Scroll act 1: bands slide into register — the "10" assembles. The red line pulls
  taut through the counter of the 0.
- Scroll act 2: the aligned bands part briefly to reveal the department name typeset
  *inside* the slice gaps, then close; supporting statement rises below.
- Exit: the bands re-offset and dissolve outward while the threaded line splits into
  the four discipline paths.

**Recommendation: H1.** It makes the line the protagonist from second zero (the
whole site's premise), it is the purest "system comes to life" reading, it is the
technically safest (pre-authored paths + `pathLength` + masks + one static ghost
layer — no path morphing), and it is maximally
distant from Concept A's static lockup. H2 is stronger typographically but the
sliced-band mechanic returns in the Journey scenes anyway — spending it in the hero
would repeat.

Sticky/moving inventory (H1): sticky = the full-stage SVG (ghost layer + live path
+ pre-authored split paths) + identity block (`PPMD`, `2016 — 2026`) + name band +
labels;
moving = scroll position drives `pathLength`, gradient stops, mask insets, and the
final scale/translate. Nothing is animated on a timer except a 2s idle "pulse"
before first scroll (skipped under reduced motion).

Mobile fallback: stage becomes `220vh`; ghost + drawn 10 at ~80vw width; the
rest-state identity (`PPMD`, `2016 — 2026`) stacks at the top; acts 2–3 merge
(name + statement reveal together); the four-way split simplifies to the line
exiting as a single stroke that visually splits at the top of Pillars.

### 9.2 Four Pillars — "One department, four disciplines"

Layout: **asymmetric system map** (not a symmetric cross — avoids org-chart reading).
A `PPMD` core node sits at ~42% x / 50% y of a `100vh` sticky stage; four discipline
nodes at unequal radii and angles, connected by the four colored paths arriving from
the hero. Inactive paths stay visible at 35% opacity — interdependence is always on
screen.

Disciplines (reuse `src/data/pillars.ts` — titles/descriptions map 1:1):
Project Delivery · Process Excellence · Business Transformation · Testing & Quality.

Interaction: scroll steps focus through the four nodes (scroll-driven on desktop);
each node is also a real `<button>` — click/keyboard selection jumps focus. The
active node's path thickens (2→4px), its label scales up, and its description
(1–3 sentences) settles **next to the node along the path**, not in a card below.
The core node pulses subtly whenever focus changes: everything routes through PPMD.

Exit: the four paths retract into the core, which slides toward the top of the next
section and becomes the Department Head connector node.

### 9.3 Department Head & Teams — three streams from one point

No wide Head card; no three-cards-in-a-row.

- The single line arrives at a **gold-graphite Head node**: a generous editorial
  portrait (masked in an arch/oval crop, never tiny), name, `Head of PPMD` label,
  and their one-line quote — composed asymmetrically beside the node, on the warm
  ground. Gold is used only here and in hallmark moments.
- From the Head node, the line fans into **three vertical streams**:
  Project Management (`--b-red`), Process & Procedures (`--b-rose`),
  BPT & Testing (`--b-blue`). Streams are flowing bands (SVG path + band fill),
  not columns of cards.
- Scroll moves focus down through the streams one by one: the focused stream widens
  (~52vw), reveals mission, codename and 3 contribution labels (from `teams.ts`),
  plus live people count; the other two compress (~14vw each) but never disappear.
- Selecting a stream (click/Enter) opens that **team chapter** (9.4) — the stream
  band visually expands to become the chapter's spine.

### 9.4 Team chapter & People — one team composition

One chapter layout, instantiated per team with the team's stream color as its spine.

- The stream band becomes a vertical **spine** running down the chapter; every
  person connects to it. No card wall, no separated leadership block.
- **Layered roster / editorial contact sheet** (chosen direction): portraits sit on
  alternating sides of the spine in a syncopated rhythm (2–3 per row band, varying
  crop heights) like an editorial contact sheet. All colleagues visible; portraits
  minimum ~160px tall on desktop (~120px mobile) — always recognizable.
- Hierarchy by **scale + position, not distance**:
  - PM team: Team Lead largest, anchored at the spine's origin; the 2 Program
    Managers next scale, immediately adjacent; all other members equal size after.
  - PP and BPT: Team Lead largest at origin; all other members equal.
  - Leadership is *within* the flow — first among the team, not floating above it.
  - Rendering is driven by the existing `roleGroup`/`teamSections` data (reused
    as-is) so hierarchy stays in data, not JSX.
- Each portrait: photo (or initials fallback), name, role label, superpower line on
  focus/hover. Activation opens a **detail overlay** (accessible dialog: focus trap,
  `Esc`, focus restore — same a11y bar as Concept A's `PersonModal`, new component)
  with superpower / fun fact / contribution / quote from `people.ts`.
- Team-in-numbers: not a tile grid — 3–4 large numerals set directly on the spine
  as stations (e.g. people count, projects, years), with small labels.
- Exit: the spine narrows and re-joins the other two streams, which merge back to a
  single line heading into Hot Topics.

### 9.5 Hot Topics — the live portfolio ribbon

One shared component for all teams. Not a carousel of cards.

- The line turns horizontal and becomes a **kinetic ribbon** crossing a `~120vh`
  band. Initiatives ride the ribbon as **stations**: title (statement-size type),
  stage tag (`In progress` / `Rollout` / `Scaling` / …), team color tick on the line,
  one-sentence detail below the active station.
- The ribbon shows ~2.5 stations at a time; the active station is centered and
  full-ink, neighbors are ghosted at 40%. Movement = `transform: translateX` on the
  ribbon track; the line itself appears to slide through a fixed viewport.
- Navigation: prev/next buttons (real buttons, visible focus), drag/swipe, and
  arrow keys when the region is focused; position dots (station index) beneath.
  No autoplay.
- Data: variable item count, `{ title, detail, stage, team: TeamId | 'all' }` —
  Concept A's hot-topic data is currently **inline and unexported** in
  `AppPrototype.tsx`; Concept B gets its own data file (see §18).

### 9.6 Journey — the 2016–2026 exhibition

**First dark scene.** The ground flips to `--b-dark`; the line becomes a light path.

- **Eleven scenes (2016 → 2026)**, one per year, in a vertical
  `scroll-snap` exhibition (`scroll-snap-type: y proximity` — proximity, not
  mandatory, so scrolling never feels hijacked). Each scene is `100vh`.
- Composition alternates: year numeral huge left / statement right, then mirrored,
  then centered — three alternating layouts cycling.
- The year numeral is monumental (~30vw), outlined for past years, solid+gold for
  the hallmark years (2016 origin, 2026 anniversary). The incoming year rises
  through a mask as the previous dissolves upward (opacity + translate).
- The line is the journey path: it bends direction between scenes (each scene's
  segment enters where the previous exited, angle alternating with the layout).
- One strong milestone statement per year + one short sentence. Content comes from
  a **new** `journey` dataset (2016–2026) — the existing `timeline.ts` (2015–2025)
  stays untouched for Concept A (see §18).
- **Persistent decade meter:** a slim fixed indicator (bottom edge on desktop, top
  on mobile) showing `2016 ———●——— 2026` with the current year — doubles as the
  section's orientation device.
- No horizontal scrolling anywhere in this section.

### 9.7 Voices — the organizational chorus

Ground returns to warm light. No quote grid.

- **One active quote** center-stage at statement scale, attributed with name, role,
  department and relationship line (data model of `messages.ts` reused fully —
  external voices only).
- Around it, **fragments** of the other quotes (short excerpts) float at low opacity
  along thin branches off the main line, each tagged with its department label —
  the chorus. Scroll/next advances which voice is active; fragments and the active
  quote trade places via mask + translate (no reflow).
- Business-area labels (Marketing, Technology, Customer Operations…) act as context
  chips connected to the line — the whole of A1 speaking back to PPMD.

### 9.8 Closing — the loop

**Second dark scene** (or deep-warm graphite — decided in PoC review).

- The line gathers every stream color into a braided single stroke, travels to
  center stage, and **curls into a closed loop that reforms a compact "10"** —
  the hero's numeral returning, now filled and gold-edged.
- Closing statement: **"10 years of PPMD — the best is still ahead."** with the
  sub-line `Project & Processes Management Department · A1 Bulgaria`.
- Footer credit (`Made by Valentin Stoev`) in system-label type.
- The loop visibly closes — the last drawn pixel of the site completes the circle.

## 10. Navigation — the System Rail

Not a generic top navigation bar.

- **Desktop:** a slim fixed vertical rail on the left edge — itself a miniature of
  the system line, with **8 nodes** (Hero · Pillars · Teams · People · In Motion ·
  Journey · Voices · Close). The active chapter's node is enlarged and labeled
  (`03 · Teams`); progress between nodes fills the rail (scroll-linked
  `scaleY`/`pathLength`).
- Hover or focus expands the rail into full chapter names; each node is an anchor
  link inside a `<nav aria-label="Chapters">` list — natively keyboard reachable,
  visible `:focus-visible` ring, `aria-current="true"` on the active chapter.
- **Mobile:** rail collapses to a compact chapter pill (bottom-left, e.g. `03 · Teams`
  with a tiny progress arc). Tapping opens a full-screen chapter overlay (accessible
  dialog semantics) listing all chapters; selecting jumps and closes.
- The rail is the *only* persistent chrome. It inverts its ink automatically on the
  two dark scenes.

## 11. Motion rules

Reusable named rules — one place (`alternative/motionRules` in implementation),
referenced by every section. Storyboard scenes cite these by name.

| Rule | Definition |
|---|---|
| `ease-system` | `cubic-bezier(0.22, 1, 0.36, 1)` — the default for all entries |
| `ease-exit` | `cubic-bezier(0.55, 0, 0.55, 0.2)` — for content leaving |
| **`type-reveal`** | headline wipes in via `clip-path: inset(0 0 100% 0 → 0)` + `y: 24→0`, 640ms `ease-system`; staggers 60ms/line |
| **`line-draw`** | scroll-linked `pathLength` via `useScroll`+`useTransform` (no duration); on discrete activation: 900ms `ease-system` |
| **`ghost-guide`** | static pre-render of a destination geometry at 6–12% ink opacity beneath the live stroke; fades out (`opacity` only) as the drawn path covers it; never animated on its own |
| **`section-enter`** | scene content: `opacity 0→1`, `y: 48→0`, 560ms, children stagger 70ms |
| **`section-exit`** | `opacity 1→0.15`, `y: 0→-40`, `scale 1→0.97` scroll-linked over the last 20% of the section |
| **`state-active` / `state-inactive`** | active: full ink, stroke 4px, `scale 1.0`; inactive: 35% opacity, stroke 2px, `scale 0.96`; 320ms crossfade — never `display` toggles |
| **`portrait-activate`** | frame mask expands `inset(6%) → inset(0)` + `scale 1→1.03`, 360ms; ink label rises `type-reveal` at 80% size |
| **`stream-transition`** | focused stream width animates via `transform: scaleX` on the band (transform-only; text container width snaps at the midpoint to avoid text reflow jank), 480ms `ease-system` |
| **`year-transition`** | incoming year: mask rise + `y: 80→0`; outgoing: `opacity→0`, `y: →-60`, both 520ms; line bend interpolates scroll-linked |
| **`overlay-open`** | detail dialog: `clip-path: inset(12% round 24px) → inset(0 round 0)` + `opacity`, 380ms; backdrop `opacity` 240ms; close reverses at 280ms |
| **`nav-state`** | node scale `1→1.4` + label `type-reveal` at small size, 240ms; progress fill scroll-linked |

Global constraints: only `transform`, `opacity`, `pathLength`, `clip-path`; no
`filter`, no `box-shadow` animation, no layout properties, no timer-driven loops
(except the single pre-scroll hero pulse). Every rule has a reduced-motion variant
(§16).

## 12. Desktop wireframes (text)

```
HERO (sticky stage within ~280vh)
┌──────────────────────────────────────────────┐
│ A1                              PPMD         │  ← PPMD readable from frame 1
│                                 2016 — 2026  │  ← immediately readable
│            ╷    ┌╌╌╌╌╮                       │
│         1  │    ╎ 0  ╎  ← ghost "10" skeleton│
│    (live   │    ╎    ╎    at 6–12% opacity,  │
│    stroke) ╵    └╌╌╌╌╯    ~50–60vw wide      │
│   ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒                     │  ← name band wipes in on scroll
│   supporting statement (2 sentences max)     │
│        ↓    ↓     ↓    ↓  (4 pre-authored    │
│                            split paths exit) │
└──────────────────────────────────────────────┘

FOUR PILLARS (sticky 100vh stage in 260vh full build; PoC: 180–210vh, hub + first focus only)
┌──────────────────────────────────────────────┐
│        ○ Process Excellence                  │
│       ╱                 ╲                    │
│  ○───●PPMD               ○ Business Transf.  │
│ Delivery ╲              ╱                    │
│           ○ Testing & Quality                │
│   [active node: label XL + 2-line desc       │
│    placed along its path]                    │
└──────────────────────────────────────────────┘
  (asymmetric radii/angles — not a symmetric cross)

TEAMS — three streams
┌──────────────────────────────────────────────┐
│           ◉ HEAD (gold node, portrait,       │
│              name, quote — asymmetric)       │
│          ╱        │        ╲                 │
│   ██████████   ▒▒▒▒▒       ▒▒▒▒▒             │
│   PM stream    PP           BPT              │
│   (focused,    (compressed) (compressed)     │
│    mission +                                 │
│    3 labels +                                │
│    count)                                    │
└──────────────────────────────────────────────┘

TEAM CHAPTER (per team, spine = stream color)
┌──────────────────────────────────────────────┐
│  ║ TEAM LEAD (largest portrait, at origin)   │
│  ║     [PM only: 2 Program Managers, mid]    │
│  ║ ▣ ▣     ← members on alternating sides    │
│  ║    ▣ ▣     of the spine, contact-sheet    │
│  ║ ▣ ▣ ▣     rhythm, equal size              │
│  ║ 16 ← numeral stations on the spine        │
└──────────────────────────────────────────────┘

HOT TOPICS ribbon
┌──────────────────────────────────────────────┐
│  ghosted ── ● ACTIVE INITIATIVE ── ghosted → │
│      stage tag · team tick · one sentence    │
│         [‹]  · · ● · ·  [›]                  │
└──────────────────────────────────────────────┘

JOURNEY (dark, 11 × 100vh, snap-proximity)
┌──────────────────────────────────────────────┐
│  2019          milestone statement           │
│  (30vw,        one short sentence            │
│   outlined)         ╲ line bends to next     │
│  2016 ———●—————————— 2026   ← decade meter   │
└──────────────────────────────────────────────┘

VOICES
┌──────────────────────────────────────────────┐
│   fragment·Marketing        fragment·Tech    │
│        “ACTIVE QUOTE AT STATEMENT SCALE”     │
│         name · role · department             │
│   fragment·Customer Ops     fragment·…       │
└──────────────────────────────────────────────┘

CLOSING (dark)
┌──────────────────────────────────────────────┐
│            ⟲ line curls into “10”            │
│   10 years of PPMD — the best is still ahead │
│        PPMD · A1 Bulgaria · credit           │
└──────────────────────────────────────────────┘
```

## 13. Tablet adaptation (768–1199px)

- Hero: unchanged mechanics, "10" at ~70vw; name band wraps to two lines.
- Pillars: same hub, radii compressed; description docks to a fixed lower-third
  band instead of floating along paths.
- Streams: three streams remain side-by-side but focused stream takes ~60vw.
- Team chapter: contact sheet drops to max 2 portraits per row band.
- Ribbon: ~1.5 stations visible; buttons remain.
- Journey/Voices/Closing: unchanged, type scales via `clamp()`.
- Nav rail: kept (tablets in landscape), touch targets ≥44px.

## 14. Mobile adaptation (<768px)

- Hero: 220vh stage, merged acts (see 9.1), split exit simplified to one stroke.
- Pillars: hub becomes a **vertical mini-map** — core node top, four nodes stacked
  along a single winding path; scroll focuses each in turn; same button semantics.
- Streams: stacked vertically; the focused stream expands in height
  (transform-driven), others compress to slim labeled bands — all three always
  visible in the viewport at the focus moment.
- Team chapter: single-column contact sheet, portraits full-bleed to one side of
  the spine, ≥120px tall; leadership still first + largest.
- Ribbon: one station per view, swipe + buttons.
- Journey: snap retained (`proximity`); year at ~40vw; decade meter moves to top.
- Voices: fragments reduce to 2, stacked above/below the active quote.
- Nav: chapter pill + full-screen chapter overlay (§10).
- No sticky stage exceeds 100svh; all stages use `svh` units to survive the mobile
  address-bar resize.

## 15. Accessibility

- Semantic structure: every chapter a `<section>` with a real (sometimes visually
  monumental) heading; one `<h1>` in the hero; landmarks (`nav`, `main`, `footer`).
- All interactive nodes/stations/portraits are `<button>` or `<a>` — never bare divs.
- Keyboard: full traversal in DOM order; the rail is a skip-capable nav; ribbon and
  journey respond to arrow keys **only when focused**; visible `:focus-visible`
  rings on all targets (inherit the global pattern from `index.css`).
- Detail overlay: `role="dialog"`, `aria-modal`, focus trap, `Esc`, focus restore,
  body scroll lock — matching the a11y bar already set by Concept A's modal.
- Decorative SVG lines: `aria-hidden="true"`; meaningful graphics get titles.
- Scroll-driven reveals never gate *reachability*: content is in the DOM and
  readable by AT regardless of scroll progress.
- Color: never the only carrier of team identity — codename labels accompany color
  everywhere; AA contrast per §6.
- Touch: hover-only affordances get `@media (hover: none)` equivalents.

## 16. Reduced-motion behavior

With `prefers-reduced-motion: reduce` (checked via `useReducedMotion` +.CSS):

- All line segments render **fully drawn, static**; no `pathLength` animation.
- Hero becomes a static completed composition ("10" + name + statement) — the page
  simply scrolls past it; sticky stages collapse to natural flow height.
- `type-reveal`, `section-enter/exit`, `year-transition` → opacity-only fades ≤200ms
  or none.
- Streams/pillars focus changes swap state instantly (opacity states preserved so
  active/inactive remains legible).
- Scroll-snap is retained (it is an ergonomics feature, not an animation); the
  decade meter still updates (position, no easing).
- Overlay opens with a simple fade. The idle hero pulse never runs.
- Music/audio: none in Concept B phase one.

## 17. React / file architecture

**New files only.** Concept A files are not touched.

```
src/
  AppAlternative.tsx              ← Concept B root (composition + providers)
  AppAlternative.module.css      ← Concept B tokens (scoped) + root layout
  alternative/
    types.ts                     ← Concept-B-only types (LineAnchor, Station, …)
    lineContract.ts              ← handoff anchors/state per section (§8)
    theme.ts                     ← TeamId → Concept B accent map (red/rose/blue/gold)
    motionRules.ts               ← named rules from §11 (variants + eases)
    hooks/
      useSectionProgress.ts      ← useScroll wrapper per section (target ref, offsets)
      useLineHandoff.ts          ← reads lineContract, exposes entry/exit state
    components/
      SystemLine.tsx / .module.css     ← <LineSegment> renderer (SVG, pathLength)
      NavRail.tsx / .module.css        ← system rail + mobile chapter pill/overlay
      PortraitFrame.tsx / .module.css  ← masked editorial portrait + initials fallback
      DetailOverlay.tsx / .module.css  ← accessible person/topic dialog
      DecadeMeter.tsx / .module.css    ← persistent 2016–2026 indicator
    sections/
      Hero.tsx / .module.css
      Pillars.tsx / .module.css
      Streams.tsx / .module.css        ← Head + three team streams
      TeamChapter.tsx / .module.css    ← one layout, instantiated per team
      HotTopicsRibbon.tsx / .module.css
      Journey.tsx / .module.css
      Voices.tsx / .module.css
      Closing.tsx / .module.css
    data/
      journey.ts                 ← 2016–2026 milestones (new; timeline.ts untouched)
      hotTopics.ts               ← ribbon items (Concept A's are inline/unexported)
      heroCopy.ts                ← hero statement + labels (2016–2026)
```

- Shared, reused as-is: `src/data/types.ts`, `teams.ts`, `people.ts`, `messages.ts`,
  `department.ts`, `pillars.ts`; global font import and `:focus-visible`/reduced-motion
  base from `index.css`.
- Concept B does **not** import Concept A components, styles or the `SceneBackground`
  system; visual worlds stay independent.
- `motion/react` (`motion`, `useScroll`, `useTransform`, `useReducedMotion`,
  `AnimatePresence`) is the only animation dependency. No new packages.

## 18. Content / data mapping

**Reusable today (no changes):**

| Data | Used by Concept B for |
|---|---|
| `department.ts` | names, tagline base, intro source |
| `pillars.ts` (`departmentPillars`) | the four discipline nodes — titles/descriptions map exactly |
| `teams.ts` | team names, codenames, missions, stories, contributions, facets; `teamSections` drives roster hierarchy |
| `people.ts` | full roster + Head, role groups, superpower/funFact/contribution/quote |
| `messages.ts` | Voices — full model reused (external voices, category, relationship) |
| `types.ts` | `TeamId`, `Person`, `Team`, `RoleSection`, `WallMessage`, `Milestone` |

**Not reused / replaced:**

- `timeline.ts` — period is **2015–2025**; Concept B's mandate is **2016–2026**.
  A new `alternative/data/journey.ts` (11 entries, 2016→2026, `Milestone` type
  reused) keeps Concept A intact. When the correct period is confirmed as the
  official one, retiring `timeline.ts` is a separate decision for Concept A's owner.
- `stats.ts` — Concept A telemetry (and also says 2015–2025); Concept B's numeral
  stations (§9.4) define their own values in-section.
- Concept A hot topics — defined inline (unexported) in `AppPrototype.tsx`; Concept B
  gets `alternative/data/hotTopics.ts` with the same shape + `stage` field.
- Team accent hexes in `teams.ts` — Concept B overrides via `alternative/theme.ts`
  (PM red `#E2001A`, PP coral rose, BPT **blue** — Concept A's BPT is coral/orange).

**Missing data fields (needed before/during implementation):**

1. Real people names + photo files (roster is placeholder "Team Member N"); photo
   specs: min 800px on the long edge, face-centered crops possible.
2. Department Head real name, photo, quote.
3. `journey.ts` content: one milestone title + sentence per year 2016–2026, with
   hallmark flags for 2016 and 2026 (and optionally 1–2 majors between).
4. Hot topics list (4–8 items): title, one-sentence detail, stage, owning team.
5. Hero statement (≤2 sentences) and closing sub-line confirmation.
6. Optional per-person short "excerpt" for Voices fragments (else derived from quote).
7. Confirmation of the anniversary period **2016–2026** as official (it contradicts
   every current data file and the content template's 2015–2025).

**Excel / content template:** `PPMD_SITE_CONTENT_TEMPLATE.md` already covers ~90% of
Concept B's needs because both concepts share the data model. Concept B needs a
short **addendum section** (to be appended, not rewritten): hero statement (new
composition), journey years shifted to 2016–2026 (11 entries), hot-topic `stage`
values, and the Head portrait/photo note. The prefilled import `.xlsx` referenced at
the repo root is currently an **empty directory**, not a workbook — flagged for the
content owner. One collected content pass can then feed both concepts.

**Switching Concept B on (this branch only):** `src/main.tsx` already has the
documented swap point (`App` ↔ `AppPrototype`). At implementation time — not now —
the only change on this branch is importing `AppAlternative` there. One line,
trivially revertable, never merged to Concept A's branches.

**Publishing for comparison (later):**

- *Note:* `deploy.yml` currently triggers on pushes to `full-visual-redesign` —
  neither `main` nor this branch — so today, deploys of any concept are effectively
  manual (`workflow_dispatch`).
- **Recommended:** a runtime switch in `main.tsx` (e.g. `?concept=b` URL parameter
  chooses `AppAlternative` vs `AppPrototype`) built once on a comparison branch —
  one Pages deployment serves both concepts at the same URL for side-by-side review.
- Alternative: temporarily point `deploy.yml`'s branch trigger at
  `alternative-concept-v2` (workflow edits stay on this branch) so Pages serves
  Concept B only during a review window, then revert.
- Both options leave Concept A's code untouched; the choice is deferred to the
  comparison phase.

## 19. Performance considerations

- Animate **only** `transform`, `opacity`, `pathLength` (stroke-dashoffset under the
  hood — cheap), `clip-path` on bounded elements. No `filter: blur()` on large
  surfaces (a known cost in Concept A's atmosphere), no animated shadows.
- One scroll listener economy: `useScroll` per section target (motion consolidates
  to rAF); derived values via `useTransform` — no React re-renders on scroll for
  the hot paths (motion writes styles directly).
- SVG segments are small (one per section, simple paths); `overflow: visible`
  overdraw regions kept ≤12vh; `pointer-events: none` on all line SVGs.
- Sticky stages: max one sticky element per section; total pinned distance budget
  ~1200vh for the full site (~30 viewports of scroll — comparable to the references).
- Images: portraits lazy-loaded (`loading="lazy"`, `decoding="async"`), sized via
  `srcset`; below-fold sections get `content-visibility: auto` where it doesn't
  fight sticky positioning.
- `will-change: transform` only on the currently animating stage, set/unset via
  motion's lifecycle — never globally.
- Fonts already self-hosted (fontsource); no new font weight files needed (variable).
- Budget: Lighthouse Performance ≥ 90 on a mid-tier laptop, CLS < 0.02 (masked
  reveals don't reflow), main-thread scroll work < 4ms/frame on the hub and ribbon.
- Mobile: reduce stroke complexity (simplified hero path), no overdraw regions,
  `100svh` stages.

## 20. Implementation phases

1. **Phase 0 — Skeleton:** `AppAlternative` root, tokens, NavRail (static), section
   shells with correct heights/anchors, line contract stub. Site scrolls end-to-end
   with placeholder statements.
2. **Phase 1 — Proof of concept** (§22): Hero (H1) + Hero→Pillars transition +
   Pillars initial hub + working NavRail progress. **Approval gate.**
3. **Phase 2 — System spine:** Streams (Head + 3 teams), TeamChapter with roster +
   DetailOverlay, line handoffs 3→4→5.
4. **Phase 3 — Motion chapters:** HotTopicsRibbon, Journey (11 scenes, dark flip,
   DecadeMeter), Voices, Closing loop.
5. **Phase 4 — Adaptation & hardening:** tablet/mobile layouts, reduced-motion pass,
   keyboard/AT audit, performance pass against §19 budgets.
6. **Phase 5 — Content & comparison:** real content/photos via the template
   addendum, `?concept=b` comparison switch, stakeholder review deploy.

## 21. Acceptance criteria

Concept B is accepted when:

1. A first-time viewer describes the site as **clearly different** from Concept A
   (bright/kinetic/connected vs dark/cinematic/stacked) without prompting.
2. The system line reads as **one continuous element** from Hero to Closing at
   normal scroll speed on desktop and mobile — no visible handoff seams.
3. The hero "10" forms under scroll control and its four-way split lands visually
   in the Pillars hub with no dead zone between sections.
4. Every section communicates its one message (§9) with ≤2 sentences of copy.
5. All 34 colleagues + Head are visible, recognizable (portrait size floors met),
   leadership reads through scale/position, and every person opens a detail view.
6. Hot topics handle 4–8 items without layout breakage; manual navigation works via
   buttons, keyboard and touch.
7. Journey covers 2016–2026 in 11 scenes with the persistent decade meter; no
   horizontal scrolling; snap never traps the user.
8. Navigation rail: current chapter always visible, all chapters reachable by
   keyboard alone, mobile pill/overlay usable one-handed.
9. Reduced motion yields a complete, legible, fully navigable site with static
   lines and fade-only transitions.
10. Performance budgets in §19 met; no use of canvas/WebGL/particles/new libraries.
11. Concept A untouched: `git diff` against Concept A files is empty; `main.tsx`
    modified only at the sanctioned swap point, only on this branch.

## 22. Proof-of-concept scope

**In scope (build first, nothing else):**

- Hero, Option H1 "The Drawn Ten" — full scroll choreography incl. ghost-10 rest
  state (with readable `PPMD` + `2016 — 2026` from frame 1), idle pulse, draw,
  early name reveal, ignite, statement, scale-down.
- The Hero → Four Pillars transition — the four-way split and its landing.
- Four Pillars **initial hub state** — core + four nodes + arriving paths + first
  focus state (scroll focus for node 1 only; full 4-node cycle is Phase 2 polish).
- NavRail — nodes, active state, scroll progress fill, keyboard traversal
  (desktop); mobile pill may be visual-only in the PoC.
- Reduced-motion variants of all of the above.

**Explicitly out of scope:** Teams, People, Hot Topics, full Timeline, Voices,
Closing, detail overlay, mobile chapter overlay, real content/photos.

**PoC scroll budget (hard limits):**

- Hero container: **~260–280vh** (not 320vh).
- Four Pillars initial hub container: **~180–210vh** for the PoC (the full
  four-node focus cycle stays outside the PoC; the container grows toward ~260vh
  only in Phase 2).
- Hero + initial Pillars combined: **≤ ~480vh.** The PoC must prove the concept
  without feeling slow or scroll-hijacked.

**PoC technique constraint:** per §8's SVG technique policy, the PoC uses only
pre-authored paths + scroll-linked `pathLength` + opacity crossfades + SVG group
transforms. **No path-`d` morphing of any kind in the PoC.**

**PoC viewport acceptance tests (must pass before the approval gate):**

Test matrix — every combination of:

| Viewport | Browser zoom |
|---|---|
| 1366×768 | 90% · 100% · 110% |
| 1536×864 | 90% · 100% · 110% |
| 1920×1080 | 90% · 100% · 110% |

Exercise in each cell: normal slow scroll · fast scroll (flick / PageDown) ·
reverse scroll (full scrub back to top) · viewport resize after load.

Validation checklist (all must hold in every cell and exercise):

- [ ] no visible Hero→Pillars line seam
- [ ] no clipped "10" and no clipped department name text
- [ ] no dead/empty state at page top (ghost 10 + `PPMD` + `2016 — 2026` present at `P = 0`)
- [ ] no scroll lock or scroll jump
- [ ] reduced-motion state is complete and readable

**The PoC exists to prove:** visual differentiation from Concept A; the continuous
line device works (draw + handoff + landing); scroll storytelling feels strong, not
gimmicky; performance within budget on the heaviest pattern (sticky + SVG draw);
and the references translate into a credible internal-corporate PPMD experience.

**PoC review questions:** Does the drawn 10 land emotionally? Is the split→hub
transition legible at fast scroll? Does the light world feel premium (not empty)?
Proceed / adjust / try Hero H2?
