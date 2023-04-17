---
layout: post
title: RTL Support in Angular CurrencyTextBox Control | Syncfusion
description: Learn here about RTL Support in Syncfusion Essential Angular CurrencyTextBox Control, its elements, and more.
platform: Angular
control: CurrencyTextBox  
documentation: ug
---

# RTL Support in Angular CurrencyTextBox

The **Textbox** provides **RTL** (Right-To-Left) support. The alignment of CurrencyTextBox can be changed from **Left-To-Right** into **Right-To-Left**.

## Enable RTL

The following steps explain the implementation of **enableRTL** in CurrencyTextBox.

In the **HTML** page set the corresponding **&lt;input&gt;** elements for rendering CurrencyTextBox controls.


{% highlight html %}

<input id="currency" type="text" ej-currencytextbox [value]="value" [enableRTL]="true" />
	
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/currencytextbox/currencytextbox.component.html'
})
export class CurrencyTextboxComponent {
    public value: number;
    constructor() {
        this.value = 33;
    }
}

{% endhighlight %}


The output for CurrencyTextBox when **enableRTL** is **“true”** is as follows. 

![Angular CurrencyTextBox RTL support](RTL-Support_images/RTL-Support_img1.png)