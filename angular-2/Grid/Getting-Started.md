layout:post
title: Getting Started for Angular-2 Grid
description: How to create the Grid, data bind, enable paging, grouping, filtering and add summaries
platform: Angular-2
control: Grid
documentation: ug
---
# Getting started

To get start with how to use the Grid component within Angular-2 platform, please refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/gettingstarted/getting-started-systemjs).By following the above steps in the document, you can get the newly cloned **angular2-seeds** template sample folder.Grid control has been already configured in that **angular2-seeds** folder.So that you can use already exisiting or modifiy grid sample available in **src/grid** folder.


## Copying Grid source file

In that newly cloned **angular2-seeds** folder,we have referred `grid.component.ts` source file from 14.3 version.If you want the upgraded version  of `grid.component.ts` source file, you can get it from the below mentioned location and add it under the **src/ej** folder. 

* (**Installed location**)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\

N> `core.ts` source file is mandatory for all Syncfusion JavaScript Angular 2 components. 


##  External and Internal Dependencies

If you want to know about the external and internal dependencies of the Grid control, please refer here [here](https://help.syncfusion.com/js/grid/getting-started)

I> `ej.angular2.min.js` file is additionally required to render the Grid in angular-2 platform which is available under the location, _(**Installed location**)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common_.


## Data Binding

[`Data binding`](http://help.syncfusion.com/js/grid/data-binding) in the grid is achieved by using the [`ej.DataManager`](https://help.syncfusion.com/js/datamanager/overview) that supports both RESTful JSON data services binding and local JSON array binding.  To set the data source to the grid, the [`dataSource`](http://help.syncfusion.com/js/api/ejgrid#members:columns-datasource) property is assigned with the instance of the `ej.DataManger`. For demonstration purpose, [Northwind OData service](http://mvc.syncfusion.com/Services/Northwnd.svc/) is used in this tutorial. Refer to the following code example.

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

{% highlight ts %}
   
    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      providers:[NorthwindService]
    })
    export class AppComponent {
        public gridData;
        public dataManager;
    	constructor()
        {
             this.dataManager = ej.DataManager({
                    url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                    crossDomain:true
                });
             this.gridData = this.dataManager;
         }
     }

{% endhighlight %}

![](Getting-started_images/Getting-started2_img1.jpeg)
{:.image }

N> 1.In the above code snippet, `ej-grid` denotes the control directive for the Syncfusion's Grid angular 2 widget and all its properties can be initialized with the exact casing of original property names also binded within square bracket(`[]`).(For example, [dataSource]).
N> 2.Events can be bound to the control using the event name within bracket [`()`].  For example, the `actionBegin` event of Grid control can be defined as follows.
     
 {% highlight html %}

   <ej-grid id="Grid" [dataSource]="gridData"  (actionBegin)= actionBegin($event)>

 {% endhighlight %}

N> 3.ODataAdaptor is the default adaptor for the DataManager. On binding to other web services, proper [data adaptor](http://help.syncfusion.com/js/datamanager/data-adaptors)  needs to be set on `adaptor` option of the DataManager.

## Enable Paging

[`Paging`](http://help.syncfusion.com/js/grid/paging) can be enabled by setting the [`allowPaging`](http://help.syncfusion.com/js/api/ejgrid#members:allowpaging) to true. The Paging feature in Grid offers complete navigation support to easily switch between the pages, using the page bar available at the bottom of the Grid control

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


{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      providers:[NorthwindService]
    })
    export class AppComponent {
        public gridData;
        public dataManager;
    	constructor()
        {
             this.dataManager = ej.DataManager({
                    url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                    crossDomain:true
                });
             this.gridData = this.dataManager;
         }
     }

{% endhighlight %}

![](Getting-started_images/Getting-started2_img2.png)
{:.image }

N> Pager settings can be customized by using the `pageSize` of [`pagesettings`](http://help.syncfusion.com/js/api/ejgrid#members:pagesettings-pagesize) property. When it is not given the default values for `pageSize` and `pageCount` are 12 and 8 respectively.


## Enable Filtering

[`Filtering`](/js/grid/filter) can be enabled by setting the [`allowFiltering`] (https://help.syncfusion.com/js/api/ejgrid#members:allowfiltering) to be `true`. By default, the filter bar row is displayed to perform filtering, you can change the filter type by using `filterType` of [`filterSetting`](http://help.syncfusion.com/js/api/ejgrid#members:filtersettings) property.


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


{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      providers:[NorthwindService]
    })
    export class AppComponent {
        public gridData;
        public dataManager;
    	constructor()
        {
             this.dataManager = ej.DataManager({
                    url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                    crossDomain:true
                });
             this.gridData = this.dataManager;
         }
     }

{% endhighlight %}


![](Getting-started_images/Getting-started2_img3.png)
{:.image }

## Enable Grouping

[`Grouping`](/js/grid/grouping) can be enabled by setting the [`allowGrouping`](http://help.syncfusion.com/js/api/ejgrid#members:allowgrouping) to `true`.  Columns can be grouped dynamically by drag and drop the grid column header to the group drop area. The initial grouping can be done by adding required column names in the `groupedColumns` of [`groupSettings`](http://help.syncfusion.com/js/api/ejgrid#members:groupsettings-groupedcolumns) property. 


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

{% highlight ts %}
    
    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      providers:[NorthwindService]
    })
    export class AppComponent {
        public gridData;
        public dataManager;
    	constructor()
        {
             this.dataManager = ej.DataManager({
                    url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                    crossDomain:true
                });
             this.gridData = this.dataManager;
        }
     }

{% endhighlight %}


![](Getting-started_images/Getting-started2_img4.png)
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

{% highlight ts %}

import {Component, ViewEncapsulation} from '@angular/core';
import {NorthwindService} from './services/northwind.service';
@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
  providers:[NorthwindService]
})
export class AppComponent {
    public gridData;
    public dataManager;
    groupedColumns:object;
	constructor()
    {
         this.dataManager = ej.DataManager({
                url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                crossDomain:true
            });
         this.gridData = this.dataManager;
         this.groupedColumn = {groupedColumns: ["ShipCountry"]};
     }
 }

{% endhighlight %}


![](Getting-started_images/Getting-started2_img5.png)
{:.image }


## Add Summaries

[`Summaries`](http://help.syncfusion.com/js/grid/summary) can be added by setting the [`showSummary`](http://help.syncfusion.com/js/api/ejgrid#members:showsummary) to true and adding required summary rows and columns in the [`summaryRows`](http://help.syncfusion.com/js/api/ejgrid#members:summaryrows) property. For demonstration, Freight column's sum value is displayed as summary.

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

{% highlight ts %}

import {Component, ViewEncapsulation} from '@angular/core';
import {NorthwindService} from './services/northwind.service';
@Component({
  selector: 'ej-app',
  templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
  providers:[NorthwindService]
})
export class AppComponent {
    public gridData;
    public dataManager;
    groupedColumns:object;
    summaryRows:array;
	constructor()
    {
         this.dataManager = ej.DataManager({
                url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/", 
                crossDomain:true
            });
         this.gridData = this.dataManager;
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


![](Getting-started_images/Getting-started2_img6.png)
{:.image }






