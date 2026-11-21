# 🧍 Stickman story

Histoire racontée par des bonhommes bâtons animés, fond simple, texte et voix off.

## Outils
- **Remotion** (recommandé) ou **HyperFrames**
- **FFmpeg**
- Voir `guides/INSTALLATION.md` sections 1, 2, 3/4

## Direction artistique
- Fond blanc ou couleur unie, traits noirs épais (4–6 px)
- 1 couleur d'accent par personnage
- Format : 1920×1080 (YouTube) ou 1080×1920 (Shorts/TikTok), 30 fps
- Rythme : 1 idée par plan, plans de 2 à 4 secondes

## Workflow
1. `1_story_script/script.md` : scènes avec durée, action du stickman, texte à l'écran, voix off
2. `2_voice/` : voix off scène par scène (`scene01.wav`, `scene02.wav`…)
3. `3_test/` : une seule scène animée pour valider le style du stickman
4. `4_low_render/` : rendu complet 480p
   `npx remotion render --scale=0.5`
5. `5_low_sfx/` : ajout SFX (pop, whoosh, impact) + musique
6. `6_output/` : rendu final 1080p

## Si l'IA ne peut pas exécuter
Elle fournit le code complet des composants (ex : `Stickman.tsx`) dans un bloc à copier, avec le chemin exact (`src/Stickman.tsx`), puis la commande à lancer.

## Assemblage voix + vidéo (FFmpeg)
```bash
ffmpeg -i video.mp4 -i voix.wav -c:v copy -c:a aac -shortest sortie.mp4
```
