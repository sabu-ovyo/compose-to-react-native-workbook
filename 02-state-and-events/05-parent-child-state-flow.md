# 05 Parent Child State Flow

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
import React, {useState} from 'react';
import {
  SafeAreaView,
  View,
  Text,
  Button,
  StyleSheet,
} from 'react-native';

function App(): React.JSX.Element {
  const [count, setCount] = useState<number>(0);

  return (
    <SafeAreaView style={styles.container}>
      <View style={styles.card}>
        <Text style={styles.title}>Counter</Text>
        <Text style={styles.count}>{count}</Text>
        <View style={styles.row}>
          <Button title="-1" onPress={() => setCount(count - 1)} />
          <Button title="+1" onPress={() => setCount(count + 1)} />
        </View>
      </View>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {flex: 1, padding: 16, backgroundColor: '#FFFFFF', justifyContent: 'center'},
  card: {padding: 16, borderRadius: 12, backgroundColor: '#F4F4F4'},
  title: {fontSize: 22, fontWeight: '700', marginBottom: 12},
  count: {fontSize: 40, fontWeight: '700', marginBottom: 12},
  row: {flexDirection: 'row', justifyContent: 'space-between'},
});

export default App;

```

## 8. How to Run
```bash
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
![Screenshot](../screenshots/05-parent-child-state-flow.png)
```

## 13. Common Mistakes
- Forgetting to export default component.
- Missing imports in `App.tsx`.
- Keeping old Metro cache after large changes.
- Using JavaScript patterns without TypeScript types.

## 14. Summary
You learned this concept in React Native and mapped it to Compose so you can build faster with familiar mental models.
