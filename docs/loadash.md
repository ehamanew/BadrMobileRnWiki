---
id: loadash
title: Loadash
---

### 1. Aperçu théorique :

<p style='text-align: justify;'>Loadash est une librairie Javascript qui fournit des fonctions utilitaires permettant de gagner énormément de temps et qui rendent le code plus propre et lisible.</p>

### 2. Aperçu pratique :

- Installation le package.json :

```json
"lodash": "^4.17.15",
```

- Import et utilisation :

Exemple au niveau du fichier : ./src/redux/reducers/menu.js

```javascript
import _ from 'lodash';
...
/** Filtrer les menus **/
 collection = _.filter(collection, action.value.predicate)
...
```

Quelques cas d'utilisation de Loadash :

```javascript
_.intersection([2, 1], [2, 3]);
// => [2]
```

```javascript
_.uniq([2, 1, 2]);
// => [2, 1]
```

```javascript
_.groupBy(['apple', 'banana', 'orange'], 'length');
// => { '0': ['apple'], '1': ['banana', 'orange'] }
```
