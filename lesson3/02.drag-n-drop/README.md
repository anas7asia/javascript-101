# Drag & Drop

+ [MDN > Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API )
+ [w3school > Drag and Drop API](https://www.w3schools.com/Html/html5_draganddrop.asp)

Créer une API qui permet de mettre un div dans un autre div.

---

Utilisez le HTML et le JS suivants pour pouvoir glisser et déposer les images et afficher leurs apérçus.

Dans le fichier JavaScript:
1. Sur les lignes 8-11 utilisez les vrais noms des événements de Drag&Drop au lieu de `'USE_CORRECT_EVENT_HERE'`.
2. Ecrivez un commentaire pour **chaque ligne de code** afin d'éxpliquer comment elle fonctionne et pourquoi nous en avons besoin.

<details>
  <summary>HTML</summary>

  ```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <title>Drag & Drop Images</title>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
  <style>
    h1 {
      margin-top: 4rem;
    }

    .drop {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: 2rem;
      width: 100%;
      height: 4rem;
      border: 4px dashed #ccdbdc;
      border-radius: 8px;
    }

    .js-is-dragged-over {
      border-color: #007ea7;
    }

    .file-list {
      margin-top: 1.5rem;
    }

    .file-list-item {
      display: flex;
      align-items: center;
    }

    .file-list-item-preview {
      margin-right: .7rem;
      width: 2rem;
      height: 2rem;
    }

    .file-list-item-error {
      margin-left: .6rem;
      font-size: .8rem;
      font-style: italic;
    }

    p {
      margin-bottom: 0;
    }
  </style>
</head>
<body>

  <div class="container">
    <h1>Drag and Drop</h3>

    <div id="js-drop-to" class="drop">
      Drag your images here
    </div>
    
    <ul id="js-file-list" class="list-group file-list"></ul>
  </div>
  
  <script src="./drag-n-drop.js"></script>
</body>
</html>

  ```
</details>


<details>
<summary>JavaScript</summary>

```js
'use strict';

const ACCEPTED_FORMATS = ['image/jpeg', 'image/png', 'image/svg'];
const MAX_IMG_SIZE = 300 * 1024; // 30 Kb
const dropZone = document.querySelector('#js-drop-to');
const filesList = document.querySelector('#js-file-list');

dropZone.addEventListener('USE_CORRECT_EVENT_HERE', (e) => onDragOver(e));
dropZone.addEventListener('USE_CORRECT_EVENT_HERE', (e) => onDrop(e));
dropZone.addEventListener('USE_CORRECT_EVENT_HERE', () => changeDropZoneState(true));
dropZone.addEventListener('USE_CORRECT_EVENT_HERE', () => changeDropZoneState(false));

function onDragOver(event) {
  event.stopPropagation();
  event.preventDefault();
}

function onDrop(e) {
  e.stopPropagation();
  e.preventDefault();
  filesList.innerHTML = '';
  const filesUploaded = Array.from(e.dataTransfer.files);
  filesUploaded.forEach((file, index) => handleUploadedFile(file, index));
  changeDropZoneState(false);
}

function changeDropZoneState(isDragging) {
  isDragging ? 
    dropZone.classList.add('js-is-dragged-over') :
    dropZone.classList.remove('js-is-dragged-over');
}

function handleUploadedFile(file, index) {
  const error = getUploadError(file);
  error ?
    console.warn(`"${file.name}" Upload Error: ${error}`) :
    filesList.appendChild(createListEl(file, index));
}

function createListEl(file, index) {
  const el = document.createElement('li');
  el.setAttribute('id', 'file-list-item-'+index);
  el.className = 'list-group-item file-list-item';

  // add image
  const elPreview = document.createElement('img');
  elPreview.classList.add('file-list-item-preview');
  el.appendChild(elPreview);
  renderImage(file, 'file-list-item-'+index);

  // add name
  const elName = document.createElement('p');
  elName.classList.add('file-list-item-name');
  elName.innerText = file.name;
  el.appendChild(elName);

  return el;
}

function renderImage(file, elId) {
  const reader = new FileReader();
  reader.onload = (e) => {
    const img = document.querySelector(`#${elId} img`);
    img.setAttribute('src', e.target.result);
  }
  reader.readAsDataURL(file);
}

function getUploadError(file) {
  if (file.size > MAX_IMG_SIZE) {
    return 'Your image is too big';
  } else if (!ACCEPTED_FORMATS.includes(file.type)) {
    return 'Image of this format is not accepted';
  } else {
    return;
  }
}
```
</details>


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



