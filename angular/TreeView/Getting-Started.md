---
title: Getting Started for Angular TreeView
description: Getting Started for Angular TreeView
platform: Angular
control: TreeView
documentation: Ug
keywords: ejtreeview, js treeview, treeview
---

# Getting Started

This section explains briefly about how to create a **TreeView** control in your application with **Angular**.

## Create TreeView in Angular Application using Webpack

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [Webpack starter](https://github.com/syncfusion/Angular-seeds) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add treeview component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/app/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `treeview` folder inside `src/app` folder.

* Create `treeview.component.html` view file inside `src/app/treeview` folder and render ejTreeView Angular component using the below code example. 

{% highlight html %}
   <ej-treeview>
        <ul>
            <li id="1" class="expanded">
                Artwork
                <ul>
                    <li id="2">
                        Abstract
                        <ul>
                            <li id="3">2 Acrylic Mediums</li>
                            <li>Creative Acrylic</li>
                            <li>Modern Painting</li>
                            <li>Canvas Art</li>
                            <li>Black white</li>
                        </ul>
                    </li>
                    <li>
                        Children
                        <ul>
                            <li>Preschool Crafts</li>
                            <li>School-age Crafts</li>
                            <li>Fabulous Toddler</li>
                        </ul>
                    </li>
                    <li>
                        Comic / Cartoon
                        <ul>
                            <li>Batman</li>
                            <li>Adventures of Superman</li>
                            <li>Super boy</li>
                        </ul>
                    </li>
                </ul>
            </li>
            <li class="expanded">
                Books
                <ul>
                    <li>
                        Comics
                        <ul>
                            <li>The Flash</li>
                            <li>Human Target</li>
                            <li>Birds of Prey</li>
                        </ul>
                    </li>
                    <li>Entertaining</li>
                    <li>Design</li>
                </ul>
            </li>
            <li>
                Music
                <ul>
                    <li>
                        Classical
                        <ul>
                            <li>Avant-Garde</li>
                            <li>Medieval</li>
                            <li>Orchestral</li>
                        </ul>
                    </li>
                    <li>Mass</li>
                    <li>Folk</li>
                </ul>
            </li>
        </ul>
    </ej-treeview>
{% endhighlight %}

* Create `treeview.component.ts` model file inside the folder `src/app/treeview` and create treeview sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './treeview.component.html'
})
export class TreeViewComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejTreeView component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created TreeView sample in `src/app/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#treeview" [routerLink]="['/treeview']">TreeView </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejTreeView sample component and define the route in `src/app/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { TreeViewComponent } from './treeview/treeview.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'treeview', component: TreeViewComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejTreeView sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { TreeViewComponent } from './treeview/treeview.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , TreeViewComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to TreeView tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

N> if you want to use other port, open `package.json` file, then change port in `--port 3000` script and also change the port in `config/webpack.dev.js`.

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Create TreeView in Angular Application using SystemJS  

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/Angular-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/Angular-seeds/ -b systemjs

 > cd Angular-seeds

 > npm install
{% endhighlight %}

The below steps describes to add treeview component with above cloned seed application.

### Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder.

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\Angular\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `treeview` folder inside `src` folder.

* Create `treeview.component.html` view file inside `src/treeview` folder and render ejTreeView Angular component using the below code example. 

{% highlight html %}
    <ej-treeview>
        <ul>
            <li id="1" class="expanded">
                Artwork
                <ul>
                    <li id="2">
                        Abstract
                        <ul>
                            <li id="3">2 Acrylic Mediums</li>
                            <li>Creative Acrylic</li>
                            <li>Modern Painting</li>
                            <li>Canvas Art</li>
                            <li>Black white</li>
                        </ul>
                    </li>
                    <li>
                        Children
                        <ul>
                            <li>Preschool Crafts</li>
                            <li>School-age Crafts</li>
                            <li>Fabulous Toddler</li>
                        </ul>
                    </li>
                    <li>
                        Comic / Cartoon
                        <ul>
                            <li>Batman</li>
                            <li>Adventures of Superman</li>
                            <li>Super boy</li>
                        </ul>
                    </li>
                </ul>
            </li>
            <li class="expanded">
                Books
                <ul>
                    <li>
                        Comics
                        <ul>
                            <li>The Flash</li>
                            <li>Human Target</li>
                            <li>Birds of Prey</li>
                        </ul>
                    </li>
                    <li>Entertaining</li>
                    <li>Design</li>
                </ul>
            </li>
            <li>
                Music
                <ul>
                    <li>
                        Classical
                        <ul>
                            <li>Avant-Garde</li>
                            <li>Medieval</li>
                            <li>Orchestral</li>
                        </ul>
                    </li>
                    <li>Mass</li>
                    <li>Folk</li>
                </ul>
            </li>
        </ul>
    </ej-treeview>
{% endhighlight %}

* Create `treeview.component.ts` model file inside the folder `src/treeview` and create treeview sample component using the below code example.

{% highlight javascript %}
import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/treeview/treeview.component.html'
})
export class TreeViewComponent { }
{% endhighlight %}

### Configure the routes for the Router

Before adding router configuration for above created ejTreeView component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created TreeView sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#treeview" [routerLink]="['/treeview']">TreeView </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejTreeView sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { TreeViewComponent } from './treeview/treeview.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'treeview', component: TreeViewComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejTreeView sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJAngularModule } from 'ej-Angular';
import { AppComponent } from './app.component';
import { TreeViewComponent } from './treeview/treeview.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, EJAngularModule.forRoot(), RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , TreeViewComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to TreeView tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![](Getting-Started_images/Getting-Started_img1.jpeg)

