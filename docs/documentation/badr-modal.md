---
id: doc-badr-modal
title: Modal
---

### Visualisation du composant:

![badrpicker](assets/BadrModal.gif)

### Emplacement du composant:

> ./src/components/shared/modal/BadrModal

### Utilisation du composant:

```javascript
import { BadrModal } from "../../../components";
```

```JSX
...

 <BadrModal visible={this.state.visible} onDismiss={this.onDismiss}>

    ... children ...

  </BadrModal>
...
```

### Liste des attributs :

| Attribut  |             Description             |
| --------- | :---------------------------------: |
| visible   |         Visibilité du modal         |
| onDismiss | Callback sur la fermeture du modal. |

