---
title: Getting Started for Angular2 Scroller
description: Getting Started for Angular 2 Scroller
platform: Angular
control: Scroller
documentation: Ug
keywords: ejScroller, js Scroller, Scroller
---

# Getting Started

This section explains briefly about how to create a **Scroller** control in your application with **Angular 2**.

## Create Scroller in Angular 2 Application using Webpack

To quick start with Syncfusion JavaScript Angular 2 components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}

 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install

{% endhighlight %}

The below steps describes to add Scroller component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular 2 source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}

(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 

{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.



* Create `scroller` folder inside `src/app` folder.

* Create `scroller.component.html` view file inside `src/app/scroller` folder and render ejScroller Angular 2 component using the below code example. 

{% highlight html %}
    <ej-scroller height="300" width="460px" style="display:block;border:1px solid #bbbcbb">
    <div>
        <div class="sampleContent" style="width:700px;padding:10px">
            Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the
            user's interaction with it. The model consists of application data, business rules, logic, and functions. A view
            can be any output representation of data, such as a chart or a diagram. Multiple views of the same data are possible,
            such as a bar chart for management and a tabular view for accountants. The controller mediates input, converting
            it to commands for the model or view.The central ideas behind MVC are code reusability and n addition to dividing
            the application into three kinds of components, the MVC design defines the interactions between them.
            <ul>
                <li>
                    <b>A controller </b>can send commands to its associated view to change the view's presentation of the
                    model (e.g., by scrolling through a document). It can also send commands to the model to update the model's
                    state (e.g., editing a document).
                </li>
                <li>
                    <b>A model</b> notifies its associated views and controllers when there has been a change in its state.
                    This notification allows the views to produce updated output, and the controllers to change the available
                    set of commands. A passive implementation of MVC omits these notifications, because the application does
                    not require them or the software platform does not support them.
                </li>
                <li>
                    <b>A view</b> requests from the model the information that it needs to generate an output representation
                    to the user.
                </li>
            </ul>
        </div>
    </div>
</ej-scroller>
{% endhighlight %}

* Create `scroller.component.ts` model file inside the folder `src/app/scroller` and create scroller sample component using the below code example.

{% highlight javascript %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './scroller.component.html'
})
export class DefaultComponent {
  constructor() { }
}

{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejScroller component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

* Now, we are going to configure the route navigation link for created Scroller sample in `src/app/app.component.html` file.

{% highlight html %}

<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#scroller" [routerLink]="['/scroller']">Scroller</a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>

{% endhighlight %}

* Import the ejScroller sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { ScrollerComponent } from './scroller/scroller.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'scroller', component: ScrollerComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejScroller sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_SCROLLER_COMPONENTS } from './ej/scroller.component';
import { ScrollerComponent } from './scroller/scroller.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_SCROLLER_COMPONENTS,ScrollerComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}

npm start

{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Scroller tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting_Started_images/Getting-Started_img1.png)

## Create Scroller in Angular 2 Application using SystemJS  

To quick start with Syncfusion JavaScript Angular 2 components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}

 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

 > cd angular2-seeds

 > npm install

{% endhighlight %}

The below steps describes to add Scroller component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular 2 source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}

(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 

{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular 2 components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `scroller` folder inside `src` folder.

* Create `scroller.component.html` view file inside `src/scroller` folder and render ejScroller Angular 2 component using the below code example. 

{% highlight html %}

<ej-scroller height="300" width="460px" style="display:block;border:1px solid #bbbcbb">
    <div>
        <div class="sampleContent" style="width:700px;padding:10px">
            Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the
            user's interaction with it. The model consists of application data, business rules, logic, and functions. A view
            can be any output representation of data, such as a chart or a diagram. Multiple views of the same data are possible,
            such as a bar chart for management and a tabular view for accountants. The controller mediates input, converting
            it to commands for the model or view.The central ideas behind MVC are code reusability and n addition to dividing
            the application into three kinds of components, the MVC design defines the interactions between them.
            <ul>
                <li>
                    <b>A controller </b>can send commands to its associated view to change the view's presentation of the
                    model (e.g., by scrolling through a document). It can also send commands to the model to update the model's
                    state (e.g., editing a document).
                </li>
                <li>
                    <b>A model</b> notifies its associated views and controllers when there has been a change in its state.
                    This notification allows the views to produce updated output, and the controllers to change the available
                    set of commands. A passive implementation of MVC omits these notifications, because the application does
                    not require them or the software platform does not support them.
                </li>
                <li>
                    <b>A view</b> requests from the model the information that it needs to generate an output representation
                    to the user.
                </li>
            </ul>
        </div>
    </div>
</ej-scroller>

{% endhighlight %}

* Create `scroller.component.ts` model file inside the folder `src/scroller` and create scroller sample component using the below code example.

{% highlight javascript %}
import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './scroller.component.html'
})
export class DefaultComponent {
  constructor() { }
}
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejScroller component, we recommend you to go through the [Angular 2 Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular 2 routing. 

* Now, we are going to configure the route navigation link for created Scroller sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#scroller" [routerLink]="['/scroller']">Scroller </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejScroller sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { ScrollerComponent } from './scroller/scroller.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'scroller', component: ScrollerComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejScroller sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_SCROLLER_COMPONENTS } from './ej/scroller.component';
import { ScrollerComponent } from './scroller/scroller.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_SCROLLER_COMPONENTS,ScrollerComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}

npm start

{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Scroller tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting_Started_images/Getting-Started_img1.png)

