# Les nichoirs

Un site d'une seule page qui explique comment choisir, construire, installer et
entretenir un nichoir à oiseaux. Écrit par Léo.

**En ligne :** https://acassan.github.io/leo-oiseaux/

## Écrire le contenu

Tout le texte est dans `index.html`. Il n'y a rien à installer, rien à compiler :
on ouvre le fichier, on écrit entre les balises, on enregistre.

Les endroits qui attendent du texte sont marqués par un encadré en pointillés
(`<div class="a-ecrire">`). Une fois la section écrite, on supprime l'encadré et
on met ses paragraphes `<p>…</p>` à la place.

`style.css` ne contient aucun texte du site — seulement les couleurs, les polices
et la mise en page.

## Voir le site sur son ordinateur

Il suffit d'ouvrir `index.html` dans un navigateur : double-clic sur le fichier.

Pour le voir comme sur un vrai serveur, depuis le dossier du projet :

```bash
python3 -m http.server 8000
```

puis ouvrir http://localhost:8000

## Publier

Le site est hébergé par GitHub Pages, servi directement depuis la branche `main`.
Il n'y a aucune étape de construction : pousser suffit.

```bash
git add -A
git commit -m "Écrit la section sur l'entretien"
git push
```

La mise en ligne prend environ une minute.

## Structure

```
index.html   la page (tout le texte est ici)
style.css    couleurs, polices, mise en page
assets/      les images, à venir
.nojekyll    demande à GitHub Pages de servir les fichiers tels quels
docs/        les notes de conception
```
