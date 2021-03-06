---
id: doc-badr-picker
title: Picker
---

### Visualisation du composant:

![badrpicker](assets/badrPicker.gif)

### Emplacement du composant:

> ./src/components/shared/pickers/BadrPicker

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
| cle           |                                         Identificateur unique de l'objet json affich??, exemple : code                                         |
| libelle       |                                            Libell?? qui sera affich?? dans la vue, exemple : libelle                                            |
| selectedValue | Valeur s??l??ctionn??e par d??faut (correspond ?? l'attribut cle), exemple : selectedValue="06" pour afficher la valeur Passeport Diplomatique(06) |
| module        |                                                              Nom du module BADR                                                               |
| command       |                                                            Nom de la commande BADR                                                            |
| typeService   |                                                             Type de service BADR                                                              |
| onValueChange |                                             Callback sur le changement de la valeur du composant                                              |
| param         |                                                          Param??tre fourni au service                                                          |
| storeWithKey  |         Si cette cet attribut est mentionn??, le composant sauvgardera ?? chaque fois la valeur s??lectionn??e dans le storage local du device avec la cl?? fournie.          |

### Recharger les donn??es du composants :

On peut recharger des donn??es du composant en lui fournissant une r??f??rence comme suit :

```JSX
<BadrPicker onRef={ref => (this.comboArrondissements = ref)} ... />
```

Afin de pouvoir appeler la fonction refresh avec le nouveau param??tre :

```javascript
...
this.comboArrondissements.refresh(selectedValue);
...
```
