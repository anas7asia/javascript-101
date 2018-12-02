# Tableaux et traitements itératifs

Resources:
+ [w3schools](https://www.w3schools.com/js/js_arrays.asp)
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
+ [JavaScript.info > Tableaux](https://javascript.info/array)
+ [JavaScript.info > Méthodes de tableau](https://javascript.info/array)

1. Créez un tableau qui contient 3 de vos sites web préférés.
2. Loggez le premier élément de ce tableau.
3. Loggez le second élément de ce tableau.
4. Loggez le dernier élément de ce tableau avec l'aide de .length property.
5. Loggez le nombre d'élément du tableau.

Créez un tableau qui contient les éléments de différents types.

Créez un tableau *multidimensionnel* d'au moins de 3 éléments.
Loggez le premier élément du premier élément.
Modifiez le seconde élément du dernier élément.

## Ajouter/supprimer les éléments du tableau
Les méthodes à utiliser: 
[shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift), 
[unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift), 
[push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push), 
[pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop), 
[concat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)

```js
[1, 2, 3, 4, 5, 6, 7]
```
+ Supprimez le premier élément du tableau
+ Supprimez le dernier élément du tableau
+ Ajoutez un élément au début du tableau
+ Ajoutez un élément à la fin du tableau

---

Fusionnez deux tableau dans un seul: `[1, 2, 3]` et `[4, 5, 6]`
Fusionnez plusieurs tableaux dans un seul: `[1, 2, 3]` et `[4, 5, 6]` et `[7, 8, 9, 10]` et `[11, 12, 13, 14]`

## Transformer les tableaux
Les méthodes à utiliser: 
[reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse),
[join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join),
[sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

+ Transformez la chaîne de charactères `'Hello World'` en `'dlroW olleH'`. ()
+ Triez tous les éléments du tableau `[10, 3, 5, 2, 7, 9, 8, 6, 1, 0, 4]` de plus petit à plus grand.
+ Ensuite triez tous les éléments de ce tableau de plus grand à plus petit.
+ Triez les éléments du tableau `['One', 'two', 'Three', 'Four', 'Five']` en ordre alphabétique.
+ Triez le éléments du tableau aléatoirement

---

Créez une fonction `palindrome()` qui vérifie qu'une chaîne de charactères est un [palindrome](https://fr.wikipedia.org/wiki/Palindrome)
```js
palindrome('never odd or even') // should return true
palindrome('Radar') // should return true
palindrome('nope') // should return false
palindrome(`1 eye for of 1 eye.`) // should return false
palindrome('0_0 (: /-\ :) 0–0') // should return true
palindrome('Evil is a name of foeman as I live') // should return true
// Use String.prototype.replace to remove whitespaces, String.prototype.toLowerCase to manipulate strings
``` 

## Boucle for
Utilisez une boucle [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) pour créer un tableau `[0, 1, 2, 3, 4, 5]`.
Utilisez une autre boucle `for` pour augmenter par 1 chaque élément du tableau que vous venez de créer.

Triez le tableau `[0, 1, 2, 3, 4, 5, 6, 7]` avec une boucle `for` pour obtenir que des nombres impairs.

## Boucle while
Dans une boucle `while` augmenter la variable `index` par 1. Si le valeur de `index` est superieur à 10, arretez l'augmetation. 
> Attention de ne pas créer une boucle infinie 😱

Demandez l'utilisateur son mot de passe jusque ce qu'il saisi le mot de passe correct (toujours avec la boucle `while`)

## Itération
Les méthodes à utiliser: 
[map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map),
[forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach),
[reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

+ Divisez chaque élément du tableau `[0, 1, 2, 3, 4, 5]` par 2 sans modifier le tableau original
+ Passez chaque élément du tableau original en majuscule: `['Hello', 'World', 'I', 'am', 'John', 'Doe']`. Si l'index d'itération est 3, laissez l'élément comme il est.
+ Pouvez vous trouver la différence entre .map et .forEach? Répondez dans un commentaire.
+ En utilisant la méthode `reduce` concatenez tous les éléments du tableau `['Hello', 'World', 'I', 'am', 'John', 'Doe']` pour avoir une chaîne de charactères `'Hello World I am John Doe'`. 

## Trier le tableau
Les méthodes à utiliser: 
[find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find),
[some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort),
[every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every),
[filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter),
[includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)

+ Trouvez tous les éléments truthy du tableau: `[0, '0', null, 'Yay!', true, false, 'false']`
+ Trouvez la première chaîne de charactères qui a plus de 7 symboles: `['Hello', 'World', 'Am I long enough?', 'I am event longer, but what the point']`
+ Vérifiez si tous les éléments des tableaux suivants sont les chaînes de charactères: `['', 'I am', 'Ho ho ho']`, `['', 0, '']` 
+ Vérifiez s'il y a au moins 1 zéro dans le tableau: `[1, 1, 1, 1, 0, 1, 1, 0, 1]`
+ Vérifiez si 'Alex' est present dans le tableau: `['Mary', 'Thibaud', 'JF', 'Alex']`
+ Vérifiez si 'Alex' est present dans le tableau: `['Mary', 'Thibaud', 'JF', 'Alex']`. Si oui, loggez le premier emplacement (index) où il se trouve dans le tableau.

## Modifier le tableau
Les méthodes à utiliser: 
[slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

+ Extrayez les élément de position 2 à 4 sans modifier le tableau original: `[1, 2, 3, 4, 5, 6, 7]`
+ Extrayez le dernier élément du tableau sans modifier le tableau original: `[1, 2, 3]`
+ Supprimez deux premiers éléments du tableau original: `[1, 2, 3, 4, 5]`
+ Insérez trois éléments dans un tableau à la position 2: `[1, 2, 3, 4, 5]`
+ Insérez un élément dans un tableau au lieu d'un élément à la position 1: `[1, 2, 3, 4, 5]`

## Go an extra mile

Transformez un tableau multidimensionnel en un tableau simple
```js
[1, [2, 3], [3], [4, 5, 6]]
// becomes
[1, 2, 3, 4, 5, 6]
```

---

Vérifiez que tous les éléments du premier tableau sont présents dans le deuxìeme tableau:
```js
// First array
[1, 4, 3, 2, 5]
// Second array
[0, 1, 2, 3, 4, 5, 6, 7]
```

---

Créez une fonction qui mélange les éléments du tableau et ensuite le sépare en certain nombre d'autre tableaux plus petits
```js
function randomize(arr, elementsInArr) {
  // your code here
}

const myArr = ['a', 'b', 'c', 'd', 'e', 'f', 'j', 'k'];

const res1 = randomize(myArr, 3) // returns [['k', 'f', 'a'], ['b', 'j', 'e'], ['d', 'c']]
const res2 = randomize(myArr, 5) // returns [['k', 'f', 'a', 'b', 'j'], ['e', 'd', 'c']]

```
