---
layout: post
title: Getting Started for Angular-2 Grid | Syncfusion 
description: Learn here how to create the Grid, data bind, enable paging, grouping, filtering and add summaries in Syncfusion 
platform: Angular
control: Grid
documentation: ug
keywords: ejGrid, Grid, Grid widget
api: /api/Angular/grid
---

# Getting Started for Angular-2 Grid

To get start with how to use the Grid component within Angular-2 platform, please refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular/gettingstarted/getting-started-systemjs).By following the above steps in the document, you can get the newly cloned **angular2-seeds** template sample folder.Grid control has been already configured in that **angular2-seeds** folder. So that you can use already existing Grid sample available in **src/grid** folder.


## Copying Grid source file

In that newly cloned **angular2-seeds** folder,we have referred `grid.component.ts` source file from 14.3 version.If you want the upgraded version  of `grid.component.ts` source file, you can get it from the below mentioned location and add it under the **src/ej** folder. 

* (**Installed location**)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\

N> `core.ts` source file is mandatory for all Syncfusion JavaScript Angular components. 


##  External and Internal Dependencies

If you want to know about the external and internal dependencies of the Grid control, please refer here [here](https://help.syncfusion.com/js/grid/getting-started)


## Data Binding

[`Data binding`](https://help.syncfusion.com/angular/grid/data-binding) in the grid is achieved by assigning an array of JavaScript objects to the [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource) property. Refer to the following code example.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" width="75" textAlign="right"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID" width="75" textAlign="left"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}" textAlign="right"></e-column>
        <e-column field="OrderDate" headerText="OrderDate" width="80" format="{0:MM/dd/yyyy}" textAlign="right"></e-column>
        <e-column field="ShipCity" headerText="ShipCity" width="110"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
   
    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
        }
     }

{% endhighlight %}

![Data Binding in Angular Grid](Getting-started_images/Getting-started2_img1.jpeg)
{:.image }

N> 1.In the above code snippet, `ej-grid` denotes the control directive for the Syncfusion's Grid Angular widget and all its properties can be initialized with the exact casing of original property names also binded within square bracket(`[]`).(For example, [dataSource]).
N> 2.Events can be bound to the control using the event name within bracket [`()`].  For example, the [`actionBegin`](https://help.syncfusion.com/api/angular/ejgrid#events:actionbegin) event of Grid control can be defined as follows.
     
 {% highlight html %}

   <ej-grid id="Grid" [dataSource]="gridData"  (actionBegin)= actionBegin($event)>

 {% endhighlight %}


## Enable Paging

[`Paging`](https://help.syncfusion.com/angular/grid/paging) can be enabled by setting the [`allowPaging`](https://help.syncfusion.com/api/angular/ejgrid#members:allowpaging) to true. The Paging feature in�Grid�offers complete navigation support to easily switch between the pages, using the page bar available at the bottom of the Grid control

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true"  >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = window.gridData;
         }
     }

{% endhighlight %}

![Angular Grid Enable Paging](Getting-started_images/Getting-started2_img2.png)
{:.image }

N> Pager settings can be customized by using the `pageSize` of [`pageSettings`](http://help.syncfusion.com/api/angular/ejgrid#members:pagesettings-pagesize) property. When it is not given the default values for `pageSize` and `pageCount` are 12 and 8 respectively.


## Enable Filtering

[`Filtering`](https://help.syncfusion.com/angular/grid/filter) can be enabled by setting the [`allowFiltering`](https://help.syncfusion.com/api/angular/ejgrid#members:allowfiltering) to be `true`. By default, the filter bar row is displayed to perform filtering, you can change the filter type by using `filterType` of [`filterSetting`](http://help.syncfusion.com/api/angular/ejgrid#members:filtersettings) property.


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}


{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = window.gridData;
         }
     }

{% endhighlight %}


![Angular Grid in Enable Filtering](Getting-started_images/Getting-started2_img3.png)
{:.image }

## Enable Grouping

[`Grouping`](https://help.syncfusion.com/angular/grid/grouping) can be enabled by setting the [`allowGrouping`](http://help.syncfusion.com/api/angular/ejgrid#members:allowgrouping) to `true`.  Columns can be grouped dynamically by drag and drop the grid column header to the group drop area. The initial grouping can be done by adding required column names in the `groupedColumns` of [`groupSettings`](http://help.syncfusion.com/api/angular/ejgrid#members:groupsettings-groupedcolumns) property. 


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>


{% endhighlight %}

{% highlight javascript %}
    
    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = window.gridData;
        }
     }

{% endhighlight %}


![Angular Grid in Enable Grouping](Getting-started_images/Getting-started2_img4.png)
{:.image }

Refer to the following code example for initial grouping.


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupedColumn" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
})
export class AppComponent {
    public gridData;
    groupedColumns:object;
	constructor()
    {
         //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
         this.gridData = window.gridData;
         this.groupedColumn = {groupedColumns: ["ShipCountry"]};
     }
 }

{% endhighlight %}


![Angular Grid in Initial Grouping](Getting-started_images/Getting-started2_img5.png)
{:.image }


## Add Summaries

[`Summaries`](https://help.syncfusion.com/angular/grid/summary) can be added by setting the [`showSummary`](http://help.syncfusion.com/api/angular/ejgrid#members:showsummary) to true and adding required summary rows and columns in the [`summaryRows`](http://help.syncfusion.com/api/angular/ejgrid#members:summaryrows) property. For demonstration, Freight column's sum value is displayed as summary.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupedColumn" [showSummary]="true"  [summaryRows]="summaryRows">
    <e-columns>
        <e-column field="OrderID"  headerText="Order ID"  width="80" textAlign="left"></e-column>
        <e-column field="CustomerID" headerText="Customer ID" width="80" textAlign="right"></e-column>
        <e-column field="ShipCity" headerText="Ship City" width="80" textAlign="left"></e-column>
        <e-column field="EmployeeID" headerText="Employee ID" width="80" textAlign="right"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}" width="80" textAlign="right"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import {Component, ViewEncapsulation} from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html'  //give the path file for Grid control html file.
})
export class AppComponent {
    public gridData;
    groupedColumns:object;
    summaryRows:array;
	constructor()
    {
         //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
         this.gridData = window.gridData;
         this.groupedColumn = {groupedColumns: ["ShipCity"]};
         this.summaryRows=[{
                  	title: "Sum",
                  	summaryColumns: [
                    { summaryType: ej.Grid.SummaryType.Sum, displayColumn: "Freight", dataMember: "Freight" }
              	  ]
              }
			];  
     }
 }

{% endhighlight %}


![Angular Grid in Add Summaries](Getting-started_images/Getting-started2_img6.png)
{:.image }
