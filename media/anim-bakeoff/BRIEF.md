# Motion-graphics bake-off brief — identical for every model

One task, given verbatim to Claude Opus 5, a Codex model, and Gemini. The point is a fair
comparison of motion-graphics authoring ability, so the brief, the constraints, and the output
contract are identical for all three. Judged on: does the motion carry meaning, is the timing
musical, is the typography clean, does it read on a projector, and does it run without errors.

## Output contract (identical for all three)

Produce exactly THREE self-contained HTML files. Each one:

- is a single `.html` file — all CSS and JS inline, **no external requests of any kind**
  (no CDN, no webfonts, no images, no network). System font stacks only.
- renders at **1920x1080** as the design size, and scales to fit any viewport without
  clipping or horizontal scroll (CSS `transform: scale()` on a fixed-size stage is the
  easy correct answer).
- animates **on load**, runs about **8-12 seconds**, and then **holds on a clean final
  frame** forever. It must not loop, and must not end on a blank stage — a presenter
  will leave this on screen while talking.
- exposes `window.__restart()` to replay the animation from zero.
- is dark-background. Palette: near-black ground `#0a0b0f`, off-white text `#f2f3f5`,
  one teal accent `#2dd4bf`, one amber accent `#fbbf24`. Use the accents sparingly.
- uses **no `alert`, no `console.error`, and must throw no exceptions** — it will be
  loaded in an iframe inside a presentation deck.
- is motion built from CSS animations / transitions / Web Animations API / `requestAnimationFrame`
  and inline SVG. No canvas-only solutions (they do not scale crisply), no libraries.

Name them exactly: `cold-open.html`, `urk-pipeline.html`, `classes-reveal.html`.

## Slide 1 — `cold-open.html`

The title card for a live YouTube stream that is starting right now. Text to use, verbatim:

- Kicker: `ALEX COULOMBE PRESENTS`
- Title: `Live AMA: Meta's VR Glasses, the Member Toolkit, and What's Next`
- Subtitle: `October 7, 2026`

Make the title arrive with some confidence — this is the first thing 
a live audience sees. Do not animate it so slowly that it is still moving when he starts talking.

## Slide 2 — `urk-pipeline.html`

An animated diagram of a real data path. Four stages, left to right, connected by a flowing link:

`Unreal Engine 5.8`  →  `URK Live Link`  →  `RealityKit`  →  `Apple Vision Pro`

The meaning the motion must carry: this is a **live** link, not an export. Geometry, lights,
cameras and materials leave Unreal, travel the link, and appear in the headset **while the scene
is still being edited** — and an edit made in Unreal travels the same path again immediately.
Show the round trip. Label the payload travelling the wire (USD geometry + a JSON manifest of
transforms, lights, cameras) if you can do it without crowding the diagram.

Be honest in the diagram: the last hop to the headset is a packaged app; the live preview hop
targets the visionOS simulator and the headset. Do not imply the headset updates mid-edit if you
have to choose — the simulator is the live surface.

## Slide 3 — `classes-reveal.html`

The upcoming class schedule, revealed one at a time. These are real, use them verbatim:

- `Oct 14` — `MetaHuman Wardrobes: Infinite Possibilities` — `Franco Vilanova`
- `Oct 21` — `Deep Dive with Lumen for UE 5.8` — `Sean Spitzer`
- `Oct 28` — `VR Cinematics for UE 5.8` — `Alex Coulombe`
- `Nov 4` — `Creative AI Workflow Masterclass, Part 1: Set Up From Scratch` — `Alex Coulombe`
- `Nov 11` — `Creative AI Workflow Masterclass, Part 2: Let It Run` — `Alex Coulombe`
- `Nov 18` — `Gaussian Splatting for VR in UE 5.8` — `Alex Coulombe`

Footer line, verbatim: `alexcoulombepresents.com/classes`

**No prices anywhere.** Six items is a lot to reveal — find a rhythm that does not take 30
seconds. The two Creative AI parts belong together visually.

## Hard rules

- American spelling throughout.
- No prices, no purchase language, no "unlock"/"revolutionize" marketing voice.
- Every string above is real and must appear exactly as written. Do not invent class names,
  dates, instructors, or product claims.
