# Fonctions

+ [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)
+ [w3schools](https://www.w3schools.com/js/js_functions.asp)
+ [JavaScript.info > Functions](https://javascript.info/function-basics)
+ [JavaScript.info > Function Expressions](https://javascript.info/function-expressions-arrows)

Pourquoi utiliser les fonctions?
​
```js
// I need to convert Fahrenheit to Celsius five times with different values:
const res1 = (5/9) * (18-32);
const res2 = (5/9) * (12-32);
const res3 = (5/9) * (33-32);
const res4 = (5/9) * (14-32);
const res5 = (5/9) * (17-32);

// Oh boy, this is repetitive. How can I spend less time on code writing and its maintaining?
// FUNCTIONS is the answer!

function toCelsius(fahrenheit) {
  return (5/9) * (fahrenheit-32);
}

const loveIt1 = toCelsius(18);
const loveIt2 = toCelsius(12);
const loveIt3 = toCelsius(33);
const loveIt4 = toCelsius(14);
const loveIt5 = toCelsius(17);
// Love it!
```

> DRY - **D**on't **R**epeat **Y**ourself
>
> A basic strategy for reducing complexity to managable units is to divide a system into pieces.
>
> from [3 Key Software Principles You Must Understand](https://code.tutsplus.com/tutorials/3-key-software-principles-you-must-understand--net-25161)

![Super function](http://www.commitstrip.com/wp-content/uploads/2014/12/La-fonctoin-utile-650-final.jpg)

1. Créez une fonction qui log `'Hello World'`
2. Créez une fonction qui retourne `'Hello World'`
3. Sauvegardez la valeur retournée par la première fonction
3. Sauvegardez la valeur retournée par la deuxième fonction
4. Comparez ces deux résultat. Est-ce que l'instruction `return` est obligatoire? Expliquez dans un commentaire.

---

Créez une fonction qui retourne un paramètre de cette fonction

---

Créez une fonction qui retourne la somme de deux nombres passés en paramètre de cette fonction

---

Créez une fonction qui [tronque](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring) la chaîne de caractères. Elle prend la chaîne de caractères, la longeur et la traînée (..., ->, etc) en tant que paramètres.
Donnez une valeur par défaut à la traînée. 
```js
truncate('I will be truncated', 15, '->') // returns 'I will be trunc->'
truncate('I will be truncated', 5) // returns 'I wil...'
```

## Scope local et global

Qu'est-ce que c'est le [scope](https://www.w3schools.com/js/js_scope.asp)?

Expliquez pour chaque variable précédée d’un commentaire si celle-ci est accessible.
​
```js
let count = 2;

function multiplyThemAll(num) {
  console.log(count) // accessible here ?
  let count2 = 3;
  console.log(count2) // accessible here ?
  return num * 2;
}

console.log(count) // accessible here ?
console.log(count2) // accessible here ?

```
> Préférez toujours les variables locales

<!-- ## Fonctions pures et impures

Une fonction pure est
​
> The function always returns the same result if the same arguments are passed in. It does not depend on any state, or data, change during a program’s exécution. It must only depend on its input arguments.
>
> from [What Are Pure Functions And Why Use Them?](https://medium.com/@jamesjefferyuk/javascript-what-are-pure-functions-4d4d5392d49c)

Refactorisez ce code pour avoir une fonction pure :
```js

const totalPrice = 0;

function calcPrice(price, qty) {
  totalPrice = price * qty;
}

calcPrice(14, 3);
```

> Quand vous pouvez, créez toujours les fonctions pures -->

## Fonctions ES6

Refactorisez ce code pour utiliser une [expression de fonction fléchée](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions):

```js
const numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
  return a - b;
})
```

## Expression de fonction  

Refactorisez ce code pour utiliser une [expression de fonction](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function)

```js
const numbers = [4, 2, 5, 1, 3];
numbers.sort(function(a, b) {
  return a - b;
})
```

## Hoisting

Expliquez dans un commentaire quelles expressions sont ["hoisted"](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) et quand on peut les appeler.

```js

multiply(3, 4); // what's happening here?
sum(2, 2); // what's happening here?

const sum = function(a, b) { 
  return a + b;
};

function multiply(a, b) {
  return a * b;
}

multiply(3, 4); // what's happening here?
sum(2, 2); // what's happening here?
```

## Pour aller plus loin

Copiez collez le code du calculateur de BMI que vous avez créé puis refactorisez-le pour utiliser les fonctions.

<!-- pures. -->
​
## Reading List

+ [Eloquent JavaScript > Functions](https://eloquentjavascript.net/03_functions.html)
+ [Principles To Code By](https://medium.com/dailyjs/principles-to-code-by-3c516ad61fcc)
+ [You don't know JS > Hoisting](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch4.md)
+ [You don't know JS > Scope](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch1.md#review-tldr)
+ [You don't know JS > Function Arguments](https://github.com/getify/You-Dont-Know-JS/blob/master/types%20%26%20grammar/ch5.md#function-arguments)