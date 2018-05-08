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
