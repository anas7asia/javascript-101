# Evénements jQuery

+ [jQuery > Events](https://api.jquery.com/category/events/)
+ [w3schools > Events](https://www.w3schools.com/jquery/jquery_events.asp)

## Evénements de souris

Créez un bouton. Si ce bouton est cliqué, loggez dans la console `'Clicked!'`.
Si ce bouton est cliqué plus de 5 fois, enlevez son écouteur d'événement 'click'.

---
Créez un div bleu. Si on le survole, il passe en vert. Si on sort le curseur du div, il redevient bleu. 
Utilisez les méthodes `mouseenter`, `mouseleave` ou `hover`.

---

Desactivez le comportement par defaut du click du bouton droit de la souris sur toute la page. Si le bouton a été cliqué, vérifiez si le comportement par defaut est desactivé. Dans ce cas-là, loggez dans la console `'You shall not pass'`

![Clicks not allowed](http://www.commitstrip.com/wp-content/uploads/2016/06/Strip-Les-codeurs-et-les-images-650-final-1.jpg)

## Evénements de formulaire

```html
<form id="js-form">
  <input type="radio" name="pettype" value="cat" id="js-radio-cat">Cat
  <input type="radio" name="pettype" value="dog" id="js-radio-dog">Dog

  <input type="text" name="petname" placeholder="Your pet name" id="js-input">

  <input type="submit" value="Submit" id="js-submit">
</form>
```

Si le champ de saisie `#js-input` est mis en avant passez la couleur de sa bordure en bleu.
Si ce champ n'est plus mis en avant et reste vide, passez la couleur de sa bordure en rouge.

---

Associez *d'un coup* les trois événements: 'keyup', 'keydown', 'keypress' - au champ de saisie. Si l'un d'eux est déclenché, loggez dans la console le code de la touche appuyée.

---

Si le bouton radio 'Cat' a été choisi, loggez dans la console `'Go cats!'`
Si le bouton radio 'Dog' a été choisi, loggez dans la console `'Go dogs!'`

---

A la soumission du formulaire, récupérez les valeurs de tous ces champs et loggez-les dans la console.

## Reading List

+ [DOM Manipulation fun with jQuery](https://medium.com/truthy-or-falsy/dom-manipulation-fun-with-jquery-cc9ddeff1e16)
+ [How to correctly use preventDefault(), stopPropagation(), or return false; on events](https://medium.com/@jacobwarduk/how-to-correctly-use-preventdefault-stoppropagation-or-return-false-on-events-6c4e3f31aedb)

