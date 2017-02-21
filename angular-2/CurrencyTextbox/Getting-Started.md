---
title: Getting Started for Angular2 CurrencyTextbox
description: Getting Started for Angular 2 CurrencyTextbox
platform: Angular2
control: CurrencyTextbox
documentation: Ug
keywords: ejcurrencytextbox, js currencytextbox, currencytextbox
---

# Getting Started

This section explains briefly about how to create a **CurrencyTextbox** control in your application with **Angular2**.

## Create CurrencyTextbox in Angular2 Application using Webpack

To quick start with Syncfusion JavaScript Angular 2 components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add currencytextbox component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular 2 source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `currencytextbox` folder inside `src/app` folder.

* Create `currencytextbox.component.html` view file inside `src/app/currencytextbox` folder and render ejCurrencyTextbox Angular 2 component using the below code example. 

{% highlight html %}
    <input id="currency" type="text" ej-currencytextbox value="10" width="250px" />
{% endhighlight %}

* Create `currencytextbox.component.ts` model file inside the folder `src/app/currencytextbox` and create currencytextbox sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './currencytextbox.component.html'
})
export class CurrencyTextboxComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejCurrencyTextbox component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

* Now, we are going to configure the route navigation link for created CurrencyTextbox sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#currencytextbox" [routerLink]="['/currencytextbox']">CurrencyTextbox </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejCurrencyTextbox sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { CurrencyTextboxComponent } from './currencytextbox/currencytextbox.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'currencytextbox', component: CurrencyTextboxComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejCurrencyTextbox sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { CurrencyTextboxComponent } from './currencytextbox/currencytextbox.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , CurrencyTextboxComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to CurrencyTextbox tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Create CurrencyTextbox in Angular2 Application using SystemJS  

To quick start with Syncfusion JavaScript Angular 2 components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add currencytextbox component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular 2 source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `currencytextbox` folder inside `src` folder.

* Create `currencytextbox.component.html` view file inside `src/currencytextbox` folder and render ejCurrencyTextbox Angular 2 component using the below code example. 

{% highlight html %}
    <input id="currency" type="text" ej-currencytextbox value="10" width="250px" />
{% endhighlight %}

* Create `currencytextbox.component.ts` model file inside the folder `src/currencytextbox` and create currencytextbox sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/currencytextbox/currencytextbox.component.html'
})
export class CurrencyTextboxComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejCurrencyTextbox component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

* Now, we are going to configure the route navigation link for created CurrencyTextbox sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#currencytextbox" [routerLink]="['/currencytextbox']">CurrencyTextbox </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejCurrencyTextbox sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { CurrencyTextboxComponent } from './currencytextbox/currencytextbox.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'currencytextbox', component: CurrencyTextboxComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejCurrencyTextbox sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { CurrencyTextboxComponent } from './currencytextbox/currencytextbox.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , CurrencyTextboxComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to CurrencyTextbox tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpeg)

