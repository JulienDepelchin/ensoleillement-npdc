# Ensoleillement Nord–Pas-de-Calais, 1986-2005 / 2006-2025

Données de la carte interactive de *La Voix du Nord* sur le gain d'ensoleillement dans le Nord et le Pas-de-Calais.

## Fichiers (`data/`)

| Fichier | Contenu |
|---|---|
| `ecart_h.png`, `ecart_pct.png` | Images classées (style v3), en heures et en %, bornes et classes dans `carte_meta.json` |
| `traits.geojson` | Côte, frontières, départements, contour Nord / Pas-de-Calais (France : IGN ADMIN EXPRESS) |
| `npdc_contour.geojson` | Contours précis du Nord et du Pas-de-Calais (IGN), pour le cadrage |
| `etiquettes.json` | Villes (valeurs communales ; hors région, moyenne de 3 x 3 cases) et mers |
| `ecart_lisse.png` | Image lissée de l'écart (Web Mercator, découpée aux terres), bornes dans `image_meta.json` |
| `grille_zone.json` | Valeurs par case satellite sur la zone élargie (survol hors région) |
| `departements_59_62.geojson` | Contours du Nord et du Pas-de-Calais |
| `cases.geojson` | Cases satellite (0,05°, environ 5 km) découpées au contour régional (version 1, non utilisée) |
| `communes.geojson` | Contours simplifiés des 1 534 communes |
| `communes.json` | Index de recherche (centroïde, sans contour) |
| `villes.json` | Villes repères pour les étiquettes |
| `meta.json` | Chiffres régionaux, échelle, note et source |

Propriétés : `e` écart en heures par an, `pct` écart en %, `sig` écart significatif (test de Welch, p < 0,05), `partage` nombre de communes dont la case satellite principale est la même, `id` code INSEE.

## Page France (`data/france/`)

| Fichier | Contenu |
|---|---|
| `departements.geojson` | Contours des 96 départements métropolitains (IGN ADMIN EXPRESS COG CARTO, simplifiés) |
| `departements.json` | Écart en heures et en %, significativité, rangs (hors Savoie et Haute-Savoie, sur valeurs arrondies), centroïdes |
| `voisins.geojson` | Pays voisins (Natural Earth), fond gris |
| `france_meta.json` | Classes, couleurs, textes |

## Méthode

Durée d'ensoleillement annuelle estimée par satellite (SARAH-3, EUMETSAT CM SAF). Pour chaque case : moyenne 2006-2025 moins moyenne 1986-2005, et test de Welch sur les deux séries de 20 cumuls annuels. Pour chaque commune : moyenne des cases qui la couvrent, pondérée par la surface. Les estimations satellite surestiment légèrement les durées absolues : seuls les écarts sont publiés.

## Source et licence

EUMETSAT CM SAF, SARAH-3 (CDR/ICDR), DOI [10.5676/EUM_SAF_CM/SARAH/V003](https://doi.org/10.5676/EUM_SAF_CM/SARAH/V003). Copyright (c) (2025) EUMETSAT. Contours communaux : geo.api.gouv.fr. Contours des terres : Natural Earth. Départements : IGN ADMIN EXPRESS (traits, côte française), france-geojson (G. David) pour `departements_59_62.geojson`. Calculs : La Voix du Nord.
