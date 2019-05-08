# Effets jQuery

+ [jQuery > Effects](https://api.jquery.com/category/effects/)
+ [w3schools > Effects](https://www.w3schools.com/jquery/jquery_ref_effects.asp)

## Gérer la visiblité

### hide/show
```html
<div class="alert alert-primary" style="display: none;" id="js-alert">
  Hide me!
  <button id="js-hide-alert">✕</button>
</div>

<button class="btn btn-primary" id="js-show-alert">Show alert</button>
```
Utilisez le HTML ci-dessus.
Affichez l'alerte si le bouton `#js-show-alert` est cliqué. Cachez-la si le bouton `#js-hide-alert` est cliqué.

---

```html
<form>
  <input type="radio" name="side" value="false" id="js-sith">Sith
  <input type="radio" name="side" value="true" id="js-jedi">Jedi

  <div class="alert alert-danger" style="display: none;" id="js-jedi-alert">Come to the Dark Side</div>
</form>
```
Utilisez le HTML ci-dessus.
Si le bouton radio 'Jedi' est sélectionné, montrez l'alerte. Sinon cachez-la.
<!-- (Pour cela utilisez la méthode `toggle`) -->

### slide

```css
#js-slide-example-address {
  margin: 0;
  padding: 2rem;
  background-color:	#b9bdd4;
}

#js-slide-example-links {
  display: flex;
  padding: 1rem 2rem;
  background-color: #6e6f87;
  color: #fff;
}

#js-slide-example-links a {
  margin-right: 2rem;
  color: inherit;
}
```

```html
<p id="js-slide-example-address">Quai de Chartrons 33000 Bordeaux</p>
<div id="js-slide-example-links" style="display: none;">
  <a href="#">Voir sur la carte</a>
  <a href="#">Directions</a>
</div>
```

Utilisez les méthodes `slideUp`, `slideDown` ou `slideToggle` pour afficher/cacher la bannière `.js-slide-example-links` sous le paragraphe `#js-slide-example-1` si celui-ci est cliqué.

![slideToggle](https://i.ibb.co/T43qPQt/slide-toggle.gif)

### fade

```html
<div class="alert alert-warning" style="display: none;">
  This alert will be hidden automatically in 3 seconds!
</div>

<button id="js-show-disappearing-alert">Show alert</button>
```
Utilisez le HTML ci-dessus.

Cliquez sur le bouton pour que l'alerte aparesse avec l'animation fondu (fade in) en 400 millisecondes. 3 secondes après l'apparition, faites disparaître l'alerte en 600 millisecondes.

Utilisez les méthodes `fadeIn`, `fadeOut` et le principe de callback.

---

```html
<button class="btn btn-success" id="js-btn-fade-in">Fade In</button>
<button class="btn btn-danger" id="js-btn-fade-out">Fade Out</button>
<div style="background:#2E9AFE; width:200px; height:200px; margin-top:30px;" id="js-div-fade-in-out"></div>
```

Au clique sur le bouton avec l'id `js-btn-fade-in` faites apparaître le div avec l'animation fondu (fade in).
Au clique sur le bouton avec l'id `js-btn-fade-out` faites disparaître le div avec l'animation fondu (fade out).

---

```html
<div id="js-div-1"></div>
<div id="js-div-2"></div>
<div id="js-div-3"></div>
<div id="js-div-4"></div>
```

Utilisez le HTML ci-dessus.

Après le rendu de la page tous les `<div>` ont l'opacité de 30%. Quand un `<div>` est cliqué, son opacité monte à 100%. Quand un autre `<div>` est cliqué, son opacité monte à 100% et l'opacité de tous les autres divs descend de nouveau à 30%.

Utilisez la méthode `fadeTo`.

![Choose one div](https://i.ibb.co/NYhBZV1/choose-one-div.gif)

---
```css
#js-animation-1 {
  position: relative;
  width: 100px;
  height: 100px;
  background-color: aqua;
  border: 0 solid red;
}
```

```html
<p id="js-p-fade-to">Cliquez sur ce paragraphe pour baisser son opacité à 10%.</p>
```

Au clique sur le paragraphe avec l'id `js-p-fade-to` faites baisser son opacité jusque 10%.


## Gérer l'animation

```html
<div id="js-animation-1"></div>
```

Utilisez le HTML ci-dessus.

Appliquez une animation au div `#js-animation-1`: ce `<div>` se deplace à 300px de gauche à droit en 700 millisecondes 3 secondes après la fin du rendu de la page. Utilisez les méthodes `delay` et `animate`.

---

Créez un `<div>` de taille `5rem` sur `5rem` et un bouton qui déclenche les animations suivantes :
1. La hauteur et la longeur du div s'elargissent jusque 8rem en 500 millisecondes.
2. Ensuite le div se deplace à `10rem` vers la droite et 5rem vers le bas par rapport à sa position actuelle en 700 millisecondes.
3. Ensuite l'opacité du div descend à 50% en 300 millisecondes.
4. Ensuite la largeur de la bordure du div passe de 0 à 5 pixels en 400 milisecondes.

Créez un autre bouton qui arrete l'animation en cours et annule toutes les autres animations.

![Chained animation](https://i.ibb.co/Rj0GwhQ/chained-animation.gif) ![Chained animation stopped](https://i.ibb.co/XkGQ0s3/chained-animation-stopped.gif)

---

```html
<div id="js-animate-div" style="background:#98bf21;height:100px;width:100px"></div>
<button class="btn btn-success" id="js-animate-div-btn">Animate!</button>
```

Au clique sur le bouton appliquez l'animation au `<div>` en changeant sa largeur et sa hauteur à `200px`.

---

Voici quatre `<div>`.

```html
<div class="animated" id="js-animated-1"></div>
<div class="animated" id="js-animated-2"></div>
<div class="animated" id="js-animated-3"></div>
<div class="animated" id="js-animated-4"></div>
```

Ce code JavaScript applique l'animation aux trois `<div>` choisis aléatoirement.

```js
const randomDivsAnimation = {

  init: () => {
    this.config = {
      items: $('.animated'),
    };
    this.setup();
  },

  setup: () => {
    const randomNums = this.getArrayOfRandomNums(this.config.items.length);
    // animate divs
    const divsToAnimate = this.getDivsToAnimate(randomNums);
    this.animateDivs(divsToAnimate);
  },

  animateDivs: (divsToAnimate) => {
    $(divsToAnimate).slideToggle('slow', this.animateDivs); // ATTENTION: recursion here
  },

  getDivsToAnimate: (randomNums) => {
    return randomNums.sort().reduce((acc, currVal, currIndex, array) => {
      acc += `#js-animated-${currVal}${currIndex !== array.length - 1 ? ',' : ''}`;
      return acc 
    }, '');
  },

  getRandomNumber: max => Math.floor(Math.random() * max + 1),

  getArrayOfRandomNums: (itemsCount) => {
    const nums = [];
    // itemsCount - 1 to make sure that final array is one item less than all of the divs in HTML
    while (nums.length < itemsCount - 1) {
      const randomNum = this.getRandomNumber(itemsCount);
      if (!nums.includes(randomNum)) {
        nums.push(randomNum);
      }
    }
    return nums;
  },
};

$('document').ready(() => {
  randomDivsAnimation.init();

  // HERE: select divs that are animated
});
```

Créez une fonction qui sélectionne tous les divs animés et change leur couleur de fond.

![4 divs animés](https://i.ibb.co/fnHPWLH/4-animated-divs.gif)