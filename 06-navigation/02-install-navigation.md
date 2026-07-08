# 02 Install Navigation

## 1. Goal
Learn and practice this topic with runnable code.

## 2. Why This Matters for Compose Developers
This helps you transfer your existing Jetpack Compose thinking into React Native quickly.

## 3. Compose Mental Model
```kotlin
val name by remember { mutableStateOf("Compose") }
Text(text = name)
```

## 4. React Native Mental Model
In React Native, use hooks and components to model UI and behavior similarly to Compose state + UI functions.

## 5. Compose vs React Native Comparison
| Compose | React Native |
|---|---|
| remember/mutableStateOf | useState |
| LaunchedEffect | useEffect |
| data class | TypeScript type |

## 6. Code Practice Setup
- Open `App.tsx` in your local RN project.
- Replace full file content unless file paths are explicitly shown below.
- Install package only if this topic requires it.

## 7. Copy-Paste Working Code
```tsx
import React from 'react';
import {NavigationContainer} from '@react-navigation/native';
import {createNativeStackNavigator} from '@react-navigation/native-stack';
import {SafeAreaView, Text, Button, StyleSheet} from 'react-native';

type RootStackParamList = {
  Home: undefined;
  Details: undefined;
};

const Stack = createNativeStackNavigator<RootStackParamList>();

function HomeScreen({navigation}: {navigation: any}): React.JSX.Element {
  return (
    <SafeAreaView style={styles.container}>
      <Text style={styles.title}>Home Screen</Text>
      <Button title="Go to Details" onPress={() => navigation.navigate('Details')} />
    </SafeAreaView>
  );
}

function DetailsScreen(): React.JSX.Element {
  return (
    <SafeAreaView style={styles.container}>
      <Text style={styles.title}>Details Screen</Text>
    </SafeAreaView>
  );
}

function App(): React.JSX.Element {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

const styles = StyleSheet.create({
  container: {flex: 1, justifyContent: 'center', alignItems: 'center', backgroundColor: '#FFF'},
  title: {fontSize: 22, fontWeight: '700', marginBottom: 12},
});

export default App;
```

## 8. How to Run
```bash
npm install @react-navigation/native
npm install @react-navigation/native-stack
npm install react-native-screens react-native-safe-area-context
# iOS only
cd ios
pod install
cd ..
npm start
npm run android
```

## 9. Expected Output
You should see a working screen and be able to interact with the UI without TypeScript errors.

## 10. Practice Task
- Change one displayed text value.
- Add one extra UI element.
- Adjust one style property.
- Write what changed in notes.

## 11. Practice Area

### My Practiced Code
```tsx
// Paste your practiced code here
```

### What I Changed
```txt
Write 2-3 lines about what you changed.
```

## 12. Screenshot Proof
Add your screenshot below:

```md
![Screenshot](../screenshots/02-install-navigation.png)
```

## 13. Common Mistakes
- Forgetting to export default component.
- Missing imports in `App.tsx`.
- Keeping old Metro cache after large changes.
- Using JavaScript patterns without TypeScript types.

## 14. Summary
You learned this concept in React Native and mapped it to Compose so you can build faster with familiar mental models.
