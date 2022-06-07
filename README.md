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

Once you have installed it, open it, and open the .xcworkspace file that is in your app/ios folder.

If you are asked to agree to terms, Agree.

In the main menu, go to 

Xcode > Preferences > Location and choose the command line tools installed.

Close Xcode.

## Android Studio

Download and install Android Studio.

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
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

and / or update

```console
brew update
```

## Install CocoaPods

```console
sudo gem install cocoapods
```

## Install Node Version Manager

You will want to be able to easily switch between versions of node for different projects.

```console
brew install nvm
```

Once this is done, it will give you some code to copy into your ~/.zscrc file.

```console
nano ~/.zshrc
```

Scroll or down arrow all the way to the bottom of the file.

Paste in the following code given to you in the installation script (it should look something like this)

```zsh
export NVM_DIR="$HOME/.nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
  [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
  ```

Restart your terminal or run ```source ~/.zshrc```

Then, install a node version or two (change out for the latest version)

```console
nvm install 16
```

Check that it is installed by running

```console
node -v
```

## Install Yarn

```console
npm i yarn -g
```

## Install Java

We want to have multiple versions of java so as we develop over time we can easily switch between them.  I'm going to show you Java 8 and Java 11.  A lot of projects are on Java 8.  I'm currently using Java 11.  There are newer versions - you can explore at your own risk.

```console
brew tap adoptopenjdk/openjdk
```

Then

```console
brew install adoptopenjdk8
brew install adoptopenjdk11
```

We need to edit our command line now.  I'm going to use nano - if you prefer a different editor, fine.

```console
nano ~/.zshrc
```

Scroll or down arrow all the way to the bottom of the file.

Paste in the following code

```console
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)

alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java11='export JAVA_HOME=$JAVA_11_HOME'

#default to Java 11
java11
```

Close out of nano and save.

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
