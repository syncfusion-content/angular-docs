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
* [.NET Core SDK 2.0](https://www.microsoft.com/net/download/core#/current) 

## Install the SPA Template

* To create a new application in .Net Core, we should install the Single Page Application(SPA) template by following command.

{% highlight js %}
dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
{% endhighlight %}

![](/angular/GettingStarted/Images/createtemplate.png)

* To generate a new angular project run the below command in your directory.

{% highlight javascript %}

dotnet new angular

{% endhighlight %}


## Install the Dependencies

* To restore the .NET dependencies and install the NPM dependencies, run the below command in your root directory.

{% highlight javascript %}

dotnet restore
npm install

{% endhighlight %}

N> To run the ASP.NET in development mode, set the below environment variable using command prompt and restart your command prompt to make the change take effect.

{% highlight javascript %}

setx ASPNETCORE_ENVIRONMENT "Development"

{% endhighlight %}

![](/angular/GettingStarted/Images/environmentvariable.png)

N> To know more about environment variable refer the [link](https://blogs.msdn.microsoft.com/webdev/2017/02/14/building-single-page-applications-on-asp-net-core-with-javascriptservices/)

## Configuration of Syncfusion Angular Component

* Open the project in Visual Studio Code or Visual Studio 2017 to configure the Syncfusion Components.

* To install Syncfusion JavaScript for Angular components run below commands from sample's root folder.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save
npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}


* Import `ej-angular2` module into `app.module.shared.ts` file.

{% highlight ts %}

import { NgModule } from '@angular/core';
. . .
. . .
import { EJAngular2Module } from 'ej-angular2';

@NgModule({
    declarations: [
        AppComponent,
        NavMenuComponent,
        CounterComponent,
        FetchDataComponent,
        HomeComponent
    ],
    imports: [
        CommonModule,
        HttpModule,
        FormsModule,
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
export class AppModuleShared {
}

{% endhighlight %}

* Syncfusion JavaScript components need jQuery to render the control, so add jQuery plugin in `webpack.config.js` file. Refer to the below code snippet.

{% highlight javascript %}
. . .
. . .
    const clientBundleConfig = merge(sharedConfig, {
        entry: { 'main-client': './ClientApp/boot.browser.ts' },
        output: { path: path.join(__dirname, clientBundleOutputDir) },
        plugins: [
            new webpack.ProvidePlugin({
                '$': "jquery",
                'jQuery': "jquery",
                'window.jQuery': "jquery",
                'window.$': 'jquery'
                }), 
            new webpack.DllReferencePlugin({
                context: __dirname,
                manifest: require('./wwwroot/dist/vendor-manifest.json')
            })
       ...
       ...
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

* We are going to configure bundling of `syncfusion-javascript` theme file into `vendor.css` by importing the file in `webpack.config.vendor.js`. 

 {% highlight javascript %}
 const path = require('path');
const webpack = require('webpack');
const ExtractTextPlugin = require('extract-text-webpack-plugin');
const merge = require('webpack-merge');
const treeShakableModules = [
    '@angular/animations',
    '@angular/common',
    '@angular/compiler',
    '@angular/core',
    '@angular/forms',
    '@angular/http',
    '@angular/platform-browser',
    '@angular/platform-browser-dynamic',
    '@angular/router',
    'zone.js',
];
const nonTreeShakableModules = [
    'bootstrap',
    'bootstrap/dist/css/bootstrap.css',
    'syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css', 
    'es6-promise',
    'es6-shim',
    'event-source-polyfill',
    'jquery',
];
        . . .
        . . .     
 {% endhighlight %}

* Also add `gif and cur` filetypes in `webpack.config.vendor.js` to load `syncfusion-javascript` theme's used files(.png, .jpg, etc.). 

{% highlight javascript %}
. . .
. . .
const allModules = treeShakableModules.concat(nonTreeShakableModules);

module.exports = (env) => {
    const extractCSS = new ExtractTextPlugin('vendor.css');
    const isDevBuild = !(env && env.prod);
    const sharedConfig = {
        stats: { modules: false },
        resolve: { extensions: [ '.js' ] },
        module: {
            rules: [
                { test: /\.(png|woff|woff2|eot|ttf|svg|gif|cur)(\?|$)/, use: 'url-loader?limit=100000' }
            ]
        },
        output: {
            publicPath: 'dist/',
            filename: '[name].js',
            library: '[name]_[hash]'
        },
        . . .
        . . .
{% endhighlight %}

* To bundle the Syncfusion JavaScript Theme file, add the below script in `package.json` file.

{% highlight javascript %}

"build": "webpack --config webpack.config.vendor.js && webpack"

{% endhighlight %}

* After adding the script in `package.json` file, Run the below command in your command prompt.

{% highlight javascript %}

npm run build 

{% endhighlight %}

N> If you change the theme in `webpack.config.vendor.js` file, run the above command to bundle the new theme in application.

N> If you get an error like below screenshot while bundling other themes in application, then change the output path from `dist/` to `./` in `webpack.config.vendor.js` file. 

![](/angular/GettingStarted/Images/bundlingerror.png)

Refer to the below code snippet to change the output path in `webpack.config.vendor.js`.

{% highlight javascript %}
module.exports = (env) => {
    const extractCSS = new ExtractTextPlugin('vendor.css');
    const isDevBuild = !(env && env.prod);
    const sharedConfig = {
        stats: { modules: false },
        resolve: { extensions: [ '.js' ] },
        module: {
            rules: [
                { test: /\.(png|woff|woff2|eot|ttf|svg|gif|cur)(\?|$)/, use: 'url-loader?limit=100000' },
            ]
        },
        output: {
            publicPath: './',
            filename: '[name].js',
            library: '[name]_[hash]'
        },
        . . .
         . . .
{% endhighlight %}

## Adding Dialog sample

* Import the `ejDialog` component in `home.component.html`.

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

* Create sample component using the below code example in `home.component.ts`.

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
  onClick(event: any) {
    this.btndisplay = false;
    this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event: any) {
    this.btndisplay = true;
  }
}

{% endhighlight %}


Refer the below codes to create the application.

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
  onClick(event: any) {
    this.btndisplay = false;
    this.dialog.widget.element.ejDialog('open');
  }
  //Dialog close event handler
  onClose(event: any) {
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

// Refer the code for app.module.shared.ts file 

import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';
import { HttpModule } from '@angular/http';
import { RouterModule } from '@angular/router';

import { AppComponent } from './components/app/app.component';
import { NavMenuComponent } from './components/navmenu/navmenu.component';
import { HomeComponent } from './components/home/home.component';
import { FetchDataComponent } from './components/fetchdata/fetchdata.component';
import { CounterComponent } from './components/counter/counter.component';
import { EJAngular2Module } from 'ej-angular2';

@NgModule({
    declarations: [
        AppComponent,
        NavMenuComponent,
        CounterComponent,
        FetchDataComponent,
        HomeComponent
    ],
    imports: [
        CommonModule,
        HttpModule,
        FormsModule,
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
export class AppModuleShared {
}

{% endhighlight %}

{% highlight javascript %}

// Refer this code to add 'jQuery plugin' in 'webpack.config.js'

const path = require('path');
const webpack = require('webpack');
const merge = require('webpack-merge');
const AotPlugin = require('@ngtools/webpack').AotPlugin;
const CheckerPlugin = require('awesome-typescript-loader').CheckerPlugin;

module.exports = (env) => {
    // Configuration in common to both client-side and server-side bundles
    const isDevBuild = !(env && env.prod);
    const sharedConfig = {
        stats: { modules: false },
        context: __dirname,
        resolve: { extensions: [ '.js', '.ts' ] },
        output: {
            filename: '[name].js',
            publicPath: 'dist/' // Webpack dev middleware, if enabled, handles requests for this URL prefix
        },
        module: {
            rules: [
                { test: /\.ts$/, include: /ClientApp/, use: isDevBuild ? ['awesome-typescript-loader?silent=true', 'angular2-template-loader'] : '@ngtools/webpack' },
                { test: /\.html$/, use: 'html-loader?minimize=false' },
                { test: /\.css$/, use: [ 'to-string-loader', isDevBuild ? 'css-loader' : 'css-loader?minimize' ] },
                { test: /\.(png|jpg|jpeg|gif|svg)$/, use: 'url-loader?limit=25000' }
            ]
        },
        plugins: [new CheckerPlugin()]
    };

    // Configuration for client-side bundle suitable for running in browsers
    const clientBundleOutputDir = './wwwroot/dist';
    const clientBundleConfig = merge(sharedConfig, {
        entry: { 'main-client': './ClientApp/boot.browser.ts' },
        output: { path: path.join(__dirname, clientBundleOutputDir) },
        plugins: [
            new webpack.ProvidePlugin({
                '$': "jquery",
                'jQuery': "jquery",
                'window.jQuery': "jquery",
                'window.$': 'jquery'
                }), 
            new webpack.DllReferencePlugin({
                context: __dirname,
                manifest: require('./wwwroot/dist/vendor-manifest.json')
            })
        ].concat(isDevBuild ? [
            // Plugins that apply in development builds only
            new webpack.SourceMapDevToolPlugin({
                filename: '[file].map', // Remove this line if you prefer inline source maps
                moduleFilenameTemplate: path.relative(clientBundleOutputDir, '[resourcePath]') // Point sourcemap entries to the original file locations on disk
            })
        ] : [
            // Plugins that apply in production builds only
            new webpack.optimize.UglifyJsPlugin(),
            new AotPlugin({
                tsConfigPath: './tsconfig.json',
                entryModule: path.join(__dirname, 'ClientApp/app/app.module.browser#AppModule'),
                exclude: ['./**/*.server.ts']
            })
        ])
    });

    // Configuration for server-side (prerendering) bundle suitable for running in Node
    const serverBundleConfig = merge(sharedConfig, {
        resolve: { mainFields: ['main'] },
        entry: { 'main-server': './ClientApp/boot.server.ts' },
        plugins: [
            new webpack.DllReferencePlugin({
                context: __dirname,
                manifest: require('./ClientApp/dist/vendor-manifest.json'),
                sourceType: 'commonjs2',
                name: './vendor'
            })
        ].concat(isDevBuild ? [] : [
            // Plugins that apply in production builds only
            new AotPlugin({
                tsConfigPath: './tsconfig.json',
                entryModule: path.join(__dirname, 'ClientApp/app/app.module.server#AppModule'),
                exclude: ['./**/*.browser.ts']
            })
        ]),
        output: {
            libraryTarget: 'commonjs',
            path: path.join(__dirname, './ClientApp/dist')
        },
        target: 'node',
        devtool: 'inline-source-map'
    });

    return [clientBundleConfig, serverBundleConfig];
};

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
  "private": true,
  "version": "0.0.0",
  "scripts": {
    "test": "karma start ClientApp/test/karma.conf.js",
    "build": "webpack --config webpack.config.vendor.js && webpack"
  },
  "dependencies": {
    "@angular/animations": "4.2.5",
    "@angular/common": "4.2.5",
    "@angular/compiler": "4.2.5",
    "@angular/compiler-cli": "4.2.5",
    "@angular/core": "4.2.5",
    "@angular/forms": "4.2.5",
    "@angular/http": "4.2.5",
    "@angular/platform-browser": "4.2.5",
    "@angular/platform-browser-dynamic": "4.2.5",
    "@angular/platform-server": "4.2.5",
    "@angular/router": "4.2.5",
    "@ngtools/webpack": "1.5.0",
    "@types/webpack-env": "1.13.0",
    "angular2-template-loader": "0.6.2",
    "aspnet-prerendering": "^3.0.1",
    "aspnet-webpack": "^2.0.1",
    "awesome-typescript-loader": "3.2.1",
    "bootstrap": "3.3.7",
    "css": "2.2.1",
    "css-loader": "0.28.4",
    "ej-angular2": "^15.3.29",
    "es6-shim": "0.35.3",
    "event-source-polyfill": "0.0.9",
    "expose-loader": "0.7.3",
    "extract-text-webpack-plugin": "2.1.2",
    "file-loader": "^0.11.2",
    "html-loader": "0.4.5",
    "isomorphic-fetch": "2.2.1",
    "jquery": "3.2.1",
    "json-loader": "0.5.4",
    "preboot": "4.5.2",
    "raw-loader": "0.5.1",
    "reflect-metadata": "0.1.10",
    "rxjs": "5.4.2",
    "style-loader": "0.18.2",
    "syncfusion-javascript": "^15.3.29",
    "to-string-loader": "1.1.5",
    "typescript": "2.4.1",
    "url-loader": "0.5.9",
    "webpack": "2.5.1",
    "webpack-hot-middleware": "2.18.2",
    "webpack-merge": "4.1.0",
    "zone.js": "0.8.12"
  },
  "devDependencies": {
    "@types/chai": "4.0.1",
    "@types/ej.web.all": "^15.3.2",
    "@types/jasmine": "2.5.53",
    "@types/jquery": "^3.2.12",
    "chai": "4.0.2",
    "jasmine-core": "2.6.4",
    "karma": "1.7.0",
    "karma-chai": "0.1.0",
    "karma-chrome-launcher": "2.2.0",
    "karma-cli": "1.0.1",
    "karma-jasmine": "1.1.0",
    "karma-webpack": "2.0.3"
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
