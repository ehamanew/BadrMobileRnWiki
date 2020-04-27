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
            key="bureau"
            style={CustomStyleSheet.badrPicker}
            titleStyle={CustomStyleSheet.badrPickerTitle}
            title={translate('profile.listeBureaux')}
            cle="codeBureau"
            libelle="nomBureauDouane"
            module="REF_LIB"
            command="getListeBureaux"
            onValueChange={(selectedValue, selectedIndex) =>
              this.handleBureauChanged(selectedValue, selectedIndex)
            }
            param=""
            typeService="SP"
            storeWithKey="bureau"
          />

          <BadrPicker
            onRef={ref => (this.comboArrondissements = ref)}
            style={CustomStyleSheet.badrPicker}
            titleStyle={CustomStyleSheet.badrPickerTitle}
            key="arrondissements"
            style={CustomStyleSheet.badrPicker}
            title={translate('profile.listeArrondissements')}
            cle="code"
            libelle="libelle"
            module="REF_LIB"
            command="getArrondissementsByAgentAndBureau"
            onValueChange={(selectedValue, selectedIndex) =>
              this.handleArrondissementChanged(selectedValue, selectedIndex)
            }
            param={this.state.selectedBureau}
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
| onValueChange |                                             Callback sur le changement de la valeur du composant                                              |
| param         |                                                          Paramétre fourni au service                                                          |
| storeWithKey  |         Si cette cet attribut est mentionné, le composant sauvgardera à chaque fois la valeur sélectionnée dans le storage local du device avec la clé fournie.          |

### Recharger les donées du composants :

On peut recharger des données du composant en lui fournissant une référence comme suit :

```JSX
<BadrPicker onRef={ref => (this.comboArrondissements = ref)} ... />
```

Afin de pouvoir appeler la fonction refresh avec le nouveau paramétre :

```javascript
...
this.comboArrondissements.refresh(selectedValue);
...
```
