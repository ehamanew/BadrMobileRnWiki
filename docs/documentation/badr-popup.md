---
id: doc-badr-popup
title: Popup
---

### Visualisation du composant:

![badrpicker](assets/Badrpopup.gif)

### Emplacement du composant:

> ./src/components/messages/index

### Utilisation du composant:

```javascript
import { BadrPopup } from "../../../components";
```

```JSX
...
         <BadrPopup
            message={this.state.message}
            type={this.state.messageType}
            visible={this.state.messageVisibility}
            onClosePressed={this.onCloseMessagesPressed}
          />
...
```

### Liste des attributs :

| Attribut       |             Description              |
| -------------- | :----------------------------------: |
| message        |           Message du popup           |
| type           | type du popup [warn, error, success] |
| visible        |         Visibilité du popup          |
| onClosePressed |  Callback sur la fermeture du popup  |
