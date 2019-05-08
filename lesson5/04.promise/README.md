# Promise

+ [MDN > Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/promise)
+ [Handling async operations gracefully with Promises](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises)

Créez une *promise* (promesse) qui retourne une chaîne de caractères 'Hello' immediatement. Récupérez et logguez la valeur qu'elle retourne.

---

Créez une *promise* qui retourne une chaîne de caractères 'Hello' dans 3 secondes. Récupérez et logguez la valeur qu'elle retourne.

---

Créez une *promise* qui retourne une erreur 'Something went wrong!'. Récupérer et logguez cette erreur.

---

Créez une *promise* qui retourne un nombre N. [Enchaînez](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then#Chaining) le traitement de la *promise* pour effectuez les operations suivantes:
+ multiplier N par 2
+ ensuite soustraire 1
+ ensuite decrementer de 2
+ ensuite augmenter de 10. 
Logguez le résultat réçu.

---

Créez une fonction qui prend un nombre comme parametre et qui retourne une promise. Si le nombre passé est supérieur à 5 la promise est résolue avec succès, sinon la promise retourne une erreur 'Le nombre passé est trop grand'. Appelez la fonction créée et récupérez la valeur retournée par la promise.


## CRUD avec les promises

### Placeholder API: 

> Placeholder API: [https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)

Récupérez et affichez un article avec l'id 25, ensuite récupérez et affichez ses commentaires.

---

Récupérez et affichez 5 articles, sous chaque article récupérez et affichez leurs commentaires.

```js
const articles = [1, 2, 3, 4, 5];
```


### ReqRes

> Utilisez l'API de [https://reqres.in/](https://reqres.in/) et la méthode [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) qui retourne une *promise*.


Récupérez et affichez les informations de l'utilisateur avec l'id 5.

---

Créez un formulaire d'inscription. A la soumission du formulaire envoyez une requête pour créez un nouvel utilisateur. Sauvegardez ces données dans les cookies.

---

Créez un formulaire pour modifier le nom de l'utilisateur sauvegardé dans les cookies. Mettez à jour les données sauvegardées.

---

Copiez collez le code que vous avez créé puis refactorisez-le en utilisant la déclaration [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) et l'operateur [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await).


## Créez votre propre site de gifs.

![GIFS](http://www.commitstrip.com/wp-content/uploads/2016/02/Strip-Le-Gif-a-la-belle-vie-650-final.jpg)

[Giphy](https://giphy.com) est un service d'hébérgement de gifs avec un [API ouvert](https://developers.giphy.com/docs/).
Pour travailler avec l'API Giphy, vous avez besoin de créer un compte sur [giphy.com](https://giphy.com) et ensuite [obtenir une clé](https://developers.giphy.com/dashboard/?create=true) de test.

### Première page

Récuperez et affichez un gif aléatoire.


### Deuxième page

Affichez 5 gifs de la rubrique 'trending'. 

En bas de la page ajoutez un bouton 'Voir plus de gifs'. Si ce bouton est cliqué, téléchargez et affichez 5 gifs en plus.

Pour aller plus loin: ajoutez un champ de tri par note.


### Troisième page

Créez un champ de formulaire pour choisir et uploader un gif. Après avoir choisit un gif, montrez son aperçu. A la soumission du formulaire, uploadez le gif sur Giphy. 

En cas de succès, réinitialisez le formulaire, montrez en vert 'Success! Here is the link to your gif: $url'. 

En cas d'erreur, laissez le formulaire comme il est et montrez en rouge l'erreur 'Uh oh! An error occured. The error status is: $errorStatus'.

### Quatrième page

Créez un champ de recherche de gifs. Après chaque changement de la valeur du champs (et si sa longeur est supérieure à 3), cherchez et affichez les gifs avec le mot clé saisit. 

Le nombre maximum de gifs retournés ne doit pas depasser 10. S'il y a plus de 10 gifs trouvés, affichez la [pagination](https://getbootstrap.com/docs/4.1/components/pagination/).

Calculez le décalage *(offset)* avec la fonction `calculateOffset`

```js
/*
 * @param {number} currentPage
 * @param {number} limit
 */
function calculateOffset(currentPage, limit) {
  return currentPage * limit - limit
}
```

## Reading List

+ [Understanding promises in JavaScript](https://hackernoon.com/understanding-promises-in-javascript-13d99df067c1)
+ [JavaScript: Promises explained with simple real life analogies](https://codeburst.io/javascript-promises-explained-with-simple-real-life-analogies-dd6908092138)
+ [Promises for asynchronous programming](http://exploringjs.com/es6/ch_promises.html)
+ [Understanding async-await in Javascript](https://hackernoon.com/understanding-async-await-in-javascript-1d81bb079b2c)
+ [Asynchronous JavaScript: From Callback Hell to Async and Await](https://www.toptal.com/javascript/asynchronous-javascript-async-await-tutorial)