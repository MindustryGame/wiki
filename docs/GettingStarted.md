# Getting Started

Getting started with Mindustry is easy. This article covers how to install Mindustry on different platforms and situations. 

## Typical Setup

This is your typical, run-of-the-mill setup process.

### Desktop

#### Steam 

As of recent, you can now [buy the game on Steam](https://store.steampowered.com/app/1127400/) if you would like to support Anuke!

#### Itch.io

1. Visit the game's [itch.io page](https://anuke.itch.io/mindustry), then download a copy of the game from there.
2. Once the `.zip` file is downloaded, unzip it. Usually that is just done by opening it like normal. When it's done, navigate to the folder it extracted into.
3. 
    1. **Windows**: simply open `desktop-release.exe`.
    2. **MacOS**: run `Mindustry.app.`
    3. **Linux**: run `Mindustry`. 

If you have JRE already installed (which is recommended), you can also run `desktop-release.jar` on Windows and Linux.

### Android

There are two different versions of Mindustry on the Play Store; Mindsutry and Mindustry Classic. If you want to get teh latest releases of Mindustry, go get Mindustry. Otherwise, if you want the old classic version, you can get Mindustry Classic.

### iOS

The latest released builds are available on iOS devices only for purchase.

## For Contributors

If you would like to contribute to the game's source code, the best way to go is to compile the game yourself or use the builds provided [here](https://jenkins.hellomouse.net/job/mindustry/). To compile it yourself:

1. If you haven't already, install at least JRE and JDK 8. 
2. Open a terminal in the root directory, then run these commands: 
    1. For Windows:
        1. Running: `gradlew desktop:run`
        2. Building: `gradlew desktop:dist`
    2. For Linux:
        1. Running: `./gradlew desktop:run`
        2. Building: `./gradlew desktop:dist`
    3. For Server builds, replace `desktop` with `server`. Example: `./gradlew server:run`
