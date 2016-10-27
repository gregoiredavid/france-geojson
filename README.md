Dernière mise à jour 25 octobre 2016.

# Régions, départements et communes métropolitaines françaises au format GeoJSON

Ce projet contient les données géographiques françaises (Métropole et DOM-TOM) suivantes au format [GeoJSON](http://geojson.org/) :

* Régions (post redécoupage de 2015)
* Départements
* Cantons
* Arrondissements
* Communes

Les fichiers sont organisés par région et par département.

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
