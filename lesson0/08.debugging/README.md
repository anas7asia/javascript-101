# Débogage

![End of coding](http://www.commitstrip.com/wp-content/uploads/2016/03/Strip-Reflexion-de-codeur-4-650-final.jpg)

> !!! Gardez toujours la console ouverte, elle est votre meilleur ami

Comment déboger mieux et pas seulement avec `console.log`: les [conseils](https://developers.google.com/web/tools/chrome-devtools/javascript/) d'experts Google pour les développeurs.

Débogez ce code défectueux :

```js

myCharacter = 'Luna Lovegood';

myCharacterHouse = useSortingHat()

isMyCharacterRich = checkMyGringottAccount()

function useSortngHat(char) {
  let choice = ''
  
  switch (ch) {
    case 'Harry Potter':
      choice = 'Gryffindor';
    case 'Draco Malfoy':
      choice = 'Ravenclaw';
    case 'Luna Lovegood':
      choice = 'Ravenclaw';
    default:
      'Gryffindor'
  }
}

const checkMyGringottsAccount = () {
  myMoney = Math.random() * 100

  if (myMoney > 0 || myMoney < 30) {
    return 'Hello Weasley'
  } elseif ( myMoney > 30 ||  myMoney < 75 ) {
    return 'Hey, that's cool'
  } elseif {
    'You're reach!'
  }
}

```

## Reading List

+ [Eloquent JavaScript > Bugs and Errors](https://eloquentjavascript.net/08_error.html)