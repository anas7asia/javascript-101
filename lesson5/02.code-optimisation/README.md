# Optimisation du code

Utiliser les fonction si le code est réutilisé plusieurs fois - les fonction peuvent être mis en cache.

Accessing the HTML DOM is very slow, compared to other JavaScript statements.
If you expect to access a DOM element several times, access it once, and use it as a local variable.
Essayez d’écrire le stricte minimum de HTML pour que le navigateur passe moins de temps à chercher les élément dedans.

Eviter de loop plusieurs fois dans la même tableau -> optimiser le nombre des boucles.

Minimiser le nombre de variables globales.

## Optimiser le code avant le mettre sur le serveur

Préparer le code JavaScript pour la stade de production
+ Grouper les fichiers
+ Transpiler pour rendre votre code accessible aux navigateur qui ne supportent pas ES6
+ Minifier les fichiers : cela permet de réduire la taille de fichier [par 20-40%](https://www.gribble.org/techreports/minification/)

<!-- # Optimisation de code

+ [w3schools > JavaScript Performance](https://www.w3schools.com/js/js_performance.asp)
+ []()
+ []()

Multiple requests means more latency
Chaque requête HTTP ajoute en moyenne ~700-800 octets et 100ms de latency. Donc le but ultime est de faire le moins de requêtes que possible.


Il y a plusieurs task runners et bundlers, vous pouvez utiliser celui qui vous plaît le plus:
- Webpack
- Gulp
- Grunt
- Browserify
- Rollup -->





