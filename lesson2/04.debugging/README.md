# Débogage

![End of coding](http://www.commitstrip.com/wp-content/uploads/2016/03/Strip-Reflexion-de-codeur-4-650-final.jpg)

> !!! Gardez toujours la console ouverte, elle est votre meilleur ami

Comment déboger mieux et pas seulement avec `console.log`: les [conseils](https://developers.google.com/web/tools/chrome-devtools/javascript/) d'experts Google pour les développeurs.

Débogguez ce code défectueux :

```js
'use strict';

myCharacter = 'Luna Lovegood';

myCharacterHouse = useSortingHat()

isMyCharacterRich = checkMyGringottAccount()

function useSortngHat(char) {
  let choice = ''
  
  if (ch = 'Harry Potter') {
    let choice = 'Gryffindor';
  } else (ch = 'Draco Malfoy') {
    let choice = 'Ravenclaw';
  } else (ch = 'Luna Lovegood') {
    choice = 'Ravenclaw';
  } elseif {
    ch = 'Gryffindor'
  }

  return '${char} goes to ${ch}'
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