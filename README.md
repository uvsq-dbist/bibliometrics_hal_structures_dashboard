# bibliometrics_hal_structures_dashboard
<h1>Dashboard de structures Hal</h1>
<h2>En un mot</h2>
L'objectif de l'outil est de présenter les sous-structures Hal d'une structure première sous deux formes
<ul>
  <li>hiérarchique : pour avoir une bonne appréciation de l'arboresence et pour pouvoir facilement avoir accès aux liens de modification</li>
  <li>"plate" : pour faciement pouvoir décharger en format .csv toutes les sous-structures</li>
</ul>
<h2>Utilisation</h2>
L’utilisateur se voit présenter un formulaire qui contient toutes les sous-structures de l'UVSQ. (Mais il peut aussi choisir une autre institution que l'UVSQ, le bouton se trouve un peu plus bas dans la page). Il choisit une sous structure et a un choix : affichage hiérachique ou affichage plat de la sous-structure choisie et de elle qui sont "en dessous" de cette sous-structure
<br/><br/>
Il recoit une liste de datasets classés par dataverse. Pour chaque dataset : le nom, avec un lien, la descrition, le publisher, les producers
<h2>Langage</h2>
HTML, JavaScript
<br/><br/>
N'importe quel browser permet d'utiliser le code
<h2>Fichiers</h2>
Pour permettre une instalation la plus facile possible tout le code (toutes les fonctions) se trouve dans un seul fichier, check_RDG.html.html
<h2>Dépendance</h2>
L'outil est dépendant des API de Recheche Data Gouv telle qu'elles existent aujourd'hui (mars 2025) avec le point d'entrée https://entrepot.recherche.data.gouv.fr/api/search
<h2>Fonctionnement, fonctions</h2>
La fonction send_function() lance le processus, elle est déclenchée par le bouton du formulaire
<br/><br/>
La fonctin get_data_function() va chercher les données, via un fetch
<br/><br/>
La fonction can_data_function() stocke les données, dans trois variables : dataset_data_object, dataverse_data_object, data_structure_object
<br/><br/>
La fonctin display_data_function() affiche les données
