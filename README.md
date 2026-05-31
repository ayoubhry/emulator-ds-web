# 🎮 GBA Web Emulator — Next Gen

Un émulateur **Game Boy Advance** tournant entièrement dans le navigateur, hébergé sur GitHub Pages. Il charge automatiquement **Pokémon Version Émeraude** dès l'ouverture de la page — sans installation, sans plugin.

> Propulsé par [EmulatorJS](https://emulatorjs.org/) & le cœur **mGBA WebAssembly**.

---

## ✨ Fonctionnalités

- ⚡ **Chargement automatique** — la ROM démarre sans aucun clic
- 🕹️ **Console GBA fidèle** — rendu CSS pixel-perfect avec gâchettes L/R, croix directionnelle et boutons A/B
- 💾 **Sauvegardes et chargements d'état** intégrés via EmulatorJS
- 📸 **Screenshot** en un clic
- 🎮 **Support manette** (Gamepad API)
- 🔄 **Changer de jeu** — glisser-déposer n'importe quelle ROM `.gba` pour la remplacer à la volée
- 📱 **Responsive** — s'adapte aux petits écrans

---

## 🗂️ Structure du projet

```
📁 GBA Web/
├── 📄 index.html          # Interface principale (console GBA en CSS)
├── 🎨 style.css           # Design system & modélisation de la console
├── ⚙️  script.js           # Logique d'émulation & chargement automatique
└── 📁 Roms/
    └── 🎮 Pokemon - Version Emeraude.gba   ← ROM chargée au démarrage
```

---

## 🚀 Déploiement sur GitHub Pages

### 1. Forker / Cloner le dépôt

```bash
git clone https://github.com/VOTRE-USERNAME/gba-web-emulator.git
cd gba-web-emulator
```

### 2. Ajouter votre ROM

Placez votre fichier ROM dans le dossier `Roms/` :

```bash
Roms/Pokemon - Version Emeraude.gba
```

> ⚠️ Le nom du fichier doit correspondre **exactement** à la valeur `AUTO_ROM.path` dans `script.js`.

Pour utiliser une ROM différente, modifiez ces deux lignes dans `script.js` :

```js
const AUTO_ROM = {
  path: 'Roms/Mon-Jeu.gba',   // ← chemin relatif vers votre ROM
  name: 'Mon Jeu GBA',        // ← nom affiché dans l'interface
};
```

### 3. Pousser sur GitHub

```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### 4. Activer GitHub Pages

1. Allez dans **Settings** → **Pages**
2. Source : `Deploy from a branch`
3. Branch : `main` / `root`
4. Cliquez **Save**

Votre site sera disponible à l'adresse :
`https://VOTRE-USERNAME.github.io/gba-web-emulator/`

> 💡 **Fichiers volumineux** : les ROMs GBA font généralement 16–32 Mo. GitHub accepte jusqu'à 100 Mo par fichier. Au-delà de 50 Mo, activez **Git LFS** :
> ```bash
> git lfs install
> git lfs track "*.gba"
> git add .gitattributes
> ```

---

## 🖥️ Tester en local

`fetch()` est bloqué par le navigateur en protocole `file://`. Utilisez un **serveur HTTP local** :

| Méthode | Commande |
|---|---|
| **VS Code** | Clic droit sur `index.html` → *Open with Live Server* |
| **Node.js** | `npx serve .` |
| **Python 3** | `python -m http.server 8080` |

Puis ouvrez `http://localhost:3000` (ou `8080` selon la méthode).

> En `file://`, la section **"Changer de jeu"** s'ouvre automatiquement pour vous permettre de sélectionner la ROM manuellement pendant vos tests.

---

## ⌨️ Contrôles clavier

| Bouton console | Touche |
|---|---|
| Croix ↑ ↓ ← → | `Z` `S` `Q` `D` |
| Bouton **A** | `L` |
| Bouton **B** | `M` |
| Gâchette **L** | `I` |
| Gâchette **R** | `P` |
| **START** | `Entrée ↵` |
| **SELECT** | `Maj ⇧` |
| Plein écran | `F11` |

Les contrôles sont reconfigurables directement dans l'interface EmulatorJS (bouton ⚙️ dans la barre de l'émulateur).

---

## 🛠️ Technologies

| Outil | Rôle |
|---|---|
| [EmulatorJS](https://emulatorjs.org/) | Framework d'émulation web |
| [mGBA](https://mgba.io/) | Cœur d'émulation GBA (compilé en WebAssembly) |
| HTML / CSS / JS natif | Interface & logique — zéro dépendance |
| GitHub Pages | Hébergement statique gratuit |

---

## ⚖️ Avertissement légal

Ce projet ne distribue, ne télécharge et ne contient **aucun jeu protégé par copyright**.

La ROM utilisée doit être obtenue légalement — par exemple en extrayant vous-même la cartouche physique dont vous êtes propriétaire. L'auteur de ce projet décline toute responsabilité quant à l'utilisation de ROMs obtenues illégalement.

---

## 📄 Licence

Ce projet est distribué sous licence **MIT**.
EmulatorJS est distribué sous sa propre licence — voir [emulatorjs.org](https://emulatorjs.org/).
