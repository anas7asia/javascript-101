
# Scripts

Resources:
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
+ [w3schools](https://www.w3schools.com/tags/tag_script.asp)
+ [JavaScript.info](http://javascript.info/hello-world)

Dans votre code HTML créez une balise script avec du code interne.
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Internal script</title>
  </head>

  <body>
    <h1>Welcome to my document!</h1>
    <p>Get yourself comfortable.</p>
  </body>
</html>
```

---

+ Insérez le script `before-render.js` qui doit être présent avant le rendement de la page. Dans ce fichier créez des commentaires JavaScript: d'une ligne (*inline*) et de plusieurs lignes (*multiline*).
+ Insérez le script `after-render.js` qui doit commencer à télécharger après le rendement de la page.
+ Insérez le script `whenever.js` qui est commence à télécharger pendant le rendement de la page.
+ Si le navigateur d'utilisateur de votre site n'a pas de JavaScript activé, montrez-lui une petite notice qui dit que pour accéder toutes les fonctionnalités du site il a besoin de JavaScript.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Internal scripts</title>
    <!-- script here? -->
  </head>

  <body>
    <h1>Welcome to my document!</h1>

    <p>Beginning of the document...</p>
    
    <!-- or here? -->

    <p>...end of the document</p>

    <!-- or maybe there? -->
  </body>
</html>
```

## async et defer

1. Quelle script est téléchargé le premier?
```html
<script src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script src="./small-script.js"></script>
```

2. Quelle script est téléchargé le premier?
```html
<script async src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script async src="./small-script.js"></script>
```

3. Quelle script est téléchargé le premier?
```html
<script defer src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script defer src="./small-script.js"></script>
```

4. Quelle script est téléchargé le premier?
```html
<script async src="./small-script.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
```