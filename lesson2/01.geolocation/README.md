# Géolocalisation

+ [MDN > Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)
+ [w3school > Geolocation API](https://www.w3schools.com/html/html5_geolocation.asp)


> Continuez à travailler sur le formulaire de recherche de billets d'avion.

Tout d'abord vérifiez que votre navigateur supporte Geolocation API.

En cas négatif, mettez une bannière pour prévenir que ÇA FONCTIONNE PAS.
En cas positive, obtenez la longitude et la latitude de votre positionnement.

Si vous n'avez pas eu la permission d'avoir ces données, loggez 'Pity'.
Sinon faites une fausse appelle (*mock api call*) à un serveur distant qui retourne l'information sur la ville la plus proche aux long/lat fournies.
```js

getCityData() {
  const data = {
    ...
  }; // get the object in the file from this folder
  return data;
}

```

Vérifiez que vous avez réçu les données valides: id, code postale et nom de la ville sont présents.

Si c'est le cas, sauvegardez les données réçues dans sessionStorage et pre-remplissez le nom de la ville dans le champ "Départ de".
