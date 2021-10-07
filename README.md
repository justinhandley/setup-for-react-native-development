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

That is all you need to start.

## Android Studio

Download and install Android Studio.



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
