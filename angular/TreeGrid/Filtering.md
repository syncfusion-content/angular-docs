---
layout: post
title: Filtering
description: filtering
platform: Angular
control: TreeGrid
documentation: ug
api: /api/js/ejtreegrid
---

# Filtering

Filtering helps to view specific or related records from data source which meets a given filtering criteria. To enable filtering in TreeGrid, set `allowFiltering` as `true`
TreeGrid provides support for the following filtering modes,

* Filter bar
* Menu

Also, the following filtering types are available in TreeGrid

* String
* Boolean
* Date
* Numeric
* Dropdown

The below code explains how to enable filtering in TreeGrid.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

The output of the TreeGrid with filtering enabled is as follows.

![](Filtering_images/Filtering_img1.png)

## Filtering Modes

### Filter Bar 

This is the default filtering mode in TreeGrid. It can also be enabled by setting `filterSettings.filterType` as `filterbar`. When this filtering mode is enabled, a filter row will be displayed below the column header, in which we can provide the filter query.

There are two types of actions available to initiate the filtering process in the filter bar mode,

`immediate`- Filtering action will be initiated immediately on key press, for each character being typed in the filter bar.
`onEnter` – Filtering action will be initiated only on enter key press in the filter bar.

The below code snippet explains the above behavior,

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [filterSettings]="filterSettings" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public filterSettings: any;

    constructor() {
        //...
        this.filterSettings = {
            filterType: ej.TreeGrid.FilterType.FilterBar
            filterBarMode: "onEnter"
        }
    }
}

{% endhighlight %}

The output of the filtering with filter bar enabled is as follows.

![](Filtering_images/Filtering_img2.png)

### Menu filtering
Menu filtering can be enabled by setting `filterSettings.filterType` property as `menu`. The below code snippet explains how to enable menu filtering in TreeGrid

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [filterSettings]="filterSettings" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public filterSettings: any;

    constructor() {
        //...
        this.filterSettings = {
            filterType: ej.TreeGrid.FilterType.Menu
        }
    }
}

{% endhighlight %}

The output of the filtering with filter menu enabled is as follows.

![](Filtering_images/Filtering_img3.png)

## Filtering types
By default, the filtering type for a column is inherited from the `columns.editType` property. You can also define a specific filtering type for a column using `columns.filterEditType` property.
The below code snippet explains on how to set a filtering type for a column.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [columns]="columns" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public columns: any;

    constructor() {
        //...
        this.columns = [{
                field: "taskID",
                allowFiltering: false,
            },
            {
                field: "taskName",
                editType: "stringedit",
                filterEditType: "stringedit"
            },
            {
                field: "startDate",
                editType: "datepicker",
                filterEditType: "datepicker",
                format: dateFormat
            },
            {
                field: "priority",
                editType: "dropdownedit",
                filterEditType: "dropdownedit",
                dropdownData: stageData,
                editParams: {
                    fields: {
                        text: "text",
                        value: "value"
                    },
                    showCheckbox: false
                }
            },
            {
                field: "progress",
                editType: "numericedit",
                filterEditType: "numericedit"
            }
        ],
    }
}

{% endhighlight %}

## Filter columns at initial load
It is also possible to filter one or more columns at load time by providing the field and filter query values to the `filterSettings.filteredColumns` property. The following code example explains how to filter a column on initial load.

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [filterSettings]="filterSettings" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public filterSettings: any;

    constructor() {
        //...
        this.filterSettings = {
            filteredColumns: [{
                value: "plan",
                field: "taskName",
                predicate: "and",
                operator: "startswith"
            }]
        }
    }
}

{% endhighlight %}

## Disabling filtering for a specific column 
It is possible to disable filtering for a specific column by setting `columns.allowFiltering` as `false` in the column definition.
The below code snippet explains the above behavior

{% highlight javascript %}

<ej-treegrid id="TreeGridControl" [columns]="columns" [allowFiltering]="true"
    //...>
</ej-treegrid>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public columns: any;

    constructor() {
        //...
        this.columns = [{
            field: "taskID",
            allowFiltering: false,
        }, ]
    }
}

{% endhighlight %}

The output of the filtering enabled for only one column is as follows.

![](Filtering_images/Filtering_img4.png)

[Click here](http://js.syncfusion.com/demos/web/#!/bootstrap/treegrid/columnfiltering) to find the demo sample for filtering in TreeGrid

## Filtering multiple columns dynamically

It is possible to filtering multiple columns dynamically by using the [`filterContent`](/api/js/ejtreegrid#methods:filtercontent) public method. 
The below code snippet explains how to filter mulitple columns dynamically in TreeGrid

{% highlight html %}
 
<button id="filterContent" (click)="filterContent($event)">filterContent</button>
<ej-treegrid id="TreeGridControl">
 [filterSettings]= "filterSettings"
//...
</ej-treegrid>

{% endhighlight %}


{% highlight ts %}

export class AppComponent {
    public filterSettings: any;
    constructor() {
        //...
        this.filterSettings = {
            filterType: ej.TreeGrid.FilterType.Menu,
        }
    }
    public filterContent(event) {
        var treeObj = $("#TreeGridControl").ejTreeGrid("instance");
        var predicate = ej.Predicate("taskName", ej.FilterOperators.startsWith, "Plan", true)
                        .or("taskName", ej.FilterOperators.equal, "Software Specification", true)
                        .and("progress", ej.FilterOperators.notEqual, 0, true);
        treeObj.filterContent(predicate);
    }
}
{% endhighlight %}
The output of the filtering applied for a column is as follows.

![](Filtering_images/Filtering_img5.png)