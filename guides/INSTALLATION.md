# 🧰 Guide d'installation des outils (100 % gratuits)

> Pour l'IA : en mode MANUEL, recopie à l'utilisateur uniquement la section de son système, au format 🛠️.
> Pour l'utilisateur : copie-colle chaque commande dans un terminal (Windows : touche Windows → tape « PowerShell » → Entrée ; macOS : Cmd+Espace → « Terminal » ; Linux : Ctrl+Alt+T).

---

## 1. Node.js (requis pour Remotion et HyperFrames)
| Système | Commande |
|---|---|
| Windows | `winget install OpenJS.NodeJS.LTS` |
| macOS | `brew install node` (si Homebrew absent : installer depuis https://brew.sh) |
| Linux (Debian/Ubuntu) | `sudo apt update && sudo apt install -y nodejs npm` |

Sans terminal : télécharger la version **LTS** sur https://nodejs.org et lancer l'installeur (tout laisser par défaut).

✅ Vérifier : `node -v` → affiche un numéro (v18 ou plus recommandé). **Fermer et rouvrir le terminal après installation.**

---

## 2. FFmpeg (montage, conversion, ajout du son)
| Système | Commande |
|---|---|
| Windows | `winget install Gyan.FFmpeg` |
| macOS | `brew install ffmpeg` |
| Linux | `sudo apt install -y ffmpeg` |

✅ Vérifier : `ffmpeg -version`
❌ « commande introuvable » sous Windows : fermer/rouvrir le terminal, ou redémarrer le PC.

---

## 3. Remotion (vidéos codées en React)
```bash
npx create-video@latest
```
Choisir un modèle (ex : *Hello World*), donner un nom au projet, puis :
```bash
cd nom-du-projet
npm install
npm run dev
```
Un aperçu s'ouvre dans le navigateur (Remotion Studio).

Rendu :
```bash
npx remotion render
```
✅ Vérifier : la page d'aperçu s'affiche.
ℹ️ Licence : gratuit pour les particuliers et petites structures (voir https://remotion.dev/license).

---

## 4. HyperFrames (vidéos en HTML)
Alternative à Remotion basée sur HTML/CSS. Les commandes évoluent vite : **toujours suivre la doc officielle** (rechercher « HyperFrames » sur GitHub / npm) pour la commande d'initialisation et de rendu à jour.
✅ Vérifier : un rendu de l'exemple fourni génère un fichier vidéo.

---

## 5. Blender (3D)
| Système | Commande |
|---|---|
| Windows | `winget install BlenderFoundation.Blender` |
| macOS | `brew install --cask blender` |
| Linux | `sudo snap install blender --classic` |

Sans terminal : https://www.blender.org/download/

✅ Vérifier : `blender --version` (ou ouvrir Blender depuis le menu).
Réglages conseillés pour les rendus test : Moteur **Eevee**, résolution 50 %, 24 fps.

---

## 6. Roblox Studio (style « In this town »)
⚠️ Windows et macOS uniquement, installation graphique (aucune IA ne peut le faire à ta place).
1. Aller sur https://create.roblox.com
2. Se connecter (compte Roblox gratuit)
3. Cliquer **Start Creating** / **Télécharger Studio** et lancer l'installeur
4. Ouvrir Studio → **Nouveau** → modèle **Baseplate** ou **City**

Capture vidéo : outil d'enregistrement intégré de Roblox, ou **OBS Studio** (gratuit, https://obsproject.com).

---

## 7. Sketchfab (modèles 3D gratuits)
1. Créer un compte gratuit sur https://sketchfab.com
2. Rechercher un modèle, puis cocher le filtre **Downloadable**
3. Vérifier la licence : **CC0** ou **CC Attribution** uniquement
4. **Download 3D Model** → format **glTF / .glb** (le plus simple pour Blender)
5. Mettre le fichier dans `assets/models/` et noter le crédit dans `assets/CREDITS.md`
6. Blender : **Fichier → Importer → glTF 2.0**

---

## 8. Voix off gratuite (optionnel)
- Enregistrer sa propre voix : **Audacity** (https://www.audacityteam.org), export en `.wav`
- Synthèse vocale locale gratuite : **Piper TTS** (voir sa page GitHub pour l'installation)

## 9. SFX et musique gratuits
- https://pixabay.com/sound-effects/ et https://pixabay.com/music/
- https://freesound.org (vérifier la licence CC0 / CC-BY)

---

## 🆘 Problèmes fréquents
| Erreur | Solution |
|---|---|
| `command not found` / « n'est pas reconnu » | Fermer et rouvrir le terminal, sinon redémarrer |
| `winget` introuvable | Installer « App Installer » depuis le Microsoft Store |
| `brew` introuvable | Installer Homebrew : https://brew.sh |
| `permission denied` (Linux/macOS) | Ajouter `sudo` devant la commande |
| `npm ERR!` | Vérifier `node -v` (v18+), puis supprimer `node_modules` et relancer `npm install` |
