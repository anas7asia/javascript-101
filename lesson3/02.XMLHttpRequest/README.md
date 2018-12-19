# XMLHttpRequest et AJAX

+ [w3schools > AJAX Intro](https://www.w3schools.com/js/js_ajax_intro.asp)
+ [MDN > XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
+ [w3schools > XMLHttpRequest](https://www.w3schools.com/xml/xml_http.asp)

AJAX est "**A**synchronous **J**avaScript **A**nd **X**ML", mais on utilise JSON au lieu de XML
Grâce à l'AJAX on peut envoyer/récupérer des données d'un serveur distant après le chargement de la page.


```js
// Exeptionally comments are in French this time
// la méthode encorporée dans le navigateur - XMLHttpRequest - est instanciée
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

## Practise now!

`https://swapi.co/documentation` est un API RESTful qui provide l'information sur l'univers de Star Wars et nécessite pas d'autorization, donc que les requêtes GET sont possibles.

Récupérez l'information du profil de Han Solo sachant que sont id est égal à 14 dans la base de donnée.
Ensuite affichez sur votre page ces données: nom, sexe, date de naissance, couleur de yeux, couleur de cheveux.

---

Trouvez toutes les personnes avec le nom de famille Skywalker. Affichez leur profiles sur votre page.

---

Récupérez et affichez les données de 5 planètes avec les ids suivants:

```js
const planets = [1, 2, 3, 4, 5];
```

---

// TODO: use headers

---

Placeholder API: [https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)

Récupérez et affichez un article, sous cet article affichez ces comentaires.

---

Récupérez et affichez 5 articles, sous chaque article affichez ces comentaires.