# Electron vs. React Native for Mac

This repository contains the source code of three applications built with [Electron](https://www.electronjs.org/) or [React Native for Mac](https://microsoft.github.io/react-native-windows/docs/rnm-getting-started):

* **`electron-app`** - An Electron application based on the instructions of the "[Quick Start](https://www.electronjs.org/docs/tutorial/quick-start)" page of the Electron Documentation. It displays a simple, static HTML document inside of the shell.
* **`electron-react-ts-app`** - An Electron application based on [Electron Forge](https://www.electronforge.io/)'s React, TypeScript and Webpack template. It displays an HTML document that has the `<App />` component rendered within a `<div id="root" />` container element.
* **`rnMacWindows`** - A React Native for Windows and macOS application bootstrapped with `react-native-macos-init`.

Since each application is barebones, a comparison of their memory consumption can be considered fair and valid.

Electron applications come packaged with a copy of Chromium and Node.js. They display a web page within a browser window, but add unnecessary overhead and results in a greater consumption of memory. With React Native for Mac, the React components provided by the framework map to native components. Therefore, you don't need additional software like Chromium or Node.js to be packaged within your application since the compiled build will be compatible with its target platform.  

## Building `electron-app`

Run the following commands to generate a release build of the `electron-app` application:

```shell
$ cd electron-app
$ npm run make:mac
```

## Building `electron-react-ts-app`

Run the following commands to generate a release build of the `electron-react-ts-app` application:

```shell
$ cd electron-react-ts-app
$ npm run make:mac
```

## Building `rnMacWindows`

Run the following commands to generate a release build of the `rnMacWindows` application:

```shell
$ cd electron-react-ts-app
$ npm run build:mac
```

## Results

Memory-wise, the application built with React Native for Mac only spawns a single process, not four processes like an application built with Electron (one main and three helper processes per application). That one single process consumes less memory than the combined memory consumption of an Electron application's four processes.

Output of `top` command:

![](https://www.dl.dropboxusercontent.com/s/77vf771055ljq4s/fhdasuh19821212e.png)

Space-wise, the application built with React Native for Mac takes up significantly less space on your machine than the applications built with Electron. 

![](https://www.dl.dropboxusercontent.com/s/mbofq2i84al70nn/Screen%20Shot%202021-07-07%20at%201.12.29%20AM.png)