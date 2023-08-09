# Tarrega
Tarrega is mainly used to build desktop applications powered by Apache Cordova and ElectronJS. It was named after Francisco Tárrega a Spanish composer and classical guitarist of the late Romantic period. He is known for such pieces as Capricho Árabe and Recuerdos de la Alhambra. He is often called father of classical guitar.

<img src="https://firebasestorage.googleapis.com/v0/b/lonica.appspot.com/o/img%2Fdpddlv7h086a1.png?alt=media&token=358823b9-c213-4a3c-abeb-53259e08e9ea" style="max-width:100%;" width="360">

### https://cordova.apache.org (Apache Cordova)

### STEP 1: Make sure to have all of these installed on your machine.

```sh
1. https://nodejs.org/en/
2. https://git-scm.com/downloads
3. https://www.oracle.com/ph/java/technologies/javase/javase8-archive-downloads.html
4. https://developer.android.com/studio
5. https://gradle.org/
5. Configure Environment Variables
   Watch the installation process bit.ly/3JX1aXa
```

### STEP 2: Apache Cordova Framework Installation via NPM

```sh
npm install -g cordova
```

### STEP 3: Adding Platform

```sh
(Run this command inside the "Tarrega Folder/Directory")

cordova platform add cordova-electron
```

### STEP 4: Previewing your app

```sh
It is not necessary to build the Electron application for previewing. Since the building process can be slow, it is recommended to pass in the --nobuild flag to disable the build process when previewing.

cordova run electron --nobuild
```

### STEP 5: Release (DevTools are shown by default on Debug Builds (without a flag or with --debug). If you want to hide the DevTools pass in the --release flag when building or running the application.)

```sh
cordova run electron --nobuild --release
```

### STEP 6: Building your app

```sh
cordova build electron --release
```

### You can customize the browser window behavior directly via this directory: res/electron/settings.json

```sh
{
  "browserWindow": {
    "width": 800,
    "height": 600,
    "autoHideMenuBar": false,
    "resizable": true,
    "fullscreen": false,
    "webPreferences": {
      "nodeIntegration": false
    }
  }
}
```

### Plugins

All browser-based plugins are usable with the Electron platform.

When adding a plugin, if the plugin supports both the electron and browser platform, the electron portion will be used. If the plugin misses electron but contains the browser implementation, it will fall back on the browser implementation.

Internally, Electron is using Chromium (Chrome) as its web view. Some plugins may have conditions written specifically for each different browser. In this case, it may affect the behavior of what is intended. Since Electron may support feature that the browser does not, these plugins would possibly need to be updated for the electron platform.

Read More: https://cordova.apache.org/docs/en/11.x/guide/platforms/electron/index.html
