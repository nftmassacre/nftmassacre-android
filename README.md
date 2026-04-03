# NFT Massacre Android

Native Android wrapper for the NFT Massacre web game.

## What It Is

NFT Massacre is a small third-person 3D game set on a ringworld street. You control a pink CRT-headed avatar, load an Ethereum wallet address, and spawn that wallet's NFTs into the scene as wandering NPCs. The core loop is simple: move around the neighborhood, load a wallet, find the spawned NFT NPCs, and punch them into panic or knock them down.

This Android app packages the current `nftmassacre.github.io` game into a WebView wrapper via Android's `WebViewAssetLoader`. The boot-critical web runtime now ships inside the APK: the main game bundle, `three`, `ethers`, the default avatar model, the scene textures, and the fixed prop art are all local assets. The app still talks to live network services for wallet/NFT lookups and still lets players browse outward to external URLs from the in-world browser.

## Runtime Features

- Fullscreen native Android wrapper around a self-contained local NFT Massacre web bundle
- Wallet-driven NFT NPC spawning from a user-supplied Ethereum address
- Touch controls for Android play
- In-world browser screen and URL entry with a bundled local start page
- File chooser bridge for the hidden world-object import input
- Download handoff through Android's download manager or browser fallback

## Download

- Current debug APK: `https://raw.githubusercontent.com/nftmassacre/nftmassacre-android/main/releases/0.1.2/nftmassacre-v0.1.2-debug.apk`

## Build

Standard Android Gradle project:

```sh
./gradlew assembleDebug
./gradlew assembleRelease
```

If you edit the packaged web runtime, rebuild the local JS bundle before the Android build:

```sh
npm install
npm run bundle:web
```

On the Android/Termux Debian build host, use the local `aapt2` override if needed:

```sh
./gradlew assembleDebug -Pandroid.aapt2FromMavenOverride=/data/data/com.termux/files/usr/bin/aapt2
./gradlew assembleRelease -Pandroid.aapt2FromMavenOverride=/data/data/com.termux/files/usr/bin/aapt2
```

## Release Notes

- Current version: `0.1.2`
- Source license: `AGPL-3.0-or-later`
- Canonical Android bundle is now self-contained for its boot/runtime assets while keeping live wallet data and outbound browsing behavior.

## F-Droid Status

This build no longer depends on remote executable JavaScript or remote scene assets at startup. The remaining F-Droid review questions are about the live network services the game uses for wallet/NFT data and the external sites reachable from the in-world browser.
