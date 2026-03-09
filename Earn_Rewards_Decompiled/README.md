# Earn Rewards - Decompiled APK Contents

**APK File:** `_EarnRewards_19614139.apk`  
**Decompiled Date:** March 9, 2026  
**Format:** Extracted APK structure (not fully decompiled to source code)

---

## 📁 FOLDER STRUCTURE

```
Earn_Rewards_Decompiled/
├── AndroidManifest.xml          ← App manifest & configuration
├── classes.dex                  ← Compiled Java bytecode (file 1)
├── classes2.dex                 ← Compiled Java bytecode (file 2)
├── classes3.dex                 ← Compiled Java bytecode (file 3)
├── classes4.dex                 ← Compiled Java bytecode (file 4)
├── classes5.dex                 ← Compiled Java bytecode (file 5)
├── classes6.dex                 ← Compiled Java bytecode (file 6)
├── resources.arsc               ← Compiled resources
├── META-INF/                    ← Signatures & certificates
├── assets/                      ← Raw app assets
├── lib/                         ← Native libraries (.so files)
│   ├── arm64-v8a/              ← ARM64 native libs
│   └── armeabi-v7a/            ← ARM32 native libs
├── res/                         ← Resources (drawables, layouts, etc)
├── kotlin/                      ← Kotlin standard library
├── explorestack/                ← ExploreStack library
├── okhttp3/                     ← OkHttp library
├── org/                         ← Google libraries
└── *.properties                 ← Gradle build info
```

---

## 📄 KEY FILES EXPLAINED

### AndroidManifest.xml
- **What:** App configuration and permissions
- **Purpose:** Tells Android about app structure
- **Size:** ~64 KB
- **Format:** Binary XML (not human-readable directly)

### classes.dex & classes2-6.dex
- **What:** Compiled Java/Kotlin bytecode
- **Purpose:** The actual app code
- **Total Size:** ~42.8 MB
- **Format:** DEX format (can be decompiled with specialized tools)
- **Note:** Not source code - obfuscated and compiled

### resources.arsc
- **What:** Compiled resources (strings, colors, dimensions)
- **Size:** ~1.4 MB
- **Format:** Binary resource format

### assets/ Folder
**Key files:**
- `aps_mobile_client_config.json` - Appodeal configuration
- `apd_adapters/` - Ad mediation network configs
- `bm_networks/` - Bidding network configs
- `audience_network.dex` - Facebook Audience Network
- `omsdk-v1.js` - Open Measurement SDK for ad verification
- `dexopt/baseline.prof` - Performance optimization profiles

### lib/ Folder (Native Libraries)
**arm64-v8a/ (ARM 64-bit):**
- `libmodpdfium.so` - PDF rendering (4.8 MB)
- `libjniPdfium.so` - PDF JNI interface (493 KB)
- `libnms.so` - Mobile security/anti-fraud
- `libapminsighta.so` & `libapminsightb.so` - Performance monitoring
- `libpglarmor.so` - Security/armor
- File/buffer managers

**armeabi-v7a/ (ARM 32-bit):**
- Same libraries, compiled for 32-bit ARM processors
- Slightly smaller sizes

### res/ Folder
**Contains:**
- `drawable-*` - Images and icons (density-specific)
- `layout/` - XML layout files (compiled)
- `values/` - Strings, colors, dimensions
- `menu/` - Menu definitions
- `animator/` - Animation definitions

### META-INF/ Folder
**Purpose:** Digital signatures and verification
- `MANIFEST.MF` - Manifest file
- `CERT.SF` - Certificate signature
- `CERT.RSA` - Certificate

---

## 🔧 HOW TO USE THIS FOLDER

### Option 1: Analyze with a Decompiler
You can decompile the DEX files to Java source code:

```bash
# Using cfr (Java decompiler)
cfr classes.dex --outputdir src

# Using procyon
procyon -o src classes.dex

# Using jadx (Android decompiler - recommended)
jadx classes.dex -o src
```

### Option 2: Inspect with APK Tools
Extract specific information:

```bash
# List all files
unzip -l _EarnRewards_19614139.apk

# Extract specific file
unzip -p _EarnRewards_19614139.apk AndroidManifest.xml > manifest.xml

# View properties
strings classes.dex | grep "package\|activity\|permission"
```

### Option 3: Analyze with Online Tools
- Upload to: https://www.decompiler.com
- Or: https://www.javadecompilers.com
- Upload DEX files to decompile

### Option 4: Use Android Studio
1. File → Open → Select the APK
2. Android Studio will analyze and show structure

---

## 📊 WHAT'S IN EACH DEX FILE

### classes.dex (8.9 MB)
- Main application code
- Primary logic and activities

### classes2.dex through classes5.dex (7.8-9 MB each)
- Libraries (AppLovin, Appodeal, Google services)
- Firebase
- AndroidX
- Kotlin runtime

### classes6.dex (709 KB)
- Smaller utilities
- Additional libraries

---

## 🔍 KEY INSIGHTS FROM THIS FOLDER

### Ad Networks Integrated:
Located in `assets/apd_adapters/` and `assets/bm_networks/`:
- AppLovin (primary mediation)
- Appodeal (secondary mediation)
- IronSource/LevelPlay
- AdMob
- Facebook Audience Network
- Criteo, Amazon, AdColony, Pangle, Notsy
- And 8 more ad networks

### Native Features:
Located in `lib/arm64-v8a/` and `lib/armeabi-v7a/`:
- PDF viewing/processing
- Mobile security/anti-fraud
- Performance monitoring
- Encryption & secure file handling

### Permissions & Manifest:
Located in `AndroidManifest.xml`:
- Internet access
- Ad identifiers
- Location services (for location-based ads)
- Standard Android permissions

---

## ⚠️ IMPORTANT NOTES

### This is NOT Source Code
```
❌ What you DON'T have:
- Original .java or .kt source files
- Variable names (obfuscated)
- Comments
- Original code structure
- Package organization

✅ What you DO have:
- Compiled bytecode
- Can be decompiled to Java-like code
- Asset files
- Resource definitions
- Native libraries
- Configuration files
```

### Size Considerations
```
Total folder size: ~43+ MB
This is the extracted APK contents
Much smaller than full Android Studio project
```

### DEX File Limits
```
Each DEX file max: 65,536 methods
This app uses 6 DEX files
Total methods: ~400,000+ (estimated)
Indicates complex, feature-rich app
```

---

## 🛠️ TOOLS TO EXPLORE THIS FURTHER

### Free Tools:

**JADX** (Recommended)
- Download: https://github.com/skylot/jadx
- Converts DEX → Java source code
- GUI and CLI versions

**APKTool**
- Download: https://ibotpeaches.github.io/Apktool/
- Disassembles APK resources

**CFR**
- Download: http://cfr.javadecompilers.com
- Java decompiler

**Procyon**
- Download: https://bitbucket.org/strobel/procyon
- Modern Java decompiler

### Online Tools:
- Decompiler.com
- JavaDecompilers.com
- Apk.tools

### IDEs:
- Android Studio (File → Open → APK)
- IntelliJ IDEA (has APK explorer)

---

## 📋 WHAT YOU CAN LEARN FROM THIS

### Architecture:
- How ads are integrated
- Which libraries are used
- How features are organized
- PDF handling approach
- Security implementations

### Code Analysis:
- Which ad networks perform best
- Initialization sequence
- Error handling patterns
- Resource management

### Optimization:
- DEX file organization
- Native library sizing
- Asset optimization
- Resource efficiency

---

## 🚀 NEXT STEPS

### If you want to decompile to source:
1. Download JADX
2. Open `classes.dex` in JADX
3. Export to Java files
4. Analyze the code
5. Learn implementation patterns

### If you want to understand the app:
1. Look at `assets/` folder for configs
2. Check `lib/` for native features
3. Review `AndroidManifest.xml` for permissions
4. Examine `res/` for UI structure

### If you want to rebuild:
1. You would need source code (not here)
2. Recompiling from DEX alone not practical
3. Use decompiled code as reference
4. Better to implement from scratch

---

## 📊 TECHNICAL DETAILS

### Multi-DEX Info
```
This app uses Android MultiDex support
Necessary because total methods > 65,536
Indicates:
  - Complex app
  - Many dependencies
  - Full-featured application
```

### Architectures Supported
```
ARM64 (arm64-v8a):  Modern Android phones
ARM (armeabi-v7a):  Older/budget Android phones
Both included = wide device compatibility
```

### Kotlin Support
```
`kotlin/` folder present
App uses Kotlin for parts of the code
Modern Android development
```

---

## 💡 USAGE RECOMMENDATIONS

### For Learning:
✅ Study how ads are integrated  
✅ Understand app architecture  
✅ Learn best practices  
✅ See library usage patterns  

### For Reverse Engineering:
✅ Decompile to Java  
✅ Analyze code flow  
✅ Understand implementation  
✅ Extract logic patterns  

### For Modification:
❌ NOT recommended without source code  
❌ Recompiling DEX alone is complex  
❌ Better to build fresh from source  

---

## 📁 HOW THIS RELATES TO PATH B IMPLEMENTATION

**Your Decompiled APK shows:**
- ✓ Ad networks ARE present (AppLovin, Appodeal)
- ✓ SDK dependencies exist
- ✓ Native libraries compiled in
- ✓ Assets configured

**But MISSING:**
- ✗ Initialization code in MainActivity
- ✗ SDK key configuration
- ✗ Ad placement setup
- ✗ Callback implementations
- ✗ UI to display ads

**Which is exactly what Path B adds!**

---

## 🎯 SUMMARY

This folder contains the **complete extracted structure** of your Earn Rewards APK:

- **Raw files:** 100+ files and folders
- **Compiled code:** 6 DEX files totaling 42.8 MB
- **Resources:** Layouts, strings, drawables
- **Native code:** PDF library + security libs
- **Configuration:** Ad network configs, build info

**You can analyze this to understand how the app is structured and what libraries it uses, but for actual implementation work, follow Path B instead!**

---

## ✅ FINAL NOTES

**What's included here:**
- ✅ Complete decompiled APK structure
- ✅ All assets, resources, and libraries
- ✅ Configuration files
- ✅ Native libraries
- ✅ Everything from the original APK

**What's NOT included:**
- ❌ Original source code (.java/.kt files)
- ❌ Variable names (obfuscated)
- ❌ Developer comments
- ❌ Full project structure

**To implement features, use Path B guides!**

---

**Explore this folder to understand your app's structure, then follow Path B to implement working ads.** ✨

