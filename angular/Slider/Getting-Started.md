---
title: Getting Started for Angular Slider
description: Getting Started for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Getting Started

This section explains briefly about how to create a **Slider** control in your application with **Angular**.

## Create Slider in Angular Application using Web pack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Web pack starter](https://github.com/syncfusion/angular2-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add slider component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `slider` folder inside `src/app` folder.

* Create `slider.component.html` view file inside `src/app/slider` folder and render ejSlider Angular component using the below code example. 

{% highlight html %}
    <ej-slider width="100%" [value]="value"></ej-slider>
{% endhighlight %}

* Create `slider.component.ts` model file inside the folder `src/app/slider` and create slider sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './slider.component.html'
})
export class SliderComponent { 
    value: string;
    constructor() {
        this.value = '20';
    }
}
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejSlider component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created Slider sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
	<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#slider" 
    [routerLink]="['/slider']">Slider </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejSlider sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { SliderComponent } from './slider/slider.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'slider', component: SliderComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejSlider sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { SliderComponent } from './slider/slider.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), 
  RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , SliderComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Slider tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpg)

## Create Slider in Angular Application using SystemJS  

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

 > cd angular2-seeds

 > npm install
{% endhighlight %}

The below steps describes to add slider component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `slider` folder inside `src` folder.

* Create `slider.component.html` view file inside `src/slider` folder and render ejSlider Angular component using the below code example. 

{% highlight html %}
    <ej-slider width="100%" [value]="value"></ej-slider>
{% endhighlight %}

* Create `slider.component.ts` model file inside the folder `src/slider` and create slider sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './slider.component.html'
})
export class SliderComponent { 
    value: string;
    constructor() {
        this.value = '20';
    }
}
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejSlider component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created Slider sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
	<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#slider"
     [routerLink]="['/slider']">Slider </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejSlider sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { SliderComponent } from './slider/slider.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'slider', component: SliderComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejSlider sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngular2Module } from 'ej-angular2';
import { AppComponent } from './app.component';
import { SliderComponent } from './slider/slider.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngular2Module.forRoot(), 
  RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , SliderComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to Slider tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpg)

