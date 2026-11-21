# 🧊 3D explanation

Explication d'un concept (moteur, cellule, trou noir…) avec modèles 3D, éclatés, annotations.

## Outils
- **Blender** (modélisation, animation, rendu)
- **Sketchfab** (modèles gratuits CC0 / CC-BY)
- **FFmpeg**
- Voir `guides/INSTALLATION.md` sections 2, 5, 7

## Workflow
1. Script : chaque scène = 1 notion + le mouvement de caméra associé
2. Voix off pédagogique
3. Test : un plan (modèle + rotation lente + 1 annotation)
4. Rendu basse résolution : Eevee, 50 %, 24 fps, export en séquence PNG ou MP4
5. SFX légers + musique calme
6. Rendu final : Eevee haute qualité ou Cycles, 1080p

## Automatisation
Si l'IA a un terminal, elle peut générer un script Python Blender et lancer :
```bash
blender -b scene.blend -P script.py -a
```
Sinon, procédure clic par clic : Rendu → Propriétés de sortie → Format **FFmpeg Video** → Rendu → **Rendre l'animation** (Ctrl+F12).
