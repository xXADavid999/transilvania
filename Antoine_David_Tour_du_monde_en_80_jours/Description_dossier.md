# Description du dossier sur *Le tour du monde en 80 jours* de Jules Verne

Ce dossier constitue une étude du texte *Le tour du monde en 80 jours* de Jules Verne, notamment avec l'utilisation d'Iramuteq pour créer des visualisations à partir de statistiques issues de cette oeuvre. Il a fallu récupérer le texte intégral pour pouvoir l'encoder afin de l'étudier avec Iramuteq. Grâce aux visualisations, un spécialiste pourra mettre en avant les rapports et thèmes de l'oeuvre.

## Récupération du texte et encodage

Pour créer un fichier .txt contenant l'ensemble de l'oeuvre, j'ai récupéré le texte sur [Wiki Source](https://fr.wikisource.org/wiki/Le_Tour_du_monde_en_quatre-vingts_jours/Texte_entier).  

J'ai procédé à un nettoyage très rapide : suppression de l'indicateur dynamique des pages qui s'était mis à la fin de mon document, simplification de l'entête.  
J'ai ensuite encodé mon texte en assignant une variable à chaque chapitre, soit 37 variables différentes.

Lien vers [Le tour du monde en 80 jours.txt](https://github.com/xXADavid999/Antoine_David_Tour_du_monde_en_80_jours/blob/master/Le%20tour%20du%20monde%20en%2080%20jours.txt).

## Version Epub de l'oeuvre

Je suis allé sur le site du Projet Gutenberg pour trouver *Le tour du monde en 80 jours* en [version .epub](http://www.gutenberg.org/ebooks/800), il est intéressant de noter qu'il existe plusieurs versions avec ou sans images, et avec différents formats pour faciliter l'accessibilité.

## Les fichiers en .CSV des occurences

Les visualisations issues d'Iramuteq proviennent d'analyses statistiques que l'on peut retrouver dans les .CSV suivants :

+ [total.csv](https://github.com/xXADavid999/Antoine_David_Tour_du_monde_en_80_jours/blob/master/CSV/total.csv) : sur ce document on retrouve l'ensemble de mots par fréquence décroissante.
+ [formes_actives.csv](https://github.com/xXADavid999/Antoine_David_Tour_du_monde_en_80_jours/blob/master/CSV/formes_actives.csv) : sur ce document, on trouve  la liste   des   formes/mots   actifs (avec   leur   catégorie grammaticale) par fréquences décroissantes. 

Iramuteq résume les statisques générales comme : 
+ Nombre de textes : 37
+ Nombre d'occurrences : 71179
+ Nombre de formes : 5600
+ Nombre d'hapax : 2360 (3,32% des occurrences - 42,14% des formes)
+ Moyenne d'occurrences par texte : 1923,76

Le nombre de texte fait référence à mes variables qui représentent les 37 chapitres du roman.

Comme l'oeuvre étudiée possède 37 chapitres, il m'est également possible d'extraire des CSV pour chaque chapitre ou par regroupement arbitraire de chapitre.


## Visualisation de données 

![représentation statistiques des fréquences sur l'ensemble de l'oeuvre](https://github.com/xXADavid999/Antoine_David_Tour_du_monde_en_80_jours/blob/master/Visualisations/Statistiques%20totales.PNG)

Ce graphique est issu de l'outil statistique d'Iramuteq. On retrouve sur l'axe des ordonnées la fréquence des mots cités, et sur l'axe des abscisses la quantité d'occurrences. Sans surprise, on retouve une petite quantité de mots cités beaucoup de fois, et une grande quantité de mots peu cités.  

![nuage de mots sur l'ensemble de l'oeuvre](https://github.com/xXADavid999/Antoine_David_Tour_du_monde_en_80_jours/blob/master/Visualisations/nuage_1_total.png)

Ce nuage de mots représente les 200 occurrences les plus présentes sur l'ensemble de l'oeuvre. En mots les plus cités on retrouve les personnages principaux, mais aussi des thématiques autour du voyage et du temps.

![nuage de mots comparant les chapitres 1 et 37](https://github.com/xXADavid999/Antoine_David_TourDuMondeEn80Jours/blob/master/Visualisations/nuagemot_chap1chap37.png)

Pour ce graphique, j'ai utilisé mes variables pour permettre une comparaison entre différents chapitres, ici le premier et le dernier. J'ai repris les mêmes paramètres que le précédent. Il est possible de combiner les chapitres à volonté pour comparer certains passages.

![Analyse des similitudes](https://github.com/xXADavid999/Antoine_David_TourDuMondeEn80Jours/blob/master/Visualisations/graph_simi_2.png)

Ce graphique est issu de l'outil "analyses de similitudes", il permet de visualiser les mots les plus cités en fonction de leurs rapports aux autres mots. Par exemple, Phileas Fogg apparaît toujours au centre, car il est le personnage principal (Fogg possède 656 occurrences et Phileas 301).

Pour faciliter la lecture, et essayer d'être plus concis, j'ai réduit le nombre de mots en choisissant seulement ceux qui ont 30 ou plus occurrences (ce qui donne 168 mots). J'ai également retiré les mots "Mr" et "Mrs" que je ne trouvais pas pertinent. J'ai utilisé de l'indice de cooccurrence et une présentation de type fruchterman reingold. J'ai également activé l'option pour afficher les regroupements par communautés visibles via les halos.

![Graphique Méthode de Reinert](https://github.com/xXADavid999/Antoine_David_TourDuMondeEn80Jours/blob/master/Visualisations/dendrogramme_2.png)

Sur ce graphique issu de la méthode Reinert, j'ai volontairement choisi de laisser 5 classes, qui ne peuvent retranscrire que de manière partielle la représentation des classes sur toute l'oeuvre. Je trouvais plus pertinent de faire ainsi, car on retrouve nos familles de manière assez similaire à nos premiers graphiques. J'ai essayé en augmentant le nombre de classe, mais à cause du volume de l'oeuvre, on perdait en lisibilité avec un trop grand nombre de classes. En revanche, la méthode Reinert pourrait être pertinente à plus petite échelle, notamment sur des chapitres ou des regroupements de chapitres.

![AFC de la Méthode de Reinert](https://github.com/xXADavid999/Antoine_David_TourDuMondeEn80Jours/blob/master/Visualisations/AFC2DL.png)

Ce deuxième est l'AFC (analyse factorielle des correspondances) issu du dendrogamme fait avec la méthode de Reinert. On retrouve nos 5 grandes classes avec trois qui sont regroupées (les personnages, des lieux, des actions), et les deux autres sont isolées. La classe rouge apparrait lié au champ lexical de la locomotion, tandis que le gris contient de mots liés à la description. Les mots ont également une taille proportionnelle à leur nombre d'occurrence dans le texte.

J'aurais aimé améliorer la visualisation de ce graphique en utilisant Gephi, mais je n'ai pas réussi à le faire fonctionner sur mon ordinateur. 
