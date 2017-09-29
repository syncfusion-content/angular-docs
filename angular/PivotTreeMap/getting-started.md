---
title: Getting Started for Angular PivotTreeMap
description: How to create a PivotTreeMap with data source.
platform: Angular
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Getting Started

This section explains briefly about how to create a **PivotTreeMap** control in your application with **Angular**. This section covers only the minimal features that you need to know to get started with the PivotTreeMap.

## Getting started with SystemJS

To quick start with Syncfusion JavaScript Angular components run the below commands to clone the repository for [SystemJS starter](https://github.com/syncfusion/angular2-seeds/tree/systemjs) and installing required dependency packages.

{% highlight javascript %}
 > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs

 > cd angular2-seeds

 > npm install
{% endhighlight %}
 
The below steps describes to add component with above cloned seed application.

## Syncfusion JavaScript components source configuration and sample creation

* Copy required Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder (For ex., consider the `pivottreemap` component).

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v{{ site.releaseversion }}.

* Create `pivottreemap` folder inside `src` folder.

* Create `pivottreemap.component.html` view file inside `src/pivottreemap` folder and render ejPivotTreeMap Angular component using the below code example. 

{% highlight html %}

<ej-pivottreemap id="PivotTreeMap1" ></ej-pivottreemap>

{% endhighlight %}

* Create `pivottreemap.component.ts` model file inside the folder `src/pivottreemap` and create sample component using the below code example.

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/pivottreemap/pivottreemap.component.html',
  styleUrls: ['app/components/pivottreemap/pivottreemap.component.css'], 
})

export class PivotTreeMapComponent {
    //..
}

{% endhighlight %}

## Configure the routes for the Router

Before adding router configuration for above created ejPivotTreeMap component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created PivotTreeMap sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		. . . .
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#pivottreemap" [routerLink]="['/pivottreemap']">PivotTreeMap </a></li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejPivotTreeMap sample component and define the route in `src/app.routes.ts` file.

{% highlight javascript %}
import { Routes } from '@angular/router';
. . . . 
import { PivotTreeMapComponent } from './pivottreemap/pivottreemap.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'pivottreemap', component: PivotTreeMapComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejPivotTreeMap sample component into `app.module.ts` like the below code snippet.

{% highlight javascript %}

import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_PIVOTTREEMAP_COMPONENTS } from './ej/pivottreemap.component';
import { PivotTreeMapComponent } from './pivottreemap/pivottreemap.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_PIVOTTREEMAP_COMPONENTS,PivotTreeMapComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Control Initialization

Add necessary HTML elements in `pivottreemap.component.html` to render PivotTreeMap

{% highlight html %}

<ej-pivottreemap id="PivotTreeMap1" dataSource.data="http://bi.syncfusion.com/olap/msmdpump.dll" dataSource.catalog="Adventure Works DW 2008 SE" dataSource.cube="Adventure Works" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values" [dataSource.filters]="filters">
</ej-pivottreemap>

{% endhighlight %}

Create a **CSS** page and add necessary CSS elements for PivotTreeMap

{% highlight CSS %}

    .e-pivottreemap {
        min-height: 275px; 
        display: block;
        min-width: 525px; 
        height: 460px !important; 
        width: 99%
    }

{% endhighlight %}

### Populate PivotTreeMap with data

Let us now see how to populate the PivotTreeMap control using a sample data as shown below.

{% tabs %}

{% highlight html %}

<ej-pivottreemap id="PivotTreeMap1" dataSource.data="http://bi.syncfusion.com/olap/msmdpump.dll" dataSource.catalog="Adventure Works DW 2008 SE" dataSource.cube="Adventure Works" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values" [dataSource.filters]="filters" (renderSuccess)="renderSuccess($event)">
</ej-pivottreemap>

{% endhighlight %}

{% highlight ts %}
    //..
    export class PivotTreeMapComponent {
        public rows; columns; values; filters;
        constructor() {
          this.rows = [{ fieldName: "[Date].[Fiscal]" }];
          this.columns = [{ fieldName: "[Customer].[Customer Geography]" }];
          this.values = [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]", }], axis: "columns" }];
          this.filters = [];
        }
        renderSuccess(args){
         let treemapTarget = $('#PivotTreeMap1TreeMapContainer').data('ejTreeMap');
         treemapTarget.model.tooltipTemplate = null;
         treemapTarget.model.showTooltip = false;
         treemapTarget.refresh();
        }
    }

{% endhighlight %}

{% endtabs %}

The above code will generate a simple PivotTreeMap with internet sales amount over a period of fiscal years across different customer geographic locations.

![](getting-started_images/Olap.png)