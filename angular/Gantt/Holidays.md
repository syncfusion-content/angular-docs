---
layout: post
title: Holidays
description: holidays
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Holidays

Holidays in Gantt control is used to highlight the non-working days in Gantt control and it can be initialized with Gantt control by using the following code example.

{% highlight javascript %}

<ej-gantt
    //...
    [holidays]= "holidays">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public holidays: any;
    constructor() {

        this.holidays = [{
            day: "2/03/2014",
            label: " Public holiday",
            background: "yellowgreen "
        }]
    }
}

{% endhighlight %}

The following screenshot shows the output of Holidays in Gantt control.

![](Holidays_images/Holidays_img1.png)

