---
layout: post
title: Getting started with Webpack
description: Overview of Syncfusion Essential Angular 2.
platform:  Angular-2
control: Introduction
documentation: ug
---


# Getting started with Webpack

To quick start with Syncfusion JavaScript Angular 2 components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}
 
The below steps describes to add component with above cloned seed application.

## Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular 2 source component(s) from the below build location and add it in `src/app/ej` folder (For ex., consider the `dialog` component).

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `dialog` folder inside `src/app` folder.

* Create `dialog.component.html` view file inside `src/app/dialog` folder and render ejDialog Angular 2 component using the below code example. 

{% highlight html %}
<div id="parent" >
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

* Create `dialog.component.ts` model file inside the folder `src/app/dialog` and create sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './dialog.component.html'
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

## Configure the routes for the Router

Before adding router configuration for above created ejDialog component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

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

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { DialogComponent } from './dialog/dialog.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'dialog', component: DialogComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejDialog sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_DIALOG_COMPONENTS } from './ej/dialog.component';
import { DialogComponent } from './dialog/dialog.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_DIALOG_COMPONENTS,DialogComponent],
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

![](/angular-2/GettingStarted/Images/getting-started-output.png) 
 
## Demos

We have implemented our [Angular 2 sample browser](http://ng2jq.syncfusion.com/) using Angular 2 Syncfusion Angular 2 components.



