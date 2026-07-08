# 01 Fetch Vs Retrofit

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
import React, {useEffect, useState} from 'react';
import {SafeAreaView, Text, StyleSheet, ActivityIndicator, FlatList, View} from 'react-native';

type Post = {id: number; title: string};

function App(): React.JSX.Element {
  const [posts, setPosts] = useState<Post[]>([]);
  const [loading, setLoading] = useState<boolean>(true);

  useEffect(() => {
    const loadPosts = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=10');
        const data: Post[] = await response.json();
        setPosts(data);
      } finally {
        setLoading(false);
      }
    };
    loadPosts();
  }, []);

  if (loading) {
    return (
      <SafeAreaView style={styles.center}>
        <ActivityIndicator size="large" />
      </SafeAreaView>
    );
  }

  return (
    <SafeAreaView style={styles.container}>
      <FlatList
        data={posts}
        keyExtractor={item => String(item.id)}
        renderItem={({item}) => (
          <View style={styles.card}>
            <Text style={styles.title}>{item.title}</Text>
          </View>
        )}
      />
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {flex: 1, padding: 16, backgroundColor: '#FFF'},
  center: {flex: 1, justifyContent: 'center', alignItems: 'center'},
  card: {padding: 12, borderRadius: 10, backgroundColor: '#F4F4F4', marginBottom: 8},
  title: {fontSize: 15, fontWeight: '600'},
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
![Screenshot](../screenshots/01-fetch-vs-retrofit.png)
```

## 13. Common Mistakes
- Forgetting to export default component.
- Missing imports in `App.tsx`.
- Keeping old Metro cache after large changes.
- Using JavaScript patterns without TypeScript types.

## 14. Summary
You learned this concept in React Native and mapped it to Compose so you can build faster with familiar mental models.
