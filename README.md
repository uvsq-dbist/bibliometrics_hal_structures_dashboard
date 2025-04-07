# bibliometrics_hal_structures_dashboard
<h1>Dashboard de structures Hal</h1>
<h2>En un mot</h2>
L'objectif de l'outil est de présenter les sous-structures Hal d'une structure première sous deux formes :
<ul>
  <li>hiérarchique : pour avoir une bonne appréciation de l'arboresence et pour pouvoir facilement avoir accès aux liens de modification</li>
  <li>"plate" : pour faciement pouvoir décharger en format .csv toutes les sous-structures</li>
</ul>
<h2>Utilisation</h2>
L’utilisateur se voit présenter un formulaire qui contient toutes les sous-structures de l'UVSQ. (Mais il peut aussi choisir une autre institution que l'UVSQ, le bouton se trouve un peu plus bas dans la page). Il choisit une sous structure et se voit proposer deux possibilités : affichage hiérachique ou affichage plat. 
<ul>
<li>affichage hiérarchique : l'utilisateur peut, visuellement, mettre en avant ou mettre en retrait les structures selon leur type ou leur "validity"
<li>affichage "plat" : l'utilisateur peut décharger le tableu en format .csv
  </ul>
Dans les deux cas l'affichage concerne la sous-structure choisie ET celles qui sont "en dessous" de cette sous-structure
<h2>Langage</h2>
HTML, JavaScript
<br/><br/>
N'importe quel browser permet d'utiliser le code
<h2>Fichiers</h2>
Pour permettre une instalation la plus facile possible tout le code (toutes les fonctions) se trouve dans un seul fichier de code
<h2>Dépendance</h2>
L'outil est dépendant de l'API Hal telle qu'elles existent aujourd'hui (avril 2025) avec le point d'entrée https://entrepot.recherche.data.gouv.fr/api/search
<h2>Fonctionnement, fonctions</h2>
<ul>
  <li>Fonctions
  <ul>
<li>Fonction de recherche / affichage du formulaire :
<ul>
<li>get_first_hal_affiliation_data_function() <== lancé au chargement de la page 
ou lancé par le bouton de changement de structure
<br/>puis : </li>
<li>
  get_hal_affiliation_data_function() <= récursive
<br/>puis, quand arrivé à la fin : </li>
<li>build_selection_from_element_function()</li>
  </ul>
</li>
<li>Fonctions d'affichage :
  <ul>
<li>affichage hierarchique : 
  <ul>
<li>hierarchical_display_function() <== déclenché par bouton
<br/>puis : 
<li>hierarchical_display_from_element_function()
<br/>puis : 
<li>display_one_hierarchical_line_function() <== fabrique une ligne
  </ul>
  </li>
<li>affichage plat : 
<ul>
  <li>flat_display_function() <== déclenché par bouton
<br/>puis : 
<li>flat_display_from_element_function()
<br/>
  puis :
<li>display_one_flat_line_function() <== fabrique une ligne
</ul>
</li>
  </ul>
</li>
<li>Fonction multi-usage :
get_element_function()
(utilisée dans get_hal_affiliation_data_function(), dans hierarchical_display_function(), 
et dans flat_display_function())
</li>
<li>Fonction de mise en avant / mise en retrait des affichages 
de la visualisation hiérarchique :
switch_function()
</li>
<li>Fonctions de déchargement .csv de la table plate :
<ul>
<li>download_main_file_function() <== déclenché par bouton</li>
<li>table_to_csv_function()</li>
</ul>
</li>
</ul>
</li>
  <li>Codes couleurs : les types et les validities sont associés à des couleurs. Elles sont gérées dans le tag &lt;style&gt;. Les couleurs des validities sont les couleurs officielles Hal</li>
<li>Mise en avant / en retrait : l'affichage hiérarchique permet une mise en avant / en retrait de certains lignes. Celle ci fait intervenir l'opacité et la taille des caratères. Les valeurs sont réunies dans deux variables : 
  <br/>var opacity={"standard":1,"down":0.5};
<br/>var font_size={"standard":1,"down":0.75};
</li>
  </ul>
