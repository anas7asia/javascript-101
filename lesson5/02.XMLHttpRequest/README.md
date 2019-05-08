# XMLHttpRequest et AJAX

+ [w3schools > AJAX Intro](https://www.w3schools.com/js/js_ajax_intro.asp)
+ [MDN > XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
+ [w3schools > XMLHttpRequest](https://www.w3schools.com/xml/xml_http.asp)

AJAX signifie "**A**synchronous **J**avaScript **A**nd **X**ML".
AJAX permet d'envoyer et de récupérer des données d'un serveur distant après que le rendu de la page par le navigateur soit terminé.
A l'origine AJAX utilise le format XML pour la communication avec le serveur. Desormais on préfère utiliser le format JSON, celui-ci étant bien plus simple à manipuler.


```js
// Exeptionally comments are in French this time

// La méthode de BOM - XMLHttpRequest - est instanciée
var xhttp = new XMLHttpRequest();
// onreadystatechange est appelé de manière asynchrone et sera déclenché à chaque changement du statut de l'objet "XMLHttpRequest" (comme un écouteur d'événement)
xhttp.onreadystatechange = () => {
    /*
    Si l'état de "XMLHttpRequest" est égal à 4 (4 signifie "DONE"). Voir tous les statuts: https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState

    Et si le statut la requête est égal à 200 (Ok / réussite)
    */
    if (xhttp.readyState == 4 && xhttp.status == 200) {
      // procédez à un traitement de la réponse 
      console.log(xhttp)
      console.log(xhttp.responseText)
    }
};
// La méthode "open" crée la requête
xhttp.open('GET', 'url', true);
// Quand le traitement de la requête est terminé, la méthode "send" envoie la requête
xhttp.send();
```

![Ajax](https://i.ibb.co/CK86F0R/ajax.gif)

VSCode JavaScript Snippet:

```json
"XMLHttpRequest": {
  "prefix": "xml",
  "body": [
    "let xhttp = new XMLHttpRequest();",
    "xhttp.onreadystatechange = () => {",
    "  if (xhttp.readyState == 4 && xhttp.status == 200) {",
    "    console.log(xhttp.responseText)",
    "  }",
    "};",
    "xhttp.open('GET', 'url', true);",
    "xhttp.send();"
  ]
},
```

## C'est en forgeant qu'on devient forgeron

[swapi.co](https://swapi.co/documentation) est un API RESTful qui fournit les données de l'univers Star Wars et ne nécessite pas d'autorization.

![Star Wars](http://www.commitstrip.com/wp-content/uploads/2015/12/Strip-Star-wars-650-final.jpg)

Récupérez l'information du profil de Han Solo (son id dans la base de données est 14).
Ensuite affichez sur votre page ces données: nom, sexe, date de naissance, couleur des yeux, couleur des cheveux.

---

Trouvez toutes les personnes avec le nom de famille Skywalker. Affichez leur profiles sur votre page.

---

Récupérez et affichez les données de 5 planètes avec les ids suivants:

```js
const planets = [1, 2, 3, 4, 5];
```

---

Récupérez l'information du profil de Chewbacca (son id dans la base de données est 13) en format **wookiee**.
Attention les clés json sont également en wookiee. 
Pour chaque clé json, si la valeur est primitive (string, number, etc), affichez la paire de clé/valeur.

```
**whrascwo:** Cacwoohrhraoaoara
```

## Données fictives (mock data)

Des fois c'est très utile de tester le code avec des données fictives en attendant que la vrai API soit prête. 
![API](http://www.commitstrip.com/wp-content/uploads/2013/07/Strips-Unknown-error-600-final.jpg)

### Reqres

> API RESTful https://reqres.in/ accepte les données en format JSON.

```html
<form id="js-signin-form">

  <fieldset id="js-signin-fields">
    <div class="form-group">
      <label for="js-signin-email">Email</label>
      <input type="email" name="email" placeholder="Email" value="test@ynov.com" id="js-signin-email" class="form-control">
    </div>
    <div class="form-group">
      <label for="js-signin-password">Password</label>
      <input type="password" name="password" placeholder="Password" id="js-signin-password" value="qwerty" class="form-control">
    </div>
  </fieldset>

  <input type="submit" value="Sign in" class="btn btn-primary">
</form>
```

Créez un formulaire de **connexion** qui comprend les champs *email* et *mot de passe*. A la soumission du formulaire, envoyez la requête de connexion à l’API `https://reqres.in/`. En cas de succès, mettez le token dans les cookies, en cas d’erreur, affichez l’erreur sous le formulaire.

---

Créez un bouton de deconnexion. Au clique sur ce bouton effacez le token sauvegardé dans les cookies.

---

```html
<form id="js-signup-form">

  <fieldset id="js-signup-fields">
    <div class="form-group">
      <label for="js-signup-email">Email</label>
      <input type="email" name="email" placeholder="Email" value="test@ynov.com" id="js-signup-email" class="form-control">
    </div>
    <div class="form-group">
      <label for="js-signup-password">Password</label>
      <input type="password" name="password" placeholder="Password" id="js-signup-password" value="qwerty" class="form-control">
    </div>
    <div class="form-group">
      <label for="js-signup-lastname">Last name</label>
      <input type="text" name="lastname" placeholder="Last name" id="js-signup-lastname" value="Besson" class="form-control">
    </div>
    <div class="form-group">
      <label for="js-signup-firstname">First name</label>
      <input type="text" name="firstname" placeholder="First name" id="js-signup-firstname" value="Luc" class="form-control">
    </div>
  </fieldset>

  <input type="submit" value="Sign up" class="btn btn-primary">
</form>
```

Créez un formulaire d'**inscription** qui comprend les champs *nom*, *prénom*, *email* et *mot de passe*. A la soumission du formulaire, envoyez la requête d'inscription à l’API https://reqres.in/. En cas de succès, mettez ses informations et le token renvoyé dans les cookies, en cas d’erreur, affichez l’erreur sous le formulaire.

---

Créez un bouton de suppression d'un utilisateur. Au clique sur ce bouton supprimez l'objet utilisateur et son token des cookies.

## Reading List

+ [A gentle Introduction to Ajax.](https://codeburst.io/a-gentle-introduction-to-ajax-1e88e3db4e79)