# 🧰 Tool installation guide (100% free)

> For the AI: in MANUAL mode, give the user only the section for their OS, using the 🛠️ format.
> For the user: copy-paste each command into a terminal (Windows: Windows key → type "PowerShell" → Enter; macOS: Cmd+Space → "Terminal"; Linux: Ctrl+Alt+T).

---

## 1. Node.js (required for Remotion and HyperFrames)
| OS | Command |
|---|---|
| Windows | `winget install OpenJS.NodeJS.LTS` |
| macOS | `brew install node` (no Homebrew? install it from https://brew.sh) |
| Linux (Debian/Ubuntu) | `sudo apt update && sudo apt install -y nodejs npm` |

No terminal: download the **LTS** version from https://nodejs.org and run the installer (keep all defaults).

✅ Check: `node -v` → shows a version number (v18 or newer recommended). **Close and reopen the terminal after installing.**
⚠️ Linux: if `apt` installs a version older than v18, use the LTS installer from https://nodejs.org instead.

---

## 2. FFmpeg (editing, conversion, adding sound)
| OS | Command |
|---|---|
| Windows | `winget install Gyan.FFmpeg` |
| macOS | `brew install ffmpeg` |
| Linux | `sudo apt install -y ffmpeg` |

✅ Check: `ffmpeg -version`
❌ "command not found" on Windows: close/reopen the terminal, or restart the PC.

---

## 3. Remotion (videos coded in React)
```bash
npx create-video@latest
```
Pick a template (e.g. *Hello World*), name the project, then:
```bash
cd project-name
npm install
npm run dev
```
A preview opens in the browser (Remotion Studio).

Render:
```bash
npx remotion render
```
✅ Check: the preview page shows up.
ℹ️ License: free for individuals and small teams (see https://remotion.dev/license).

---

## 4. HyperFrames (HTML-based videos) — experimental
An HTML/CSS-based alternative to Remotion. Its commands change quickly: **always follow the official docs** (search "HyperFrames" on GitHub / npm) for the current init and render commands. If anything is unclear, use Remotion instead.
✅ Check: rendering the provided example produces a video file.

---

## 5. Blender (3D)
| OS | Command |
|---|---|
| Windows | `winget install BlenderFoundation.Blender` |
| macOS | `brew install --cask blender` |
| Linux | `sudo snap install blender --classic` |

No terminal: https://www.blender.org/download/

✅ Check: `blender --version` (or open Blender from the menu).
Recommended settings for test renders: **Eevee** engine, 50% resolution, 24 fps.

---

## 6. Roblox Studio ("In this town" style)
⚠️ Windows and macOS only, graphical install (no AI can do it for you).
1. Go to https://create.roblox.com
2. Log in (free Roblox account)
3. Click **Start Creating** / **Download Studio** and run the installer
4. Open Studio → **New** → **Baseplate** template (or any city-like template)

Video capture: **OBS Studio** (free, https://obsproject.com).

---

## 7. Sketchfab (free 3D models)
1. Create a free account at https://sketchfab.com
2. Search for a model, then tick the **Downloadable** filter
3. Check the license: **CC0** or **CC Attribution** only
4. **Download 3D Model** → **glTF / .glb** format (easiest for Blender)
5. Put the file in `assets/models/` and record the credit in `assets/CREDITS.md`
6. Blender: **File → Import → glTF 2.0**

---

## 8. Free voice-over (optional)
- Record your own voice: **Audacity** (https://www.audacityteam.org), export as `.wav`
- Free local text-to-speech: **Piper TTS** (see its GitHub page for installation)

## 9. Free SFX and music
- https://pixabay.com/sound-effects/ and https://pixabay.com/music/
- https://freesound.org (check the license: CC0 / CC-BY)

---

## 🆘 Common problems
| Error | Fix |
|---|---|
| `command not found` / "is not recognized" | Close and reopen the terminal, otherwise restart |
| `winget` not found | Install "App Installer" from the Microsoft Store |
| `brew` not found | Install Homebrew: https://brew.sh |
| `permission denied` (Linux/macOS) | Add `sudo` in front of the command |
| `npm ERR!` | Check `node -v` (v18+), then delete `node_modules` and run `npm install` again |
