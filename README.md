# Mot Masqué

Jeu de déduction entre amis sur un seul téléphone. Chaque joueur reçoit un mot secret ; les imposteurs ont un mot proche, Mister White n'en a aucun. On donne des indices, on vote, on élimine.

## Fonctionnalités
- Joueurs mémorisés sur le téléphone, présents/absents, ordre de passage
- Nombre d'imposteurs et de Mister White au choix
- 31 thèmes et 1 079 familles de mots liés (4 340 paires possibles), plus des thèmes personnalisés
- Élimination tour par tour, devinette écrite de Mister White, détection de la victoire
- Variantes : imposteurs aveugles, mode Duo, manches sans intrus (fréquence réglable)
- Installable sur l'écran d'accueil et utilisable hors ligne (PWA)

## Structure
- `app.html` : le code de l'application (interface, logique, banque de mots)
- `tools/build.js` : assemble `index.html` (la PWA) à partir de `app.html`
- `manifest.webmanifest`, `sw.js`, `icons/` : installation et mode hors ligne
- `.github/workflows/pages.yml` : déploiement automatique sur GitHub Pages à chaque push sur `main`

## Modifier
1. Éditer `app.html` (la banque de mots est dans la constante `RAW` : une famille de mots liés par groupe « A|B|C », groupes séparés par « ; »).
2. Lancer `node tools/build.js` pour régénérer `index.html` (le déploiement le fait aussi automatiquement).
3. Incrémenter la version du cache dans `sw.js` pour que les téléphones récupèrent la mise à jour.
