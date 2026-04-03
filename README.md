# NFT Massacre Android

Native Android wrapper for the `nftmassacre.github.io` site.

## Download

- Latest debug APK: `https://raw.githubusercontent.com/nftmassacre/nftmassacre-android/main/releases/0.1.0/nftmassacre-v0.1.0-debug.apk`

## What The Game Is

NFT Massacre is a small third-person 3D game set on a ringworld street. You control a pink CRT-headed avatar, load an Ethereum wallet, and spawn that wallet's NFTs into the scene as wandering NPCs. The core loop is simple: move around the neighborhood, load a wallet, find the spawned NFT NPCs, and punch them into panic or knock them down.

The scene also includes a built-in web screen, ambient crowd audio, speech bubbles, target highlighting, and a small info overlay. NFT data is loaded through the bundled wallet loader and used to place wallet-specific NPCs into the world.

## How To Use It

1. Launch the app and wait for the loading overlay to clear.
2. Enter an Ethereum address in the wallet field and press `Load NFTs`.
3. Move around the world and approach the spawned NFT NPCs.
4. Attack while facing them to panic or knock them down.
5. Use the info button for the About dialog.

## Controls

### Desktop-style controls

- Click the world to lock input and enter movement mode.
- Move the mouse to look around.
- Use `WASD` or the arrow keys to move.
- Hold `Shift` to run.
- Press `Space` to jump.
- Press `C` to crouch-toggle.
- Left click while locked to punch/attack.
- Press `ESC` to release the cursor or leave the in-world screen.

### Touch controls

- Use the left on-screen pad to move.
- Drag on the world view to look around.
- Pinch to zoom the camera.
- Tap outside the in-world screen to leave screen mode.

## In-Game Interactions

- Loading a wallet spawns that wallet's NFTs as NPCs in the neighborhood.
- The HUD shows wallet load status and the current target.
- A nearby attack can stagger NFT NPCs, trigger panic, or knock characters down.
- The CRT screen in the world can browse web content.
- The keyboard object opens the URL entry bar for the in-world screen.

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
