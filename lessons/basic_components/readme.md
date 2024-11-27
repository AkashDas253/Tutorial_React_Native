## **Basic Components in React Native**

React Native provides essential building blocks for creating a user interface. These **basic components** are commonly used in most apps and serve as the foundation for creating interactive and visually appealing applications.

---

### **1. View**

#### **Description**
The `View` component is the most fundamental building block of a UI in React Native. It acts as a container for other components and supports layout, styling, and touch handling.

#### **Syntax**
```javascript
<View {...props}>
  {children}
</View>
```

#### **Key Parameters**

| Parameter             | Default Value | Description                                                                 | Value Range        |
|-----------------------|---------------|-----------------------------------------------------------------------------|--------------------|
| `style`               | `undefined`  | Defines the layout and appearance of the view.                              | `object`           |
| `onLayout`            | `undefined`  | Callback for when the view is laid out.                                     | Function           |
| `accessibilityLabel`  | `undefined`  | Accessibility label for the component.                                      | `string`           |
| `pointerEvents`       | `'auto'`     | Determines how touch events interact with the view.                         | `'auto'`, `'none'`, `'box-only'`, `'box-none'` |

---

### **2. Text**

#### **Description**
The `Text` component is used to display text content in the app. It supports nesting, styling, and touch handling.

#### **Syntax**
```javascript
<Text {...props}>
  {content}
</Text>
```

#### **Key Parameters**

| Parameter             | Default Value | Description                                                                 | Value Range        |
|-----------------------|---------------|-----------------------------------------------------------------------------|--------------------|
| `style`               | `undefined`  | Defines the appearance of the text.                                         | `object`           |
| `numberOfLines`       | `undefined`  | Limits the number of displayed lines.                                       | `number`           |
| `ellipsizeMode`       | `'tail'`     | Controls how text is truncated.                                             | `'head'`, `'middle'`, `'tail'`, `'clip'` |
| `onPress`             | `undefined`  | Callback for handling press events.                                         | Function           |

---

### **3. Image**

#### **Description**
The `Image` component is used for displaying images, supporting both local and remote sources.

#### **Syntax**
```javascript
<Image source={require('path/to/image')} {...props} />
```

#### **Key Parameters**

| Parameter             | Default Value | Description                                                                 | Value Range        |
|-----------------------|---------------|-----------------------------------------------------------------------------|--------------------|
| `source`              | `undefined`  | Specifies the image source (local or remote).                               | `object`           |
| `resizeMode`          | `'cover'`    | Determines how the image is resized to fit its container.                   | `'cover'`, `'contain'`, `'stretch'`, `'repeat'`, `'center'` |
| `style`               | `undefined`  | Defines the size and shape of the image.                                    | `object`           |
| `onLoad`              | `undefined`  | Callback for when the image is loaded.                                      | Function           |

---

### **4. TextInput**

#### **Description**
`TextInput` is a component for entering text, providing options to customize behavior and appearance.

#### **Syntax**
```javascript
<TextInput {...props} />
```

#### **Key Parameters**

| Parameter             | Default Value | Description                                                                 | Value Range        |
|-----------------------|---------------|-----------------------------------------------------------------------------|--------------------|
| `value`               | `undefined`  | The current text in the input.                                              | `string`           |
| `placeholder`         | `undefined`  | Placeholder text displayed when the input is empty.                         | `string`           |
| `keyboardType`        | `'default'`  | Type of keyboard to display.                                                | `'default'`, `'numeric'`, `'email-address'`, `'phone-pad'` |
| `secureTextEntry`     | `false`      | If `true`, hides the text input (for passwords).                            | `true`, `false`    |
| `onChangeText`        | `undefined`  | Callback for handling text changes.                                         | Function           |

---

### **5. ScrollView**

#### **Description**
`ScrollView` is a container for enabling scrolling through child components. It supports both horizontal and vertical scrolling.

#### **Syntax**
```javascript
<ScrollView {...props}>
  {children}
</ScrollView>
```

#### **Key Parameters**

| Parameter             | Default Value | Description                                                                 | Value Range        |
|-----------------------|---------------|-----------------------------------------------------------------------------|--------------------|
| `horizontal`          | `false`      | If `true`, enables horizontal scrolling.                                    | `true`, `false`    |
| `contentContainerStyle` | `undefined` | Styling for the scrollable content.                                         | `object`           |
| `onScroll`            | `undefined`  | Callback for handling scroll events.                                        | Function           |
| `refreshControl`      | `undefined`  | Adds a pull-to-refresh feature.                                             | React component    |

---

### **6. StyleSheet**

#### **Description**
`StyleSheet` abstracts styling logic, similar to CSS, and improves performance by optimizing styles.

#### **Syntax**
```javascript
const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
  },
});
```

#### **Key Functions**

| Function             | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `StyleSheet.create`  | Creates a style object, improving app performance and consistency.          |
| `flatten`            | Merges multiple style objects into one.                                    |

---

