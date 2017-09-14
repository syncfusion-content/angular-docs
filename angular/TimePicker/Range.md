---
layout: post
title: Range
description: range
platform: Angular
control: TimePicker
documentation: ug
---

# Range

**TimePicker** widget provide options to set the Range (minTime & maxTime) for the time.

## Steps to change minTime & maxTime of the TimePicker

The following steps explains you to change the Range of the **TimePicker**.

In the **HTML** page, add a **&lt;input&gt;** element to configure **TimePicker** widget.

{% highlight html %}

    <div align="center">
    <input type="text" ej-timepicker [(ngModel)]="value" minTime="10:00 AM" maxTime="9:00 PM"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {

}

{% endhighlight %}


Execute the above code to render the following output.



![](/Angular/TimePicker/Range_images/Range_img1.png) 

