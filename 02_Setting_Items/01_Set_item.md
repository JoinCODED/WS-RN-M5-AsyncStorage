1. Open `components/Onboarding.js`.

2. In the `scrollTo` function `else` block, we need to save a value to AsyncStorage, that indicates that the user has seen the onboarding screen.

3. Import `AsyncStorage` from `@react-native-async-storage/async-storage`.

```js
import AsyncStorage from '@react-native-async-storage/async-storage';
```

4. All `AsyncStorage` methods are asynchronous. So we need to use the `await` keyword. and a `try/catch` block to handle errors.

```js
try {
  await AsyncStorage.setItem('viewedOnboarding', 'true');
} catch (err) {
  console.log('Error setItem: ', err);
}
```
