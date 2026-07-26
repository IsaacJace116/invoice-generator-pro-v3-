# Building APK from Invoice Generator Pro

This guide will help you convert the web application into an Android APK.

## Prerequisites

1. **Node.js & npm** - Download from [nodejs.org](https://nodejs.org/)
2. **Java Development Kit (JDK)** - Install JDK 11 or later
3. **Android SDK** - Download Android Studio from [developer.android.com](https://developer.android.com/studio)
4. **Gradle** - Usually comes with Android SDK

## Option 1: Using Apache Cordova (Recommended)

### Step 1: Install Cordova globally
```bash
npm install -g cordova
```

### Step 2: Create a Cordova project
```bash
cordova create invoice-app com.invoicegenerator.pro "Invoice Generator Pro"
cd invoice-app
```

### Step 3: Add Android platform
```bash
cordova platform add android
```

### Step 4: Copy your files
Replace the contents of `www/` directory with your files:
- `index.html`
- `Change password.html`
- `Payment-cancelled.html`
- `Payment-success.html`
- Any CSS and JavaScript files

### Step 5: Update config.xml
The `config.xml` file is already prepared in this repo. Use it to configure app permissions and settings.

### Step 6: Build the APK
```bash
# Debug APK (for testing)
cordova build android

# Release APK (for distribution)
cordova build android --release
```

### Step 7: Sign the APK (for Release only)
For a release APK, you need to sign it with a keystore:

```bash
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 \
  -keystore my-release-key.keystore \
  platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk \
  alias_name

zipalign -v 4 app-release-unsigned.apk invoice-generator-pro.apk
```

## Option 2: Using Capacitor (Modern Alternative)

### Step 1: Initialize Capacitor
```bash
npm init
npm install @capacitor/core @capacitor/cli
npx cap init
```

### Step 2: Add Android
```bash
npm install @capacitor/android
npx cap add android
```

### Step 3: Copy web files
```bash
npx cap copy
```

### Step 4: Build APK
```bash
cd android
./gradlew assembleDebug
```

The APK will be in: `android/app/build/outputs/apk/debug/`

## Option 3: Using Android Studio Directly

1. Download Android Studio
2. Create a new Native Android project
3. In the assets folder, place your HTML/CSS/JS files
4. Use WebView to load the files
5. Build → Build Bundle(s) / APK(s)

## Where to find your APK

After building, your APK files will be located at:

**Cordova:**
- Debug: `platforms/android/app/build/outputs/apk/debug/app-debug.apk`
- Release: `platforms/android/app/build/outputs/apk/release/app-release-unsigned.apk`

**Capacitor:**
- `android/app/build/outputs/apk/debug/app-debug.apk`

## Testing the APK

1. Enable USB Debugging on your Android device
2. Connect via USB
3. Run: `adb install app-debug.apk`
4. Or manually install by transferring the APK file to your phone

## Important Notes

- ✅ Your app uses EmailJS, PDF export, and file uploads - all compatible with Cordova
- ✅ No backend required - runs entirely client-side
- ⚠️ Local storage will persist data on the device
- ⚠️ Test thoroughly on Android 8+ devices
- 📦 Debug APKs are larger; use release builds for distribution

## Troubleshooting

If you encounter issues:

1. **Gradle not found**: Install Android SDK properly and set `ANDROID_SDK_ROOT` environment variable
2. **Java version mismatch**: Use Java 11+
3. **Plugin errors**: Update Cordova: `npm install -g cordova@latest`
4. **Build fails**: Clean and try again: `cordova clean android && cordova build android`

## Support

For more help:
- [Cordova Documentation](https://cordova.apache.org/docs/en/latest/)
- [Capacitor Documentation](https://capacitorjs.com/docs)
- [Android Developer Guides](https://developer.android.com/docs)
