# Skype-M1

> This project is a fork of [Discord-M1](https://github.com/yannhodiesne/Discord-M1)

An ARM64 native Skype desktop app for M1 Macs, based on Discord [yannhodiesne](https://github.com/yannhodiesne)'s work.

## Working features

 - Voice calls
 - Screen sharing OOB (entire screens and individual windows)
 - Right-clicking to bring the context menu OOB

## Coming soon
 - Badges (notifications count on the Skype icon)

# How to install

 1. Head to the [releases page](https://github.com/dyanakiev/Skype-M1/releases) and download the latest version.
 2. Open the .dmg file and copy the application **anywhere but not inside your Applications folder**.
 3. Open a terminal, and type `xattr -rd com.apple.quarantine ` (with a space at the end), then drag the Skype application onto the terminal before pressing Enter.
 4. Enjoy !

> Steps 2 and 3 are mandatory because I did not pay Apple's 99$ fee to sign the application.  
> Putting the application inside the Applications folder will break the screen sharing feature, as Apple restricts the permissions of unsigned apps.

# Building from source

## Requirements

 - Have Xcode installed and run it at least once to install required tools
 - Node.js 14.16.0 or above (https://nodejs.org/en/)

> As of today, Node 17 fails to compile one of the project's dependencies  
> I recommend to use Node 16 while waiting for `node-gyp` to fix this issue

## Build the application

1. Clone the project

```$ git clone https://github.com/dyanakiev/Skype-M1.git```

2. Navigate to the project's folder

```$ cd Skype-M1```

3. Install the required dependencies

```$ npm run install```

4. Compile and package the application

```$ npm run dist```

5. You can now find the `Skype-vX.X.X-arm64.dmg` file inside `Skype-M1/dist` and the `Skype.app` file inside `DiscordSkype-M1/dist/mac-arm64`

> Alternatively you can run the app directly from source using `npm run start`, but it will be slower as it is intended for development purposes

# FAQ

## Why is macOS is telling me the application is damaged and cannot be opened?

It happens because you dit not run, or made a mistake when running the terminal command inside the *How to install* section.  
Follow the instructions inside the *How to install* section, and feel free to blame Apple for their developer's fee.

## Why is the share screen button opening the System Preferences but I still cannot share my screen?

It happens because you moved Skype inside the Applications folder.  
Apple is restricting the permissions of unsigned applications inside of this folder, to ensure only trusted ones can interact with some parts of the system.  
Follow the instructions inside the *How to install* section, and feel free to blame Apple for their developer's fee.


# Credits from original authors of Discord Native M1

Made with [Electron-Builder](https://www.electron.build/).

Kudos to [yannhodiesne](https://github.com/yannhodiesne) for his fork work on an M1-friendly Discord client.
Kudos to [17hoehbr](https://github.com/17hoehbr) for his original work on an M1-friendly Discord client.

Screen sharing support would not have been possible without these ressources and their authors :
 - [Hacking Together a Native Version of Discord for M1 Macs](https://rthr.me/2021/03/discord-native-apple-silicon/)
 - [WesselKroos' comment on electron/electron#16513](https://github.com/electron/electron/issues/16513#issuecomment-602070250)

Badge count support would not have been possible without [Randomblock1](https://gist.github.com/Randomblock1)'s work : [JavaScript code for Nativefier Discord to add a counter and native style](https://gist.github.com/Randomblock1/b8cd3948ce0b4688b874f2643a2a6941)
