---
id: doc-badr-tree
title: Tree
---

### Visualisation du composant:

![badrpicker](assets/Tree.gif)

### Emplacement du composant:

> ./src/components/tree/BadrTree

### Utilisation du composant:

```javascript
import { BadrTree, BadrTreeItem } from "../../../components";
```

```JSX
...

<BadrTree
  getCollapsedNodeHeight={() => 60}
  data={this.props.data}
  onItemSelected={(item) => this.onItemSelected(item)}
  renderNode={({ node, level, isExpanded, hasChildrenNodes }) => {
    return (
      <BadrTreeItem
        node={node}
        level={level}
        isExpanded={isExpanded}
        hasChildrenNodes={hasChildrenNodes}
      />
    );
  }}
/>

...
```

### Liste des attributs :

| Attribut               |                            Description                             |
| ---------------------- | :----------------------------------------------------------------: |
| getCollapsedNodeHeight |                Hauteur de chaque élément de l'arbe                 |
| data                   |                Données à afficher en arboréscence.                 |
| onItemSelected         | Callback appelé lors de la séléction de chaque élément de l'arbre. |

> Les données doivent respecter le format suivant :

```json
[
  { "id": 4, "parent": 2 },
  { "id": 3, "parent": 2 },
  { "id": 2, "parent": 1 },
  { "id": 1, "parent": 0 }
]
```

