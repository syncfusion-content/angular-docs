---
layout: post
title:  Getting Started with Electron
description: Desktop application using Electron for Syncfusion Angular seed - SystemJS
platform: Angular
control: Introduction
documentation: ug
---

# Desktop application using Electron for Syncfusion Angular seed

[Electron](https://electron.atom.io/docs/tutorial/quick-start/) is a framework which enables the development of cross-platform desktop application using web technologies(HTML,CSS,JavaScript).

The Syncfusion [angular-seed](https://github.com/syncfusion/angular2-seeds) application is fully configured to work with Essential Studio for JavaScript Angular components, in which we configured our [ej-angular2](https://github.com/syncfusion/ej-angular2) library and necessary changes to consume our Angular components.

The below steps depict how to create desktop app of Syncfusion Angular seed application(SystemJS) using Electron.

## Prerequisites

* [Node.js](https://nodejs.org/en/) (v6.x.x or higher)
* [NPM](https://docs.npmjs.com/getting-started/installing-node#install-npm--manage-npm-versions) (v5.4.2 or higher)

## Synopsis

* [Clone the seed application](#clone-the-seed-application)
* [Installing Electron dependencies](#installing-electron-dependencies)
* [Configure Electron application window](#configure-electron-application-window-for-electron)
* [jQuery configuration](#jquery-configuration)
* [Adding NPM script for running Electron app](#adding-npm-script-for-running-electron-app)
* [Run the electron app](#run-the-electron-app)
* [Packaging the electron app](#packaging-the-app)
* [Run the Executable File](#run-the-executable-file)

## Clone the seed application

Clone the angular seed application from GitHub repository. Use below command to clone the application.

{% highlight javascript %}
git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs 
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

Create JavaScript file `main.js` at root of application. This `main.js` file is the `startup of electron application`. It should create window and it handles the system events. To know more about main process of electron, refer the link [here.](https://electron.atom.io/docs/tutorial/quick-start/#write-your-first-electron-app)

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

## jQuery configuration

To resolve the [issue](https://github.com/electron/electron/issues/254) `jQuery is not defined` add below script section into index.html file. Refer the below code snippet.

{% highlight html %}

<script>window.$ = window.jQuery = require('jquery');</script>

{% endhighlight %}

## Adding NPM script for running Electron app

To transpile the typescript file run `tsc` compiler, before start electron app. Here we run the electron app from root folder, add below script into `package.json` file for running and packaging electron app.

{% highlight javascript %}

"run-electron": "npm run tsc && electron .",
"build-electron-app": "npm run tsc &&electron-packager . --overwrite"

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

* The electron executable file is created in the location `ejangular2-systemjs-starter-win32-x64/ejangular2-systemjs-starter.exe`. Double click on the `.exe` file to launch the application.

![](/angular/GettingStarted/Images/electron-output-systemjs.png)




