1. Back to `App.js`. Import `AsyncStorage` from `@react-native-async-storage/async-storage`.

```js
import AsyncStorage from '@react-native-async-storage/async-storage';
```

2. We will create 2 states:

```js
const [loading, setLoading] = useState(true);
const [viewedOnboarding, setViewedOnboarding] = useState(false);
```

3. We will create a function to check the `onboarding`.

```js
const checkOnboarding = async () => {
  try {
    const value = await AsyncStorage.getItem('viewedOnboarding');

    if (value !== null) {
      setViewedOnboarding(true);
    }
  } catch (err) {
    console.log('Error @checkOnboarding: ', err);
  } finally {
    setLoading(false);
  }
};
```

4. Now we will call this function in a `useEffect` hook.

```js
useEffect(() => {
  checkOnboarding();
}, []);
```

5. And in the return of the component, we will check if the user has seen the onboarding.

```js
return (
  <View style={styles.container}>
    {loading ? <Loading /> : viewedOnboarding ? <HomeScreen /> : <Onboarding />}
    <StatusBar style="auto" />
  </View>
);
```
