# Performance de site

+ [Les métriques RAILS de Google](https://developers.google.com/web/fundamentals/performance/rail)
+ [14 Important Website Performance Metrics You Should Be Analyzing](https://www.keycdn.com/blog/website-performance-metrics)

## L'importance de sites légers et rapides

C'est très important d'optimisation du code et des resources (images, vidéos, etc) pour augmenter la conversion sur votre site. Les sites lents causent du stress à leurs utilisateurs aussi grand que les filmes d'horreur 😱.

![Web horror](https://i.ibb.co/NmwXrjW/stress-by-web.png)

Google Search [pénalise](https://webmasters.googleblog.com/2018/01/using-page-speed-in-mobile-search.html) les sites mobiles lents et les placent plus bas dans les résultats de recherche.

![Slow Websites Study](https://neilpatel-qvjnwj7eutn3.netdna-ssl.com/wp-content/uploads/2011/04/loading-time-sml.jpg)

## Pourquoi les sites sont peu performants?

### Le site est trop lourd

![Average website size](https://i.ibb.co/9W06tvT/website-average-weight.png)

Si le site télécharge des **grands** fichiers HTML, des scripts JavaScript et CSS **lourds**, le temps de leurs evaluation et de rendu augmente et la satisfaction de l'utilisateur baisse.

### Trop de requêtes HTTPS

Chaque requête HTTP ajoute en moyenne ~700-800 octets (pas très grave) et 100ms de latence (grave !). Donc le but ultime est de faire le moins de requêtes que possible.

Si le site télécharge **trop de scripts** JavaScript, CSS et d'images le temps de leurs evaluation et de rendu augmente et la satisfaction de l'utilisateur baisse.


## Tester la performance d'un site

Vous pouvez tester la performance d'un site directement dans la console de Chrome (tab 'Audit')

![Ynov Audit](https://i.ibb.co/vvpw7wD/ynov-audit.png)

Il y a aussi les services qui mésurent la performance des sites déjà mis en ligne :
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