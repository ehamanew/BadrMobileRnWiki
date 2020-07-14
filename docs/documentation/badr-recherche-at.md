---
id: doc-badr-rechercheRefAt
title: RechercheRefAt
---

### Visualisation du composant:

![badrpicker](assets/rechercheRefAt.png)

### Emplacement du composant:

> ./src/components/modules/rechercheRefAt/index

### Utilisation du composant:

```javascript
import { RechercheRefAt } from "../../../components";
```

```JSX
...
        <RechercheRefAt
          onApurManuelle={(reference) => this.apurManuelle(reference)}
          onApurAutomatique={(reference) => this.apurAutomatique(reference)}
        />
...
```

### Liste des attributs :

| Attribut          |                 Description                  |
| ----------------- | :------------------------------------------: |
| onApurManuelle    |   Callback si Apurement manuel est cliqué    |
| onApurAutomatique | Callback si Apurement automatique est cliqué |
