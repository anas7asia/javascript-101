# Configuration de Webpack

+ [Webpack Concepts](https://webpack.js.org/concepts/)
+ []()

c'est 
Webpack est un système de construction (build) de fichiers et un outil qui permet de mieux organiser notre code, le regrouper, appliquer certaines transformations.
Il impacte aussi la structure de nos projets. Si on utilise Webpack, on met tous les fichiers sur lesquels on travaille dans le dossier `/src`. Les fichiers transformés par Webpack vont se trouver dans le dossier `/dist`.

```
package.json
webpack.config.js
-- src
  -- assets
    -- styles
    -- images
  -- scripts
  index.html
-- dist

```

Pas à pas on va créer un fichier de configuration Webpack pour un site multipage qui permettra de

1. Grouper les fichiers `.js` dans un seul ou plusieurs fichiers
2. Transpiler le code ES6 en ES5 et le minifier
3. Insérer dynamiquement les fichiers `.js` dans les fichiers `.html`.
4. Grouper, minifier, convertir en CSS et préfixer automatiquement les fichiers `.scss`.

Pour avoir la configuration complète, il vous suffit de copier coller ensemple la configuration de toutes les parties et installer les plugins nécessaires.

![Webpack](https://i.ibb.co/Rzcwk1k/webpack-is-coming.png)

Comment fonctionne webpack?
```js
{
  test: /\.YOUR_FILE_EXTENSION$/, // il cherche tous les fichiers précisé dans "entry" avec certain format
  exclude: /SOMETHING THAT IS THAT EXTENSION BUT SHOULD NOT BE PROCESSED/, // mais pas avec ce nom
  use: {
    loader: "loader for your file extension or a group of loaders" // ensuite il les prétraite et leurs applique transformations nécessaires
  }
}
```

Webpack connaît pas d'autres formats que `.js`, donc il faut installer les loaders pour charger les fichiers .html, .css, des images, des polices, etc.

## Webpack

> Travaillez dans le dossier `webpack-test`.

Créez un fichier `.gitignore` avec le contenu suivant qui interdira envoyer certains dossiers ou fichiers lourds ou inutiles à partager :
```
/node_modules
/dist
```

Créez un fichier `package.json` avec la commande :
```
npm init
```

Ensuite installez `webpack` et `webpack-cli` dans votre projet en tant que les dependences de développement :
```
npm install --save-dev webpack webpack-cli
```

Toujours dans le même dossier créez un fichier `webpack.config.js` où vous allez mettre toute la configuration de Webpack (webpack pourra la trouver automatiquement par le nom du fichier) :

```js
module.exports = (env, argv) => ({

});
```

### Serveur de développement

Installez le plugin [webpack-dev-server](https://github.com/webpack/webpack-dev-server) dans le projet qui permet de recompiler votre code à chaque changement et le visualisez à l'adresse : `http://localhost:9000`

```
npm install webpack-dev-server --save-dev
```

Ajoutez la configuration
```js
module.exports = (env, argv) => ({
  devServer: {
    contentBase: path.join(__dirname, 'dist'),
    compress: true,
    port: 9000
  }
});

```

Dans `package.json` ajoutez la commande du lancement du serveur :
```json
"scripts": {
  "start:dev": "webpack-dev-server"
}
```

Executez cette commande pour voir vos changements en live:
```
npm run start:dev
```
> Attention! Si vous modifiez `webpack.config.js`, n'oubliez pas de relancer le serveur

### HTML

Installez le plugin webpack pour charger des fichiers HTML :
```
npm install html-webpack-plugin --save-dev
```

<details>
<summary>Voir la configuration</summary>

```js
const path = require('path');
const HtmlWebPackPlugin = require("html-webpack-plugin");

module.exports = (env, argv) => ({
  // code that you work on in 'src' folder
  entry: {
    vendor: './src/scripts/vendor.js', // all the not development dependencies from node_modules go here
    scripts: './src/scripts/scripts.js', // all the code shared between different pages goes here
    index: './src/scripts/index.js', // code specific to index page
    'contact-form': './src/scripts/contact-form.js', // code specific to contact-form page
  },
  // compiled code
  output: {
    filename: argv.mode == 'development' ? '[name].js' : '[name].[hash].js', // '[name].[hash].js' for production
    path: path.resolve(__dirname, 'dist'), // folder where all tranformed files will be placed
  },
  module: {
    rules: [
      {
        test: /\.html$/,
        use: [{ 
          loader: "html-loader", 
          options: { minimize: true } 
        }]
      },
    ]
  },
  plugins: [
    // create an instance of HtmlWebPackPlugin for every page of a multipage website
    new HtmlWebPackPlugin({
      template: "src/index.html", // take html from this path
      filename: "./index.html", // name it 'index.html' and insert to the root of output folder
      chunks: ['vendor', 'scripts', 'index'] // insert dymamically vendor.js, scripts.js and index.js to index.html
    }),
    new HtmlWebPackPlugin({
      template: "src/contact-form.html",
      filename: "./contact-form.html",
      chunks: ['vendor', 'scripts', 'contact-form']
    }),
  ]
});
```
</details>



### CSS

Les [preprocesseur CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor) ajoutent les fonctionnalités qui n'existent pas dans CSS mais qui sont très utiles en stade de développement.

Dans cette exemple on va utiliser [SASS](http://sass-lang.com/), le preprocesseur le plus populaire.

La configuration suivante permet de compiler scss en css, le minifier et ajouter les préfixer pour les 2 dernières versions des navigateurs modernes les plus repandus (Chrome, Firefox, Safari, Edge).

Tous d'abord installez les packages suivants :
```
npm install css-loader sass-loader postcss-loader autoprefixer node-sass mini-css-extract-plugin --save-dev
```

Le fichier `global.scss` est inséré dans `scripts.js` pour le rendre visible à Webpack.

<details>
<summary>Voir la configuration</summary>

Toujours dans `webpack.config.js` rajoutez:
```js
const MiniCssExtractPlugin = require("mini-css-extract-plugin");

module.exports = (env, argv) => ({
  module: {
    rules: [
      {
        test: /\.(sa|sc|c)ss$/, // look for .sass, .scss or .css files
        use: [
          MiniCssExtractPlugin.loader, // minify css files
          "css-loader", // translate CSS to JavaScript
          { 
            loader: "postcss-loader", // perform some actions on compiled css
            options: {
              plugins: [require("autoprefixer")] // add prefixes to css properties if needed for browsers mentioned in 'browserslist' property in package.json
            }
          },
          "sass-loader" // convert SASS/SCSS to css
        ],
      },
    ],
  },
  plugins: [
    new MiniCssExtractPlugin({
      filename: argv.mode == 'development' ? '[name].css' : '[name].[hash].css', // '[name].[hash].css for production - hash this file, so users always will get the newest version of this file and not that one from cache
    })
  ]
});

```
</details>


### JS

ES6 n'est pas supporté par tous les navigateurs modernes, donc il faut convertir (*transpiler*) les fichiers .js écrits en ES6 en ES5. Au passage on va minifier tous le code et grouper certains fichiers.

Installez le plugin [Babel](https://babeljs.io/docs/en/) responsable de transpilation :
```
npm i -D babel-loader @babel/core @babel/preset-env 
```

Les fichiers `.js` sont déjà mis dans la propriété `entry`, il reste qu'à ajouter le loader pour exécuter les actions nécessaires :
```js
module.exports = (env, argv) => ({
  module: {
    rules: [
      {
        test: /\.m?js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
          options: {
            presets: ['@babel/preset-env'] // transpile ES6 to ES5
          }
        }
      },
    ]
  }
});
```


// TODO: image how specific to a page scripts are not loaded at once

### Images

Pour diminuer le nombre de requêtes envoyées on peut transformer les toutes petites images [en Base64 URL](https://stackoverflow.com/questions/11736159/advantages-and-disadvantages-of-using-base64-encoded-images) parce que le poids d'header est superieur au poids de l'image elle-même.

Grandes images doivent être optimisées en poids. Reduisez leurs poids automatiqument sans perdre en qualité avec Webpack.

Tous d'abord installez les plugins necessaires:
```
npm i -D img-loader url-loader file-loader
```

<details>
<summary>Voir la configuration</summary>

```js

module.exports = (env, argv) => ({
  module: {
    rules: [
      // convert an image lighter than 10.000 bytes to Base64 URL
      // otherwise reduce its size
      {
        test: /\.(png|jpe?g)/i,
        use: [
          {
            loader: "url-loader",
            options: {
              name: "./assets/images/[name].[ext]",
              limit: 10000 // 10k bytes
            }
          },
          {
            loader: "img-loader"
          }
        ]
      }
    ]
  }
});
```
</details>

## Compilation

Si vous avez terminé le développement de votre site, il est temps de builder votre code pour le mettre sur un serveur. Ça veut dire exporter le code optimisé dans le dossier `dist`.

Ajoutez ces scripts dans le fichier `package.json` :
```json
  "scripts": {
    "build:dev": "webpack --mode development",
    "build:prod": "webpack --mode production"
  }
```

Exécutez celui pour le serveur de développement :

```
npm run build:dev
```

Résultat:

![Webpack-Dev](https://i.ibb.co/W5gbMN1/webpack-dev.png)

Exécutez celui pour le serveur de production :

```
npm run build:prod
```

Résultat:
![Webpack-Prod](https://i.ibb.co/fFv2mcY/webpack-prod.png)

## Pour aller plus loin

Créez la configuration de [Hot Module Replacement](https://webpack.js.org/concepts/hot-module-replacement/) - le moyen de mettre à jour la page avec le nouveau code sans refraîchir cette page.