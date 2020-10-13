# Schéma de données d'aménagements cyclables 

Schéma des aménagements cyclables.
Ce schéma permet de modéliser et définir les aménagements cyclables.  

Contexte
Dans le cadre des travaux de l’équipe du Point d’accès national et de la mise en oeuvre de l’ouverture des données pour améliorer l’information dont disposent les voyageurs, l’équipe de transport.data.gouv.fr, en collaboration avec l'association Vélo & Territoires, proposent une solution simple et structurée pour l’ouverture des données de parcs de stationnement en France : la Base Nationale des aménagements cyclables (BNLAC). Il s’adresse à toute nouvelle agglomération qui souhaiterait se lancer dans l’ouverture d’une base décrivant les aménagements cyclables de son ressort territorial.

Cadre juridique
L’ouverture des données sur les aménagements cyclables nécessaires à l’information voyageur est une obligation légale, définie par le règlement délégué (UE) 2017/1926 concernant la mise à disposition de services d’informations sur les déplacements multimodaux. Le règlement statue la création d’un Point d’Accès National par pays membre, et que les données nécéssaires à l’information voyageur y soient mises à disposition. Le règlement exige la mise à disposition des données concernant les caractéristiques du réseau cyclable à échéance du 1er décembre 2019.

Ces obligations sont précisées en droit français par la loi d’orientation des mobilités (LOM), qui désigne les collectivités territoriales comme étant responsables de la mise à disposition des données sur la plateforme transport.data.gouv.fr, qui constitue le Point d’Accès National des données de mobilité pour la France.
Les collectivités ont la responsabilité de transmettre les données existantes les plus complètes possibles.

Finalité
Afin de faciliter la réutilisation de ces données, et réduire le coût d’intégration de ces données dans des services tiers, un schéma a été défini afin d’assurer une harmonisation de ces données sur l’ensemble du territoire. Le schéma définit des informations nécessaires et des données additionnelles. Cette distinction a été mise en place pour ne pas pénaliser les petits producteurs de données, et définit un standard minimal de complétude des données. Il est cependant demandé aux producteurs de données de compléter le schéma avec le plus grand niveau de détail possible, afin de transmettre une information plus riche à l’usager final.
La base des aménagements cyclables permet ainsi de regrouper en un unique fichier consolidé l’ensemble des itinéraires aménagés pour les cyclistes. 

La base présente plusieurs cas d’usage :

Elle permet de mettre en avant les aménagements cyclables d’une collectivité en permettant à des services de calcul d’itinéraire d’intégrer ces données. Cela permet notamment à ces services de proposer des itinéraires favorisant la mobilité douce à leurs usagers.
Elle peut servir également à favoriser l'usage du vélo dans les plans de mobilité des entreprises.

Le schéma de la base de données a été co-construit avec l'association Vélo & Territoires, les producteurs de données et les réutilisateurs. Trois ateliers ouverts (le 27/06/2019, le 08/07/2020 et le 27/08/2020) ont permis sa production. Aujourd’hui en version 0.1.0, il sera mis-à-jour prochainement.

Vous trouverez ici la documentation détaillée du schéma de la base de données : lien.

Ce dataset comprend notamment :

le code INSEE de la commune 
la géolocalisation des aménagements cyclables
le type d'aménagement 
le sens de circulation des cyclistes
la vitesse de circulation des véhicules motorisés dans le trafic adjacent 

Attention : ce dataset ne concerne pas le stationnement vélo. 

Format de fichier
Le fichier doit être encodé en UTF-8 et utiliser le point-virgule comme séparateur de colonnes. Aucune valeur ne peut contenir le caractère « point-virgule » choisi comme séparateur, sauf dans le cas des “listes ouvertes” où on peut séparer les différentes attributs par des points virgules. L’en-tête de colonne sur la première ligne est obligatoire. Tous les champs sont obligatoires ; si la donnée n’est pas disponible, la colonne doit être présente et vide.
Nom du fichier : AménagementCyclable_nom_AAAAMMJJ.csv avec nom étant le nom de la collectivité productrice des données, par exemple AménagementCyclable_Ain_20191013.csv.

Consolidation
Cette base de données est issue de l’assemblage de fichiers de données transmis par des producteurs. Nous tenons à les remercier pour leur travail de normalisation des fichiers. Le travail de consolidation est fait en continu par l’association Vélo & Territoires et l'équipe de transport.data.gouv à partir de fichiers qui sont publiés sur data.gouv avec le tag “aménagements cyclables”, des fichiers importés depuis OpenStreetMap ou qui sont transmis directement par mail.

Transmission des données
Dans le but de constituer un répertoire consolidé des aménagements cyclables en France, les collectivités peuvent transmettre systématiquement les données relatives à ces aménagements. 
Elles peuvent ajouter le mot-clef "aménagement cyclable" lors de la publication du jeu de données sur leur espace de publication ou directement sur data.gouv.fr.
En cas de mise à jour d’un fichier déjà intégré à la base consolidée, il est recommandé de prévenir l’équipe transport.data.gouv.fr afin de s’assurer que la mise à jour du fichier a bien été pris en compte et intégré à la base consolidée.

Mise-à-jour
La Base Nationale des Aménagements Cyclable est mise-à-jour en continu par Vélo & Territoires. Elle publie de manière ponctuelle de nouvelles versions à mesure que de nouveaux aménagements cyclables sont recensés ou mis-à-jour par les producteurs de données. Cette mise à jour se fait à partir du fichier communiqué précédemment et en reprennent, en les modifiant le cas échéant, les données qui y figurent déjà. Le fichier principal du dataset constitue systématiquement la dernière mise-à-jour.


Conditions d’utilisation
Comme cela est indiqué dans les métadonnées, ce fichier et ses mises-à-jour sont distribués sous la licence ODbL. Cela signifie que vous pouvez télécharger librement cette base, la réutiliser, la modifier, l’utiliser commercialement, etc, tant que vous en mentionnez la source (par exemple dans les mentions légales de votre application) et que vous repartagez les modifications, améliorations et corrections éventuelles dans les mêmes conditions que cette base (licence ODbL). Plus d’informations ici.


Fichiers d’exemples
Vous pouvez télécharger des fichiers gabarits d’exemple :
Un fichier au format CSV ;
Un fichier au format tableur.



