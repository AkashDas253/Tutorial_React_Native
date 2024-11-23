# React Native

## The Basics

### Introduction
React Native is a framework for building mobile applications using JavaScript and React. It allows developers to create apps for both iOS and Android using a single codebase. React Native uses native components, which means the app will have the look and feel of a native app.

### Core Components and Native Components
React Native provides a set of core components that are essential for building mobile applications. These components include:
- `View`: A container that supports layout with flexbox, style, touch handling, and accessibility controls.
- `Text`: A component for displaying text.
- `Image`: A component for displaying images.
- `ScrollView`: A scrollable container that can hold multiple components and views.
- `TextInput`: A component for text input.

Native components are platform-specific components that are written in native code (Objective-C, Swift, Java, Kotlin) and can be used in React Native applications.

### React Fundamentals
React Native is built on top of React, so understanding React fundamentals is crucial. Key concepts include:
- **JSX**: A syntax extension for JavaScript that looks similar to HTML and is used to describe the UI.
- **Components**: Reusable pieces of UI that can be functional or class-based.
- **Props**: Short for properties, props are used to pass data from parent to child components.
- **State**: An object that holds data that may change over the lifecycle of the component.
- **Lifecycle Methods**: Methods that are called at different stages of a component's lifecycle (e.g., `componentDidMount`, `componentDidUpdate`).

## Handling Text Input
Handling text input in React Native is done using the `TextInput` component. It supports various props for handling user input, such as `onChangeText`, `value`, `placeholder`, and more. Example:

```javascript
import React, { useState } from 'react';
import { View, TextInput, Text, StyleSheet } from 'react-native';

const App = () => {
  const [text, setText] = useState('');

  return (
    <View style={styles.container}>
      <TextInput
        style={styles.input}
        placeholder="Type here"
        onChangeText={setText}
        value={text}
      />
      <Text style={styles.text}>{text}</Text>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    padding: 20,
  },
  input: {
    height: 40,
    borderColor: 'gray',
    borderWidth: 1,
    marginBottom: 10,
  },
  text: {
    fontSize: 20,
  },
});

export default App;
```

## Using a ScrollView
`ScrollView` is a scrollable container that can hold multiple components and views. It is useful for displaying content that may not fit on the screen. Example:

```javascript
import React from 'react';
import { ScrollView, Text, StyleSheet } from 'react-native';

const App = () => {
  return (
    <ScrollView style={styles.container}>
      <Text style={styles.text}>Item 1</Text>
      <Text style={styles.text}>Item 2</Text>
      <Text style={styles.text}>Item 3</Text>
      {/* Add more items as needed */}
    </ScrollView>
  );
};

const styles = StyleSheet.create({
  container: {
    padding: 20,
  },
  text: {
    fontSize: 20,
    marginBottom: 10,
  },
});

export default App;
```

## Using List Views
For displaying a large list of data, `FlatList` and `SectionList` are commonly used components. `FlatList` is used for simple lists, while `SectionList` is used for lists with sections. Example of `FlatList`:

```javascript
import React from 'react';
import { FlatList, Text, View, StyleSheet } from 'react-native';

const DATA = [
  { id: '1', title: 'Item 1' },
  { id: '2', title: 'Item 2' },
  { id: '3', title: 'Item 3' },
];

const App = () => {
  const renderItem = ({ item }) => (
    <View style={styles.item}>
      <Text style={styles.title}>{item.title}</Text>
    </View>
  );

  return (
    <FlatList
      data={DATA}
      renderItem={renderItem}
      keyExtractor={item => item.id}
    />
  );
};

const styles = StyleSheet.create({
  item: {
    padding: 20,
    borderBottomWidth: 1,
    borderBottomColor: '#ccc',
  },
  title: {
    fontSize: 20,
  },
});

export default App;
```

## Troubleshooting
Common issues in React Native development include:
- **Build Errors**: Ensure all dependencies are correctly installed and linked.
- **Performance Issues**: Optimize rendering and avoid unnecessary re-renders.
- **Platform-Specific Bugs**: Test on both iOS and Android to catch platform-specific issues.

#### Platform-Specific Code
React Native allows you to write platform-specific code using file extensions (`.ios.js` and `.android.js`) or the `Platform` module. Example:

```javascript
import { Platform, StyleSheet } from 'react-native';

const styles = StyleSheet.create({
  container: {
    padding: Platform.OS === 'ios' ? 20 : 10,
  },
});
```

## More Resources
- **Official Documentation**: [React Native Docs](https://reactnative.dev/docs/getting-started)
- **Community**: Join forums, Slack channels, and GitHub discussions.
- **Tutorials**: Follow online tutorials and courses to deepen your understanding.
