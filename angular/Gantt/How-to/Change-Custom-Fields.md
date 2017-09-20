---
layout: post
title: Change-Weekend
description: Display custom fields in General tab
platform: Angular
control: Gantt
documentation: ug
---

# Display custom fields in general tab
Gantt add and edit dialogs groups the data sources fields in five different tabs such as `General`, `Predecessors`, `Resources`, `Custom Fields` and `Notes`.

![](How-to/Change-Custom-Fields_images/dialog_all_tab.png)

The custom fields are usually displayed in `Custom Fields` tab, but it is also possible to display the custom fields in general tab using `displayInGeneralTab` property in Gantt. By default, its value is false.
The following code example explains how to display custom fields in general tab

{% highlight javascript %}

<ej-gantt id="GanttControl"
    [addDialogFields]= "addDialogFields"
    [editDialogFields]="editDialogFields">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public editDialogFields: any;
    public addDialogFields: any;    
    constructor() {
        this.editDialogFields = [{ field: "taskID" }, { field: "taskName" }, { field: "startDate" }, { field: "endDate" }, { field: "duration" }, { field: "notes" }, { field: "expectedDate", displayInGeneralTab: true}]
        this.addDialogFields = [{ field: "taskID" }, { field: "taskName" }, { field: "startDate" }, { field: "endDate" }, { field: "duration" }, { field: "notes" }, { field: "expectedDate", displayInGeneralTab: true }]
    }
}

{% endhighlight %}

![](How-to/Change-Custom-Fields_images/dialog_specific_tab.png)

The above screen shot shows custom column field “Expected Date” displayed in General tab.
{:.caption}