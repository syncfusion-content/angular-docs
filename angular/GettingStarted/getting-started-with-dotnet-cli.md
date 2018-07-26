---
layout: post
title:  Angular SPA on ASP.NET Core with .NET CLI
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---

# Getting Started with Angular SPA on ASP.NET Core with .NET CLI

ASP.NET Single Page Application(SPA) helps you to build applications that include significant client-side interactions using HTML 5, CSS 3 and JavaScript.

To getting started with Syncfusion Angular Components, the NPM packages [ej-angular2](https://www.npmjs.com/package/ej-angular2) and [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) helps to seamlessly supports ASP.NET Core environment for our components. The following steps depicts, to create an application in ASP.NET Core using SPA template with Syncfusion Angular Components.

## Synopsis

* [Prerequisites](#prerequisites)
* [Install the SPA Template](#install-the-spa-template)
* [Install the Dependencies](#install-the-dependencies)
* [Configuration of Syncfusion Angular Component](#configuration-of-syncfusion-angular-component)
* [Bundling Syncfusion JavaScript Theme Files](#bundling-syncfusion-javascript-theme-files)
* [Adding Dialog Sample](#adding-dialog-sample) 
* [Run the Application](#run-the-application)

## Prerequisites

* [Node JS](https://nodejs.org/en/)(v6.x.x or higher)
* [NPM](http://blog.npmjs.org/post/85484771375/how-to-install-npm)(v4.x.x or higher)
* [.NET Core SDK 2.1.302](https://www.microsoft.com/net/download/core#/current)

## Install the SPA Template

* To create a new application in .NET Core, we should install the Single Page Application(SPA) template by following command.

{% highlight js %}
dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
{% endhighlight %}

![](/angular/GettingStarted/Images/createtemplate.png)

* To generate a new Angular project run the below command in your directory.

{% highlight javascript %}

dotnet new angular

{% endhighlight %}

## Install the Dependencies

* To restore the .NET dependencies and install the NPM dependencies, run the below command in your root directory.

{% highlight javascript %}

dotnet restore
npm install // Run this command in ClientApp folder

{% endhighlight %}

N> To run the ASP.NET in development mode, set the below environment variable using command prompt and restart your command prompt to make the change take effect.

{% highlight javascript %}

setx ASPNETCORE_ENVIRONMENT "Development"

{% endhighlight %}

![](/angular/GettingStarted/Images/environmentvariable.png)

N> To know more about environment variable refer the [link](https://blogs.msdn.microsoft.com/webdev/2017/02/14/building-single-page-applications-on-asp-net-core-with-javascriptservices/)

## Configuration of Syncfusion Angular Component

* Open the project in Visual Studio Code or Visual Studio 2017 to configure the Syncfusion Components.

* To install Syncfusion JavaScript for Angular components run below commands from `ClientApp` folder.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save
npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}

* And also include the typings `jquery` and `ej.web.all` in `ClientApp/src/tsconfig.app.json` file.

{% highlight javascript %}

{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "baseUrl": "./",
    "module": "es2015",
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

* Syncfusion JavaScript widgets need `window.jQuery` object to render the Angular components, since, we need to import jQuery in `ClientApp/src/polyfills.ts` file as like the below code snippet.

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
    "name": "aspcoresample"
  },
  "apps": [
    {
      "root": "src",
      "outDir": "dist",
      . . .
      . . .
      "styles": [
        "styles.css",
        "../node_modules/bootstrap/dist/css/bootstrap.min.css",
        // Here we have referred Syncfusion Theme
        "./../node_modules/syncfusion-javascript/Content/ej/web/office-365/ej.web.all.min.css"  
      ],
      "scripts": [],
      "environmentSource": "environments/environment.ts",
      "environments": {
        "dev": "environments/environment.ts",
        "prod": "environments/environment.prod.ts"
      }
    }
  ],
 . . .
  }
}

{% endhighlight %}

## Render Syncfusion Angular Component

* To render any Syncfusion Angular Components into the project, we need to import `ej-angular2` module into `ClientApp/src/app/app.module.ts` file. Refer to the below code snippet.

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpClientModule } from '@angular/common/http';
import { RouterModule } from '@angular/router';
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { NavMenuComponent } from './nav-menu/nav-menu.component';
import { HomeComponent } from './home/home.component';
import { CounterComponent } from './counter/counter.component';
import { FetchDataComponent } from './fetch-data/fetch-data.component';

@NgModule({
  declarations: [
    AppComponent,
    NavMenuComponent,
    HomeComponent,
    CounterComponent,
    FetchDataComponent
  ],
  imports: [
    BrowserModule.withServerTransition({ appId: 'ng-cli-universal' }),
    HttpClientModule,
    FormsModule,
    RouterModule.forRoot([
      { path: '', component: HomeComponent, pathMatch: 'full' },
      { path: 'counter', component: CounterComponent },
      { path: 'fetch-data', component: FetchDataComponent },
    ]), EJAngular2Module.forRoot()
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

## Adding Dialog sample

* Render the `ejDialog` component in `ClientApp/src/app/home/home.component.html`.

{% highlight html %}

<div id="parent">
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

* Modify the `home.component.ts` file using the below code example.

{% highlight ts %}

import { Component, ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
})
export class HomeComponent {
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

Refer the below codes to create the application.

{% tabs %}

{% highlight ts %}

// Refer the code for home.component.ts file.

import { Component, ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'app-home',
  templateUrl: './home.component.html',
})
export class HomeComponent {
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

{% highlight html %}

<!-- Refer the code for home.component.html file -->

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

// Refer the code for app.module.ts file

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpClientModule } from '@angular/common/http';
import { RouterModule } from '@angular/router';
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { NavMenuComponent } from './nav-menu/nav-menu.component';
import { HomeComponent } from './home/home.component';
import { CounterComponent } from './counter/counter.component';
import { FetchDataComponent } from './fetch-data/fetch-data.component';

@NgModule({
  declarations: [
    AppComponent,
    NavMenuComponent,
    HomeComponent,
    CounterComponent,
    FetchDataComponent
  ],
  imports: [
    BrowserModule.withServerTransition({ appId: 'ng-cli-universal' }),
    HttpClientModule,
    FormsModule,
    RouterModule.forRoot([
      { path: '', component: HomeComponent, pathMatch: 'full' },
      { path: 'counter', component: CounterComponent },
      { path: 'fetch-data', component: FetchDataComponent },
    ]), EJAngular2Module.forRoot()
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight json %}

// Refer the code for angular-cli.json file.

{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "project": {
    "name": "aspcoresample"
  },
  "apps": [
    {
      "root": "src",
      "outDir": "dist",
      "assets": [
        "assets"
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
        "../node_modules/bootstrap/dist/css/bootstrap.min.css",
        "./../node_modules/syncfusion-javascript/Content/ej/web/office-365/ej.web.all.min.css" 
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
    "component": {},
    "build": {
      "progress": true
    }
  }
}

{% endhighlight %}

{% highlight ts %}

// Refer the code for polyfills.ts (src/polyfills.ts)

/**
 * This file includes polyfills needed by Angular and is loaded before the app.
 * You can add your own extra polyfills to this file.
 *
 * This file is divided into 2 sections:
 *   1. Browser polyfills. These are applied before loading ZoneJS and are sorted by browsers.
 *   2. Application imports. Files imported after ZoneJS that should be loaded before your main
 *      file.
 *
 * The current setup is for so-called "evergreen" browsers; the last versions of browsers that
 * automatically update themselves. This includes Safari >= 10, Chrome >= 55 (including Opera),
 * Edge >= 13 on the desktop, and iOS 10 and Chrome on mobile.
 *
 * Learn more in https://angular.io/docs/ts/latest/guide/browser-support.html
 */

/***************************************************************************************************
 * BROWSER POLYFILLS
 */

/** IE9, IE10 and IE11 requires all of the following polyfills. **/
// import 'core-js/es6/symbol';
// import 'core-js/es6/object';
// import 'core-js/es6/function';
// import 'core-js/es6/parse-int';
// import 'core-js/es6/parse-float';
// import 'core-js/es6/number';
// import 'core-js/es6/math';
// import 'core-js/es6/string';
// import 'core-js/es6/date';
// import 'core-js/es6/array';
// import 'core-js/es6/regexp';
// import 'core-js/es6/map';
// import 'core-js/es6/weak-map';
// import 'core-js/es6/set';

/** IE10 and IE11 requires the following for NgClass support on SVG elements */
// import 'classlist.js';  // Run `npm install --save classlist.js`.

/** IE10 and IE11 requires the following for the Reflect API. */
// import 'core-js/es6/reflect';


/** Evergreen browsers require these. **/
// Used for reflect-metadata in JIT. If you use AOT (and only Angular decorators), you can remove.
import 'core-js/es7/reflect';


/**
 * Required to support Web Animations `@angular/platform-browser/animations`.
 * Needed for: All but Chrome, Firefox and Opera. http://caniuse.com/#feat=web-animation
 **/
// import 'web-animations-js';  // Run `npm install --save web-animations-js`.

/**
 * By default, zone.js will patch all possible macroTask and DomEvents
 * user can disable parts of macroTask/DomEvents patch by setting following flags
 */

 // (window as any).__Zone_disable_requestAnimationFrame = true; // disable patch requestAnimationFrame
 // (window as any).__Zone_disable_on_property = true; // disable patch onProperty such as onclick
 // (window as any).__zone_symbol__BLACK_LISTED_EVENTS = ['scroll', 'mousemove']; // disable patch specified eventNames

 /*
 * in IE/Edge developer tools, the addEventListener will also be wrapped by zone.js
 * with the following flag, it will bypass `zone.js` patch for IE/Edge
 */
// (window as any).__Zone_enable_cross_context_check = true;

/***************************************************************************************************
 * Zone JS is required by default for Angular itself.
 */
import 'zone.js/dist/zone';  // Included with Angular CLI.

import * as jquery from 'jquery';
window['jQuery'] = jquery;
window['$'] = jquery;

/***************************************************************************************************
 * APPLICATION IMPORTS
 */

{% endhighlight %}

{% highlight json %}

// Refer the code for tsconfig.app.json(src/tsconfig.app.json)
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "../out-tsc/app",
    "baseUrl": "./",
    "module": "es2015",
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

{% endtabs %}

## Run the Application

* Now run the application with below command in application folder.

{% highlight javascript %}

dotnet run

{% endhighlight %}

## Running the Application using Visual Studio 2017

* Open the `.csproj` file which is in project folder and then press `Ctrl+F5` to launch the application in a browser.

![](/angular/GettingStarted/Images/spatemplateoutput.png)

## Sample Application

We have prepared .NET CLI Application with the above steps. Refer to the link for application
[Getting Started with .NET CLI](http://www.syncfusion.com/downloads/support/directtrac/general/ze/aspcoresample1576232350.zip). Run the below commands at the root of the application, to launch the application.

```batch

`dotnet restore` in Application folder

`npm install` in ClientApp Folder

`dotnet run` in Application folder

```
