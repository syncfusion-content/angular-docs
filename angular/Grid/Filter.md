---
layout: post
title: Filtering with Grid widget for Syncfusion Essential Angular-2
description: How to enable filtering and its functionalities
platform: Angular
control: Grid
documentation: ug
api: /api/Angular/grid
--- 
# Filtering

Filtering helps to view particular or related records from dataSource which meets a given filtering criteria. To enable filter, set [`allowFiltering`](https://help.syncfusion.com/api/angular/ejgrid#members:allowfiltering "allowFiltering") as `true`. 

The Grid supports three types of filter, they are

1. Filter bar
2. Menu 
3. Excel

And also four types of filter menu is available in all filter types, they are

1. String 
2. Numeric 
3. Date 
4. Boolean

The corresponding filter menu is opened based on the column type.

N> 1. Need to specify the [`type`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-type "type") of column, when first record data value is empty or null otherwise the filter menu is not opened. 
N> 2. The default filter type is Filter bar, when [`allowFiltering`](https://help.syncfusion.com/api/angular/ejgrid#members:allowfiltering "allowFiltering") is enabled and [`filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterType") is not set.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img1.png)


## Menu filter

You can enable menu filter by setting [`filterSettings.filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterSettings.filterType") property as `menu`. 

There is an option to show or hide the additional filter options in the menu by setting [`showPredicate`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-showpredicate "showPredicate") of [`filterSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings "filterSettings") property as `true` or `false` respectively.

N> For [`filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterType") property you can assign either `string` value ("menu") or `enum` value (`ej.Grid.FilterType.Menu`).

The following code example describes the above behavior.


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="OrderDate" headerText="OrderDate"  format="{0:dd/MM/yyyy}"></e-column>
        <e-column field="Verified" headerText="Verified" ></e-column>
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
        public filterType;
        constructor()
        { 
            //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={filterType:"menu"};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img2.png)
{:caption}
Numeric Filter

![](filtering_images/filtering_img3.png)
{:caption}
String Filter

![](filtering_images/filtering_img4.png)
{:caption}
Date Filter

![](filtering_images/filtering_img5.png)

Boolean Filter

## Excel-like filter

You can enable excel menu by setting [`filterSettings.filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterSettings.filterType") as `excel`. The excel menu contains an option such as Sorting, Clear filter, submenu for advanced filtering.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID" ></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        public filterType;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={filterType:"excel"};
         }
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img6.png)


### Checkbox list generation:

By default, the checkbox list is generated from distinct values of the filter column from dataSource which gives an option to search and select the required items.

Also on checkbox list generation, if the number of distinct values are greater than 1000, then the excel filter will display only first 1000 values to ensure the best performance on rendering and searching. However this limit has been customized according to your requirement by setting [`filterSettings.maxFilterChoices`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-maxfilterchoices "filterSettings.maxFilterChoices") property with required limit in integer.

N> 1. Using excel filter events you can change the dataSource of the checkbox list. 
N> 2. `ej.Query` of checkbox list can also be changed using excel filter events.

The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        public filterType;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={filterType:"excel",maxFilterChoices:"4"};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img7.png)


### Add current selection to filter checkbox:

When filtering is done multiple times on the same column then the previously filtered values on the column will be cleared. So, to retain the old values `Add current selection to filter` checkbox can be used which is displayed when data is searched in the search bar.

The following image describes the above mentioned behavior.

![](filtering_images/filtering_img12.png)


### Case Sensitivity

To perform filter operation with case sensitive in excel styled filter menu mode by setting [`enableCaseSensitivity`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-enablecasesensitivity "enableCaseSensitivity") as `true`.

The following code example describes the above behavior.


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        public gridData
        public filterType;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={filterType:"excel",enableCaseSensitivity : true};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img8.png)


## Filter bar

[Filter bar](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "Filter bar") row is located next to column header of grid. You can filter the records with different expressions depending upon the column type. To show the filter bar row, set the [`filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterType") as `filterbar`.

List of Filter bar Expressions:

You can enter the below filter expressions manually in the filter bar.

 <table>
        <tr>
            <th>
                Expression
            </th>
            <th>
                Example
            </th>
            <th>
                Description
            </th>
            <th>
                Column Type
            </th>
        </tr>
        <tr>
            <td>
                =
            </td>
            <td>
                = value
            </td>
            <td>
                equal
            </td>
            <td rowspan="5">
                Numeric
            </td>
        </tr>
        <tr>
            <td>
                != 
            </td>
            <td>
                != value
            </td>
            <td>
                notequal
            </td>
           
        </tr>
        <tr>
            <td>
                >
            </td>
            <td>
                > value
            </td>
            <td>
                greaterthan
            </td>
          
        </tr>
        <tr>
            <td>
                <
            </td>
            <td>
                < value
            </td>
            <td>
                lessthan
            </td>
          
        </tr>
        <tr>
            <td>
                >=
            </td>
            <td>
                >= value
            </td>
            <td>
                greaterthanorequal
            </td>
           >
        </tr>
        <tr>
            <td>
                <=
            </td>
            <td>
                <= value
            </td>
            <td>
                lessthanorequal
            </td>
           
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `startswith` operator will be used for string filter
            </td>
            <td>
                String
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Date filter 
            </td>
            <td>
                Date
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Boolean filter
            </td>
            <td>
                Boolean
            </td>
        </tr>
    </table>
	
	
The following code example describes the above behavior.

{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        public filterType;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={filterType:"filterbar"};
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img9.png)


Filter bar modes:

This specifies the grid to start the filter action while typing in the filter bar or after pressing the enter key based on [`filterBarMode`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filterbarmode "filterBarMode").There are two types of [`filterBarMode`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filterbarmode "filterBarMode"), they are

1. OnEnter
2. Immediate

N> For [`filterBarMode`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filterbarmode "filterBarMode") property you can assign either `string` value (onenter) or `enum` value (`ej.Grid.FilterBarMode.OnEnter`).

Filter bar message:

The filter bar message is supported only for the [`filterType`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-filtertype "filterType") as "filterbar". The filtered data with column name is displayed in the grid pager itself. By default [`showFilterBarMessage`](https://help.syncfusion.com/api/angular/ejgrid#members:filtersettings-showfilterbarstatus "showFilterBarMessage") is true.

The following code example describes the above behavior.


{% highlight html %}

 <ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" [filterSettings]="filterType" >
    <e-columns>
        <e-column field="OrderID"  headerText="OrderID"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"></e-column>
        <e-column field="CustomerID" headerText="CustomerID"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry"></e-column>
        <e-column field="Freight" headerText="Freight"></e-column>
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
        public filterType;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
             this.gridData = window.gridData;
             this.filterType={ showFilterBarStatus: true };
         }
     }

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img10.png)


## Filter Operators

The grid controls uses filter operators from `ej.DataManager`, which are used at the time of filtering.

List of Column type and Filter operators

<table>
        <tr>
            <th>
                Column Type
            </th>
            <th>
                Filter Operators
            </th>
        </tr>
        <tr>
            <td rowspan="6">
                Number
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
       
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                String
            </td>
            <td>
                ej.FilterOperators.startsWith
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.endsWith
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.contains
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="2">
                Boolean
            </td>
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            
            <td>
	
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="6">
                Date
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
    </table>
    
## FilterBar Template

Usually enabling allowFiltering, will create default textbox in Grid FilterBar. So, Using [`filterBarTemplate`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-filterbartemplate "filterBarTemplate") property of `columns` we can render any other controls like AutoComplete, DropDownList etc in filterbar to filter the grid data for the particular column.
It has three functions. They are    

1. `create` - It is used to create the control at time of initialize.
2. `read`   - It is used to read the Filter value selected.
3. `write`  - It is used to render the control and assign the value selected for filtering.


The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowFiltering]="true" >
    <e-columns>
        <e-column field="Order ID" headerText="OrderID" width="75"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" [filterBarTemplate]="CustomerIDFilterBarTemp" width="100"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="100"></e-column>
        <e-column field="Freight" headerText="Freight" [filterBarTemplate]="FreightFilterBarTemp" width="100" ></e-column>
        <e-column field="ShipCountry" headerText="Ship Country" width="100"></e-column>
        <e-column field="Verified" headerText="Verified" [filterBarTemplate]="VerifiedFilterBarTemp" width="90"></e-column>
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
		public CustomerIDFilterBarTemp;
        public FreightFilterBarTemp;
        public VerifiedFilterBarTemp;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.FreightFilterBarTemp = {
            write: function (args) {
                args.element.ejNumericTextbox({ width: "100%",decimalPlaces: 2, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
            },
            read: function (args) {
                this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
            }
        };
        this.CustomerIDFilterBarTemp = {
            create: function (args) {
                return "<input>"
            },
            write: function (args) {
                var data = new ej.DataManager(this.gridData).executeLocal(new ej.Query().select("CustomerID"));
                args.element.ejAutocomplete({ width: "100%", dataSource: data, enableDistinct: true, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
            },
            read: function (args) {
                this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
            }
        };
        this.VerifiedFilterBarTemp = {
            write: function (args) {
                args.element.ejCheckBox({ change: ej.proxy(args.column.filterBarTemplate.read, this, args) });
            },
            read: function (args) {
                this.filterColumn(args.column.field, "equal", args.element.parent().attr('aria-checked'), "and", true)
            }
        };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](filtering_images/filtering_img11.png)
{:caption}
After Filtering