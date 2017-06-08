---
layout: post
title: Columns with Grid widget for Syncfusion Essential Angular-2
description: How to define the columns and its features
platform: Angular
control: Grid
documentation: ug
api: /api/angular2/grid
--- 
# Columns

Column definitions are used as the `dataSource` schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on the column definitions. The `field` property of the `e-column` is necessary to map the datasource values in Grid columns.

N> 1. If the column with `field` is not in the datasource, then the column values will be displayed as empty.
N> 2. If the `field` name contains "dot" operator then it is considered as complex binding.

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