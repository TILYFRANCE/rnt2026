# RNT Wiltz 2026 

Site vitrine pour la RNT 2026.

## Structure du projet

- `index.html` : page d'accueil
- `historique.html`, `infos-pratiques.html`, `lieu-rnt.html`, `sous-camp.html`, `equipe-camp.html` : pages principales
- `activites/` : pages par branche
- `styles/` : styles partages
- `img/` : images et icones
- `.github/workflows/deploy-pages.yml` : workflow de deploiement GitHub Pages

## Apercu en local

Le site est entierement statique. Pour le consulter en local, il suffit d'ouvrir `index.html` dans un navigateur.

## Deploiement sur GitHub Pages

Le depot est configure pour deployer automatiquement le site avec GitHub Actions a chaque push sur `main`.

### 1. Activer GitHub Pages

Dans le depot GitHub :

1. Ouvrir **Settings**.
2. Ouvrir **Pages**.
3. Dans **Build and deployment**, choisir **Source: GitHub Actions**.

### 2. Pousser sur `main`

Une fois GitHub Pages configure, chaque push sur `main` declenche :

1. le checkout du depot
2. la preparation d'un artefact statique de deploiement
3. le deploiement sur GitHub Pages

Le workflow peut aussi etre lance manuellement depuis l'onglet **Actions** grace a `workflow_dispatch`.

### 3. Recuperer l'URL publiee

Une fois le workflow termine :

1. ouvrir la derniere execution dans **Actions**
2. verifier le deploiement `github-pages`
3. ou ouvrir **Settings → Pages** pour voir l'URL publiee

## Mettre le site a jour

1. Modifier les fichiers HTML, CSS, images ou autres ressources du depot.
2. Committer les changements.
3. Pousser sur `main`.
4. Attendre la fin du workflow GitHub Actions.

## Notes

- Le site est deploye comme artefact statique ; aucune etape de build n'est necessaire.
- Le workflow de deploiement exclut `.git`, `.github` et le dossier temporaire `dist/` de l'artefact publie.
