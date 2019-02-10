# HTTP

+ [MDN > HTTP Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
+ [What is RESTful?](https://stackoverflow.com/questions/671118/what-exactly-is-restful-programming)

## Méthodes de requêtes HTTP

> [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) - **C**reate, **R**ead, **U**pdate, **D**elete

### Read

Une méthode [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) est utilisée pour récupérer des données d'un serveur. Par exemple, des articles d'un blog, ou des commentaires sous un article.

### Create

Une méthode [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) est utilisée pour envoyer des données sur un serveur. Par exemple, créer un article, soumettre un formulaire de contact, se connecter à un compte.

### Update

Une méthode [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) est utilisée pour modifier du contenu qui existe déjà sur un serveur. Par exemple, modifier un mot de passe ou modifier un commentaire sous un article.

### Delete

Une méthode [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) est utilisée pour supprimer des données qui existent sur un serveur. Par exemple, supprimer un commentaire d'un article ou supprimer un compte.


> Les méthodes à utiliser et les paramètres acceptés sont décrits dans les docs de APIs RESTful, par exemple, de [Dota2](https://docs.opendota.com/), [Twitter](https://developer.twitter.com/en/docs.html), [référence de l’intégralité des adresses français](https://adresse.data.gouv.fr/api)


Voir toutes les méthodes HTTP: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)


## Headers

![Headers](https://i.ibb.co/7NRhQ2S/headers.png)

Pour communiquer des informations additionnelles dans une requête HTTP on utilise les [headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers). 


## Réponses

![Header](https://www.commitstrip.com/wp-content/uploads/2018/08/Strip-Response-code-650-final.jpg)

En cas de succès ainsi que d'erreur de chaque requête HTTP un code numérique indiquant le status d'éxecution est envoyé. Voir tout les statuts: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)