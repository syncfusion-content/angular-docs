---
layout: post
title: Time Picker in Angular TimePicker Control | Syncfusion
description: Learn here all about time format support in Syncfusion Angular TimePicker control, its elements, and more.
platform: Angular
control: TimePicker
documentation: ug
---

# Time Format in Angular TimePicker

**TimePicker** widget provides you an option to change the time format.

## Steps to change Time Format of TimePicker widget

The following steps explains you to change the time format for the **TimePicker**.

In the **HTML** page, add a **&lt;input&gt;** element to configure **TimePicker** widget.

{% highlight html %}

    <div align="center">
    <input type="text" ej-timepicker [(ngModel)]="value" timeFormat="h:mm:ss tt"/>
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

![Angular TimePicker time format](Time-Format_images/Time-Format_img1.png) 

