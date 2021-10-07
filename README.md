## How to Set up a Mac for React-Native Development

Getting your computer set up for development in React-Native is no easy task.  To avoid endless googling, here are some guides to send you on your way.  I'm going to assume default paths for most things, and depending on the age of your machine, the operating system, etc some of these variables may change.  I am assuming you are on a Mac, as it isn't really possible to do full stack dev and deploy on a PC.  You can do react-native development for Android, but if you are going to run a cross platform app, you need a Mac.

## Create a react-native project

There are many different ways to do this, and that is not what this page is about.  Pick your poison.  

```npx react-native init MyTestApp```

That is probably the easiest - [full docs on React Native here](https://reactnative.dev/).

## Xcode

Open your terminal and type in

```xcode-select —install```

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

## Command Line

Open Terminal.

I like a pretty terminal - most macs are defaulting to zsh, and I am assuming that is your terminal.

I use [beeman's shell settings](https://github.com/beeman/server-shell)

```sh -c "$(curl -fsSL https://raw.github.com/beeman/server-shell/master/tools/install.sh)"```

Restart your terminal.

## Install Homebrew

If you are on a new machine and haven't installed Homebrew run

```ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

and / or update

```brew update```

## Install Node Version Manager

You will want to be able to easily switch between versions of node for different projects.

```brew install nvm```

Once this is done, it will give you some code to copy into your ~/.zscrc file.

```nano ~/.zshrc```

Scroll or down arrow all the way to the bottom of the file.

Paste in the following code given to you in the installation script (it should look something like this)

```
export NVM_DIR="$HOME/.nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
  [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
  ```

Restart your terminal.

Then, install a node version or two

```nvm install 15```

Check that it is installed by running

```node -v```

## Install Yarn

```npm i yarn -g```

## Install Java

We want to have multiple versions of java so as we develop over time we can easily switch between them.  I'm going to show you Java 8 and Java 11.  A lot of projects are on Java 8.  I'm currently using Java 11.  There are newer versions - you can explore at your own risk.

```brew tap adoptopenjdk/openjdk```

Then

```brew install adoptopenjdk8```
```brew install adoptopenjdk11```

We need to edit our command line now.  I'm going to use nano - if you prefer a different editor, fine.

```nano ~/.zshrc```

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

Restart your terminal. 

Make sure it is loading:

```java --version```

## Install Reactotron

```brew install reactotron```



### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/justinhandley/setup-for-react-native-development/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
