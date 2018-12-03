# Objets

Resources:
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
+ [w3schools](https://www.w3schools.com/js/js_objects.asp)

1. Créez un objet avec les valeurs suivants: id = 1, name = Jeremy, email = jeremy@ynov.com.
2. Loggez l'id de cet objet avec .
3. Loggez l'id de cet objet avec les crochets.
4. Declarez une variable avec le valeur 'name'. Accédez la propriété 'name' de votre objet par cette variable.
5. Changez la valeur de id dans votre objet à 2.
6. Ajoutez une nouvelle propriété 'human' de valeur `true` à votre objet.
7. Changez la valeur de la propriété 'email' à `undefined`.
8. Supprimez complètement la propriété 'email'.
9. Vérifiez si votre objet [a](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty) la propriété 'email'/'human'

---

Refactoriser ce code pour ne plus utiliser la même référence et pouvoir modifier `myObj2` sans modifier `myObj`.
Utilisez la métode `Object.create()` ou opérateur spread `...`

```js
const myObj = { name: 'Pascal' };
const myObj2 = myObj;
myobj2['name'] = 'Paul';
console.log(myObj2) // { name: 'Paul' } - What the heck?
console.log(myObj) // { name: 'Paul' }
```

---

Créez un objet imbriqué 'user' avec les propriétés: id, name, car. 'Car' est aussi un objet avec les propriétés: id, brand, color.
Loggez l'id de user.
Loggez l'id de car.
Loggez la couleur de la voiture.

---
Vous avez un tableau d'objets. 
Vérifiez par le nom si l'object est présent dans le tableau.
Si l'objet n'existe pas, retournez 'Stop it, muggle'.
Si l'objet existe, vérifiez s'il a la propriété demandé.
Si la propriété existe retournez-la, sinon retournez 'No such property. Contact Madame Pince to find out more.'

```js
const magicians = [
  {
    id: 1,
    firstname: 'Harry',
    lastname: 'Potter',
    house: 'Gryffindor'
  },
  {
    id: 2,
    firstname: 'Hermione',
    lastname: 'Granger',
    house: 'Gryffindor'
  },
  {
    id: 3,
    firstname: 'Draco',
    lastname: 'Malfoy',
    house: 'Slytherin'
  },
  {
    id: 4,
    firstname: 'Albus',
    lastname: 'Dumbledore'
  }
]
magicLookUp('Potter', 'id') // 1
magicLookUp('Granger', 'house') // Gryffindor
magicLookUp('Dursley', 'house') // Stop it, muggle
magicLookUp('Malfoy', 'lastname') // Draco
magicLookUp('Dumbledore', 'house') // No such property. Contact Madame Pince to find out more.
```
---

Calculez le prix total avec la boucle [For...In](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)

```js
const cart = [
  { item: 'x', price: 3 , quantity: 1 },
  { item: 'y', price: 7, quantity: 5 },
  { item: 'z', price: 4, quantity: 2 },
]
```

---

Trouvez dans un tableau l'objet avec une certaine propriété:

```js
const cart = [
  { name: 'Mathieu', age: 18, hobby: 'Snowboard'},
  { name: 'Claire', age: 22, hobby: 'Gaming'},
  { name: 'Franck', age: 20, hobby: 'Astronomy'}
]

findObjectByProperty('hobby', 'Snowboard') // returns { name: 'Mathieu', age: 18, hobby: 'Snowboard'}
findObjectByProperty('age', 22) // returns { name: 'Claire', age: 22, hobby: 'Gaming'}
```

---

Calculez le prix d'achat total avec `.reduce()`, `.forEach()`, ou `.map()`. 
Doublez le prix de chaque élément du tableau. 💰💰💰 
Trouvez le nouveau prix total. 

```js
const cart = [
  { item: 'a', price: 2, quantity: 1 }
  { item: 'b', price: 3, quantity: 1 }
  { item: 'c', price: 4, quantity: 1 }
]
```

---

Trouvez tous les produits qui sont plus chers que 10€

```js
const cart = [
  { item: 'a', quantity: 1, price: 8 },
  { item: 'b', quantity: 2, price: 10 },
  { item: 'c', quantity: 3, price: 13 },
  { item: 'd', quantity: 4, price: 5 },
  { item: 'e', quantity: 5, price: 23 },
]
```

## Les objets globaux

JavaScript a [plusieurs objets]() qui sont disponibles à n'importe quel moment dans votre application. Vous conaissez déjà cerains entre eux.

### Math

Utilisez les méthodes de l'objet `Math`.

Créez une fonction qui retourne un nombre entier aléatoire entre 0 et un nombre passé comme paramètre.
```js
getRandomNumber(23); // returns 10 or another number between 0 and 23
getRandomNumber(3); // returns 2 or another number between 0 and 3
```

---

Créez une fonction qui prend un nombre décimal et retourne un nombre entier forcément plis petit (ou égal) que le nombre passé.
```js
yourFunction(3.3); // returns 3
yourFunction(4.5); // returns 4
yourFunction(5.7); // returns 5
```

---

Créez une fonction qui prend un nombre décimal et retourne un nombre entier forcément plus grand (ou égal) que le nombre passé.
```js
yourFunction(3.3); // returns 4
yourFunction(4.5); // returns 5
yourFunction(5.7); // returns 6
```

---

Créez une fonction qui prend un nombre décimal et retourne un nombre entier arrondi.
```js
yourFunction(3.3); // returns 3
yourFunction(4.5); // returns 5
yourFunction(5.7); // returns 6
```

---

Créez une fonction qui trouve le plus grand nombre du tableau passé
```js
yourFunction([1, 2, 3]); // returns 3
yourFunction([20, 3, 18]); // returns 20
```

---

Créez une fonction qui trouve le plus petit nombre du tableau passé
```js
yourFunction([1, 2, 3]); // returns 1
yourFunction([20, 3, 18]); // returns 2
```

### Date

![Hardcoded date is no good](http://www.commitstrip.com/wp-content/uploads/2013/01/Strips-Date-hardcod%C3%A9e-test-trollface.jpg)

Utilisez les méthodes de l'objet `Date`. N'oubliez d'*instancier* cet objet.

Affichez la date d'aujourd'hui en format DD/MM/YYYY

---

Affichez le jour de la semaine du 1 janvier 2005

---

Créez une horloge qui log le temps chaque seconde en format heures:minutes:secondes


## Reading List
+ [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/ch3.md)