# Effets jQuery

+ [jQuery > Effects](https://api.jquery.com/category/effects/)
+ [w3schools > Effects](https://www.w3schools.com/jquery/jquery_ref_effects.asp)

## Gérer la visiblité

### hide/show
```html
<div class="alert alert-primary" style="display: none;">
  Hide me!
  <button id="js-hide-alert">✕</button>
</div>

<button id="js-show-alert">Show alert</button>
```
Utilisez le HTML ci-dessus.
Affichez l'alerte si le bouton `#js-show-alert` est cliqué. Cachez-la si le bouton `#js-hide-alert` est cliqué.

---

```html
<form>
  <input type="radio" name="side" value="false">Sith
  <input type="radio" name="side" value="true">Jedi

  <div class="alert alert-danger" style="display: none;">Come to the Dark Side</div>
</form>
```
Utilisez le HTML ci-dessus.
Si le bouton radio 'Jedi' est sélectionné, montrez l'alerte. Si ce bouton n'est plus sélectionné, cachez-la.
(Utilisez la méthode `toggle` pour faire cela)

### slide

```html
<p id="js-slide-example-1">Quai de Chartrons 33000 Bordeaux</p>
<div class="js-slide-example-links" style="display: none;">
  <a href="#">Voir sur la carte</a>
  <a href="#">Directions</a>
</div>
```

Utilisez les méthodes `slideUp`, `slideDown` ou `slideToggle` pour afficher/cachee la bannière `.js-slide-example-links` sous le paragraphe `#js-slide-example-1` si celui-ci est cliqué.

![slideToggle](https://i.ibb.co/T43qPQt/slide-toggle.gif)

### fade

```html
<div class="alert alert-warning" style="display: none;">
  This alert will be hidden automatically in 3 secons!
</div>

<button id="js-show-disappearing-alert">Show alert</button>
```
Utilisez le HTML ci-dessus.
Cliquez sur le bouton pour que l'alerte aparesse avec l'animation fondu (fade in) en 400 millisecondes. 3 secondes après l'apparition, faites disparetre l'alerte en 600 millisecondes.

Utilisez les méthodes `fadeIn`, `fadeOut` et le principe de callback.

---

```html
<div id="js-div-1"></div>
<div id="js-div-2"></div>
<div id="js-div-3"></div>
<div id="js-div-4"></div>
```

Utilisez le HTML ci-dessus.
Après le rendu de la page tous les divs ont l'opacité de 30%. Quand un div est cliqué dessus, son opacité monte à 100%. Quand un autre div est cliqué, son opacité monte à 100% et l'opacité de tous les autres divs descend de nouveau à 30%.

Utilisez la méthode `fadeTo`

![Choose one div](https://i.ibb.co/NYhBZV1/choose-one-div.gif)


## Gérer l'animation
animate
  delay
  rotate

enchainer les méthodes

chain animations
stop animation
stop all animations



