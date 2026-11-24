# 🧍 Stickman story (Ricks Clips / Viral Explainer Edition)

A high-retention micro-documentary or bizarre true story told by animated stick figures, engineered around the **Ricks Clips 60-Second Retention Formula** and **Six-Beat Shorts Grammar**.

## Tools
- **Remotion** (recommended) or **HyperFrames** (experimental)
- **FFmpeg**
- See `guides/INSTALLATION.md` sections 1, 2, 3/4

---

## 🎯 Phase 1: Ideation & Title Engineering (Step 3 of Popcorn Flow)
When proposing 5 story ideas in STEP 3, never propose generic stories. Every idea **must** use one of the **3 Ricks Clips Outlier Archetypes**:
1. **Counter-Intuitive Engineering / Science** (*"Why Perfect [X] Don't Work"*, *"Why Astronauts Can't [X]"*)
2. **Bizarre Historical / True-Crime Schemes** (*"The Prisoner Who [X]"*, *"How [Strange Scam] Worked"*)
3. **Hidden Human Instincts / Forbidden Jobs** (*"The Instinct That Makes You [X]"*, *"The Job Nobody Wants in [X]"*)

**Title Rule:** 5–7 words max, built on a **Curiosity Gap** or **Physical Paradox**.

---

## 📐 Phase 2: The 6-Beat Script Grammar (`1_story_script/script.md`)
Target duration: **56 to 62 seconds** (~140–160 words at 2.5 words/sec) for Shorts/TikTok (`1080×1920`, 30 fps), or scaled proportionally for `1920×1080`.

Every script in `1_story_script/script.md` MUST be structured into these **6 Retention Beats** with a visual reset every **2 to 3.5 seconds** (18–24 scenes total):

| Beat | Time | Narrative Goal | Stickman & Camera Action |
|---|---|---|---|
| **1. Paradox Hook** | `0–3s` | State a counter-intuitive claim immediately. **Zero "Hey guys" or throat-clearing.** | Fast zoom-in (`scale: 1 -> 1.15`), stickman in immediate physical jeopardy or absurd situation. |
| **2. Stakes & Context** | `3–12s` | Establish the time, place, or problem in 2 crisp sentences. | Split-screen or environment draw-in; accent-colored prop appears. |
| **3. The Naive Attempt** | `12–25s` | Show what a normal person thinks would work—and why it fails catastrophically. | Stickman tries the obvious solution → comedic/dramatic fail (`red #FF3B30` flash + shake). |
| **4. Mechanism Twist** | `25–42s` | Reveal the hidden physics, ingenuity, or bizarre historical method ("Here's the catch..."). | Cross-section / diagram overlay with arrows, dashed lines, and spring-physics motion. |
| **5. Climax / Escalation** | `42–54s` | Push the consequence to its extreme real-world result. | Rapid 1.5–2s cuts, camera pan across scale comparison. |
| **6. Seamless Loop Payoff** | `54–60s` | Final twist punchline whose last sentence grammatically/thematically flows back into `0:00`. | Match-cut pose returning to Frame 1 geometry for infinite Shorts replay. |

### Pre-Script Virality Gate (Self-Check)
Before showing `1_story_script/script.md` to the user, verify and display a **3-Point Virality Score**:
- ✅ **Hook < 3s?** (First sentence creates an open loop)
- ✅ **No Dead Air?** (Every scene is ≤ 3.5 seconds with a named motion verb)
- ✅ **Loopable Ending?** (Final line bridges back to the title/hook)

---

## 🎨 Phase 3: Art Direction & Remotion Animation Rules
- **Canvas & Lines:** Clean off-white (`#F8F6F0`) or dark blueprint (`#0F172A`) background; thick black/white stickman strokes (`5 px`, rounded caps).
- **Color Coding:**
  - Protagonist stickman: **1 bold accent color** (e.g., `#3B82F6` blue or `#F59E0B` amber)
  - Danger / Failure / Antagonist: **High-contrast red** (`#EF4444`)
  - Solution / Mechanism highlight: **Emerald green** (`#10B981`)
- **Non-Stop Motion Rule (Anti-Static Trap):**
  - Never leave a stickman frozen. Combine `spring()` limb keyframes with a slow continuous camera drift (`interpolate(frame, [0, duration], [1, 1.08])`).
- **Word-by-Word Kinetic Captions:**
  - Center-lower third (`y: 72%` on 1080×1920), bold sans-serif (`Inter` / `Montserrat Black`), 3–4 words on screen max, active word highlighted in yellow/accent color with a `spring` pop.

---

## 🔊 Phase 4: Automated SFX Cue Mapping (`5_low_sfx/`)
Every scene transition and stickman action in `1_story_script/script.md` must include an explicit `[SFX: ...]` tag so `5_low_sfx/` is deterministic:
- **Camera zoom / transition:** `whoosh_fast.wav`
- **Text / diagram pop-in:** `pop_soft.wav`
- **Naive attempt failure (Beat 3):** `thud_impact.wav` or `error_buzz.wav`
- **Mechanism twist reveal (Beat 4):** `riser_tension.wav` + `ding_idea.wav`

---

## 💻 Workflow & Commands
1. `1_story_script/script.md`: 6-Beat table with `Scene # | Time | Stickman Action & Camera | On-Screen Caption | Voice-Over | [SFX]`
2. `2_voice/`: fast-paced voice-over (`scene01.wav`, `scene02.wav`…), trim leading/trailing silences > 0.15s with FFmpeg:
   ```bash
   ffmpeg -i raw.wav -af "silenceremove=start_periods=1:start_silence=0.1:start_threshold=-40dB" scene01.wav
   ```
3. `3_test/`: render Beat 1 (the 3-second Paradox Hook) to validate stickman rig, caption pop, and hook energy.
4. `4_low_render/`: full 480p preview render:
   ```bash
   npx remotion render --scale=0.5
   ```
5. `5_low_sfx/`: mix SFX cues at `-12dB` and background tension music at `-22dB` under the voice-over (`0dB`).
6. `6_output/`: final 1080p vertical (`1080×1920`) or horizontal (`1920×1080`) render.

## If the AI can't run commands
Provide the full component code (e.g. `src/StickmanScene.tsx` with `spring()` and `interpolate()` camera hooks) in a copy-ready block, with the exact path, then the `🛠️ YOUR TURN` command to run.
