---
layout: post
title: Getting started with Webpack
description: Overview of Syncfusion Essential Angular 2.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Webpack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}
 
N> The cloned application is fully configured to work with Essential Studio for JavaScript Angular components, in which we configured our [ej-angular2](https://github.com/syncfusion/ej-angular2) library and necessary changes to consume our Angular components. 
 
## What is in Syncfusion cloned Angular seed.?
The cloned Angular seed consists of files in the following structure. The files in the `src` folder is used for our application logical functionalities. The other files available outside the src folder is used to build, bundle and deploy the application. 

* config
    * helpers.js
    * webpack.common.js
    * webpack.dev.js
    * webpack.prod.js
* src
    * app
        * app.component.ts
        * app.module.ts
    * main.ts
    * index.html
* package.json
* tsconfig.json
* webpack.config.js

The below table depicts the purpose of files in the above structure.

<table>
<tr>
<th>Files  </th>
<th>Purpose </th>
</tr>
<tr>
<td>webpack.config.js</td>
<td><ul><li>Webpack is a powerful module bundler which building a dependency graph, and emitting one or more bundles. </li> <li>With plugins and rules, Webpack can preprocess and minify different non-JavaScript files such as Typescript, SASS, and LESS files.</li> <li>We can determine what Webpack does and how it does it with a JavaScript configuration file.</li></ul></td>
</tr>
<tr>
<td>webpack.common.js</td>
<td>It is known as the common configuration file for development, production and test environments. The configuration imports dependencies with `require` statements and exports several objects as properties of a `module.exports` object.<ul><li>entries - We can supply webpack with one or more entry files and let it find and incorporate the dependencies that radiate from those entries.</li> <li>resolve -The application will import lot of java script and typescript files. But most `import` statements don't mention the extension at all. So, we should tell the Webpack to resolve extension-less file requests by looking for matching files with ts or js extension.</li> <li>plugins - It creates instances of the plugins. i.e. Webpack has a build pipeline with well-defined phases. Tap into that pipeline with plugins such as the `uglify` minification plugin.</li></ul></td>
</tr>
<tr>
<td>webpack.prod.js</td>
<td>Configuration of a production build resembles development configuration with a few key changes. We will deploy the application and its dependencies to a real production server. Here we have the additional plugins. <ul><li>NoEmitOnErrorsPlugin - Stops the build if there is an error.</li> <li>UglifyJsPlugin - It minifies the bundles</li> <li>ExtractTextPlugin - It extracts embedded css as external files, adding cache-busting hash to the filename</li> <li>DefinePlugin - It allows you to create global constants which can be configured at compile time. This can be useful for allowing different behavior between development builds and release builds.</li> </ul> </td>
</tr>
<tr>
<td>webpack.dev.js</td>
<td>The development build relies on the webpack development server, configured near the bottom of the file. Here, <ul> <li>Webpack puts output bundles in the `dist` folder</li> <li>HtmlwebpackPlugin use the public path and the filename settings to generate appropriate `script` and `link` tags into the index.html.</li> <li>CSS styles are buried inside the JavaScript bundles by default.</li> </ul> </td>
</tr>
<tr>
<td>src/app/app.component.ts</td>
<td>It is a top-level component where all the functionalities are lies in this component</td>
</tr>
<tr>
<td>src/app/app.module.ts</td>
<td>It tells the angular how to construct and bootstrap the app in the root module. In our application, it bootstraps the `AppComponent` to launch the application.</td>
</tr>
<tr>
<td>src/main.ts</td>
<td>The main entry point of the application, in which we kick-off our application by importing the `AppComponent` and bootstrapping it. </td>
</tr>
<tr>
<td>package.json</td>
<td>It serves as documentation for what packages our project depends on. It allows you to specify the name, version, scripts, dependencies of a package.<ul><li> Name- Name of our package </li> <li> Version- Current version of package </li> <li> Scripts- It runs at various time of lifecycle of package </li> <li> Dependencies- It is used for production in our application </li></ul> In our application, we used name, version, scripts and dependencies in package.json file </td>
</tr>
<tr>
<td> index.html  </td>
<td> It is the host page of application. It loads all needed libraries and essential scripts in a prescribed order. It holds a custom tag which is used for load the meta data of `AppComponent`. <br> E.g.: `ej-app` is the custom tag in our cloned seed application. </td>
</tr>
<tr>
<td>tsconfig.json</td>
<td>All typescript files need to be transpiled/compiled to native JavaScript files so that we can run them on browser. To accomplish this, we need to add `Typescript Configuration file` called as tsconfig.json, which is used as input of typescript compiler(tsc) to transpile the typescript files.</td>
</tr>
</table>

{% tabs %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './app.component.html',
})
export class AppComponent {
}

{% endhighlight %}

{% highlight ts %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { RouterModule } from '@angular/router';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';

import { EJAngular2Module } from 'ej-angular2';

import { AppComponent } from './app.component';
import { HomeComponent } from './home/home.component';
import { GridComponent } from './grid/grid.component';

import { rootRouterConfig } from './app.routes';

enableProdMode();

class CustomErrorHandler implements ErrorHandler {
  call(error, stackTrace = null, reason = null) {
    console.log(error + "\n" + stackTrace);
  }
  handleError(error: any): void {
    console.log(error);
  }
}

@NgModule({
  imports: [
    BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true }), EJAngular2Module.forRoot()
  ],
  declarations: [
    AppComponent, HomeComponent, GridComponent
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }

{% endhighlight %}

{% highlight ts %}

import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { enableProdMode } from '@angular/core';
import { AppModule } from './app/app.module';
if (process.env.ENV === 'production') {
  enableProdMode();
}
platformBrowserDynamic().bootstrapModule(AppModule);

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<html>

<head>
	<base href="/">
	<title>Essential JavaScript for Angular 2 | Webpack seed</title>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="shortcut icon" type="image/png" href="deps/images/favicon.ico">
	<link href="src/deps/default.css" rel="stylesheet" />
	<link href="../node_modules/bootstrap/dist/css/bootstrap.min.css" rel="stylesheet" />
</head>

<body>
	<ej-app>
		<div class="splash">
			<div class="message">Angular Syncfusion Components App</div>
			<div class="spinner"></div>
		</div>
	</ej-app>
</body>

</html>

{% endhighlight %}

{% highlight json %}

{
  "name": "ejangular-webpack-starter",
  "version": "1.0.0",
  "repository": {
    "type": "git",
    "url": "git+https://github.com/syncfusion/angular2-seeds.git"
  },
  "description": "A webpack starter for Angular",
  "scripts": {
    "start": "webpack-dev-server --inline --progress --port 3000",
    "test": "karma start",
    "build": "rimraf dist && webpack --config config/webpack.prod.js --progress --profile --bail"
  },
  "keywords": [
    "syncfusion",
    "ej",
    "essential",
    "javascript",
    "Angular 2",
    "angular2"
  ],
  "author": "Syncfusion Inc",
  "license": "SEE LICENSE IN README.md",
  "bugs": {
    "url": "https://github.com/syncfusion/angular2-seeds/issues"
  },
  "homepage": "https://github.com/syncfusion/angular2-seeds#readme",
  "dependencies": {
    "@angular/common": "~2.4.0",
    "@angular/compiler": "~2.4.0",
    "@angular/core": "~2.4.0",
    "@angular/forms": "~2.4.0",
    "@angular/http": "~2.4.0",
    "@angular/platform-browser": "~2.4.0",
    "@angular/platform-browser-dynamic": "~2.4.0",
    "@angular/router": "~3.4.0",
    "core-js": "^2.4.1",
    "rxjs": "5.0.1",
    "zone.js": "^0.7.4"
  },
  "devDependencies": {
    "angular2-template-loader": "^0.4.0",
    "awesome-typescript-loader": "^3.0.0-beta.17",
    "css-loader": "^0.23.1",
    "extract-text-webpack-plugin": "^1.0.1",
    "file-loader": "^0.8.5",
    "html-loader": "^0.4.3",
    "html-webpack-plugin": "^2.15.0",
    "jasmine-core": "^2.4.1",
    "karma": "^1.2.0",
    "karma-jasmine": "^1.0.2",
    "karma-phantomjs-launcher": "^1.0.2",
    "karma-sourcemap-loader": "^0.3.7",
    "karma-webpack": "^1.8.0",
    "null-loader": "^0.1.1",
    "phantomjs-prebuilt": "^2.1.7",
    "raw-loader": "^0.5.1",
    "rimraf": "^2.5.2",
    "style-loader": "^0.13.1",
    "typescript": "^2.1.4",
    "webpack": "^1.13.0",
    "webpack-dev-server": "^1.14.1",
    "webpack-merge": "^0.14.0",
    "bootstrap": "^3.3.6",
    "jquery": "^3.1.1",
    "jsrender": "^0.9.75",
    "syncfusion-javascript": "^15.1.33",
    "ej-angular2": "^15.1.33",
    "@types/ej.web.all": "^14.4.1",
    "@types/jquery": "2.0.34",
    "@types/es6-shim": "0.31.32",
    "@types/node": "^6.0.46"
  }
}

{% endhighlight %}

{% highlight javascript %}

module.exports = require('./config/webpack.dev.js');

{% endhighlight %}

{% endtabs %}

## Syntax of Angular component

{% highlight ts %}

//import statements
import {Component} from '@angular/core';

@Component ({
         . . . .
         . . . .
         // Takes metadata object from exported class
         // It describes how the HTML template and component class work together 
})

export class ComponentName { 
         . . . .
         // Exports the metadata object to component 
}

{% endhighlight %}

N> We recommend you to go through the [quick start](https://angular.io/docs/ts/latest/quickstart.html) of Angular application to get deeper knowledge of setup and structure of the application.

## Configuration of Syncfusion Javascript Widget Dependencies

* Syncfusion JavaScript widgets need `window.jQuery` to render the Angular components, since, we need to import jQuery in `vendor.ts` file and include `Syncfusion theme files` from `node_modules` as like the below code snippet

{% highlight javascript %}

import * as $ from 'jquery';
window["jQuery"] = $;
window["$"] = $;
import 'jsrender';
import '../node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css';

{% endhighlight %}

## Consuming ej-angular2 library

The cloned application already configured with `ej-angular2` library to seamlessly work with Angular and Essential JavaScript components. The below steps describe, how the library consumed in the Angular seed application.

* To install this library, run the below command in the root of Angular application.

{% highlight javascript %}

npm install ej-angular2 --save

{% endhighlight %}

*	We can import this library in any Angular application's AppModule. Here we imported the `ej-angular2` library in our cloned application.

{% highlight ts %}

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
// Import the library module
import { EJAngular2Module } from 'ej-angular2';

@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule,LibraryModule, EJAngular2Module.forRoot()],
  providers: [],
  bootstrap: [AppComponent]
})

export class AppModule { }

{% endhighlight %}

Now we can render any Syncfusion JavaScript Angular components in Angular application which we discussed in the next section.

## Adding sample with seed application

* Create `dialog` folder inside `src/app` folder.

* Create `dialog.component.html` view file inside `src/app/dialog` folder and render ejDialog Angular component using the below code example. 

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

* Create `dialog.component.ts` model file inside the folder `src/app/dialog` and create sample component using the below code example.

{% highlight ts %}
import { Component, ViewEncapsulation, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'ej-app',
  templateUrl: './dialog.component.html'
})
export class DialogComponent {
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

## Configure the routes for the Router

Before adding router configuration for above created ejDialog component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created Dialog sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#dialog" [routerLink]="['/dialog']">Dialog </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejDialog sample component and define the route in `src/app/app.routes.ts` file.

{% highlight ts %}
import { Routes } from '@angular/router';
. . . . 
import { DialogComponent } from './dialog/dialog.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'dialog', component: DialogComponent }
];
{% endhighlight %}

* Import and declare the ejDialog sample component into `app.module.ts` like the below code snippet.

{% highlight ts %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
. . . . .
import { DialogComponent } from './dialog/dialog.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , DialogComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

## Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Dialog tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](/angular/GettingStarted/Images/getting-started-output.png) 
 
## Demos

We have implemented our [Angular sample browser](http://ng2jq.syncfusion.com/) using Syncfusion Angular components.

