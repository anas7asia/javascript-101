# Configuration de Webpack

+ [Npm](https://docs.npmjs.com/)
+ [Webpack Concepts](https://webpack.js.org/concepts/)

## Introduction à npm

> N'oubliez d'[installer](https://nodejs.org/en/download/) les dernières versions Node.js et npm

On utilise Node.js et [npm](https://docs.npmjs.com/about-npm/) (Node Packages Manager) pour télécharger, gérer et utiliser les dependences d'un projet.
Chaque projet npm doit avoir à sa racine un fichier `package.json` qui contient toutes les informations relatives à ce projet. Au fur et à mesure du développement ce fichier est mis à jour.

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

## Webpack

Webpack est un système de construction (build) de fichiers et un outil qui permet de mieux organiser notre code, le regrouper et appliquer certaines transformations.
Il impacte aussi la structure de nos projets. Si on utilise Webpack, on met tous les fichiers sur lesquels on travaille dans le dossier `/src`. Les fichiers transformés par Webpack vont être ajoutés automatiquement dans le dossier `/dist`.

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

![Webpack](https://i.ibb.co/Rzcwk1k/webpack-is-coming.png)

Comment fonctionne Webpack?
```js
{
  test: /\.YOUR_FILE_EXTENSION$/, // il cherche tous les fichiers précisés dans "entry" avec un format spécifique
  exclude: /SOMETHING THAT IS THAT EXTENSION BUT SHOULD NOT BE PROCESSED/, // mais pas avec ce nom
  use: {
    loader: "loader for your file extension or a group of loaders" // ensuite il les pré-traite et leurs applique les transformations nécessaires
  }
}
```

Webpack ne connaît pas d'autres formats que `.js`, il faut donc installer les plugins (loaders) pour charger les fichiers .html, .css, les images, les polices, etc.


## Préparer l'environnement de travail

> Travaillez toujours dans le dossier `webpack-test`.

Créez un fichier `.gitignore` avec le contenu suivant qui interdira l'envoie de certains dossiers ou fichiers inutiles à partager sur GitHub :
```
node_modules/
dist/
```

Exécutez la commande suivante pour créez un fichier `package.json`. Répondez aux questions posées dans le terminal ou appuyez sur 'Enter' pour mettre la réponse par defaut.
```
npm init
```

Installez tout de suite la dernière version de `jQuery` parce qu'elle est utilisée dans le projet. jQuery se trouvera dans le dossier `node_modules`.

```
npm install jquery@latest --save
```

Ensuite installez `webpack` et `webpack-cli` dans votre projet en tant que dependences de développement :
```
npm install --save-dev webpack webpack-cli
```

Toujours dans le même dossier créez un fichier `webpack.config.js`. Copiez-collez la configuration de Webpack (il pourra la trouver automatiquement avec le nom du fichier) dans ce fichier.

<details>
  <summary>Voir la configuration</summary>

Cette configuration Webpack pour un site multipage permet de

1. Grouper les fichiers `.js` dans un seul ou plusieurs fichiers.
2. Transpiler le code ES6 en ES5 et le minifier.
3. Insérer dynamiquement les fichiers `.js` dans les fichiers `.html`.
4. Grouper, minifier, convertir en CSS et préfixer automatiquement les fichiers `.scss`.
5. Réduire le poids des images lourdes ou transformer en `Base64 URL` les images de moins de 10Ko.

```js
const path = require('path');
const HtmlWebPackPlugin = require("html-webpack-plugin");
const MiniCssExtractPlugin = require("mini-css-extract-plugin");

module.exports = (env, argv) => ({
	devServer: {
	    contentBase: path.join(__dirname, 'dist'),
	    compress: true,
	    port: 9000
	},
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
      },
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
  new MiniCssExtractPlugin({
    filename: argv.mode == 'development' ? '[name].css' : '[name].[hash].css', // '[name].[hash].css for production - hash this file, so users always will get the newest version of this file and not that one from cache
    })
  ]
});
```
</details>

Installez tous les plugins suivants :

[Babel](https://babeljs.io/docs/en/) pour transpiler le code **JavaScript** :
```
npm i -D babel-loader @babel/core @babel/preset-env 
```

Pour **HTML** :
```
npm install html-loader html-webpack-plugin --save-dev
```

Pour **CSS** :
```
npm install css-loader sass-loader postcss-loader autoprefixer node-sass mini-css-extract-plugin --save-dev
```

Pour les **images** :
```
npm i -D img-loader url-loader file-loader
```



<!-- ### HTML

Installez le plugin webpack pour charger des fichiers HTML :
```
npm install html-loader html-webpack-plugin --save-dev
``` -->
<!-- 
<details>
<summary>Voir la configuration</summary>

Ajoutez dans le fichier `webpack.config.js` l'import du plugin :
```js
const HtmlWebPackPlugin = require("html-webpack-plugin");
```

Ajoutez la propriété `entry` dans `module.exports` :
```js
// code that you work on in 'src' folder
entry: {
  vendor: './src/scripts/vendor.js', // all the not development dependencies from node_modules go here
  scripts: './src/scripts/scripts.js', // all the code shared between different pages goes here
  index: './src/scripts/index.js', // code specific to index page
  'contact-form': './src/scripts/contact-form.js', // code specific to contact-form page
},
```

Ajoutez la propriété `output` dans `module.exports` :
```js
output: {
  filename: argv.mode == 'development' ? '[name].js' : '[name].[hash].js', // '[name].[hash].js' for production
  path: path.resolve(__dirname, 'dist'), // folder where all tranformed files will be placed
}
```

Dans la propriété `rules` (qui est un tableau) de la propriété `module` de `module.exports` ajoutez le loader de html
```js
{
  test: /\.html$/,
  use: [{ 
    loader: "html-loader", 
    options: { minimize: true } 
  }]
}
```

Dans la propriété `plugins` (qui est un tableau) de `module.exports` ajoutez ces deux objets :
```js
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
  })
```
</details> -->


### CSS

Les [preprocesseur CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS_preprocessor) ajoutent les fonctionnalités qui n'existent pas dans CSS mais qui sont très utiles en stade de développement.

Dans cette exemple on va utiliser [SASS](http://sass-lang.com/) - le preprocesseur le plus populaire.

Avec la configuration Webpack ci-dessus il est possible de compiler scss en css, le minifier et ajouter les préfixes pour les 2 dernières versions des navigateurs modernes les plus repandus (Chrome, Firefox, Safari, Edge).

Le fichier `global.scss` est inséré dans `scripts.js` pour le rendre visible à Webpack.
<!-- 
<details>
<summary>Voir la configuration</summary>

Dans le fichier `webpack.config.js` ajoutez :
```js
const MiniCssExtractPlugin = require("mini-css-extract-plugin");
```

Dans la propriété `rules` de la propriété `module` de `module.exports` ajoutez les loaders de css
```js
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
}
```

Dans la propriété `plugins` de `module.exports` ajoutez ces deux objets :
```js
new MiniCssExtractPlugin({
  filename: argv.mode == 'development' ? '[name].css' : '[name].[hash].css', // '[name].[hash].css for production - hash this file, so users always will get the newest version of this file and not that one from cache
})
```
</details> -->


### JS

ES6 n'est pas supporté par tous les navigateurs modernes, il faut donc convertir (*transpiler*) les fichiers `.js` écrits en ES6 en ES5. Au passage on va minifier tous le code et grouper certains fichiers.

<!-- Les fichiers `.js` sont déjà mis dans la propriété `entry`. -->

<!-- <details>
  <summary>Voir la configuration</summary>

  ```js
  {
    test: /\.m?js$/,
    exclude: /node_modules/,
    use: {
      loader: 'babel-loader',
      options: {
        presets: ['@babel/preset-env'] // transpile ES6 to ES5
      }
    }
  }
  ```
</details> -->


Les scripts `vendor`, `scripts` et `index` sont chargés sur la page `index.html`
![Webpack Index page](https://i.ibb.co/yYBm6JG/webpack-index.png)

Les scripts `vendor`, `scripts` et `contact-form` sont chargés sur la page `contact-form.html`
![Webpack Contac Form page](https://i.ibb.co/qRKMHjm/webpack-contact-form.png)

### Images

Pour diminuer le nombre de requêtes envoyées on peut transformer toutes les petites images [en Base64 URL](https://stackoverflow.com/questions/11736159/advantages-and-disadvantages-of-using-base64-encoded-images).

Les grandes images doivent être optimisées en poids. Reduisez leurs poids automatiqument sans perdre en qualité avec Webpack.


<!-- <details>
<summary>Voir la configuration</summary>

Ajoutez un loader des images dans la propriété `module.rules` de `module.exports` :
```js
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
```
</details> -->

### Serveur de développement

Installez le plugin [webpack-dev-server](https://github.com/webpack/webpack-dev-server) dans le projet qui permet de recompiler votre code à chaque changement et de le visualisez à l'adresse : `http://localhost:9000`

```
npm install webpack-dev-server --save-dev
```

Dans `package.json` ajoutez la commande de lancement du serveur. On peut avoir plusieurs scripts séparés par une virgule :
```json
"scripts": {
  "start:dev": "webpack-dev-server"
}
```

Exécutez cette commande pour voir vos changements en temps réel :
```
npm run start:dev
```
> Attention! Si vous modifiez `webpack.config.js`, n'oubliez pas de relancer le serveur


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

Vous devez avoir les mêmes fichiers que sur l'image ci-dessous :

![Webpack-Dev](https://i.ibb.co/W5gbMN1/webpack-dev.png)

Exécutez celui pour le serveur de production :

```
npm run build:prod
```

Résultat:

![Webpack-Prod](https://i.ibb.co/fFv2mcY/webpack-prod.png)
<!-- 
## Pour aller plus loin

Créez la configuration de [Hot Module Replacement](https://webpack.js.org/concepts/hot-module-replacement/) - le moyen de mettre à jour la page avec le nouveau code sans refraîchir cette page. -->