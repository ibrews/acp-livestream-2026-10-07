# Live AMA — Oct 7, 2026

The Spatial Deck for **Alex Coulombe Presents: Live AMA — Meta's VR Glasses, the Member
Toolkit, and What's Next**, streamed live on YouTube at 11:00am ET on October 7, 2026
([watch the stream](https://www.youtube.com/watch?v=uYAjHLA3htU)). It is public so anyone who
watched can explore every tool, trailer and clip at their own pace.

**Open it:** https://ibrews.github.io/acp-livestream-2026-10-07/

Built on [Spatial Deck](https://github.com/ibrews/spatial-deck) — one self-contained
`index.html`, no build step, no npm. Everything on screen is a real capture, a real class
recording frame, a real product trailer or a video from the
[Alex Coulombe Presents YouTube channel](https://www.youtube.com/@AlexCoulombePresents);
there are no placeholder slides and no stock imagery.

## Quickstart

```bash
git clone https://github.com/ibrews/acp-livestream-2026-10-07.git
cd acp-livestream-2026-10-07
open index.html          # macOS; or double-click it, or serve the folder with any static server
```

Use `→` / `←` (or click) to move between slides. Press `/` to search every slide.

## What's in it

| | |
|---|---|
| **108 slides** | the eight live chapters, then *More from the Lab*, *Open source* and a motion-graphics bake-off |
| **The Lab** | 1–6 slides per tool — trailer, what it is, real captures and video — for xrsim, Forage, Constellation, Promptbook, SceneAudit, Blueprint Anti-Pasta, URMBridge, UnRealityKit / URKPreviewer, Pinchwork and Spatial Deck, plus the all-tools reel |
| **More from the Lab** | deeper UnRealityKit captures, the Vision Pro + OpenXR engine work, Project Ion, Video QA Workbench, the Fable Showcase |
| **Open source** | Unreal Custodian and 25 more public repos, by their GitHub social cards |
| **`media/trailers/`** | all 10 product trailers and the all-tools reel, H.264 at 1280 wide |
| **`media/posters/`, `media/lab/`** | trailer posters, repo social cards, README screenshots and captures |
| **`media/meta-connect/`, `media/class-frames/`** | photos from Meta Connect 2026 and frames from the Aug–Sep classes |
| **`media/anim/`, `media/anim-bakeoff/`** | the animated slides, and the same three animations as built by Codex and Gemini |

YouTube slides load their player only when you reach them; everything else is in this repo and
works offline.

## Things to Try

1. **Watch a whole trailer.** Open the deck and go to Chapter 3, *The Lab*. Each tool opens on its
   trailer; click any video to zoom it to fullscreen.
2. **Jump straight to a tool.** Press `/`, type `Forage` (or `xrsim`, `URMBridge`, `Pinchwork`)
   and press Enter.
3. **See an edit cross the bridge.** In the UnRealityKit slides, find *One edit, no re-export* —
   the same scene before and after moving a light panel in Unreal, with nothing re-exported.
4. **Compare three models.** The `APPX` chapter holds the motion-graphics bake-off: the same brief
   built by Claude Opus, Codex and Gemini, side by side.
5. **Make it yours.** Fork [Spatial Deck](https://github.com/ibrews/spatial-deck), edit the
   `SECTIONS` array near the top of `index.html`, and reload — every slide is generated from it.

## Credits

**Alex Coulombe Presents** — https://alexcoulombepresents.com. Trailers, captures and deck built
for the October 7, 2026 livestream. Class recording frames show instructors only. House style:
[acp-style-guide](https://github.com/ibrews/acp-style-guide).
