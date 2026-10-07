# Motion-Graphics Bake-Off: Build Notes

## Approach & Shared Architecture
All three slides adhere to the strict output contract: no external assets, no libraries, and fully self-contained HTML.
To ensure the 1920x1080 design size scales perfectly without clipping, I used a responsive JavaScript `resize` listener that applies `transform: scale()` to the `#stage` element. 
The `window.__restart()` function in all files utilizes a clean DOM-cloning technique (`stage.cloneNode(true)`), which seamlessly resets and replays all CSS animations without inducing complex style-recalculation loops or manual state resets.

---

## Slide 1: `cold-open.html`
**Goal**: A confident title card that settles quickly for a live presenter.
- **Typography & Motion**: The kicker fades up gently using the teal accent, followed by a staggered word-by-word reveal for the main title. I used a brief inline script to wrap each word in an `overflow: hidden` span, allowing the inner text to slide up (`translateY(110%)` to `0`) sequentially. This gives a professional, snappy motion-graphics feel.
- **Timing**: The title completes its reveal by ~2 seconds, and the amber subtitle lands at 2.5s, allowing the slide to reach a clean, held frame well under the 8-12 second limit, ensuring it isn't distracting once the presenter starts speaking.
- **Atmosphere**: A subtle radial gradient glow fades in behind the text to give depth to the near-black `#0a0b0f` stage.

## Slide 2: `urk-pipeline.html`
**Goal**: Illustrate a complex data pipeline, specifically highlighting the live-preview nature of RealityKit/Simulator versus the packaged nature of the Vision Pro.
- **Timeline & Synchronization**: I used a 10-second absolute timeline for all CSS keyframes where 1% equals 0.1 seconds. This made it trivial to sync the arrival of payloads with the pulsing of the destination nodes.
- **The "Live" Connection**: The connection between Unreal, URK, and RealityKit uses an inline SVG line with an animated `stroke-dashoffset` to represent flowing data. 
- **Addressing the Constraints**: To honor the rule *"Do not imply the headset updates mid-edit... the simulator is the live surface"*, I positioned the `visionOS Simulator` as a branch beneath RealityKit. When the "Editor Update" payload hits RealityKit, a fast sync payload drops immediately into the Simulator, and both nodes pulse. 
- **The Packaged Hop**: The final link to the Apple Vision Pro is styled as a distinct dashed line without flowing dots. A separate, text-colored payload explicitly labeled "Packaged App" travels this link at the very end of the sequence.

## Slide 3: `classes-reveal.html`
**Goal**: Reveal six items with a rhythm that isn't exhausting, grouping the AI classes.
- **Layout**: The schedule is built using a CSS Grid layout for each row (`200px 1fr 340px`), aligning the dates, titles, and instructors perfectly. 
- **Rhythm**: Instead of a linear reveal which could drag on, I implemented a variable rhythm using `animation-delay`. Standard classes arrive every ~1.2 seconds.
- **Visual Grouping**: The two "Creative AI Workflow Masterclass" parts are wrapped in an `.ai-group` flex container. They share a continuous amber border, and their border-radiuses are stitched together so they look like a single unit. Rhythmically, Part 2 follows Part 1 rapidly (a 0.4s delay instead of 1.2s), mentally linking them for the viewer.
- **Completion**: The footer pulses in cleanly at 8.0 seconds, satisfying the timing requirement and holding static for the rest of the presentation.