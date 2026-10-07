# Live AMA — Oct 7, 2026

The Spatial Deck for **Alex Coulombe Presents: Live AMA — Meta's VR Glasses, the Member
Toolkit, and What's Next**, streamed live on YouTube at 11:00am ET on October 7, 2026.

Built on [spatial-deck](https://github.com/ibrews/spatial-deck) — one self-contained
`index.html`, no build step, no npm. Open the file and present. Everything on screen is a real
capture, a real recording frame, or a real product trailer; there are no placeholder slides and
no stock imagery.

**This repo is private and is not published.** No GitHub Pages, no public visibility.

## What's in it

| | |
|---|---|
| **45 slides** | 8 chapters in running order, plus a motion-graphics appendix |
| **`media/meta-connect/`** | 8 photos from Meta Connect, Sep 23–24 2026 |
| **`media/class-frames/`** | 16 frames pulled from the Aug–Sep class recordings |
| **`media/trailers/`** | all 10 product trailers, transcoded to 1280-wide for repo size |
| **`media/anim/`** | 3 animated slides (cold open, URK pipeline, classes reveal) |
| **`media/instructors/`** | headshots for the two guest instructors |

The deck opens on the cover slide. Slide 0 is the framework's theme-editor panel and only
appears with `?edit` — you will not land on it by accident while screen-sharing.

## Things to Try

1. **Present it.** `open index.html` and use `→` / `←` or click to advance. The deck opens in
   view mode with the presenter chrome hidden.
2. **Watch a trailer slide end to end.** Chapter 3 has ten of them, one per tool. They autoplay
   and loop, so you can leave one up while you talk over it.
3. **Watch the pipeline diagram tell its story.** Chapter 3, "How the live link actually works" —
   the payload hops Unreal → URK Live Link → RealityKit → the visionOS simulator, then an edit
   fires the whole path again carrying only the delta. That round trip is the argument.
4. **Compare the three models.** The `APPX` chapter holds the motion-graphics bake-off. The same
   brief and the same output contract went to Claude Opus, a Codex model and Gemini; the other
   two models' versions are in `media/anim-bakeoff/` — open them side by side in a browser.
5. **Edit a slide and watch it regenerate.** Open `index.html`, find the `SECTIONS` array near the
   top of the second `<script>` block, change any `title` or `bullets`, and reload. All slides are
   generated from that array.
6. **Press `A` to annotate.** Click any element, type a note, and export the batch — the format is
   designed to be handed straight back to an AI agent to bake into source.

## Rebuilding the animated slides

The three animations in `media/anim/` are standalone HTML files. Each runs on load, holds on a
clean final frame, and exposes `window.__restart()`. To re-shoot a contact sheet of one:

```bash
cd /Users/alex/Archives/acp-livestream-2026-10-07
node shoot.mjs deck/media/anim/urk-pipeline.html /tmp/out "1,2.5,4,6,8,10"
```

## Credits

Alex Coulombe Presents. Built overnight on 2026-10-07.
