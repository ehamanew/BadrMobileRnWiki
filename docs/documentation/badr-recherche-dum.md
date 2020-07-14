---
id: doc-badr-rechercheRefDum
title: rechercheRefDum
---

### Visualisation du composant:

![badrpicker](assets/rechercheRefDum.png)

### Emplacement du composant:

> ./src/components/modules/rechercheRefDum/index

### Utilisation du composant:

```javascript
import { RechercheRefDum } from "../../../components";
```

```JSX
...
       <RechercheRefDum
            module="CONTROL_LIB"
            commande={infoControle.commande}
            typeService="UC"
            navigation={this.props.navigation}
            successRedirection={infoControle.successRedirectionScreen}
            routeParams={this.props.route.params}
          />
...
```

### Liste des attributs :

| Attribut           |                    Description                     |
| ------------------ | :------------------------------------------------: |
| navigation         | Objet responsable sur la navigation du menu drawer |
| commande           |             Commande d'initialisation              |
| module             |             Commande d'initialisation              |
| typeService        |                Type de service Badr                |
| successRedirection |       Route de redirection en cas de succés        |
| routeParams        |            Paramétres de la redirection            |
| navigation         |              Object de la navigation               |
