---
layout: post
title: scrolling with Grid widget for Syncfusion Essential Angular-2
description: How to enable scrolling and its functionalities
platform: Angular
control: Grid
documentation: ug
api: /api/angular/ejgrid
--- 
# Scrolling

Scrolling can be enabled by setting [`allowScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:allowscrolling "allowScrolling") as `true`. The height and width can be set to grid by using the properties [`scrollSettings.height`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-height"scrollSettings.height") and [`scrollSettings.width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width "scrollSettings.width") respectively. 

N> If [`width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width "width") and [`height`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-height "height") is not defined in the [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") property then the horizontal and vertical scrollbar is enabled, only when the grid width exceeds the browser width.

The height and width can be set in percentage and pixel. The default value for [`height`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-height "height") and [`width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width "width") in [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") is 0 and `auto` respectively.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
   <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: 400, height: 300 };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img1.png)


## Set width and height in pixel 	

To specify the [`scrollSettings.width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width"scrollSettings.width") and [`scrollSettings.height`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-height "scrollSettings.height") in pixel, by set the pixel value as integer. 

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}

import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: 500, height: 300 };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img2.png)


## Set width and height in percentage

To specify the [`scrollSettings.width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width "scrollSettings.width") and [`scrollSettings.height`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-height "scrollSettings.height") in percentage, by set the percentage value as string.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: "70%", height: "25%" };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img3.png)


## Set width as auto

Specify [`width`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-width "width") property of [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") as auto, then the scrollbar is rendered only when the grid width exceeds the browser window width.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: "auto", height: 300  };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img4.png)


## Frozen columns

Specify [`frozenColumns`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozencolumns "frozenColumns") property of [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") to freeze the columns(upto the specified frozenColumns value) at the time of scrolling. Horizontal scrollbar must be enabling while specifying [`frozenColumns`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozencolumns "frozenColumns") then only you can scroll and see the remaining columns with freeze pane.

N> [`allowScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:allowscrolling "allowScrolling") must be `true` while specifying [`frozenColumns`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozencolumns "frozenColumns").

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings =  { width: 550, height: 300, frozenColumns: 2 };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img5.png)


### Freeze particular columns:

To freeze selected columns in grid at the time of scrolling, by set [`isFrozen`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-isfrozen "isFrozen") property of columns as `true`. [`isFrozen`](https://help.syncfusion.com/api/angular/ejgrid#members:columns-isfrozen "isFrozen") columns are rendered first in the grid even the columns index is different while declaring the [`columns`](https://help.syncfusion.com/api/angular/ejgrid#members:columns "columns").

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>  
        <e-column field="Freight" [isFrozen]="true"></e-column> 
        <e-column field="OrderDate" format= "{0:dd/MM/yyyy}"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry" [isFrozen]="true" width=100></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
    </e-columns>
</ej-grid>
{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    
    constructor() {

         this.scrollSettings =  { width: 550, height: 300, frozenColumns: 2 };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img6.png)


### Frozen Columns alert Messages:

1. If [`allowScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:allowscrolling "allowScrolling") is false while using [`frozenColumns`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozencolumns "frozenColumns") then "Enable [`allowScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:allowscrolling "allowScrolling") while using frozen Columns" alert message is thrown.
2. If [`frozenColumns`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozencolumns "frozenColumns") is specified out of the grid column view then "Frozen columns should be in grid view area" alert message is thrown.
3. Frozen Rows and Columns are not supported the following features
 Grouping
 Row Template
 Detail Template
 Hierarchy Grid 
 Batch Editing
 Virtual Scrolling

If any one of the above feature is enabled along with Frozen Rows and Columns, then "Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template, Hierarchy Grid and Batch Editing" alert message is thrown.

## Frozen Rows

Specify [`frozenRows`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozenrows "frozenRows") property of [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") to freeze rows(upto the specified frozenRows value) at the time of scrolling. Vertical scrollbar must be enabling while specifying [`frozenRows`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozenrows "frozenRows") then only you can scroll and see the remaining rows with freeze pane.

N> [`allowScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:allowscrolling "allowScrolling") must be `true` while specifying [`frozenRows`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-frozenrows "frozenRows").

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

          this.scrollSettings = { width: 550, height: 300, frozenRows: 4 };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img7.png)


## Touch scroll

In [touch](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-enabletouchscrolll "touch") supported devices you can scroll and show the content by swipe left, right, top and bottom. Disable touch scroll by setting [`enableTouchScroll`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-enabletouchscroll "enableTouchScroll") property of [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings "scrollSettings") as `false`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: 550, height: 300, enableTouchScroll: false };
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        this.gridData = (window as any).gridData;
    }
}
{% endhighlight %}

## Virtual Scrolling

The virtual scrolling support allows you to load data that you require (load data based on page size) without buffering the entire huge database. To enable virtual scrolling by setting [`allowVirtualScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-allowvirtualscrolling) property of [`scrollSettings`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings) as `true`. 

We also have an enhanced virtual scrolling feature with an improvised virtual scrolling performance. To enable improvised virtual scrolling feature by setting [`enableVirtualization`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-enablevirtualization) property of `scrollSettings` as true and it doesn't requires [`allowVirtualScrolling`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-allowvirtualscrolling) to be enabled. It allows you to load the grid with data while scrolling. Some of the relevant functionalities of this are,

1.	White space will not be appeared in the Grid. 
2.	Improved page rendering performance. 
3.  It can render nearly 500 thousand records.

It supports two mode of virtualization. They are,

1. Normal Mode
2. Continuous Mode

N> Enhanced Virtual Scrolling supports only Normal mode
N> The following features are not supported by virtual scrolling 
N> 1. Grouping
N> 2. Frozen Rows 
N> 3. Cell merging 
N> 4. Detail template 
N> 5. Hierarchy
N> 6. Editing

### Normal Mode:

It allows you to load the grid with data while scrolling. This can be achieved by setting [`virtualScrollMode`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-virtualscrollmodee "virtualScrollMode") as `normal`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

         this.scrollSettings = { width: 550, height: 300, allowVirtualScrolling: true, virtualScrollMode: "normal" };
        this.gridData = ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Orders");
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img8.png)

#### Enhanced Virtual Scrolling:

In order to enable this, you need to set the [`enableVirtualization`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-enablevirtualization) property of the `scrollSettings` as true.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

        this.scrollSettings = { width: 550, height: 300, enableVirtualization: true },
        this.gridData = ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Orders");
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img10.png)


### Continuous Mode:

In Continuous mode, the data is loaded in grid when the scrollbar reaches the end.  You can enable the continuous mode by setting the [`virtualScrollMode`](https://help.syncfusion.com/api/angular/ejgrid#members:scrollsettings-virtualscrollmode "virtualScrollMode") property as `continuous`.

The following code example describes the above behavior.

{% highlight html %}
<ej-grid  id="Grid" [dataSource]="gridData" [allowScrolling]="true" [scrollSettings]="scrollSettings">
    <e-columns>
        <e-column field="OrderID"></e-column>
        <e-column field="EmployeeID"></e-column>
        <e-column field="CustomerID"></e-column>        
        <e-column field="ShipCity"></e-column>     
        <e-column field="ShipCountry"></e-column>
        <e-column field="ShipAddress"></e-column>
        <e-column field="ShipPostalCode"></e-column>
        <e-column field="Freight"></e-column>  
      </e-columns>
</ej-grid>

{% endhighlight %}

{% highlight javascript %}
import { Component } from '@angular/core';


@Component({
    selector: 'ej-app',
    templateUrl: 'src/grid/grid.component.html',
})
export class GridComponent {
    public gridData: any;
    public scrollSettings;
    

    constructor() {

        this.scrollSettings = { width: 550, height: 300, allowVirtualScrolling: true, virtualScrollMode: "continuous" },
        this.gridData = ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Orders");
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](scrolling_images/scrolling_img9.png)
