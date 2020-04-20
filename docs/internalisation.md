---
id: internalisation
title: Internalisation
---

### 1. Aperçu théorique :
<p style='text-align: justify;'>
L'internationalisation d'une application mobile, abrégé i18n du fait des 18 lettres entre le « i » et le « n » de « internationalisation » consiste à préparer l'adaptation d'une application mobile Android à des langues et des cultures différentes. La librairie la plus recommandée pour React native est i18njs qui est une bibliothèque JavaScript facile à configurer pour pouvoir bébénificier des fonctionnalités d'i18n.</p>

### 2. Aperçu pratique :

Il y a 3 étapes principales dans le processus de traduction dans une application :

- **Détécter** <p style='text-align: justify;'>le langage : Nous détecterons la langue de l'appareil à l'aide de la librairie react-native-localize.</p>

Déclaration au niveau du package.json :

```json
 "react-native-localize": "^1.4.0",
```

- **Préparer** <p style='text-align: justify;'>le texte du langage : les fichiers de traduction dediés à chaque langage sont situés dans : ./src/common/translations/{fr} .</p>

Exemple :

```javascript
export default {
  login: {
    userName: "Nom d'utilisateur",
    password: 'Mot de pass',
    connexion: 'Connexion',
  },
  smsVerify: {
    message:
      'Veuillez saisir le code de vérification que vous avez reçu par SMS (compose de 6 chiffres)',
    confirm: 'Confirmer',
    ...
```

- **Traduire** : <p style='text-align: justify;'> Après les deux étapes ci-dessus, vous traduisez réellement le texte de votre application vers le texte de la langue de traduction. Nous utiliserons la bibliothèque i18n-js pour traduire nos textes.</p>

Déclaration au niveau du package.json :

```json
 "react-native-localize": "^1.4.0",
```

Import & Utilisation :

```javascript
/**  ./src/common/translations/i18n.js **/
import I18n from "i18n-js";

...

I18n.translations = {
  fr
};

...

export function translate(key) {
  return I18n.t(key);
}
```
Importez le fichier i18n :
```javascript
/**  ./src/screens/login/index.js **/
import { translate } from "../../common/translations/i18n";
```
Puis : 
```JSX
<BadrButton onPress={this.handleLogin} text={translate('login.connexion')}/>
```
