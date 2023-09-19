# <img src="https://raw.githubusercontent.com/CraftLR/workshop-git/main/src/main/resources/assets/logo.png" alt="class logo" class="logo"/> 

## La Rochelle Software Craftsmenship

* **Auteurs:**

  * [Sébastien NEDJAR](mailto:sebastien.nedjar@univ-amu.fr)

* **Besoin d'aide ?**

  * Consulter et/ou créer des [issues](https://github.com/CraftLR/workshop-git/issues).
  * [Email](mailto:sebastien.nedjar@univ-amu.fr) pour toutes questions autres.

## Aperçu du workshop et objectifs d'apprentissage

L'objectif premier de cet atelier est de pratiquer le Test Driven Development (TDD) sur des exemples classiques. Durant cet atelier, vous serez encouragé à découvrir le pair-programming et pratiquer le refactoring pour apprendre à produire un code plus propre.

Les exercices de ce document sont une adaptation de certains [Coding Kata du site codingdojo.org](https://codingdojo.org/kata/) et de ceux proposés par Emilie Bache dans son livre ["The Coding Dojo Handbook"](https://www.amazon.fr/Coding-Dojo-Handbook-Emily-Bache/dp/919811803X).

## Test Driven Development et Kata

### Création de votre fork

Vous connaissez déjà les bases de Git. Si ce n'est pas le cas, vous pouvez vous entraîner avec [l'atelier Git](https://github.com/CraftLR/workshop-git).

La première chose à faire est de créer un fork de ce dépôt. Pour ce faire, rendez-vous sur le lien suivant :

<https://classroom.github.com/a/MVDK521d>

GitHub va vous créer un dépôt contenant un fork de ce dépôt. Vous apparaîtrez automatiquement comme contributeur de ce projet pour y pousser votre travail.

Le travail de cet atelier se fera en binôme. Vous aurez donc deux dépôts sur lequel vous devrez pousser votre travail. Vous pouvez très bien travailler sur un seul dépôt et pousser sur le second uniquement quand vous avez terminé.

### Test Driven Development

Dans les exercices de cet atelier, vous allez devoir écrire les tests unitaires par vous-même. Comme dans l'atelier précédent vous allez devoir appliquer le workflow du TDD (RED, GREEN, REFACTOR). Mais au lieu de simplement activer les cas tests, vous allez les penser et les écrire les uns après les autres.

L'ajout d'un nouveau cas de test doit vous demander de produire que très peu de nouveau code. Dans le vocabulaire du TDD on dit que chaque nouveau cycle doit être un petit pas (ou Baby step).

Les petits pas sont l'une des pratiques de base que vous devez maîtriser avant de devenir un expert en TDD. Cela aide à accélérer considérablement le processus TDD et votre vitesse de codage lorsque vous deviendrez un maître artisan logiciel.

De nombreuses personnes choisissent de sauter des étapes parce qu'elles ont l'impression que faire des pas de bébé est lent. C'est vraiment une mauvaise idée car cela vous empêcherait de devenir un maître et de ne pas profiter des avantages de cette pratique de développement.

#### Qu'est-ce qu'une itération ?

TDD consiste essentiellement à suivre trois étapes simples à plusieurs reprises :

* Rédigez un test pour la prochaine fonctionnalité que vous souhaitez ajouter.
* Écrivez le code fonctionnel jusqu'à ce que le test réussisse.
* Refactorisez à la fois le nouveau et l'ancien code pour le rendre bien structuré.

Chaque fois que vous terminez un cycle, vous avez accompli une itération.

#### Pourquoi devrions-nous suivre Baby Steps par itérations ?

Beaucoup de développeurs ne parviennent pas à faire du TDD parce qu'ils ne savent pas comment trouver un ordre approprié de tests qui pilotent l'implémentation. Ils finissent par écrire seulement quelques cas de test complexes, chaque cas de test couvrant plusieurs scénarios, ce qui entraîne trop peu d'itérations et chaque itération contient beaucoup de code préconçu (le code n'est pas piloté par la refactorisation).

#### Pourquoi les grandes itérations conduisent-elles à du code préconçu ?

Lorsque l'on doit faire fonctionner un test pour plusieurs scénarios, il est difficile d'écrire simplement le code sans penser à la conception. Il est d'autant plus difficile de faire du refactoring car trop *d'odeurs* sont introduites en même temps. Dans ce cas, la seule solution est de réécrire tout le code, ce qui aboutit à un code préconçu. En revanche, si un test n'introduit qu'un seul scénario, il est facile de le faire passer sans trop réfléchir, il est également facile de refactoriser le code.

#### Conception émergente et pré-conception

**Conception émergente (objectif)** : écrire du code fonctionnel sans penser aux principes de conception et nettoyer le code, puis refactoriser le code en supprimant les odeurs de code jusqu'à ce qu'il ne reste plus aucune odeur de code.

**Pré-conception (subjectif)** : penser la conception avant d'écrire le code, cela conduit à du sur-design car on imagine de nombreux cas idéaux dont au moins une partie finiront inévitablement par ne jamais être utiles.

**Conception émergente** vs **pré-conception** est l'une des plus grandes différences entre le TDD et le non-TDD. La conception consiste à faire des choix et prendre des décisions. En soi, ils sont subjectifs et très similaires à des paris sur un avenir incertain. Plus nous avons de charge cognitive, moins nous avons de chances de gagner un pari. En réduisant la taille de chaque itération, nous pouvons réduire la charge cognitive de chaque décision de conception, de sorte que nous pouvons toujours gagner les paris. Nous devrions obtenir la meilleure conception finale puisque nous sommes en mesure d'obtenir un résultat optimal à chaque itération.

Bien sûr, les petits pas seuls ne suffisent pas. Vous devez suivre d'autres principes tels que KISS et YAGNI pour obtenir le meilleur code possible. Cependant, les petits pas sont la base. Il est difficile de suivre d'autres principes si vous ne faites pas des Baby Steps.

Un autre avantage des Baby Steps est que nous pouvons faire l'implémentation juste suffisante. Il est moins probable de faire une implémentation avant d'écrire les tests correspondants car nous nous concentrons sur une petite tache à chaque itération. Ainsi, il est assuré que chaque ligne de code a été dirigée par un test qui matérialise un besoin métier.

#### Faites de petits pas entre les itérations

Chaque itération démarre sur un nouveau test. Le principe est donc de minimiser l'écart entre le test suivant et le test précédent, et d'échouer.

Pour pouvoir profiter des avantages de TDD, avoir une implémentation vraiment pilotée par des tests et faire émerger la meilleure conception, vous ferez des Baby Steps en minimisant toujours la différence entre deux tests consécutifs. Sinon, vous finirez par écrire du code et des tests séparément, ce qui n'est pas l'objectif du TDD.

### Découverte du pair programming

Faire du TDD n'est pas une tache facile. Souvent, une fois les premiers tests passés, on peut commencer à manquer d'inspiration et à avoir du mal à produire de nouveaux tests pertinents. Pour éviter ce phénomène, généralement on couple le TDD avec une autre pratique, le pair programming.

#### Qu'est-ce que la programmation en binôme ?

La programmation en binôme (ou pair programming) est la pratique consistant à s'associer pour travailler sur des tâches de programmation. Habituellement, la plupart des gens imaginent deux développeurs assis sur le même ordinateur, partageant le clavier. Mais avec la popularité croissante des plates-formes de codage à distance , il est désormais possible de jumeler des programmes à des milliers de kilomètres l'un de l'autre.

Les deux membres doivent verbaliser leurs processus de pensée pour que la programmation en binôme soit efficace. Une programmation en binôme réussie repose autant sur une communication réussie que sur des compétences en programmation. La prémisse est que lorsque l'on travaille sur une tâche complexe, "deux têtes valent mieux qu'une"

Pourquoi la programmation en binôme est-elle importante ?

* **Produire de meilleures solutions** : La raison la plus importante d'associer un programme est qu'il produit souvent de meilleures solutions que celles que l'un ou l'autre des développeurs aurait pu produire par lui-même. Les problèmes sont détectés plus tôt et les bugs potentiels sont identifiés par deux personnes au lieu d'une. Avant que la paire ne décide d'une approche à un problème particulier, ils discutent, évaluent et discutent de tous les compromis impliqués. Les solutions sont évaluées à l'avance plutôt qu'après leur mise en œuvre.

* **Partagez les connaissances et le contexte à la volée** : La programmation en binôme fournit un processus de partage des connaissances et du contexte qui est intégré à votre flux de travail quotidien. Pour chaque ligne de code écrite lors de la programmation en binôme, deux personnes ont un contexte sur le code au lieu d'une. Cela fournit une redondance intégrée si une personne part, change d'équipe, est occupée par un autre travail ou part en vacances. Sans programmation en binôme, les développeurs doivent faire des efforts supplémentaires pour partager leurs connaissances, généralement par le biais de réunions supplémentaires et de sessions de révision de code.

* **Apprentissage mutuel et développement des compétences** : L'un des plus grands avantages de la programmation en binôme est d'apprendre de votre partenaire. L'association avec un développeur plus expérimenté est le meilleur moyen pour les développeurs juniors d'améliorer leurs compétences. Les développeurs seniors peuvent également apprendre de nouvelles choses en s'associant à un développeur plus junior, que ce soit une commande Linux astucieuse qu'ils ne connaissaient pas, comment utiliser un nouvel IDE ou comment être productif dans le dernier framework frontal. Tout le monde est un expert dans quelque chose, et tout le monde a quelque chose à enseigner.

#### Comment fonctionne la programmation en binôme ?

Les exigences pour la programmation en binôme sont minimales : deux développeurs et une ligne de commande ou un éditeur de code partagé. Avec ces ingrédients de base en place, il existe de nombreuses façons de jumeler le programme, du "Ping Pong Pattern" à des formes beaucoup moins structurées. Nous allons plonger dans différentes techniques de programmation en binôme dans les sections ci-dessous, mais elles ont toutes deux points essentiels en commun : le tour de rôle et la communication ouverte.

#### Quelles sont les principales techniques de programmation en binôme ?

* **Ping pong** : Cette forme de programmation en binôme est réalisée en conjonction avec le développement piloté par les tests. Une personne écrit un test et l'autre fait passer le test. Ce modèle est efficace parce que le tour de rôle est intégré au processus. Assurez-vous que chaque membre alterne entre l'écriture des tests et la réussite des tests. Cela peut devenir un anti-modèle Ping Pong si la même personne écrit toujours les tests (souvent le développeur le plus junior ou le moins confiant) et la même personne les fait toujours passer (souvent le développeur le plus expérimenté ou le plus confiant).

* **Pilote-Navigateur** : Cette forme de programmation en binôme est une forme plus lâche du modèle de ping-pong. Cela fonctionne un peu comme deux personnes conduisant dans une course de voitures de rallye, une personne conduisant (ou tapant) et l'autre naviguant. Le conducteur exécute les instructions du navigateur, mais a la possibilité d'apporter des corrections ou de demander des éclaircissements. Ce style est un antidote efficace pour l'anti-modèle où la personne qui tape contrôle souvent ce qui est tapé, plaçant l'autre personne dans un mode passif où elle regarde simplement ce qui se passe. Le conducteur et le navigateur changent régulièrement de rôle toutes les 15 minutes environ.

* **Appariement non structuré** : C'est le genre d'appariement qui se produit généralement lorsqu'aucune approche particulière n'est suivie. Il est fluide, avec un virage entre le conducteur et le navigateur qui se produit au fur et à mesure que cela a du sens. Cette liberté de structure peut aider des paires naturellement bien assorties à se déplacer encore plus rapidement. Cependant, les paires qui ont des styles différents peuvent avoir du mal avec le manque de structure impliqué ici.

#### Qu'est-ce qui fait un bon partenaire de programmation en binôme ?

La programmation en binôme est plus efficace lorsque les deux personnes apportent quelque chose d'unique à la table, qu'il s'agisse de connaissances, d'expérience ou d'une perspective diversifiée. Si vous avez la possibilité de choisir votre partenaire de programmation en binôme, il est préférable de rechercher quelqu'un qui peut combler une lacune dans vos connaissances ou vous offrir une perspective différente.

#### Comment programmer efficacement en binome ?

* **Continuer de parler** : La programmation en binôme ne doit jamais se faire en silence. Lorsqu'une paire est silencieuse, cela peut signifier qu'elle est si parfaitement synchronisée que rien n'a besoin d'être dit (c'est rare). Plus souvent, cela signifie qu'ils ne partagent pas leurs processus de pensée. Que vous soyez assis avec votre partenaire ou que vous communiquiez à distance , une bonne programmation en binôme implique beaucoup de discussions et de réflexions à haute voix. Une bonne astuce consiste à toujours raconter ce que vous faites et ce que vous pensez chaque fois que vous tapez.

* **Passer autant de temps à taper** : Lorsqu'une personne tape pendant une période prolongée, généralement plus d'une demi-heure, cela peut être le symptôme d'une mauvaise programmation en binôme. Si les rôles de conducteur et de navigateur sont correctement partagés, les deux membres taperont à tour de rôle. Si une personne a tendance à dominer le clavier, il peut être utile de régler une alarme toutes les 20 minutes pour encourager l'échange de rôles. En binôme avec une personne plus senior , la personne experte doit faire particulièrement attention à ne pas saisir le clavier lorsque la personne junior se débat ou va lentement.

* **Utiliser un environnement de développement avec lequel les deux personnes sont également à l'aise** : Ne soyez pas la personne qui insiste pour que votre partenaire de programmation en binôme utilise votre Vim ou Emacs hyper-personnalisé avec un millier de plugins à moins qu'il ne soit aussi à l'aise avec Vim ou Emacs que vous. En insistant sur un environnement qui n'est pas familier à votre partenaire, vous doublez la charge cognitive qu'il doit supporter. Si vous êtes beaucoup plus productif dans l'environnement de développement que votre partenaire, ou vice versa, l'équilibre de la programmation en binôme sera perturbé et votre partenaire sera moins enclin à « piloter ». Utilisez un IDE avec lequel vous êtes à peu près à l'aise et utilisez votre environnement hautement personnalisé autant que vous le souhaitez lorsque vous travaillez seul.

### Exercice 1 : Années bissextiles

Premier kata pour pratiquer le TDD et le pair programming en mode ping-pong. Relativement simple, il vous permettra de commencer à écrire des tests simplement.

#### Description du problème

Avant 1582, le calendrier julien était largement utilisé et définissait les années bissextiles comme chaque année divisible par 4. Cependant, il a été constaté à la fin du XVIe siècle que l'année civile s'était éloignée de l'année solaire d'environ 10 jours. Le calendrier grégorien a été défini afin de réduire le nombre d'années bissextiles et d'aligner plus étroitement l'année civile sur l'année solaire. Il a été adopté dans les pays pontificaux le 15 octobre 1582, sautant 10 jours à partir de la date du calendrier julien. Les pays protestants ont adopté le calendrier grégorien après un certain temps.

Le calendrier grégorien est assez précis, mais pourrait être rendu plus précis en ajoutant une règle supplémentaire qui élimine les années divisibles par 4000 comme années bissextiles. Mais je suppose que nous traverserons ce pont quand nous y arriverons. Vous pouvez envisager d'ajouter cette règle en tant que deuxième histoire utilisateur pour continuer l'exercice.

#### Histoire utilisateur

En tant qu'utilisateur, je souhaite savoir si une année est une année bissextile, afin de pouvoir prévoir une journée supplémentaire le 29 février au cours de ces années.

#### Critères d'acceptation

* Toutes les années divisibles par 400 **SONT** des années bissextiles (ainsi, par exemple, 2000 était bien une année bissextile),
* Toutes les années divisibles par 100 mais pas par 400 **ne sont PAS** des années bissextiles (ainsi, par exemple, 1700, 1800 et 1900 n'étaient PAS des années bissextiles, **NI** 2100 ne sera pas une année bissextile),
* Toutes les années divisibles par 4 mais pas par 100 **SONT** des années bissextiles (par exemple, 2008, 2012, 2016),
* Toutes les années non divisibles par 4 **ne sont PAS** des années bissextiles (par exemple 2018, 2019, 2021 et 2022).

#### Consignes

Commencez par choisir votre binôme. Asseyez-vous à coté de votre co-équipier et commencez à discuter du premier test. Après vous être mis d'accord, commencez à résoudre l'exercice, cas de test après cas de test en mode ping-pong.

Ne pas oublier de créer une branche de fonctionnalité appelée `exercice1` avant de commencer. Pour la créer, vous devez exécuter les commandes suivantes :

```sh
~/.../atelier-kata-VotreUsername (main)$ git branch exercice1
~/.../atelier-kata-VotreUsername (main)$ git checkout exercice1
~/.../atelier-kata-VotreUsername (exercice1)$ 
```

Une fois l'exercice terminé, poussez vos modifications sur votre fork. Créez votre PR et fusionnez là dès qu'elle est parfaite. Une fois la fusion effectuée, n'oubliez pas de vous replacer sur la branche `main` et de tirer votre dépôt distant.

### Exercice 2 : Comptage de point au Tennis

Ce Kata consiste à implémenter un système de comptage des point lors d'un jeu au tennis. Le système de notation est assez simple :

* Chaque joueur peut avoir l'un ou l'autre de ces points dans un jeu "0" "15" "30" "40"

* Si un joueur a un score de 40 et qu'il gagne le point, alors ce joueur remporte le jeu, cependant il y a des règles
  spéciales.

* Si les deux ont 40, les joueurs sont à "Égalité".

* Si le jeu est à "Égalité", le gagnant d'un point aura l'avantage.

* Si le joueur avec l'avantage remporte la balle, il gagne le jeu.

* Si le joueur sans avantage gagne, il y a un retour à "Égalité".

Description alternative des règles par Wikipedia (<https://fr.wikipedia.org/wiki/Tennis#R%C3%A8gles>):

* Une partie est gagnée par le premier joueur à avoir remporté au moins quatre points au total et au moins deux points
  de plus que son adversaire.

* Le score courant de chaque jeu est décrit d'une manière propre au tennis : les scores de zéro à trois points sont
  respectivement décrits comme « 0 », « 15 », « 30 » et « 40 ».

* Si au moins trois points ont été marqués par chaque joueur et que les scores sont égaux, le score est "Égalité".

* Si au moins trois points ont été marqués par chaque camp et qu'un joueur a un point de plus que son adversaire, le
  score du jeu est "avantage" pour le joueur en tête.

#### Histoires utilisateurs

En tant que joueur de Tennis, je souhaite disposer d'un système de comptage des points me permettant de determiner si un joueur à gagner un jeu.

#### Critères d'acceptation

Le système de comptage des points doit respecter [les règles officielles de l'International Tennis Federation](https://web.archive.org/web/20100331051519/http://www.itftennis.com/shared/medialibrary/pdf/original/IO_46376_original.PDF)
.

#### Consignes

Pour ce kata, comme le précédent, il faut essayer de trouver les exemples pertinents pour tester tous les cas permis par la règles. Cette fois-ci votre binôme fonctionnera en mode pilote-navigateur.

Une fois l'exercice terminé, n'oubliez pas de pousser les modifications de la branche `exercice2` sur votre fork. Créez votre PR et fusionnez là dès qu'elle est parfaite. Une fois la fusion effectuée, n'oubliez pas de vous replacer sur la branche `main` et de tirer votre dépôt distant.

### Exercice 3 : Système de gestion des employés

Ce second exercice, est un peu plus complexe que le premier. Il va vous faire découvrir pourquoi la sur-spécification peut nuire à la maintenabilité des tests.

#### Description du problème

Vous construisez un système de gestion des employés d'une épicerie locale. Le propriétaire du magasin souhaite ouvrir le magasin le dimanche et, en raison de restrictions légales, les employés de moins de 18 ans ne sont pas autorisés à travailler le dimanche.

La personne s'occupant de la RH, vous demande une fonction de rapport afin qu'elle puisse planifier le travail de tous les employés. Tous les employés sont déjà stockés quelque part et ont les propriétés suivantes :

- `name` : `string` (le nom de l'employé)
- `age` : `nombre` (l'âge en années de l'employé)

```js
const employees = [
    {name: 'Max', age: 17},
    {name: 'Sepp', age: 18},
    {name: 'Nina', age: 15},
    {name: 'Mike', age: 51},
];
```

#### Histoires utilisateurs

* En tant que propriétaire de magasin, je souhaite voir une liste de tous les employés âgés de plus de 18 ans, afin de savoir qui est autorisé à travailler le dimanche.
* En tant que propriétaire de magasin, je souhaite que la liste des employés soit triée par leur nom, afin de pouvoir trouver des employés plus facilement.
* En tant que propriétaire de magasin, je veux que la liste des employés soit en majuscules, afin que je puisse mieux la lire.
* En tant que propriétaire de magasin, je veux que les employés soient triés par leurs noms descendants au lieu d'ascendants.

#### Consignes

Toujours en binôme, commencez par la première user-story et rédigez au moins un test pour chaque exigence. Bien évidement, si vous en rédigez plusieurs pour faire des petits pas ce n'est que mieux. Essayez de ne pas regarder les exigences futures à l'avance et suivez strictement le cycle TDD.

Une fois l'exercice terminé, n'oubliez pas de pousser les modifications de la branche `exercice3` sur votre fork. Créez votre PR, faite la relire et fusionnez là dès qu'elle est parfaite. Une fois la fusion effectuée, n'oubliez pas de vous replacer sur la branche `main` et de tirer votre dépôt distant.

### Exercice 4 : Pagination Seven

#### Description du problème

La pagination peut être trouvée dans de nombreux sites. La plupart du temps, vous pouvez voir la page en cours et passer à la page précédente et à la page suivante. Parfois, vous pouvez aller à la première et à la dernière page. Certaines informations telles que le nombre total de pages peuvent être aussi affichées.

Conscients de la nécessité de toutes ces contraintes, il existe de nombreux exemples de pagination comme par exemple:

* Pagination simplifiée :

```
< 42 >
```

* Pagination avancée :

```
<< < Page 42 of 100 > >>
```

La pagination avancée est vraiment verbeuse. Il faut pourtant une solution de pagination qui permette de se déplacer à la première page, la dernière page, la page suivante, la page précédente et le numéro de la page actuelle. Le système "Pagination Seven" permet de représenter toutes ces informations en même temps avec moins de complexité:

```
1 … 41 (42) 43 … 100
```

#### Critères d'acceptation

1. Il faut représenter toutes les pages jusqu'à 7, le but est d'afficher la page courante entre (et ), à titre d'exemples :
    * Page 2 sur 5 :

    ```
    1 (2) 3 4 5
    ```

    * Page 6 sur 7 :

    ```
    1 2 3 4 5 (6) 7
    ```

2. Nous devons voir la première, la dernière, la page précédente et la page suivante, mais en utilisant uniquement 7 emplacements lorsque le nombre total de pages est supérieur à 7. Nous devons donc remplacer le groupe de pages par …, voici quelques exemples :

    * Page 42 sur 100 :

    ```
    1 … 41 (42) 43 … 100
    ```

    * Page 5 sur 9 :

    ```
    1 … 4 (5) 6 … 9
    ```


3. Parfois on n'a pas besoin de montrer `…` parce qu'on est dans la première partie de la pagination, on aura donc :

    * Page 2 sur 9 :

    ```
    1 (2) 3 4 5 … 9
    ```

    * Page 4 sur 9 :

    ```
    1 2 3 (4) 5 … 9
    ```


4. même idée que le critère d'acceptation précédent mais pour la dernière partie de la pagination :

    * Page 8 sur 9 :

    ```
    1 … 5 6 7 (8) 9
    ```

    * Page 6 sur 9 :
    
    ```
    1 … 5 (6) 7 8 9
    ```

#### Histoire utilisateur

En tant qu'utilisateur d'un moteur de recherche, je souhaite que mes résultats de recherche puissent être paginés avec le système "Pagination Seven" pour facilement naviguer entre les différentes pages de ma recherche sans me perdre.

#### Consignes

Toujours en binôme, commencez par la première user-story et rédigez au moins un test pour chaque exigence. Bien évidement, si vous en rédigez plusieurs pour faire des petits pas ce n'est que mieux.

Une fois l'exercice terminé, n'oubliez pas de pousser les modifications de la branche `exercice4` sur votre fork. Créez votre PR et fusionnez là dès qu'elle est parfaite. Une fois la fusion effectuée, n'oubliez pas de vous replacer sur la branche `main` et de tirer votre dépôt distant.

### Exercice 5 : Yahtzee

Le jeu de Yahtzee (ou Yatzy) est un jeu de dés relativement simple de hasard raisonné. Le but est d'enchaîner les combinaisons à l'aide de cinq dés pour remporter un maximum de points.

#### Description du problème

Chaque joueur lance cinq dés à six faces. Ils peuvent relancer tout ou partie des dés. Ils peuvent faire jusqu'à trois lancés (jet initial compris).

Le joueur place ensuite le lancer dans une catégorie, telle que un, deux, cinq, paire, deux paires, etc. (voir les règles ci-dessous). Si le jet est compatible avec la catégorie, le joueur obtient un score pour le jet selon les règles. Si le jet n'est pas compatible avec la catégorie, le joueur marque zéro pour le jet.

Par exemple, supposons qu'un joueur marque 5, 6, 5, 5, 2 dans la catégorie des cinq, il marquerait 15 (trois cinq). Le score de ce coup est ensuite ajouté à son total et la catégorie ne peut plus être utilisée dans les coups restants pour ce match. Un jeu complet consiste en une partie pour chaque catégorie. Ainsi, pour son dernier passage dans une partie, un joueur peut choisir uniquement la seule catégorie restante même si elle ne lui fait marquer aucun point.

Votre tâche est de marquer un lancer DONNÉ dans une catégorie DONNÉE. Vous n'avez PAS besoin de programmer le lancement aléatoire des dés. Le jeu n'est PAS joué en laissant l'ordinateur choisir la catégorie de score la plus élevée pour un jet donné.

#### Catégories et règles de notation

* **Chance:** : Le joueur marque la somme de tous les dés, peu importe ce qu'il lit.

  Par example:

  * Le lancé `1, 1, 3, 3, 6` placé sur la catégorie "chance" donne 14 points (1+1+3+3+6)

  * `4, 5, 5, 6, 1` placé sur "chance" donne 21 points (4+5+5+6+1)

* **Yahtzee** : Si tous les dés ont le même nombre, le joueur marque 50 points.
  Par example:

  * `1, 1, 1, 1, 1` placé sur « Yahtzee » rapporte 50 points.

  * `1, 1, 1, 2, 1` placé sur « Yahtzee » rapporte 0 point.

* **Un, Deux, Trois, Quatre, Cinq, Six** : Le joueur marque la somme des dés qui indique respectivement un, deux, trois, quatre, cinq ou six.

  Par example:

  * `1, 1, 2, 4, 4` placé sur « quatre » donne un score de 8 points (4+4).
  * `2, 3, 2, 5, 1` placé sur « deux » donne un score de 4 points (2+2).
  * `3, 3, 3, 4, 5` placé sur « un » donne un score de 0 point.
* **Paire** : Le joueur marque la somme des deux dés correspondants les plus élevés.

  Par exemple, lorsqu'il est placé sur "paire":

  * `1, 2, 3, 4, 5` donne 0 point
  * `3, 3, 3, 4, 4` donne 8 points (4+4)
  * `1, 1, 6, 2, 6` donne 12 points (6+6)
  * `3, 3, 3, 4, 1` donne 6 points (3+3)
  * `3, 3, 3, 3, 1` donne 6 points (3+3)
* **Deux paires** : S'il y a deux paires de dés avec le même nombre, le joueur marque la somme de ces dés.

  Par exemple, lorsqu'il est placé sur "deux paires":

  * `1, 1, 2, 3, 3` donne 8 points (1+1+3+3)
  * `1, 1, 2, 3, 4` donne 0 point
  * `1, 1, 2, 2, 2` donne 6 points (1+1+2+2)
  * `3, 3, 3, 3, 1` donne 0 point

* **Un brelan** : S'il y a trois dés avec le même numéro, le joueur marque la somme de ces dés.

  Par exemple, lorsqu'il est placé sur "brelan":

  * `3, 3, 3, 4, 5` donne 9 points (3+3+3)
  * `3, 3, 4, 5, 6` donne 0 point
  * `3, 3, 3, 3, 1` donne 9 points (3+3+3)

* **Carré** : S'il y a quatre dés avec le même numéro, le joueur marque la somme de ces dés.

  Par exemple, lorsqu'il est placé sur "un carré":

  * `2, 2, 2, 2, 5` donne 8 points (2+2+2+2)
  * `2, 2, 2, 5, 5` donne 0 point
  * `2, 2, 2, 2, 2` donne 8 points (2+2+2+2)

* **Petite suite** : Lorsqu'il est placé sur "petite suite", si les dés indiquent `1, 2, 3, 4, 5`, le joueur marque 15 points (la somme de tous les dés).

* **Grande Suite** : Lorsqu'il est placé sur "grande suite", si les dés indiquent `2, 3, 4, 5, 6`, le joueur marque 20 (la somme de tous les dés).

* **Full** : Si les dés sont deux d'une valeur identique et les trois autre d'une autre valeur également identique, le joueur marque la somme de tous les dés.

  Par exemple, lorsqu'il est placé sur "full house":

  * `1, 1, 2, 2, 2` donne 8 points (1+1+2+2+2)
  * `2, 2, 3, 3, 4` donne 0 point
  * `4, 4, 4, 4, 4` donne 0 point

#### Histoires utilisateurs

En tant que joueur de Yahtzee, je veux disposer d'une fonction qui me calculera le score de mon lancé dans une catégorie que je choisi.

#### Critères d'acceptation

Le système de comptage des points doit respecter les règles énumérées ci-dessus.

#### Consignes

Le kata consiste à créer une fonction pour marquer un jet dans n'importe laquelle catégorie prédéfinie. Étant donné un jet et une catégorie, la solution finale devrait produire le score de ce jet placé dans cette catégorie.

Une fois l'exercice terminé, n'oubliez pas de pousser les modifications de la branche `exercice5` sur votre fork. Créez votre PR, faite la relire et fusionnez là dès qu'elle est parfaite. Une fois la fusion effectuée, n'oubliez pas de vous replacer sur la branche `main` et de tirer votre dépôt distant.
