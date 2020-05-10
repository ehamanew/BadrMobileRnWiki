---
id: doc-badr-toolbar
title: Toolbar
---

### Visualisation du composant:

![badrpicker](assets/Toolbar.gif)

### Emplacement du composant:

> ./src/components/toolbar/index

### Utilisation du composant:

```javascript
import { Toolbar } from "../../../components";
```

```JSX
...
        <Toolbar
            navigation={this.props.navigation}
            icon="menu"
            title={translate('title')}
            subtitle={translate('subTitle')}
          />
...
```

### Liste des attributs :

| Attribut   |                  Description                  |
| ---------- | :-------------------------------------------: |
| navigation | Objet responsable sur la navigation du menu drawer |
| title      |               Titre du toolbar                |
| subtitle   |             Sous titre du toolbar             |
| icon       |               Icone du toolbar                |
