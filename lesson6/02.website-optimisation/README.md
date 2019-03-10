# Optimisation des images et des vidéos pour le Web

## Images

Les images constituent la partie la plus importante du poids d'un site. C'est pour ça c'est très important d'optimiser leurs poids, diminuer le nombre de requêtes, bien choisir leur format.

+ réduire le poids des images
+ bien choisir leurs formats, utiliser les formats modernes
+ choisir la taille d’image appropriée avec la balise HTML `<picture>` côté client ou utiliser un hosting des images avec une option de redimensionnement à la volée: [Cloudinary](https://cloudinary.com/), [Dynamic Media](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/solutions.html), [Cloudimage](https://www.cloudimage.io/en/home), [Sirv](https://sirv.com/features/image-resize-api/), [Amazon S3](https://aws.amazon.com/s3/), etc
+ lazy load (“chargement fainéant”) des images qui se trouvent hors de la partie visible du site

Voici la [checklist Google](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization) de l’optimisations des images

### Nombre de requêtes et poids d'image

On peut réduire le nombre de requêtes en regroupant les petites images/icones en une seule grande qui s’appelle [“image sprite”](https://www.w3schools.com/css/css_image_sprites.asp).

C’est possible de créer un sprite automatiquement grace aux task managers, par exemple, avec [ce plugin](https://github.com/mixtur/webpack-spritesmith) de Webpack.

### Lazy load

Toutes les images de la page commencent à charger de suite après son overture. Ça se trouve que l’utilisateur ne va jamais descendre en bas de la page, et ces images vont être chargées pour rien.
Le principe de lazy load est retarder le chargement des images qui se trouvent plus bas que la partie visible de la page et commencer à les charger seulement si l’utilisiteur descend jusque leur position. Voir la [démonstration](https://davidwalsh.name/demo/lazyload-2.0.php).

Plusieurs plugins ont été créé pour nous faciliter la tache:
+ [jQuery Lazyload](https://github.com/tuupola/jquery_lazyload)
+ [Unveil.js](http://luis-almeida.github.io/unveil/)
+ [jQuery.Lazy](http://jquery.eisbehr.de/lazy/)
+ etc

Créez une page HTML avec le contenu qui se trouve dans `lazy-load-content.html` de ce dossier. Utilisez un de ces plugins pour lazy-loader les images de votre page.

## Vidéos

Comment bien utiliser les vidéos :

+ Bien choisir leurs formats, toujours priviliger les vidéos aux gifs.
+ Optimiser la taille et le poids, supprimer les stream audio si le son n’est pas utilisé.
+ Redimensionner les videos à la volée pour les viewports différents avec Cloudinary 
+ Ne pas commencer à télécharger la vidéo tant que l’utilisateur n’a pas cliqué sur ‘Play’, faite attention à l’attribut `preload`

Guide complet Google d’utilisations des videos sur le web : <https://developers.google.com/web/fundamentals/media/video>