# Getting Started

Getting started with Mindustry is easy. This article covers how to install Mindustry on different platforms and situations. 

## Typical Setup

This is your typical, run-of-the-mill setup process.

### Desktop

1. Visit the game's [itch.io page](https://anuke.itch.io/mindustry), then download a copy of the game from there. **The latest build is `alpha-59`, which we refer to as Build 59.**
2. Once the `.zip` file is downloaded, unzip it. Usually that is just done by opening it like normal. When it's done, navigate to the folder it extracted into.
3. 
    1. **For Windows users**, simply open `desktop-release.exe`. Enjoy!
    2. **For MacOS or Linux users**:
        1. If you don't already have it installed, install the **Java Runtime Environment** or JRE. [Download it here.](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) *Make sure you download the right executable for your system!*
        2. Go through the installation process and follow the instructions. 
        3. Run `desktop-release.jar`. Have fun!

### Android

This particular section covers how to install Mindustry's **latest builds** on Android. You might be here because you don't know what sort of Mindustry everyone's talking about on the Discord, or heard of `build 59`. If so, please read on.

1. Open Google Play Store and visit Mindustry's entry.
2. Scroll down a bit and notice the "Become a beta tester" section. Press "Join now" and confirm. Fully signing up will take a while, so be patient.
3. The green button will then say "Update". Update and enjoy!

### iOS

Unfortunately, **iOS only goes up to 3.5 build 40.** The latest builds are not available to download on said platform because of the cost of having it on the App Store. Again, we apologize for the inconvenience.

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

## For aspiring server hosts

Please keep in mind that doing this does not make you automatically cool. Use the local LAN feature if you only want to play with a friend under your home network.

A dedicated Linux or Windows machine is highly recommended for this.

1. If you haven't already, install at least JRE and JDK 8.
2. Download the desired server release from [itch.io](itch.io), or compile one yourself. 
3. Open a terminal or TTY session in the directory the file is placed in.
4. Run `java -jar server-release.jar`. The commands are explained in the `help` command.

If you have come this far, you should already have the skill and time to be able to port-forward. Do so if you must.
