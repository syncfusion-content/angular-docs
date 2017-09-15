---
layout: post
title: TimePicker-Customization
description: timepicker customization
platform: Angular
control: TimePicker
documentation: ug
---

# TimePicker Customization

The **TimePicker** provides support to display a **TimePicker** in your web page and allows you to pick a time from it.

## Creating TimePicker Widget

The following steps explains you to create a **TimePicker** widget.

In an **HTML** page, add a **&lt;input&gt;** element to configure **TimePicker** widget.

{% highlight html %}

    <div align="center">
    <input type="text" ej-timepicker/>
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

The following screenshot illustrates you a default **TimePicker**.



![](/Angular/TimePicker/TimePicker-Customization_images/TimePicker-Customization_img1.png) 

