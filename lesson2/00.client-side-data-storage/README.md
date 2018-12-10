# Garder les données côté client

Il y a trois APIs qui permettent garder les données dans un navigateur: 
+ [MDN > Cookies](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)
+ [w3school > Cookies](https://www.w3schools.com/js/js_cookies.asp)
+ [LocalStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
+ [SessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

&nbsp; | Cookies | LocalStorage | SessionStorage
--- | --- | --- | ---
Poids maximum par domaine |  50 cookies et 4093 octets | ~5MB | ~5MB
Date d'expiration | Possible à règler | Non | Après la fermeture de window
Envoyé avec chaque requête HTTP | Oui | Non | Non
Partagé entre tous les sous-domaines? | Oui | Non | Non
Facile à manipuler | Pas vraiment | Oui | Oui


## Cookies

> Pour travailler avec les cookies utilisez le [framework](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie/Simple_document.cookie_framework) de MDN ou créez un.

Créez une bannière qui prévient que votre site utilise des cookies.
![Cookies](https://i.ibb.co/QN5QJ1H/cookies-notice.png)


Quand un utilisateur vient sur votre site, vérifiez s'il a un cookie "cookiesAccepted" qui est égal à true.
Si oui, ne montrez pas la bannière.
Si non, montrez la bannière. Quand il la marquera comme lue, créez un cookie "cookiesAccepted" qui est égal à `true`.

---

Cookie qui expire dans une minute
Cookie qui éxpire dans trois un

---

Lire cookies

---

Modifier un cookie

---

Supprimer un cookie

----

Mettre un objet dans un cookie
JSON.parse
JSON.stringify


## SessionStorage

Créez une entrée

---

Lire une entrée

---

Modifier une entrée

---

Supprimer une entrée

---

Supprimer tous les données du storage

---

Si SessionStorage est supporté par le navigateur, mettez les données là-bas, sinon dans les cookies


## LocalStorage

Créez

---

Lire

---

Modifier

---

Supprimer

---

Si SessionStorage est supporté par le navigateur, mettez les données là-bas, sinon dans un cookie qui expire aujourd'hui à minuit