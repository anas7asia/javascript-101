# HTTP

## Comment fonctionne le Web

[![How web works](http://img.youtube.com/vi/7_LPdttKXPc/0.jpg)](http://www.youtube.com/watch?v=7_LPdttKXPc)

<!-- // How web works: https://www.youtube.com/watch?v=7_LPdttKXPc -->

## Méthodes de requêtes HTTP
> **CRUD** - **C**reate, **R**ead, **U**pdate, **D**elete

> Pour pouvoir utiliser ces methodes avec JavaScript et avoir les résponses correctes il faut avoir un API RESTful
> Normalement chaque API possède un doc avec la liste de toutes les requêtes et les méthodes qu'il faut utiliser

### Read

Méthode [GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET)
Search params

Utilisée pour récupérer les données d'un serveur. Par exemple, vous avez un blog. Avec la méthode GET vous pouvez récupérer les articles du blog, faire la recherche parmis les articles (avec query params), avoir l'info de l'auteur du blog.

Utilisée également pour récupérer les fichiers de votre ordinateur ou serveur.

### Create

Méthode [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
Utilisée pour envoyer les données sur le serveur. Par exemple, créer un article, soumettre un formulaire de contacte, se connecter à votre compte.
Avec cette methode il faut faire attention et bien formatter les données avant envoie. 

### Update

Méthode [PUT](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT)
Utilisée pour mettre à jour le contenu qui existe déjà sur le serveur. Par exemple, modifier le mot de passe ou contenu d'un article.

### Delete

Méthode [DELETE](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE)
Utilisée pour supprimer les données qui existent sur le serveur. Par exemple, supprimer un commentaire d'un article, supprimer son compte, 


## Headers

![Headers](https://i.ibb.co/pz5jVTL/Request.png)

Pour communiquer l'information additionnelle dans une requête HTTP on peut utiliser les [headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers). 
Les plus communs sont:

General:

Request URL
Request Method
Status Code

Request:

Accept
Accept-Encoding
Accept-Language
Authorization
Connection
Content-Type
Origin
etc


## Réponses

![Header](https://www.commitstrip.com/wp-content/uploads/2018/08/Strip-Response-code-650-final.jpg)

API RESTful en cas de succès ainsi que d'erreur envoie toujours un statut numérique pour dire si tout va bien ou il a subit une erreur.

Les statuts de réponses: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
200,
201,
204,
400,
401,
404,
408
409