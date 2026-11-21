# 🧍 Stickman story

A story told by animated stick figures, with a simple background, on-screen text and voice-over.

## Tools
- **Remotion** (recommended) or **HyperFrames** (experimental)
- **FFmpeg**
- See `guides/INSTALLATION.md` sections 1, 2, 3/4

## Art direction
- White or solid-color background, thick black lines (4–6 px)
- 1 accent color per character
- Format: 1920×1080 (YouTube) or 1080×1920 (Shorts/TikTok), 30 fps
- Pacing: 1 idea per shot, shots of 2 to 4 seconds

## Workflow
1. `1_story_script/script.md`: scenes with duration, stickman action, on-screen text, voice-over
2. `2_voice/`: voice-over scene by scene (`scene01.wav`, `scene02.wav`…)
3. `3_test/`: one single animated scene to validate the stickman style
4. `4_low_render/`: full 480p render
   `npx remotion render --scale=0.5`
5. `5_low_sfx/`: add SFX (pop, whoosh, impact) + music
6. `6_output/`: final 1080p render

## If the AI can't run commands
It provides the full component code (e.g. `Stickman.tsx`) in a copy-ready block, with the exact path (`src/Stickman.tsx`), then the command to run.

## Merging voice + video (FFmpeg)
```bash
ffmpeg -i video.mp4 -i voice.wav -c:v copy -c:a aac -shortest output.mp4
```
