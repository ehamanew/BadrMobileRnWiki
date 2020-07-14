---
id: doc-badr-accordion
title: Accordion
---

### Visualisation du composant:

![badrpicker](assets/Accordion.gif)

### Emplacement du composant:

> ./src/components/shared/accordion/index

### Utilisation du composant:

```javascript
import { Accordion } from "../../../components";
```

```JSX
...
        <Accordion title={translate('title')}>
            <View> children here... </View>
        </Accordion>
...
```

### Liste des attributs :

| Attribut               |                            Description                             |
| ---------------------- | :----------------------------------------------------------------: |
| title |                Titre de l'accordion                 |
