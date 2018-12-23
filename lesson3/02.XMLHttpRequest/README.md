# XMLHttpRequest et AJAX

+ [w3schools > AJAX Intro](https://www.w3schools.com/js/js_ajax_intro.asp)
+ [MDN > XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
+ [w3schools > XMLHttpRequest](https://www.w3schools.com/xml/xml_http.asp)

AJAX est "**A**synchronous **J**avaScript **A**nd **X**ML", mais on utilise JSON au lieu de XML
Grâce à l'AJAX on peut envoyer/récupérer des données d'un serveur distant et modifier le contenue de la page après son chargement.

```js
// Exeptionally comments are in French this time
// La méthode de BOM - XMLHttpRequest - est instanciée
var xhttp = new XMLHttpRequest();
// onreadystatechange est déclenché à chaque changement du statut de l'objet "XMLHttpRequest" (comme un écouteur d'événement)
xhttp.onreadystatechange = () => {
    /*
    Si l'état de "XMLHttpRequest" est égal à 4 (4 signifie "DONE"). Voir tous les statuts: https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState

    Et si le statut la requête est égal à 200 (Ok / réussite)
    */
    if (xhttp.readyState == 4 && xhttp.status == 200) {
      // faites ce que vous voulez avec 
      console.log(xhttp)
      console.log(xhttp.responseText)
    }
};
// La méthode "open" crée la requête
xhttp.open('GET', 'url', true);
// Quand le traitement de la requête est prêt, la méthode "send" envoie la requête
xhttp.send();
```

![Ajax](https://i.ibb.co/CK86F0R/ajax.gif)

## C'est en forgeant qu'on devient forgeron

`https://swapi.co/documentation` est un API RESTful qui fournit les données de l'univers Star Wars et ne nécessite pas d'autorization.

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

Récupérez l'information du profil de Chewbacca (son id dans la base de données est 14) en format wookiee.
Ensuite affichez sur votre page ces données: nom, hauteur, date de naissance, couleur des yeux, couleur des cheveux.

**whrascwo:** Cacwoohrhraoaoara
etc


## Données fictives (mock data)

Des fois c'est très utile de tester le code avec des données fictives en attendant que la vrai API soit prête. 
![API](http://www.commitstrip.com/wp-content/uploads/2013/07/Strips-Unknown-error-600-final.jpg)

### Placeholder API: 

> Placeholder API: [https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)

Récupérez et affichez un article avec l'id 25, ensuite affichez ces commentaires.

---

Récupérez et affichez 5 articles, sous chaque article affichez ces comentaires.

```js
const articles = [1, 2, 3, 4, 5];
```

### Reqres

> API RESTful https://reqres.in/ accepte les données en format JSON.

Créez un formulaire de **connexion** qui comprend les champs de email et de mot de passe. A la soumission du formulaire, envoyez la requête de connexion à l’API https://reqres.in/. En cas de succès, mettez le token dans les cookies, en cas d’erreur, affichez l’erreur sous le formulaire.

---

Créez un bouton de deconnexion. Cliquez-le pour effacer le token sauvegardé das les cookies.

---

Créez un formulaire d'**inscription** qui comprend les champs de email et de mot de passe. A la soumission du formulaire, envoyez la requête d'inscription à l’API https://reqres.in/. En cas de succès, mettez ses information et le token rétourné dans les cookies, en cas d’erreur, affichez l’erreur sous le formulaire.

---

Créez un bouton de suppression d'un utilisateur. Cliquez-le pour supprimer l'utilisateur sauvegardé das les cookies.
Supprimer ses infos et son token des cookies.

## Reading List

+ [A gentle Introduction to Ajax.](https://codeburst.io/a-gentle-introduction-to-ajax-1e88e3db4e79)