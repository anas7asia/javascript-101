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

Récupérez et logguez dans la console le contenu du titre de la page.

---
Changez le contenu du titre de la page à `'My page title'`.

---
Récupérez et logguez dans la console le HTML de l'article.

---
Changez le contenu de l'article à 

```html
<h2>This is my article.</h2>
<p>This is my article's content.</p>
<a href="https://example.com">Read more</a>
```

---
Récupérez et logguez dans la console la valeur du champ de saisie avec l'id `js-search`.

---
Changez la valeur du champ de saisie à `'Beagles'`

---
Récupérez et logguez dans la console la valeur du placeholder du champ de saisie.

---
Changez la valeur du placeholder du champ de saisie à `'Search'`

<!-- ---
Ajoutez un attribut `data-article-id` avec la valeur `1` à l'article avec l'id `js-article`. Pour en savoir plus sur les attributs de données: [https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes). -->

<!-- ---
Récupérez et logguez dans la console la valeur de l'attribut `data-article-id` que vous venez d'ajouter. -->

---

```html
  <div class="container">
    <form class="form-row" id="js-search-form">

      <div class="col-auto">
        <div class="input-group">
          <div class="input-group-prepend">
            <div class="input-group-text">Search</div>
          </div>
          <input type="text" class="form-control" id="js-search" placeholder="Recherche">
        </div>
      </div>

      <div class="col-auto">
        <button class="btn btn-primary" type="submit">Rechercher</button>
      </div>
    </form>

    <div id="js-search-result"></div>
  </div>

```

Sélectionnez le formulaire dans le DOM.
Ajoutez un écouteur d'événements 'submit' au formulaire pour déclencher un événement à chaque fois que le formulaire est soumis.
Quand ce formulaire est soumis, récupérez la valeur saisie dans le champ de recherche.
Si la valeur saisie est égale à 'Chat', insérez le texte 'Miaou!' dans le `<div>` avec l'id `js-search-result`. Sinon dans ce même `<div>` insérez du HTML `<p>Pas de resultats pour la recherche : <strong>' + keyword + '</strong></p>`.

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
</article>
```
---
Supprimez le contenu de l'article `#js-article-2`.

---
Supprimez du DOM l'article `#js-article-2`.

---
```html
<div id="js-cat-problems" class="container"></div>
```
Dans le `<div>` avec l'id `js-cat-problems` insérez dynamiquement :
1. [append] Une image avec `src` égal à `https://img.buzzfeed.com/buzzfeed-static/static/2014-12/23/9/enhanced/webdr12/anigif_enhanced-23685-1419343761-9.gif?downsize=800:*&output-format=auto&output-quality=auto`
2. [prepend] Un paragraphe avec le texte `Votre chat a de l'humour. Par exemple, il adore se mettre à chasser une souris invisible, faire des dérapages contrôlés ou gratter sous votre lit à 5h11 du matin.` en tant que **premier enfant du div**.
3. [append] Un paragraphe avec le texte `Et ne vous avisez pas de trop remuer les pieds : vous pourriez le regretter.` en tant que **dernier enfant du div**.
4. [before] Un paragraphe avec le texte `C'est la raison pour laquelle il peut aussi remplir la fonction « réveil », ce qui est bien pratique. Enfin, sauf les week-ends.` **juste avant l'image**.
5. [after] Un paragraphe avec le texte `S'il dort dans votre lit, il y a de grandes chances pour qu'il s'installe pile au centre et que vous vous retrouviez au bord, prêt(e) à tomber.` **juste après l'image**.

Le texte final sera : Votre chat a de l'humour. Par exemple, il adore se mettre à chasser une souris invisible, faire des dérapages contrôlés ou gratter sous votre lit à 5h11 du matin. 
C'est la raison pour laquelle il peut aussi remplir la fonction « réveil », ce qui est bien pratique. Enfin, sauf les week-ends.
(image)
S'il dort dans votre lit, il y a de grandes chances pour qu'il s'installe pile au centre et que vous vous retrouviez au bord, prêt(e) à tomber.
Et ne vous avisez pas de trop remuer les pieds : vous pourriez le regretter.'

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
Récupérez et logguez dans la console la couleur du fond du bouton.

---
Passez la couleur du fond du bouton en `#71b8af`.

---
Changez *d'un coup* la couleur du texte du bouton à `#fff2d5` et le radius de la bordure à `3px`.

---

```css
.text-danger {
  color: red;
}
```

```html
<div class="alert alert-danger" id="js-danger-alert">
  <p>My alert</p>
  <button class="btn btn-success" id="js-danger-alert-btn">Ok</button>
</div>
```

Vérifiez si le `<div>` a la classe `alert-danger`. Si oui, ajoutez la classe `text-danger` au `<p>` et supprimez la classe `btn-success` du bouton. 
Au clique sur le bouton ajoutez la propriété css `display` égale à `none` au `<div>`.