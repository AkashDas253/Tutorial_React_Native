## **User Interface Components in React Native**

React Native provides platform-agnostic **user interface controls** that work seamlessly across iOS and Android. Below are the details for **`Button`** and **`Switch`**, including their syntax, parameters, default values, usage, and value ranges.

---

## **1. Button**

### **Description**
The `Button` component is used for touchable interactions in a UI. It is simple to use and designed to render consistently across platforms.

### **Syntax**
```javascript
<Button {...props} />
```

### **Key Parameters**

| Parameter       | Default Value | Description                                                                 | Value Range            |
|-----------------|---------------|-----------------------------------------------------------------------------|------------------------|
| `title`         | `undefined`  | Text displayed on the button.                                               | `string`               |
| `onPress`       | `undefined`  | Callback function triggered when the button is pressed.                     | Function               |
| `color`         | `undefined`  | Background color of the button (Android only).                              | Any valid color value  |
| `disabled`      | `false`      | If `true`, the button is not interactive.                                   | `true`, `false`        |
| `accessibilityLabel` | `undefined` | Accessibility label for screen readers.                                    | `string`               |

---

## **2. Switch**

### **Description**
The `Switch` component is a toggle control used for boolean inputs. It allows the user to switch between two states, such as `on` and `off`.

### **Syntax**
```javascript
<Switch {...props} />
```

### **Key Parameters**

| Parameter           | Default Value | Description                                                                 | Value Range           |
|---------------------|---------------|-----------------------------------------------------------------------------|-----------------------|
| `value`             | `false`      | Determines the state of the switch (`true` for on, `false` for off).        | `true`, `false`       |
| `onValueChange`     | `undefined`  | Callback function triggered when the value changes.                         | Function              |
| `disabled`          | `false`      | If `true`, the switch is non-interactive.                                   | `true`, `false`       |
| `thumbColor`        | `undefined`  | Color of the switch's thumb when not active.                                | Any valid color value |
| `trackColor`        | `{ false: undefined, true: undefined }` | Object with colors for the track (inactive and active states).              | `{false: color, true: color}` |
| `ios_backgroundColor` | `#ffffff`  | Background color for the switch (iOS only).                                 | Any valid color value |

---

These components provide basic and essential controls for user interactions, ensuring consistent rendering across platforms.