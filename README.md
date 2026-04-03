# NFT Massacre Android

Native Android wrapper for the NFT Massacre web game.

## What It Is

NFT Massacre is a small third-person 3D game set on a ringworld street. You control a pink CRT-headed avatar, load an Ethereum wallet address, and spawn that wallet's NFTs into the scene as wandering NPCs. The core loop is simple: move around the neighborhood, load a wallet, find the spawned NFT NPCs, and punch them into panic or knock them down.

This Android app packages the current `nftmassacre.github.io` site into a WebView wrapper via Android's `WebViewAssetLoader`. The web app itself still uses remote network services and remote web assets exactly as the live site does.

## Runtime Features

- Fullscreen native Android wrapper around the live NFT Massacre web app bundle
- Wallet-driven NFT NPC spawning from a user-supplied Ethereum address
- Touch controls for Android play
- In-world browser screen and URL entry
- File chooser bridge for the hidden world-object import input
- Download handoff through Android's download manager or browser fallback

## Download

- Current debug APK: `https://raw.githubusercontent.com/nftmassacre/nftmassacre-android/main/releases/0.1.1/nftmassacre-v0.1.1-debug.apk`

## Build

Standard Android Gradle project:

```sh
./gradlew assembleDebug
./gradlew assembleRelease
```

On the Android/Termux Debian build host, use the local `aapt2` override if needed:

```sh
./gradlew assembleDebug -Pandroid.aapt2FromMavenOverride=/data/data/com.termux/files/usr/bin/aapt2
./gradlew assembleRelease -Pandroid.aapt2FromMavenOverride=/data/data/com.termux/files/usr/bin/aapt2
```

## Release Notes

- Current version: `0.1.1`
- Source license: `AGPL-3.0-or-later`
- Canonical Android bundle currently mirrors the working upstream web app again after a failed attempt to localize all runtime assets.

## F-Droid Status

This canonical working build is not ready for the main F-Droid repository yet. The packaged web app still loads executable JavaScript and other assets from remote hosts at runtime, which conflicts with F-Droid main-repo policy. The correct path is to vendor those runtime dependencies cleanly without breaking the web app, then submit.
