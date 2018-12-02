# Traitments conditionnés

Resources: 
+ [MDN > opérateurs de comparaison](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
+ [MDN > If...Else](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
+ [JavaScript.info > opérateurs de comparaison](https://javascript.info/comparison)
+ [JavaScript.info > If...Else](https://javascript.info/comparison)

![ifs](https://pics.me.me/a-programmers-wife-sends-him-to-the-grocery-store-with-31715874.png)

## Opérateurs de comparaison

+ Vérifiez si 2 est supérieur à 1.
+ Vérifiez si 2 est inférieur à 1.
+ Vérifiez si 2 est inférieur à 5.
+ Vérifiez si 20 est supérieur ou égal à 10.
+ Vérifiez si 10 est supérieur ou égal à 10.
+ Vérifiez si 5 est inférieur ou égal à 10.
+ Vérifiez si 4 n'est pas égal à 6.
+ Vérifiez si '5' transformé en nombre n'est pas égal à 5.
+ Vérifiez si '2' est égal à 2 avec l'opérateur d'égalité simple. Si vrai, loggez "Strangely, it's true".
+ Vérifiez si '2' est égal à 2 avec l'opérateur d'égalité stricte. Si vrai, loggez "Now it makes sense", sinon logez une explication pourquoi l'opérateur d'égalité stricte est préférable.
+ Vérifiez si 0 n'est pas égal à '0'.
+ Vérifiez si 0 n'est pas strictement égal à '0'.
+ Vérifiez si 'hello' est égal à 'hello'.
+ Vérifiez si 'hello' est égal à 'Hello'.
+ Vérifiez si `'true'` est égal à `true`. Si c'est le cas, loggez 'Nice!', sinon trouvez un moyen de les comparer.

## If ... Else

Vérifiez si `5` est supérieur à 0 ET inférieur à 10 dans la même expression.

Vérifiez si `20` divisé par `2` est supérieur ou égal à 10 OU inférieur à 15 dans la même expression. Si vrai, loggez `'Yes'`, sinon loggez `'No'`.

Un groupe peut être publique ou privé. Utilisateur peut accéder son contenu si le groupe est publique ou si le groupe est privé mais il a rejoint ce group. 
Utilisez deux variables `isPrivate` et `isMember` pour écrire une seule condition qui vérifie que utilisateur peut voir le contenu du group.
Testez votre solution avec les valeurs suivants:
```js
// can see the group
let isPrivate = false;
let isMember = false;

// can't see the group
let isPrivate = true;
let isMember = false;

// can see the group
let isPrivate = true;
let isMember = true;

```

## Vrai ou faux?

Utilisez opérateur `!` avec les valeurs suivants. Expliquez dans un commentaire pourquoi on utilise cet opérateur.
```js
'', '0', 1, 0, undefined, null, NaN, 'Hello World', {hello: 'World}, {}, [1, 2, 3], []
```

---

```js
let isButtonVisible = true; // can be true or false
```
Comparer `isButtonVisible` avec `false` pour vérifier si le bouton n'est pas visible. Si non visible, loggez `'Hidden'`, sinon loggez `'Visible'`.
Refactorisez votre code pour utiliser l'opérateur `!`.

---

Utilisez opérateur `!!` avec les valeurs suivants. Expliquez dans un commentaire pourquoi on utilise cet opérateur.
```js
'', '0', 1, 0, undefined, null, NaN, 'Hello World', {hello: 'World}, {}, [1, 2, 3], []
```

---

Demandez utilisateur de se présenter avec la méthode [prompt](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt). Pour vérifier qu'utilisateur a saisi son prénom comparez le user input avec `true`. Si le prénom est saisi, [alert](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert) 'Nice to meet you $username ($username est le prénon saisi)!', sinon alert 'Don't be shy!'
Refactorisez votre code pour utiliser l'opérateur `!!`.

---

Testez les valeurs suivants dans la construction `if`. Lesquels sont TRUTHY et lesquels sont FALSY? 
```js
'', '0', 1, 0, undefined, null, NaN, 'Hello World', {hello: 'World}, {}, [1, 2, 3], []
// List truthy values here:
// List falsy values here:
```

Refactorisez le code de la tâche précédante pour ne pas comparer avec `true`. Vérifiez simplement que le valeur saisi est truthy/falsy.

## Nested if

Utilisateur de votre site web est soit connecté soit pas connecté. Celui qui est connecté peut avoir des status différents:
0 - standard user
1 - admin
2 - website owner

Si utilisateur est connecté, vérifiez son status et loggez: 'Hello %username' for standard user, 'Hello powerful' for admin 'Hello powerful' for admin.
S'il n'est pas connecté, loggez 'Please, connect'

## Switch

Refactorisez le code de la tâche précédante pour utiliser l'instruction [switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)

Obtenez ce jour de la semaine avec l'objet [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) et sa méthode `getDay`.
Utilisez l'instruction `switch` pour traduire les jours de la semaine en français. 
En JavaScript, le premier jour de la semaine est dimanche 😉.
```js
const today = new Date();
const todayDay = today.getDay();
```

Obtenez le mois en cours toujour avec l'objet Date.
Utilisez l'instruction `switch` avec le regroupement des cas pour dire dans quelle saison on se trouve: hiver, été ou mi-saison.

## Opérateur ternaire

Utilisez l'opérateur ternaire pour effectuer l'opération suivante:
Si l'id du client est valide, sauvegarder ces achats dans la base de données (ou juste loggez 'Saved'). Sinon annulez la commande.

Utilisateur arrive sur votre site web. Si c'est sa première fois ici, vous devez montrer une notice que vous utilisez cookies selon le RGPD (Règlement Général à la Protection des Données). Sinon, ne le montrez plus.
Pour décider de montrer la notice ou pas 
```js
const isFirstTimeHere = true; // ou false
const isCookiesVisible = // use ternaty operator here to assign value to isCookiesVisible variable
```

## BMI calculator
Créez un calculateur de [Body Mass Index](https://fr.wikipedia.org/wiki/Indice_de_masse_corporelle).
Utilisez la méthode prompt pour récevoir les données nécessaires.
Pour calculer le BMI utilisez la formule suivante: poids / (hauteur /100 * hauteur / 100).
Ecrivez une construction `if` pour trouver le résultat:
Si l'indice est inférieur à 18.5, le résultat est 'considered underweight';
Si l'indice est égal ou superieur à 18.5 mais égal ou inférieur à 25, le résultat est 'a healthy weight';
Si l'indice est superieur à 25, le résultat est 'considered underweight';

Loggez le résultat: 'Your BMI is (insert bmi value here). It is (insert the result here). This test is not the most reliable, but if you are concerned about the result, check it with your doctor.'

## Reading time

