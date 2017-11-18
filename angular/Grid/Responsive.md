---
layout: post
title: Responsive with Grid widget for Syncfusion Essential JS
description: How to set the grid, responsive to screen resolutions
platform: Angular
control: Grid
documentation: ug
api: /api/Angular/ejgrid
---
# Responsive

The grid control has support for responsive behavior based on client browser's width and height. To enable responsive, [`isResponsive`](https://help.syncfusion.com/api/js/ejgrid#members:isresponsive "isResponsive") property should be true. There are three modes of responsive layout is available in grid based on client width. They are.

* Mobile(<321px) * tablet (321px to 800px)
                 * desktop(>
    800px)

    N> The following features are not supported by Grid's Responsive
    N> 1. Virtual Scrolling
    N> 2. Frozen Rows and Frozen Columns
    N> 3. Hierarchy
    N> 4. Detail template

    ## Mobile Layout

    If client width is less than 321px, the grid will render in mobile mode. In which, you can see that grid user interface is customized and redesigned for best view in small screens. The customized features includes responsive row rendering, filtering, sorting, searching and editing.

    ### Responsive Row

    Enabling Responsive row makes the Grid to render the record values in vertical order which removes the need for horizontal scrolling to view complete record details. It can be enabled by defining [`enableResponsiveRow`](https://help.syncfusion.com/api/js/ejgrid#members:enableresponsiverow "enableResponsiveRow") property as `true`.

    {% highlight html %}

             <ej-grid [allowPaging]="true" [dataSource]="gridData" [isResPonsive]="true" [enableResponsiveRow]="true" [pageSettings]="pagesettings">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID"></e-column>
                     <e-column field="ShipCity" headertext="Ship City" width="100"></e-column>
                     <e-column field="Freight" headertext="Freight" format="{0:C}"></e-column>
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
        public pagesettings;
        constructor()
        {
             //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           this.gridData = window.gridData;
           this.pagesettings = { pageCount: 3, pageSize: 7 },            
        }
    }

    {% endhighlight %}

    ![](Responsive_images/Responsive_img1.png)


    W> IE8 and IE9 does not support responsive row. `ejgrid.responsive.css` should be referred to display Responsive Row.

    ### Customized Features

    The customized layout for filtering, sorting, searching and CRUD operations in mobile device can be seen following screen shots.

    ![](Responsive_images/Responsive_img2.png)
    {:caption}
    Responsive row with filtering , sorting and searching

    ![](Responsive_images/Responsive_img3.png)

    {:caption}
    CRUD in mobile layout

    ![](Responsive_images/Responsive_img4.png)

    {:caption}
    Filtering in mobile layout

    ![](Responsive_images/Responsive_img5.png)
    {:caption}

    Filtering in mobile layout

    ![](Responsive_images/Responsive_img6.png)

    {:caption}
    Sorting in mobile layout

    ![](Responsive_images/Responsive_img7.png)
    {:caption}

    Searching in mobile layout

    {% highlight html %}
    
             <ej-grid [allowPaging]="true" [dataSource]="gridData" [isResponsive]="true" [enableResponsiveRow]="true" [pageSettings]="pagesettings" [editSettings]="editSettings" [toolbarSettings]="toolbarsettings" [allowFiltering]="true" [allowSorting]="true" [allowSearching]="true" [allowMultiSorting]="true" [filterSettings]="filtersettings">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID" [isPrimaryKey]="true" width="80" textalign="right"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID" width="100"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID" edittype="dropdownedit" textalign="right"></e-column>
                     <e-column field="ShipCity" headertext="Ship City" width="120" edittype="dropdownedit"></e-column>
                     <e-column field="Freight" headertext="Freight" format="{0:C}" width="120" edittype="numericedit"></e-column>
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
         public gridData: any;
         public pagesettings;
         public editSettings;
         public toolbarsettings;
         public filtersettings;
         constructor() {
             this.gridData = window.gridData;
             this.pagesettings = { pageCount: 3, pageSize: 7 },
             this.editSettings = {allowAdding: true,allowDeleting: true,allowEditing: true},
             this.toolbarsettings = {showToolbar: true, toolbarItems: ["add", "edit", "delete", "update", "cancel", "search"]
             },
             this.filtersettings = {filterType: "menu"},
         }
    }

    {% endhighlight %}

    ## Tablet Layout

    If the client width is between 321px and 800px, then the grid will render in tablet mode. Also it has customized filtering design to match tablet screen size.

    {% highlight html %}
    
             <ej-grid [allowPaging]="true" [dataSource]="gridData" [isResponsive]="true" [pageSettings]="pagesettings" [allowFiltering]="true" [filterSettings]="filtersettings">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID" [isPrimaryKey]="true" width="90" textalign="right"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID" width="100"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID" textalign="right" width="90"></e-column>
                     <e-column field="ShipCity" headertext="Ship City" width="120"></e-column>
                     <e-column field="Freight" headertext="Freight" format="{0:C}" width="80"></e-column>
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
       public gridData: any;
       public pagesettings;
       public filtersettings;
       constructor() {
             this.gridData = window.gridData;
             this.pagesettings = { pageCount: 3, pageSize: 8 },
             this.filtersettings = {filterType: "menu"},
       }
    }

    {% endhighlight %}

    ![](Responsive_images/Responsive_img8.png)
    {:caption}

    Default tab layout

    ![](Responsive_images/Responsive_img9.png)

    {:caption}
    Filtering design in tab layout.

    ## Width

    By default, the grid is adaptable to its parent container. It can adjust its width of columns based on parent container width. You can also assign `width` of [`columns`](https://help.syncfusion.com/api/js/ejgrid#members:columns "columns") in percentage.

    {% highlight html %}
    
             <ej-grid [dataSource]="gridData">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID" [isPrimaryKey]="true" width="10%" textalign="right"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID" width="15%"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID" textalign="right" width="10%"></e-column>
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
       public gridData: any;           
       constructor() {
             this.gridData = window.gridData;
       }
     }

   {% endhighlight %}

    I>  [`allowScrolling`](https://help.syncfusion.com/api/js/ejgrid#members:allowscrolling "allowScrolling") should be false while defining width in percentage.

    ## Min Width

    Min Width is used to maintain minimum width for the Grid. To enable Min Width, [`minWidth`](https://help.syncfusion.com/api/js/ejgrid#members:minwidth "minWidth") should be defined. If the grid width is less than [`minWidth`](https://help.syncfusion.com/api/js/ejgrid#members:minwidth "minWidth") then the scrollbar will be displayed to maintain minimum width.

    {% highlight html %}
    
             <ej-grid [datasource]="gridData" [minWidth]="700" [allowPaging]="true">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID" [isPrimaryKey]="true" width="90" textalign="right"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID" width="100"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID" textalign="right" width="90" textalign="right"></e-column>
                     <e-column field="ShipCity" headertext="Ship City" width="120"></e-column>
                     <e-column field="Freight" headertext="Freight" format="{0:C}" width="110"></e-column>
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
       public gridData: any;
       constructor() {
          this.gridData = window.gridData;
       }
    }

    {% endhighlight %}

    ![](Responsive_images/Responsive_img10.png)


    MinWidth set to Grid

    N> We can render the Grid with height responsive by setting the scrollSettings `height`as `100%`. If the grid height is greater than its parent container's height then the vertical scrollbar will be displayed to view the content.

    ## Priority for Columns

    Priority makes column to be visible or hidden based on the `priority` value and browser's width to best accommodate the possible columns. To enable `priority` for `columns`, `priority` needs to be defined in columns collection. These Priority values are from one to six.

    {% highlight html %}
    
             <ej-grid [dataSource]="gridData" [allowPaging]="true">

                 <e-columns>
                     <e-column field="OrderID" headertext="Order ID" [isPrimaryKey]="true" width="90" textalign="right" priority="1"></e-column>
                     <e-column field="CustomerID" headertext="Customer ID" width="100" priority="2"></e-column>
                     <e-column field="EmployeeID" headertext="Employee ID" textalign="right" width="90" textalign="right" priority="3"></e-column>
                     <e-column field="ShipCity" headertext="Ship City" width="120" priority="4"></e-column>
                     <e-column field="Freight" headertext="Freight" format="{0:C}" width="110" priority="5"></e-column>
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
       public gridData: any;
       constructor() {
           this.gridData = window.gridData;
       }
    }

    {% endhighlight %}

    I> `ejgrid.responsive.css` should be referred.


