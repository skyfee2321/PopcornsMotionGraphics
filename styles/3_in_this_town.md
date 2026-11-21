# 🏘️ In this town

A small Roblox-style 3D town where characters live a story ("In this town, …").

## Tools
- **Roblox Studio** (set, characters, camera)
- **Blender** (alternative or touch-ups)
- **Sketchfab**: **free assets only** (CC0 / CC-BY)
- **OBS Studio** (capture), **FFmpeg**
- See `guides/INSTALLATION.md` sections 2, 5, 6, 7

⚠️ Roblox Studio is graphical software: the AI guides the user step by step (🛠️ format) and can write Lua scripts to paste.

## Workflow
1. Script: list of places (house, school, shop…) and characters
2. Narrator voice-over
3. Test: build **one single place** and film one shot
   - Studio → Toolbox → **Marketplace** tab → free filter
   - Camera: Lua script provided by the AI (ServerScriptService or StarterPlayerScripts depending on the case)
4. Capture every shot with OBS (1280×720 for the low render)
5. SFX: city ambience, footsteps, doors
6. Final 1080p render

## Credits
Every Sketchfab/Toolbox asset used is recorded in `assets/CREDITS.md` (name, author, link, license).
