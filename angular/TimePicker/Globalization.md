---
layout: post
title: Localization
description: localization
platform: Angular
control: TimePicker
documentation: ug
---

# Globalization

**TimePicker** supports globalization with different culture.

## Enabling Globalization Support

The following steps explains you on how to enable **Globalization** support for **TimePicker**.

In an **HTML** page, add a **&lt;input&gt;** element to configure **TimePicker** widget.   


{% highlight html %}

    <div align="center">
    <input type="text" id="time" [locale]="locale" ej-timepicker/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
    locale: string;
    constructor() {
        this.locale = "zh-CN";
}
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/TimePicker/Globalization_images/Globalization_img1.png) 

