# JSX vs Compose UI

## 1. Goal
Learn how JSX tree maps to Compose UI tree.

## 2. Why This Matters for Compose Developers
This helps you transfer your existing Jetpack Compose thinking into React Native quickly.

## 3. Compose Mental Model
```kotlin
Column {
  Text("Title")
  Button(onClick = {}) { Text("Tap") }
}
```

## 4. React Native Mental Model
JSX is XML-like syntax inside TypeScript returning a component tree.

## 5. Compose vs React Native Comparison
| Compose | React Native |
|---|---|
| Column/Row | View with flexDirection |
| Text composable | Text component |
| UI function body | return JSX |

## 6. Code Practice Setup
- Open `App.tsx`.
- Replace full code.
- No new package.

## 7. Copy-Paste Working Code
```tsx
import React from 'react';
import {
  SafeAreaView,
  View,
  Text,
  Button,
  StyleSheet,
} from 'react-native';

function App(): React.JSX.Element {
  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.card}>
        <Text style={styles.title}>Hello React Native</Text>
        <Text style={styles.subtitle}>Compose developer to RN journey</Text>
        <Button title="Press me" onPress={() => {}} />
      </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    padding: 16,
    backgroundColor: '#FFFFFF',
    justifyContent: 'center',
  },
  card: {
    padding: 16,
    borderRadius: 12,
    backgroundColor: '#F2F2F2',
  },
  title: {
    fontSize: 22,
    fontWeight: '700',
    marginBottom: 8,
  },
  subtitle: {
    fontSize: 14,
    marginBottom: 12,
  },
});

export default App;

```

## 8. How to Run
```bash
npm start
npm run android
```

## 9. Expected Output
Same basic card UI rendered through JSX.

## 10. Practice Task
- Wrap subtitle in another View.
- Change button title.
- Add one emoji in title.

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
![Screenshot](../screenshots/01-02-jsx-vs-compose-ui.png)
```

## 13. Common Mistakes
- Forgetting to export default component.
- Missing imports in `App.tsx`.
- Keeping old Metro cache after large changes.
- Using JavaScript patterns without TypeScript types.

## 14. Summary
You learned this concept in React Native and mapped it to Compose so you can build faster with familiar mental models.
