# Manipulation de DOM avec jQuery

## Récupérer/modifier

Utilisez les méthodes `text`, `html`, `val`, `attr` pour travailler avec le HTML suivant.

```html
<article id="js-article">
  <h2>Article title</h2>
  <p>Article content</p>
</article>

<input type="text" id="js-search" placeholder="Search something..." value="Poodles">
```

Récupérez et loggez le contenu du titre de la page.

---
Changez le contenu du titre de la page à `'My page title'`.

---
Récupérez et loggez la sructure HTML (et son contenu) de l'article.

---
Changez le contenu de l'article à 

```html
<h2>This is my article.</h2>
<p>This is my article's content.</p>
<a href="https://example.com">Read more</a>
```

---
Récupérez et loggez la valeur du champ de saisie avec l'id `js-search`.

---
Changez la valeur du champ de saisie à `'Beagles'`

---
Récupérez et loggez la valeur de placeholder du champ de saisie.

---
Changez la valeur de placeholder du champ de saisie à `'Search'`

---
Ajoutez un attribut `data-article-id` à l'article `js-article` avec la valeur `1`. Savoir plus sur les attributs de données: [https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes).

---
Récupérez et loggez la valeur de l'attribut `data-article-id`.

## Insérer/supprimier du contenu

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

Ajouter une balise `<div>` dans l'article avec l'id `js-article-1`.

---

Dans la balise `<div>` de l'article `js-article-1` ajoutez un paragraphe avec la valeur `'He starts to look at me pleadingly, paces around, and meows insistently. He even climbs on top of the book and bites my wrists in protest.'`

---

Dans la balise `<div>` de l'article `js-article-1` ajoutez un autre paragraphe avec la valeur `'I recently found out that my cat, Marv, hates it when I read aloud.'` *avant* le paragraphe ajouté précédement.

---

*Après* le premier paragraphe (entre les deux paragraphes) de l'article `js-article-1` ajoutez un [image](https://cdn.pixabay.com/photo/2018/03/28/16/23/cute-3269715__340.jpg).

---

*Avant* l'article avec l'id `js-article-1` ajoutez un autre article:

```html
<article id="js-article-3">
  <h1>Cats are the weirdest-3</h1>
  <p>My cat brought me two large potatoes in the middle of the night from the kitchen counter.</p>
</article
```
---
Supprimez le contenu de l'article avec l'id `js-article-2`.

---
Supprimez complètement l'article avec l'id `js-article-2`.

## Manipuler le CSS

addClass
removeClass
hasClass
css (read, write, write multiple)

## Dimensions


