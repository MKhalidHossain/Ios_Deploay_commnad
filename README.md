
# Flutter iOS App Deployment Cheat Sheet

This cheat sheet provides step-by-step instructions and commands to deploy a Flutter iOS app from **VS Code → Xcode → App Store**.

---

## 2. Build Flutter iOS App

**Run app on a device for testing:**

```bash
flutter devices            # List available devices
flutter run -d <device_id> # Run on a specific device
```

**Create a release build:**

```bash
flutter build ios --release
```

**Output folder:** `build/ios/iphoneos`

---

## 3. Open Project in Xcode (form VS code)

```bash
cd ios
pod install 
open Runner.xcworkspace
```
Open Project in Xcode (form cmd)
```bash
cd path/to/your/flutter_project/ios
open Runner.xcworkspace
```

> Always open `.xcworkspace`, not `.xcodeproj`.-

---

## 4. Configure Signing in Xcode

1. Open `Runner` → `Signing & Capabilities`
2. Select **Team**
3. Enable **Automatically manage signing**
4. Set **Bundle Identifier** (must be unique)
5. Update Version & Build number:
   - Version = 1.0.0
   - Build = 1

---

## 5. Archive App in Xcode

1. Xcode → `Product` → `Archive`
2. Wait for **Organizer** to open with the archive

---

## 6. Upload to App Store

1. In Organizer → `Distribute App` → `App Store Connect` → `Upload`
2. Select **Team**
3. Enable **Bitcode** (if needed)
4. Validate & upload

---

## 7. App Store Connect Steps

1. Go to [App Store Connect](https://appstoreconnect.apple.com)
2. Navigate to **My Apps → Your App → iOS App**
3. Fill in:
   - App Information
   - Screenshots
   - Description
4. Submit for Review

---

## 8. Useful Flutter Commands

```bash
flutter clean                # Clean build files
flutter build ios             # Build iOS app
flutter build ios --release   # Release build
flutter run                   # Run on connected device
flutter run -d <device_id>    # Run on specific device
flutter devices               # List connected devices
```

---

## 9. GitHub Upload Commands (Optional)

```bash
# Initialize Git repo
git init

# Add files
git add README.md

# Commit changes
git commit -m "Add Flutter iOS deployment cheat sheet"

# Add remote (replace URL with your repo)
git remote add origin https://github.com/username/ios-deployment-cheatsheet.git

# Set main branch
git branch -M main

# Push to GitHub
git push -u origin main
```

---

## 10. Tips & Best Practices

- Test your app on a real device before submitting.
- Increment build number for every new submission.
- Include all required assets:
  - App Icons
  - Launch Screens
  - Privacy Policy
- Use `flutter clean` if builds fail.
- Ensure provisioning profiles and certificates are valid.
- Always open `.xcworkspace` in Xcode for Flutter projects.

---

### References

- [Flutter iOS Deployment Docs](https://docs.flutter.dev/deployment/ios)
- [Apple App Store Connect](https://appstoreconnect.apple.com)
