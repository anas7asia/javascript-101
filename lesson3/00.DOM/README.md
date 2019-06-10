# Document Object Model

+ [w3schools](https://www.w3schools.com/js/js_htmldom_eventlistener.asp)
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
+ [JavaScript.info](http://javascript.info/dom-nodes)

## Inspécter un node

Utilisez la console pour regarder toutes les propriétés et méthodes associés à un node.
Console > Séléctionner un élément > Elements > Properties

![Quick DOM Inspector](https://i.ibb.co/X7bW84V/DOM-inspector.png)

## Trouver un node

| Sélecteurs | Un node | Une liste de nodes |
| ------------- |:-------------:| :-----:|
| par id | getElementById <br> querySelector | - |
| par classe | querySelector | getElementsByClassName <br> querySelectorAll |
| par un nom de balise | querySelector | getElementsByTagName <br>querySelectorAll |
| par un sélecteur CSS | querySelector | querySelectorAll |

Utilisez le HTML et le CSS ci-dessous:
<details>
  <summary>HTML</summary>

  ```html
  <h1>Qu'est-ce que c'est le DOM ?</h1>

  <p>Le Document Object Model ou DOM (pour modèle objet de document) est une interface de programmation pour les documents HTML, XML et SVG. Il fournit une <span>représentation structurée du document sous forme d'un arbre</span> et définit la façon dont la structure peut être manipulée par les programmes, en termes de style et de contenu.</p>

  <p>Le DOM représente le document <span>comme un ensemble de nœuds</span> et d'objets possédant des propriétés et des méthodes. Les nœuds peuvent également avoir des gestionnaires d'événements qui se déclenchent lorsqu'un événement se produit. Cela permet de manipuler des pages web grâce à des scripts et/ou des langages de programmation.</p>

  <p> Les nœuds peuvent être associés à des gestionnaires d'événements. Une fois qu'un événement est déclenché, les gestionnaires d'événements sont exécutés.</p>

  <div class="circles">
    <div class="circle">
      <span>Div 1</span>
    </div>
    <div class="circle" id="middle-circle">
      <span>Div 2</span>
    </div>
    <div class="circle">
      <span>Div 3</span>
    </div>
  </div>
  ```
</details>

<details>
  <summary>CSS</summary>

  ```html
    <style>
    .circles {
      display: flex;
    }

    .circle {
      position: relative;
      margin-right: 5%;
      padding-top: 30%;
      width: 30%;
      background-color: palegreen;
      border-radius: 100%;
    }

    .circle span {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translateX(-50%) translateY(-50%);
    }

    #middle-circle {
      background-color: cornflowerblue;
    }

    p span {
      text-decoration: underline;
    }
  </style>
  ```
</details>

Faites les tâches suivantes deux fois. La première fois avec les méthodes `getElementById / getElementsByClassName / getElementsByTagName`, la deuixème fois avec les méthodes `querySelector / querySelectorAll `:

+ Sélectionnez tous les paragraphes.
+ Sélectionnez tous les divs par le nom de class.
+ Sélectionnez le div bleu.
+ Sélectionnez les spans qui se trouvent dans les paragraphes.


<!-- ---

Utilisez: `getElementById`, `getElementsByClassName`, `getElementsByTagName`, `querySelector`, `querySelectorAll` pour

+ Trouvez toutes les balises `div` du document. Loggez le deuxième élément s'il est présent.
+ Trouvez toutes les balises `p` avec la classe 'my-paragraph' du document. Loggez le premier élément s'il est présent.
+ Trouvez la balise `span` avec l'id 'js-unique-el'. Loggez-là. Inspéctez les propriétés de cet objet [Element](https://developer.mozilla.org/en-US/docs/Web/API/Element)
+ Trouvez toutes les balises `p` qui se trouvent dans un div. 
+ Trouvez toutes les balises `span` qui sont précédées par un div. 

```html
<div>
  <p class="main-paragraph">Paragraph 1</p>
</div>
<div>
  <p class="secondary-paragraph">Paragraph 2</p>
</div>
<span></span>
<div>
  <p class="secondary-paragraph">Paragraph 3</p>
</div>
<p class="secondary-paragraph">Paragraph 3</p>
<span id="js-unique-el"></span>
``` -->

> **Bonne pratique :** si vous créez une classe ou un id pour manipuler les éléments avec JS, prefixez leurs noms avec 'js-', comme `.js-my-class`


## Modifier un node

Ajoutez le texte 'I am the first paragraph' au premier paragraphe du document.

Ajoutez le HTML `<span>Hello</span>` au deuxième paragraphe du document.

Modifiez la largeur `width` à 50% et `height` à 'auto' de l'image.

<!-- Ajoutez un attribut `alt` non vide à l'image. -->

Donnez la couleur 'blue' au premier paragraphe du div et la taille de police '1.5rem'.

Ajoutez la classe `img` à l'image.

```html
<p class="first-p"></p>
<p class="second-p"></p>
<img src="http://lorempixel.com/10/10/" width="10" height="10">
<div><p>I'm inside of a div</p></div>
```

---

Copiez-collez le HTML suivant dans votre page web.

<details>
<summary>HTML</summary>

```html
<section>
  <h1 id="js-artist"></h1>
  <p id="js-artist-real-name"></p>

  <h2>Albums :</h2>

  <article>
    <h1 class="js-album-title"></h1>
    <p id="js-release-date">L'année de sortie: <span></span></p>
    <p><span id="js-songs-count"></span> chansons</p>

    <hr>

    <ul>
      <li>Ma chanson préférée : <span class="js-favourite-song"></span></li>
      <li>La chanson la plus connue : <span id="js-famous-song"></span></li>
      <li>La chanson la plus longue : <span id="js-longest-song"></span></li>
    </ul>
  </article>
</section>
    
```
</details>


Prenez l'objet avec les informations de votre musicien préféré que vous avez créé au dernier cours.

Affichez en bleu le pseudo, le nom et le prénom de l'artiste.

Affichez les information de son premier album : le titre, l'année de sortie et le nombre de chansons.

Affichez les titres de trois chansons de l'album en gras.


---

Copiez-collez le HTML et le CSS suivants dans votre page web.

<details>
<summary>HTML</summary>

```html
  <h1 id="page-title">Page title</h1>
  <p id="page-subtitle">Page subtitle</p>

  <p class="page-text">
    <em>Felis catus</em> has had a very long relationship with humans. Ancient Egyptians may have first domesticated cats as early as <span class="text-highlight">4,000 years ago.</span>
  </p>
  <p class="page-text">Text to replace</p>
  <p class="page-text">
    The cats' skill in killing them may have first earned the <span class="text-highlight">affectionate attention</span> of humans.
  </p>

  <section>
    <h2>Our featured articles:</h2>

    <div class="magazine-articles">
      <article>
        <img src="http://lorempixel.com/400/300/cats/?id=1">
        <div class="magazine-article-content">
          <h1>Cats are one of, if not the most, popular pet in the world.</h1>
        </div>
      </article>
    
      <article>
        <img src="http://lorempixel.com/400/300/cats/?id=2">
        <div class="magazine-article-content">
          <h1>There are over 500 million domestic cats in the world.</h1>
        </div>
      </article>
    
      <article>
        <img src="http://lorempixel.com/400/300/cats/?id=3">
        <div class="magazine-article-content">
          <h1>Cats and humans have been associated for nearly 10000 years.</h1>
        </div>
      </article>
    
      <article>
        <img src="http://lorempixel.com/400/300/cats/?id=4">
        <div class="magazine-article-content">
          <h1>Cats conserve energy by sleeping for an average of 13 hours a day.</h1>
        </div>
      </article>
    </div>
  </section>
  ```
</details>

<details>
<summary>CSS</summary>

```css
body {
  background-color: #efeeed;
  font-family: Arial, Helvetica, sans-serif;
}

.magazine-articles {
  display: flex;
  justify-content: space-between;
}

.magazine-article {
  width: 24%;
  background-color: #FFF;
  border-radius: 4px;
}

.magazine-article img {
  width: 100%;
}

.magazine-article-content {
  padding: 0 1rem;
}

.text-highlight {
  text-decoration: line-through;
}
```

</details>

1. Sélectionnez le titre principal de la page avec la méthode `getElementById`. Remplacez son texte par ‘Cats are awesome’ avec la propriété `innerText`. Changez sa propriété `text-decoration` en `underline`.
2. Sélectionnez le paragraphe sous le titre principal de la page avec la méthode `querySelector`. Ajoutez le HTML suivant avec la propriété `innerHTML`: `'Domestic cats, no matter their breed, are <strong>all members of one species.</strong>'`. Changez sa couleur en gris.
3. Sélectionnez tous les paragraphes avec le nom de classe `page-text` grace à la méthode `getElementsByClassName`. Remplacer le contenu du deuxième paragraphe par `'Plentiful rodents probably drew wild felines to human communities.'` avec la propriété `innerText`.
4. Sélectionnez toutes les balises `span` avec la classe `text-highlight` grace à la méthode `querySelectorAll`. Parcourez la liste des nodes sélectionnés. Supprimez la classe `text-highlight` de chacun d'eux.
5. Sélectionnez toutes les images de la page avec la méthode `getElementsByTagName`. Ajoutez un filtre CSS `grayscale(100%)` à la première et à la dernière image.
6. Sélectionnez toutes les balises `article` avec la méthode `querySelectorAll`. Parcourez la liste des nodes sélectionnés. Ajoutez à chacun la classe `magazine-article` pour leurs appliquer les styles prédéfinies.

Le résultat :

![Resultat](https://i.ibb.co/8Yy0hZr/DOM-practise.png)

## Créez un node

Créez un paragraphe avec le texte `'Hello'` et insérez-le dans la balise `body`.

Créez une balise `ul` avec 5 `li` dedans et insérez-la dans un div dans body. 
<!-- N'hésitez pas à utiliser la boucle `for` pour ne pas répéter la même ligne de code 5 fois. -->

<!-- --- -->

<!-- Créez une balise `script` qui télécharge la librairy jQuery `https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js` de manière asynchrone. -->


## Supprimer un node

Supprimez le paragraphe qui se trouve dans un div.
Supprimez le span.

```html
<p>I will not be deleted</p>
<div>
  <p>I will be deleted</p>
</div>
<span>I will be deleted</span>
```


## Practise

Utilisez le CSS ci-dessous.

<details>
  <summary>CSS</summary>

  ```css
  .cookies-notice {
    display: none;
    align-items: center;
    justify-content: center;
    padding: 1rem 2rem;
    width: 100%;
    background-color: rgba(0,0,0,.45);
    color: #FFF;
    font-family: Arial, Helvetica, sans-serif;
  }

  .cookies-text {
    margin-right: 3rem;
    font-style: italic;
  }

  .cookies-button {
    display: inline-block;
    padding: .7rem 1rem;
    background-color: green;
    border-radius: 4px;
    color: #FFF;
  }
  ```
</details>

1. Créez un `div` avec une classe `cookies-notice`. 
  1. Modifiez la propriété `display` de ce div pour qu'il devienne visible. 
  2. Passez-le en position fixe en bas de l'écran.
2. Créez un paragraphe `p` avec une classe `cookies-text`. 
  1. Dans ce paragraphe ajoutez le HTML suivant : `'By using our website, you acknowledge that you have read and understand our <strong>Cookies Policy</strong>'`
3. Créez un lien avec une class `cookies-button`.
  1. Insérez le texte `'Ok'` dans ce lien. 
4. Insérez le paragraphe dans le div.
5. Insérez le lien dans le div.
6. Insérez le div dans le body de votre page web.

Voici le résultat souhaité :

![Cookies](https://i.ibb.co/f1TYcmJ/Screenshot-2019-06-04-at-11-27-12.png)

---

Recréez le HTML suivant uniquement avec JavaScript.

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Page Title</title>
</head>
<body>
  <!-- from here -->
  <main>
    <h1>Main title</h1>
    <p>Here goes the <strong>description</strong></p>
  
    <img src="http://lorempixel.com/400/200/" alt="My image" width="30%">
  </main>

  <div class="cookies" style="background-color:#fdfdfd; border-radius: 4px;">
    <p>Hello, this site uses cookies! <span class="cookie-icon" data-custom-id="35"></span></p>
  </div>

  <footer>
    <ul class="links">
      <li>Link 1</li>
      <li>Link 2</li>
      <li>Link 3</li>
      <li>Link 4</li>
      <li>Link 5</li>
      <li>Link 6</li>
      <li>Link 7</li>
      <li>Link 8</li>
      <li>Link 9</li>
      <li>Link 10</li>
      <li>Link 11</li>
      <li>Link 12</li>
      <li>Link 13</li>
    </ul>
  </footer>

  <!-- till here -->
</body>
</html>
```

## Reading List

+ [Eloquent JavaScript > DOM](https://eloquentjavascript.net/14_dom.html)
+ [A comprehensive dive into NodeLists, Arrays, converting NodeLists and understanding the DOM](https://toddmotto.com/a-comprehensive-dive-into-nodelists-arrays-converting-nodelists-and-understanding-the-dom/)


