---
layout: post
title: Right-to-Left
description: right-to-left
platform: Angular
control: DateTimePicker
documentation: ug
---

# Right-to-Left

RTL control supports right-to-left functionality and features for languages that work right-to-left for selecting and editing date and time. You can change your popup and textbox display to read right-to-left. Arabic and Hebrew are written from right to left. The customer who has a right to left writing style can use this feature. You can achieve this in your **DateTimePicker** by using **enableRTL** property. Setting this property to “**True**”allows you to write in the right to left format. Position of the toolbars are also changed to right to left.

Add the following code in your **HTML** page.

{% highlight html %}
  
    <div align="center">
    <input type="text" ej-datetimepicker width='200' [(ngModel)]="value" [(enableRTL)]= "rtl">
    </div>

{% endhighlight %}


{% highlight html %}s

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './rtl.component.html'
})
export class RTLComponent {
    value: any;
    rtl: boolean;
    constructor() {
        this.value = Date();
        this.rtl = true;
    }
}

{% endhighlight %}
  
![](/js/DateTimePicker/Right-to-Left_images/Right-to-Left_img1.png)

