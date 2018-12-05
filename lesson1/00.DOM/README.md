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

```html
<div>
  <p class="main-paragraph">Paragraph 1</p>
</div>
<div>
  <p class="secondary-paragraph">Paragraph 2</p>
</div>
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

## Supprimer un node

