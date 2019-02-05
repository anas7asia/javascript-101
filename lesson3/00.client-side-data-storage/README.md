# Garder les données côté client

+ [MDN > Cookies](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)
+ [w3school > Cookies](https://www.w3schools.com/js/js_cookies.asp)
+ [Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
+ [Session Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

Il y a trois APIs qui permettent de garder les données dans le navigateur: 

&nbsp; | Cookies | LocalStorage | SessionStorage
--- | --- | --- | ---
Poids maximum par domaine |  50 cookies et 4093 octets | ~5Mo | ~5Mo
Date d'expiration | Possible à règler | Non | Après la fermeture de l'onglet
Envoyé avec chaque requête HTTP | Oui | Non | Non
Partagé entre tous les sous-domaines? | Oui | Non | Non
Facile à manipuler | Pas vraiment | Oui | Oui


## Cookies

> Pour travailler avec les cookies utilisez le [framework](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie/Simple_document.cookie_framework) de MDN ou créez votre propre parseur de cookies.

Créez un cookie *lang* égal à `'fr'`.

Créez un cookie *previewSeen* égal à `true` qui va expirer le lendement.

Créez un cookie *test* égal à `'test'` qui va expirer le 31 décembre 2019.

Créez un cookie *userId* égal à `123` 
 <!-- qui sera `secure`. -->

<!-- Créez un cookie *superSecret* qui sera accessible uniquement dans une requête http (inacessible par JavaScript). -->

Récupérez et loggez les valeurs des cookies *lang*, *previewSeen* et *userId*

Modifiez la valeur du cookie *userId* à `321`.

Supprimez le cookie *test*.

---

> Qu'est-ce que c'est [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)?

![JSON](http://www.commitstrip.com/wp-content/uploads/2014/05/Strips-XML-VS-JSON.jpg)

Mettez l'objet *user* et le tableau *emails* dans les cookies et ensuite récupérez-les. Utilisez les méthodes [JSON.stringify](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) et [JSON.parse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)

```js
const user = {
  id: 1,
  name: 'Thibaud'
}

const emails = ['a@ynov.com', 'b@ynov.com', 'c@ynov.com']
```

---

![GDRP](https://www.commitstrip.com/wp-content/uploads/2018/05/Strip-CYB-RGPD-650-final-.jpg)

Créez une bannière qui prévient l'utilisateur que votre site utilise les cookies.

1. Au chargement de la page vérifiez si l'utilisateur a un cookie "cookiesAccepted" et si ce cookie est égal à `true`. 
2. Si oui, cachez la bannière, sinon montrez-la. 
3. A l'acceptation des conditions, créez un cookie "cookiesAccepted" qui est égal à `true` et cachez la bannière.

![Cookies](https://i.ibb.co/QN5QJ1H/cookies-notice.png)

## LocalStorage

Vérifiez si l'objet LocalStorage est supporté par le navigateur.

Créez une entrée `greeting` égale à `'Hello World'`.
Créez une entrée `adIds` égale à l'objet `{top: 1, bottom: 2}`.
Récupérez `greeting`.
Modifiez cette entrée à `'Welcome'`.
Supprimez `greeting` du LocalStorage.

---

Ajoutez les entrées `test1`, `test2`, `test3`, `test4` dans l'objet LocalStorage.
Supprimez toutes les données du LocalsStorage d'un coup.


## SessionStorage

Vérifiez si l'objet SessionStorage est supporté par le navigateur.

Créez une entrée `posts` égale à `[{id: 0}, {id: 1}, {id: 2}]`.

Créez une entrée `userId` égale au nombre `123`.

Récupérez `posts`.

Modifiez cette entrée à `[{id: 321}, {id: 1}, {id: 2}]`.

Supprimez `userId` du SessionStorage.

---

Rafraîchissez la page, regardez si les données sont toujours présentes dans SessionStorage.

Fermez et ouvrez de nouveau la page, regardez si les données sont toujours présentes dans SessionStorage.

---

Ajoutez les entrées `test1`, `test2`, `test3`, `test4`.
Supprimez toutes les données du SessionStorage d'un coup.

## Pour aller plus loin

Sur votre page affichez soit le formulaire de connexion, soit les données de l'utilisateur connecté.

1. Créez un formulaire de connexion qui comprend les champs *email* et *mot de passe*. 
2. A la soumission du formulaire, faites un appel à la fonction `login()` (sur un vrai site la fonction `login()` appellerai un serveur distant).
3. Mettez les données utilisateur dans les cookies, ainsi que son [token](https://jwt.io/introduction/).
4. Si l'utilisateur est connecté, cachez le formulaire et affichez son nom, prénom, email et avatar.

```js
const userdata = {
  firstname: 'Anna',
  lastname: 'Gavalda',
  email: 'anna.gavalda@gmail.com',
  sex: 'F',
  id: 123456,
  avatar: 'https://upload.wikimedia.org/wikipedia/commons/thumb/0/07/Anna_Gavalda_20100328_Salon_du_livre_de_Paris_1.jpg/220px-Anna_Gavalda_20100328_Salon_du_livre_de_Paris_1.jpg'
}

// mock api call
function login(credentials) {
  return {
    user: {
      ...userdata
    },
    extra: {
      token: 'Bearer gibberish'
    }
  }
}

// token should be always supplied
function getUserData(token) {
  return userdata
}
```

---

Créez un formulare de réservation de billets d'avion avec les champs suivants:
+ départ de
+ arrivée à 
+ date de départ (champ text)
+ date de retour (champ text)
+ nombre de voyageurs (balise `select`)

A la soumission du formulaire mettez toutes les données saisies dans le LocalStorage ou le SessionStorage.
Au rafraîchissement de la page remplissez le formulaire avec les données sauvegardées.


## Reading List

+ [Cookies vs. LocalStorage: What’s the difference?](https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44)
+ [What is session hijacking and how you can stop it](https://medium.freecodecamp.org/session-hijacking-and-how-to-stop-it-711e3683d1ac)
+ [Session vs Token Based Authentication](https://medium.com/@sherryhsu/session-vs-token-based-authentication-11a6c5ac45e4)
