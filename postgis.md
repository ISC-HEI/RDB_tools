# Postgis

## Qu'est ce que Postgis ?

PostGIS est une extension de **PostgreSQL**, une base de données relationnelle, qui ajoute un support complet pour les données géographiques. Grâce à cette extension, il est possible de stocker, manipuler et analyser des informations spatiales, telles que :  
- **Points** : par exemple, un lieu spécifique comme un événement ou une adresse.  
- **Lignes** : comme des routes, des chemins ou des rivières.  
- **Polygones (surfaces)** : par exemple, des zones comme des quartiers, des parcs ou des territoires administratifs.

PostGIS propose une riche bibliothèque de fonctions géospatiales qui permettent de répondre à des questions complexes:  
- Quelle est la distance entre deux lieux ?  
- Quels points d'intérêt se trouvent dans une certaine zone ?  
- Quelle est l'intersection entre deux surfaces géographiques ?  

C'est un outil largement utilisé dans des domaines variés, tels que l'urbanisme, la gestion environnementale, la logistique et les transports.

## Exemples d'utilisation de Postgis
Voici un exemple concret d'utilisation de PostGIS pour fusionner des données géographiques de deux tables (quartiers et homicides) issues d'une base de données de la ville de New York (https://www.crunchydata.com/blog/postgis-for-newbies).

```SQL
SELECT 
    'Neighborhood' AS type,
    ne.boroname AS neighborhood,
    ne.name AS district_name,
	NULL as motive,
    NULL AS weapon,
    NULL AS year,
    NULL AS num_victims,
    ne.geom
FROM nyc_neighborhoods AS ne

UNION ALL

SELECT 
    'Homicide' AS type,
	NULL AS neighborhood,
    NULL AS district_name,
	ho.primary_mo AS motive,
    ho.weapon AS weapon,
    ho.year AS year,
    ho.num_victim AS num_victims,
    ho.geom
FROM nyc_homicides AS ho;
```

<img src="https://github.com/user-attachments/assets/be79b23f-d212-4eea-9f05-d0521e656506" height="400">

<img src="https://github.com/user-attachments/assets/bbd5bfc8-48ce-41b8-bd22-9e16b03d39f8" height="400">

<img src="https://github.com/user-attachments/assets/2bf1547f-256d-47c4-9356-39c5799b2c7c" height="400">

Vous pouvez visualiser ci-dessus les résultats de la requête directement dans un logiciel, tel que PGAdmin. Il est possible d'interagir avec la carte pour obtenir les informations souhaitées sur les différents homicides et quartiers.
