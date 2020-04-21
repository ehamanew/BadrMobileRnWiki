---
id: exemple0
title: SimpleCounter
---

<p style='text-align: justify;'>
Cet exemple aide à comprendre comment les composants de React Native partagent leur données (data) dans un contexte parent & enfant.</p>

On commence tout d'abord par la création des composants :

**1) Modifiez le fichier App.js :**

```javascript
import React from "react";
import { View } from "react-native";
/** Composant qui contient le bouton qui incrémente la valeur du state.**/
import Counter from "./src/screens/Counter";
/** Composant 1 qui afficher la valeur envoyée.**/
import Watcher from "./src/screens/WatcherOne";
/** Composant 2 qui afficher la valeur envoyée.**/
import WatcherTwo from "./src/screens/WatcherTwo";

export default class App extends React.Component {
  /** State local avec l'attribut value **/
  state = {
    value: 0,
  };

   /** Fonction qui permet d'incrémenter la valeur en modifiant le state local. **/
  increment = () => {
    this.setState({ value: this.state.value + 1 });
  };

  render() {
    return (
       /** Passage de la valeur et de la fonction aux composants fils . **/
      <View>
        <Counter value={this.state.value} increment={this.increment} />
        <Watcher value={this.state.value} />
        <WatcherTwo value={this.state.value} />
      </View>
    );
  }
}
```

**2) Ensuite créez le composant Counter qui permet d'incrémenter la valeur du state du composant parent:**

```javascript
import {Button} from 'react-native';
import React from 'react';

class Counter extends React.Component {
  state = {
    value: 0,
  };

  increment = () => {
    this.props.increment();
  };

  render() {
    return <Button title="Increment" onPress={this.increment} />;
  }
}

export default Counter;
```

**3) On doit maintenant créer les composants watchers qui seront notifiés des changements du parent Watcher et WatcherTwo :**


```javascript
import {Text, View, StyleSheet} from 'react-native';
import React from 'react';

class Watcher extends React.Component {
  render() {
    return <Text style={styles.counterWatcherOne}>{this.props.value}</Text>;
  }
}

const styles = StyleSheet.create({
  counterWatcherOne: {
    fontSize: 40,
    textAlign: 'center',
  },
});

export default Watcher;
```

Et : 

```javascript
import {Text, StyleSheet} from 'react-native';
import React from 'react';

class WatcherTwo extends React.Component {
  render() {
    return <Text style={styles.counterWatcherOne}>{this.props.value}</Text>;
  }
}

const styles = StyleSheet.create({
  counterWatcherOne: {
    fontSize: 40,
    textAlign: 'center',
  },
});

export default WatcherTwo;
```

> De cette manière on a pu communiquer des informations et même des fonctions entre différents composants React native en utilisant les props.

