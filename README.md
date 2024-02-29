## How to Set up a Mac for React-Native Development

Getting your computer set up for development in React-Native is no easy task.  To avoid endless googling, here are some guides to send you on your way.  I'm going to assume default paths for most things, and depending on the age of your machine, the operating system, etc some of these variables may change.  I am assuming you are on a Mac, as it isn't really possible to do full stack dev and deploy on a PC.  You can do react-native development for Android, but if you are going to run a cross platform app, you need a Mac.

## Create a react-native project

There are many different ways to do this, and that is not what this page is about.  Pick your poison.  

```console
npx react-native init MyTestApp
```

That is probably the easiest - [full docs on React Native here](https://reactnative.dev/).

## Xcode

Open your terminal and type in

```console
xcode-select —install
```

This should install Xcode command line tools - follow the prompts and grant necessary permissions.

From the Apple App Store, make sure you have Xcode installed.

Once you have installed it, open it.  On the first open, it may ask if you want to install other operating systems.  Make sure you at least have a Mac and an IOS OS installed.  The download on this can take a bit of time.

Then, open the .xcworkspace file that is in your app/ios folder.

If you are asked to agree to terms, Agree.

In the main menu, go to 

Xcode > Preferences > Location and choose the command line tools installed.

Xcode > Preferences > Accounts and log in with your Apple ID
Close Xcode.

## Android Studio

Download and install Android Studio.

When you open it for the first time, agree to terms and install all the default settings.

Open the folder app/android

In the main menu, go to: 

Tools > AVD Manager

Choose a device - I usually go with one with a Play Store logo so I have the possibility of using the play store - Pixel 4 is a good choice at the time of this writing.  Install the device.  If you don't have an Android OS installed, when you get to that step choose the most recent / default selection and install that.

Close Android Studio.

## M1 Mac Android Studio Hack

If you are on a M1 mac and it can't find node, you can open it from the command line with

```console
open -a /Applications/Android\ Studio.app  
```

and this also is supposed to be a permanent fix

```console
chmod +x /Applications/Android\ Studio.app/Contents/bin/printenv
```
## Command Line

Open Terminal.

I like a pretty terminal - most macs are defaulting to zsh, and I am assuming that is your terminal.

I use [beeman's shell settings](https://github.com/beeman/server-shell)

```sh -c "$(curl -fsSL https://raw.github.com/beeman/server-shell/master/tools/install.sh)"```

Restart your terminal or run ```source ~/.zshrc```

## Install Homebrew

If you are on a new machine and haven't installed Homebrew run

```console
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Once this is done, it will give you some code to copy into your terminal.  Execute it.

If you already have Homebrew, just run:

```console
brew update
```

## Install CocoaPods

```console
brew install cocoapods
```

## Install ASDF

You will want to be able to easily switch between versions of node for different projects.

```console
brew install asdf
```

Once this is done, it will give you some code to copy into your ~/.zscrc file.

```console
nano ~/.zshrc
```

Restart your terminal or run ```source ~/.zshrc```

Python has a dependency it needs, you can run 

```console
brew install readline xz
```

Then, install a node version or two (change out for the latest version)

```console
asdf plugin add nodejs
asdf plugin add pythong
asdf install nodejs latest
asdf install python latest
```

Check that it is installed by running

```console
node -v
python -v
```

Then, take those versions and run

```console
asdf global nodejs (version)
asdf global python (version)
```

That sets global versions - you can then overwrite per project by using

```console
asdf local nodejs (version)
```

## Install PNPM

```console
brew install pnpm
```

## Install SDKMan and JAVA

```console
 curl -s "https://get.sdkman.io" | bash
 sdk install java 17.0.9-zulu
 sdk use java 17.0.9-zulu
```

Restart your terminal or run ```source ~/.zshrc```

Make sure it is loading:

```console
java --version
```

## Install Reactotron

```console
brew install reactotron
```

## Install Watchman

```console
brew install watchman
```

## Configure Android in Your Path

If you want to be able to do run-android and have it auto launch a device, you need to also add the android SDKs to your path.

```console
nano ~/.zshrc
```

Scroll or down arrow all the way to the bottom of the file.

Paste in the following code given to you in the installation script

```console
export ANDROID_HOME="$HOME/Library/Android/sdk"
export PATH=$PATH:$ANDROID_HOME/platform-tools
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/emulator
```

Restart your terminal or run ```source ~/.zshrc```
