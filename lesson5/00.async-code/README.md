# Programmation asynchrone

+ [MDN > Introducing async JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing)
+ [w3school > setTimeout](https://www.w3schools.com/jsref/met_win_settimeout.asp)

JavaScript côté client est *single threaded* (une seule chose peut se passer à la fois) et *blocking*
(l'exécution du code qui suit est bloqué jusqu'à la fin de l'opération en cours).

### Code synchrone

> *Synchrone* fait référence à une communication en temps réel pendant laquelle chaque partie reçoit les messages (et, si nécessaire, les traite et y répond) dès que possible après qu'ils aient été envoyés.
>
> [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Synchronous)

![Sync code](https://i.ibb.co/GJjg9r3/sync-code-gif.gif)

Toutes les expressions du code synchrone s'exécutent une par une. Si une expression n'a pas fini de s'exécuter, l'autre ne commencera pas son exécution – chacun à son tour.

Les expressions synchrones:
+ itérations
+ if / switch / operateur ternaire
+ calculs
+ écouteurs d'événements
+ alert / prompt / confirm
+ etc


### Code asynchrone

> *Asynchrone* fait référence à un environnement de communication où chaque partie reçoit et traite les messages lorsque c'est possible ou plus pratique, au lieu de le faire au même moment.
>
> [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Asynchronous)

![Async code](https://i.ibb.co/L84rYtj/async-code-gif.gif)

Les expressions asynchrones commencent leurs exécution quand toutes les expressions synchrones ont été exécutées. 

Nous ne sommes pas en mésure de prédire quand l'exécution du code asynchrone sera fait, cela dépendra de la performance du réseau, par exemple. Une exception est la methode setTimeout pour laquelle on précise le temps d'attente total.

**Exemple:**
Un étudiant travaille sur une tâche. Son professeur veut savoir quand l'étudiant terminera pour passer à la tâche suivante. 

*En mode synchrone,* le professeur reste à côté de l'étudiant et lui demande regulièrement si la tâche est terminée. Le professeur ne sais pas quand l'étudiant terminera, donc il est obligé de redemander plusieurs fois. L'enfer pour le prof ainsi que l'étudiant.

*En mode asynchrone,* le professeur travaille sur d'autres sujets en attendant que l'étudiant termine son travail. Quand il terminera, il previendra le professeur. Le temps est géré plus efficacement.

Les expressions asynchrones:
+ setTimeout
+ XMLHttpRequest
+ Promises
+ fetch

## setTimeout

Logguez dans la console `'Hello'` 3 secondes après le rendu de la page.

---

Logguez dans la console 'Logged after 5 seconds' 5 secondes après le rendu de la page.

---

Ajoutez un écouteur d'événement `'click'` à l'objet `window` pour logguer dans la console `'Clicked'` 3 secondes après le clique.

---

Créez un div. Au survol de ce div logguez dans la console `'I was hovered 5.5 seconds ago'` 5 secondes plus tard.


## onload et onerror

Créez dynamiquement une [image](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image) avec `src` égal à `http://lorempixel.com/400/200/`. 
<!-- Pas besoin de l'afficher sur la page. -->

Quand l'image sera entièrement chargée, logguez dans la console `'Done!'` et l'affichez sur la page.

En cas d'erreur de chargement, logguez dans la console `'Error'`.

---

Créez dynamiquement une node de script avec l'url de la librarie lodash: `https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js`.

Quand le script sera téléchargé, appelez la [fonction round](https://lodash.com/docs/4.17.11#round) pour arrondir le nombre `10.02`.


## Reading List

+ [Asynchronous Programming](https://eloquentjavascript.net/11_async.html)