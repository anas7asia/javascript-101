# Drag & Drop

+ [MDN > Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API )
+ [w3school > Drag and Drop API](https://www.w3schools.com/Html/html5_draganddrop.asp)

Créer un API qui permet de mettre un div dans un autre div.

---

![Drag&Drop images](https://i.ibb.co/xCsGFwk/drag-n-drop-images.gif)

Créez un API de dépôt d'un ou plusieurs images pour ensuite les télécharger sur le serveur.
Créez un div, faites glisser un image, [affichez son aperçu](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/FileReader) et son nom.

Le poids maximum du'image ne doit pas depasser 300Ko.
Les formats acceptés d'un image sont jpeg, png et svg.

Pour aller plus loin:
Vérifiez que les images avec le même nom ne peuvent pas être uploadés plusieurs fois.
Ajoutez la restriction d'uploader plus de 10 images.

---

Créez un quiz avec l'API de Drag & Drop.

![IT Quiz](https://i.ibb.co/D8dTWwH/drag-n-drop-demo.gif)


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

Créez *dynamiquement* la liste de choix de quiz.
C'est possible de mettre et enlever les choix avant la validation de la réponse.
A chaque déplacement d'un choix mettez à jour le compteur des choix.
Le bouton de soumission est inactive s'il y a plus ou moins de 3 choix.

A la soumission de la réponse vérifiez si 3 réponses sont corrèctes. Si la réponse est corrècte, passez sa couleur du fond en vert, sinon en rouge.



