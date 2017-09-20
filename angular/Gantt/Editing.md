---
layout: post
title: Editing
description: editing
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Editing

The Gantt control provides built-in support to add, insert and update the tasks. The following are the types of editing available in Gantt,

* Cell Editing
* Normal Editing
* Taskbar Editing
* Predecessor Editing

## Cell Editing

Update the task details through grid cell editing by setting editMode as `cellEditing`.

The following code example shows you how to enable `cellEditing` in Gantt control.

{% highlight javascript %}

<ej-gantt
    //...
    [editSettings]= "editSettings">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public editSettings: any;
    constructor() {
        this.editSettings = {
            allowEditing: true,
            editMode: "cellEditing"
        }
    }
}

{% endhighlight %}

The output of Gantt with cellEditing is as follows.

![](Editing_images/Editing_img1.png)

## Normal Editing

Update the task details through edit dialog by setting `editMode` as `normal`.

The following code example shows you how to enable normal editing in Gantt control.

{% highlight javascript %}

<ej-gantt
    //...
    [editSettings]= "editSettings">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public editSettings: any;
    constructor() {
        this.editSettings = {
            allowEditing: true,
            editMode: "normal"
        }
    }
}

{% endhighlight %}

The following screenshot shows the output of `normal` editing.

![](Editing_images/Editing_img2.png)

## Taskbar Editing

Update the task details by interactions such as resizing and dragging the taskbar. The following code example shows you how to enable taskbar resizing in Gantt control.

{% highlight javascript %}

<ej-gantt
    //...
    [allowGanttChartEditing]= "true">
</ej-gantt>

{% endhighlight %}

You can also enable or disable the progressbar resizing by setting 'enableProgressbarResizing'. The following code example shows you to disable this property.

{% highlight javascript %}

<ej-gantt
    //...
    [enableProgressBarResizing]= "true">
</ej-gantt>

{% endhighlight %}

## Predecessor Editing

Update the predecessor details of a task using mouse interactions. The following code example shows how to enable predecessor editing.

{% highlight javascript %}

<ej-gantt
    //...
    [dataSource]= "data"
    [allowGanttChartEditing]="true"
    predecessorMapping= "predecessor">
</ej-gantt>

{% endhighlight %}

The following screen shot shows the predecessor editing in Gantt control.

![](Editing_images/Editing_img3.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/editing) here to view the online demo sample for editing in Gantt.