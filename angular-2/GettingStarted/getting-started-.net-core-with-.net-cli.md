---
layout: post
title:  Angular SPA on ASP.NET Core with .NET CLI
description: Overview of Syncfusion Essential Angular 2
platform: Angular-2
control: Introduction
documentation: ug
---


# Getting Started with Angular SPA on ASP.NET Core with .NET CLI

ASP.NET Single Page Application(SPA) helps you to build applications that include significant client-side interactions using HTML 5, CSS 3 and Javascript.

To getting started with Syncfusion Angular Components, the NPM packges [ej-angular2](https://www.npmjs.com/package/ej-angular2) and [syncfusion-javascript](https://www.npmjs.com/package/syncfusion-javascript) helps to seamlessly supports ASP.NET Core environment for our components. The following steps depicts, to create an application in ASP.NET Core using SPA template with Syncfusion Angular Components.

## Create a new Application

* Create simple application using [.NET Web Development](https://blogs.msdn.microsoft.com/webdev/2017/02/14/building-single-page-applications-on-asp-net-core-with-javascriptservices/) and Tool and run the application to ensure the system environment is properly configured to work with Angular applications.

## Configuration of Syncfusion Angular Component

* To install Syncfusion JavaScript and Angular components run below commands from sample's root folder.

{% highlight javascript %}

npm install syncfusion-javascript --save
npm install ej-angular2 --save
npm install --save-dev @types/jquery
npm install --save-dev @types/ej.web.all

{% endhighlight %}

* Refer the below code snippet for Npm Configuration file.

{% highlight javascript %}

{
  "name": "ejapplication",
  "version": "0.0.0",
  "scripts": {
    "build": "webpack",
    "copy-ej": "xcopy node_modules\\syncfusion-javascript\\Content\\ej wwwroot\\dist\\ej /y /s /i",
    "postinstall": "npm run copy-ej",
    "test": "karma start ClientApp/test/karma.conf.js"
  },
  "dependencies": {
    . . .
    . . .
  },
  "devDependencies": {
    . . . 
  }
}

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

* Syncfusion JavaScript components need `jQuery` to render the control, so import jQuery in `ClientApp/boot-client.ts` file.

{% highlight ts %}

import 'angular2-universal-polyfills/browser';
import { enableProdMode } from '@angular/core';
import { platformUniversalDynamic } from 'angular2-universal';
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

![](/angular-2/GettingStarted/Images/windowerror.png)

* To overcome this issue, modify the code is referred as below and refer `ej-themes` from `dist` folder.

{% highlight javascript %}

@{
ViewData["Title"] = "Home Page";
}

<!--To overcome the issue "ReferenceError: window is not defined"-->
<app asp-ng2-prerender-module="ClientApp/dist/main-server">Loading...</app>
<!--ej theme reference-->
<link href="~/dist/ej/web/material/ej.web.all.min.css" rel="stylesheet" asp-append-version="true">

<script src="~/dist/vendor.js" asp-append-version="true"></script>
@section scripts {
<script src="~/dist/main-client.js" asp-append-version="true"></script>
}

{% endhighlight %}

* Import the `ejDialog` component in `home.component.html`

{% highlight html %}

<div id="parent" >
	<input *ngIf="btndisplay" id="btnOpen" style="height: 30px" type="button" ej-button class="ejinputtext" value="Click to open Dialog" (click)="onClick($event)"/>
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

import { Component, ViewChild, ElementRef } from '@angular/core';
import { EJComponents } from 'ej-angular2';

@Component({
    selector: 'home',
    templateUrl: './home.component.html'
})
export class HomeComponent {
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

* Now run the application with below command and navigate to [http://localhost:5000/](http://localhost:5000/) to see the output window.

{% highlight javascript %}

dotnet run

{% endhighlight %}

![](/angular-2/GettingStarted/Images/spatemplateoutput.png)