---
id: doc-badr-basic-table
title: BadrTable
---

### Visualisation du composant:

![badrpicker](assets/badrTableBasic.png)

### Emplacement du composant:

> ./src/components/shared/tree/basic

### Utilisation du composant:

```javascript
import { BadrTable } from "../../components";
```

```JSX
...

<BadrTable
          rows={[]}
          cols={[]}
          onItemSelected={this.onItemSelected}
          totalElements={rowsLength}
          maxResultsPerPage={5}
          paginate={true}
  />

...
```

### Liste des attributs :

| Attribut          |                                           Description                                           |
| ----------------- | :---------------------------------------------------------------------------------------------: |
| rows              |                       Lignes à afficher sous forme d'un tableau d'objets                        |
| cols              |                      Colonnes à afficher sous forme d'un tableau d'objets                       |
| onItemSelected    | Callback appelé lors de la séléction de chaque élément du tableau, renvoi la ligne selectionnée |
| totalElements     |                                     Nombre total d'elements                                     |
| maxResultsPerPage |                                   Nombre d'elements par page                                    |
| paginate          |                          Flag pour autoriser la pagination coté client                          |

> Les données doivent respecter le format suivant :

```json
[
  { "id": 4, "parent": 2 },
  { "id": 3, "parent": 2 },
  { "id": 2, "parent": 1 },
  { "id": 1, "parent": 0 }
]
```
