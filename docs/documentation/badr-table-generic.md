---
id: doc-badr-generic-table
title: BadrApiTable
---

### Visualisation du composant:

![badrpicker](assets/badrTableGeneric.png)

### Emplacement du composant:

> ./src/components/shared/generic

### Utilisation du composant:

```javascript
import { BadrApiTable } from "../../components";
```

```JSX
...

      <BadrApiTable
          module="REF_LIB"
          command="getCmbTypeIdentifiant"
          typeService="SP"
          searchObject={{
            numeroVersionCourante: '3'
          }}
          maxResultsPerPage={5}
          onItemSelected={(item) => this.onItemSelected(item)}
          cols={[
            {
              code: 'code',
              libelle: 'Code',
              width: 100,
              action: (row) => this.onItemSelected(row),
            },
            {code: 'libelle', libelle: 'Libelle', width: 200},
          ]}
          paginate={true}
        />

...
```

### Liste des attributs :

| Attribut          |                                                                                                                                                             Description                                                                                                                                                             |
| ----------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| rows              |                                                                                                                                         Lignes à afficher sous forme d'un tableau d'objets                                                                                                                                          |
| cols              | Colonnes à afficher sous forme d'un tableau d'objets, on peut avoir une colonne de type action (checkbox, button..) il suffit d'ajouter l'attribut component qui permet de définir le type de composant responsable sur l'action puis l'attribut action dans lequel on définit le callBack qui va être appelé lors de l'événement., |
| onItemSelected    |                                                                                                                   Callback appelé lors de la séléction de chaque élément du tableau, renvoi la ligne selectionnée                                                                                                                   |
| totalElements     |                                                                                                                                                       Nombre total d'elements                                                                                                                                                       |
| maxResultsPerPage |                                                                                                                                                     Nombre d'elements par page                                                                                                                                                      |
| paginate          |                                                                                                                                           Flag pour autoriser la pagination coté serveur                                                                                                                                            |
| command           |                                                                                                                                                       Nom de la commande Badr                                                                                                                                                       |
| module            |                                                                                                                                                         Nom du module Badr                                                                                                                                                          |
| typeService       |                                                                                                                                                        Type de service Badr                                                                                                                                                         |
| searchObject      |                                                                                                                                             Objet pour filtrer les résultats retournés                                                                                                                                              |
