# **Android Components and APIs in React Native**

React Native offers several components and APIs that are specifically designed for **Android**. These components provide wrappers for commonly used Android classes, enabling developers to access platform-specific functionality on Android devices.

---

## **1. BackHandler**

### **Description**
`BackHandler` allows you to handle hardware back button presses on Android. This is useful for implementing custom back navigation behavior or preventing default back navigation in specific scenarios.

### **Syntax**
```javascript
import { BackHandler } from 'react-native';
```

### **Key Functions**

| Function              | Description                                                           | Value Range      |
|-----------------------|-----------------------------------------------------------------------|------------------|
| `addEventListener`    | Adds an event listener to detect hardware back button presses.        | Function         |
| `removeEventListener` | Removes the event listener for back button presses.                   | Function         |
| `exitApp`             | Exits the app when invoked.                                           | `void`           |

---

## **2. DrawerLayoutAndroid**

### **Description**
`DrawerLayoutAndroid` is a component that provides a sliding menu (drawer) on the left or right side of the screen, often used for navigation in Android apps.

### **Syntax**
```javascript
import { DrawerLayoutAndroid } from 'react-native';
```

### **Key Parameters**

| Parameter               | Default Value | Description                                                               | Value Range           |
|-------------------------|---------------|---------------------------------------------------------------------------|-----------------------|
| `drawerWidth`           | `300`         | Width of the drawer when open.                                             | `number`              |
| `renderNavigationView`  | `undefined`   | A function that renders the content inside the drawer (menu).              | React component       |
| `onDrawerOpen`          | `undefined`   | Callback when the drawer is opened.                                        | Function              |
| `onDrawerClose`         | `undefined`   | Callback when the drawer is closed.                                        | Function              |
| `drawerPosition`        | `'left'`      | Position of the drawer (`left` or `right`).                               | `'left'`, `'right'`   |

---

## **3. PermissionsAndroid**

### **Description**
`PermissionsAndroid` provides access to the permissions model introduced in Android M (API 23) and later. It allows you to request and check permissions in Android applications.

### **Syntax**
```javascript
import { PermissionsAndroid } from 'react-native';
```

### **Key Functions**

| Function              | Description                                                           | Value Range           |
|-----------------------|-----------------------------------------------------------------------|-----------------------|
| `check`               | Checks if a specific permission has been granted.                     | `Promise<boolean>`    |
| `request`             | Requests a specific permission.                                       | `Promise<string>`     |
| `requestMultiple`     | Requests multiple permissions at once.                                | `Promise<object>`     |
| `shouldShowRequestPermissionRationale` | Checks if the app should show an explanation before requesting permission. | `Promise<boolean>`  |

---

## **4. ToastAndroid**

### **Description**
`ToastAndroid` allows you to create Android-style Toast alerts. Toasts are small pop-up messages that appear on the screen for a short period of time.

### **Syntax**
```javascript
import { ToastAndroid } from 'react-native';
```

### **Key Functions**

| Function              | Description                                                           | Value Range          |
|-----------------------|-----------------------------------------------------------------------|----------------------|
| `show`                | Displays a Toast message on the screen.                                | `show(message: string, duration: number)` |
| `LENGTH_SHORT`        | Constant for a short duration Toast (typically 2 seconds).            | `number`             |
| `LENGTH_LONG`         | Constant for a long duration Toast (typically 3.5 seconds).           | `number`             |

---

These Android-specific components and APIs enable React Native apps to interact with platform features such as hardware buttons, permissions, and Toast messages.