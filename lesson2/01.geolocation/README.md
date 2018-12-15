# Géolocalisation

+ [MDN > Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)
+ [w3school > Geolocation API](https://www.w3schools.com/html/html5_geolocation.asp)

Tout d'abord vérifiez que votre navigateur supporte Geolocation API.

Essayez d'obtenir la longitude et la latitude de votre positionnement.

En cas d'échec, traitez les [erreurs](https://developer.mozilla.org/en-US/docs/Web/API/PositionError) suivantes: permission refusée par utilisateur, position undisponible, temps d'attente expiré, erreur non-connue. Loggez la raison d'échec.

Regardez les propriétés de l'objet [Position](https://developer.mozilla.org/en-US/docs/Web/API/Position).

Si vous avez réussi d'obtenir la latitude et la longitude, affichez une carte en forme d'image (sont `src` est égal à `"https://maps.googleapis.com/maps/api/staticmap?center=" + latitude + "," + longitude + "&zoom=13&size=300x300&sensor=false"`).

---

> Continuez à travailler sur le formulaire de recherche de billets d'avion.

Essayez d'obtenir latutide et longitude du positionnement d'utilisateur.
Définissez le temps maximum d'attente de réponse à 1 minute.
En cas de réussite, faites une fausse appelle (*mock api call*) à un serveur distant qui retourne les données de la ville la plus proche aux longitude et latitude fournies.

```js
getCityData(lat, long) {
  if (lat, long) {
    const data = {
      id: 23,
      zipcode: 33000,
      name: 'Bordeaux'
    }; // get the object in the file from this folder
    return data;
  }
  return
}
```

Vérifiez que vous avez réçu les données valides: id, code postale et nom de ville sont présents.
Si c'est le cas, sauvegardez les données réçues dans sessionStorage et remplissez le champ "Départ de" avec le nom de ville.


## Reading List 


+ [The Sweet Embrace of Big Brother: HTML5 Geolocation](https://medium.com/@tchryssos/the-sweet-embrace-of-big-brother-html5-geolocation-11c0d792d7e5)
+ [How to get user Latitude, Longitude & current address using HTML5](https://medium.com/cuelogic-technologies/how-to-get-user-latitude-longitude-current-address-using-html5-f15b76da57e9) 