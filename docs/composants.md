---
id: composants
title: Composants
---

### 1. Aperçu théorique :

<p style='text-align: justify;'>React native fournit plusieurs composants prédéfinis, par contre vous pouvez écrire vos propres composants ou bien installer des composants tiers developpés par la communauté ReactNative.    
Les composants vous permettent de découper l’interface utilisateur en éléments indépendants et réutilisables. Pour communiquer des données entre les composants dans une arboréscence, il suffit de passer par les props.</p>

### 2. Aperçu pratique :

<p style='text-align: justify;'>Nous donnerons l'exemple du bouton "BadrButton" dans notre application, tous les composants sont situés dans le dossier : **./src/components/** et regroupés par type de composant (Button, TextInput...)</p>

Définition du composant dans le fichier **./src/components/Button**:

```javascript
const buildButton = (style, onPress, text, textStyle) => {
  return (
    <TouchableOpacity style={style} onPress={onPress}>
      <Text style={textStyle}>{text}</Text>
    </TouchableOpacity>
  );
};

export class BadrButton extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return buildButton(
      CustomStyleSheet.badrButton,
      this.props.onPress,
      this.props.text,
      CustomStyleSheet.badrButtonText
    );
  }
}
```

<p style='text-align: justify;'>Ce bouton est caractérisé par un ensemble de propriétés dont les deux onPress et text sont émises par le composant englobant via l'utilisation des props. (Notez bien qu'on peut même passer une fonction via les props).</p>

Utilisation du composant dans l'écran de login : 

```javascript
import {BadrButton} from '../../components/buttons/Button';
...
handleLogin = () => {
    ...
}
...
<BadrButton onPress={this.handleLogin} text={translate('login.connexion')} />
...
```
