---
id: storage
title: Async sotrage
---

### 1. Aperçu théorique :

<p style='text-align: justify;'>L'async storage peut s'avérer très utile lorsque nous voulons enregistrer des données que l'application devrait utiliser, même lorsque l'utilisateur l'a fermée ou a même fermé l'appareil. Il est recommandé d'utiliser une abstraction au-dessus d'AsyncStorage au lieu d'AsyncStorage directement.</p>

Les actions de base à effectuer dans AsyncStorage sont les suivantes:
1. Définir un élément, ainsi que sa valeur
2. Récupérer la valeur d'un article
3. Supprimer un élément

 ### 2. Aperçu pratique :

- Installation : au niveau du package.json
```json
"@react-native-community/async-storage": "^1.9.0",
```
- Import et utilisation :

L'abstraction au-dessus de l'asyncstorage a été faite au niveau du fichier : ./src/services/storage-service.js

```javascript
import AsyncStorage from '@react-native-community/async-storage';

export const save = async (key, value) => {
  return AsyncStorage.setItem(key, value);
};

export const load = async key => {
  const value = await AsyncStorage.getItem(key);
  if (value !== null) {
    return value;
  }
  return '';
};
```
Ces deux fonctions asynchrones permette de sauvegarder et de récupérer une valeur par clé unique.

- Exemple de sauvegarde: 

```javascript
import {save} from '../../services/storage-service';

...

save('user', JSON.stringify(data)).then(() => data.login);
```

- Exemple de récupération: 

```javascript
import {load} from '../../services/storage-service';

...
load('listFonctionnaliteVOs')
      .then(data => {
          ...
      });
```


