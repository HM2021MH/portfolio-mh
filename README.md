# Portfolio — Elmehdi Hassani

Portfolio personnel (site statique, aucune dépendance, aucun build) déployé automatiquement sur **GitHub Pages** via **GitHub Actions**.


## ✨ Fonctionnalités
- **Bilingue FR / EN** — sélecteur dans la barre de navigation (détection automatique de la langue du navigateur).
- **Photo dans le hero**, sans cadre (halo + fondu), à côté du nom.
- **Bouton « Télécharger le CV »** — sert le PDF depuis `assets/CV_Elmehdi_Hassani.pdf`.
- **Formulaire de contact** (nom / email / message).
- **WhatsApp** : clic sur le numéro = ouverture du chat WhatsApp + bouton WhatsApp flottant.
- **Pensé pour les RH et les recruteurs** — titres clairs, badge de disponibilité, contenu lisible.
- 100% statique, responsive (mobile inclus), accessible.

## 📬 Formulaire de contact
Par défaut, le bouton **« Envoyer le message »** ouvre la messagerie du visiteur avec un message pré-rempli vers votre Gmail — aucune configuration requise.

Pour **recevoir les messages directement par email** (sans ouvrir le client mail du visiteur) :
1. Créez un formulaire gratuit sur [formspree.io](https://formspree.io) → vous obtenez un endpoint du type `https://formspree.io/f/abcdwxyz`.
2. Dans `index.html`, cherchez `var FORMSPREE_ENDPOINT = "";` et collez votre endpoint entre les guillemets.
3. `git commit` + `git push` → le formulaire envoie désormais les messages vers votre boîte mail.

## 💬 Changer le numéro WhatsApp
Le numéro est `212691242390` (indicatif sans `+` ni espaces). Pour le modifier, remplacez les deux occurrences de `wa.me/212691242390` dans `index.html`.

```
portfolio/
├── index.html                  # le site (HTML + CSS + JS, tout-en-un)
├── assets/
│   ├── profile.jpg             # photo (carré) — remplacez ce fichier pour changer la photo
│   ├── profile_wide.jpg        # image de partage (Open Graph)
│   └── CV_Elmehdi_Hassani.pdf  # CV servi par le bouton de téléchargement
├── .github/workflows/deploy.yml
└── README.md
```

## 🚀 Déploiement (5 minutes)

### 1. Créer le dépôt et pousser le code
```bash
cd portfolio
git init
git add .
git commit -m "Initial commit — portfolio"
git branch -M main
git remote add origin https://github.com/HASSANI-ELMEHDI/portfolio.git
git push -u origin main
```
> Crée d'abord un dépôt **public** nommé `portfolio` sur GitHub (sans README/.gitignore pour éviter les conflits).

### 2. Activer GitHub Pages avec Actions
Sur GitHub : **Settings → Pages → Build and deployment → Source : `GitHub Actions`**.

C'est tout. Le workflow `deploy.yml` se lance à chaque `push` sur `main`. Suis-le dans l'onglet **Actions**.

### 3. Le site est en ligne
👉 `https://hassani-elmehdi.github.io/portfolio/`

## 💡 Option : adresse plus courte
Renomme le dépôt en **`HASSANI-ELMEHDI.github.io`** : le site sera servi à la racine
👉 `https://hassani-elmehdi.github.io/`

## ✏️ Personnaliser
- Tout le contenu et le style sont dans **`index.html`**.
- Remplace `assets/profile.jpg` par une autre photo (garde un format carré ~900×900).
- Chaque `push` redéclenche le déploiement automatiquement.

## 🧪 Aperçu en local
```bash
python3 -m http.server 8000
# puis ouvre http://localhost:8000
```
