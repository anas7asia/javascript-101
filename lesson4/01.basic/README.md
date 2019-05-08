# Foctionnalités de base

+ [ready](https://api.jquery.com/ready/)
+ [Selectors](https://api.jquery.com/category/selectors/)
+ [w3schools](https://www.w3schools.com/jquery/jquery_selectors.asp)

## Document

Logguez dans la console `'My page is ready'` quand le rendu de la page sera terminé.

## Selecteurs

```html
<div>First paragraph</div>
<div class="js-paragraph">Second paragraph</div>
<div class="js-paragraph">Third paragraph</div>
<div id="js-unique-paragraph">Fourth paragraph</div>

<article>
  <h1>Title</h1>
  <h2>Another title</h2>
  <h3>Small title 1</h3>
  <h3>Small title 2</h3>
  <h3>Small title 3</h3>
  <a href="https://example.com" target="_blank">External article link</a>
  <a href="https://my-website.com">Internal article link</a>
</article>

<table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th> 
    <th>Age</th>
  </tr>
  <tr>
    <td>Anne</td>
    <td>Smith</td> 
    <td>18</td>
  </tr>
  <tr>
    <td>Michel</td>
    <td>Erikson</td> 
    <td>19</td>
  </tr>
</table>

<form>
  <input type="text" placeholder="My input">
  <input type="button" value="My button">
</form>
```

Quand le rendu de la page sera terminé, utilisez les selecteurs jQuery pour sélectionner et logguer:

+ toutes les balises `<div>`
+ toutes les balises avec le nom de classe `js-paragraph`
+ la balise avec l'id `js-unique-paragraph`
+ le premier titre `<h3>`
+ le premier `<th>` du premier `<tr>` 
+ le premier `<td>` du chaque `<tr>`
+ tous les liens
+ tous les lien externes (ceux qui ont l'attribut `target` égal à `_blank`)
+ tous les lien internes (ceux qui n'ont pas d'attribut `target` égal à `_blank`)
+ tous les boutons dans un formulaire