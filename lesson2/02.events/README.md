# Evénements 

+ [MDN > List of all the events](https://developer.mozilla.org/en-US/docs/Web/Events)
+ [w3school > JavaScript Events](https://www.w3schools.com/js/js_events.asp)
+ [JavaScript.info > Browser Events](http://javascript.info/introduction-browser-events)

## Evénements de souris

<!-- Créez un bouton dans votre HTML. Associez-lui un événement `onclick` avec un attribut directement dans HTML. Si le bouton est cliqué, loggez 'Clicked!'.

Créez un bouton dans votre HTML. Avec JavaScript associez à la propriété `onclick` à une fonction qui logge 'Clicked!' si le bouton est cliqué. -->

Créez un bouton dans votre HTML. Ajoutez-lui un écouteur d'événements côté JavaScript. Si le bouton est cliqué, loggez 'Clicked!'. Loggez également [l'événement](https://developer.mozilla.org/en-US/docs/Web/API/Event) passé et explorez ces propriétés.

---

Créez un bouton gris. S'il est cliqué, passez sa couleur en vert. S'il est cliqué à nouveau, repassez sa couleur en gris. Gérez les couleurs côté JavaScript.

Faites la même chose en utilisant des classes css.

---

Si le div a été cliqué deux fois d'affilé, loggez 'Double click event is catched'. 

---

Créez un div rose. Si on le survole, il passe en rouge. Si on sort le curseur du div, il redevient rose. 

---

Créez un bouton bleu. Il devient violet quand une touche de la souris est [appuyée](https://developer.mozilla.org/en-US/docs/Web/Events/mousedown) sur le bouton. Il devient rouge quand la touche de la souris est [relâché](https://developer.mozilla.org/en-US/docs/Web/Events/mouseup).

---

Créez un bouton, associez-lui un événement `click`. Si ce bouton a été cliqué trois fois, enlevez l'écouteur d'événement.

---

Créez 20 boutons (côté JavaScript bien sûr!). Chaque bouton loggue 'Button number $son_numéro_de_1_à_20 has been clicked' s'il a été cliqué. 

<!-- ---

Créez un [menu déroulant](https://getbootstrap.com/docs/4.0/components/dropdowns/#single-button-dropdowns) avec HTML, CSS et JavaScript. -->

## Cible d'événement

Ajoutez le même événement à ces deux liens. Trouvez quel lien a été cliqué en fonction de la propriété `target` de l'`Event`.

```html
<div>
  <a href="#" id="js-link-1">Link 1</a>
  <a href="#" id="js-link-2">Link 1</a>
</div>
```

## Evènements de clavier

Créez un champ de la taille de la fenêtre de votre navigateur. Dedans créez un carré qui bouge de 20px à droite/gauche/en-haut/en-bàs si on appuie sur les boutons fléchés. Ce carré ne peut pas dépasser les bords du champ.

```js
const KEY_CODES = {
  LEFT_ARROW: 37,
  RIGHT_ARROW: 39,
  UP_ARROW:	38,
  DOWN_ARROW:	40
}
```

---

Créez un champ de saisie de texte. A chaque fois que l'on tape une lettre dedans, loggez le contenu du champ. 


## Evénements de vue du document

Affichez la largeur et l'hauteur de la fênetre de votre navigateur.
Si elle est [redimensionnée](https://developer.mozilla.org/en-US/docs/Web/Events/resize), mettez à jour ces valeurs.

```html
<p>Viewport width: <span><!-- put your value here --></span></p>
<p>Viewport height: <span><!-- put your value here --></span></p>
```

---

Créez une page HTML. Sur la page placez un div qui changera sa couleur si on fait défiler la page. Votre page doit avoir assez de contenu pour pouvoir déclencher l'événement de [scroll](https://developer.mozilla.org/en-US/docs/Web/Events/scroll).


## Pour aller plus loin

Observez les liens de partage à gauche sur la page d'[article Medium](https://codeburst.io/top-javascript-vscode-extensions-for-faster-development-c687c39596f5) qui apparessent quand on descends la vue. Recréez le même comportèment.
Les liens de partage en `position: fixed;` apparessent si on a descendu à 200 pixels. Ils disparessent à 500 pixels du bas de page.

---

Sur la page créez un div avec des boutons (ou des liens). Si le div ou les boutons sont cliqués, marquez 'Clicked inside', si un endroit en dehors du div est cliqué, marquez 'Clicked outside'.

![Click outside](https://i.ibb.co/6tNfRxM/click-outside.gif)

<!-- ---

Creéz un système d'affichage de contenu de type ["accordeon"](https://getbootstrap.com/docs/4.1/components/collapse/#accordion-example) avec JavaScript. -->


## Reading List
+ [Eloquent JavaScript > Events](https://eloquentjavascript.net/15_event.html)
+ [JavaScript.info > Events bubbling and capture](https://javascript.info/bubbling-and-capturing)
+ [A simplified explanation of event propagation in JavaScript.](https://medium.freecodecamp.org/a-simplified-explanation-of-event-propagation-in-javascript-f9de7961a06e)