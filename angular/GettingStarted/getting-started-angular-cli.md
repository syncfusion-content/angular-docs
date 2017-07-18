---
layout: post
title:  Getting Started with Angular CLI
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---
 

# Getting Started with Angular CLI

The [Angular CLI](https://cli.angular.io/) is a command line interface for Angular which makes it easy to create an application that already works. To getting started with Syncfusion Angular components, the NPM packages [ej-angular2](https://www.npmjs.com/package/ej-angular2) and [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) helps to seamlessly supports angular-cli environment for our components.

The following steps depicts, to create an application in angular-cli with Syncfusion Angular Components

## Prerequisites

* [Node JS](https://nodejs.org/en/) (v6.x.x or higher)
* [NPM](http://blog.npmjs.org/post/85484771375/how-to-install-npm) (v3.x.x or higher)

The following synopsis illustrates the major steps in creation of application.

## Synopsis 

* [Install the latest version of Angular CLI](#install-the-angular-cli)
* [Create new Application](#create-a-new-application)
* [Configuration of Syncfusion Angular Component](#configuration-of-syncfusion-angular-component)
* [Render Syncfusion Angular Component](#render-syncfusion-angular-component)
* [Serve the application](#serve-the-application)

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
E.g.: ng new ejProject
{% endhighlight %}

N> This command installs all the required dependencies for Angular application.

## Configuration of Syncfusion Angular Component

We need to install the below packages to work with Syncfusion Angular components.
 
* Run the below command to move to sample's root folder of created application.

{% highlight javascript %}
cd project-name

E.g.: cd ejProject
{% endhighlight %}

* To install Syncfusion JavaScript and Angular components along with typings, run below commands from sample's root folder.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save
npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}

* Include the required typings `jquery` and `ej.web.all` in `tsconfig.app.json` file. 

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

* Include `Syncfusion theme files` from `node_modules` in style section of `angular-cli.json` file.

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

* Syncfusion JavaScript widgets need `window.jQuery` to render the Angular components, since, we need to import jQuery in `polyfills.ts` file as like the below code snippet which we already configured in our [webpack angular seed](https://github.com/syncfusion/angular2-seeds/blob/master/src/vendor.ts/#L12-L14) application.

{% highlight javascript %}

import * as jquery from 'jquery';
window['jQuery'] = jquery;
window['$'] = jquery;

{% endhighlight %}

## Render Syncfusion Angular Component

* To render `ejDialog` Angular component in angular-cli, modify the `app.component.html` file using the below code example.

{% highlight html %}
<div id="parent" >
	<input id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" *ngIf="btndisplay"/>
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
})
export class AppComponent {
  resize: boolean;
  btndisplay: boolean;
  @ViewChild('dialog') dialog: EJComponents <any,any>;
    constructor() {
    this.resize = false;
    this.btndisplay = false;
  }
  //Button click event handler to open the ejDialog
  onClick(event) {
   this.btndisplay = false;
   this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event) {
    this.btndisplay = true;
  }
}

 {% endhighlight %}


* Import `EJAngular2Module` from `ej-angular2` package in `app.module.ts` file to import Syncfusion Angular components into the project. Refer to the below code snippets to import Syncfusion Angular components.

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { EJAngular2Module } from 'ej-angular2'; 
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,FormsModule,HttpModule,EJAngular2Module.forRoot() 
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

Refer the below codes to create the application

{% tabs %}

{% highlight ts %}

import { Component,  ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  resize: boolean;
  btndisplay: boolean;
  @ViewChild('dialog') dialog: EJComponents<any, any>;
  constructor() {
    this.resize = false;
    this.btndisplay = false;
  }
  //Button click event handler to open the ejDialog
  onClick(event) {
    this.btndisplay = false;
    this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event) {
    this.btndisplay = true;
  }
}
{% endhighlight %}

{% highlight html %}

<div id="parent" >
	<input id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" *ngIf="btndisplay" />
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
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { EJAngular2Module } from 'ej-angular2';  
import { AppComponent } from './app.component';
 
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,FormsModule,HttpModule,EJAngular2Module.forRoot() 
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight ts %}
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
{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "project": {
    "name": "angularcliaot"
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
      "project": "src/tsconfig.app.json"
    },
    {
      "project": "src/tsconfig.spec.json"
    },
    {
      "project": "e2e/tsconfig.e2e.json"
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

// Refer the code for polyfills.ts
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

// Refer the code for tsconfig.app.json
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

{
  "name": "angularcliaot",
  "version": "0.0.0",
  "license": "MIT",
  "scripts": {
  
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "private": true,
  "dependencies": {
    "@angular/common": "^4.0.0",
    "@angular/compiler": "^4.0.0",
    "@angular/core": "^4.0.0",
    "@angular/forms": "^4.0.0",
    "@angular/http": "^4.0.0",
    "@angular/platform-browser": "^4.0.0",
    "@angular/platform-browser-dynamic": "^4.0.0",
    "@angular/router": "^4.0.0",
    "core-js": "^2.4.1",
    "ej-angular2": "^15.2.41",
    "jquery": "^3.2.1",
    "rxjs": "^5.1.0",
    "syncfusion-javascript": "^15.1.41",
    "zone.js": "^0.8.4"
  },
  "devDependencies": {
    "@angular/cli": "1.0.0",
    "@angular/compiler-cli": "^4.0.0",
    "@types/ej.web.all": "^15.1.4",
    "@types/jasmine": "2.5.38",
    "@types/jquery": "^2.0.43",
    "@types/es6-shim": "0.31.32",
    "@types/node": "~6.0.60",
    "codelyzer": "~2.0.0",
    "jasmine-core": "~2.5.2",
    "jasmine-spec-reporter": "~3.2.0",
    "karma": "~1.4.1",
    "karma-chrome-launcher": "~2.0.0",
    "karma-cli": "~1.0.1",
    "karma-coverage-istanbul-reporter": "^0.2.0",
    "karma-jasmine": "~1.1.0",
    "karma-jasmine-html-reporter": "^0.2.2",
    "protractor": "~5.1.0",
    "ts-node": "~2.0.0",
    "tslint": "~4.5.0",
    "typescript": "~2.2.0"
  }
}

{% endhighlight %}

{% endtabs %}

## Serve the Application

Now, navigate to the root of the application and run the application using the below command and navigate to the appropriate port [http://localhost:4200](localhost:4200) in browser

{% highlight javascript %}

ng serve

{% endhighlight %}

![](/angular/GettingStarted/Images/angularcli.png)

## ng build - production

To generate production build, run below command.

{% highlight javascript %}
node_modules\.bin\ng build --prod
{% endhighlight %}

If you get error `FATAL ERROR: CALL_AND_RETRY_LAST Allocation failed - JavaScript heap out of memory` add `--max_old_space_size=xxxx` space in `ngc.cmd` and `ng.cmd` file from `node_modules\.bin` folder.

Modify **ngc.cmd**

{% highlight javascript %}
@IF EXIST "%~dp0\node.exe" ( 
  "%~dp0\node.exe" --max_old_space_size=1000 "%~dp0\..\@angular\compiler-cli\src\main.js" %* 
) ELSE ( 
  @SETLOCAL 
  @SET PATHEXT=%PATHEXT:;.JS;=;% 
  node  "%~dp0\..\@angular\compiler-cli\src\main.js" %* 
) 
{% endhighlight %}

Modify **ng.cmd**

{% highlight javascript %}
@IF EXIST "%~dp0\node.exe" ( 
  "%~dp0\node.exe" --max_old_space_size=1000 "%~dp0\..\@angular\cli\bin\ng" %* 
) ELSE ( 
  @SETLOCAL 
  @SET PATHEXT=%PATHEXT:;.JS;=;% 
  node  "%~dp0\..\@angular\cli\bin\ng" %* 
)
{% endhighlight %}

### Importing required Syncfusion Angular components

Importing `EJAngular2Module` from `ej-angular2` package may cause bundle size bigger, because it imports all Syncfusion Angular components and all its Syncfusion JavaScript dependencies. So, we recommend to import required Angular component from ej-angular2 package as like below code sample. 

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser'; 
import { NgModule } from '@angular/core'; 
import { EJ_GRID_COMPONENTS } from 'ej-angular2/src/ej/grid.component'; 
import { AppComponent } from './app.component'; 
 
@NgModule({ 
  declarations: [ 
    AppComponent, EJ_GRID_COMPONENTS 
  ], 
  imports: [ 
    BrowserModule 
  ], 
  providers: [], 
  bootstrap: [AppComponent] 
}) 
export class AppModule { } 

{% endhighlight %}