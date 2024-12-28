<h1 align="Center">Examen Final - 40% (1Q2-Programmation structurée)</h1>

## Contexte

Lors de cet examen final, vous devez démontrer votre capacité à appliquer les connaissances acquises en classe afin de compléter une mini-application répondant aux spécifications d'un client potentiel.

<h1 align="Center">Consignes à suivre</h1>

1. 🪑 Les places seront attribuées par l'enseignant, sans exceptions.  Vous aurez du temps pour configurer l'environnement de travail à votre aise.
1. 🖥️ L'utilisation d'un seul écran ne sera permise. Vous devrez vous assurer, en appuyant sur le bouton en dessous de l'écran secondaire, que ce dernier sera désactivé de Windows et il se fermera automatiquement.
   > Si un deuxième écran est apperçu allumé, la personne étudiante se verra automatiquement attribuée la note de zéro.
2. 📱 Les cellulaires doivent être fermés (pas en mode avion mais complètement fermés) et placés la boîte prévue à cet effet, en avant de la classe.
   > Si une notification est entendue pendant l'examen, la personne étudiante se verra automatiquement attribuée la note de zéro.
3. 🎧 Les casques d'écoutes, lunettes électroniques ou tout autre dispositif électronique devront être placés dans votre sac à dos que vous déposerez en avant de la classe en dessous du tableau.
   > Si un appareil électronique est aperçu, la personne étudiante se verra automatiquement attribuée la note de zéro.
4. 🚪 Sauf urgence, aucun accès à la salle de bain ne sera autorisé.
   > Nous attendrons que toutes les personnes étudiantes aient eu le temps d'y aller avant de débuter l'examen.`
5. ❓ Une seule question ne sera permise par personne. Assurez-vous de bien avoir lu l'énoncé avant d'interroger l'enseignant !
5. 🖋️ Après la remise de votre solution sur Omnivox, vous devrez aller signer la feuille de confirmation de dépôt.
   > Si une personne étudiante quitte sans signer la feuille de confirmation de dépôt, elle se verra automatiquement attribuée la note de zéro.

<h1 align="Center">🖥️ Atlas Informatique 🖥️</h1>

**Atlas Informatique**, une entreprise œuvrant dans la vente rapide de matériel informatique, a besoin d'une mini-application qui affiche d'abord la liste des produits disponibles. Comme elle veut écouler rapidement son inventaire, elle aimerait que vous puissiez générer un rabais entre 10% et 50% et ce, pour 10 produits sélectionnés au hasard. Ensuite la mini-application conservera ces produits et ces rabais tout au long de la génération de commandes.

L'entreprise souhaite ensuite pouvoir tester son système d'achat en ligne en vous demandant de générer 5 commandes complètes (produits, quantité, sous-total, TPS, TVQ, total) avec précisément 3 lignes d'`Achat` par commande (pour simplifier les tests). Un `Achat` représente une ligne de produit dans une commande (exemple: 3 exemplaires du produit au code 938475).

Cédrik Dubogue, un employé de la compagnie **Atlas Informatique**, à créé une [solution C++](./_bin/atlas.zip). en y programmant l'architecture générale requise selon l'analyse effectuée par l'équipe de développement. Il vous demande donc de débuter votre travail à partir de cette solution et d'analyser le code en place. Il a placé des étiquettes `TODO` aux endroits où, au minimum, vous aurez à programmer afin de répondre aux besoins de son entreprise (merci pour ce petit coup de main Cédrik 😉 )

Vous êtes donc embauchés afin de reprendre ce projet et de le faire fonctionner.

Voici un exemple de visuel du devis du client :

## Liste des produits

```plaintext
----------------------------------------------------------------------------------------------------
|                                      Liste des produits                                          |
----------------------------------------------------------------------------------------------------
| CODE   | NOM                  | DESCRIPTION                         |  VALEUR | RABAIS |    PRIX |
----------------------------------------------------------------------------------------------------
| 911410 | Laptop               | Puissant et performant              | 1074.61 |        | 1074.61 |
| 063880 | Souris gaming        | RGB et ergonomique                  |   50.65 |        |   50.65 |
| 822194 | Clavier mAccanique   | RActroAcclairage RGB                |   75.99 |    29% |   53.95 |
| 594943 | A%cran 24 pouces     | Full HD 144Hz                       |  201.58 |        |  201.58 |
| 167139 | Casque audio         | Sans fil avec rAcduction de bruit   |  146.52 |        |  146.52 |
| 683777 | Carte graphique      | NVIDIA RTX dernier cri              |  457.79 |    43% |  260.94 |
| 261197 | Disque dur SSD       | 1 To NVMe rapide                    |  111.87 |    33% |   74.95 |
| 906036 | Alimentation         | 750W certifiAc 80 PLUS Gold         |  102.35 |    11% |   91.09 |
| 328317 | BoArtier PC          | Design moderne avec verre trempAc   |   94.32 |    17% |   78.29 |
| 363299 | Processeur           | AMD Ryzen haute vitesse             |  324.78 |        |  324.78 |
| 299530 | Laptop               | Puissant et performant              | 1114.17 |        | 1114.17 |
| 503593 | Souris gaming        | RGB et ergonomique                  |   47.44 |    13% |   41.27 |
| 741194 | Clavier mAccanique   | RActroAcclairage RGB                |   74.47 |        |   74.47 |
| 546206 | A%cran 24 pouces     | Full HD 144Hz                       |  206.52 |    31% |  142.50 |
| 794095 | Casque audio         | Sans fil avec rAcduction de bruit   |  151.52 |        |  151.52 |
| 002940 | Carte graphique      | NVIDIA RTX dernier cri              |  367.09 |        |  367.09 |
| 082927 | Disque dur SSD       | 1 To NVMe rapide                    |  105.41 |    45% |   57.98 |
| 347402 | Alimentation         | 750W certifiAc 80 PLUS Gold         |   84.05 |        |   84.05 |
| 599341 | BoArtier PC          | Design moderne avec verre trempAc   |   85.39 |    14% |   73.44 |
| 925547 | Processeur           | AMD Ryzen haute vitesse             |  342.92 |    33% |  229.76 |
----------------------------------------------------------------------------------------------------

Appuyez sur ESPACE pour généner les commandes...
```

## Génération des commandes

```plaintext
--------------------------------------------------------------
|                      Commande #1001                        |
--------------------------------------------------------------
| CODE   | NOM                  | QTÉ |     PRIX |   MONTANT |
--------------------------------------------------------------
| 683777 | Carte graphique      |   5 |  260.94$ |  1304.70$ |
| 363299 | Processeur           |   4 |  324.78$ |  1299.12$ |
| 822194 | Clavier mAccanique   |   3 |   53.95$ |   161.86$ |
--------------------------------------------------------------
                                       | Montant |  2765.68$ |
                                       | TPS     |   138.28$ |
                                       | TVQ     |   275.88$ |
                                       | TOTAL   |  3179.84$ |
                                       -----------------------

--------------------------------------------------------------
|                      Commande #1002                        |
--------------------------------------------------------------
| CODE   | NOM                  | QTÉ |     PRIX |   MONTANT |
--------------------------------------------------------------
| 261197 | Disque dur SSD       |   5 |   74.95$ |   374.76$ |
| 328317 | BoArtier PC          |   1 |   78.29$ |    78.29$ |
| 546206 | A%cran 24 pouces     |   4 |  142.50$ |   570.00$ |
--------------------------------------------------------------
                                       | Montant |  1023.05$ |
                                       | TPS     |    51.15$ |
                                       | TVQ     |   102.05$ |
                                       | TOTAL   |  1176.25$ |
                                       -----------------------

--------------------------------------------------------------
|                      Commande #1003                        |
--------------------------------------------------------------
| CODE   | NOM                  | QTÉ |     PRIX |   MONTANT |
--------------------------------------------------------------
| 063880 | Souris gaming        |   2 |   50.65$ |   101.30$ |
| 683777 | Carte graphique      |   2 |  260.94$ |   521.88$ |
| 503593 | Souris gaming        |   1 |   41.27$ |    41.27$ |
--------------------------------------------------------------
                                       | Montant |   664.45$ |
                                       | TPS     |    33.22$ |
                                       | TVQ     |    66.28$ |
                                       | TOTAL   |   763.96$ |
                                       -----------------------

--------------------------------------------------------------
|                      Commande #1004                        |
--------------------------------------------------------------
| CODE   | NOM                  | QTÉ |     PRIX |   MONTANT |
--------------------------------------------------------------
| 599341 | BoArtier PC          |   1 |   73.44$ |    73.44$ |
| 503593 | Souris gaming        |   3 |   41.27$ |   123.82$ |
| 167139 | Casque audio         |   1 |  146.52$ |   146.52$ |
--------------------------------------------------------------
                                       | Montant |   343.77$ |
                                       | TPS     |    17.19$ |
                                       | TVQ     |    34.29$ |
                                       | TOTAL   |   395.25$ |
                                       -----------------------

--------------------------------------------------------------
|                      Commande #1005                        |
--------------------------------------------------------------
| CODE   | NOM                  | QTÉ |     PRIX |   MONTANT |
--------------------------------------------------------------
| 822194 | Clavier mAccanique   |   1 |   53.95$ |    53.95$ |
| 906036 | Alimentation         |   1 |   91.09$ |    91.09$ |
| 167139 | Casque audio         |   1 |  146.52$ |   146.52$ |
--------------------------------------------------------------
                                       | Montant |   291.56$ |
                                       | TPS     |    14.58$ |
                                       | TVQ     |    29.08$ |
                                       | TOTAL   |   335.23$ |
                                       -----------------------
```

> ATTENTION: Il est à noter que les accents n'ont pas à être gérés dans ce projet.

<h1 align="Center">Spécification techniques</h1>

1. Placer votre nom complet sur la première ligne du fichier `main.cpp`.
2. Respecter le devis du client à la lettre.
3. Respecter les normes et conventions apprises en classe.
4. Remettre un seul fichier `.zip` contenant l'ensemble de la solution.

### Trucs, astuces et rappels

1. Ouvrir le fichier `.csv` avec un editeur de texte afin de bien analyser la structure.
2. Utiliser l'utilitaire `Format document on Save` afin de formater votre code au fur et à mesure.
3. Programmer une seule fonction à la fois et la tester à l'aide du `débogueur`.
4. Pour la signature de la fonction retournerProduitHasard(), revenir au principe de passage par valeur ou par référence.
5. Aurez-vous besoin d'une fonction de recherche pour aller chercher des information d'un `Produit` à partir d'un `Achat` ? 😉

<h1 align="Center">Grille de correction</h1>

| #   | Critère                                                                                                                                     | Pts |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| 01  | La liste des produits est lue du fichier de données et est placée en mémoire.                                                               | 3   |
| 02  | Les rabais sont correctement générés dans les produits en mémoire, respectant le format.                                                    | 5   |
| 03  | La liste des produits s'affiche à l'écran incluant les rabais et le prix de vente.                                                          | 4   |
| 04  | Il est possible de placer une commande complète en mémoire.                                                                                 | 5   |
| 05  | La liste des commandes générées s'affiche correctement à l'écran.                                                                           | 6   |
| 06  | Implémentation et utilisation correcte de la fonction retournerProduitHasard().                                                             | 2   |
| 07  | L'implémentation de la fonction genererRabais s'assure qu'il y ait réellement 10 produits avec des rabais après sont exécution.             | 1   |
| 08  | L'implémentation de la fonction genererCommandes s'assure qu'il y ait pas deux fois le même produit dans deux lignes d'`Achat` différentes. | 1   |
| 09  | Utilisation adécoite et fonctionnelle du code déjà en place écrit par Cédrik Dubogue.                                                       | 3   |
| 10  | Respect des normes et des conventions de code apprises en classe.                                                                           | 10  |
| P  | Non-respect d'un des éléments de l'énoncé (par présence)                                                                          | -1  |
|     |
|     | TOTAL                                                                                                                                       | 40  |
|     |

<p align="Center"><img src="./images/end.png" alt="drawing" width="150"/></p>
