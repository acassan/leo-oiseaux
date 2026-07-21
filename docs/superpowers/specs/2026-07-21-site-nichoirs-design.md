# Site « Les nichoirs » — conception

Date : 2026-07-21
Dépôt : `acassan/leo-oiseaux`

## Objectif

Un site informatif d'une seule page sur les nichoirs à oiseaux, hébergé
publiquement sur GitHub Pages. Léo écrit le contenu ; l'architecture est posée en
amont pour qu'il visualise la forme du site avant d'avoir rédigé une ligne.

## Contraintes retenues

- **Une seule page**, parcourue en défilant, avec un sommaire ancré.
- **Aucune dépendance** : ni gestionnaire de paquets, ni étape de construction, ni
  police distante. Le site doit fonctionner tel quel dans cinq ans sans
  maintenance.
- **Éditable par un enfant** : le HTML est commenté en français, les emplacements
  à remplir sont visuellement marqués.
- **Dépôt public** — GitHub Pages sur dépôt privé exige un plan payant. Le dépôt a
  été basculé en public le 2026-07-21.

## Approche

HTML et CSS purs. GitHub Pages sert la racine de la branche `main` ; aucun
workflow GitHub Actions, puisqu'il n'y a rien à construire. Un `git push` publie.

Écartées : Vite + Tailwind (impose Node et des dépendances vieillissantes pour une
page unique) et un générateur de site type Astro ou Eleventy (existe pour
factoriser plusieurs pages — il n'y en a qu'une).

## Direction visuelle

Le motif directeur est **le trou d'envol**. Son diamètre décide à lui seul quelle
espèce peut s'installer, ce qui en fait l'objet le plus caractéristique du sujet.
Il se décline en trois endroits :

- un nichoir dessiné en CSS pur dans l'en-tête, avec son trou ;
- un petit cercle en guise de marqueur devant chaque titre de section — plutôt
  qu'une numérotation, car les sections ne se lisent pas dans l'ordre ;
- des pastilles dont la taille est proportionnelle au diamètre annoncé, pour
  comparer les espèces d'un coup d'œil.

**Palette** tirée des matériaux du sujet : gris-vert de lichen (fond), encre
vert-noir, brun pin, et le noir du fond du trou. Thèmes clair et sombre via
`prefers-color-scheme`.

**Typographie** en polices locales uniquement : Optima pour les titres, Charter
pour le texte long, une monospace pour les mesures en millimètres.

## Structure des fichiers

```
index.html   la page ; contient tout le texte
style.css    couleurs, polices, mise en page
assets/      images à venir
.nojekyll    désactive le traitement Jekyll de Pages
.gitignore
README.md
docs/        ce document
```

## Sections de la page

Découpage de départ, à remanier librement selon ce que Léo écrit :

pourquoi installer un nichoir · les types de nichoirs · dimensions et trou
d'envol · où l'installer · quand l'installer · le construire soi-même ·
l'entretien · les erreurs à éviter

Chaque section vide contient un bloc `.a-ecrire` : un encadré en pointillés qui
décrit ce qu'on attend à cet endroit. Il est conçu pour être supprimé une fois la
section rédigée.

Les quatre diamètres de trou d'envol présents dans la section « dimensions »
(28, 32, 34 et 45 mm) sont des valeurs courantes servant à démontrer le
composant. Elles sont explicitement signalées comme à vérifier — le site ne doit
pas présenter comme établi ce qui n'a pas été recoupé.

## Qualité minimale

Responsive jusqu'au mobile, lien d'évitement, contour de focus visible au clavier,
`prefers-reduced-motion` respecté, `lang="fr"`, image décorative décrite par
`aria-label`.

## Volontairement exclus

Pas de JavaScript — le sommaire ancré est du HTML natif. Pas de `404.html`, pas de
domaine personnalisé, pas de mesure d'audience, pas de formulaire de contact.

## Vérification

La mise en place n'est pas considérée comme terminée sur la foi de la
configuration : l'URL publiée doit répondre 200 et servir la page attendue.
