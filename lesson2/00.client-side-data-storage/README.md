# Garder les données côté client

Il y a trois APIs qui permettent garder les données dans un navigateur: 
+ [MDN > Cookies](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)
+ [w3school > Cookies](https://www.w3schools.com/js/js_cookies.asp)
+ [LocalStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
+ [SessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

![GDRP](https://www.commitstrip.com/wp-content/uploads/2018/05/Strip-CYB-RGPD-650-final-.jpg)

&nbsp; | Cookies | LocalStorage | SessionStorage
--- | --- | --- | ---
Poids maximum par domaine |  50 cookies et 4093 octets | ~5MB | ~5MB
Date d'expiration | Possible à règler | Non | Après la fermeture de window
Envoyé avec chaque requête HTTP | Oui | Non | Non
Partagé entre tous les sous-domaines? | Oui | Non | Non
Facile à manipuler | Pas vraiment | Oui | Oui


## Cookies

> Pour travailler avec les cookies utilisez le [framework](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie/Simple_document.cookie_framework) de MDN ou créez un.


Créez un cookie 'lang' égal à 'fr'.
Créez un cookie 'previewSeen' égal à 'true' qui va expirer dans 5 minutes.
Créez un cookie 'test' égal à 'test' qui va expirer ce miniut.
Créez un cookie 'userId' égal à '123' qui sera `secure`.
Créez un cookie 'superSecret' qui sera accessible uniquement dans la requête http (pas côté client).

Récupérez et loggez les valeurs de cookies 'lang', 'previewSeen' et 'userId'

Modifiez la valeur du cookie 'userId' à '321'.

Supprimez le cookie 'test'.

> Qu'est-ce que c'est [JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)

Mettez l'objet et le tableau suivants dans les cookies et ensuite récupérez-le. Utilisez les méthodes [JSON.stringify](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) et [JSON.parse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)

```js
const user = {
  id: 1,
  name: 'Thibaud'
}

const emails = ['a@ynov.com', 'b@ynov.com', 'c@ynov.com']
```

---

Créez une bannière qui prévient les utilisateurs que votre site utilise des cookies.

![Cookies](https://i.ibb.co/QN5QJ1H/cookies-notice.png)

1. Au chargement de page vérifiez si l'utilisateur a un cookie "cookiesAccepted" et ce cookie est égal à true. 
2. Si oui, cachez la bannière, sinon montrez-là. 
3. A l'acceptation Quand il la marquera comme lue, créez un cookie "cookiesAccepted" qui est égal à true et cachez la bannière.


## LocalStorage

Vérifiez si LocalStorage est supporté par le navigateur.

Créez une entrée `greeting` égale à 'Hello World'.
Créez une entrée `adIds` égale à l'objet `{top: 1, bottom: 2}`.
Récupérez `greeting`.
Modifiez cette entrée à 'Welcome'.
Supprimez `greeting` du LocalStorage.

---

Ajoutez les entrées `test1`, `test2`, `test3`, `test4`
Supprimez tous les données du storage en un click.


## SessionStorage

Vérifiez si SessionStorage est supporté par le navigateur.

Créez une entrée `posts` égale à `[{id: 0}, {id: 1}, {id: 2}]`.
Créez une entrée `userId` égale au nombre 123.
Récupérez `posts`.
Modifiez cette entrée à `[{id: 321}, {id: 1}, {id: 2}]`.
Supprimez `userId` du LocalStorage.
Refraîchissez la page, est-ce que les données sont toujours présents dans SessionStorage?
Fermer et re-ouvrez la fênetre, est-ce que les données sont toujours présents dans SessionStorage?

---

Ajoutez les entrées `test1`, `test2`, `test3`, `test4`
Supprimez tous les données du storage en un click.

## Pour aller plus loin

Sur votre page affichez soit le formulaire de connexion, soit les données de l'utilisateur connecté.

1. Créez un formulaire de connexion qui comprend les champs d'email et de mot de passe. 
2. Quand le formulaire est soumis, faites une fausse appelle `login()` au serveur distant.
3. Mettez le données d'utilisateur dans les cookies, ainsi que son [token](https://jwt.io/introduction/).
4. Si l’utilisateur est connecté, affichez son nom, prénom, email et avatar (soit au chargement de page si déjà connecté et après la connexion).

```js
const userdata = {
  firstname: 'Anna',
  lastname: 'Gavalda',
  email: 'anna.gavalda@gmail.com',
  sex: 'F',
  id: 123456,
  avatar: ''
}

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

function getUserData() {
  return userdata
}
```

---

Créez un formulare de réservation des billets d'avion avec les champs suivants:
+ départ de
+ arrivée à 
+ date de départ
+ date de retour
+ nombre de voyageurs

Remplissez le formulaire et à sa soumission mettez les données saisis dans le Local/Session Storage.
Au refraîchissement de la page remlissez le formulaire avec les données sauvegardées.


## Reading List

+ [Cookies vs. LocalStorage: What’s the difference?](https://medium.com/swlh/cookies-vs-localstorage-whats-the-difference-d99f0eb09b44)
+ [What is session hijacking and how you can stop it](https://medium.freecodecamp.org/session-hijacking-and-how-to-stop-it-711e3683d1ac)
+ [Session vs Token Based Authentication](https://medium.com/@sherryhsu/session-vs-token-based-authentication-11a6c5ac45e4)
