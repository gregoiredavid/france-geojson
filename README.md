# France Geojson

Ce projet contient les tracés des entités géographiques et administratives françaises suivantes au format [GeoJSON](http://geojson.org/) :

* Régions
* Départements
* Cantons
* Arrondissements
* Communes

À la racine du repo on trouvera également le tracé des anciennes régions métropolitaines (avant redécoupage de 2015).

## Simplification

Pour optimiser la taille des fichiers, les tracés ont été simplifiés (voir détails ci-dessous : "comment ont été générés ces fichiers ?"). La version "brute", non simplifiée, des tracés est disponible en téléchargement [en cliquant sur ce lien (143 Mo)](https://france-geojson.gregoiredavid.fr/download/france-geojson-raw.tgz).

## Organisation des fichiers

Des fichiers nationaux, avec et sans les départements et régions d'outre-mer, sont inclus à la racine du projet et des subdivisions [par région](https://github.com/gregoiredavid/france-geojson/tree/master/regions/) et [par département](https://github.com/gregoiredavid/france-geojson/tree/master/departements/) dans leurs dossiers respectifs :

* Contours des départements par région (exemple : [Départements de la région Bourgogne-Franche-Comté](https://github.com/gregoiredavid/france-geojson/tree/master/regions/bourgogne-franche-comte/departements-bourgogne-franche-comte.geojson)).
* Contours des arrondissements par région et par départements (exemple : [Arrondissements du Finistère](https://github.com/gregoiredavid/france-geojson/tree/master/departements/29-finistere/arrondissements-29-finistere.geojson)).
* Contours des cantons par région et par départements (exemple : [Cantons de Corrèze](https://github.com/gregoiredavid/france-geojson/tree/master/departements/19-correze/cantons-19-correze.geojson)).
* Contours des communes par région et par départements (exemple : [Communes du Bas-Rhin](https://github.com/gregoiredavid/france-geojson/tree/master/departements/67-bas-rhin/communes-67-bas-rhin.geojson)).


## Meta-données

À chaque territoire sont associées les propriétés suivantes :

* **Code** issu du [Code Officiel Géographique](http://www.insee.fr/fr/methodes/nomenclatures/cog/documentation.asp) de l'INSEE
* **Nom** du territoire

## Sources / Mises à jour

* [INSEE](http://www.insee.fr/fr/methodes/nomenclatures/cog/telechargement.asp) pour les noms et codes (millésime 2018).
* [IGN / Admin Express COG](http://professionnels.ign.fr/adminexpress) pour les tracés (édition 2018)

## Comment ont été générés ces fichiers ?

Les données proviennent d'une conversion des tracés depuis le format SHP fourni par l'IGN vers le format GeoJSON via [Mapshaper](https://github.com/mbloch/mapshaper) (cli).

Les données de l'IGN sont extrèmement précises, pour optimiser la taille des fichiers ceux-ci ont été simplifés de 2 manières :
* La précision des coordonnées a été limitée (conformément [aux recommandations du standard GeoJSON](https://tools.ietf.org/html/rfc7946#section-11.2)) à 5 chiffres après la virgule ce qui correspond à une marge de 1,11 mètres environ.
* Les tracés ont été simplifiés (méthode ["visvalingam weighted"](https://github.com/mbloch/mapshaper/wiki/Command-Reference#-simplify) à 25% (plus ce chiffre est bas plus la simplification est importante).

Exemple de commande mapshaper pour convertir un fichier shapefile de l'IGN (input.shp) au format geojson avec les paramètres décrits ci-dessus :

```
mapshaper -i input.shp snap -proj wgs84 -simplify 25% weighted keep-shapes -o format=geojson precision=0.00001 output.json
```

En cas de besoin, une "version légère" de chaque fichier national (régions, communes, etc...) est également disponible à la racine du repo, elle se base sur les données simplifiées de l'IGN, et une simplification à 5% au lieu de 25% selon la méthode décrite ci-dessus.

Les tracés "bruts", non simplifiés, sont disponibles en téléchargement [en cliquant sur ce lien (143 Mo)](https://france-geojson.gregoiredavid.fr/download/france-geojson-raw.tgz).

## Données manquantes / incomplètes

* **Certains arrondissements** : pas de données pour Mayotte et la Martinique (données absentes de la base Admin Express de l'IGN).
* **[Collectivités d'outre-mer (COM)](https://fr.wikipedia.org/wiki/Collectivit%C3%A9_d%27outre-mer)**, c'est à dire la Polynésie française, Saint-Barthélemy, Saint-Martin, Saint-Pierre-et-Miquelon et Wallis-et-Futuna. Données non proposées par l'IGN à cette date.

## Licence

Voir conditions d'utilisation d'Admin Express ([Licence ouverte](http://www.etalab.gouv.fr/pages/licence-ouverte-open-licence-5899923.html)).

## Contribuer

Contributions, remarques et suggestions bienvenues.
