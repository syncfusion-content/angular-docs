---
title: Getting Started for Angular NumericTextbox
description: Getting Started for Angular NumericTextbox
platform: Angular
control: NumericTextbox
documentation: Ug
keywords: ejnumerictextbox, js numerictextbox, numerictextbox
---

# Getting Started

This section explains briefly about how to create a **NumericTextbox** control in your application with **Angular**.

## Create NumericTextbox in Angular Application using Webpack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/Angular-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add numerictextbox component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `numerictextbox` folder inside `src/app` folder.

* Create `numerictextbox.component.html` view file inside `src/app/numerictextbox` folder and render ejNumericTextbox Angular component using the below code example. 

{% highlight html %}
    <input id="numeric" type="text" ej-numerictextbox value="40" width="250px" />
{% endhighlight %}

* Create `numerictextbox.component.ts` model file inside the folder `src/app/numerictextbox` and create numerictextbox sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './numerictextbox.component.html'
})
export class NumericTextboxComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejNumericTextbox component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created NumericTextbox sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#numerictextbox" [routerLink]="['/numerictextbox']">NumericTextbox </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejNumericTextbox sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { NumericTextboxComponent } from './numerictextbox/numerictextbox.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'numerictextbox', component: NumericTextboxComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejNumericTextbox sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { NumericTextboxComponent } from './numerictextbox/numerictextbox.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , NumericTextboxComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to NumericTextbox tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Create NumericTextbox in Angular Application using SystemJS  

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/Angular-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds/ -b systemjs

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add numerictextbox component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `numerictextbox` folder inside `src` folder.

* Create `numerictextbox.component.html` view file inside `src/numerictextbox` folder and render ejNumericTextbox Angular component using the below code example. 

{% highlight html %}
    <input id="numeric" type="text" ej-numerictextbox value="40" width="250px" />
{% endhighlight %}

* Create `numerictextbox.component.ts` model file inside the folder `src/numerictextbox` and create numerictextbox sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/numerictextbox/numerictextbox.component.html'
})
export class NumericTextboxComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejNumericTextbox component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created NumericTextbox sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#numerictextbox" [routerLink]="['/numerictextbox']">NumericTextbox </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejNumericTextbox sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { NumericTextboxComponent } from './numerictextbox/numerictextbox.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'numerictextbox', component: NumericTextboxComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejNumericTextbox sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { NumericTextboxComponent } from './numerictextbox/numerictextbox.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , NumericTextboxComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to NumericTextbox tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpeg)

