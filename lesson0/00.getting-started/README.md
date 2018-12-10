# Avant commencer

![IDE](http://www.commitstrip.com/wp-content/uploads/2015/04/Strip-Ce-que-le-codeur-detest-dans-lIDE-650-final.jpg)

Pour écrire du code vous pouvez utiliser NotePad, vim (comme un pro!) ou un IDE (Integrated Development Environment).
Les IDEs les plus populaire sont:

+ VSCode 💖
+ WebStorm (payant)
+ SublimeText
+ Atom

Utiliser les raccourcis est gangner du temps. Voilà la liste de raccoucis de VSCode pour [Mac](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf) et [Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)


## Commentaires

N'oubliez pas d'utiliser les commentaires JavaScript d'une ligne (*inline*) et de plusieurs lignes (*multiline*). C'est un moyen de faciliter le travail à nos collegues et nous-même dans l'avenir.

```js
// quick inline commment

/*
I am 
so
multiline
*/

```

## Code style

Le plus important en façon d'écrire du code est être cohérent. Il faut se mettre d'accord avec l'équipe ou soi-même quels règles de syntax et d'indentation on va utiliser.
[Airbnb](https://github.com/airbnb/javascript) et [Google](https://google.github.io/styleguide/jsguide.html) ont crée leurs styleguides que chaqu'un est libre de suivre (ou pas). 

Si vous avez une hésitation comment bien indenter votre code ou mettre / ne pas mettre les crochets, retournez voir le styleguide choisi.

Pour automatiser ce processus, vous pouvez installer un *code linter* [ESLint](https://eslint.org/) dans votre projet ou en global.

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
4.1 Avec vim
```
vi .eslintrc
```
4.2 Ou avec VSCode
Dans VSCode ouvrez [*Command Palette*](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette) en appuyant Ctrl+Shift+P (Windows) ou (Cmnd+Shift+P) et choisissez "Shell Command: Install 'code' command in PATH command".

Ensuite retournez au terminal et lancez
```
code .eslintrc
```

5. Ajouter ce code dans le ficher et sauvgardez
```json
{
 "extends": "airbnb",
 "env": {
 "node": true,
 "es6": true,
 "browser": true
 },
 "rules": { }
}
```

6. Installez l'extension ESLint dans la partie des [extensions sur VSCode](https://code.visualstudio.com/docs/editor/extension-gallery)
