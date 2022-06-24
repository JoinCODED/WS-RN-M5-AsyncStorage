1. In `HomeScreen.js`, Create a button to clear the onboarding:

```js
<TouchableOpacity onPress={clearOnboarding}>
  <Text>Clear Onboarding</Text>
</TouchableOpacity>
```

2. Next, we will create a function to clear the onboarding.

```js
const clearOnboarding = async () => {
  try {
    await AsyncStorage.removeItem('viewedOnboarding');
  } catch (err) {
    console.log('Error removeItem: ', err);
  }
};
```

3. Assign the function to the `onPress` property of the button.

```js
<TouchableOpacity onPress={clearOnboarding}>
  <Text>Clear Onboarding</Text>
</TouchableOpacity>
```
