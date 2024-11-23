## **Props**

Props (short for "properties") are used to pass data from parent components to child components in React. They are read-only and cannot be modified by the child component. Props allow components to be dynamic and reusable.

#### Types of Props

1. **Primitive Types**
   - **String**
   - **Number**
   - **Boolean**
   - **Null**
   - **Undefined**

2. **Complex Types**
   - **Object**
   - **Array**
   - **Function**
   - **React Elements**
   - **Custom Types (using PropTypes or TypeScript)**

#### Functions and Properties Related to Props

1. **Default Props**
   - Used to define default values for props if they are not provided by the parent component.
   ```javascript
   const Greeting = ({ name }) => <Text>Hello, {name}!</Text>;

   Greeting.defaultProps = {
     name: 'Guest',
   };
   ```

2. **Prop Types**
   - Used to enforce type checking on props. This can be done using the `prop-types` library or TypeScript.
   ```javascript
   import PropTypes from 'prop-types';

   const Greeting = ({ name }) => <Text>Hello, {name}!</Text>;

   Greeting.propTypes = {
     name: PropTypes.string,
   };
   ```

3. **Destructuring Props**
   - Props can be destructured directly in the function parameter list or within the function body.
   ```javascript
   const Greeting = ({ name }) => <Text>Hello, {name}!</Text>;
   // or
   const Greeting = (props) => {
     const { name } = props;
     return <Text>Hello, {name}!</Text>;
   };
   ```

4. **Passing Props**
   - Props are passed from parent to child components.
   ```javascript
   const App = () => {
     return (
       <View>
         <Greeting name="John" />
         <Greeting name="Jane" />
       </View>
     );
   };
   ```

5. **Accessing Props in Class Components**
   - In class components, props are accessed using `this.props`.
   ```javascript
   class Greeting extends React.Component {
     render() {
       return <Text>Hello, {this.props.name}!</Text>;
     }
   }
   ```

#### Example with All Concepts

```javascript
import React from 'react';
import PropTypes from 'prop-types';
import { View, Text } from 'react-native';

// Functional Component with Default Props and Prop Types
const Greeting = ({ name }) => {
  return (
    <View>
      <Text>Hello, {name}!</Text>
    </View>
  );
};

Greeting.defaultProps = {
  name: 'Guest',
};

Greeting.propTypes = {
  name: PropTypes.string,
};

// Class Component with Props
class App extends React.Component {
  render() {
    return (
      <View>
        <Greeting name="John" />
        <Greeting name="Jane" />
        <Greeting />
      </View>
    );
  }
}

export default App;
```

### Summary

- **Primitive Types**: String, Number, Boolean, Null, Undefined
- **Complex Types**: Object, Array, Function, React Elements, Custom Types
- **Default Props**: Define default values for props
- **Prop Types**: Enforce type checking on props
- **Destructuring Props**: Simplify access to props
- **Passing Props**: Pass data from parent to child components
- **Accessing Props in Class Components**: Use `this.props` to access props in class components

Props are essential for making components dynamic and reusable, allowing data to flow through the component tree.



## **Style and Layout Props in React Native**

React Native provides various props to customize the styling and layout of components. Below are the details of the common props, including **Image Style Props**, **Layout Props**, **Shadow Props**, **Text Style Props**, and **View Style Props**.

---

### **1. Props (General Overview)**

Props in React Native are used to pass data and configuration to components. Style and layout props are essential for customizing the appearance of components. These props are either standard styles or specific to components like images, text, or views.

### **2. Image Style Props**

These props define the appearance of an `Image` component in React Native.

#### **Common Props**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `resizeMode`            | `'cover'`        | Defines how the image should resize to fit its container.      | `'cover'`, `'contain'`, `'stretch'` |
| `borderRadius`          | `0`              | Radius of the image’s corners.                                | `number` (px, em, %)        |
| `opacity`               | `1`              | Controls the transparency of the image.                       | `0` to `1`                  |
| `tintColor`             | `undefined`      | Color to apply to the image to make it tinted.                 | `string` (color)             |
| `alignSelf`             | `stretch`        | Aligns the image within its parent container.                  | `'auto'`, `'flex-start'`, `'flex-end'`, `'center'`, `'baseline'`, `'stretch'` |
| `width`                 | `undefined`      | Width of the image.                                           | `number`, `'auto'`           |
| `height`                | `undefined`      | Height of the image.                                          | `number`, `'auto'`           |

---

### **3. Layout Props**

Layout props in React Native help in defining how components are arranged and positioned.

#### **Common Layout Props**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `flex`                  | `0`              | Flexbox factor for distributing space in a container.          | `number`                     |
| `flexDirection`         | `'column'`       | Defines the primary axis for layout (row or column).           | `'row'`, `'column'`          |
| `justifyContent`        | `'flex-start'`   | Aligns children along the main axis.                           | `'flex-start'`, `'center'`, `'flex-end'`, `'space-between'`, `'space-around'` |
| `alignItems`            | `'stretch'`      | Aligns children along the cross axis.                          | `'flex-start'`, `'center'`, `'flex-end'`, `'stretch'` |
| `position`              | `'relative'`     | Defines how the component is positioned in its parent container. | `'absolute'`, `'relative'`  |
| `top`, `left`, `right`, `bottom` | `undefined` | Define offset for absolute positioning.                        | `number` (px, em, %)        |
| `margin`, `padding`     | `0`              | Controls the space around and inside the component.            | `number` (px, em, %)        |
| `alignSelf`             | `'auto'`         | Aligns the component within its parent container.              | `'auto'`, `'flex-start'`, `'flex-end'`, `'center'`, `'baseline'`, `'stretch'` |
| `zIndex`                | `0`              | Controls the stacking order of components.                     | `number`                     |

---

### **4. Shadow Props**

Shadow props are used to apply shadow effects on iOS and Android devices, enhancing the depth and layering of components.

#### **Common Shadow Props (iOS)**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `shadowColor`           | `'#000'`         | The color of the shadow.                                      | `string` (color)             |
| `shadowOffset`          | `{width: 0, height: 2}` | The offset of the shadow.                                    | `{width: number, height: number}` |
| `shadowOpacity`         | `0.8`            | The opacity of the shadow.                                    | `0` to `1`                   |
| `shadowRadius`          | `3`              | The blur radius of the shadow.                                 | `number` (px)                |

#### **Common Shadow Props (Android)**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `elevation`            | `0`              | The elevation of the component, used to create a shadow.       | `number` (greater than `0`)  |

---

### **5. Text Style Props**

Text style props are used for styling `Text` components.

#### **Common Text Style Props**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `fontSize`              | `14`             | The size of the text.                                         | `number` (px, em, %)         |
| `fontWeight`            | `'normal'`       | The weight of the font.                                       | `'normal'`, `'bold'`, `'100'`, `'200'`, etc. |
| `lineHeight`            | `undefined`      | The height of each line of text.                              | `number` (px, em, %)         |
| `letterSpacing`         | `0`              | The space between letters.                                    | `number` (px, em, %)         |
| `textAlign`             | `'left'`         | Horizontal alignment of the text.                             | `'left'`, `'center'`, `'right'`, `'justify'` |
| `color`                 | `'#000'`         | The color of the text.                                        | `string` (color)             |
| `textDecorationLine`    | `'none'`         | Text decoration such as underline or line-through.            | `'none'`, `'underline'`, `'line-through'` |
| `textTransform`         | `'none'`         | Controls the capitalization of the text.                      | `'none'`, `'uppercase'`, `'lowercase'` |

---

### **6. View Style Props**

`View` components are used as containers, and their styling controls the overall layout and appearance of the app.

#### **Common View Style Props**

| Prop                   | Default Value    | Description                                                   | Value Range                  |
|------------------------|------------------|---------------------------------------------------------------|------------------------------|
| `backgroundColor`       | `undefined`      | Background color of the view.                                 | `string` (color)             |
| `borderWidth`           | `0`              | The width of the view’s border.                               | `number`                     |
| `borderColor`           | `undefined`      | Color of the border.                                          | `string` (color)             |
| `borderRadius`          | `0`              | Radius of the corners of the view.                            | `number` (px, em, %)         |
| `width`                 | `undefined`      | Width of the view.                                            | `number`, `'auto'`           |
| `height`                | `undefined`      | Height of the view.                                           | `number`, `'auto'`           |
| `overflow`              | `'visible'`      | Controls how child elements are clipped when they overflow.   | `'visible'`, `'hidden'`, `'scroll'` |
| `opacity`               | `1`              | Transparency of the view.                                     | `0` to `1`                   |

---

These props allow you to customize a variety of aspects of components in React Native, from layout and appearance to behavior and interactivity. For further information or examples of usage, feel free to ask!