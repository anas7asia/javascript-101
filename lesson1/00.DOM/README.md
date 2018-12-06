# Document Object Model

+ [w3school](https://www.w3schools.com/js/js_htmldom_eventlistener.asp)
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
+ [JavaScript.info](http://javascript.info/dom-nodes)


## Trouver un node

Utilisez: `getElementById`, `getElementsByClassName`, `getElementsByTagName`, `querySelector`, `querySelectorAll`

+ Trouvez toutes les balises `div` du document. Loggez le deuxième élément s'il est présent.
+ Trouvez toutes les balises `p` avec la classe 'my-paragraph' du document. Loggez le premier élément s'il est présent.
+ Trouvez la balise `span` avec l'id 'js-unique-el'. Loggez-là.
+ Trouvez toutes les balises `p` qui se trouvent dedans `div`. 
+ Trouvez toutes les balises `p` qui ne se trouvent pas dedans `div`. 
+ Trouvez toutes les balises `span` qui sont précédéss par un `div`. 

```html
<div>
  <p class="main-paragraph">Paragraph 1</p>
</div>
<div>
  <p class="secondary-paragraph">Paragraph 2</p>
</div>
<span></span>
<div>
  <p class="secondary-paragraph">Paragraph 3</p>
</div>
<p class="secondary-paragraph">Paragraph 3</p>
<span id="js-unique-el"></span>
```


## Inspécter un node

Utilisez la console pour regarder toutes les propriétés et méthodes associés à un node.
Console > Séléctionner un élément > 'Elements' > 'Properties'
// TODO: add an image


## Modifier un node

Ajoutez le texte 'I am the first paragraphe' au premier paragraph du document.
Ajoutez le HTML `<span>Hello</span>` au deuxième paragraphe du document.
Modifiez les attributs `width` à 50% et `height` à 'auto' de l'image.
Ajoutez un attribut `alt` à l'image.
Donnez la couleur 'blue' au premier paragraphe et la taille de police '1.5rem'.

```html
<p class="first-p"></p>
<p class="second-p"></p>
<img src="path/to/image" width="10px" height="10px">

```

## Créez un node


## Supprimer un node

