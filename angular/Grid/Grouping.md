---
layout: post
title: Grouping with Grid widget for Syncfusion Essential Angular-2
description: How to enable grouping and its functionalities
platform: Angular
control: Grid
documentation: ug
api: /api/Angular/grid
--- 
# Grouping

The Grid control has options to group the records based on the required column. When grouping is applied, grouped records are organized into a hierarchical structure to facilitate easier expand and collapse of records. To enable grouping, set [`allowGrouping`](https://help.syncfusion.com/api/js/ejgrid#members:allowgrouping "allowGrouping") property as `true`.

Columns can be grouped by simply dragging the column header and drop on the group drop area or simply click the group button which is displayed in the column. By default, sorting is done while grouping the column.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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

![](Grouping_images/Grouping_img1.png)


## Initial Grouping

While initializing the grid itself, there is an option to group the column and display it in a hierarchical structure. To enable initial grouping, set array of column's [`field`](https://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name to be grouped to [`groupSettings.groupedColumns`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-groupedcolumns "groupSettings.groupedColumns") property. Define the [`field`](https://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name in the array format.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { groupedColumns: ["ShipCountry"] };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img2.png)


## Multi-Column Grouping

Group multiple columns by simply drag and drop the columns one by one from column header into group drop area.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { groupedColumns: ["ShipCountry","CustomerID"] };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img3.png)


## Group buttons

To do grouping easily without doing drag and drop column header by setting [`showToggleButton`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-showtogglebutton "showToggleButton") property of [`groupSettings`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings "groupSettings") as `true`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { showToggleButton: true };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img4.png)


## Hide Ungroup button

Hide ungroup button from grouped columns which is in the group drop area by setting the [`showUngroupButton`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-showungroupbutton "showUngroupButton") property of [`groupSettings`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings "groupSettings") as `false`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { showUngroupButton: false };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img5.png)


## Hide Grouped Column

While grouping a particular column, there is an option to hide the grouped columns from grid. To enable hide grouped column option, set [`showGroupedColumn`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-showgroupedcolumn "showGroupedColumn") property of [`groupSettings`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings "groupSettings") as `false`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { showGroupedColumn: false };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img6.png)


## AutoSize Drop Area

Drag any column header and move it to the group drop area, then its portion expands smoothly. Stop this animation by setting [`enableDropAreaAutoSizing`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-enabledropareaautosizing "enableDropAreaAutoSizing") property of [`groupSettings`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings "groupSettings") as `false`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { enableDropAreaAutoSizing: false };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img7.png)


## Hide Drop area

To avoid ungrouping or further grouping of a column after an initial column grouping by setting [`showDropArea`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-showdroparea "showDropArea") property of [`groupSettings`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings "groupSettings") as `false`.

The following code example describes the above behavior.

{% highlight html %}

<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowGrouping]="true" [groupSettings]="groupSettings" > 
    <e-columns>
        <e-column field="OrderID" headerText="OrderID" width="75"></e-column>
        <e-column field="EmployeeID" headerText="EmployeeID"  width="80"></e-column>
        <e-column field="CustomerID" headerText="CustomerID" width="80"></e-column>
        <e-column field="ShipCountry" headerText="ShipCountry" width="90"></e-column>
        <e-column field="Freight" headerText="Freight" width="90" ></e-column>
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
		public groupSettings;
        constructor()
        {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
		   this.groupSettings = { showDropArea: false, groupedColumns: ["ShipCountry"] };
		}
     }

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Grouping_images/Grouping_img8.png)