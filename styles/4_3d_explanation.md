# 🧊 3D explanation

Explaining a concept (engine, cell, black hole…) with 3D models, exploded views and annotations.

## Tools
- **Blender** (modeling, animation, rendering)
- **Sketchfab** (free CC0 / CC-BY models)
- **FFmpeg**
- See `guides/INSTALLATION.md` sections 2, 5, 7

## Workflow
1. Script: each scene = 1 notion + its camera move
2. Educational voice-over
3. Test: one shot (model + slow rotation + 1 annotation)
4. Low-res render: Eevee, 50%, 24 fps, export as PNG sequence or MP4
5. Light SFX + calm music
6. Final render: high-quality Eevee or Cycles, 1080p

## Automation
If the AI has a terminal, it can generate a Blender Python script and run:
```bash
blender -b scene.blend -P script.py -a
```
Otherwise, click by click: **Output Properties** → File Format **FFmpeg Video** → menu **Render → Render Animation** (Ctrl+F12).
