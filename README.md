# France Geojson

Ce projet contient les tracés des entités géographiques et administratives françaises suivantes au format [GeoJSON](http://geojson.org/) :

* Régions (post-redécoupage de 2015).
* Anciennes régions métropolitaines (avant redécoupage).
* Départements
* Cantons
* Arrondissements
* Communes

Des fichiers nationaux, avec et sans les départements et régions d'outre-mer, sont inclus à la racine du projet et des subdivisions [par région](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/regions/) et [par département](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/) dans leurs dossiers respectifs :

* Contours des départements par région (exemple : [Départements de la région Bourgogne-Franche-Comté](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/regions/bourgogne-franche-comte/departements-bourgogne-franche-comte.geojson)).
* Contours des arrondissements par région et par départements (exemple : [Arrondissements du Finistère](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/29-finistere/arrondissements-29-finistere.geojson)).
* Contours des cantons par région et par départements (exemple : [Cantons de Corrèze](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/19-correze/cantons-19-correze.geojson)).
* Contours des communes par région et par départements (exemple : [Communes du Bas-Rhin](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/67-bas-rhin/communes-67-bas-rhin.geojson)).

## Simplification

Pour optimiser la taille des fichiers, les contours ont été largement simplifiés (détails ci-dessous). Pour une version non-simplifiée des tracés, [utiliser la branche "v2-hd-dev"](https://github.com/gregoiredavid/france-geojson/tree/v2-hd-dev).

## Meta-données

À chaque territoire sont associées les propriétés suivantes :

* **Code** issu du [Code Officiel Géographique](http://www.insee.fr/fr/methodes/nomenclatures/cog/documentation.asp) de l'INSEE
* **Nom** du territoire

## Sources / Mises à jour

Données à jour au 16 avril 2017 :

* [INSEE](http://www.insee.fr/fr/methodes/nomenclatures/cog/telechargement.asp) pour les noms et codes (données 2016).
* [IGN / Geofla](http://professionnels.ign.fr/geofla) pour les contours (version 2.2, 28 juin 2016)

## Cookbook

Conversion des contours du format SHP au GeoJSON via [Mapshaper](https://github.com/mbloch/mapshaper) (cli) avec une simplification ("visvalingam weighted", [en savoir plus](https://github.com/mbloch/mapshaper/wiki/Command-Reference#-simplify)) à 15%. Les tracés originaux, non simplifiés, sont disponibles dans la branche "v2-hd-dev" du projet.

## Données manquantes / incomplètes

* **Arrondissements de mayotte** données incomplètes sur le portail de l'IGN.
* **[Collectivités d'outre-mer (COM)](https://fr.wikipedia.org/wiki/Collectivit%C3%A9_d%27outre-mer)**, c'est à dire la Polynésie française, Saint-Barthélemy, Saint-Martin, Saint-Pierre-et-Miquelon et Wallis-et-Futuna. Données non proposées par l'IGN à cette date.
* **[Découpage infracommunal en IRIS](http://professionnels.ign.fr/contoursiris)**, à venir dans une version future.

## Licence

Voir conditions d'utilisation de GEOFLA ([Licence ouverte](http://www.etalab.gouv.fr/pages/licence-ouverte-open-licence-5899923.html)).

## Contribuer

Contributions bienvenues. PR de préférence sur la branche v2-dev.
