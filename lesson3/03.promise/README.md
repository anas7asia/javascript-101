# Promise

+ [MDN > Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/promise)
+ [Handling async operations gracefully with Promises](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises)

Créez un promise qui retourne une chaîne de caractèrs 'Hello' immediatement. Récupérez et loggez le valeur qu'il retourne.

---

Créez un promise qui retourne une chaîne de caractèrs 'Hello' dans 3 secondes. Récupérez et loggez le valeur qu'il retourne.

---

Créez un promise qui retourne une erreur 'Something went wrong!'. Récupérer et loggez cette erreur.

---

Créez un promise qui retourne un nombre. [Enchaînez](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then#Chaining) le traitement du promise pour effectuez les operations suivantes:
multiplier par 2, ensuite soustraire 1, ensuite decrementer de 2, augmenter de 10. Loggez le résultat réçu.


## CRUD avec les promises

Utiliser l'API de [https://reqres.in/](https://reqres.in/) et la méthode [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) qui retourne un promise.


Récupérez et affichez l'info de l'utilisateur avec l'id 5.

---

Créez un formulaire d'inscription. A la soumission du formulaire envoyer une requête pour créez un nouveau utilisateur. Sauvegardez ces données dans les cookies.

---

Créez un formulaire pour modifier le nom de l'utilisateur sauvegardé dans les cookies. Mettez à jour les données sauvegardée.

---

Copiez collez le code que vous avez créé puis refactorisez-le en utilisant la déclaration [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) et l'operateur [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await).


## Créez votre propre site de gifs.

[Giphy](https://giphy.com) est un service d'hébérgement de gifs avec un [API ouvert](https://developers.giphy.com/docs/).
Pour travailler avec Giphy API, vous avez besoin de créer un compte sur [giphy.com](https://giphy.com) et ensuite [obtenir une clé](https://developers.giphy.com/dashboard/?create=true) de développement.

### Première page

Récuperez et affichez un gif aléatoire.


### Deuxième page

Affichez 5 gifs de la rubrique 'trending'. 
En bas de la page ajoutez un bouton 'Voir plus de gifs'. Si ce bouton est cliqué, téléchargez 5 gifs suivants et affichez toute la collection de gifs.

(optionnel) Ajouter un champ de tri par rating.


### Troisième page

Créez un champ de formulaire pour choisir et uploader un gif. Après avoir choisit un gif, montrez son aperçu. A la soumission du formulaire, uploadez le gif sur Giphy. 
En cas de succès, empty le formulaire, montrez en vert 'Success. Here is the link to your gif: $url'. 
En cas d'erreur, laissez le formulaire comme il est et montrez en rouge l'erreur 'Uh oh! An error occured. The error status is: $errorStatus'.

(optionnel) Ajoutez un autre champ pour uploader un gif à partir d'un url. A là soumission du formulaire vérifiez que un de ces deux champs est rempli et uploadez le ficher sur Giphy.


### Quatrième page

Créez un champ de recherche de gifs. Après chaque changement de la valeur du champs (et sa longeur est inférioeur à 3), cherchez et affichez les gifs avec le mot clé saisit. Nombre maximum de gifs retournés ne doit pas depasser 10. S'il y a plus, affichez la [pagination](https://getbootstrap.com/docs/4.1/components/pagination/)
Si un bouton de pagination est cliqué, montrez la liste de gifs avec un propre décalage *(offset)*

```js
/*
 * @param {number} currentPage
 * @param {number} limit
 */
function calculateOffset(currentPage, limit) {
  return currentPage * limit - limit
}
```