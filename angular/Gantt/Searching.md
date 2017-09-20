---
layout: post
title: Searching
description: searching
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Searching

The Gantt control for JavaScript has built-in support for searching any content in Gantt.

### Searching for Content Columns

In Gantt we can search the content using the JavaScript method searchItem with search key as parameter. Also, we can integrate the search text box in Gantt toolbar, by adding search toolbar item in toolbarSetting.toolbarItems property.

The following code example shows you how to add search option in Gantt toolbar.

{% highlight javascript %}

<ej-gantt id="GanttControl" [toolbarSettings]="toolbarSettings"
    //...>
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

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
                ej.Gantt.ToolbarItems.Search, //TO FIND THE TASK
            ],
        };
    }
}

{% endhighlight %}

The following screenshot shows the output of searching for string in Gantt control.

![](Searching_images/Searching_img1.png)

