## React Native for React Devs

Docs link: https://docs.google.com/document/d/1JfZjoqg-OCYuqFXl9SZxvS9pro0GMyW_NUw5H2tuYac/edit?usp=sharing

### Getting Started
* Make sure that you are using the latest version of MacOS
* Navigate to: https://facebook.github.io/react-native/docs/getting-started.html
  * At the top, you have two options, Quick Start or Building Projects with Native Code. Select Building Projects with `Native Code`
  * Select the proper `Development OS` and `Target OS`. Follow the instructions.
    * Note: when installing Xcode (for mac), you need to make sure that you have the most up to date OS, or it will get angry and not install.
* After following the instructions, create a new application by running `react-native init [project name]`
* When you first run `react-native run-ios` or `react-native run-android`, be prepared to wait for a few mins...it takes its sweet time.

### Some of the basics
* Use the `<Text></Text>` component for displaying text. You need to use it if you want text to show up. You will lose time searching for a bug if you don’t remember this early on.
* Replace `<div>` with `<View></View>`, the most fundamental component for building a UI in react-native.
* Instead of using `<img src={}  />` for images, use `<Image source={}  />`.
* No more `<input />`, you should use the <TextInput /> component.

### Styling in React Native

You may have heard that styling in React Native isn’t fun. It isn’t. Many of the CSS style properties that you are used to are not supported for React Native. Here are some resources to help out with that…
* React Native Styling Cheat Sheet: https://github.com/vhpoet/react-native-styling-cheat-sheet#flexbox
* `<View>` style props: https://facebook.github.io/react-native/docs/view-style-props.html
* `<Text>` style props: https://facebook.github.io/react-native/docs/text-style-props.html
* `<Image />` style props: https://facebook.github.io/react-native/docs/image-style-props.html

Another option is to use a library such as styled-components. Styled-components supports more of the CSS properties that you are used to.: https://www.npmjs.com/package/styled-components
From what I have read and seen through searching the interwebs, there are not tons of good component libs for React Native. Here are some options at the time that this guide was written:

* NativeBase: https://nativebase.io/
* React Native Material Design: https://github.com/react-native-material-design/react-native-material-design
* React Native Elements: https://github.com/react-native-training/react-native-elements
* React Native Material Kit: https://github.com/xinthink/react-native-material-kit

If none of these options are providing you with what you want, then you always have the option of learning how to style with the CSS properties that are supported for React Native: https://facebook.github.io/react-native/docs/stylesheet.html

A few things to know:

* Components in React Native are styled using JavaScript. You will not use a class/className prop for styling. You will instead use the style prop. The style prop can either be an object, or an array of styles. Convert kabob case to camel case, example: background-color should be backgroundColor.
* Height and width dimensions are unitless. If you want something to have a height of ‘50px’, just use: height: 50
* Flexbox works a little differently. On the web, flex-direction defaults to ‘row’, while in React Native, flexDirection defaults to column. The flex property specifies how a flex item will grow or shrink so as to fit the space available in the flex container (https://developer.mozilla.org/en-US/docs/Web/CSS/flex). In React Native, the flex property only supports using a single number, eg. flex: 2.

### HTTP Requests
* Use axios, just like you have been using for all your other projects.

### Routing
* Use: `react-router-native`. There is another lib out there called ‘react-native-router’, which you don’t want, but it is easy to confuse the two.
* Use `<Route>` and `<Link>` just like you normally do with `react-router-dom`
* Docs: https://reacttraining.com/react-router/native/example/Basic

### Redux
* You can use redux and react-redux libs in a React Native app just like you would normally for your React apps.
* Here is what index.js will look like:

```
import React from 'react';
import {AppRegistry} from 'react-native';
import App from './src/App';
import {Provider} from 'react-redux';
import store from './src/store';

const providerWrapper = () => (
    <Provider store={store}>
        <App/>
    </Provider>
)

AppRegistry.registerComponent('rn_example', () => providerWrapper);

```
