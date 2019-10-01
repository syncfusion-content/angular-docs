---
layout: post
title:  Getting Started Angular CLI with Electron | Syncfusion
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---
 

# Getting Started Angular CLI with Electron

The [Angular CLI](https://cli.angular.io/) is a command line interface is used to create an Angular application that already works. 

[Electron](https://electron.atom.io/docs/tutorial/quick-start/) is a framework which enables the development of cross-platform desktop application using web technologies(HTML,CSS,JavaScript.)

To getting started with Syncfusion Angular components, the NPM packages [ej-angular2](https://www.npmjs.com/package/ej-angular2) and [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) helps to seamlessly supports [angular-cli]((https://cli.angular.io/)) environment.

The following steps depicts, to create an application in angular-cli with Syncfusion Angular Components and integrate into Electron.

## Prerequisites

* [Node JS](https://nodejs.org/en/) (v6.x.x or higher)
* [NPM](https://docs.npmjs.com/getting-started/installing-node#install-npm--manage-npm-versions) (v3.x.x or higher)

The following synopsis illustrates the major steps in creation of application.

## Synopsis 

* [Install the latest version of Angular CLI](#install-the-angular-cli)
* [Create new Application](#create-a-new-application)
* [Configure Syncfusion Angular Component in Angular CLI](#configure-syncfusion-angular-component-in-angular-cli)
* [Refer the Syncfusion Theme Files](#refer-the-syncfusion-theme-files)
* [Render Syncfusion Angular Component](#render-syncfusion-angular-component)
* [Serve the Application with AngularCLI](#serve-the-application-with-angularcli)
* [Integration of Electron](#integration-of-electron)
* [Install the Electron](#install-the-electron)
* [Electron Configuration](#electron-configuration)
* [Build the Application with Electron](#build-the-application-with-electron)
* [Application Distribution with Electron Packager](#application-distribution-with-electron-packager)
* [Run the Executable File](#run-the-executable-file)

## Install the Angular CLI

* To install the angular-cli globally, run the following command in Command Prompt

{% highlight javascript %}
npm install -g @angular/cli
{% endhighlight %}

N> To know more about angular-cli commands refer [here](https://github.com/angular/angular-cli)

## Create a new Application

* To create a new Angular application run the below command in Command Prompt

{% highlight javascript %}
ng new project-name
E.g.: ng new angular-electron
{% endhighlight %}

N> This command installs all the required dependencies for Angular application.

## Configure Syncfusion Angular Component in Angular CLI
 
* To configure the Syncfusion Angular component, change the directory to your application's root folder 

{% highlight javascript %}
cd project-name

E.g.: cd angular-electron
{% endhighlight %}

* Essential JavaScript provides support for Angular Framework through wrappers. Since, we need the dependencies `ej-angular2` package and `syncfusion-javascript` package. Run the below commands, to install the dependencies.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save

{% endhighlight %}

* We are working with `typescript`, since, we need to install the typings dependencies `jquery` and `ej.web.all`. We may need of accessing the `ej` object for Syncfusion widget's properties in Angular application, which is defined in `ej.web.all` typings file.
E.g.  `ej.TextAlign.right`

{% highlight javascript %}

npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}

* And also include the typings `jquery` and `ej.web.all` in `src/tsconfig.app.json` file. 

{% highlight javascript %}

{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "module": "es2015",
    "baseUrl": "",
    "types": [
      "jquery",
      "ej.web.all"
    ]
  },
  "exclude": [
    "test.ts",
    "**/*.spec.ts"
  ]
}

{% endhighlight %}

* Syncfusion JavaScript widgets need `window.jQuery` object to render the Angular components, since, we need to import jQuery in `src/polyfills.ts` file as like the below code snippet which we already configured in our [webpack angular seed](https://github.com/syncfusion/angular2-seeds/blob/master/src/vendor.ts/#L12-L14) application.

{% highlight javascript %}

import * as jquery from 'jquery';
window['jQuery'] = jquery;
window['$'] = jquery;

{% endhighlight %}

## Refer the Syncfusion Theme Files

* We configured the Syncfusion Angular components and their dependencies. For the appearance we need to include `Syncfusion theme files` from `node_modules` in style section of `angular-cli.json` file. Here, we referred the `material theme`. 

{% highlight javascript %}
{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "project": {
    "name": "my-app"
  },
  "apps": [
    {
      "root": "src",
      "outDir": "dist",
       . . .
       . . .
      "styles": [
        "styles.css",
         "./../node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css" 
      ],
      "scripts": [],
       . . . 
       . . .
      }

{% endhighlight %}

## Render Syncfusion Angular Component

* To render any Syncfusion Angular Components into the project, we need to import `EJAngular2Module` from `ej-angular2` package in `app.module.ts` file. Refer to the below code snippet to import Syncfusion Angular components.

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { EJAngular2Module } from 'ej-angular2'; 
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,EJAngular2Module.forRoot() 
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

* Now we can render any Angular component. Here, We rendered the `ejDialog` Angular component in angular-cli. Refer the below code snippet for `app.component.html` file.

{% highlight html %}
<div id="parent" >
	<input id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" *ngIf="button_display"/>
	<ej-dialog id="basicDialog" #dialog title="Facebook" [(enableResize)]="resize" containment="#parent" (close)="onClose($event)">
		Facebook is an online social networking service headquartered in Menlo Park, California. Its website was launched on February
		4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo Saverin, Andrew McCollum, Dustin
		Moskovitz and Chris Hughes. The founders had initially limited the website's membership to Harvard students, but later
		expanded it to colleges in the Boston area, the Ivy League, and Stanford University. It gradually added support for students
		at various other universities and later to high-school students.
	</ej-dialog>
</div>
{% endhighlight %}

* Modify the `app.component.ts` file using the below code example.

 {% highlight ts %}
 
import { Component, ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  resize: boolean;
  button_display: boolean;
  @ViewChild('dialog') dialog: EJComponents <any,any>;
    constructor() {
    this.resize = false;
    this.button_display = false;
  }
  //Button click event handler to open the ejDialog
  onClick(event) {
   this.button_display = false;
   this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event) {
    this.button_display = true;
  }
}

 {% endhighlight %}

## Serve the Application with AngularCLI

Now, navigate to the root of the application and run the application using the below command and navigate to the appropriate port [http://localhost:4200](localhost:4200) in browser.

{% highlight javascript %}

ng serve

{% endhighlight %}

* We configured the Syncfusion Angular components in Angular CLI. Now, we are going to configure the Electron in the next section.

## Integration of Electron

[Electron](https://electron.atom.io/docs/tutorial/quick-start/) is a framework which enables the development of cross-platform desktop application using web technologies(HTML,CSS,JavaScript.)

## Install the Electron

* To install the Electron package, run the below command in your application's root directory.

{% highlight javascript %}
npm install electron --save-dev
{% endhighlight %}

## Electron Configuration

* To configure the electron in our application, create `main.js` file outside the `src` directory. This `main.js` file is the `startup of electron application`. It should create window and it handles the system events.To know more about main process of electron, refer the link [here](https://electron.atom.io/docs/tutorial/quick-start/#write-your-first-electron-app)

Refer to the below code snippet for `electron/main.js` file.

{% highlight javascript %}
// src/electron/main.js
 
const {app, BrowserWindow} = require('electron')
 
// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let win
 
function createWindow () {
  // Create the browser window.
  win = new BrowserWindow({width: 800, height: 600})
 
  // and load the index.html of the app.directory name is angular-electron.
  win.loadFile('./dist/angular-electron/index.html');
 
  // Open the DevTools.
  // win.webContents.openDevTools()
 
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

* Include the created `main.js` file in [main](https://docs.npmjs.com/files/package.json#main) field of package.json file.

Refer to the below code snippet for `package.json` file.
{% highlight javascript %}
 "name": "angular-electron",
  "version": "0.0.0",
  "main": "main.js",
  ...
  ...
{% endhighlight %}

* Electron is using the `file://` protocol instead of `http://`. So, we need to modify the `base href` in `index.html` as like the below code snippet.
{% highlight javascript %}
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>AngularElectron</title>
  <base href="./">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <app-root></app-root>
</body>
</html>
{% endhighlight %}

## Build the Application with Electron

* To build the application with electron, we should add the `npm scripts` in `package.json` file as like the below code snippet.

{% highlight javascript %}
 "electron-build": "ng build --prod ",
 "electron": "electron",
 {% endhighlight %}

The below table explains the functionalities of above npm scripts.

|npm scripts              | Functionality       |
|:------------------------|:--------------------|
|electron-build|It builds the application using ngc compiler and copy the `main.js` file and `package.json` file to `dist` folder|
|electron      |It runs the build-electron script and launch the application from dist folder|

* Now, run the below command to build the application with electron and it will launch the electron application.

{% highlight javascript %}

npm run eletron-build

npm run electron
 
{% endhighlight %}

## Application Distribution with Electron Packager

Package the Electron app into OS-specific bundles(.app, .exe, etc.) via JavaScript or the command line. [Electron Packager](https://www.npmjs.com/package/electron-packager) is a command line tool and Node.js library that bundles Electron-based application source code with a renamed Electron executable and supporting files into folders ready for distribution.

Refer the below steps to distribute the executable electron application.

* To install the electron-packager, run the below command in your application's root directory.
{% highlight javascript %}
npm install electron-packager --save-dev
{% endhighlight %} 

* To package the Electron app as executable file, add the `npm script` in `package.json` file as like the below code snippet.
{% highlight javascript %}
    "electron-package": "electron-packager dist ej-angular-package --overwrite"
{% endhighlight %}

* Now run the below command in application's root directory.
{% highlight javascript %}
npm run electron-package
{% endhighlight %}

Refer the below codes to create the application

{% tabs %}

{% highlight ts %}

// Refer the code for app.component.ts file (src/app/app.component.ts)

import { Component,  ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  resize: boolean;
  button_display: boolean;
  @ViewChild('dialog') dialog: EJComponents<any, any>;
  constructor() {
    this.resize = false;
    this.button_display = false;
  }
  //Button click event handler to open the ejDialog
  onClick(event) {
    this.button_display = false;
    this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event) {
    this.button_display = true;
  }
}
{% endhighlight %}

{% highlight html %}

<!-- Refer the code for app.component.html file (src/app/app.component.html)-->

<div id="parent" >
	<input id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" *ngIf="button_display" />
	<ej-dialog id="basicDialog" #dialog title="Facebook" [(enableResize)]="resize" containment="#parent" (close)="onClose($event)">
		Facebook is an online social networking service headquartered in Menlo Park, California. Its website was launched on February
		4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo Saverin, Andrew McCollum, Dustin
		Moskovitz and Chris Hughes. The founders had initially limited the website's membership to Harvard students, but later
		expanded it to colleges in the Boston area, the Ivy League, and Stanford University. It gradually added support for students
		at various other universities and later to high-school students.
	</ej-dialog>
</div>
{% endhighlight %}

{% highlight ts %}

// Refer the code for app.module.ts file (src/app/app.module.ts)

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { EJAngular2Module } from 'ej-angular2';  
import { AppComponent } from './app.component';
 
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,EJAngular2Module.forRoot() 
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight ts %}
// Refer the code for main.ts (src/main.ts)

import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule);

{% endhighlight %}

{% highlight json %}

// Refer the code for angular-cli.json file 

{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "project": {
    "name": "angular-electron"
  },
  "apps": [
    {
      "root": "src",
      "outDir": "dist",
      "assets": [
        "assets",
        "favicon.ico"
      ],
      "index": "index.html",
      "main": "main.ts",
      "polyfills": "polyfills.ts",
      "test": "test.ts",
      "tsconfig": "tsconfig.app.json",
      "testTsconfig": "tsconfig.spec.json",
      "prefix": "app",
      "styles": [
        "styles.css",
        "./../node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css" 
      ],
      "scripts": [],
      "environmentSource": "environments/environment.ts",
      "environments": {
        "dev": "environments/environment.ts",
        "prod": "environments/environment.prod.ts"
      }
    }
  ],
  "e2e": {
    "protractor": {
      "config": "./protractor.conf.js"
    }
  },
  "lint": [
    {
      "project": "src/tsconfig.app.json",
      "exclude": "**/node_modules/**"
    },
    {
      "project": "src/tsconfig.spec.json",
      "exclude": "**/node_modules/**"
    },
    {
      "project": "e2e/tsconfig.e2e.json",
      "exclude": "**/node_modules/**"
    }
  ],
  "test": {
    "karma": {
      "config": "./karma.conf.js"
    }
  },
  "defaults": {
    "styleExt": "css",
    "component": {}
  }
}


{% endhighlight %}

{% highlight ts %}

// Refer the code for polyfills.ts (src/polyfills.ts)

/** Evergreen browsers require these. **/
import 'core-js/es6/reflect';
import 'core-js/es7/reflect';


/** ALL Firefox browsers require the following to support `@angular/animation`. **/
// import 'web-animations-js';  // Run `npm install --save web-animations-js`.



/***************************************************************************************************
 * Zone JS is required by Angular itself.
 */
import 'zone.js/dist/zone';  // Included with Angular CLI.

import * as jquery from 'jquery';
window['jQuery'] = jquery;
window['$'] = jquery;
//import './../node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css'; 

/***************************************************************************************************
 * APPLICATION IMPORTS
 */

/**
 * Date, currency, decimal and percent pipes.
 * Needed for: All but Chrome, Firefox, Edge, IE11 and Safari 10
 */
// import 'intl';  // Run `npm install --save intl`.

{% endhighlight %}

{% highlight json %}

// Refer the code for tsconfig.app.json(src/tsconfig.app.json)
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "module": "es2015",
    "baseUrl": "",
    "types": [
      "jquery",
      "ej.web.all"
    ]
  },
  "exclude": [
    "test.ts",
    "**/*.spec.ts"
  ]
}

{% endhighlight %}

{% highlight json %}


// Refer the code for package.json file  

{
  "name": "angular-electron",
  "version": "0.0.0",
  "main": "main.js",
  "license": "MIT",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e",
    "build-electron": "ng build --base-href . && xcopy src\\electron\\* dist && xcopy package.json dist",
    "electron": "npm run build-electron && electron dist",
    "electron-package": "electron-packager dist ej-angular-package --overwrite"
  },
  "private": true,
  "dependencies": {
    "@angular/animations": "^4.2.4",
    "@angular/common": "^4.2.4",
    "@angular/compiler": "^4.2.4",
    "@angular/core": "^4.2.4",
    "@angular/forms": "^4.2.4",
    "@angular/http": "^4.2.4",
    "@angular/platform-browser": "^4.2.4",
    "@angular/platform-browser-dynamic": "^4.2.4",
    "@angular/router": "^4.2.4",
    "core-js": "^2.4.1",
    "ej-angular2": "^15.3.29",
    "rxjs": "^5.4.2",
    "syncfusion-javascript": "^15.3.29",
    "zone.js": "^0.8.14"
  },
  "devDependencies": {
    "@angular/cli": "1.4.3",
    "@angular/compiler-cli": "^4.2.4",
    "@angular/language-service": "^4.2.4",
    "@types/ej.web.all": "^15.3.3",
    "@types/jasmine": "~2.5.53",
    "@types/jasminewd2": "~2.0.2",
    "@types/jquery": "^3.2.12",
    "@types/node": "~6.0.60",
    "codelyzer": "~3.1.1",
    "electron": "^1.7.8",
    "electron-packager": "^9.1.0",
    "electron-rebuild": "^1.6.0",
    "jasmine-core": "~2.6.2",
    "jasmine-spec-reporter": "~4.1.0",
    "karma": "~1.7.0",
    "karma-chrome-launcher": "~2.1.1",
    "karma-cli": "~1.0.1",
    "karma-coverage-istanbul-reporter": "^1.2.1",
    "karma-jasmine": "~1.1.0",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.1.2",
    "ts-node": "~3.2.0",
    "tslint": "~5.3.2",
    "typescript": "~2.3.3"
  }
}

{% endhighlight %}

{% highlight javascript %}
// Refer the below code for main.js file(src/electron/main.js)
// src/electron/main.js
 
const {app, BrowserWindow} = require('electron')
 
// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let win
 
function createWindow () {
  // Create the browser window.
  win = new BrowserWindow({width: 800, height: 600})
 
  // and load the index.html of the app.
  win.loadURL(`file://${__dirname}/index.html`)
 
  // Open the DevTools.
  // win.webContents.openDevTools()
 
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

{% endtabs %}

## Run the Executable file

* The electron executable file is created in the location `ej-angular-package-win32-x64/ej-angular-package.exe`. Double click on the `.exe` file to launch the application.

![Electron Output](./angular/GettingStarted/Images/electronoutput.png)

