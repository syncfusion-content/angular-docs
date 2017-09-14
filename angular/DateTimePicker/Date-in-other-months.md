---
layout: post
title: Date-in-other-months
description: date in other months
platform: Angular
control: DateTimePicker
documentation: ug
---

# Date in other months

**DateTimePicker** calendar can display the dates in other months at the start or end of the current month. To enable or disable the display of other month dates in the current month, you can use the property called **showOtherMonths**. By setting this property value as **“True”** you can display the dates in other months at the start or end of the current month. By default the value of this property is **“True”**. 

Consider you are going to calculate the monthly report of your company’s employee attendance. To avoid the mistake of selecting other month dates while calculating current month report, you can disable showing other month dates in the current month. You can achieve this requirement by setting **showOtherMonths** value as **“False”.**

Add the following code in your **HTML** page.


{% highlight html %}
  
    <div align="center">
    <input type="text" id="dateTime" ej-datetimepicker width='200' [showOtherMonths]="months" [(ngModel)]="value">
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
    months: boolean;
    constructor() {
        this.value = Date();
        this.months = false;
    }
}

{% endhighlight %}
  
![](/DateTimePicker/Date-in-other-months_images/Date-in-other-months_img1.png)

