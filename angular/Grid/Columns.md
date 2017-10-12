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

The [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns") are automatically generated when [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns") declaration is empty or undefined while initializing the Grid. Also, all the columns which are in [`dataSource`](https://help.syncfusion.com/api/js/ejgrid#members:datasource "dataSource") are bound as a Grid columns.

The following code example shows auto-generate columns behavior.

{% highlight html %} 
<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true">
</ej-grid>
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img1.png)


### How to set isPrimaryKey for auto generated columns when editing is enabled:

Using [`dataBound`](https://help.syncfusion.com/api/js/ejgrid#events:databound "dataBound") event, you can set [`isPrimaryKey`](https://help.syncfusion.com/api/js/ejgrid#members:columns-isprimarykey "isPrimaryKey") value as `true` by two ways. The following code example demonstrates the above behavior.

1. If primary key "column index" is known then refer the following code example
{% highlight html %} 
<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" (dataBound)="onDataBound($event)">
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		editSettings : {
			allowEditing : true
		},
		dataBound : function (args) {
			var column = args.model.columns[0];
			//(or)
			var column = this.getColumnByIndex(0);
			column.isPrimaryKey = true;
			//Here columns method used to update the particular column
			this.columns(column, "update");
		}
	});
});
{% endhighlight %}
{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
this.editSettings={allowEditing:true};

{% endhighlight %}

2. If primary key "column field name" is known then refer the following code example
{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		editSettings : { allowEditing : true },
		dataBound : function (args) {
			var column = this.getColumnByField("OrderID");
			column.isPrimaryKey = true;
			//Here columns method used to update the particular column
			this.columns(column, "update");
		}
	});
});
{% endhighlight %}

## Headers

### HeaderText

It represents the title for particular column. To enable header text, set [`headerText`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertext "headerText") property of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). The following code example describes the above behavior.

N> If [`headerText`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertext "headerText") is not defined then the [`field`](https://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name is considered as header text for that particular column. If both [`field`](https://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name and [`headerText`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertext "headerText") are not defined then the column is rendered with "empty" header text.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
       <e-column field="OrderID"  headerText="OrderID"></e-column>
       <e-column field="CustomerID" headerText="CustomerID"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img2.png)


### Header Text alignment

[Align](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertextalign "Align") the header text of column header using [`headerTextAlign`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertextalign "headerTextAlign") property of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). There are four possible ways to align header text, they are

1. Right
2. Left
3. Center
4. Justify

N> For [`headerTextAlign`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertextalign "headerTextAlign") property you can assign either `string` value ("right") or `enum` value (`ej.TextAlign.Right`).

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData">
    <e-columns>
       <e-column field="OrderID"  headerText="OrderID"></e-column>
       <e-column field="CustomerID" headerText="CustomerID" [headerTextAlign]="right"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
this.right=ej.TextAlign.Right;
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img3.png)


## Header Template

The template design that applies on for the column header. To render template, set [`headerTemplateID`](https://help.syncfusion.com/api/js/ejgrid#members:columns-headertemplateid "headerTemplateID") property of the [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns").


N> It's a standard way to enclose the [`template`](https://help.syncfusion.com/api/js/ejgrid#members:columns-template "template") within the `script` tag with `type` as `text/x-jsrender`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
<script id="empTemplate" type="text/x-jsrender">
Emp ID
<span class="e-userlogin e-icon employee"></span>
</script>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		columns : [
			{ field : "OrderID", headerText : "Order ID" },
			{ field : "EmployeeID", headerTemplateID : "#empTemplate" },
			{ field: "Freight", headerText: "Freight" },
			{ field: "ShipCountry", headerText: "Country" },
			{ field: "ShipCity", headerText: "City" }
		]
	});
});
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img4.png)


## Text alignment

You can [align](https://help.syncfusion.com/api/js/ejgrid#members:columns-textalign "align") both content and header text of particular column using [`textAlign`](https://help.syncfusion.com/api/js/ejgrid#members:columns-textalign "textAlign") property of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns"). There are four possible ways to align content and header text of column, they are 

1. Right
2. Left
3. Center
4. Justify

N> 1. For [`textAlign`](https://help.syncfusion.com/api/js/ejgrid#members:columns-textalign "textAlign") property you can assign either `string` value ("right") or `enum` value (`ej.TextAlign.Right`).
N> 2. The [`textAlign`](https://help.syncfusion.com/api/js/ejgrid#members:columns-textalign "textAlign") property will affect both content and header text of the grid.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="CustomerID" [textAlign]="right"></e-column>
        <e-column field="EmployeeID"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
this.right=ej.TextAlign.Right;
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img5.png)


## Format

[Format](https://help.syncfusion.com/api/js/ejgrid#members:columns-format "Format") is the process of customizing the particular column data with specified jQuery recognized globalize formats, such as currency, numeric, decimal, percentage or dates. The globalize format can be specified by using [`format`](https://help.syncfusion.com/api/js/ejgrid#members:columns-format "format") property of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns").

The [`format`](https://help.syncfusion.com/api/js/ejgrid#members:columns-format "format") value should be wrapped within "{0:" and "}". (For ex: "{0:C3}"). The [data format](https://github.com/jquery/globalize/tree/v0.1.1#format "data format") strings are available for the Date and Number types.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData">
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="Freight" width="75" format="{0:C2}"></e-column>
    </e-columns>
</ej-grid> 
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img6.png)


## Width

You can specify the width for particular column by setting [`width`](https://help.syncfusion.com/api/js/ejgrid#members:columns-width "width") property of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns") as in pixel (ex: 100) or in percentage (ex: 40%).

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" >
    <e-columns>
        <e-column field="OrderID" width="75"></e-column>
        <e-column field="CustomerID" width="80"></e-column>
        <e-column field="ShipCity" width="110"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight ts %}
//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
this.gridData = window.gridData;
{% endhighlight %}



The following output is displayed as a result of the above code example.

![](columns_images/columns_img7.png)


## Resize to fit 

The [`allowResizeToFit`](https://help.syncfusion.com/api/js/ejgrid#members:allowresizetofit "allowResizeToFit") property enable the Grid to set width to columns based on maximum width of the particular column's content to facilitate full visibility of data in all the grid rows. This automatic behavior is applicable only for the columns which does not have width specified. 

On columns where "width is defined", double click on the particular column header's resizer symbol to resize the column to show the whole text. For example, refer the "ShipCity" column in the below code snippet and output screen shot. 

The following code example describes the above behavior. 

{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		allowResizeToFit : true,
		columns : [
			{ field: "OrderID", width: 100 },
			{ field: "EmployeeID" },
			{ field: "Freight", width: 75 },
			{ field: "ShipCity", width: 50 },
			{ field: "ShipAddress" }
		]
	});
});
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img8.png)


## Reorder

Reordering can be done by drag and drop the particular column header from one index to another index within the Grid. Reordering can be enabled by setting [`allowReordering`](https://help.syncfusion.com/api/js/ejgrid#members:allowreordering "allowReordering") property as `true`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		allowReordering : true,
		columns : ["OrderID", "EmployeeID", "ShipCity", "ShipCountry", "Freight"]
	});
});
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img10.png)


## Visibility

You can hide particular column in Grid view by setting [`visible`](https://help.syncfusion.com/api/js/ejgrid#members:columns-visible "visible") property of it as `false`.

The following code example describes the above behavior.

{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		columns : [
			{ field: "EmployeeID"},
			{ field: "OrderID", visible: false },
			{ field: "Freight" },
			{ field: "ShipCity" },
			{ field: "ShipCountry" }
		]
	});
});
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img11.png)


## Unbound Column

You can define the unbound columns in Grid by not defining [`field`](https://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") property for that particular column. Value for these columns can be populated either manually using [`queryCellInfo`](https://help.syncfusion.com/api/js/ejgrid#events:querycellinfo "queryCellInfo") event or by using column [`template`](https://help.syncfusion.com/api/js/ejgrid#members:columns-template "template") or by column [`format`](https://help.syncfusion.com/api/js/ejgrid#members:columns-format "format") property.

N> Editing, grouping, filtering, sorting, summary and searching support are not available for unbound columns.

The following code example describes the above behavior. 

{% highlight html %}
<div id="Grid"></div>
{% endhighlight %}

{% highlight javascript %}
$(function () {
	$("#Grid").ejGrid({
		//The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
		dataSource : window.gridData,
		allowPaging : true,
		editSettings : {
			allowDeleting : true
		},
		columns : [
			{ field: "OrderID", isPrimaryKey: true },
			{ field: "CustomerID" },
			{ field: "EmployeeID" },
			{ field: "Freight" },
			{ headerText: "",format: "<a onclick =\"click(this)\" href=#>Delete</a>" }
		]
	});
});

function click(e) {
	var obj = $("#Grid").data("ejGrid");
	obj.deleteRecord("OrderID", obj.getSelectedRecords()[0]);
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img13.png)


## Column Template

HTML templates can be specified in the `template` property of the particular column as a string (HTML element) or ID of the template's HTML element.

N> If `field` is not specified, you will not able to perform editing, grouping, filtering, sorting, search and summary functionalities in particular column.

The following code example describes the above behavior.


{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" allowPaging="true" [pageSettings]="pageSettings">
    <e-columns>
        <e-column headerText="Photo">
             <template e-template let-data>
                <div *ngIf="data.EmployeeID">
                <img style="width: 75px; height: 70px" [attr.src]="'app/Content/images/grid/Employees/' + data.EmployeeID + '.png' " [alt]="data.EmployeeID" />
                </div>
            </template>
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

![](columns_images/columns_img1.png)