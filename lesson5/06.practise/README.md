
# Projet en jQuery

Créez un site du chateau viticole bordelais Fauxvin qui aimerait vendre ses produits. 

En haut de chaque page mettez un header avec les liens de navigation vers les autres pages du site.

En bas de chaque page mettez un footer avec la marque déposée et l'année en cours (2019).

### Première page

#### Présentation du produit.

Installez un carousel pour montrer 5 photos et leurs titres par dessus. Ces photos doivent defiler toutes les 7 secondes à la vitesse de 500 millisecondes.

Les plugins à utiliser: [slick](http://kenwheeler.github.io/slick/) ou [Owl Carousel](https://owlcarousel2.github.io/OwlCarousel2/)

```js
const carouselItems = [
  {
    title: 'Notre voisin',
    img: 'https://cdn.pixabay.com/photo/2016/07/17/21/45/landscape-1524808_1280.jpg'
  },
  {
    title: 'Notre vin',
    img: 'https://cdn.pixabay.com/photo/2015/07/20/18/01/wine-853109_1280.jpg'
  },
  {
    title: 'La vue de notre propriété',
    img: 'https://cdn.pixabay.com/photo/2017/02/14/03/03/germany-2064517_1280.jpg'
  },
  {
    title: 'Notre chateau',
    img: 'https://cdn.pixabay.com/photo/2018/11/20/18/29/castle-3827949_1280.jpg'
  },
  {
    title: 'Nos vignes',
    img: 'https://cdn.pixabay.com/photo/2018/11/19/20/35/vineyards-3826012_1280.jpg'
  }
] 
```

#### Histoire du chateau

Affichez l'histoire du chateau avec des balises `<p>`.

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit. In diam mauris, semper et tincidunt sed, interdum in est. Nam fermentum elementum augue in sollicitudin. Vestibulum lectus felis, mattis eu condimentum sit amet, laoreet a sem. Aliquam elementum ac purus convallis blandit. Maecenas consequat est sapien, eu porta tellus semper ac. Praesent mattis nibh risus. Sed lobortis metus varius convallis facilisis. Suspendisse sed nunc id dolor posuere molestie. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Donec quam libero, sagittis id facilisis id, commodo tincidunt augue. Praesent gravida tellus erat, sed convallis urna vestibulum eget. Aenean suscipit, massa finibus pellentesque vulputate, enim nunc dapibus justo, ac pellentesque quam augue eget nulla. Vivamus ac lacus nec orci euismod semper.

Maecenas et aliquam tortor, consequat laoreet mi. Praesent auctor imperdiet augue, quis elementum metus. Aenean sit amet ligula sed libero bibendum faucibus. Duis molestie aliquam vulputate. Etiam sed orci in arcu vulputate rutrum ut eu turpis. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nam vestibulum commodo leo, in blandit massa rutrum eu. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Suspendisse potenti.

Maecenas ac tellus vulputate, posuere dolor vitae, maximus turpis. Cras vitae nisl pharetra, porta ante quis, imperdiet massa. Nulla suscipit vulputate dapibus. Etiam feugiat consequat malesuada. Ut mollis sit amet leo vel scelerisque. Phasellus interdum felis tellus. Ut placerat magna vitae suscipit viverra. Vestibulum blandit pharetra tortor, et aliquet metus iaculis nec. Nam nec ligula velit. Morbi dignissim lectus in diam pulvinar, scelerisque lobortis velit vestibulum. Aenean malesuada ullamcorper leo ultricies vestibulum. Etiam dictum vestibulum est non convallis.

Nunc eu nunc ex. Quisque vel scelerisque quam. Sed non rutrum leo. Phasellus lacinia magna massa, ac vehicula erat consequat id. Maecenas nec orci eu neque sodales luctus ut a sem. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Morbi velit nisl, pulvinar rhoncus quam non, fermentum congue nisi. Duis bibendum commodo sapien semper iaculis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Maecenas vehicula a leo ac vestibulum. Nunc consequat vulputate massa, in vestibulum lacus sagittis quis. Quisque sed lectus ut augue facilisis laoreet.

Quisque eget dolor a ipsum mattis ultrices. Proin bibendum porttitor rutrum. In et facilisis ante, quis vulputate nisi. Nam bibendum ornare nunc vel tempor. In hac habitasse platea dictumst. Suspendisse rutrum bibendum arcu, ut euismod felis. Donec sagittis augue eros, ut lobortis augue facilisis nec. Curabitur in lorem vel lorem placerat faucibus. Phasellus ullamcorper nibh enim, vitae gravida velit condimentum non. Nulla elementum aliquam sollicitudin.
```

Au dessous de cette histoire, affichez une chronologie des événements de ce chateau avec le plugin [Timeline.js](https://ilkeryilmaz.github.io/timelinejs/)

```js

const timelineItems = [
  {
    year: '2000',
    img: 'https://cdn.pixabay.com/photo/2018/07/20/14/02/grapes-3550733__480.jpg',
    title: 'Duis pretium risus.',
    description: 'Sed tristique ut dui vitae volutpat. Nulla id erat eu risus sodales dignissim eget et sapien. Mauris dolor justo, tincidunt sed urna et, consectetur ultricies ipsum. Aliquam diam augue, suscipit quis euismod a, viverra eu sapien. Suspendisse sed venenatis est. Quisque mollis vulputate urna egestas consequat. Suspendisse potenti. Donec sed velit consequat, cursus velit at, ultricies eros.'
  },
  {
    year: '2005',
    img: 'https://cdn.pixabay.com/photo/2014/12/02/03/11/purple-grapes-553464__480.jpg',
    title: 'Sed sed lobortis.',
    description: 'Integer eget ex blandit, dignissim metus nec, bibendum turpis. Proin eu fermentum eros. Phasellus vulputate non justo eget pulvinar. Nunc bibendum ac leo at ullamcorper. Praesent sed ultrices tortor, et bibendum ante.'
  },
  {
    year: '2007',
    img: 'https://cdn.pixabay.com/photo/2017/08/18/19/48/grapes-2656259__480.jpg',
    title: 'Quisque elementum varius.',
    description: 'Cras pharetra tristique bibendum. Fusce nec dolor at orci viverra mollis. Interdum et malesuada fames ac ante ipsum primis in faucibus. Morbi lobortis, nunc nec tincidunt ultricies, nisi ligula blandit velit, vitae ornare neque arcu et sapien. Nullam ultricies magna lorem, nec mattis nulla volutpat in. Etiam eleifend congue maximus. Ut tristique mi quis ante tristique, in luctus ante interdum.'
  },
  {
    year: '2013',
    img: 'https://cdn.pixabay.com/photo/2018/07/20/14/03/grapes-3550742__480.jpg',
    title: 'Duis tristique, tortor.',
    description: 'Suspendisse at mauris ut elit tempor varius. Cras consectetur dolor in justo viverra, at tempor lectus sollicitudin. Nulla pellentesque tempus lectus, quis semper ipsum efficitur ut. Proin commodo tristique lobortis.'
  },
  {
    year: '2018',
    img: 'https://cdn.pixabay.com/photo/2016/03/09/09/20/grapes-1245739__480.jpg',
    title: 'Suspendisse vehicula volutpat.',
    description: 'Suspendisse interdum dolor sed nisl porttitor auctor. Donec sed lorem condimentum, malesuada lorem et, tincidunt justo. Mauris at vulputate elit. Aliquam erat dolor, porta non ullamcorper a, auctor in neque. Sed quis laoreet quam, sed consequat ex.'
  },
]

```

#### Navigation

En bas de la page mettez une flèche pour remonter tout en haut de la page à l'aide du plugin [AnchorScroll.JS](http://www.virgiliudiaconu.com/work/anchor-scroll).


### Deuxième page

Créez un formulaire de contact qui comprend les champs suivants :

+ nom
+ prénom
+ promotion
+ email
+ date de naissance ([sélecteur de date](https://jqueryui.com/datepicker/) de jQuery UI)
+ message (textarea)

A la soumission de formulaire envoyez les informations saisies en format JSON à 
```
POST https://usebasin.com/f/ddec74dc7c7b
```
N'oubliez pas d'ajouter un header `Accept` égal à `application/json` à votre requête.


### Troisième page

```js
const products = [
  {
    id: 1,
    name: "Chateau Fauxvin Un",
    desc: "The predominance of Merlot accounts for the wines' dark colour and red fruit aromas featuring oaky and spicy overtones. The wine starts out powerful and full-bodied on the palate, with a beautiful tannic structure, going on to reveal a long, fresh aftertaste.",
    wines: [
      { year: "2000", price: "35" },
      { year: "2007", price: "25" },
      { year: "2011", price: "21" },
      { year: "2012", price: "23" },
      { year: "2013", price: "18" },
      { year: "2014", price: "19.50" },
      { year: "2015", price: "25.50" }
    ]
  },
  {
    id: 2,
    name: "Chateau Fauxvin Deux",
    desc: "The wine has an ink-black colour and intense nose featuring concentrated fruit aromas combined with vanilla and toast. The bouquet follows through on the palate to reveal a rich, full-bodied wine with black-berry fruit and an impressively long, elegant aftertaste. The tannin is well-structured with a wonderful velvety texture.",
    wines: [
      { year: "2007", price: "70" },
      { year: "2009", price: "80.30" },
      { year: "2011", price: "70" }
    ]
  }
]
```

Créez un calculateur de prix d'une commande de vin.

Chateau Fauxvin possède deux type de vin : Fauxvin Un et Fauxvin Deux. 

Affichez ces deux types dans deux blocs séparés (l'un au dessus de l'autre).

Chaque bloc contiendra le nom du type de vin et la liste des bouteilles disponibles pour ce type. Chaque bouteille a les atributs : année, prix et champ de formulaire (de type nombre) pour renseigner le nombre de bouteilles souhaitées.

On peux commander autant de bouteilles de différentes années et de differentes types qu'on souhaite.

Le prix de livraison est 19 € pour moins de 6 bouteilles, gratuit à partir de 6 bouteillles.

A chaque changement de la quantité de bouteilles, calculez le prix total frais de port compris `$totalPrice`, le prix total de toutes les bouteilles `$winePrice`, le nombre de bouteilles `$bottlesCount`, le prix de livraison `$deliveryPrice` et affichez le texte suivant en-dessous de deux blocs :
```
Total de votre commande : $totalPrice.
$winePrice euros de vin (soit $bottlesCount bouteilles)
$deliveryPrice euros de frais de port / Frais de port offerts
```

Si aucun vin n'est choisi, activez l'attribut `disabled` du bouton de soumission du formulaire.

## Pour aller plus loin

Afin de passer la commande utilisez le service [Stripe](https://stripe.com/docs/stripe-js/reference) qui gère le nom et adresse de livraison ainsi que le paiement.



