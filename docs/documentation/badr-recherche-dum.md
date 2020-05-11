---
id: doc-badr-rechercheRefDum
title: rechercheRefDum
---

### Visualisation du composant:

![badrpicker](assets/rechercheRefDum.png)

### Emplacement du composant:

> ./src/components/rechercheRefDum/index

### Utilisation du composant:

```javascript
import { RechercheRefDum } from "../../../components";
```

```JSX
...
        <RechercheRefDum
        navigation={this.props.navigation}
        commande={'initControlerDedRI'}
        successRedirection={this.getSuccessRedirectionScreen()}
      />
...
```

### Liste des attributs :

| Attribut           |                    Description                     |
| ------------------ | :------------------------------------------------: |
| navigation         | Objet responsable sur la navigation du menu drawer |
| commande           |             Commande d'initialisation              |
| successRedirection |       Route de redirection en cas de succés        |
