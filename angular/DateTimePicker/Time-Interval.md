---
layout: post
title: Time-Interval
description: time interval
platform: Angular
control: DateTimePicker
documentation: ug
---

# Time Interval

You can set time interval between two adjacent time values in the time popup manually using the **interval** property. By default the value of the **interval** property is 30 minutes. Setting this value as 60 is considered as 1 hour. Sometimes you need to update for every hour work log reports. In that case to select time from time popup window with 1 hour interval to update the every 1 hour report you can use **interval** option by setting time interval value as “60 minutes”.

Add the following code in your **HTML** page.



{% highlight html %}
  
    <div align="center">
    <input type="text" id="dateTime" ej-datetimepicker width='200' [interval]="interval" [(ngModel)]="value">
    </div>
                   
{% endhighlight %}


{% highlight html %}
  
import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html'
})
export class DefaultComponent {
    value: any;
    interval: number;
    constructor() {
        this.value = Date();
        this.interval = 60;
    }
}


{% endhighlight %}

![](/DateTimePicker/Time-Interval_images/Time-Interval_img1.png)

