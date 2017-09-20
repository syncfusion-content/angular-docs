---
layout: post
title: Change-Weekend
description: change weekend/Non-working day
platform: Angular
control: Gantt
documentation: ug
---

# Change Week end/Non-working day
Non-working days/weekend are used to represent the non-productive days in a project. It is possible to change the non-working days in a week using the `workWeek` property in Gantt.

By default, Saturdays and Sundays are considered as non-working days/weekend in a project. 

The following code example explains how to change weekend/non-working days

{% highlight javascript %}

<ej-gantt id="GanttControl"
    [workWeek]= "workWeek">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public workWeek: any;
    constructor() {
        this.workWeek = ["Sunday","Monday","Tuesday","Wednesday","Thursday"]
    }
}

{% endhighlight %}

The above code example makes Fridays and Saturdays as non-working days in a week.

![](How-to/Change-Workweek_images/Change_Workweek_img1.png)

The above screen shot will be displayed after changing the non-working days in Gantt.
{:.caption}