---
layout: page
title: Exporter
permalink: exporter.html
---

## Exporter dans différents formats

Quand on sélectionne une Frame, on a plusieurs formats d'exportation: 

- PNG
- JPEG
- SVG
- PDF

## Comportement des tailles d'exportation

Les tailles **bitmap** (PNG et JPEG) vont exporter dans le format de pixels réglé dans Figma. On peut ajouter un multiplicateur, pour faire un export x2, x3 ou autre.

### Export pour le print

Les **exports PDF** convertissent les pixels à une résolution de **72 dpi**. Un rectangle de 842x595 pixels correspond à une page A4. Dans cette échelle, 1 cm ≈ 28,35 px (28,346 px) dans Figma.

### Export vectoriel SVG

Si on exporte un SVG dans le but de le retravailler dans **Inkscape**, Inkscape appliquera à l'ouverture du fichier la conversion 1 px CSS = 1/96 pouce = 0,026458 cm. En effet, Inkscape opère en 96 dpi (et pas en 72dpi). Dans ce mode, 1 cm est équivalent à 37,795 px.

Il est cependant possible de spécifier pour Inkscape un autre ratio de conversion, en ouvrant le fichier SVG dans un éditeur de texte. Modifiez la balise `<svg>` pour y ajouter des dimensions physiques explicites. Par exemple: 

```xml
<svg
  width="60cm"
  height="30cm"
  viewBox="0 0 1700 850"
  ...>
```

Inkscape respectera alors les dimensions physiques déclarées, et votre contenu sera mis à l'échelle. 