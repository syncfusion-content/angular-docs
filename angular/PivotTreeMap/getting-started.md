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

## Script and CSS Reference

Create a **HTML** page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}

    <!DOCTYPE html>
    <html>
    <head> 
        <link href="//cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="node_modules/core-js/client/shim.min.js"></script>
        <script src="node_modules/zone.js/dist/zone.js"></script>
        <script src="node_modules/reflect-metadata/Reflect.js"></script>
        <script src="node_modules/systemjs/dist/system.src.js"></script>
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
        <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
        <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.angular2.min.js"></script>
        <script src="systemjs.config.js"></script>
    </head>
    <body>
    <ej-app>Loading...</ej-app>
    </body>
    </html>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[`CSG`](http://csg.syncfusion.com "CSG")utility to generate a custom script file with the required widgets for deployment purpose.

### Control Initialization

Add necessary HTML elements to render PivotTreeMap

{% highlight html %}

    <ej-pivottreemap [dataSource.data]="data" [dataSource.catalog]="catalog" [dataSource.cube]="cube" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values">
    </ej-pivottreemap>
    
    <script id="tooltipTemplate" type="application/jsrender">
            <div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
                <div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
            </div>
    </script>  

{% endhighlight %}

{% highlight html %}

    import {Component, ViewEncapsulation} from '@angular/core';
    
    @Component({
    selector: 'sd-home',
    templateUrl: 'app/components/pivottreemap/pivottreemap.component.html', //give the path file for pivottreemap component html file.
    styleUrls: ['app/components/pivottreemap/pivottreemap.component.css'],  //give the path file for pivottreemap component css file.
    })
    export class PivotTreeMapComponent {
    }

{% endhighlight %}

Create a **CSS** page and add necessary CSS elements for PivotTreeMap

{% highlight html %}

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

{% highlight html %}

    <ej-pivottreemap [dataSource.data]="data" [dataSource.catalog]="catalog" [dataSource.cube]="cube" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values">
    </ej-pivottreemap>
    
    <script id="tooltipTemplate" type="application/jsrender">
            <div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
                <div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
            </div>
    </script>  

{% endhighlight %}

{% highlight html %}

    import {Component, ViewEncapsulation} from '@angular/core';
    
    @Component({
    selector: 'sd-home',
    templateUrl: 'app/components/pivottreemap/pivottreemap.component.html', //give the path file for pivottreemap component html file.
    styleUrls: ['app/components/pivottreemap/pivottreemap.component.css'],  //give the path file for pivottreemap component css file.
    })
    export class PivotTreeMapComponent {
        public data; cube; catalog; rows; columns;values;filters;
        constructor() {
            this.data = "http://bi.syncfusion.com/olap/msmdpump.dll";
            this.cube = "Adventure Works";
            this.catalog = "Adventure Works DW 2008 SE";
            this.rows = [{ fieldName: "[Date].[Fiscal]" }];
            this.columns = [{ fieldName: "[Customer].[Customer Geography]" }];
            this.values = [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]", }], axis: "columns" }];
            this.filters = [];
        }
    }

{% endhighlight %}

The above code will generate a simple PivotTreeMap with internet sales amount over a period of fiscal years across different customer geographic locations.

![](getting-started_images/Olap.png)