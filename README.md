# Schéma de données d'aménagements cyclables

Schéma des aménagements cyclables.
Ce schéma permet de modéliser et définir les aménagements cyclables sur le territoire national.   

## Contexte

Dans le cadre des travaux de l’équipe du Point d’accès national et de la mise en oeuvre de l’ouverture des données pour améliorer l’information dont disposent les voyageurs, l’équipe de transport.data.gouv.fr, en collaboration avec l'association Vélo & Territoires, propose une solution simple et structurée pour l’ouverture des données sur les aménagements cyclables : la Base Nationale des Aménagements Cyclables (BNAC). 

Le schéma de la base de données a été co-construit avec Vélo & Territoires, les producteurs de données et les réutilisateurs. Cinq ateliers ouverts (le 14/04/2020, le 8/06/2020, le 27/06/2019, le 8/07/2020 et le 27/08/2020) ont permis sa production. Il a été établi après une enquête et plusieurs réunions du groupe de travail.

## Cadre juridique

L’ouverture des données sur les aménagements cyclables nécessaires à l’information voyageur est une obligation européenne, définie par le règlement délégué (UE) 2017/1926 concernant la mise à disposition de services d’informations sur les déplacements multimodaux. Le règlement statue la création d’un Point d’Accès National par pays membre ainsi que la mise à disposition des données nécessaires à l’information voyageur sur celui-ci. Le règlement exige la mise à disposition des données concernant les caractéristiques du réseau cyclable à échéance du 1er décembre 2019.

En droit français, ces obligations concernent en particulier les collectivités territoriales en tant que gestionnaire de ces infrastructures et sont donc  responsables de la mise à disposition des données sur la plateforme transport.data.gouv.fr. Les collectivités ont la responsabilité de transmettre les données existantes les plus complètes possibles.

## Finalité

Afin de faciliter la réutilisation et réduire le coût d’intégration de ces données dans des services tiers, un schéma a été défini afin d’assurer une harmonisation de ces données sur l’ensemble du territoire. Ce schéma définit des informations indispensables et complémentaires à fournir par le producteur. Cette distinction a été mise en place pour ne pas pénaliser les petits producteurs de données, et définit un standard minimal de complétude des données. Il est toutefois demandé aux producteurs de données de compléter le schéma avec le plus grand niveau de détail possible, afin de transmettre une information plus riche à l’usager final. La base des aménagements cyclables permet ainsi de regrouper en un unique fichier consolidé l’ensemble des infrastructures cyclables.

La base présente plusieurs cas d’usage :
Elle recense les aménagements cyclables d’une collectivité en permettant à des services de calcul d’itinéraire d’intégrer ces données. Cela permet notamment à ces services de proposer des itinéraires favorisant la mobilité douce à leurs usagers. Elle peut servir également à favoriser l'usage du vélo dans les plans de mobilité des entreprises.

Ce jeu de données comprend notamment :
- le code INSEE de la commune ;
- la géolocalisation des aménagements cyclables ;
- le type d'aménagement cyclable ;
- la vitesse de circulation des véhicules motorisés dans le trafic adjacent.


Attention : ce jeu de données ne concerne pas le stationnement cyclable. Vous trouverez le schéma national pour le stationnement cyclable [ici](https://schema.data.gouv.fr/etalab/schema-stationnement-cyclable/latest.html).

## Format de fichier

Les jeux de données seront publiés au format GeoJSON. Certains champs sont obligatoires et d'autres optionnels. Les champs obligatoires doivent être complétés. Pour les champs optionnels, nous recommandons de [ne pas faire apparaître le champ pour l'aménagement concerné lorsqu'il n'y a aucune valeur à renseigner](https://doc.transport.data.gouv.fr/producteurs/amenagements-cyclables/foire-a-questions#mon-fichier-nest-pas-valide-car-il-contient-des-valeurs-null-comment-corriger-cela) ou d'indiquer la valeur `null` (la chaine de caractères `"null"` n'est pas acceptée).

Les producteurs peuvent saisir leurs données sur :
- leurs logiciels internes, avec l'aide des outils développés par Vélo & Territoires, à savoir : 
    - Un [gabarit au format shapefile](https://github.com/etalab/schema-amenagements-cyclables/blob/master/tools/AC_TEMPLATE_SHP_QGIS.zip) pour QGIS ;
    - Un [script SQL pour la création d’une base de données Postgres/PostGIS](https://github.com/etalab/schema-amenagements-cyclables/blob/master/tools/AC_SQL_POSTGIS.zip) « vierge ».
- la base de données OpenStreetMap (OSM).

Ces outils sont hébergés dans le dossier [tools](https://github.com/etalab/schema-amenagements-cyclables/tree/master/tools) de ce répertoire. Pour toute question sur ces outils, vous pouvez contacter la cellule SIG de Vélo & Territoires à cette adresse : sig@velo-territoires.org


## Publication

Dans le but de maintenir à jour un répertoire consolidé des aménagements cyclables en France, les collectivités sont invitées à transmettre systématiquement les données relatives à leurs aménagements. 
Elles peuvent ajouter le mot-clef "aménagement cyclable" lors de la publication du jeu de données dans leur espace de publication ou directement sur data.gouv.fr.
Les producteurs pourront :
- publier directement sur data.gouv.fr ;
- demander à Géovélo de convertir leurs données vers le schéma national ;
- publier directement sur OpenStreetMap afin que Géovélo se charge de la conversion vers le schéma national et de la publication sur data.gouv.fr.

Nous préconisons aux producteurs de données de publier leurs fichiers avec la règle de nommage suivante : `amenagementcyclable_nom.geojson` avec nom étant le nom de la collectivité productrice des données, par exemple `amenagementcyclable_ain.geojson`.

**Nous invitons également les producteurs de données à sélectionner "schéma d'aménagements cyclables" dans la liste déroulante de la section "schema" sur data.gouv.fr lorsqu'ils publieront leurs fichiers.**

En cas de mise à jour d’un fichier déjà intégré à la base consolidée, il est recommandé de prévenir l’équipe transport.data.gouv.fr qui s’assurera de l'actualisation du fichier en question et de son intégration dans la base consolidée à l'adresse : contact@transport.beta.gouv.fr

## Consolidation

Cette base de données ainsi construite est issue de l’assemblage de fichiers de données transmis par des producteurs. Nous tenons à les remercier pour leur travail de normalisation des fichiers. 

Deux bases seront publiées sur transport.data.gouv.fr :
- une [base rassemblant les données publiées sur ](https://transport.data.gouv.fr/datasets/amenagements-cyclables-france-metropolitaine/). Géovélo sera en charge de l'extraction de ces données et de leur mise à jour mensuelle ;
- une base nationale consolidant les données publiées par les collectivités sur data.gouv.fr et celles publiées sur OSM. Cette base est hébergée par Vélo & Territoires et accessible via une carte en ligne à l'adresse suivante : [Velodatamap - carte aménagements](https://velodatamap.velo-territoires.org/vmap/dashboard/map?map_id=14).


## Mise à jour

La consolidation de la base sera effectuée en continu par transport.data.gouv.fr à partir des fichiers publiés sur data.gouv avec le tag “aménagements cyclables” par les producteurs, Vélo & Territoires et Géovélo. De nouvelles versions seront publiées lorsque de nouveaux aménagements cyclables seront recensés ou mis-à-jour par les producteurs. Cette mise à jour se fait à partir du fichier communiqué précédemment et en reprenant, en les modifiant le cas échéant, les données existantes. Le fichier principal du jeu de données constitue ainsi systématiquement la dernière mise à jour.


## Conditions d’utilisation

Comme indiqué dans les métadonnées, le fichier et ses mises à jour sont distribués sous la licence ODbL. Cela signifie que vous pouvez télécharger librement cette base, la réutiliser, la modifier, l’utiliser commercialement, etc, tant que vous en mentionnez la source (par exemple dans les mentions légales de votre application) et que vous repartagez les modifications, améliorations et corrections éventuelles dans les mêmes conditions que cette base (licence ODbL). Plus d’informations ici.





Nous tenons à remercier les membres du groupe de travail pour leur investissement dans l'élaboration de ce schéma.
