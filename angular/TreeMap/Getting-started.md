---
title: Getting Started with Angular TreeMap Control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Angular TreeMap Control, its elements, and more.
platform: Angular
control: treemap
documentation: ug
keywords: ejtreemap, treemap, treemap widget, Angular treemap
---
# Getting Started with Angular TreeMap

Before we start with the TreeMap, please refer [this page](https://help.syncfusion.com/angular-2/overview) for general information regarding integrating Syncfusion widget’s.

## Adding JavaScript and CSS Reference

To render the TreeMap control, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [Angular](https://angular.io/) - Angular latest versions

The other required internal dependencies are tabulated below,

<table>
   <tr>
      <th>
         <b>Files</b>
      </th>
      <th>
         <b>Description/Usage </b>
      </th>
   </tr>
   <tr>
      <td>
         ej.core.min.js
      </td>
      <td>
        It is referred always before using all the JS controls.
      </td>
   </tr>
   <tr>
      <td>
         ej.data.min.js
      </td>
      <td>
         Used to handle data operation and is used while binding data to the JS controls.
      </td>
   </tr>
   <tr>
      <td>
        ej.treemap.min.js
      </td>
      <td>
        TreeMap core script file which includes TreeMap related scripts files.
      </td>
   </tr>
</table>

N> TreeMap uses one or more script files, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the TreeMap, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Preparing HTML document

Create an HTML page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

    <html>
    <head>
    <title>Angular TreeMap</title>

    <!-- Essential Studio for JavaScript  theme reference -->
    <link rel="stylesheet" href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" />

    <!-- Angular related script references -->
    <!-- 1. Load libraries -->
         <!-- Polyfill(s) for older browsers -->
    <script src="node_modules/core-js/client/shim.min.js"></script>   
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>

    <!-- Essential Studio for JavaScript  script references -->
    <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script> 
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    
    <!-- 2. Configure SystemJS -->
    <script src="systemjs.config.js"></script>
    <script>       
      System.import('app')
            .then(null, console.error.bind(console));
    </script>

    </head>
    <!-- 3. Display the application -->
    <body>
    <ej-app>  
		    <div class="splash">
			      <div class="message">Angular Syncfusion Components App</div>
			      <div class="spinner"></div>
		    </div>
	  </ej-app>
    </body>
    </html>

{% endhighlight %}

N> Uncompressed version of library files are also available which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).

## Control Initialization

* Copy TreeMap Syncfusion Angular source component(s) from the below build location and add it in `src/ej` folder (For ex., consider the `treemap` component).

{% highlight javascript %}
(Installed Location)\Syncfusion\Essential Studio\14.3.0.49\JavaScript\assets-src\angular2\ 
{% endhighlight %}

N> `core.ts` file is mandatory for all Syncfusion JavaScript Angular components. The repository having the source file from Essential Studio for JavaScript v14.3.0.49.

* Create `treemap` folder inside `src` folder.

* Create `treemap.component.html` view file inside `src/treemap` folder and render ejTreeMap Angular component using the below code example. 

{% highlight html %}
<ej-treemap id="defaulttreemap">
</ej-treemap>
{% endhighlight %}

* Create `treemap.component.ts` model file inside the folder `src/treemap` and create sample component using the below code example.

{% highlight ts %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/treemap/treemap.component.html'
})
export class TreeMapComponent {

}
{% endhighlight %}

## Configure the routes for the Router

Before adding router configuration for above created ejTreeMap component, we recommend you to go through the [Angular Routing](https://angular.io/docs/ts/latest/guide/router.html) configuration to get the deeper knowledge about Angular routing. 

* Now, we are going to configure the route navigation link for created treemap sample in `src/app.component.html` file.

{% highlight html %}
<div>
	<ul class="nav navbar-nav">
		<li>
           <a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" 
           href="#treemap" [routerLink]="['/treemap']">treemap </a>
        </li>
	</ul>
</div>
<main>
	<router-outlet></router-outlet>
</main>
{% endhighlight %}

* Import the ejTreeMap sample component and define the route in `src/app.routes.ts` file.

{% highlight ts %}
import { Routes } from '@angular/router';
. . . . 
import { TreeMapComponent } from './treemap/treemap.component';

export const rootRouterConfig: Routes = [
    { path: '', redirectTo: 'home', pathMatch: 'full' },
    . . . . 
    { path: 'treemap', component: TreeMapComponent }
];
{% endhighlight %}

* Import and declare the Syncfusion source component and ejTreemap sample component into `app.module.ts` like the below code snippet.

{% highlight ts %}
import { NgModule, enableProdMode, ErrorHandler } from '@angular/core';
. . . . . 
import { EJ_TREEMAP_COMPONENTS } from './ej/treemap.component';
import { TreeMapComponent } from './treemap/treemap.component';

import { rootRouterConfig } from './app.routes';
. . . . 
@NgModule({
  imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
  declarations: [. . . . , EJ_TREEMAP_COMPONENTS, TreeMapComponent],
  bootstrap: [AppComponent]
})
export class AppModule { }
{% endhighlight %}

### Populate DataSource

The `dataSource` property accepts the collection values as input. For example, you can provide the list of objects as input.

### Weight Value Path

You can calculate the size of the object using `weightValuePath` of **TreeMap**.

Add a **&lt;script&gt;** tag anywhere in a web page and initialize **TreeMap** as illustrated in the following code sample. 

{% highlight html %}

<div style="height:400px;width:600px;">
	<ej-treemap id="treemap" [dataSource]="dataSource" weightValuePath="Population">
	</ej-treemap>
</div>

{% endhighlight %}

{% highlight ts%}
import { Component, ViewEncapsulation} from '@angular/core';
import { DataService} from '../service/data.service';

@Component({
selector:"ej-app",
templateUrl:"src/treemap/treemap.component.html",
providers:[DataService]
})
export class TreemapComponent{
dataSource: any;
  constructor(dataService:DataService) {
    this.dataSource=dataService.treemapData();
  }
}
{% endhighlight %}
Populate the TreeMap data in JSON object. For example, you can use population data of countries to generate TreeMap data as illustrated in the following code sample.
Create a folder service and add file data.service.ts for serving data to  chart component file. Refer the below code snippet.

{% highlight ts %}
export class DataService{
// DataService file containing treemap data in treemapData method
    treemapData():Array<any>{
        return[
            { Continent: "Asia", Region: "Southern Asia", Growth: 1.32, Population: 1749046000 },
            { Continent: "Asia", Region: "Eastern Asia", Growth: 0.57, Population: 1620807000 },
            { Continent: "Asia", Region: "South-Eastern Asia", Growth: 1.20, Population: 618793000 },
            { Continent: "Asia", Region: "Western Asia", Growth: 1.98, Population: 245707000 },
            { Continent: "Asia", Region: "Central Asia", Growth: 1.43, Population: 64370000 },
            { Continent: "Europe", Region: "Europe", Growth: 0.10, Population: 742452000 },
            { Continent: "America", Region: "South America", Growth: 1.06, Population: 406740000 },
            { Continent: "America", Region: "Northern America", Growth: 0.85, Population: 355361000 },
            { Continent: "America", Region: "Central America", Growth: 1.40, Population: 167387000 },
            { Continent: "Africa", Region: "Eastern Africa", Growth: 2.89, Population: 373202000 },
            { Continent: "Africa", Region: "Western Africa", Growth: 2.78, Population: 331255000 },
            { Continent: "Africa", Region: "Northern Africa", Growth: 1.70, Population: 210002000 },
            { Continent: "Africa", Region: "Middle Africa", Growth: 2.79, Population: 135750000 },
            { Continent: "Africa", Region: "Southern Africa", Growth: 0.91, Population: 60425000 }
        ];
    }


{% endhighlight %}



N> Population data is referred from [List of continents by population](http://en.wikipedia.org/wiki/List_of_continents_by_population).


## Running the application

* To run the application, execute below command.

{% highlight javascript %}
npm start
{% endhighlight %}

* Browse to [http://localhost:3000](http://localhost:3000) to see the application. And navigate to treemap tab. The component is rendered as like the below screenshot. You can make changes in the code found under src folder and the browser should auto-refresh itself while you save files. 

![Angular TreeMap group with level](Getting-started-images/Getting-Started_img1.png) 

## Group with Levels

You can group TreeMap items using the levels in it.

### Group Path

You can use `groupPath` property for every flat level of the TreeMap control. It is a path to a field on the source object that serves as the “Group” for the level specified. You can group the data based on the `groupPath` in the TreeMap control. When the `groupPath` is not specified, then the items are not grouped and the data is displayed in the order specified in the `dataSource`.

### Group Gap

You can use `groupGap` property to separate the items from every flat level and to differentiate the levels mentioned in the TreeMap control.

The following code sample explains how to group TreeMap Items using ‘Levels’.

{% highlight html %}

<ej-treemap id="treemap" [dataSource]="dataSource" weightValuePath="Population">
   <e-levels>
	  <e-level groupPath="Continent" groupGap="5"></e-level>
   </e-levels>
</ej-treemap>

{% endhighlight %}



The following screenshot displays grouping of **TreeMap****Items** using **Levels**.

![Angular TreeMap customize by range](Getting-started-images/Getting-Started_img2.png)

## Customize TreeMap by Range

You can differentiate the nodes based on its value and color ranges using Range color. You can also define the color value range using from and to properties. 

### Color Value Path

The `colorValuePath` of TreeMap is a path to a field on the source object. You can determine the color for the object using `colorValuePath` of TreeMap.

The following code sample explains how to customize TreeMap appearance using Range.

{% highlight html %}

<div style="height:300px;width:500px;margin:0px auto;">
<ej-treemap id="treemap" [dataSource]="dataSource" weightValuePath="Population"
                                                      colorValuePath="Growth">
	<e-levels>
	   <e-level groupPath="Continent" groupGap="5"></e-level>
	</e-levels>
	<e-rangecolormapping>
       <e-rangecolor [from]="0" [to]="1" color="#DC562D"></e-rangecolor>
       <e-rangecolor [from]="1" [to]="1.5" color="#FED124"></e-rangecolor>
       <e-rangecolor [from]="1.5" [to]="2" color="#487FC1"></e-rangecolor>
       <e-rangecolor [from]="2" [to]="3" color="#0E9F49"></e-rangecolor>
	</e-rangecolormapping>
</ej-treemap>
</div>

{% endhighlight %}



The following screenshot displays a customized **TreeMap** control. 

![Angular TreeMap color with path](Getting-started-images/Getting-Started_img3.png)

## Enable Tooltip

You can enable the tooltip by setting `showTooltip` property to “true”. By default, it takes the property of the bound object that is referred in the `weightValuePath` and displays its content when the corresponding node is hovered. You can customize the template for tooltip using `tooltipTemplate` property.

Add the template script to index.html file for treemap tooltip template , refer the below code snippet for tooltipTemplate

{% highlight html %}
<script  id="template" type="application/jsrender">
        <div  style="margin-left:17px;margin-top:-45px;">      
            <div style="height:auto;width:auto;background:black;border-radius:3px;opacity:1">
                <div style="margin-top:-20px;margin-left:9px;padding-top:3px;margin-right:9px;">
                    <label style="margin-top:-20px;font-weight:normal;font-size:12px;color:white;font-family:Segoe UI;">'{{:Region}}'</label>
                </div>
               <div style="height:10px;"></div>
                <div style="margin-top:-10px;margin-left:9px;margin-right:9px;padding-bottom:3px;">
                    <label style="margin-top:-10px;font-weight:normal;font-size:14px;color:white;font-family:segoe ui light;">'{{:Population}}'</label>
                </div>
            </div>
        </div>            
</script>
{% endhighlight %}

{% highlight html %}
<div style="height:300px;width:500px;margin:0px auto;">
	<ej-treemap id="treemap" [showTooltip]="true" tooltipTemplate="template">
	</ej-treemap>
</div>
{% endhighlight %}
## Leaf ItemSettings

You can customize the Leaf level TreeMap items using `leafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `labelPath` when defined. The following code sample displays how the tooltip is enabled.

{% highlight html %}

<div style="height:300px;width:500px;margin:0px auto;">
	<ej-treemap id="treemap" leafItemSettings.labelPath="Region">
	</ej-treemap>
</div>

{% endhighlight %}



The following screenshot displays a ToolTip in a **TreeMap** control.

![Angular TreeMap enable tooltip](Getting-started-images/Getting-Started_img5.png)

## Enable Legend

You can set the color value of leaf nodes using TreeMap Legend. This legend is appropriate only for the TreeMap whose leaf nodes are colored using `rangeColorMapping`. You can set `showLegend` property value to “true” to make a legend visible.

### Label for Legend

You can customize the labels of the legend item using `legendLabel` property of `rangeColorMapping`. 

The following code sample illustrates how to add labels for legend in a TreeMap.

{% highlight html %}

<div style="height:300px;width:500px;margin:0px auto;">

<ej-treemap id="treemap" [showLegend]="true" [legendSettings.height]="38" 
                                            [legendSettings.width]="690">
	<e-rangecolormapping>
       <e-rangecolor legendLabel="0 - 1 %    Growth"> </e-rangecolor>
            <e-rangecolor legendLabel="1 - 1.5 %  Growth"></e-rangecolor>
            <e-rangecolor legendLabel="1.5 - 2 %  Growth"></e-rangecolor>
           	<e-rangecolor legendLabel="2 - 3 %  Growth"></e-rangecolor>
		</e-rangecolormapping>
</ej-treemap>

</div>

{% endhighlight %}



The following screenshot displays labels in a **TreeMap** control. 

![Angular TreeMap Label for Legend](Getting-started-images/Getting-Started_img6.png)

N> Population data is referred from [List of continents by population](http://en.wikipedia.org/wiki/List_of_continents_by_population).




