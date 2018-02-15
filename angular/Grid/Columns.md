---
layout: post
title: Columns with Grid widget for Syncfusion Essential Angular-2
description: How to define the columns and its features
platform: Angular
control: Grid
documentation: ug
api: /api/Angular/grid
--- 
# Columns

Column definitions are used as the `dataSource` schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on the column definitions. The `field` property of the `e-column` is necessary to map the datasource values in Grid columns.

N> 1. If the column with `field` is not in the datasource, then the column values will be displayed as empty.
N> 2. If the `field` name contains "dot" operator then it is considered as complex binding.

## Auto generation

The [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") are automatically generated when [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") declaration is empty or undefined while initializing the Grid. Also, all the columns which are in [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource "dataSource") are bound as a Grid columns.

The following code example shows auto-generate columns behavior.

{% highlight html %} 
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true">
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img1.png)


## Headers

### HeaderText

It represents the title for particular column. To enable header text, set [`headerText`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertext "headerText") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns"). The following code example describes the above behavior.

N> If [`headerText`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertext "headerText") is not defined then the [`field`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-field "field") name is considered as header text for that particular column. If both [`field`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-field "field") name and [`headerText`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertext "headerText") are not defined then the column is rendered with "empty" header text.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
       <e-column field="OrderID"  headerText="OrderID"></e-column>
       <e-column field="EmployeeID" headerText="Emp ID"></e-column>
       <e-column field="Freight"  headerText="Freight"></e-column>
       <e-column field="ShipCountry" headerText="Country"></e-column>
       <e-column field="ShipCity"  headerText="City"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img2.png)


### Header Text alignment

Align the header text of column header using [`headerTextAlign`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertextalign "headerTextAlign") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns"). There are four possible ways to align header text, they are

1. Right
2. Left
3. Center
4. Justify

N> For [`headerTextAlign`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertextalign "headerTextAlign") property you can assign either `string` value ("right") or `enum` value (`ej.TextAlign.Right`).

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData">
    <e-columns>
       <e-column field="OrderID"  headerText="OrderID"></e-column>
       <e-column field="EmployeeID" headerText="Emp ID" headerTextAlign="right"></e-column>
       <e-column field="Freight"  headerText="Freight"></e-column>
       <e-column field="ShipCountry" headerText="Country" headerTextAlign="center"></e-column>
       <e-column field="ShipCity"  headerText="City" headerTextAlign="right"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public right;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.right = ej.TextAlign.Right;
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img3.png)


## Header Template

The template design that applies on for the column header. To render template, set [`headerTemplateID`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-headertemplateid "headerTemplateID") property of the [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns").


N> It's a standard way to enclose the [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-template "template") within the `script` tag with `type` as `text/x-jsrender`.

The following code example describes the above behavior.

{% highlight html %}
<div id="customerTemplate">
<span class="e-userlogin e-icon headericon"></span>
 CUS ID
</div>
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
       <e-column field="OrderID"  headerText="OrderID"></e-column>
       <e-column field="EmployeeID" headerText="Emp ID" headerTemplateID= "#customerTemplate"></e-column>
       <e-column field="Freight"  headerText="Freight"></e-column>
       <e-column field="ShipCountry" headerText="Country"></e-column>
       <e-column field="ShipCity"  headerText="City"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {        
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }
     
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img4.png)


## Text alignment

You can align both content and header text of particular column using [`textAlign`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-textalign "textAlign") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns"). There are four possible ways to align content and header text of column, they are 

1. Right
2. Left
3. Center
4. Justify

N> 1. For [`textAlign`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-textalign "textAlign") property you can assign either `string` value ("right") or `enum` value (`ej.TextAlign.Right`).
N> 2. The [`textAlign`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-textalign "textAlign") property will affect both content and header text of the grid.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
       <e-column field="OrderID" textAlign="right"></e-column>
       <e-column field="EmployeeID" textAlign="right"></e-column>
       <e-column field="Freight" textAlign="right"></e-column>
       <e-column field="ShipCountry" textAlign="center"></e-column>
       <e-column field="ShipCity" textAlign="justify"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.right=ej.TextAlign.Right;
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img5.png)


## Format

[Format](https://help.syncfusion.com/api/angular/ejgrid#members:columns-format "Format") is the process of customizing the particular column data with specified jQuery recognized globalize formats, such as currency, numeric, decimal, percentage or dates. The globalize format can be specified by using [`format`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-format "format") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns").

The [`format`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-format "format") value should be wrapped within "{0:" and "}". (For ex: "{0:C3}"). The [data format](https://github.com/jquery/globalize/tree/v0.1.1#format "data format") strings are available for the Date and Number types.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData">
    <e-columns>
       <e-column field="OrderID"></e-column>
       <e-column field="EmployeeID"></e-column>
       <e-column field="Freight" format="{0:C2}"></e-column>
       <e-column field="OrderDate" format="{0:dd/MM/yyyy}"></e-column>
       <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img6.png)


## Width

You can specify the width for particular column by setting [`width`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-width "width") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") as in pixel (ex: 100) or in percentage (ex: 40%).

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="OrderID" width="110"></e-column>
        <e-column field="EmployeeID" width="110"></e-column>
        <e-column field="Freight" width="100"></e-column>
        <e-column field="ShipCountry" width="150"></e-column>
        <e-column field="ShipCity" width="100"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}



The following output is displayed as a result of the above code example.

![](columns_images/columns_img7.png)


## Resizing


The [`allowResizing`](https://help.syncfusion.com/api/angular/ejgrid#members:allowresizing "allowResizing") property enables the grid to set the width to columns based on resizing the grid column manually.


### Resizing modes


[`resizeSettings.resizeMode`](https://help.syncfusion.com/api/angular/ejgrid#members:resizesettings-resizemode "resizeSettings.resizeMode") mode is used to change the resizing modes. It indicates whether to define mode of resizing.


<table>
<tr>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td class="name">normal</td>
<td class="description">New column size will be adjusted by all other Columns</td>
</tr>
<tr>
<td class="name">nextColumn</td>
<td class="description">New column Size will be adjusted using next column.</td>
</tr>
<tr>
<td class="name">control</td>
<td class="description">New column Size will be adjusted using entire control</td>
</tr>
</table>


The following code example describes the above behavior.


{% highlight html %}


 <ej-grid id= "Grid"[dataSource] = "gridData"[allowResizing] = "true" [resizeSettings] = "resizeSettings">
                <e-columns>
                   <e-column field="OrderID" width="110"></e-column>
                    <e-column field="EmployeeID" width="110"></e-column>
                      <e-column field="Freight" width="100"></e-column>
                        <e-column field="ShipCountry" width="150"></e-column>
                           <e-column field="ShipCity" width="100"></e-column>
                                   </ej-grid>



{% endhighlight %}
{% highlight ts %}


import { Component, ViewEncapsulation } from '@angular/core';
                               @Component({
                                   selector: 'ej-app',
                                   templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
                               })
                               export class AppComponent {
                                   public gridData;
                                   public resizeSettings;
                                   constructor() {
                                       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
                                       this.gridData = window.gridData;
                                       this.resizeSettings = { allowResizing: true, resizeMode:"nextcolumn"};
                                   }
                               }


{% endhighlight %}


## Resize to fit 

The [`allowResizeToFit`](https://help.syncfusion.com/api/angular/ejgrid#members:allowresizetofit "allowResizeToFit") property enable the Grid to set width to columns based on maximum width of the particular column's content to facilitate full visibility of data in all the grid rows. This automatic behavior is applicable only for the columns which does not have width specified. 

On columns where "width is defined", double click on the particular column header's resizer symbol to resize the column to show the whole text. For example, refer the "ShipCity" column in the below code snippet and output screen shot. 

The following code example describes the above behavior. 

{% highlight html %} 
<ej-grid id="Grid" [dataSource]="gridData" [allowResizeToFit]="true">
    <e-columns>
        <e-column field="OrderID" width="100"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="Freight" width="75"></e-column>
        <e-column field="ShipCountry" width="50"></e-column>
        <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img8.png)


## Reorder

Reordering can be done by drag and drop on the particular column header from one index to another index within the Grid. Reordering can be enabled by setting [`allowReordering`](https://help.syncfusion.com/api/angular/ejgrid#members:allowreordering "allowReordering") property as `true`.

The following code example describes the above behavior.

{% highlight html %}                     
<ej-grid id="Grid" [dataSource]="gridData" [allowReordering]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipCity"></e-column>
        <e-column field="Freight"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img10.png)


## Visibility

You can hide particular column in Grid view by setting [`visible`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-visible "visible") property of it as `false`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="EmployeeID"></e-column>
        <e-column field="OrderID" [visible]="false"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img11.png)


## Unbound Column

You can define the unbound columns in Grid by not defining [`field`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-field "field") property for that particular column. Value for these columns can be populated either manually using [`queryCellInfo`](https://help.syncfusion.com/api/angular/ejgrid#events:querycellinfo "queryCellInfo") event or by using column [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-template "template") or by column [`format`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-format "format") property.

N> Editing, grouping, filtering, sorting, summary and searching support are not available for unbound columns.

The following code example describes the above behavior. 

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" >
    <e-columns>
        <e-column field= "OrderID"></e-column>
        <e-column field= "CustomerID"></e-column>
        <e-column field= "EmployeeID"></e-column>
        <e-column field= "Freight"></e-column>
        <e-column headerText="">
            <ng-template e-template let-data>
                <a (click)="Click($event)" href=#>Delete</a>
            </ng-template>
        </e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}
    
    import {Component, ViewEncapsulation} from '@angular/core';
    
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {        
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
        Click(){
            this.Grid.widget.deleteRecord("OrderID", this.Grid.widget.getSelectedRecords()[0]);
        }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img13.png)


## Column Template

HTML templates can be specified in the `template` property of the particular column as a string (HTML element) or ID of the template's HTML element.

N> If `field` is not specified, you will not able to perform editing, grouping, filtering, sorting, search and summary functionalities in particular column.

The following code example describes the above behavior.


{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [pageSettings]="pageSettings">
    <e-columns>
        <e-column headerText="Photo">
             <ng-template e-template let-data>
                <div *ngIf="data.EmployeeID">
                <img style="width: 75px; height: 70px" [attr.src]="'app/Content/images/grid/Employees/' + data.EmployeeID + '.png' " [alt]="data.EmployeeID" />
                </div>
            </ng-template>
         </e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="FirstName" headerText="FirstName"></e-column>
        <e-column field="LastName" headerText="LastName"></e-column>
        <e-column field="Country" headerText="Country"></e-column>
    </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public pageSettings;
    	constructor()
        {
           //The datasource "window.employeeView" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.employeeView;
           this.pageSettings = { pageSize:"4" };
        }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](columns_images/columns_img14.png)


## Controlling Grid actions

You can control the Grid actions of a particular column by setting [`allowSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowsorting "allowSorting"), [`allowGrouping`](https://help.syncfusion.com/api/angular/ejgrid#members:allowgrouping "allowGrouping"), `allowFiltering`, [`allowResizing`](https://help.syncfusion.com/api/angular/ejgrid#members:allowresizing "allowResizing") and [`allowEditing`](https://help.syncfusion.com/api/angular/ejgrid#members:editsettings-allowediting "allowEditing") properties.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid #Grid [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [allowGrouping]="true" [allowSorting]="true" [allowResizing]="true" [editSettings]="editSettings" >
    <e-columns>
        <e-column field= "OrderID"></e-column>
        <e-column field= "EmployeeID" [allowFiltering]=false [allowGrouping]=false [allowSorting]=false [allowResizing]=false [allowEditing]="false"></e-column>
        <e-column field= "Freight"></e-column>
        <e-column field= "ShipCountry"></e-column>
        <e-column field= "ShipCity"></e-column>
    </e-columns>
</ej-grid>  
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
    	constructor()
        {        
        //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
        this.editSettings = {allowEditing:true};
        }
     }
     
{% endhighlight %}

## Read only

To make a column as "read-only" then set [`allowEditing`](https://help.syncfusion.com/api/angular/ejgrid#members:editsettings-allowediting "allowEditing") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") as `false`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [editSettings]="editSettings">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"></e-column>
        <e-column field="EmployeeID" [allowEditing]="false"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.editSettings={allowEditing:true};
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img15.png)


## Expression Column

[Expression](https://help.syncfusion.com/api/angular/ejgrid#members:columns-template "Expression") column is possible only for [`template`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-template "template") column.

You can use JsRender syntax in the template.For more information about JsRender syntax, please refer [the link](http://www.jsviews.com/#jsrapi "the link"). 

N> This expression column is supported at read only mode.

The following code example describes the above behavior.

{% highlight html %} 
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true">
    <e-columns>
        <e-column field="FoodName" ></e-column>
        <e-column field="Protein" ></e-column>
        <e-column field="Fat" ></e-column>
        <e-column field="Carbohydrate" ></e-column>
        <e-column headerText="Calories In Take">
             <ng-template e-template let-data>
                <span>{{data.Protein * 4 + data.Fat * 4 + data.Carbohydrate * 9}}</span>
            </ng-template>
        </e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "window.FoodInformation" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = window.FoodInformation;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img16.png)


## Command Column

### Default action buttons

Using [`command`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands "command") column, you can add CRUD action buttons as one of the Grid column, through [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-type "type") property of [`commands`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands "commands"). The type property supports the below default [`UnboundType`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-type "UnboundType") buttons.

1. edit
2. save
3. delete
4. cancel

Through [`buttonOptions`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-buttonoptions "buttonOptions") property of [`commands`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands "commands"), you can specify all the button options which are supported by Essential Studio JavaScript [`Button`](https://help.syncfusion.com/api/angular/ejbutton# "Button") control. 

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [editSettings]="editSettings">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column  headerText= "Manage Records" [commands]="buttons"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.editSettings={allowEditing:true,allowAdding:true,allowDeleting:true};
            this.buttons=[    { type: "edit", buttonOptions: { text: "Edit" } },
                              { type: "delete", buttonOptions: { text: "Delete" } },
                              { type: "save", buttonOptions: { text: "Save" } },
                              { type: "cancel", buttonOptions: { text: "Cancel" } }
                         ];
        }
    }
                        
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img17.png)


### Custom buttons

You can add custom button in the command column by specifying the [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-type "type") property of [`commands`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands "commands") as "empty" or any other `string` which does not corresponds to default [`UnboundType`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-type "UnboundType") buttons.

N> 1. For [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-commands-type "type") property you can assign either `string` value ("edit") or `enum` value (`ej.Grid.UnboundType.Edit`).
N> 2. In command column you can add only buttons.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [editSettings]="editSettings">
    <e-columns>
        <e-column field= "EmployeeID"></e-column>
        <e-column  headerText= "Employee Details" [commands]="buttons"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}
    
    import {Component, ViewEncapsulation} from '@angular/core';
    
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
        public editSettings;
        public buttons;
    	constructor()
        {        
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.editSettings={allowEditing:true };
            this.buttons=[{ type: "details", buttonOptions: { text: "Edit",
                            click: function(){
                                    var grid = $("#Grid").ejGrid("instance");
                                    var index = this.element.closest("tr").index();
                                    var record = grid.getCurrentViewData()[index];
                                    alert("Record Details: " + JSON.stringify(record));
                                    } 
                            }
                        }];
        }
     }
     
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img18.png)


## Column Chooser

Column chooser contains the list of all the columns which are defined in the [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") property. Using this you can control the visibility of columns in Grid. You can prevent to show the particular column name in column chooser by setting [`showInColumnChooser`](https://help.syncfusion.com/api/angular/ejgrid#members:showcolumnchooser "showInColumnChooser") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") as `false`. 



Column Chooser would be shown in the top right corner of Grid. To enable column chooser, set [`showColumnChooser`](https://help.syncfusion.com/api/angular/ejgrid#members:showcolumnchooser "showColumnChooser") property as `true`. 

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [showColumnChooser]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID" [showInColumnChooser]="false"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img19.png)


## Foreign Key Column

Lookup data source can be bound to [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource "dataSource") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns"). Data [`field`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-field "field") and `text` can be set using [`foreignKeyField`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-foreignkeyfield "foreignKeyField") and [`foreignKeyValue`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-foreignkeyvalue "foreignKeyValue") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns").

In the [`dataSource`](https://help.syncfusion.com/api/angular/ejgrid#members:datasource "dataSource") property, we can bound local and remote data.

I> For foreign key column the sorting and grouping is based on [`foreignKeyField`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-foreignkeyfield "foreignKeyField") instead of [`foreignKeyValue`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-foreignkeyvalue "foreignKeyValue").

N> In remote data, server should be configured to perform select and filter operations since the Grid will try to fetch required columns using select operation and required data using filter operation.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [editSettings]="editSettings">
    <e-columns>
        <e-column field="OrderID" [isPrimaryKey]="true"></e-column>
        <e-column field="EmployeeID" foreignKeyField= "EmployeeID" foreignKeyValue= "FirstName" [dataSource]= "employeedata" headerText= "FirstName" ></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCity"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" and "window.employeeView" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.employee = (window as any).employeeView;
            this.editSettings={allowAdding:true, allowEditing:true, allowDeleting:true, };
        }
    }
            
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img20.png)


## Customize column

You can [customize](https://help.syncfusion.com/api/angular/ejgrid#members:columns-cssclass "customize") the header and content of the particular column by [`cssClass`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-cssclass "cssClass") property of the column.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData">
    <e-columns>
        <e-column field= "OrderID"></e-column>
        <e-column field= "CustomerID"></e-column>
        <e-column field= "EmployeeID" cssClass="customCSS"></e-column>
        <e-column field= "Freight"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
      encapsulation: ViewEncapsulation.None,
      styles:[`.customCSS.e-headercell {
	            background-color: #2382c3;
	            color: white;
	            font-family: 'Bell MT';
	            font-size: 20px;
      }
               .customCSS.e-rowcell {
	            background-color: #ecedee;
	            font-family: 'Bell MT';
	            color: red;
	            font-size: 20px;
      }`]
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img23.png)


## Type

Used to define the type of the particular column data. If the [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-type "type") property of [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns") is not specified then its type is automatically defined based on the first row data of that column.

N> The [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-type "type") is needed for filtering feature when first row of the data is "null" or "empty".

The available column data type is tabulated as follows.

<table>
<tr>
<th>
Type</th><th>
Description</th>
</tr>
<tr>
<td>
string</td><td>
Gets or sets the type of the column value as string </td>
</tr>
<tr>
<td>
number</td><td>
Gets or sets the type of the column value as number</td>
</tr>
<tr>
<td>
date</td><td>
Gets or sets the type of the column value as date</td>
</tr>
<tr>
<td>
datetime</td><td>
Gets or sets the type of the column value as datetime</td>
</tr>
<tr>
<td>
boolean</td><td>
Gets or sets the type of the column value as true or false </td>
</tr>
<tr>
<td>
guid</td><td>
Gets or sets the type of the column value as guid</td>
</tr>
<tr>
<td>
checkbox </td><td>
Gets or sets the type of the column value as checkbox for row selection </td>
</tr>
</table>

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="CustomerID" type="string"></e-column>
        <e-column field="EmployeeID" type="number"></e-column>
        <e-column field="Freight"></e-column>
        <e-column field="ShipCountry"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
        }
    }
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img24.png)

## Column Layout

You can set the Grid's columns layout based on either Grid width or its columns width using [`columnLayout`](https://help.syncfusion.com/api/angular/ejgrid#members:columnlayout "columnLayout") property of Grid. There are two ways to set the column layout, they are 

1. Auto
2. Fixed

N> 1. For [`columnLayout`](https://help.syncfusion.com/api/angular/ejgrid#members:columnlayout "columnLayout") property you can assign either `string` value ("fixed") or `enum` value (`ej.Grid.ColumnLayout.Fixed`).
N> 2. Default [`columnLayout`](https://help.syncfusion.com/api/angular/ejgrid#members:columnlayout "columnLayout") is `auto` which is set the columns layout based on the Grid's width.

The following code example describes the above behavior.

{% highlight html %}           
<ej-grid id="Grid" [dataSource]="gridData" [columnLayout]="fixed">
    <e-columns>
        <e-column field="OrderID" width= "80"></e-column>
        <e-column field="EmployeeID" width= "80"></e-column>
        <e-column field="ShipCity" width= "90"></e-column>
        <e-column field="ShipName" width= "110"></e-column>
        <e-column field="ShipCountry" width= "100"></e-column>
        <e-column field="Freight" width= "80"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}

    import {Component, ViewEncapsulation} from '@angular/core';
    @Component({
      selector: 'ej-app',
      templateUrl: 'app/app.component.html',  //give the path file for Grid control html file.
    })
    export class AppComponent {
        public gridData;
    	constructor()
        {
            //The datasource "(window as any).gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            this.gridData = (window as any).gridData;
            this.fixed = ej.Grid.ColumnLayout.Fixed;
        }
    }
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img25.png)



