# Evénements 

+ [MDN > List of all the events](https://developer.mozilla.org/en-US/docs/Web/Events)
+ [w3school > JavaScript Events](https://www.w3schools.com/js/js_events.asp)
+ [JavaScript.info > Browser Events](http://javascript.info/introduction-browser-events)

> Installez le framework CSS [Bootstrap](https://getbootstrap.com/docs/4.3/getting-started/introduction/) sur votre page: `<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">`.

## Evénements de souris

<!-- Créez un bouton dans votre HTML. Associez-lui un événement `onclick` avec un attribut directement dans HTML. Si le bouton est cliqué, loggez 'Clicked!'.

Créez un bouton dans votre HTML. Avec JavaScript associez à la propriété `onclick` à une fonction qui logge 'Clicked!' si le bouton est cliqué. -->
#### Click me

```html
<button class="btn btn-primary" id="js-click">Click me!</button>
```

Créez un bouton dans votre HTML avec le texte `'Click me'`. 
Ajoutez-lui un écouteur d'événements côté JavaScript. 
Si le bouton est cliqué, logguez dans la console 'Clicked!' et [l'événement](https://developer.mozilla.org/en-US/docs/Web/API/Event) passé à la fonction de rappel, ensuite changez son texte à `'Clicked'`.

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/bPSrRwR/01-click-me.gif)
</details>

---

<details>
  <summary>HTML</summary>

  ```html
  <button class="btn btn-primary mt-5" id="js-show-alert">Show alert</button>
  <div class="alert alert-primary mt-5" style="display: none;" id="js-alert">
    Hide me!
    <button id="js-hide-alert">✕</button>
  </div>
  ```
</details>

Utilisez le HTML ci-dessus. Affichez l'alerte si le bouton `#js-show-alert` est cliqué. Cachez-la si le bouton `#js-hide-alert` est cliqué.

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/cJBJGTD/04-show-hide-alert.gif)
</details>

---

#### Changer la couleur au click

```html
<button class="btn btn-secondary" id="js-change-color">I will change my color</button>
```

Créez un bouton gris. S'il est cliqué, passez sa couleur en vert. S'il est cliqué à nouveau, repassez sa couleur en gris. Gérez les couleurs côté JavaScript.

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/jy7Wr83/02-change-color.gif)
</details>

---

#### Infinite rotation

<details>
  <summary>HTML & CSS</summary>

  ```html
  <div id="js-rotate"></div>
  ```

  ```css
  #js-rotate {
    display: block;
    margin-top: 50px;
    width: 200px;
    height: 200px;
    background-image: linear-gradient(to right top, #d16ba5, #c777b9, #ba83ca, #aa8fd8, #9a9ae1, #8aa7ec, #79b3f4, #69bff8, #52cffe, #41dfff, #46eefa, #5ffbf1);
    transition: .3s all ease;
  }
  ```
</details>

Copiez-collez le HTML et le CSS ci-dessous.

Si le div est cliqué deux fois d'affilé, tournez-le à 45 degrés de plus de sa position precedante. 

Propriété CSS qui fait tourner les éléments :
```css
transform: rotate(45deg);
```

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/6R3sy89/03-rotate.gif)
</details>

---

#### Curseur in and out

<details>
  <summary>HTML & CSS</summary>

  ```html
  <div class="flags">
    <div class="flag flag-icon flag-icon-fr" id="js-flag-fr"></div>
    <div class="flag flag-icon flag-icon-es" id="js-flag-es"></div>
    <div class="flag flag-icon flag-icon-de" id="js-flag-de"></div>
  </div>
  <div id="js-iso-greeting"></div>
  ```

  ```css
  .flags {
    margin-top: 50px;
    display: flex;
  }

  .flag {
    margin-right: 30px;
    width: 100px;
    height: 78px;
    background-size: contain;
  }

  #js-iso-greeting {
    margin-top: 20px;
    font-size: 1.2rem;
    font-weight: bold;
  }
  ```
</details>

Quand un drapeau est survolé, le nom du pays apparaît, quand le curseur sort du drapeau le pays disparaît.
> La bibliothèque des drapeaux en format svg `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.3.0/css/flag-icon.min.css">`

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/LZ9FDZ8/05-flags.gif)
</details>

---

```js
const colors = ['#ffc7e9', '#f8f0e8', '#b6ddd8', '#2e326f', '#efd8ff'];
```

Au clique sur la page web changez sa couleur du fond. Alternez avec les couleurs présentes dans le tableau. Quand vous atteignez la fin du tableau, il faut repartir au debut du tableau.

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/qM0565d/07-body-bg-color.gif)
</details>

---

Créez un bouton, associez-lui un événement `click`. Si ce bouton a été cliqué trois fois, enlevez l'écouteur d'événement.

---

Créez un bouton bleu. Il devient violet quand une touche de la souris est [appuyée](https://developer.mozilla.org/en-US/docs/Web/Events/mousedown) sur le bouton. Il devient rouge quand la touche de la souris est [relâché](https://developer.mozilla.org/en-US/docs/Web/Events/mouseup).

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

<details>
  <summary>HTML & CSS</summary>

  ```html
  <div id="js-square"></div>
  ```

  ```css
  * {
    margin: 0;
    padding: 0;
  }

  body {
    position: relative;
    background-color:#fff;
    background-image: linear-gradient(90deg, rgba(134,168,231,.5) 50%, transparent 50%),
    linear-gradient(rgba(95,251,241,.5) 50%, transparent 50%);
    background-size: 50px 50px;
  }

  #js-square {
    position: absolute;
    top: 0;
    left: 0;
    width: 25px;
    height: 25px;
    background-color: #D16BA5;
  }
  ```
</details>

Créez un champ de la taille de la fenêtre de votre navigateur. Dedans créez un carré qui bouge de 25px à droite/gauche/en-haut/en-bàs si on appuie sur les boutons fléchés. 

**BONUS:** Ce carré ne doit pas dépasser les bords de la fenêtre.

```js
const KEY_CODES = {
  LEFT_ARROW: 37,
  RIGHT_ARROW: 39,
  UP_ARROW:	38,
  DOWN_ARROW:	40
}
```

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/Ttyw65k/08-move-square.gif)
</details>

---

Créez un champ de saisie de texte. A chaque fois que l'on tape une lettre dedans, loggez le contenu du champ. 


## Evénements de vue du document

<details>
  <summary>HTML & CSS</summary>

  ```html
  <div class="window-info">
    <span id="js-window-width"></span>
    ✕
    <span id="js-window-height"></span>
  </div>
  ```

  ```css
  body {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
  }

  .window-info {
    font-size: 2rem;
    font-family: Arial, Helvetica, sans-serif;
  }
  ```
</details>

Affichez la largeur (`window.innerWidth`) et l'hauteur (`window.innerHeight`) de la fênetre de votre navigateur.
Si elle est [redimensionnée](https://developer.mozilla.org/en-US/docs/Web/Events/resize), mettez à jour ces valeurs.

<details>
<summary>Le résultat</summary>

![Result](https://i.ibb.co/jz2XrGq/06-resize-window.gif)
</details>

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