
# Scripts

+ [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
+ [w3schools](https://www.w3schools.com/tags/tag_script.asp)
+ [JavaScript.info](http://javascript.info/hello-world)

Dans votre code HTML créez une balise 'script' interne.

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

+ Insérez le script `before-render.js` qui doit être présent avant le rendement de la page.
+ Insérez le script `after-render.js` qui doit commencer à charger après le rendement de la page.
+ Insérez le script `whenever.js` qui doit commencer à charger pendant le rendement de la page et terminer à n'importe quel moment.
+ Si le navigateur d'utilisateur de votre site n'a pas de JavaScript activé, montrez-lui une petite notice qui dit: "Pour accéder à toutes les fonctionnalités de notre site vous avez besoin de JavaScript".

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

1. Quel script est chargé en premier?
```html
<script src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script src="./small-script.js"></script>
```

2. Quel script est chargé en premier?
```html
<script async src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script async src="./small-script.js"></script>
```

3. Quel script est chargé en premier?
```html
<script defer src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
<script defer src="./small-script.js"></script>
```

4. Quel script est chargé en premier?
```html
<script async src="./small-script.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/lodash@4.17.11/lodash.min.js"></script>
```

## Reading List

+ (Understanding async, defer while loading javascript files in HTML)[https://medium.com/@arpitjay099/understanding-async-defer-while-loading-javascript-files-in-html-3df218c7e857]
+ (Speed up Google Maps(and everything else) with async & defer)[https://medium.com/@nikjohn/speed-up-google-maps-and-everything-else-with-async-defer-7b9814efb2b]