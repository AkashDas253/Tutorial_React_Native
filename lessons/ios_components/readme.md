# **iOS Components and APIs in React Native**

React Native also provides several components and APIs designed specifically for **iOS**. These components offer access to iOS-specific functionality, often wrapping UIKit classes. Below is the detailed note on **`ActionSheetIOS`**, a key iOS-specific component.

---

## **1. ActionSheetIOS**

### **Description**
`ActionSheetIOS` provides a way to display an **iOS-style action sheet** or **share sheet**. An action sheet is a modal that displays a set of options, such as actions to take or a menu of choices, usually at the bottom of the screen.

### **Syntax**
```javascript
import { ActionSheetIOS } from 'react-native';
```

### **Key Functions**

| Function                          | Description                                                               | Value Range            |
|-----------------------------------|---------------------------------------------------------------------------|------------------------|
| `showActionSheetWithOptions`      | Displays an action sheet with a set of options.                            | `options: array, callback: function` |
| `showShareActionSheetWithOptions` | Displays a share sheet for sharing content (e.g., text, images, etc.).     | `options: object, callback: function` |

### **showActionSheetWithOptions** Parameters

| Parameter                   | Default Value  | Description                                                               | Value Range           |
|-----------------------------|----------------|---------------------------------------------------------------------------|-----------------------|
| `options`                   | `[]`           | An array of strings, each representing an option in the action sheet.      | `array of strings`    |
| `cancelButtonIndex`         | `undefined`    | Index of the option that should be considered the cancel button.           | `number`              |
| `destructiveButtonIndex`    | `undefined`    | Index of the option that should be styled as destructive (e.g., red button). | `number`            |
| `anchor`                    | `undefined`    | Refers to a UI component (e.g., button) to anchor the action sheet to (iOS only). | `React component`  |
| `userInterfaceStyle`        | `undefined`    | User interface style (`light` or `dark` theme).                           | `string` (`'light'`, `'dark'`) |
| `tintColor`                 | `undefined`    | Color of the options in the action sheet.                                  | `string` (color)      |

### **showShareActionSheetWithOptions** Parameters

| Parameter                   | Default Value  | Description                                                               | Value Range           |
|-----------------------------|----------------|---------------------------------------------------------------------------|-----------------------|
| `url`                       | `undefined`    | The URL to be shared (can be an image, link, etc.).                       | `string`              |
| `message`                   | `undefined`    | The message to be shared.                                                  | `string`              |
| `subject`                   | `undefined`    | The subject of the share.                                                 | `string`              |
| `excludedActivityTypes`     | `undefined`    | Array of strings representing activity types to be excluded (e.g., Mail). | `array of strings`    |
| `tintColor`                 | `undefined`    | Tint color for the share sheet's action buttons.                           | `string` (color)      |

---

### **Usage**
- **ActionSheetIOS** is particularly useful when you need to provide a choice of actions to the user that are relevant to the context, such as confirming an action, deleting an item, or opening a menu of options.
- The `showActionSheetWithOptions` function displays the action sheet with customizable options, cancel button, and destructive button. The `showShareActionSheetWithOptions` function displays a share sheet that allows the user to share content to other apps.

---

This API provides an elegant and iOS-native way to display options to users. 