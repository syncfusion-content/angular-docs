---
layout: post
title:  Getting Started with Electron
description: Desktop application using Electron for Syncfusion Angular seed -webpack
platform: Angular
control: Introduction
documentation: ug
---

# Desktop application using Electron for Syncfusion Angular seed

[Electron](https://electron.atom.io/docs/tutorial/quick-start/) is a framework which enables the development of cross-platform desktop application using web technologies(HTML,CSS,JavaScript).

The Syncfusion [angular-seed](https://github.com/syncfusion/angular2-seeds) application is fully configured to work with Essential Studio for JavaScript Angular components, in which we configured our [ej-angular2](https://github.com/syncfusion/ej-angular2) library and necessary changes to consume our Angular components.

The below steps depict how to create desktop app of Syncfusion Angular seed application(webpack) using Electron.

## Prerequisites

* [Node.js](https://nodejs.org/en/) (v6.x.x or higher)
* [NPM](https://docs.npmjs.com/getting-started/installing-node#install-npm--manage-npm-versions) (v5.4.2 or higher)

## Synopsis

* [Clone the seed application](#clone-the-seed-application)
* [Installing Electron dependencies](#installing-electron-dependencies)
* [Configure Electron application window](#configure-electron-application-window-for-electron)
* [Index file configuration](#index-file-configuration)
* [Adding NPM script for running Electron app](#adding-npm-script-for-running-electron-app)
* [Run the electron app](#run-the-electron-app)
* [Packaging the electron app](#packaging-the-app)
* [Run the Executable File](#run-the-executable-file)

## Clone the seed application

Clone the angular seed application from GitHub repository. Use below command to clone the application.

{% highlight javascript %}
git clone https://github.com/syncfusion/angular2-seeds
{% endhighlight %}

 
To install NPM packages run the below command in root of the cloned seed application.

{% highlight javascript %}
npm install
{% endhighlight %}

## Installing Electron dependencies 

[electron](https://www.npmjs.com/package/electron) - The Electron framework lets us write cross-platform desktop applications using JavaScript, HTML and CSS.

[electron-packager](https://www.npmjs.com/package/electron-packager) - Electron Packager is a command line tool that bundles Electron based application source code with a renamed Electron executable and supporting files into folders ready for distribution.

Run below set of commands to install electron dependencies which need to run and package the Angular application as desktop app.

{% highlight javascript %}
npm install electron --save-dev

npm install electron-packager --save-dev
{% endhighlight %}


## Configure Electron application window for Electron

Create folder named, `electron` under `src` folder and create JavaScript file `main.js` within electron folder. This `main.js` file is the `startup of electron application`. It should create window and it handles the system events. To know more about main process of electron, refer the link [here.](https://electron.atom.io/docs/tutorial/quick-start/#write-your-first-electron-app)

Copy the below code into main.js file.

{% highlight javascript %}

const {app, BrowserWindow} = require('electron')

// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let win

function createWindow () {
  // Create the browser window.
  win = new BrowserWindow({width: 800, height: 600})

  // and load the index.html of the app.
  win.loadURL('file://' + __dirname + '/index.html')

  // Open the DevTools.
  //win.webContents.openDevTools()

  // Emitted when the window is closed.
  win.on('closed', () => {
    // Dereference the window object, usually you would store windows
    // in an array if your app supports multi windows, this is the time
    // when you should delete the corresponding element.
    win = null
  })
}

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
// Some APIs can only be used after this event occurs.
app.on('ready', createWindow)

// Quit when all windows are closed.
app.on('window-all-closed', () => {
  // On macOS it is common for applications and their menu bar
  // to stay active until the user quits explicitly with Cmd + Q
  if (process.platform !== 'darwin') {
    app.quit()
  }
})

app.on('activate', () => {
  // On macOS it's common to re-create a window in the app when the
  // dock icon is clicked and there are no other windows open.
  if (win === null) {
    createWindow()
  }
})

// In this file you can include the rest of your app's specific main process
// code. You can also put them in separate files and require them here.
{% endhighlight %}

Specify the `main.js` file in [main](https://docs.npmjs.com/files/package.json#main) field of `package.json` file, which is the startup script of your app. Refer below code snippet for adding main field.

{% highlight javascript %}
{
  "name": "ejangular-webpack-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "main": "main.js",
  "description": "A webpack starter for Angular",
  "scripts": {
    "start": "webpack-dev-server --inline --progress --port 3000",
    "test": "karma start",
    "build": "rimraf dist && webpack --config config/webpack.prod.js --progress --profile --bail"
  } 
  }
}
{% endhighlight %}

## Index file configuration

The `src/index.html` file in Syncfusion Angular seed application need path changes to serve the local files. Since need to change `base href` in `index.html` file. Copy the below code into index.html file.

{% highlight html %}
<!DOCTYPE html>
<html>

<head>
    <base href="./">
     . . . . 
</head>

</html>
{% endhighlight %}

## Adding NPM script for running Electron app

The build NPM script will bundle the application into `dist` folder. We need to run the electron app from dist which requires `main.js` file and seed application dependencies before running the electron app. Add below NPM scripts in `package.json` file to create and launch electron app.

{% highlight javascript %}
"copy-assets": "xcopy src\\electron\\* dist\\ /y && xcopy package.json dist\\ /y && xcopy src\\deps dist\\src\\deps\\ /y /s /i",
"build-electron": "npm run build && npm run copy-assets",
"run-electron": "npm run build-electron && electron dist",
"build-electron-app": "npm run build-electron && electron-packager dist --overwrite"
{% endhighlight %}

## Run the electron app

To run electron app, run below command.

{% highlight javascript %}
npm run run-electron

{% endhighlight %}

## Packaging the app

Packaging the electron app using below command.

{% highlight javascript %}
npm run build-electron-app
{% endhighlight %}


## Run the Executable file

* The electron executable file is created in the location `ejangular-webpack-starter-win32-x64/ejangular-webpack-starter.exe`. Double click on the `.exe` file to launch the application.

![](/angular/GettingStarted/Images/electron-output-webpack.png)



