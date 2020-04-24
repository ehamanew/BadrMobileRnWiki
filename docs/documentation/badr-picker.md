---
id: doc-badr-picker
title: BadrPicker
---

### Visualisation du composant:

![badrpicker](assets/badrPicker.gif)

### Emplacement du composant:

> ./src/components/pickers/BadrPicker

### Utilisation du composant:

```javascript
import BadrPicker from "../../components/pickers/BadrPicker";
```

```javascript

<BadrPicker
    style={{width: 400}}
    title="Profil"
    cle="codeProfil"
    libelle="libelleProfil"
    onValueChange={(selectedValue, selectedIndex) =>
      this.handleValueChanged(selectedValue, selectedIndex)
    }
    module="HAB_LIB"
    command="getListeProfil"
    typeService="SP"
/>

<BadrPicker
    style={{width: 400}}
    title="Type t6bis"
    cle="code"
    libelle="libelle"
    onValueChange={(selectedValue, selectedIndex) =>
      this.handleValueChanged(selectedValue, selectedIndex)
    }
    module="T6BIS_LIB"
    command="getAllTypeT6bis"
    typeService="SP"
/>

<BadrPicker
    style={{width: 400}}
    title="Type document"
    cle="code"
    libelle="libelle"
    module="REF_LIB"
    onValueChange={(selectedValue, selectedIndex) =>
      this.handleValueChanged(selectedValue, selectedIndex)
    }
    selectedValue="06"
    command="getCmbTypeIdentifiant"
    typeService="SP"
/>

```

### Liste des attributs :

| Attribut      |                                                                  Description                                                                  |
| ------------- | :-------------------------------------------------------------------------------------------------------------------------------------------: |
| style         |                                                              Style du composant                                                               |
| title         |                                                             Libelle du composant                                                              |
| cle           |                                         Identificateur unique de l'objet json affiché, exemple : code                                         |
| libelle       |                                            Libellé qui sera affiché dans la vue, exemple : libelle                                            |
| selectedValue | Valeur séléctionnée par défaut (correspond à l'attribut cle), exemple : selectedValue="06" pour afficher la valeur Passeport Diplomatique(06) |
| module        |                                                              Nom du module BADR                                                               |
| command       |                                                            Nom de la commande BADR                                                            |
| typeService   |                                                             Type de service BADR                                                              |
| onValueChange   |                                                          Callback sur le changement de la valeur du composant          

