### Hooks

Hooks are functions that let you use state and other React features in functional components. They were introduced in React 16.8 to allow functional components to have state and lifecycle methods, which were previously only possible in class components.

#### Commonly Used Hooks

1. **useState**
   - Manages state in functional components.
   ```javascript
   const [state, setState] = useState(initialState);
   ```

2. **useEffect**
   - Performs side effects in functional components, such as data fetching, subscriptions, or manually changing the DOM.
   ```javascript
   useEffect(() => {
     // Side effect code
     return () => {
       // Cleanup code
     };
   }, [dependencies]);
   ```

3. **useContext**
   - Accesses the value of a context.
   ```javascript
   const value = useContext(MyContext);
   ```

4. **useReducer**
   - Manages state using a reducer function, useful for complex state logic.
   ```javascript
   const [state, dispatch] = useReducer(reducer, initialState);
   ```

5. **useCallback**
   - Memoizes a callback function, preventing it from being recreated on every render.
   ```javascript
   const memoizedCallback = useCallback(() => {
     // Function code
   }, [dependencies]);
   ```

6. **useMemo**
   - Memoizes a value, preventing it from being recalculated on every render.
   ```javascript
   const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
   ```

7. **useRef**
   - Creates a mutable object that persists across renders.
   ```javascript
   const ref = useRef(initialValue);
   ```

8. **useImperativeHandle**
   - Customizes the instance value that is exposed when using `ref` in parent components.
   ```javascript
   useImperativeHandle(ref, () => ({
     // Exposed methods
   }));
   ```

9. **useLayoutEffect**
   - Similar to `useEffect`, but fires synchronously after all DOM mutations.
   ```javascript
   useLayoutEffect(() => {
     // Side effect code
   }, [dependencies]);
   ```

10. **useDebugValue**
    - Displays a label for custom hooks in React DevTools.
    ```javascript
    useDebugValue(value);
    ```

#### Example Usage of Common Hooks

##### useState Example

```javascript
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <View>
      <Text>{count}</Text>
      <Button onPress={() => setCount(count + 1)} title="Increment" />
    </View>
  );
};

export default Counter;
```

##### useEffect Example

```javascript
import React, { useState, useEffect } from 'react';
import { View, Text } from 'react-native';

const DataFetcher = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []);

  return (
    <View>
      <Text>{data ? JSON.stringify(data) : 'Loading...'}</Text>
    </View>
  );
};

export default DataFetcher;
```

##### useContext Example

```javascript
import React, { useContext } from 'react';
import { View, Text } from 'react-native';

const MyContext = React.createContext();

const DisplayValue = () => {
  const value = useContext(MyContext);

  return (
    <View>
      <Text>{value}</Text>
    </View>
  );
};

const App = () => {
  return (
    <MyContext.Provider value="Hello, World!">
      <DisplayValue />
    </MyContext.Provider>
  );
};

export default App;
```

##### useReducer Example

```javascript
import React, { useReducer } from 'react';
import { View, Text, Button } from 'react-native';

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, initialState);

  return (
    <View>
      <Text>{state.count}</Text>
      <Button onPress={() => dispatch({ type: 'increment' })} title="Increment" />
      <Button onPress={() => dispatch({ type: 'decrement' })} title="Decrement" />
    </View>
  );
};

export default Counter;
```

### Summary

- **useState**: Manages state in functional components.
- **useEffect**: Performs side effects in functional components.
- **useContext**: Accesses the value of a context.
- **useReducer**: Manages state using a reducer function.
- **useCallback**: Memoizes a callback function.
- **useMemo**: Memoizes a value.
- **useRef**: Creates a mutable object that persists across renders.
- **useImperativeHandle**: Customizes the instance value exposed when using `ref`.
- **useLayoutEffect**: Fires synchronously after all DOM mutations.
- **useDebugValue**: Displays a label for custom hooks in React DevTools.

Hooks provide a powerful and flexible way to manage state and side effects in functional components, making it easier to write and maintain React applications.