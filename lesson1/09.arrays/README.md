# Tableaux et traitements itératifs

+ [w3schools](https://www.w3schools.com/js/js_arrays.asp)
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
+ [JavaScript.info > Tableaux](https://javascript.info/array)
+ [JavaScript.info > Méthodes de tableau](https://javascript.info/array)

1. Créez un tableau qui contient 3 de vos sites web préférés.
2. Loggez le premier élément de ce tableau.
3. Loggez le second élément de ce tableau.
5. Loggez le nombre d'éléments de ce tableau.
4. Loggez le dernier élément de ce tableau avec de l'aide de la propriété .length.

---

Créez un tableau qui contient les éléments de différents types.

---

Créez un tableau *multidimensionnel* d'au moins 3 éléments.
Loggez le premier élément du premier élément.
Modifiez le second élément du dernier élément.

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
+ Supprimez le premier élément du tableau.
+ Supprimez le dernier élément du tableau.
+ Ajoutez un élément au début du tableau.
+ Ajoutez un élément à la fin du tableau.

---

Fusionnez deux tableau dans un seul: `[1, 2, 3]` et `[4, 5, 6]`
Fusionnez plusieurs tableaux dans un seul: `[1, 2, 3]` et `[4, 5, 6]` et `[7, 8, 9, 10]` et `[11, 12, 13, 14]`

---

Les méthodes à utiliser: 
[slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice),
[splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

+ Extrayez les éléments de la position 2 à 4 sans modifier le tableau original: `[1, 2, 3, 4, 5, 6, 7]`
+ Extrayez le dernier élément du tableau sans modifier le tableau original: `[1, 2, 3]`
+ Supprimez les deux premiers éléments du tableau original: `[1, 2, 3, 4, 5]`
+ Insérez trois éléments dans un tableau à la position 2: `[1, 2, 3, 4, 5]`
+ Remplacer l’élément en position 1 par un autre élément: `[1, 2, 3, 4, 5]`
​

## Référence et valeur

Refactoriser ce code pour ne plus utiliser la [même référence](https://github.com/getify/You-Dont-Know-JS/blob/master/types%20%26%20grammar/ch2.md#value-vs-reference) et pouvoir modifier `myArr2` sans modifier `myArr`.
Utilisez la métode `slice` ou l'opérateur spread `...`

```js
const myArr = [1, 2, 3];
const myArr2 = myArr;
myArr2[0] = 0;
console.log(myArr) // [0, 2, 3] - What the heck? Why? How?
console.log(myArr2) // [0, 2, 3]
```

## Transformer les tableaux
Les méthodes à utiliser: 
[reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse),
[join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join),
[sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

+ Transformez la chaîne de caractères `'Hello World'` en `'dlroW olleH'`. Utilisez la méthode ['split'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split) pour transformez chaque lettre en un élément du tableau.
+ Triez tous les éléments du tableau `[10, 3, 5, 2, 7, 9, 8, 6, 1, 0, 4]` de plus petit au plus grand.
+ Ensuite triez tous les éléments de ce tableau de plus grand au plus petit.
+ Triez les éléments du tableau `['One', 'two', 'Three', 'Four', 'Five']` par ordre alphabétique.

## Itération
Les méthodes à utiliser: 
[map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map),
[forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach),
[reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

Divisez chaque élément du tableau `[0, 1, 2, 3, 4, 5]` par 2 sans modifier le tableau original.

---

Passez chaque élément du tableau original en majuscule: `['Hello', 'World', 'I', 'am', 'John', 'Doe']`. Si l'index d'itération est égal à 3, laissez l'élément comme il est.

```js
uppercaseMyArr(['Hello', 'World', 'I', 'am', 'John', 'Doe']) // ['HELLO', 'WORLD', 'I', 'am', 'JOHN', 'DOE']
```

---

Pouvez vous trouver la différence entre .map et .forEach? Répondez dans un commentaire.

---

Utilisez la méthode `reduce` pour rassembler (concatener) tous les éléments du tableau `['Hello', 'World', 'I', 'am', 'John', 'Doe']` en une chaîne de caractères `'Hello World I am John Doe'`. 

## Trier le tableau
Les méthodes à utiliser: 
[find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find),
[some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort),
[every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every),
[filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter),
[includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes),
[indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)

Trouvez tous les éléments truthy du tableau `[0, '0', null, 'Yay!', true, false, 'false']`.

---

Trouvez la première chaîne de caractères qui a plus de 7 symboles: `['Hello', 'World', 'Am I long enough?', 'I am even longer, but what the point?']`.

---

Vérifiez si tous les éléments de tableau sont les chaînes de caractères.
```js
checkAllElmntsAreStrings(['', 'I am', 'Ho ho ho']) // true
checkAllElmntsAreStrings(['', 0, '']) // false
```

---

Vérifiez s'il y a au moins 1 zéro dans le tableau: `[1, 1, 1, 1, 0, 1, 1, 0, 1]`.

---

Vérifiez si 'Alex' est present dans le tableau: `['Mary', 'Thibaud', 'JF', 'Alex']`.

---

Vérifiez si 'Alex' est present dans le tableau: `['Mary', 'Alex', 'Thibaud', 'JF', 'Alex']`. Si oui, loggez le premier emplacement (index) où il se trouve dans le tableau.


## Boucle for

![For and Foreach](http://www.commitstrip.com/wp-content/uploads/2014/07/Strip-Dora-la-codeuse-650-final.jpg)

Utilisez une boucle [for](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) pour créer un tableau `[0, 1, 2, 3, 4, 5]`.
Utilisez une autre boucle `for` pour augmenter de 1 chaque élément de ce nouveau tableau.

---

Triez le tableau `[0, 1, 2, 3, 4, 5, 6, 7]` avec une boucle `for` pour obtenir que des nombres impairs.

## Boucle while

![While loop](https://i.ibb.co/gFGS4hy/while-loop.jpg)

Dans une boucle [`while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while) augmenter la variable `index` de 3. Si la valeur de `index` est supérieure à 10, arretez l'augmetation. Attention de ne pas créer une boucle infinie 😱

---

Pour avoir accès à votre site web, il faut saisir le mot de passe 'qwerty'.
Continuez à demander utilisateur le mot de passe avec la méthode `prompt` jusqu'à ce qu'il soit correct.


## Pour aller plus loin

Créez une fonction `palindrome()` qui vérifie qu'une chaîne de caractères est un [palindrome](https://fr.wikipedia.org/wiki/Palindrome)
```js
palindrome('never odd or even') // true
palindrome('Radar') // true
palindrome('nope') // false
palindrome(`1 eye for of 1 eye.`) // false
palindrome('0_0 (: /-\ :) 0–0') // true
palindrome('Evil is a name of foeman as I live') // true
// Use String.prototype.replace to remove whitespaces, String.prototype.toLowerCase to manipulate strings
``` 

---

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

Créez une fonction qui mélange les éléments du tableau aléatoirement et ensuite les sépare en certain nombre d'autres tableaux.
```js
function randomize(arr, elementsInArr) {
  // your code here
}

const myArr = ['a', 'b', 'c', 'd', 'e', 'f', 'j', 'k'];

const res1 = randomize(myArr, 3) // returns [['k', 'f', 'a'], ['b', 'j', 'e'], ['d', 'c']]
const res2 = randomize(myArr, 5) // returns [['k', 'f', 'a', 'b', 'j'], ['e', 'd', 'c']]

```

## Reading List

+ [Eloquent JavaScript > Data Structures](https://eloquentjavascript.net/04_data.html)
+ [You Don't Know JS > Arrays](https://github.com/getify/You-Dont-Know-JS/blob/master/types%20%26%20grammar/ch2.md#arrays)
+ [You Don't Know JS > Array-Likes](https://github.com/getify/You-Dont-Know-JS/blob/master/types%20%26%20grammar/ch2.md#array-likes)
+ [You Don't Know JS > Loop](https://github.com/getify/You-Dont-Know-JS/blob/master/up%20%26%20going/ch1.md#loops)