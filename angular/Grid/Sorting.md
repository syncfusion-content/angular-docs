---
layout: post
title: Sorting in Angular Grid Control | Syncfusion
description: Learn here all about Sorting support in Syncfusion Essential Angular Grid control, its elements, and more.
platform: Angular
control: Grid
documentation: ug
api: /api/js/ejgrid
--- 
# Sorting in Essential Angular Grid

The Grid control has support to sort data bound columns in ascending or descending order. This can be achieved by setting [`allowSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowsorting "allowSorting") property as `true`. 

To dynamically sort a particular column, click on its column header. The order switch between ascending and descending each time you click a column header for sorting.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowSorting]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
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

![Angular Grid sorting](sorting_images/sorting_img1.png)


## Initial Sorting

Through `sortedColumns` property of [`sortSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:sortsettings "sortSettings"), you can sort the columns while initializing the grid itself. You need to specify the [`field`](https://help.syncfusion.com/api/angular/ejgrid#members:sortsettings-sortedcolumns-field "field") (column) name and [`direction`](https://help.syncfusion.com/api/angular/ejgrid#members:sortsettings-sortedcolumns-direction "direction") in the `sortedColumns`.

N> 1. For [`direction`](https://help.syncfusion.com/api/angular/ejgrid#members:sortsettings-sortedcolumns-direction "direction") property you can assign either `string` value ("descending") or `enum` value (`ej.sortOrder.Descending`). 
N> 2. You can add multiple columns in `sortedColumns` for multi column sorting while initializing the grid itself.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowSorting]="true" [sortSettings]="sortSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
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
    public sortSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
        this.sortSettings = { sortedColumns: [{ field: "EmployeeID", direction: "descending" }] };
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Angular Grid initial sorting](sorting_images/sorting_img2.png)


## Multi-Column Sorting

Sort multiple columns in grid by setting [`allowMultiSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowmultisorting "allowMultiSorting") property as true. The sorting order is displayed in the header while doing multi sorting.

You can sort more than one column by pressing "Ctrl key + mouse left click" on the column header. To clear sorting for particular column, press "Shift + mouse left click". 

N> [`allowSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowsorting "allowSorting") must be true while enabling multi sort.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowSorting]="true" [allowMultiSorting]="true" [sortSettings]="sortSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
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
    public sortSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
        this.sortSettings = { sortedColumns: [{ field: "EmployeeID", direction: "descending" }, { field: "CustomerID" }] };
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![Angular Grid multi column sorting](sorting_images/sorting_img3.png)


## Stable sorting

For sorting, grid uses default browser's sort function for better performance. On multi column sorting in some browsers like chrome, the records order will be different due to unstable implementation of sorting algorithm in it. 

To resolve this, you need to set `ej.support.stableSort` as `false`.

This will tell the "DataManager" to use custom sort function for sorting data. 

Please refer the [link](https://en.wikipedia.org/wiki/Category:Stable_sorts# "link"), to know more information about stable sort.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowSorting]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
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
    public sortSettings;
    constructor()
    {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = window.gridData;
    },
    ngAfterViewInit(){
        ej.support.stableSort = false;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![Angular Grid stable sorting](sorting_images/sorting_img4.png)


## Touch options

While using Grid in a touch device, you have an option for multi sorting in single tap on the grid header. By tapping on the grid header, it will show the toggle button in small popup with sort icon. Now tap the button to enable multi sorting in single tap.

Again if you tap the popup symbol, then the single tap multi sorting will be disabled. 

N> [`allowMultiSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowmultisorting "allowMultiSorting") and [`allowSorting`](https://help.syncfusion.com/api/angular/ejgrid#members:allowsorting "allowSorting") should be `true` then only the popup will be shown.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid id="Grid" [dataSource]="gridData" [allowPaging]="true" [allowSorting]="true" [allowMultiSorting]="true">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>
        <e-column field="ShipCountry"></e-column>
        <e-column field="Freight"></e-column>
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

![Angular Grid touch options](sorting_images/sorting_img5.png)

N> To get the sorted data of the grid after sorting a column you can refer the [`How To`](https://help.syncfusion.com/angular/grid/how-to "Getting Datasource of Grid in Sorted Order").
