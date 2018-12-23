# Programmation asynchrone

+ [MDN > Introducing async JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing)
+ [w3school > setTimeout](https://www.w3schools.com/jsref/met_win_settimeout.asp)

JavaScript côté client est *single threaded* (une seule chose peut se passer à la fois) et *blocking*
(l'exécution du code qui suit est bloqué jusqu'à la fin d'une opération).

### Code synchrone

> *Synchrone* fait référence à une communication en temps réel pendant laquelle chaque partie reçoit les messages (et, si nécessaire, les traite et y répond) dès que possible après qu'ils aient été envoyés.
>
> [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Synchronous)

![Sync code](https://i.ibb.co/GJjg9r3/sync-code-gif.gif)

Toutes les expressions du code syncrone s'exécutent une par une. Si une expression n'a pas fini de s'exécuter, l'autre commencera pas son exécution – chacun à son tour.

Les expressions syncrones:
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

Les expressions asyncrones commencent leurs exécution quand toutes les expressions syncrones sont exécutées. 

Nous ne sommes pas en mésure de prédire quand l'exécution du code asyncrone sera fait, cela dépendra de la performance du réseau, par exemple. Une exception est la methode setTimeout pour laquelle on précise le temps d'attente.

**Exemple:**
Un étudiant travaille sur une tâche. Son professeur veut savoir quand l'étudiant terminera pour passer à la tâche suivante. 

*En mode synchrone,* le professeur reste à côté de l'étudiant et lui demande regulièrement si la tâche est terminée. Le professeur ne sais pas quand l'étudiant terminera, donc il est obligé de redemander plusieurs fois. L'enfer pour le prof ainsi que l'étudiant.

*En mode asynchrone,* le professeur travaille sur les autres choses en attendant que l'étudiant termine son travail. Quand il terminera, il previendra le professeur. Le temps est géré plus efficacement.

Les expressions asyncrones:
+ setTimeout
+ XMLHttpRequest
+ Promises
+ fetch

## setTimeout

Loggez `'Hello'` 3 secondes après le rendu de la page.

---

Ajoutez un écouteur d'événement 'click' à l'objet window 10 secondes après le rendu de la page.


## onload et onerror

Créez dynamiquement un [image](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image) avec `src` égal à `http://lorempixel.com/400/200/`. Pas besoin de l'afficher sur la page.
Quand l'image sera entièrement chargé, loggez `'Done!'`.
En cas d'erreur de chargement, loggez `'Error'`.

---

Créez dynamiquement un node de script avec l'url de la librarie lodash: `https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js`.
Quand le script sera téléchargé, appelez une de [ces fonctions](https://lodash.com/docs/4.17.11).


## Reading List

+ [Asynchronous Programming](https://eloquentjavascript.net/11_async.html)