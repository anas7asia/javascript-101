# Programmation asynchrone

Dans un navigateur JavaScript est un langage *single threaded* (une seule chose peut se passer à la fois) et *blocking*
(tout le reste est bloqué jusqu'à la fin d'une opération).

### Synchrone

> *Synchrone* fait référence à une communication en temps réel pendant laquelle chaque partie reçoit les messages (et, si nécessaire, les traite et y répond) dès que possible après qu'ils aient été envoyés.
>
> [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Synchronous)

![Sync code](https://i.ibb.co/GJjg9r3/sync-code-gif.gif)

Toutes les expressions du code syncrone s'exécutent une par une. Si une expression n'a pas terminé de s'exécuter, l'autre commencera pas son exécution – chaqu'un son tour.

Les expressions syncrones:
+ itérations
+ if / switch / operateur ternaire
+ calculs
+ écouteurs d'événements
+ alert / prompt / confirm
+ etc


### Asynchrone

> *Asynchrone* fait référence à un environnement de communication où chaque partie reçoit et traite les messages lorsque c'est possible ou plus pratique, au lieu de le faire au même moment.
>
> [MDN](https://developer.mozilla.org/fr/docs/Glossaire/Asynchronous)

![Async code](https://i.ibb.co/L84rYtj/async-code-gif.gif)

Les expressions asyncrones commencent leurs exécution quand toutes les expressions syncrones sont exécutées. Sauf la methode setTimeout pour laquelle on précise le temps d'attente, on ne sait jamais à quel moment l'exécution sera terminée.

**Exemple:** un étudiant travaille sur une tâche. Son professeur veux savoir quand l'étudiant terminera pour passer à la tâche suivante. 
En mode synchrone, le professeur reste à côté de l'étudiant et lui demande regulièrement si celui-là a terminé. Le professeur ne sais pas quand l'étudiant terminera, donc il est obligé de redemander plusieurs fois. Personne active ici et le prof.
En mode asynchrone, le prof travaille sur les autres tâches en attendant que l'étudiant termine son travail. Quand il terminera, il previendra le professeur. Le temps est géré plus efficacement.

Les expressions asyncrones:
+ setTimeout
+ XMLHttpRequest (AJAX)
+ Promises
+ fetch
+ async await


> Grâce à l'exécution asyncrone on peut attendre un certain temps pour exécuter un bout de code.


## setTimeout

Loggez `'Hello'` 3 secondes après le rendu de la page.

---

Ajoutez un écouteur d'événement 'click' à l'objet window 10 secondes après le rendu de la page.

---

```js

function placeOrder(oNum){
  console.log("Customer order",oNum);
  cookAndDeliverFood(function(){    
    console.log("Deliverd food order:",oNum);
  });
}
 
//Simulate a 5s operation
function cookAndDeliverFood(callback){    
  setTimeout(callback,5000);
}
 
//Simulate User requests;
placeOrder(1);
placeOrder(2);
placeOrder(3);
placeOrder(4);
placeOrder(5);


/*
Après l'exécution du code vous devez avoir:

Customer order 1
Customer order 2
Customer order 3
Customer order 4
Customer order 5
Deliverd food order: 1
Deliverd food order: 2
Deliverd food order: 3
Deliverd food order: 4
Deliverd food order: 5


*/

```

# onload

Img onload function

Script onload function
Load lodash lib and call its function


## Reading List

+ [Asynchronous Programming](https://eloquentjavascript.net/11_async.html)