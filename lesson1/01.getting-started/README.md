# Avant commencer

![IDE](http://www.commitstrip.com/wp-content/uploads/2015/04/Strip-Ce-que-le-codeur-detest-dans-lIDE-650-final.jpg)

Pour écrire du code vous pouvez utiliser NotePad, vim (comme un pro!) ou un IDE (Integrated Development Environment).
Les IDEs les plus populaire sont:

+ VSCode 💖
+ WebStorm (payant)
+ SublimeText
+ Atom

Utiliser des raccourcis est gangner du temps. Voici la liste de raccoucis de VSCode pour [Mac](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf) et [Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)


## Commentaires

N'oubliez pas d'utiliser les commentaires JavaScript d'une ligne (*inline*) et de plusieurs lignes (*multiline*). C'est un moyen de faciliter le travail aux collegues et nous-même dans l'avenir.

```js
// quick inline commment

/*
I am 
so
multiline
*/

```

## Langue de développement

Toutes les lettres d'Unicode peuvent être utilisé pour écrire du code, ça veut dire que c'est possible de le faire en français, anglais, russe, chinois ou n'importe quelle autre langue.
Généralement la meilleure pratique est d'écrire le code et les commentaires en anglais.

![Coding in French](http://www.commitstrip.com/wp-content/uploads/2015/08/Strip-à-la-française-650-final.jpg)


## Préparer l'espace de travail

<details>
<summary>Utiliser GitHub Desktop</summary>

1. Connectez-vous sur <https://github.com>.

2. Installez [git](https://git-scm.com/book/fr/v2) sur votre ordinateur : <https://git-scm.com/book/fr/v2/Démarrage-rapide-Installation-de-Git>.

3. Téléchargez et installez l'application Github Desktop : <https://desktop.github.com/>.

4. Lancez l'application Github Desktop, connectez-vous avec votre compte GitHub.

5. Créez un nouveau projet *privé* et publiez-le.

6. Ajoutez l’utilisateur `anas7asia` en tant que collaborateur: https://github.com/YOUR_USER_NAME/YOUR_PROJECT_NAME/settings/collaboration

> A la fin de chaque cours n'oubliez pas de [faire un commit et l'envoyer sur le serveur GitHub](https://help.github.com/desktop/guides/contributing-to-projects/committing-and-reviewing-changes-to-your-project/).

</details>


<details>
<summary>Utiliser git avec CLI</summary>

1. Installez [git](https://git-scm.com/book/fr/v2) sur votre ordinateur : <https://git-scm.com/book/fr/v2/Démarrage-rapide-Installation-de-Git>

2. Connectez-vous sur <https://github.com>.

3. [Créez un nouveau projet](https://help.github.com/articles/create-a-repo/) **privé** et **sans** README.md.

4. Sur votre ordinateur allez dans un dossier où vous voulez placez votre projet à l'aide de [CLI](https://www.w3schools.com/whatis/whatis_cli.asp) :
```
cd path/to/your/folder/
```

5. Dans le dossier choisi clonez le projet Github `javascript-101-template` :
```
git clone https://github.com/anas7asia/javascript-101-template.git
```

6. Rentrez dans votre dossier :
```
cd javascript-101-template
```

7. Changez l'origin du projet en éxécutant les commandes suivantes une par une. **Attention**, utilisez l'adresse du projet que vous venez de créer au lieu de *URL_TO_YOUR_GITHUB_REPO.git*
```
git remote rename origin upstream
git remote add origin URL_TO_YOUR_GITHUB_REPO.git
git push -u origin master
```

8. Ajoutez l’utilisateur `anas7asia` en tant que collaborateur: https://github.com/YOUR_USER_NAME/YOUR_PROJECT_NAME/settings/collaboration


A la fin de chaque cours n'oubliez pas de faire un commit et l'envoyer sur le serveur GitHub
```
// dans votre projet
git add .
git commit -m "YOUR COMMIT NAME"
git push origin master
```
</details>


## Code style

![Indent your code properly](http://www.commitstrip.com/wp-content/uploads/2013/02/Strips-Indentation-600-final.jpg)

Le plus important lorsqu'on écrit du code est d'être consistant. Il faut se mettre d'accord avec l'équipe ou soi-même sur les règles de syntax et d'indentation que l'on va utiliser.
[Airbnb](https://github.com/airbnb/javascript) et [Google](https://google.github.io/styleguide/jsguide.html) ont créé leurs styleguides que chacun est libre de suivre (ou pas). 

Si vous avez une hésitation sur la manière d'indenter votre code, retournez voir le styleguide choisi.
Pour automatiser ce processus, vous pouvez installer un *code linter* [ESLint](https://eslint.org/) dans votre projet ou en global.

Comment installer ESLint en local?

1. Installez la dernière version de [NodeJS](https://nodejs.org/en/download/) sur votre ordinateur.

2. *(Optionnel si vous êtes déjà dans le bon dossier)* Ouvrez le programme Terminal (Mac) ou Command Prompt (Windows) et allez à la racine de votre projet avec la commande `cd`.
```
cd /Users/yourname/path/to/project/javascript-101-template
```

3. La configuration de ce projet est déjà prête, il ne reste plus qu'à installer les dependences nécessaires avec la commande :
```
npm install
```

4. Installez le plugin ESLint dans votre IDE.

<details>
<summary>
Installer ESLint en global
</summary>

Comment [installer ESLint en global](https://medium.com/@davidchristophersally/how-to-set-up-eslint-in-vscode-globally-253f25fbaff9) (pour utiliser les mêmes reglès sur tous vos projets) et l'utiliser avec VSCode?

1. Installez la dernière version de [NodeJS](https://nodejs.org/en/download/) sur votre ordinateur.

2. Installez les modules eslint et les règles Airbnb
```
npm install --global eslint eslint-config-airbnb-base eslint-plugin-import
```

3. Créez le ficher de config ESLint
```
touch .eslintrc
```

4. Ouvrez ce fichier 
<!-- 4.1 Avec vim
```
vi .eslintrc
```
4.2 Ou avec VSCode
Dans VSCode ouvrez [*Command Palette*](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette) en appuyant Ctrl+Shift+P (Windows) ou (Cmnd+Shift+P) et choisissez "Shell Command: Install 'code' command in PATH command".

Ensuite retournez sur le terminal et exécutez: 
```
code .eslintrc
``` -->

5. Ajoutez ce code dans le ficher et sauvegardez
```json
{
 "extends": "airbnb",
 "env": {
 "node": true,
 "es6": true,
 "jquery": true,
 "browser": true
 },
 "rules": { }
}
```

6. Installez l'extension ESLint dans la partie des [extensions sur VSCode](https://code.visualstudio.com/docs/editor/extension-gallery)
</details>