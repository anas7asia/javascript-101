# Canvas

[Canvas](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) est un élément HTML qui avec l'aide de JavaScript permet de dessiner des éléments graphiques: cercles, rectangles, lignes, courbes, texte - voir la [liste complète](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D) de méthodes 2D.


Pour aller plus vite et éviter de faire le calcul des positions X et Y, utilisez ce code pour récupérer X et Y à chaque clique de la souris:

```js
const canvas = document.querySelector('canvas');
const ctx = canvas.getContext('2d');

const getCoordinatesInCanvas = (canvasEl, event) => {
  const rect = canvasEl.getBoundingClientRect(); // récupérer la taille de <canvas> et sa position relative par rapport à la zone d'affichage
  const x = event.clientX - rect.left;
  const y = event.clientY - rect.top;
  console.log(`x: ${x}, y: ${y}`);
}
canvas.addEventListener('click', (event) => {
  getCoordinatesInCanvas(canvas, event);
})
```

---

Inspirez-vous des images ci-dessous pour dessiner les [personnages de Star Wars](https://dribbble.com/creativeflip) sur une canevas de 600px sur 600px avec l'id `js-canvas`. 

**Dart Vader** de [Filipe Carvalho](https://dribbble.com/shots/2439528-Darth-Vader-Flat-Design-Icon)
![Dart Vader](https://cdn.dribbble.com/users/1016246/screenshots/2439528/dribbble-02.png)

**Yoda** de [Filipe Carvalho](https://dribbble.com/shots/2439521-Yoda-Flat-Design-Icon)
![Yoda](https://cdn.dribbble.com/users/1016246/screenshots/2439521/dribbble-01.png)

**Palpatine** de [Filipe Carvalho](https://dribbble.com/shots/2440244-The-Emperor-Flat-Design-Icon)
![Palptin](https://cdn.dribbble.com/users/1016246/screenshots/2440244/dribbble-09.png)

**Ewok** de [Filipe Carvalho](https://dribbble.com/shots/2444880-Ewok-Flat-Design-Icon)
![Ewok](https://cdn.dribbble.com/users/1016246/screenshots/2444880/dribbble-14.png)

**Stormtrooper** de [Filipe Carvalho](https://dribbble.com/shots/2441852-Stormtrooper-Flat-Design-Icon)
![Stormtrooper](https://cdn.dribbble.com/users/1016246/screenshots/2441852/dribbble-10.png)
