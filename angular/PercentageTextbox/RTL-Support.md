---
layout: post
title: RTL-Support
description: rtl support
platform: Angular
control: PercentageTextBox 
documentation: ug
---

# RTL Support

The **PercentageTextBox** provides **RTL** (**Right-To-Left**) support. The alignment of **PercentageTextBox** can be changed from **Left-To-Right** into **Right-To-Left**.

## Enable RTL

The following steps explain the implementation of **enableRTL** in **PercentageTextBox** .

In the **HTML** page set the corresponding **&lt;input&gt;** elements for rendering **PercentageTextBox** control.

{% highlight html %}

<input id="percent" type="text" ej-percentagetextbox [value]="value" [enableRTL]="true" />

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/percentagetextbox/percentagetextbox.component.html'
})
export class PercentageTextboxComponent {
    public value: number;
    constructor() {
        this.value = 21234;
    }
}

{% endhighlight %}

The output for **PercentageTextBox** when **enableRTL** is **“true”** is as follows. 

![](/angular/PercentageTextbox/RTL-Support_images/RTL-Support_img1.png)