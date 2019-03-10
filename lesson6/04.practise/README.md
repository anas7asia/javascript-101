# Projet finale


> Laissez un commentaire sur chaque ligne de votre code pour expliquer pourquoi vous l'utiliser ou comment ça marche. 

## Barre de navigation

Au clique sur le lien 'Know more', affichez le menu déroulant avec l'id `navbarDropdownMenu`. Au deuxième clique sur ce lien, cachez le menu déroulant.

**BONUS:** cachez le menu déroulant si un de ces liens a été cliqué: vérifiez que l'élément cliqué est un lien qui se trouve bien dans le menu déroulant.


Le menu déroulant est invisible:
![Dropdown Closed](https://i.ibb.co/P1gwN7p/final-project-navbar.png)

Le menu déroulant est visible après le clique sur lien 'Know more':
![Dropdown Opened](https://i.ibb.co/Tmvx3bP/final-project-navbar-opened.png)

## Footer

Dans le `<footer>` affichez l'année en cours en modifiant le texte du `<span>` avec l'id `js-current-year`. Récupérez la date d'aujourd'hui avec l'objet [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) et sa méthode [getFullYear](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear).

![Footer](https://i.ibb.co/mFQ78x9/final-project-footer.png)

## Premier bloc

Créez un calculateur de [Body Mass Index](https://fr.wikipedia.org/wiki/Indice_de_masse_corporelle).

Pour calculer le BMI utilisez la formule suivante: poids / ((hauteur / 100) * (hauteur / 100)).
Ecrivez une construction `if` pour trouver le résultat:
Si l'indice est inférieur à 18.5, le résultat est `'considered underweight'`;
Si l'indice est égal ou supérieur à 18.5 ET égal ou inférieur à 25, le résultat est `'a healthy weight'`;
Si l'indice est supérieur à 25, le résultat est `'considered underweight'`;

Afficher le résultat sous le formulaire: 'Your Body Mass Index is INSERT_CALCULATED_BMI_HERE. It is INSERT_THE_RESULT_MESSAGE_HERE.'

**BONUS:** Utilisez une fonction reutilisable pour sélectionner, changer le texte et la visibilté de l'alerte.

<details>
  <summary>Step by step instructions</summary>

1. Interceptez la soumission du formulaire
2. Récupérez la valeur du champ de sasie 'Your weight'
3. Convertissez cette valeur en nombre
4. Récupérez la valeur du champ de sasie 'Your height'
5. Convertissez cette valeur en nombre
6. Calculez le BMI
7. Vérifiez que BMI n'est pas égal à [NaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) avec la méthode [isNaN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN)
8. Ecrivez la construction `if` pour determiner le résultat
9. Si BMI est égal à NaN, cachez l'alerte
10. Si BMI n'est pas égal à NaN, affichez l'alerte avec le résultat
</details>

Le résultat: 
![BMI Calculator](https://i.ibb.co/1TVN8sp/final-project-calculator.png)

## Deuxième bloc
```js
const bmiFacts = [
  {
    title: 'Future weight of children can be anticipated by BMI',
    description: 'Scientists in a new study have concluded that future weight can be forecasted by looking at children’s BMI. ',
    img: 'http://lorempixel.com/200/200/cats'
  },
  {
    title: 'Losing BMI weight lowers the risk of diabetes',
    description: 'New research established the fact that lowering BMI by almost five units dramatically lowers risk of diabetes, in spite of the initial weight of a person.',
    img: 'http://lorempixel.com/200/200/sports'
  },
  {
    title: 'Pre-pregnancy BMI is closely related to excess weight gain during pregnancy',
    description: 'Excessive weight gain during pregnancy affects the health of a mother and her baby, pre-pregnancy BMI and ethnicity might signal a likelihood for obesity later in life for young mothers.',
    img: 'http://lorempixel.com/200/200/fashion'
  },
  {
    title: 'Coronary heart disease is proportionate to Body Mass Index (BMI)',
    description: 'According to a research from the Million Women Study, Coronary heart disease (CHD) increases with age and also with an increase in body mass index (BMI).',
    img: 'http://lorempixel.com/200/200/food'
  },
];
```

Parcourez le tableau bmiFacts pour afficher la liste des faits sur BMI dans le `<div>` avec l'id `js-facts`.
Avant chaque titre ajoutez un nombre pour énumérer les cartes. Ce nombre sera dynamique et égal à l'indice de l'élément du tableau en cours de traitement plus un.
Au final, la structure HTML pour chaque fait sera suivante (remplacez le texte en majuscule par les valeurs dynamiques) :

```html
<div class="col col-12 col-sm-6 col-lg-3 mb-3">
  <div class="card h-100">
    <img src="URL_HERE" class="card-img-top">
    <div class="card-body">
      <h5 class="card-title">TITLE_HERE</h5>
      <p class="card-text">DESCRIPTION_HERE</p>
    </div>
  </div>
</div>
```

![BMI Facts](https://i.ibb.co/JHVsLdQ/final-project-facts.png)

## Troisième bloc

Ce bloc est une publicité. 

Si le bouton avec l'id `js-ad-close` est cliqué pour la première fois, récupérez l'url de publicité - la valeur de l'attribut `href` du lien qui entoure l'image publicitaire pour l'ouvrir dans un nouvel onglet :
```js
window.open(url, '_blank');
```

Si le lien est cliqué pour la deuxième fois, supprimez le div avec l'id `js-ad` du DOM et enlèvez l'écouteur d'événement `click` lui associé.

## Quatrième bloc

Créez un formulaire de contact qui comprend les champs suivants :

+ nom
+ prénom
+ promotion
+ email
+ date de naissance ([sélecteur de date](https://jqueryui.com/datepicker/) de jQuery UI)
+ message (textarea)

A la soumission du formulaire envoyez les informations saisies en format JSON (pas besoin de convertir l'objet en chaîne de caractèrs) à 
```
POST https://usebasin.com/f/ddec74dc7c7b
```
N'oubliez pas d'ajouter un header `Accept` égal à `application/json` à votre requête.

Si la requête est executée avec succès, afficher une alerte verte avec le texte `'Your message was sent successfully'` qui disparaît au bout de 3 secondes.

Si il y a une erreur survenue, affichez une alerte rouge avec le texte `'Oups! An error has occured, please, try again later'` qui disparaît au bout de 3 secondes.

Le CDN du datepicker:
+ JS: `https://code.jquery.com/ui/1.12.1/jquery-ui.min.js`
+ CSS: `https://code.jquery.com/ui/1.12.0/themes/smoothness/jquery-ui.css`

Formulaire de contact:
![Contact form](https://i.ibb.co/12WFvpf/final-project-contact-form.png)

Datepicker jQueryUI:
![Datepicker](https://i.ibb.co/5xShskG/final-project-contact-form-datepicker.png)


## Cookies

Vérifiez que l'objet localStorage est présent dans votre navigateur.
Si il est présent, vérifiez que l'entrée `cookiesAccepted` est presente dans localStorage et sa valeur est égale à `true`. Si c'est le cas, ne faites rien. Sinon affichez la bannière avec l'id `js-cookies`.
Au clique sur le bouton avec l'id `js-accept-cookies`, créez une entrée 'cookiesAccepted' égale à `true` et cachez la bannière avec l'id `js-cookies`.

![Cookies](https://i.ibb.co/xjd2YFM/final-project-cookies.png)

