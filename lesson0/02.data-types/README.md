# Types de données
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
+ [JavaScript.info](https://javascript.info/types)

## Types primitives
1. Ecrivez une chaîne de charactèrs
2. Ecrivez un nombre Integer
3. Ecrivez un nombre Float
4. Ecrivez un boolean
5. Ecrivez un valeur non définie
6. Ecrivez un valeur non existant

> Une collection d'examples de comportement non-evidant: [wtfjs](https://github.com/denysdovhan/wtfjs)

## Conversion de types primitives
+ EN: [JavaScript.info](https://javascript.info/type-conversions)
+ EN: [w3schools](https://www.w3schools.com/js/js_type_conversion.asp)

### String
+ Transformez la chaîne de charactèrs '1' en nombre (`1`)
+ Transformez la chaîne de charactèrs 'Hello' en nombre (`NaN`)
+ Transformez la chaîne de charactèrs '0' en nombre (`0`)
+ Transformez la chaîne de charactèrs '000' en nombre (`0`)
+ Transformez la chaîne de charactèrs '0' to boolean (`true` (!))
+ Transformez la chaîne de charactèrs '000' en boolean (`true`)
+ Transformez la chaîne de charactèrs 'twenty' en nombre (`NaN`)
+ Transformez la chaîne de charactèrs '1' en nombre with [`parseInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt) function (`1`)
+ Transformez la chaîne de charactèrs vide en boolean (`false`)
+ Transformez la chaîne de charactèrs vide en nombre (`0`)

### Number
+ Transformez le nombre 42 en chaîne de charactèrs avec la methode [`toString`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString) (`'42'`)
+ Transformez le nombre 0.4242 en chaîne de charactèrs avec la methode [`toFixed`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed) (`'0.42'`)
+ Transformez NaN en en chaîne de charactèrs (`'NaN'`)
+ Transformez le nombre 1 en boolean (`true`)
+ Transformez le nombre 0 en boolean (`false`)

### Boolean
+ Transformez false en chaîne de charactèrs (`'false'`)
+ Transformez false en nombre (`0`)
+ Transformez true en chaîne de charactèrs (`'true'`)
+ Transformez true en nombre (`1`)

### Null
+ Transformez null en chaîne de charactèrs (`'null'`)
+ Transformez null en nombre (`0`)
+ Transformez null en boolean (`false`)

### Undefined
+ Transformez undefined en chaîne de charactèrs (`'undefined'`)
+ Transformez undefined en nombre (`NaN`)
+ Transformez undefined en boolean (`false`)

### Conversion automatique
Effectuez les opérations arithmétiques suivantes et observez le résultat.
Expliquez dans un commentaire pourquoi les types sont convertis comme ça.
+ `'4' * '3' // explain here`
+ `'4' + 3`
+ `'4' - 3`
+ `4 + undefined`
+ `'4' + null`
+ `4 - null`