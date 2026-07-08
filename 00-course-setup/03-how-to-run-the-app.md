# How to Run the App

## Start Metro
```bash
npm start
```

## Run Android
```bash
npm run android
```

## Run iOS (macOS only)
```bash
npm run ios
```

## Basic Troubleshooting
- Metro not running: run `npm start` in a separate terminal.
- Android emulator not open: start emulator from Android Studio Device Manager.
- iOS requires Mac + Xcode + CocoaPods.
- Reinstall modules if needed:
```bash
rm -rf node_modules package-lock.json
npm install
```
- Clean Android build if needed:
```bash
cd android
./gradlew clean
cd ..
```
