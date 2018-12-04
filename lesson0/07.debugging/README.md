# Débogage

![End of coding](http://www.commitstrip.com/wp-content/uploads/2016/03/Strip-Reflexion-de-codeur-4-650-final.jpg)

> !!! Gardez toujours la console ouverte, elle votre méilleur ami

Comment déboger mieux et ne pas qu'avec `console.log`: les [conseils](https://developers.google.com/web/tools/chrome-devtools/javascript/) de Google pour les développeurs.

Entrainez-vous avec ce code bugué:

```js
availableCharacters = ['Harry Potter', 'Luna Lovegood', 'Draco Malfoy']

myCharacter = availableCharacters[0];

myCharacterHouse = useSortingHat()

isMyCharacterRich = checkMyGringottsAccount()

function useSortingHat(char) {
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
