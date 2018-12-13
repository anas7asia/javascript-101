# Drag & Drop

+ [MDN > Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API )
+ [w3school > Drag and Drop API](https://www.w3schools.com/Html/html5_draganddrop.asp)

// 1. Simply drag one thing to another

---

Créez une question de quizz avec l'API de Drag & Drop.

![IT Quiz](https://i.ibb.co/D8dTWwH/drag-n-drop-demo.gif)

Vous avez l'objet de languages suivant:

```js
const LANGS = [
  { id: 1, name: 'HTML', correct: true },
  { id: 2, name: 'CSS', correct: true },
  { id: 3, name: 'JS', correct: true },
  { id: 4, name: 'Java' },
  { id: 5, name: 'Python' },
  { id: 6, name: 'Swift' },
];
```

Créez dynamiquement la liste de languages sur le plateau d'options. Toutes les options sont *draggable*s. Utilisez les `id` dynamiques.

Les plateaux d'options et de réponses sont *droppable*s.
<!-- On est en mésure d'mettre un élément draggable sur le plateau de réponses et l'emmener dans la liste d'options. -->

A chaque déplacement d'un language mettez à jour le compteur des éléments.

Le bouton de soumission est inactive s'il y a plus ou moins de 3 éléments.

A la soumission vérifiez si 3 réponses sont corrèctes et changez l'état du plateau de réponses. Si la réponse est corrècte, passez-le en vert, sinon en rouge. Si vous redeplacez les languages, donner la couleur initiale.



