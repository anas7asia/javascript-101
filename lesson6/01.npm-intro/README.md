# Introduction dans npm

> N'oubliez d'[installer](https://nodejs.org/en/download/) les dernières versions Node.js et npm

On utilise Node.js et [npm](https://docs.npmjs.com/about-npm/) (Node Packages Manager) pour sauvegarder et utiliser les dependences d'un projet.
Chaque projet npm doit avoir à sa racine un fichier `package.json` qui contient tous les informations relatives à ce projet. Au fur et à mesure de développement ce fichier est mis à jour.

```json
{
  "name": "my_package",
  "description": "",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    // les raccourcies de commandes
    "test": "echo \"Error: no test specified\" && exit 1",
    "build:dev": "webpack --mode development"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/ashleygwilliams/my_package.git"
  },
  "keywords": [],
  "author": "",
  "license": "MIT",
  "dependencies": {
    // librairies que vous avez besoin en production (sur le site final)
    // par exemple, jQuery, lodash, Timeline.js
    "jquery": "^3.3.1"
  },
  "devDependencies": {
    // plugins et libraries en stade de developpement
    // par exemple, webpack, autoprefixer pour compiler le code final
    "webpack": "^4.28.3",
  }
}
```

## Commandes npm

+ `npm init` pour créer un fichier `package.json`
+ `npm install` pour installer les dependences mentionnées dans `dependencies` et `devDependencies`
+ `npm install package-name-here` installer un package
+ `nom run some-script` exécuter un script précisé dans `package.json`
+ `npm -v` pour voir la version de npm utilisée
+ Voir toutes les commandes: <https://docs.npmjs.com/cli-documentation/cli>

C'est commandes sont exécutées en CLI dans Terminal (Mac) ou CommandLine (Windows)