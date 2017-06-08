---
title: Getting Started for Angular MaskEdit
description: Getting Started for Angular MaskEdit
platform: Angular
control: MaskEdit
documentation: Ug
keywords: ejmaskedit, js maskedit, maskedit
---

# Getting Started

This section explains briefly about how to create a **MaskEdit** control in your application with **Angular**.

## Create MaskEdit in Angular Application using Webpack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/Angular-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add maskedit component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `maskedit` folder inside `src/app` folder.

* Create `maskedit.component.html` view file inside `src/app/maskedit` folder and render ejMaskEdit Angular component using the below code example. 

{% highlight html %}
    <input id="maskedit" ej-maskedit value="4242422424" inputMode="ej.InputMode.Text" maskFormat='99 999-99999' width="100%" />
{% endhighlight %}

* Create `maskedit.component.ts` model file inside the folder `src/app/maskedit` and create maskedit sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './maskedit.component.html'
})
export class MaskEditComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejMaskEdit component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created MaskEdit sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#maskedit" [routerLink]="['/maskedit']">MaskEdit </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejMaskEdit sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { MaskEditComponent } from './maskedit/maskedit.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'maskedit', component: MaskEditComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejMaskEdit sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { MaskEditComponent } from './maskedit/maskedit.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , MaskEditComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to MaskEdit tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Create MaskEdit in Angular Application using SystemJS  

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/Angular-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds/ -b systemjs

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add maskedit component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `maskedit` folder inside `src` folder.

* Create `maskedit.component.html` view file inside `src/maskedit` folder and render ejMaskEdit Angular component using the below code example. 

{% highlight html %}
     <input id="maskedit" ej-maskedit value="4242422424" inputMode="ej.InputMode.Text" maskFormat='99 999-99999' width="100%" />
{% endhighlight %}

* Create `maskedit.component.ts` model file inside the folder `src/maskedit` and create maskedit sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskedit/maskedit.component.html'
})
export class MaskEditComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejMaskEdit component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created MaskEdit sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#maskedit" [routerLink]="['/maskedit']">MaskEdit </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejMaskEdit sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { MaskEditComponent } from './maskedit/maskedit.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'maskedit', component: MaskEditComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejMaskEdit sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { MaskEditComponent } from './maskedit/maskedit.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , MaskEditComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to MaskEdit tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpeg)

