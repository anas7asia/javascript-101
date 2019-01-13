# Manipulation de DOM avec jQuery

+ [jQuery > Manipulation](https://api.jquery.com/category/manipulation/)
+ [w3schools > jQuery - Get Content and Attributes](https://www.w3schools.com/jquery/jquery_dom_get.asp)
+ [w3schools > jQuery - Set Content and Attributes](https://www.w3schools.com/jquery/jquery_dom_set.asp)
+ [w3schools > jQuery - Add Elements](https://www.w3schools.com/jquery/jquery_dom_add.asp)
+ [w3schools > jQuery - Remove Elements](https://www.w3schools.com/jquery/jquery_dom_remove.asp)
+ [w3schools > jQuery - Get and Set CSS Classes](https://www.w3schools.com/jquery/jquery_css_classes.asp)
+ [w3schools > jQuery - css() Method](https://www.w3schools.com/jquery/jquery_css.asp)

## Récupérer/modifier

Utilisez les méthodes `text`, `html`, `val`, `attr` pour travailler avec le HTML suivant.

```html
<h1>Some title</h1>

<article id="js-article">
  <h2>Article title</h2>
  <p>Article content</p>
</article>

<input type="text" id="js-search" placeholder="Search something..." value="Poodles">
```

Récupérez et loggez dans la console le contenu du titre de la page.

---
Changez le contenu du titre de la page à `'My page title'`.

---
Récupérez et loggez dans la console le HTML de l'article.

---
Changez le contenu de l'article à 

```html
<h2>This is my article.</h2>
<p>This is my article's content.</p>
<a href="https://example.com">Read more</a>
```

---
Récupérez et loggez dans la console la valeur du champ de saisie avec l'id `js-search`.

---
Changez la valeur du champ de saisie à `'Beagles'`

---
Récupérez et loggez dans la console la valeur du placeholder du champ de saisie.

---
Changez la valeur du placeholder du champ de saisie à `'Search'`

---
Ajoutez un attribut `data-article-id` avec la valeur `1` à l'article avec l'id `js-article`. Pour en savoir plus sur les attributs de données: [https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes).

---
Récupérez et loggez dans la console la valeur de l'attribut `data-article-id` que vous venez d'ajouter.

## Insérer/supprimer du contenu

Utilisez les méthodes `append`, `prepend`, `before`, `after`, `remove`, `empty` pour travailler avec le HTML suivant.

```html
<article id="js-article-1"></article>
<article id="js-article-2">
  <h1>Cats are the weirdest-2</h1>
  <p>My cat would get on the kitchen counter and eat the plastic wrap on the loaf bread. Just the plastic, not the actual bread.</p>
</article>
```

Ajoutez une balise `<h1>` avec la valeur `'Cats are the weirdest'` dans l'article avec l'id `js-article-1`.

---

Ajoutez une balise `<div>` dans l'article avec l'id `js-article-1`.

---

Dans la balise `<div>` de l'article `#js-article-1` ajoutez un paragraphe avec la valeur `'He starts to look at me pleadingly, paces around, and meows insistently. He even climbs on top of the book and bites my wrists in protest.'`

---

Dans la balise `<div>` de l'article `#js-article-1` ajoutez un autre paragraphe avec la valeur `'I recently found out that my cat, Marv, hates it when I read aloud.'` *avant* le paragraphe ajouté précédement.

---

*Après* le premier paragraphe (entre les deux paragraphes) de l'article `js-article-1` ajoutez une [image](https://cdn.pixabay.com/photo/2018/03/28/16/23/cute-3269715__340.jpg).

---

*Avant* l'article `#js-article-1` ajoutez un autre article:

```html
<article id="js-article-3">
  <h1>Cats are the weirdest-3</h1>
  <p>My cat brought me two large potatoes in the middle of the night from the kitchen counter.</p>
</article
```
---
Supprimez le contenu de l'article `#js-article-2`.

---
Supprimez du DOM l'article `#js-article-2`.

## Manipuler le CSS

Utilisez les méthodes `addClass`, `removeClass`, `toggleClass`, `hasClass`, `css` pour travailler avec le HTML suivant.

```html
<div id="js-alert" class="alert">
  <p>Very important message</p>
</div>
<button id="js-btn" class="btn btn-secondary">Change alert state</button>
```

Ajoutez la classe `'alert-primary'` au `<div>`.

---
Supprimez la classe `'alert'` du `<div>`.
Supprimez la classe `'alert-primary'` du `<div>`.

---

Ajoutez *d'un coup* les classes `'alert'` et `'alert-warning'` au `<div>`.

---
Vérifiez si le `<div>` possède déjà la classe `'alert-warning'`. Si oui, supprimez-la.

---
En cliquant sur le bouton `#js-btn`, basculez la classe `'alert-success'`: premier clique ajoute la classe, deuxième clique l'enlève, troisième l'ajoute de nouveau, etc.

---
Récupérez et loggez dans la console la couleur du fond du bouton.

---
Passez la couleur du fond du bouton en `#71b8af`.

---
Changez *d'un coup* la couleur du texte du bouton à `#fff2d5` et le radius de la bordure à `3px`.


