# React Native Cheatsheet

React Native is a JavaScript framework for building mobile applications using React. It lets you use the same codebase for iOS and Android apps by enabling the use of React's component-based architecture and JavaScript for creating a cross-platform app. Here’s a comprehensive guide on **React Native** with a focus on syntax, core functions, and constructors, including parameter usage and default values.

---

## 1. **Core Syntax and Structure in React Native**

A React Native app typically consists of components, which are reusable, isolated pieces of code that define the app's user interface.

### Basic Syntax Example

```javascript
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

const App = () => {
  return (
    <View style={styles.container}>
      <Text>Hello, World!</Text>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#FFFFFF',
  },
});

export default App;
```

### Key Points
- **Importing Components**: `import { View, Text } from 'react-native';`
- **Functional Components**: Defined using arrow functions.
- **StyleSheet**: Used for defining styles in React Native.

## 2. **Core Components**

React Native offers a variety of built-in components. Here’s an overview of some commonly used ones:

| Component      | Description                                                  | Key Props                                        |
|----------------|--------------------------------------------------------------|--------------------------------------------------|
| **`View`**     | Basic container for views, can nest other components         | `style`, `onLayout`, `accessible`                |
| **`Text`**     | Renders text, supports inline styles                         | `style`, `numberOfLines`, `onPress`, `selectable`|
| **`Image`**    | Displays images from local or network sources                | `source`, `resizeMode`, `style`, `onLoad`        |
| **`Button`**   | Basic button component                                       | `title`, `onPress`, `color`, `disabled`          |
| **`TextInput`**| Input field for capturing text                               | `value`, `placeholder`, `style`, `keyboardType`  |
| **`ScrollView`**| Scrollable container for nested views                       | `horizontal`, `showsHorizontalScrollIndicator`   |
| **`FlatList`** | Efficient scrolling list for large data sets                 | `data`, `renderItem`, `keyExtractor`, `numColumns` |

### Example Usage of `TextInput`

```javascript
<TextInput
  style={styles.input}
  placeholder="Enter text"
  onChangeText={(text) => console.log(text)}
  defaultValue="Sample Text"
  keyboardType="default"
/>
```

---

## 3. **Function and Class Components**

React Native components can be created as either function or class components. Function components are more common in modern React Native applications, but class components are still used, especially when needing lifecycle methods.

### Function Component Example

```javascript
const MyComponent = () => {
  return <Text>Hello from Function Component</Text>;
};
```

### Class Component Example

```javascript
import React, { Component } from 'react';
import { Text } from 'react-native';

class MyComponent extends Component {
  render() {
    return <Text>Hello from Class Component</Text>;
  }
}
```

## 4. **Class Constructors and Lifecycle Methods**

In React Native, class components can use constructors and lifecycle methods. The constructor initializes state and binds event handlers.

### Syntax

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      data: null,
    };
  }

  componentDidMount() {
    // Fetch data or perform setup
  }

  render() {
    return <Text>Component Text</Text>;
  }
}
```

### Parameters and Default Values

| Parameter    | Default Value  | Usage                                                       | Value Range |
|--------------|----------------|-------------------------------------------------------------|-------------|
| **`props`**  | `{}`           | Used for receiving data from parent components              | `any`       |
| **`state`**  | `undefined`    | Local component state                                       | `any`       |

- **`componentDidMount`**: Executes after the component is mounted. Use for data fetching or initial setup.
- **`componentDidUpdate`**: Executes when the component’s props or state changes.
- **`componentWillUnmount`**: Cleans up resources when the component is unmounted.

## 5. **Core APIs and Functions**

React Native includes several APIs to handle animations, gestures, and network requests.

### `fetch()` - Network Request

The `fetch()` function is used to make network requests.

```javascript
fetch(url, {
  method: 'GET',
  headers: {
    Accept: 'application/json',
    'Content-Type': 'application/json',
  },
})
  .then((response) => response.json())
  .then((data) => console.log(data))
  .catch((error) => console.error(error));
```

### `useState` - State Management Hook

```javascript
import React, { useState } from 'react';

const MyComponent = () => {
  const [count, setCount] = useState(0);

  return (
    <Button title="Increment" onPress={() => setCount(count + 1)} />
  );
};
```

### Parameter List for Core APIs

| API Function  | Parameter     | Default Value     | Usage                                                     | Value Range           |
|---------------|---------------|-------------------|-----------------------------------------------------------|------------------------|
| `fetch`       | `url`         | -                 | URL endpoint for network request                          | `string` (URL)        |
| `fetch`       | `method`      | `GET`             | HTTP method for the request                               | `GET`, `POST`, etc.   |
| `useState`    | `initialValue`| -                 | Initial state value                                       | `any`                 |
| `setState`    | `value`       | -                 | New value for the state variable                          | `any`                 |

---

## 6. **Styling in React Native**

React Native styles are written in JavaScript, similar to CSS, using the `StyleSheet.create()` method.

```javascript
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

### Key Style Properties and Defaults

| Property        | Default       | Usage                                             | Value Range        |
|-----------------|---------------|---------------------------------------------------|--------------------|
| `flex`          | `0`           | Defines how a component should grow or shrink      | `number`           |
| `alignItems`    | `stretch`     | Aligns children along the cross-axis              | `center`, `flex-start`, `flex-end` |
| `justifyContent`| `flex-start`  | Aligns children along the main axis               | `center`, `flex-start`, `flex-end`, `space-between` |
| `backgroundColor`| `transparent`| Sets the background color of a component          | `color` (hex, rgba) |

---

## 7. **Navigating between Screens**

React Native uses `react-navigation` for routing and navigation in apps.

### Basic Stack Navigator Example

```javascript
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

### Stack Navigator Props

| Prop                | Default             | Usage                                                 | Value Range    |
|---------------------|---------------------|-------------------------------------------------------|----------------|
| `initialRouteName`  | First screen        | Sets the initial screen                               | `string`       |
| `screenOptions`     | `{}`                | Customizes screen styles                              | `object`       |
| `headerMode`        | `float`             | Determines header animation style                     | `float`, `screen`, `none` |

---

### Summary

React Native provides a rich environment to build mobile apps with JavaScript. Key concepts include:
- **Components**: Building blocks for UI.
- **State and Props**: Managing component data.
- **APIs and Hooks**: Functions like `fetch` and hooks like `useState`.
- **Navigation**: Uses libraries for managing screens.

This overview covered basic syntax, component properties, lifecycle methods, APIs, and styling. Let me know if you’d like further specifics on advanced topics like animations or device-specific functionalities!