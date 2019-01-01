# Drag & Drop

+ [MDN > Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API )
+ [w3school > Drag and Drop API](https://www.w3schools.com/Html/html5_draganddrop.asp)

Créer une API qui permet de mettre un div dans un autre div.

---

![Drag&Drop images](https://i.ibb.co/xCsGFwk/drag-n-drop-images.gif)

Créez une API de dépôt d'une ou plusieurs images pour pouvoir ensuite les télécharger sur un serveur.
Créez un `<div>`, faites glisser une image, [affichez son aperçu](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/FileReader) et son nom.

Le poids maximum d'une image ne doit pas depasser 300Ko.
Les formats acceptés sont jpeg, png et svg.

Pour aller plus loin:
Les images avec le même nom ne peuvent pas être uploadés plusieurs fois.
Ajoutez une restriction d'upload: le serveur ne doit pas accepter plus de 10 images d'un coup.

---

Créez un quiz avec l'API de Drag & Drop.

![IT Quiz](https://i.ibb.co/D8dTWwH/drag-n-drop-demo.gif)


```js
const LANGS = [
  { id: 1, name: 'HTML', correct: true },
  { id: 2, name: 'CSS', correct: true },
  { id: 3, name: 'JS', correct: true },
  { id: 4, name: 'Java', correct: false },
  { id: 5, name: 'Python', correct: false },
  { id: 6, name: 'Swift', correct: false }
];
```

Créez *dynamiquement* la liste de langage de quiz.

Il doit être possible d'ajouter ou de retirer un langage avant la validation de la réponse.

A chaque déplacement d'un langage mettez à jour le compteur des langages choisis.

Le bouton de soumission est inactif si le nombre de langages choisis n'est pas égale à 3.

A la soumission de la réponse vérifiez si les 3 réponses sont correctes. Si la réponse est correcte, passez la couleur du fond de la zone de 'drop' en vert, sinon en rouge.



