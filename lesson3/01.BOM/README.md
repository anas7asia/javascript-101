# Browser Object Model

+ [w3school > BOM](https://www.w3schools.com/js/js_window.asp)
+ [MDN > Window object](https://developer.mozilla.org/en-US/docs/Web/API/Window)

Dans la console loggez l'objet global `window` et regardez quelles propriétés il possède.
Regardez plus précisement les propriétés `location`, `navigator`, `screen`.

## navigator

Affichez sur la page:
+ nom de votre navigateur
+ langue principal de votre navigateur
+ platforme de votre ordinateur
+ si vous avez activé les cookies dans votre navigateur 

## screen

Affichez sur la page:
+ largeur de l'écran de votre ordinateur
+ hauteur de l'écran de votre ordinateur
+ orientation de votre écran

## window

Affichez sur la page:
+ largeur de la fenêtre d'affichage de votre navigateur
+ hauteur de la fenêtre d'affichage de votre navigateur
+ largeur de votre navigateur
+ hauteur de votre navigateur
<!-- + décalage du haut de la page  -->

## location

Affichez sur la page:
+ url complet de la page
+ nom d'hôte (sans http:// ou https:// ou file://)
+ le nom du protocole utilisé (http: ou https: ou file:)
<!-- + l'adresse (racine) de la page -->
<!-- + les [query params](https://en.wikipedia.org/wiki/Query_string) s'ils sont présents, sinon affichez 'No query params' -->

<!-- ---

Créez une fonction qui trouve le nom du sous-domaine d'un site (ou retourne null s'il n'y a pas). Pour faciliter la tâche prenez directement le nom d'hôte et découpez cette chaîne de caractères. -->

<!-- ---

Créez une fonction qui génère un nombre aléatoire entre 0 et 10.
Si le nombre est inférieur ou égal à 5, rafraîchissez complètement la page, sinon utilisez la méthode alert de l'objet `window`. -->

<!-- ## history

Créez une fonction pour pouvoir revenir à la page précédente.

---

Créez une fonction pour pouvoir revenir à la page suivante. -->


## Reading List

+ [How does Window object really works?](https://develoger.com/how-does-window-object-really-works-216ee99c356f)
+ [DOM & BOM Revisited](https://medium.com/@fknussel/dom-bom-revisited-cf6124e2a816)