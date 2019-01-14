# JavaScript

JavaScript est un langage de [haut niveau de programmation](https://fr.wikipedia.org/wiki/Langage_de_haut_niveau), [faiblement typé](https://fr.wikipedia.org/wiki/Typage_fort), [interpreté](https://fr.wikipedia.org/wiki/Interpr%C3%A8te_(informatique)), orienté objet à prototype.

> JavaScript est un langage de programmation le [plus utilisé](https://insights.stackoverflow.com/survey/2017#technology) dans le monde entier.

## JavaScript dans le Web

HTML (HyperText Markup Language) est un langage qui définit la structure des pages web et leurs contenu.

CSS (Cascading Style Sheets) est un langage qui donne des styles aux éléments HTML.

JavaScript est un langage de *programmation* qui permet de rendre les pages web interactives: transformer le contenu de la page à la volée, écouter les événements déclenchés par l'utilisateur et plein d'autres choses !

## Pourquoi JavaScript?

Aujourd'hui c'est le seul langage qui a les qualités suivantes:
1. Intégration complète avec HTML et CSS.
2. Simplicité.
3. Supporté par defaut par tous les navigateurs modernes.

## Histoire de JavaScript

![Netscape](https://upload.wikimedia.org/wikipedia/en/thumb/c/c9/Navigator_1-22.png/300px-Navigator_1-22.png)

*Netscape Navigator 1.22 - [Wikipedia](https://en.wikipedia.org/wiki/Netscape_Navigator)*


Fondée en 1994 l'entreprise *Netscape Communications* avec son navigateur *Netscape Navigator* a conquis trois quarts du marché mondial. Afin d'aller plus loin celle-ci décide de créer un nouveau langage pour ajouter de l'interactivité aux pages web. Ce langage devait ressembler à Java car celui-ci était très à la mode à ce moment là.

Brandon Eich fut recruté pour dévélopper un prototype pour ce nouveau langage qu'il termina en seulement dix jours.

> **Mocha** (nom du prototype) -->
> **LiveScript** (nom de la première version officiele) -->
> **JavaScript** (implementation dans Netscape Navigator en septembre 1995)

L'idée plu à Microsoft et une version de JavaScript - *JScript* - était né et intégré dans Internet Explorer 3.0 en août 1996. Pour éviter la confusion avec les [API](https://developer.mozilla.org/fr/docs/Glossaire/API)s des deux versions, Netscape envoya sa version à [ECMA](https://fr.wikipedia.org/wiki/Ecma_International) (European Computer Manufacturers Association) afin de créer un seul standart du langage.

Ce standart fut implementé sous le nom de **ECMAScript** (nom court - ES). Depuis, le groupe [T39](https://tc39.github.io/ecma262/) au sein d'ECMA continue à mettre à jour le standart du langage. A partir de l'année 2015 une nouvelle version d'ES sort annuellement.

> ECMAScript est le nom officiel du langage. JavaScript est une marque déposée appartenant à l'entreprise américaine Oracle

Version | Année | Déscription
--- | --- | ---
1	| ECMAScript 1 (1997) |	Première édition
2	| ECMAScript 2 (1998) | Changements mineurs
3 | ECMAScript 3 (1999) | Ajout d'expressions regulières
4 | ECMAScript 4 | Jamais sortie
5 | ECMAScript 5 (2009) | Version majeure. Actuellement supportée par tous les navigateurs *modernes*
6 | ECMAScript 2015 | Version majeure avec plusieurs ameliorations. Supportée par les navigateurs sortis depuis 2016/2017.  
7 | ECMAScript 2016 | Mise à jour
8 | ECMAScript 2017 | Mise à jour
9 | ECMAScript 2018 | Mise à jour

Même si ES6 n'est pas supporté dans 100% de navigateurs, il est fortement conseillé de l'utiliser. Il y a des outils spéciaux pour le *transpiler* (transformer) en ES5. Comme il est possible de profiter de toutes les nouvelles fonctionnalités et le code marche sur tous les navigateurs modernes.

<!-- <a href="http://www.youtube.com/watch?feature=player_embedded&v=EUAmiIsp2YU" target="_blank"><img src="http://img.youtube.com/vi/EUAmiIsp2YU/0.jpg" alt="JavaScript History" width="400" height="auto" border="3" /></a> -->

[![JavaScript History](https://img.youtube.com/vi/EUAmiIsp2YU/0.jpg)](https://www.youtube.com/watch?v=EUAmiIsp2YU)

## JavaScript dans le navigateur (client)

Aujourd'hui JavaScript est capable, par exemple, de :
+ Garder et gérer les données côté client
+ Transformer les données grâce à ses différentes APIs intégrées
+ Ajouter/modifier/supprimer des éléments HTML
+ Ecouter les événements déclenché par l'utilisateur (clique, appui de touche de clavier, etc.)
+ Faire des appels aux serveurs distants

Mais JavaScript n'est pas capable (heureusement!) de :
+ Accéder au système d'exploitation de l'ordinateur
+ Accéder aux autres onglets du navigateur
+ Créer/supprimer des fichiers sur l'ordinateur

Pour faciliter et accélérer le temps de développement, les développeurs JavaScript ont créé des miliers de librairies (collections de méthodes) et de frameworks (ils definissent le design global du code de l'application).

Les librairies les plus connues:
+ jQuery (manipulation du DOM)
+ lodash (les méthodes utiles qui n'existent pas dans JavaScript)
+ D3.js (représentation de données)
+ ...

Les frameworks les plus connus:
+ Angular
+ React
+ VueJS
+ ...

![JS Frameworks](http://www.commitstrip.com/wp-content/uploads/2015/09/Strip-Prendre-le-train-en-marche-650-final1.jpg)


## JavaScript ailleurs

> "Learn once, write anywhere" -
> Tom Occhino, ingénieur logiciel chez Facebook

### Côté serveur

![Server-side JS](http://www.commitstrip.com/wp-content/uploads/2016/05/Strip-Le-fullstack-JS-2-650-final.jpg)

En 2009 Ryan Dahl créa *Node.js* – environnement bas niveau permettant l’exécution de JavaScript côté serveur qui tourne sur la machine virtuelle V8.

Le principal avantage de Node.js est son modèle événementiel (event-driven), non-blockant E/S.
Cela dit, Node.js est un excellent logiciel pour gérer des applications temps réel gourmandes en données avec de nombreuses requêtes simultanées.

Node.js est utilisé par Netflix, PayPal, LinkedIn, IBM, Microsoft, Groupon, Walmart, Yahoo!, etc.


### CLI (Command Line Interface)

Grâce à Node.js il est possible d'exécuter les tâches en ligne de commande.

+ Télécharger et gérer les libraries avec *npm* ou *yarn*
+ Minifier et combiner des fichiers
+ Transformer ES6 en ES5
+ Compiler SASS en CSS
+ Recharger automatiqument la page après chaque changement dans le code

![npm](https://www.commitstrip.com/wp-content/uploads/2017/12/Strip-Installation-NPM-650-finalv2.jpg)

### GUI sur desktop

Le plus grand avantage de l'écriture d'applications de bureau avec JavaScript est l'abstraction de la plate-forme.
En plus, il y a beaucoup de code partagé entre l'application web et l'application de bureau.

Les applications créés avec du JS: VSCode, Slack, Facebook Desktop Messenger, WhatsApp, etc.

### Applications mobiles

Il y a plusieurs frameworks JavaScript (ReactNative, Ionic, NativeScript, etc) qui permettent de créer les applications mobiles. Ecrite une fois, une application fonctionne sur iOS et Android. Cela évite de créer deux applications natives en Swift et Java/Kotlin.

Applications JS: SudOuest, FacebooksAds, Airbnb, Bloomberg


## Reading List

+ [A Brief History of JavaScript](https://auth0.com/blog/a-brief-history-of-javascript/)
+ [What is JavaScript?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)