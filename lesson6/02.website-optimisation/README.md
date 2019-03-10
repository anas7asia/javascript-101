# Optimisation du code, des images et des vidéos pour le Web

## Code

Il n'y a pas besoin de gerer la memoire avec JavaScript. [Garbage collector](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management) s'occupe de libérer la mémoire, par contre, les fuites de mémoire peuvent avoir place.

Evitez les fuites de mémoire avec les bonnes pratiques suivantes:
+ Ne déclarer trop de variables lourdes globales. Les variables globales sont jamais détruites, donc la mémoire qui leur est donnée, n'est jamais libérée.
+ Utiliser les fonctions si le code est réutilisé plusieurs fois - les fonctions peuvent être mis en cache.
+ Ne créez pad de boucles infinies, votre navigateur va crasher.
+ N'appliquez pas trop d'animations aux éléments du DOM, elle ralentissent le site.
+ N'utilisez pas trop de librairies tières, souvent elle font beaucoup plus de choses que vous avez besoin, donc la consommation de CPU augmente pour rien.
+ Evitez de parcourir plusieurs fois le même tableau.

Si vous n'avez plus besoin d'un écouteur d'événement, **détachez-le**. Les écouteurs d'événements consomment beaucoup de mémoire, si vous ne les detachez pas, leur nombre va incrémenter et ralentir votre site. 

Manupulation du DOM est assez lente par rapport aux autres opérations JavaScript. Si vous envisagez d'accéder un élément du DOM plusieurs fois, accédez-le une fois et sauvegardez-le dans une variable locale.

**ATTENTION**: ce code est très mauvais 
![Very very bad code](https://i.ibb.co/xhWzg21/Bad-code-if-DOM.png)

## Images

Les images constituent la partie la plus grande du poids d'un site. C'est pour ça il est très important d'optimiser leurs poids, diminuer le nombre de requêtes, bien choisir leur format.

Avant mettre votre site en ligne, n'oubliez pas de :
+ réduire le poids des images
+ bien choisir leurs formats, utiliser les formats modernes
+ choisir la taille d’image appropriée avec la balise HTML `<picture>` côté client ou utiliser un hébérgeur des images avec une option de redimensionnement à la volée: [Cloudinary](https://cloudinary.com/), [Dynamic Media](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/solutions.html), [Cloudimage](https://www.cloudimage.io/en/home), [Sirv](https://sirv.com/features/image-resize-api/), [Amazon S3](https://aws.amazon.com/s3/), etc
+ lazy load (“chargement fainéant”) des images qui se trouvent hors de la partie visible du site

Voici la [checklist Google](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization) de l’optimisations des images.

![Big images](https://i.ibb.co/6n5Rtqg/website-size.jpg)

### Nombre de requêtes et poids d'image

Vous poouvez réduire le nombre de requêtes en regroupant les petites images/icones en une seule grande qui s’appelle [“image sprite”](https://www.w3schools.com/css/css_image_sprites.asp).

C’est possible de créer un sprite automatiquement grace aux task managers, par exemple, avec [ce plugin](https://github.com/mixtur/webpack-spritesmith) de Webpack.

### Lazy load

Toutes les images de la page commencent à charger de suite après son overture, mais ce n'est pas impossible que l’utilisateur ne va jamais descendre en bas de la page en la quittant de suite, donc ces images vont être chargées pour rien.
Le principe de "lazy load" est de retarder le chargement des images qui se trouvent plus bas que la partie visible de la page et de commencer à les charger seulement si l’utilisiteur descend jusque leur position. Voir la [démonstration](https://davidwalsh.name/demo/lazyload-2.0.php).

Plusieurs plugins ont été créé pour nous faciliter la tache:
+ [jQuery Lazyload](https://github.com/tuupola/jquery_lazyload)
+ [Unveil.js](http://luis-almeida.github.io/unveil/)
+ [jQuery.Lazy](http://jquery.eisbehr.de/lazy/)
+ etc

## Vidéos

Comment bien utiliser les vidéos :

+ Bien choisir leurs formats, toujours priviliger les vidéos aux gifs.
+ Optimiser leures tailles et leurs poids, supprimer les pistes audio si le son n’est pas utilisé.
+ Redimensionner les videos à la volée pour les viewports différents avec Cloudinary .
+ Ne pas commencer à télécharger la vidéo tant que l’utilisateur n’a pas cliqué sur ‘Play’.

Guide complet Google d’utilisations des videos sur le web : <https://developers.google.com/web/fundamentals/media/video>


## Optimiser le code JavaScript avant le mettre sur le serveur

Préparer le code JavaScript pour le mettre en ligne :
+ Grouper les fichiers
+ Transpiler pour rendre votre code accessible aux navigateur qui ne supportent pas ES6
+ Minifier les fichiers : cela permet de réduire la taille de fichier [par 20-40%](https://www.gribble.org/techreports/minification/)