# 🍿 Popcorn's MotionGraphics

An **AI skill** that turns your AI assistant into a step-by-step motion graphics studio. Type `/popcornM`, pick a style, and the AI guides you from idea to final video — using **free tools and free assets only**.

Works with **any AI**: Claude Code, Codex, Cursor, ChatGPT, Gemini, Mistral, local models… If the AI can't run a command itself, it explains the action to you in simple, copy-paste steps.

---

## ✨ How it works

1. **Pick a style** (5 options)
   1. 🧍 **Stickman story** — a story told with animated stick figures
   2. ❓ **What if** — hypothetical scenarios with explanatory visuals
   3. 🏘️ **In this town** — a small Roblox-style 3D town with characters
   4. 🧊 **3D explanation** — a concept explained in 3D
   5. 🎨 **Found a style** — show a reference, the AI analyzes it
2. **Install tools — only after you say yes.** The AI checks what you already have first.
3. **Get 5 story ideas** (2 lines each). Nothing more is written until you choose — no wasted tokens.
4. **Script**, then a validated pipeline: voice → test scene → low-res render → low-res + SFX → final output.

### Tools by style (all free)

| Style | Tools |
|---|---|
| 🧍 Stickman story | Remotion (or HyperFrames, experimental), FFmpeg |
| ❓ What if | Remotion (or HyperFrames, experimental), FFmpeg, Blender (optional) |
| 🏘️ In this town | Roblox Studio, Blender, Sketchfab (free assets only), OBS, FFmpeg |
| 🧊 3D explanation | Blender, Sketchfab (free assets only), FFmpeg |
| 🎨 Found a style | Chosen after analyzing your reference |

---

## 📦 Installation

### Option 1 — Git (recommended)

```bash
git clone https://github.com/skyfee2321/Popcorn-s-MotionGraphics.git
cd Popcorn-s-MotionGraphics
```

### Option 2 — ZIP

1. Click the green **Code** button → **Download ZIP**
2. Extract the archive anywhere you like

---

## 🚀 Usage

### Claude Code
Open the cloned folder in Claude Code and type:
```
/popcornM
```
The command (`.claude/commands/`) and the skill (`.claude/skills/popcornM/`) are detected automatically.

**Use it in any project (optional):** copy the skill folder to your personal skills folder:
```bash
# macOS / Linux
mkdir -p ~/.claude/skills && cp -r .claude/skills/popcornM ~/.claude/skills/
```
```powershell
# Windows (PowerShell)
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse .claude\skills\popcornM "$HOME\.claude\skills\"
```
The skill is self-contained. When the style sheets or install guide are not available locally, the AI asks you to paste them.

### Codex, Cursor and other coding agents
Open the folder: the agent reads `AGENTS.md`, then type `/popcornM`.

### ChatGPT, Gemini, Mistral and other chat AIs
1. Copy the full content of `SKILL.md`
2. Paste it into the custom instructions (or at the start of a conversation)
3. Type `/popcornM`

When the AI needs a style sheet or the install guide, it will ask you to paste the matching file.

---

## 📁 Repository structure

```
Popcorn-s-MotionGraphics/
├── SKILL.md                     # The skill (works with any AI)
├── AGENTS.md                    # Entry point for Codex / Cursor / agents
├── .claude/
│   ├── commands/popcornM.md     # /popcornM slash command (Claude Code)
│   └── skills/popcornM/SKILL.md # Self-contained Claude skill
├── styles/                      # One sheet per style (tools, look, workflow)
├── guides/INSTALLATION.md       # Install commands for Windows / macOS / Linux
├── 1_story_script/              # Script
├── 2_voice/                     # Voice-over
├── 3_test/                      # Single test scene
├── 4_low_render/                # Full low-res render
├── 5_low_sfx/                   # Low-res render + SFX + music
├── 6_output/                    # Final render
├── assets/                      # Models, sounds + CREDITS.md
└── templates/                   # Reusable prompts
```

---

## 📜 Free assets & credits

Only **CC0** or **CC-BY** assets are used. Every asset must be credited in `assets/CREDITS.md`. Check each tool's own license (e.g. Remotion is free for individuals and small teams — see https://remotion.dev/license).

## 🤝 Contributing

Ideas and fixes are welcome: open an issue or a pull request.

## 📄 License

[MIT](LICENSE) 🍿
