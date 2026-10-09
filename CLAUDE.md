# Restaurant sur le Lac — site vitrine

Site d'une page pour le restaurant de Gaëlle et Suor Heng, à Châlette-sur-Loing (Loiret). Encore en phase de preview : rien n'est en production.

## Structure

- `index.html` : toute la page. CSS dans le `<style>` du `<head>`, JS dans le `<script>` en fin de `<body>`. Pas de build, pas de dépendance, pas de framework : on ouvre le fichier dans un navigateur.
- `assets/img/` : photos locales (portrait du couple, `plats/` pour les assiettes).
- Sections, dans l'ordre : hero, `#maison`, `#cuisine`, `#lac`, `#carte`, `#venir`, footer. Si un `id` change, mettre à jour la nav, le tiroir mobile, le footer et la liste observée dans le JS (« Section active »).

## Règles du client

- **Nom** : toujours « Restaurant sur le Lac » en entier. Jamais « Sur le Lac » seul, jamais « du Lac ».
- **Texte** : l'essentiel, rien de plus. Pas de phrases d'ambiance ni de storytelling. Un titre, une ligne au maximum, puis les faits (plats, prix, horaires, téléphone).
- **Direction artistique** : luxe, table étoilée. Sobre, beaucoup d'air, typographie fine. Aucun effet voyant.
- **Orange** : une touche fine et discrète, jamais d'aplat ni de bouton orange.

## Direction artistique « Eau dormante »

- Alternance de sections sombres (`--ink`, le lac de nuit) et claires (`.sec--paper`, le lin).
- Typographie : Newsreader (titres, italiques, prix) et Hanken Grotesk (texte, labels en capitales espacées).
- Un seul accent, `--orange` : `#D4894F` sur fond sombre, redéfini en `#A8551F` dans `.sec--paper` pour rester lisible. Il sert aux numéros de section, aux prix des menus, aux « ou » de la carte, au jour courant des horaires et aux survols. Ne pas ajouter d'autre couleur d'accent.
- Titres de section : `h2.display`, la fin en italique (`<em>`) qui ne se coupe pas.
- Animations : classes `.rv` (texte), `.rv-img` (image), révélées au scroll. Respecter `prefers-reduced-motion`.
- Mobile : chaque section a sa composition dédiée dans `@media (max-width:760px)`. Vérifier à 390 px après tout changement de mise en page.

## Images

Toutes les images passent par l'objet `IMAGES` dans le JS : une clé par `data-img`. Pour changer une photo, modifier `src` à cet endroit seulement.

- Salle, terrasse, lac : fiche Tourisme Loiret du restaurant, chargées à distance.
- Plats (`p1` à `p6`) : page TripAdvisor du restaurant, copiées dans `assets/img/plats/` en 1200 px. `p6` est une photo de la maison ; `p1` à `p5` sont des photos de clients.

## La carte

Section `#carte`, reprise de la carte papier photographiée en salle : menu à 52 € et menu végétarien à 34 €, avec le tarif à la carte à droite de chaque plat. Un plat = un `<li>` dans `.course` ; le « ou » entre deux plats est ajouté par le CSS.

## Points en attente de confirmation par le client

Ils sont listés dans le panneau « Notes de preview » (pastille en bas à gauche), à retirer avant la mise en production avec le CSS `.pv-*` associé.

- Plats et prix : date de la carte photographiée inconnue.
- Horaires : la carte dit « du mardi au dimanche, midi et soir » ; le site n'annonce le dîner que le vendredi et le samedi.
- Droits des photos de plats prises par des clients, et crédit du portrait du couple.
