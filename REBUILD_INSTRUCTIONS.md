# APK Rebuild Instructions

## Automated (GitHub Actions)

Every push to `main` branch automatically:
1. Rebuilds the APK using APKTool
2. ZipAligns the APK
3. Signs with test key
4. Creates a release with the signed APK

### Manual Trigger

1. Go to **Actions** tab
2. Select **Rebuild APK** workflow
3. Click **Run workflow**
4. Download APK from releases

---

## Manual (Local Rebuild)

### Prerequisites

```bash
# Install APKTool
wget https://github.com/iBotPeaches/Apktool/releases/download/v2.9.0/apktool_2.9.0.jar

# Install Android build tools
sudo apt-get install -y zipalign apksigner
```

### Rebuild Commands

```bash
# 1. Rebuild APK
java -jar apktool_2.9.0.jar b Earn_Rewards_Decompiled -o app-unsigned.apk

# 2. ZipAlign
zipalign -v -p 4 app-unsigned.apk app-aligned.apk

# 3. Generate signing key (one-time)
keytool -genkey -v -keystore release-key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias releasekey

# 4. Sign APK
apksigner sign --ks release-key.jks --out app-signed.apk app-aligned.apk

# 5. Verify
apksigner verify app-signed.apk
```

---

## Output

- **Unsigned APK:** `app-unsigned.apk`
- **Signed APK:** `app-signed.apk`
- **Release:** GitHub Releases page

---

## ⚠️ Important Notes

1. **Test Key:** GitHub Actions uses a test key (not for production)
2. **Production:** Use your own signing key for release builds
3. **Original App:** This is a decompiled app - rebuilding may not work perfectly
4. **Legal:** Ensure you have rights to rebuild this application
