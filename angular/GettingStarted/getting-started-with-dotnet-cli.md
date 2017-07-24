---
layout: post
title:  Angular SPA on ASP.NET Core with .NET CLI
description: Overview of Syncfusion Essential Angular
platform: Angular
control: Introduction
documentation: ug
---


# Getting Started with Angular SPA on ASP.NET Core with .NET CLI

ASP.NET Single Page Application(SPA) helps you to build applications that include significant client-side interactions using HTML 5, CSS 3 and Javascript.

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
* [.NET Core SDK 1.1](https://www.microsoft.com/net/download/core#/current) 

## Install the SPA Template

* To create a new application in .Net Core, we should install the Single Page Application(SPA) template by following command

{% highlight js %}
dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
{% endhighlight %}

![](/angular/GettingStarted/Images/createtemplate.png)

* To generate a new angular project run the below command in your directory

{% highlight javascript %}

dotnet new angular

{% endhighlight %}


## Install the Dependencies

* To restore the .NET dependencies and install the NPM dependencies, run the below command in your root directory

{% highlight javascript %}

dotnet restore
npm install

{% endhighlight %}

N> To run the ASP.NET in development mode, set the below environment variable using command prompt and restart your command prompt to make the change take effect

{% highlight javascript %}

setx ASPNETCORE_ENVIRONMENT "Development"

{% endhighlight %}

![](/angular/GettingStarted/Images/environmentvariable.png)

N> To know more about environment varaible refer the [link](https://blogs.msdn.microsoft.com/webdev/2017/02/14/building-single-page-applications-on-asp-net-core-with-javascriptservices/)

## Configuration of Syncfusion Angular Component

* Open the project in Visual Studio Code or Visual Studio 2017 to configure the Syncfusion Components

* To install Syncfusion JavaScript for Angular components run below commands from sample's root folder.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save
npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}

* Import `ej-angular2` module into app.module.ts file

{% highlight ts %}

import { NgModule } from '@angular/core';
. . .
. . .
import { EJAngular2Module } from 'ej-angular2';

@NgModule({
bootstrap: [ AppComponent ],
declarations: [AppComponent,NavMenuComponent,CounterComponent,FetchDataComponent,HomeComponent],
imports: [
UniversalModule, // Must be first import. This automatically imports BrowserModule, HttpModule, and JsonpModule too.
RouterModule.forRoot([
{ path: '', redirectTo: 'home', pathMatch: 'full' },
{ path: 'home', component: HomeComponent },
{ path: 'counter', component: CounterComponent },
{ path: 'fetch-data', component: FetchDataComponent },
{ path: '**', redirectTo: 'home' }
]),
EJAngular2Module.forRoot()
]
})
export class AppModule {
}

{% endhighlight %}

* Syncfusion JavaScript components need `jQuery` to render the control, so import jQuery in `ClientApp/boot-client.ts` file which we already configured in our [webpack angular seed](https://github.com/syncfusion/angular2-seeds/blob/master/src/vendor.ts/#L12-L15) application.

{% highlight ts %}

import 'Angular-universal-polyfills/browser';
import { enableProdMode } from '@angular/core';
import { platformUniversalDynamic } from 'Angular-universal';
import * as $ from 'jquery'; // Import jQuery in Window Object 
window['jQuery'] = $;
window['$'] = $
import 'jsrender';
import { AppModule } from './app/app.module';
import 'bootstrap';

const rootElemTagName = 'app'; // Update this if you change your root component selector
...
...

{% endhighlight %}

* If you are using templates like grid, to render that component, we need to install and import dependency `jsrender` in `ClientApp/boot-client.ts` file. Run the below command to install jsrender.

{% highlight javascript %}

npm install jsrender --save

{% endhighlight %}

N> If we run our application, we will get the following error.

![](/angular/GettingStarted/Images/windowerror.png)

* To overcome this issue, modify the `Views/Home/index.cshtml` file is referred as below.

{% highlight javascript %}

@{
ViewData["Title"] = "Home Page";
}

<!--To overcome the issue "ReferenceError: window is not defined"-->
<app asp-ng2-prerender-module="ClientApp/dist/main-server">Loading...</app>

<script src="~/dist/vendor.js" asp-append-version="true"></script>
@section scripts {
<script src="~/dist/main-client.js" asp-append-version="true"></script>
}

{% endhighlight %}

## Bundling Syncfusion JavaScript Theme Files

* we can bundle `syncfusion-javascript` theme file into `vendor.css`. Refer to the below code snippet to import the theme file in `webpack.config.vendor.js` 

 {% highlight javascript %}
 module.exports = (env) => { 
    const extractCSS = new ExtractTextPlugin('vendor.css'); 
    const isDevBuild = !(env && env.prod); 
    const sharedConfig = { 
        stats: { modules: false }, 
        resolve: { extensions: ['.js'] }, 
        module: { 
            rules: [ 
                { test: /\.(png|woff|woff2|eot|ttf|svg)(\?|$)/, use: 'url-loader?limit=100000' }, 
                { 
                    test: /\.(png|jpe?g|gif|cur|svg|woff|woff2|ttf|eot|ico)$/, 
                    loader: 'file-loader?name=assets/[name].[hash].[ext]' 
                }, 
            ] 
        }, 
        entry: { 
            vendor: [ 
                '@angular/animations', 
                '@angular/common', 
                '@angular/compiler', 
                '@angular/core', 
                '@angular/forms', 
                '@angular/http', 
                '@angular/platform-browser', 
                '@angular/platform-browser-dynamic', 
                '@angular/router', 
                'bootstrap', 
                'syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css', 
                'bootstrap/dist/css/bootstrap.css', 
                'es6-shim', 
                'es6-promise', 
                'event-source-polyfill', 
                'jquery', 
                'zone.js', 
            ] 
        },   
        . . .
        . . .     
 {% endhighlight %}
 
* Syncfusion JavaScript theme files have more type of image files. To bundle these type files,  we can use `file-loader`. Run the below command to install file-loader package. 

{% highlight javascript %}
npm install file-loader --save-dev 
{% endhighlight %}

* Also configure the `webpack.config.vendor.js` file as like below code snippet. 

{% highlight javascript %}
module.exports = (env) => { 
    const extractCSS = new ExtractTextPlugin('vendor.css'); 
    const isDevBuild = !(env && env.prod); 
    const sharedConfig = { 
        stats: { modules: false }, 
        resolve: { extensions: ['.js'] }, 
        module: { 
            rules: [ 
                { test: /\.(png|woff|woff2|eot|ttf|svg)(\?|$)/, use: 'url-loader?limit=100000' }, 
                { 
                    test: /\.(png|jpe?g|gif|cur|svg|woff|woff2|ttf|eot|ico)$/, 
                    loader: 'file-loader?name=assets/[name].[hash].[ext]' 
                }, 
            ] 
        },   
        . . .
        . . .
{% endhighlight %}

* To bundle the Syncfusion Javsctipt Theme file, run the below command in your command prompt

{% highlight javascript %}

npm run build 

{% endhighlight %}

N> If you change the theme in `webpack.config.js` file , run th above command to bundle the new theme in application

## Adding Dialog sample

* Import the `ejDialog` component in `home.component.html`

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

* Create sample component using the below code example in `home.component.ts`

{% highlight ts %}

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
    selector: 'home',
    templateUrl: './home.component.html'
})
export class HomeComponent {
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

Refer the below codes to create the application

{% tabs %}

{% highlight ts %}

// Refer the code for app.component.ts file 

import { Component, ViewChild } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
  selector: 'home',
  templateUrl: './home.component.html'
})
export class HomeComponent {
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

<!-- Refer the code for app.component.html file -->

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

// Refer the code for app.module.ts file 

import { NgModule } from '@angular/core';
import { RouterModule } from '@angular/router';
import { UniversalModule } from 'angular2-universal';
import { AppComponent } from './components/app/app.component'
import { NavMenuComponent } from './components/navmenu/navmenu.component';
import { HomeComponent } from './components/home/home.component';
import { FetchDataComponent } from './components/fetchdata/fetchdata.component';
import { CounterComponent } from './components/counter/counter.component';
import { GridComponent } from './components/grid/grid.component';

import { EJAngular2Module } from 'ej-angular2';
@NgModule({
    bootstrap: [ AppComponent ],
    declarations: [
        AppComponent,
        NavMenuComponent,
        CounterComponent,
        FetchDataComponent,
        HomeComponent, 
        GridComponent
    ],
    imports: [
        UniversalModule, // Must be first import. This automatically imports BrowserModule, HttpModule, and JsonpModule too.
        RouterModule.forRoot([
            { path: '', redirectTo: 'home', pathMatch: 'full' },
            { path: 'home', component: HomeComponent },
            { path: 'counter', component: CounterComponent },
            { path: 'fetch-data', component: FetchDataComponent },
            { path: 'grid', component: GridComponent },
            { path: '**', redirectTo: 'home' }
        ]),
        EJAngular2Module.forRoot()
    ]
})
export class AppModule {
}

{% endhighlight %}

{% highlight ts %}

// Refer this code to import 'jQuery' in 'boot.client.ts'

import 'angular2-universal-polyfills/browser';
import { enableProdMode } from '@angular/core';
import { platformUniversalDynamic } from 'angular2-universal';
import * as $ from 'jquery';
window['jQuery'] = $;
window['$'] = $
import 'jsrender';
import { AppModule } from './app/app.module';
import 'bootstrap';
const rootElemTagName = 'app'; // Update this if you change your root component selector

// Enable either Hot Module Reloading or production mode
if (module['hot']) {
    module['hot'].accept();
    module['hot'].dispose(() => {
        // Before restarting the app, we create a new root element and dispose the old one
        const oldRootElem = document.querySelector(rootElemTagName);
        const newRootElem = document.createElement(rootElemTagName);
        oldRootElem.parentNode.insertBefore(newRootElem, oldRootElem);
        platform.destroy();
    });
} else {
    enableProdMode();
}

// Boot the application, either now or when the DOM content is loaded
const platform = platformUniversalDynamic();
const bootApplication = () => { platform.bootstrapModule(AppModule); };
if (document.readyState === 'complete') {
    bootApplication();
} else {
    document.addEventListener('DOMContentLoaded', bootApplication);
}

{% endhighlight %}

{% highlight html %}

<!--Refer the code for index.cshtml file-->

@{
    ViewData["Title"] = "Home Page";
}

<!--To overcome the issue "ReferenceError: window is not defined"-->
<app asp-ng2-prerender-module="ClientApp/dist/main-server">Loading...</app>

<script src="~/dist/vendor.js" asp-append-version="true"></script>
@section scripts {
    <script src="~/dist/main-client.js" asp-append-version="true"></script>
}

{% endhighlight %}

{% highlight json %}

// Refer this code for package.json file

{
  "name": "ejappliaction",
  "version": "0.0.0",
  "scripts": {
    "build": "webpack",
    "test": "karma start ClientApp/test/karma.conf.js"
  },
  "dependencies": {
    "@angular/common": "^2.4.5",
    "@angular/compiler": "^2.4.5",
    "@angular/core": "^2.4.5",
    "@angular/forms": "^2.4.5",
    "@angular/http": "^2.4.5",
    "@angular/platform-browser": "^2.4.5",
    "@angular/platform-browser-dynamic": "^2.4.5",
    "@angular/platform-server": "^2.4.5",
    "@angular/router": "^3.4.5",
    "@types/node": "^6.0.42",
    "angular2-platform-node": "~2.0.11",
    "angular2-template-loader": "^0.6.2",
    "angular2-universal": "^2.1.0-rc.1",
    "angular2-universal-patch": "^0.2.1",
    "angular2-universal-polyfills": "^2.1.0-rc.1",
    "aspnet-prerendering": "^2.0.0",
    "aspnet-webpack": "^1.0.17",
    "awesome-typescript-loader": "^3.0.0",
    "bootstrap": "^3.3.7",
    "css": "^2.2.1",
    "css-loader": "^0.25.0",
    "ej-angular2": "^15.2.41",
    "es6-shim": "^0.35.1",
    "event-source-polyfill": "^0.0.7",
    "expose-loader": "^0.7.1",
    "extract-text-webpack-plugin": "^2.0.0-rc",
    "file-loader": "^0.9.0",
    "html-loader": "^0.4.4",
    "isomorphic-fetch": "^2.2.1",
    "jquery": "^2.2.1",
    "json-loader": "^0.5.4",
    "jsrender": "^0.9.84",
    "preboot": "^4.5.2",
    "raw-loader": "^0.5.1",
    "rxjs": "^5.0.1",
    "style-loader": "^0.13.1",
    "syncfusion-javascript": "^15.1.41",
    "to-string-loader": "^1.1.5",
    "typescript": "^2.2.1",
    "url-loader": "^0.5.7",
    "webpack": "^2.2.0",
    "webpack-hot-middleware": "^2.12.2",
    "webpack-merge": "^0.14.1",
    "zone.js": "^0.7.6"
  },
  "devDependencies": {
    "@types/chai": "^3.4.34",
    "@types/ej.web.all": "^15.1.4",
    "@types/jasmine": "^2.5.37",
    "@types/jquery": "^2.0.43",
    "chai": "^3.5.0",
    "jasmine-core": "^2.5.2",
    "karma": "^1.3.0",
    "karma-chai": "^0.1.0",
    "karma-chrome-launcher": "^2.0.0",
    "karma-cli": "^1.0.1",
    "karma-jasmine": "^1.0.2",
    "karma-webpack": "^1.8.0"
  }
}

{% endhighlight %}

{% endtabs %}

## Run the Application

* Now run the application with below command and navigate to [http://localhost:5000/](http://localhost:5000/) to see the output window.

{% highlight javascript %}

dotnet run

{% endhighlight %}

## Running the Application using Visual Studio 2017

* Open the `.csproj` file which is in project folder and then press `Ctrl+F5` to launch the application in a browser.

![](/angular/GettingStarted/Images/spatemplateoutput.png)
