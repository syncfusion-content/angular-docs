---
layout: post
title: Searching
description: TreeGrid Searching
platform: Angular
control: TreeGrid
documentation: ug
api: /api/js/ejtreegrid
---

## Searching

The TreeGrid control has an option to search its content using toolbar search box. The toolbar search box can be enabled by using the [`toolbarSettings.toolbarItems`](/api/angular/ejtreegrid#members:toolbarsettings-toolbaritems) property. The following code example explains how to integrate search textbox in toolbar.

{% highlight html %}

    <ej-treegrid id="TreeGridControl" [toolbarSettings]="toolbarSettings"
        //...>
    </ej-treegrid>

{% endhighlight %}

{% highlight ts %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html'
})
export class AppComponent {
    public toolbarSettings: any;
    constructor() {
        //...
        this.toolbarSettings = {
            showToolbar: true,
            toolbarItems: [
                ej.TreeGrid.ToolbarItems.Search,
            ],
        }
    }
}

{% endhighlight %}

The below screenshot shows TreeGrid search with `plan` key word.
![](Searching_images/Searching_img1.png)

## Search Hierarchy Modes

The tree grid supports different types of search mode through the [`searchSettings.searchHierarchyMode`](/api/angular/ejtreegrid#members:searchsettings-searchhierarchymode) property.

The following are the types of search modes available in the tree grid.

**Parent**: This is the default search hierarchy mode in the tree grid. It displays a searched record with its parent records. If the searched records do not have any parent record, it displays only the searched record.

**Child**: Displays the searched record with its child record. If the searched records do not have any child record, it displays only the searched record.

**Both**: Displays the searched record with both its parent and child records. If the searched records do not have any parent and child records, it displays only the searched record.

**None**: Displays only the searched record.

The following code example shows how to set the `searchHierarchyMode` in the tree grid.

{% highlight html %}

    <ej-treegrid id="TreeGridControl" [searchSettings]= "searchSettings"
        //...>
    </ej-treegrid>


{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    public searchSettings: any;
    constructor() {
        this.searchSettings = {
            searchHierarchyMode: ej.TreeGrid.SearchHierarchyMode.Child,
        }
    }
}

{% endhighlight %}

The following image depicts the output of the previous code example.
![](Searching_images/SearchHierarchyModes_img1.png)

The above screenshot shows Tree Grid with `child` search mode.