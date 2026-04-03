# NFT Massacre Android

Native Android wrapper for the `nftmassacre.github.io` site.

## Contents

- `app/`: Android app source
- `app/src/main/assets/www/`: bundled web app
- `releases/`: built release artifacts currently tracked for this app

## Build

Standard Android Gradle project:

```sh
./gradlew assembleDebug
./gradlew bundleRelease
```

On the Android/Termux Debian build host, use the local `aapt2` override if needed:

```sh
./gradlew assembleDebug -Pandroid.aapt2FromMavenOverride=/data/data/com.termux/files/usr/bin/aapt2
```
