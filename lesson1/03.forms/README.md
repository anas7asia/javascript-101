# Géstion de formulaires

+ [MDN > Form tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
+ [MDN > Form validation](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Form_validation)
+ [MDN > Your first HTML form](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Your_first_HTML_form)
+ [MDN > HTML Forms](https://www.w3schools.com/html/html_forms.asp)
+ [JavaScript.info > Forms](http://javascript.info/form-elements)
+ [JavaScript.info > focus/blur](http://javascript.info/focus-blur)
+ [JavaScript.info > Form events](http://javascript.info/forms-submit) 

1. Créez un champ de texte. 
2. Quand la page est entièrement [chargée](https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload), appelez une fonction qui fait concentrer sur ce champ. 
3. Ecrivez du texte dedans. 
4. Quand le champ sera deconcentré, loggez le texte écrit.

---

![Password](http://www.commitstrip.com/wp-content/uploads/2014/01/Strips-Mot-de-passe-650-final.jpg)

Créez un formulaire de connexion qui comprend deux champs: email et mot de passe.
Quand ce formulaire est [soumis](https://developer.mozilla.org/en-US/docs/Web/Events/submit), vérifez que:
1. Email est saisi 
2. Email est [valide](https://stackoverflow.com/questions/46155/how-to-validate-an-email-address-in-javascript)
3. Mot de passe est saisi
4. Mot de passe est plus long que 8 symboles.

Si tous les champs du formulaire sont vides ajoutez l'attribut `disabled` au bouton du type `submit`.

Quand le formulaire est soumis, vérifiez que tous les conditions sont remplis, si oui loggez 'Welcome!', sinon affichez les erreurs et demandez de re-saisir les champs.

> Attention à la [propagation d'évènements](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events#Event_bubbling_and_capture), n'oubliez pas d'utiliser la méthode [preventDefault](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault) de votre évènement `submit`

---

Créez un formulaire d'inscription d'un utilisateur sur votre site qui comprend les champs suivants:

+ sexe (boutons radio) - champs obligatoire, accepte les valeurs 'M' (male) ou 'F' (female)
+ nom (input) - champs obligatoire
+ prénom (input) - champs obligatoire
+ email (input) - obligatoire, doit être un email valide 
+ mot de passe (input) - obligatoire, plus long que 8 symboles
+ adresse (textarea) - obligatoire
+ condition d'utilisation (checkbox) - obligatoire, doit avoir le valeur `true`

Si un de champs est concentré et ensuite deconcentré, passez la couleur de sa bordure en rouge.
Si l'information est saisie dans un champ est invalide et ce champ est deconcentré, passez la couleur de sa bordure en rouge et montrer la .
Si tous les champs du formulaire sont vides ajoutez l'attribut `disabled` au bouton du type `submit`.
Quand le formulaire est soumis, vérifiez que tous les champs sont valides:
+ Si non, passez la couleur de bordure en rouge de tous les champs invalides et mettez l'erreur sous chaque champ.
+ Si tous les champs sont valides, loggez 'Welcome!'.

Vous pouvez utiliser [Bootstrap](https://getbootstrap.com/docs/4.1/components/forms/) ou un autre framework pour donner des styles à votre formulaire.

## Aller plus loin

Créez un calculateur du prix de bonbons magiques 🔮
[Première partie](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset) du formulaire est l'information de l'utilisateur qui effectue la commande: 
+ nom (obligatoire)
+ nom d'hibou (obligatoire)

Deuxìeme partie (aussi un fieldset) est la liste de produits. Un produit comprend le nom, le prix et la quantité (`input[type=number]`).

![Magic Price Calculator](https://i.ibb.co/b5N6Cg5/Magic-price-calculator.png)

Créez la liste de bonbons dynamiquement avec JavaScript (pas de magie pour ça).
Quantité des bonbons ne peut pas être inférieur à 0.
Utilisateur doit commander au moins 1 produit.
A chaque changement de quantité, montrez la somme totale (en sickles bien sûr).
Si la quantité de tous les produits est 0, ajoutez l'attribut `disabled` au bouton du type `submit`.

```js
const candies = [
  { label: 'Chocolate Frog', price: 6 },
  { label: 'Sherbet lemon', price: 12 },
  { label: 'Fizzing Whizzbees', price: 11 },
  { label: 'Acid Pops', price: 4 },
  { label: 'Skiving Snackbox', price: 7 },
  { label: 'Pumpkin Pasty', price: 15 },
  { label: 'Jelly Slug', price: 9.5 }
]
```

## Reading List

+ [Why should I use Form Elements?](https://medium.com/@hanna.soloman/why-should-i-use-form-elements-a7baa8f8306)