---
title: Getting Started for Angular 2 Spreadsheet
description: How to create a Spreadsheet with data source, apply format and export it as excel file.
platform: Angular-2
control: Spreadsheet
documentation: Ug
keywords: 
---
# Getting started

Before we start with the Spreadsheet, please refer [`this page`](https://help.syncfusion.com/angular-2/overview) for general information regarding integrating Syncfusion widget's.
This section explains you the steps required to populate the Spreadsheet with data, format, and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

## Adding Script Reference

To render the Spreadsheet control, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions

The required angular2 script as `ej.angular2.min.js` which can be available in below `CDN` link:

* [http://cdn.syncfusion.com/14.3.0.52/js/common/ej.angular2.min.js](http://cdn.syncfusion.com/14.3.0.52/js/common/ej.angular2.min.js)

For other required internal dependencies refer the [`link`](http://help.syncfusion.com/js/spreadsheet/dependencies "link")

N> Spreadsheet uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the Spreadsheet, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

So the complete boilerplate code is

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
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js">
    </script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.angular2.min.js"></script>
    <script src="systemjs.config.js"></script>
  </head>
  <body>
   <ej-app>Loading...</ej-app>
  </body>
</html>

{% endhighlight %}

N> In production, we highly recommend you to use our [`custom script generator`](http://helpjs.syncfusion.com/js/custom-script-generator)  to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [`GZip compression`](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.
N> For themes, you can use the `ej.web.all.min.css` CDN link from the code example given. To add the themes in your application, please refer to [`this link`](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Initialize Spreadsheet

The Sreadsheet component can be created with prefix of `ej-`.The code example for defining controls in Angular2 is as follows,

{% highlight html %}

    <ej-spreadsheet id="spreadsheet" scrollSettings.height="530" scrollSettings.width="100%">
    </ej-spreadsheet>

{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet component html file.
    })
    export class AppComponent {
    }
    
{% endhighlight %}

Now, the Spreadsheet is rendered with default row and column count.

![](Getting-Started_images/Getting-Started_img1.png)

## Populate Spreadsheet with data

Now, this section explains how to populate JSON data to the Spreadsheet. You can set [`dataSource`](http://help.syncfusion.com/js/api/ejspreadsheet#members:sheets-datasource "dataSource") property in [`e-rangesettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:sheets "sheet") to populate JSON data in Spreadsheet.

{% highlight html %}

    <ej-spreadsheet id="spreadsheet">
        <e-sheets>
            <e-sheet>
                 <e-rangesettings>
                    <e-rangesetting [dataSource]="spreadData" startCell="A1" [headerStyles]="{'font-weight':'bold'}"></e-rangesetting>
                 </e-rangesettings>
            </e-sheet>
        </e-sheets>
    </ej-spreadsheet>

{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';
    @Component({
        selector: 'ej-app',
  t     emplateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[NorthwindService]
    })
    export class AppComponent {
        public spreadData;
        constructor(public northwindService: NorthwindService) {
            this.spreadData = ej.DataManager(northwindService.getFoodInformation()).executeLocal(ej.Query().take(50).select("FoodId", "Time", "FoodName", "Calorie", "Protein", "Fat", "Carbohydrate"));
     }
    }

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)

N> For more details about `data binding` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-binding "link")

## Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain color based on the cells values. You can use [`allowConditionalFormats`](http://help.syncfusion.com/js/api/ejspreadsheet#members:allowconditionalformats "allowConditionalFormats") property within square bracket(`[]`) to enable/disable Conditional formats.

Events can be bound to the controls using the event name within bracket [`()`]. For example, the `loadComplete` event of Spreadsheet control can be defined as follows.

{% highlight html %}

    <ej-spreadsheet id="spreadsheet" [allowConditionalFormats]= true (loadComplete)= loadComplete($event)>

{% endhighlight %}

To apply conditional formats for a range use [`setCFRule`](http://help.syncfusion.com/js/api/ejspreadsheet#methods:xlcformat-setcfrule "setCFRule") method. The following code example illustrates this,

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    import {NorthwindService} from './services/northwind.service';

    @Component({
        selector: 'ej-app',
        templateUrl: 'app/app.component.html',  //give the path file for spreadsheet control html file.
        providers:[NorthwindService]
    })

    export class AppComponent {
        loadComplete(event) {
            let xlObj = $("#spreadsheet").data("ejSpreadsheet");
            xlObj.XLCFormat.setCFRule({ "action": "equalto", "inputs": ["100"], "color":   "redft", "range": "D1:D7" });
        }
    }

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)

N> For more details about `Conditional Formatting` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-presentation#conditional-formatting "link")

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set [`exportSettings.allowExporting`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-allowexporting "allowExporting") option as `true`and Specify [`exportSettings.excelUrl`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-excelurl "excelUrl") option to save documents using server side helper. The following code example illustrates this,

{% highlight html %}

    <ej-spreadsheet id="spreadsheet"  exportSettings.excelUrl="http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToExcel" >
    </ej-spreadsheet>

{% endhighlight %}

Use shortcut [`Ctrl + S`](http://help.syncfusion.com/js/spreadsheet/keyboard-shortcuts "Ctrl + S") to save Spreadsheet as excel file.

N> 1. For more details about `Export` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#save "link")
N> 2. For more details about `Server Configuration` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#server-configuration "link")
