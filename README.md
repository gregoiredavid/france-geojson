Dernière mise à jour 28 octobre 2016.

# Régions, départements et communes métropolitaines françaises au format GeoJSON

Ce projet contient les tracés des entités géographiques et administratives françaises suivantes au format [GeoJSON](http://geojson.org/) :

* Régions (post-redécoupage de 2015).
* Anciennes régions métropolitaines (avant redécoupage).
* Départements
* Cantons
* Arrondissements
* Communes

Des fichiers nationaux, avec et sans les DOM-TOM, sont inclus à la racine du projet et des subdivisions [par région](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/regions/) et [par département](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/) dans leurs dossiers respectifs :

* Contours des départements par région (exemple : [Départements de la région Bourgogne-Franche-Comté](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/regions/bourgogne-franche-comte/departements-bourgogne-franche-comte.geojson)).
* Contours des arrondissements par région et par départements (exemple : [Arrondissements du Finistère](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/29-finistere/arrondissements-29-finistere.geojson)).
* Contours des cantons par région et par départements (exemple : [Cantons de Corrèze](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/19-correze/cantons-19-correze.geojson)).
* Contours des communes par région et par départements (exemple : [Communes du Bas-Rhin](https://github.com/gregoiredavid/france-geojson/blob/v2-dev/departements/67-bas-rhin/communes-67-bas-rhin.geojson)).

## Meta-données

À chaque territoire sont associées les propriétés suivantes :

* **Code** issu du [Code Officiel Géographique](http://www.insee.fr/fr/methodes/nomenclatures/cog/documentation.asp) de l'INSEE
* **Nom**

## Sources / Cookbook

* [INSEE](http://www.insee.fr/fr/methodes/nomenclatures/cog/telechargement.asp) pour les noms et codes (données 2016).
* [IGN / Geofla](http://professionnels.ign.fr/geofla) pour les contours (version 2.2, 28 juin 2016)

Conversion des contours du format SHP fourni par l'IGN au GeoJSON via [GDAL ogr2ogr](http://www.gdal.org/ogr2ogr.html). Exemple :

```
ogr2ogr -f GeoJSON -t_srs crs:84 newfile.geojson source.shp
```

## Licence

Voir conditions d'utilisation de GEOFLA ([Licence ouverte](http://www.etalab.gouv.fr/pages/licence-ouverte-open-licence-5899923.html)).
