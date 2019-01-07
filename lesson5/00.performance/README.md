# Performance de site

+ [Les métriques RAILS de Google](https://developers.google.com/web/fundamentals/performance/rail)
+ []()

## L'impacte


C'est très important de se prendre la tête avec l'optimisation du site à la fin de son développement, parce que personne aime les sites lents 😱 

Les sites qui load lentement même causent du stress à leurs utilisateurs.

![Web horror](https://i.ibb.co/NmwXrjW/stress-by-web.png)


<!-- Les metrics RAILS pour augmenter la satisfation de l'itilisateur de votre site: <https://developers.google.com/web/fundamentals/performance/rail> -->

<!-- // TODO: Si le site est 3% plus lent, il perd tant d'utilisateurs -->

Google Search [pénalise](https://webmasters.googleblog.com/2018/01/using-page-speed-in-mobile-search.html) les sites mobiles lents et les placent plus bas dans les résultats des recherches.


> Une fois de plus, optimisez vos sites

## Pourquoi les sites sont peu performants?

### Trop de requêtes HTTPS

Multiple requests means more latency
Chaque requête HTTP ajoute en moyenne ~700-800 octets (pas très grave) et 100ms de latence (grave!). Donc le but ultime est de faire le moins de requêtes que possible.

![Average website size](https://i.ibb.co/9W06tvT/website-average-weight.png)

Si le site télécharge trop de scripts JavaScript, CSS et d'images le temps de leurs evaluation et de rendu augmente et la satisfaction de l'utilisateur baisse.


### Memoire

Il n'y a pas besoin de gerer la memoire avec JS. [Garbage collector](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management) s'occupe de libérer la mémoire. Par contre, les memory leaks peuvent avoir place.

Trop de variables globales. Les variables globales sont jamais détruites, donc la mémoire qui leur est donnée, n'est jamais libérée.

Les écouteurs d'événements sont pas detachés. Les écouteurs d'événements consomment beaucoup de mémoire, si on les detache pas, leur nombre va incrementer et ralentir votre site. **N'oubliez pas de les detacher.**

Trop d'animations ralentissent le site et font bogger le rendu de la page.

Le sites a trop de plugins qui consomment beaucoup de CPU.

## Tester la performance d'un site

Vous pouvez tester les performance d'un site directement dans la console de Chrome (tab 'Audit')

![Ynov Audit](https://i.ibb.co/vvpw7wD/ynov-audit.png)

Il y a aussi les sites qui mésure la performance des sites qui permettent de tester les sites qui sont déjà en ligne :
+ [Web Page Test](https://www.webpagetest.org/)
+ [Pingdom](https://tools.pingdom.com/)
+ [Google Page Speed](https://developers.google.com/speed/pagespeed/insights/)

Les clés les plus importantes du rendu d'un site : 
1. [First Contentful Paint ou Time to First Byte](https://developers.google.com/web/tools/lighthouse/audits/first-meaningful-paint) mesure le temps nécessaire à une page d'afficher le premier byte de son contenu.
2. [Speed Index](https://developers.google.com/web/tools/lighthouse/audits/speed-index) est le temps pris d'afficher les parties visibles de la page.
2. [Time To Interact](https://developers.google.com/web/tools/lighthouse/audits/time-to-interactive) mesure le temps nécessaire à une page de devenir interactive.

## Reading List

+ [Web Performance 101](https://3perf.com/talks/web-perf-101/#perf-importance-horror)
+ [JavaScript.info > Garbage Collection](https://javascript.info/garbage-collection)