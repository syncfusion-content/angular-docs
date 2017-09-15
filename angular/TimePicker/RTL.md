---
layout: post
title: RTL
description: rtl
platform: Angular
control: TimePicker
documentation: ug
---

# RTL

This feature supports to change the left-to-right alignment of the **TimePicker** widget to right-to-left(**RTL**). The custom template **TimePicker** also supports **RTL**.

## Enabling Right-To-Left Support

The following steps explains you in enabling the right-to-left property for the **TimePicker**.

In the **HTML** page, add a **&lt;input&gt;** element to configure **TimePicker** widget.   

{% highlight html %}

     <div align="center">
     <input type="text" ej-timepicker [(ngModel)]="value" [(enableRTL)]="rtl"/>
     </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
    rtl: boolean;
    constructor() {
        this.rtl = true;
    }
}

{% endhighlight %}

The following screenshot illustrates a **TimePicker** control when **enableRTL** is set to **“true”**

![](/angular/TimePicker/RTL_images/RTL_img1.png) 

