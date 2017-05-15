---
layout: post
title:  Getting Started with Angular CLI
description: Overview of Syncfusion Essential Angular 2
platform: Angular-2
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

* Install the latest version of Angular CLI
* Create new project
* Configuration of Syncfusion Angular components
	* app.component.ts
	* app.module.ts
	* main.ts
	* package.json
	* tsconfig.json
	* angular-cli.json
* Render Syncfusion Angular Components
* Serve the application

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

* Syncfusion JavaScript widgets need `window.jQuery` to render the Angular components, since, we need to import jQuery in `polyfills.ts` file as like the below code snippet.

{% highlight javascript %}

import * as jquery from 'jquery';
window['jQuery'] = jquery;
window['$'] = jquery;

{% endhighlight %}

## Render Syncfusion Angular Component

* To render `ejDialog` Angular component in angular-cli, modify the `app.component.html` file using the below code example.

{% highlight html %}
<div id="parent">
	<input id="btnOpen" style="display:none; height: 30px" type="button" class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)" />
	<ej-dialog id="basicDialog" title="Facebook" [(enableResize)]="resize" containment="#parent" (close)="onClose($event)">
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
 
 import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/dialog/dialog.component.html'
})
export class DialogComponent {
  resize: boolean;
  constructor() {
    this.resize = false;
  }
  onClick(event) {
    $('#btnOpen').hide();
    $('#basicDialog').ejDialog('open');
  }
  onClose(event) {
    $('#btnOpen').show();
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

## Serve the Application

Now, navigate to the root of the application and run the application using the below command and navigate to the appropriate port [http://localhost:4200](localhost:4200) in browser

{% highlight javascript %}

ng serve

{% endhighlight %}

![](/angular-2/GettingStarted/Images/angularcli.png) 