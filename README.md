# Portfolio — Aziz Lamhouar

Site portfolio professionnel, statique (HTML / CSS / JS), sans dépendance ni backend.

## Structure des fichiers

```
portfolio/
├── index.html   → contenu et structure du site (toutes les sections)
├── style.css    → design (couleurs, typographie, mise en page, responsive)
├── script.js    → interactions (menu mobile, animations, formulaire)
└── assets/
    └── CV-Aziz-Lamhouar.pdf   → à ajouter par vos soins
```

## 1. Lancer le site en local

Aucune installation n'est nécessaire. Deux options :

- **La plus simple :** double-cliquez sur `index.html`, il s'ouvre dans votre navigateur.
- **Recommandée** (pour que le formulaire et les chemins fonctionnent exactement comme en ligne) : ouvrez un terminal dans le dossier `portfolio/` et lancez :
  ```
  python3 -m http.server 8000
  ```
  puis ouvrez `http://localhost:8000` dans votre navigateur.

## 2. Modifier vos informations

Tout le texte se trouve dans `index.html`, organisé par sections clairement identifiées par des commentaires (`<!-- ================= ... ================= -->`).

Quelques repères :
- **Nom / titre / accroche** → section `hero`, en haut du fichier.
- **Texte "À propos"** → section `id="about"`.
- **Formation** → section `id="formation"` (année, diplôme, université).
- **Compétences** → section `id="competences"`, une carte `.skill-card` par compétence. Pour ajouter une compétence, dupliquez un bloc `<div class="skill-card">...</div>`.
- **Objectif professionnel** → section `id="objectif"`.
- **Projets** → section `id="projets"`. Pour ajouter un vrai projet, remplacez un bloc `.projet-card--empty` par :
  ```html
  <div class="projet-card">
    <span class="cell-ref">E2</span>
    <h3>Nom du projet</h3>
    <p>Description courte du projet, contexte, résultat.</p>
  </div>
  ```
- **Contact** → section `id="contact"` (email, ville).

Les couleurs, polices et espacements se règlent tout en haut de `style.css`, dans le bloc `:root { ... }` — modifiez une valeur et elle s'applique partout sur le site.

## 3. Votre CV

Votre CV est déjà inclus dans `assets/CV-Lamouar-Aziz.pdf` — vous n'avez rien à faire. Le bouton « Télécharger mon CV » de la page d'accueil pointe déjà vers ce fichier.

Si vous mettez à jour votre CV plus tard : exportez la nouvelle version en PDF, nommez-la exactement `CV-Lamouar-Aziz.pdf` (même nom, pour remplacer l'ancienne), et remplacez le fichier dans `assets/`.

## 4. Publier le portfolio gratuitement en ligne

Trois options gratuites, de la plus simple à la plus flexible :

### Option A — Netlify Drop (la plus rapide, aucun compte requis pour tester)
1. Allez sur **https://app.netlify.com/drop**
2. Glissez-déposez le dossier `portfolio/` complet dans la fenêtre.
3. Le site est publié en quelques secondes avec un lien du type `https://nom-aleatoire.netlify.app`.
4. (Optionnel) Créez un compte gratuit pour renommer le lien et le rendre permanent, ex. `aziz-lamhouar.netlify.app`.

### Option B — GitHub Pages (bon choix si vous voulez aussi apprendre Git)
1. Créez un compte sur **https://github.com** si vous n'en avez pas.
2. Créez un nouveau dépôt, par exemple `portfolio`.
3. Ajoutez les fichiers `index.html`, `style.css`, `script.js` et le dossier `assets/` à la racine du dépôt.
4. Dans le dépôt : **Settings → Pages → Source : branche `main`, dossier `/root`** → Enregistrer.
5. Votre site sera accessible à `https://votre-nom-utilisateur.github.io/portfolio/`.

### Option C — Vercel
1. Allez sur **https://vercel.com**, créez un compte gratuit.
2. « Add New Project » → importez le dossier ou connectez votre dépôt GitHub.
3. Laissez les réglages par défaut (site statique) et cliquez sur « Deploy ».

## 5. Obtenir un lien à envoyer aux recruteurs

Une fois publié avec l'une des options ci-dessus, vous obtenez une URL publique (ex. `https://aziz-lamhouar.netlify.app`). C'est ce lien que vous pouvez :
- coller directement dans un email ou un message à un recruteur ;
- ajouter dans votre CV, sous vos coordonnées ;
- ajouter à votre profil LinkedIn (section « Coordonnées » → « Site web »).

Astuce : sur Netlify ou Vercel, vous pouvez renommer le sous-domaine gratuit (ex. `aziz-lamhouar-cv.netlify.app`) pour un lien plus professionnel, sans avoir à acheter de nom de domaine.

## Aller plus loin (facultatif)

Le formulaire de contact ouvre actuellement le client mail de l'utilisateur (aucun serveur requis). Si vous préférez recevoir les messages directement par email sans que le visiteur ait besoin d'un logiciel de messagerie configuré, vous pouvez brancher gratuitement **Formspree** (https://formspree.io) : créez un compte, récupérez l'URL de formulaire fournie, et remplacez l'attribut `action` du `<form>` dans `index.html` en suivant leur documentation.
