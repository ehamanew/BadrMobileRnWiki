---
id: doc-badr-picker-checker
title: PickerChecker
---

### Visualisation du composant:

![badrpicker](assets/badrPickerChecker.gif)

### Emplacement du composant:

> ./src/components/pickers/BadrPickerChecker

### Utilisation du composant:

```javascript
import BadrPickerChecker from "../../components/pickers/BadrPickerChecker";
```

```javascript
<BadrPickerChecker
  key="profil"
  title={translate("profile.listeProfils")}
  titleStyle={CustomStyleSheet.badrPickerTitle}
  style={CustomStyleSheet.badrPicker}
  cle="codeProfil"
  libelle="libelleProfil"
  module="HAB_LIB"
  command="getListeProfil"
  onValueChange={(selectedValue, selectedIndex) =>
    this.handleProfileChanged(selectedValue, selectedIndex)
  }
  param=""
  typeService="SP"
  onConfirm={this.handleOnConfirmProfils}
  onSelectedItemObjectsChange={this.handleOnProfilItemsChanged}
/>
```

### Liste des attributs :

| Attribut                    |                                                                  Description                                                                  |
| --------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------: |
| style                       |                                                              Style du composant                                                               |
| title                       |                                                             Libelle du composant                                                              |
| cle                         |                                         Identificateur unique de l'objet json affiché, exemple : code                                         |
| libelle                     |                                            Libellé qui sera affiché dans la vue, exemple : libelle                                            |
| selectedValue               | Valeur séléctionnée par défaut (correspond à l'attribut cle), exemple : selectedValue="06" pour afficher la valeur Passeport Diplomatique(06) |
| module                      |                                                              Nom du module BADR                                                               |
| command                     |                                                            Nom de la commande BADR                                                            |
| typeService                 |                                                             Type de service BADR                                                              |
| onValueChange               |                                             Callback sur le changement de la valeur du composant                                              |
| param                       |                                                          Paramétre fourni au service                                                          |
| onSelectedItemObjectsChange |         Callback appelé lors d'un changement sur la liste des données, ce callback renvoi une collection de clés relatives aux nouvelles valeurs         |

> N.B : On peut utliser onSelectedItemObjectsChange pour récuperer les éléments sélectionnées de la liste :
>```javascript
> handleOnProfilItemsChanged = items => {
>   this.setState({selectedProfiles: items});
> };
> ```

### Recharger les données du composants :

On peut recharger des données du composant en lui fournissant une référence comme suit :

```JSX
<BadrPicker onRef={ref => (this.comboArrondissements = ref)} ... />
```

Afin de pouvoir affeler la fonction refresh :

```javascript
...
this.comboArrondissements.refresh(selectedValue);
...
```
