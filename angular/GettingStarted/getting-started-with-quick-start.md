---
layout: post
title: Getting started with Quick Start Webpack
description: Overview of Syncfusion Essential Angular.
platform: Angular
control: Introduction
documentation: ug
---


# Getting started with Quick Start Webpack

Webpack is a popular module bundler, a tool for bundling application source code in convenient chunks and for loading that code from a server into a browser

## Prerequisites

* [Node JS](https://nodejs.org/en/) (v6.x.x or higher)
* [NPM](http://blog.npmjs.org/post/85484771375/how-to-install-npm) (v3.x.x or higher)

## Synopsis 

* [Clone the Quick Start](#clone-the-quick-start)
* [Dependencies installation](#dependencies-installation)
* [Configure Syncfusion Angular Component in Quick Start](#configure-syncfusion-angular-component-in-quick-start)
* [Render Syncfusion Angular Component](#render-syncfusion-angular-component)
* [Run the Application](#run-the-application)

## Clone the Quick Start

To getting started with webpack clone the quick start from [here](https://angular.io/guide/webpack)

## Dependencies installation

To install the dependencies, run the below command in cloned application's root directory.

{% highlight javascript %}
npm install
{% endhighlight %}

## Configure Syncfusion Angular Component in Quick Start

* Essential JavaScript provides support for Angular Framework through wrappers. Since, we need the dependencies [ej-angular2](https://www.npmjs.com/package/ej-angular2) package and [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) package.

* To configure the Syncfusion Angular Components into the cloned seed follow the below steps.

* Run the below commands, to install the above dependencies.


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

* And also include the typings `jquery` and `ej.web.all` in `src/tsconfig.json` file. 

{% highlight javascript %}

{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "moduleResolution": "node",
    "sourceMap": true,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "lib": [ "es2015", "dom" ],
    "noImplicitAny": true,
    "suppressImplicitAnyIndexErrors": true,
    "typeRoots": [
      "../node_modules/@types/"
    ],
     "types": [
      "jquery",
      "ej.web.all",
      "node"
    ]
  },
  "compileOnSave": true,
  "exclude": [
    "node_modules/*",
    "**/*-aot.ts"
  ]
}

{% endhighlight %}

N>If you get the typescript error `Cannot find name 'beforeEach, describe, it` in `app.component.specs.ts` file, then install the typings dependencies `@types/jasmine` in application. Run the below command to install the dependency.

{% highlight javascript %}
npm install --save-dev @types/jasmine
{% endhighlight %}

* And also include the dependency in `src/tsconfig.json` file.

{% highlight javascript %}

{
  "compilerOptions": {
    "target": "es5",
    . . .
    "typeRoots": [
      "../node_modules/@types/"
    ],
     "types": [
      "jquery",
      "ej.web.all",
      "node",
      "jasmine"
    ]
  },
  "compileOnSave": true,
  "exclude": [
    "node_modules/*",
    "**/*-aot.ts"
  ]
}

{% endhighlight %}

* Syncfusion JavaScript widgets need `window.jQuery` to render the Angular components, since, we need to import jQuery in `vendor.ts` file and include `Syncfusion theme files` from `node_modules` as like the below code snippet. 

{% highlight javascript %}

import * as $ from 'jquery';
window["jQuery"] = $;
window["$"] = $;
import 'jsrender';
import '../node_modules/syncfusion-javascript/Content/ej/web/material/ej.web.all.min.css';

{% endhighlight %}

N> To overcome the issue `$(..)['ej'+this.controlname] is not defined`, [alias](https://webpack.js.org/configuration/resolve/) is used to define `jQuery` in `webpack configuration(common)` file to refer the jQuery using `alias`.

{% highlight javascript %}
var webpack = require('webpack');
var HtmlWebpackPlugin = require('html-webpack-plugin');
var ExtractTextPlugin = require('extract-text-webpack-plugin');
var helpers = require('./helpers');

module.exports = {
  entry: {
    'polyfills': './src/polyfills.ts',
    'vendor': './src/vendor.ts',
    'app': './src/main.ts'
  },

  resolve: {
    extensions: ['.ts', '.js'],
    alias: {
        jquery: "jquery/src/jquery"
      }
  },
. . .
.  .  .
{% endhighlight %}

## Render Syncfusion Angular Component

* To render any Syncfusion Angular Components into the project, we need to import `EJAngular2Module` from `ej-angular2` package in `app.module.ts` file. Refer to the below code snippet to import Syncfusion Angular components.

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

* Now we can render any Angular component. Here, We rendered the `ejGrid` Angular component. Refer the below code snippet for `app.component.html` file.

{% highlight html %}

<main>
  <ej-grid [allowPaging]="true"  [dataSource]="gridData" [allowPaging]="true" [pageSettings.pageSize]="5">
    <e-columns>
        <e-column field="OrderID" headerText="Order ID" width="75" textAlign="right"></e-column>
        <e-column field="CustomerID" headerText="Customer ID" width="80"></e-column>
        <e-column field="EmployeeID" headerText="Employee ID" width="75" textAlign="right"></e-column>
        <e-column field="Freight" width="75" format="{0:C}" textAlign="right"></e-column>
        <e-column field="OrderDate" headerText="Order Date" width="80" format="{0:MM/dd/yyyy}" textAlign="right"></e-column>
    </e-columns>
</ej-grid>
</main>

{% endhighlight %}

* Modify the `app.component.ts` file using the below code example.

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent { 
   public gridData: any;
    constructor() {
        this.gridData = [{
            OrderID: 10248, CustomerID: 'VINET', EmployeeID: 5,
            OrderDate: new Date(8364186e5), Freight: 32.38
        },
        {
            OrderID: 10249, CustomerID: 'TOMSP', EmployeeID: 6,
            OrderDate: new Date(836505e6), Freight: 11.61
        },
        {
            OrderID: 10250, CustomerID: 'HANAR', EmployeeID: 4,
            OrderDate: new Date(8367642e5), Freight: 65.83
        },
        {
            OrderID: 10251, CustomerID: 'VICTE', EmployeeID: 3,
            OrderDate: new Date(8367642e5), Freight: 41.34
        },
        {
            OrderID: 10252, CustomerID: 'SUPRD', EmployeeID: 4,
            OrderDate: new Date(8368506e5), Freight: 51.3
        },
         {
            OrderID: 10251, CustomerID: 'BERGS', EmployeeID: 8,
            OrderDate:new Date(840006e6), Freight: 8.98
        },
         {
            OrderID: 10251, CustomerID: 'BLONP', EmployeeID: 2,
            OrderDate: new Date(838278e6), Freight: 55.28
        },
         {
            OrderID: 10251, CustomerID: 'BONAP', EmployeeID: 7,
            OrderDate: new Date(8738748e5), Freight: 113.15
        },
         {
            OrderID: 10251, CustomerID: 'BOTTM', EmployeeID: 4,
            OrderDate: new Date(8921916e5), Freight: 74.44
        },
         {
            OrderID: 10251, CustomerID: 'CACTU', EmployeeID: 3,
            OrderDate: new Date(88416e7), Freight: 19.76
        }];
    }
}
{% endhighlight %}

## Run the Application

* To run the application, execute below command in application's root folder.

N> If you get the following error, you need to refer the corresponding image type in `webpack.common.js` file. 

![](/angular/GettingStarted/Images/css loader.png)

* Refer the below code snippet to refer the image types.
{% highlight javascript %}
var webpack = require('webpack');
var HtmlWebpackPlugin = require('html-webpack-plugin');
var ExtractTextPlugin = require('extract-text-webpack-plugin');
var helpers = require('./helpers');

module.exports = {
  . . .
  . . .
  module: {
    rules: [
      {
        test: /\.ts$/,
        loaders: [
          {
            loader: 'awesome-typescript-loader',
            options: { configFileName: helpers.root('src', 'tsconfig.json') }
          } , 'angular2-template-loader'
        ]
      },
      {
        test: /\.html$/,
        loader: 'html-loader'
      },
      {
        test: /\.(png|jpe?g|gif|svg|woff|woff2|ttf|eot|ico|cur|ani)$/,
        loader: 'file-loader?name=assets/[name].[hash].[ext]'
      },
      {
        test: /\.css$/,
        exclude: helpers.root('src', 'app'),
        loader: ExtractTextPlugin.extract({ fallbackLoader: 'style-loader', loader: 'css-loader?sourceMap' })
      },
      {
        test: /\.css$/,
        include: helpers.root('src', 'app'),
        loader: 'raw-loader'
      }
    ]
  },


{% endhighlight %}

![](/angular/GettingStarted/Images/webpackoutput.png)


