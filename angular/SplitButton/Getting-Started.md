---
layout: post
title: Getting-Started
description: getting started 
platform: Angular
control: Split Button
documentation: ug
---

# Getting Started 

This section explains briefly about how to create a **Split Button** in your application.The basic rendering of **Essential Angular Split** **Button** is achieved by using default functionality. Initially the **target** is a mandatory one, without this field it does not act as normal button on two sides.


![](/Angular/SplitButton/Getting-Started_images/Getting-Started_img1.png)

**Split Button Creation**

Adding button element and **&lt;UL&gt;, &lt;LI&gt;** element for **Split** **Button** rendering.

{% highlight html %}

    <ej-splitbutton id="target1" target="#target" text="save" width="500" buttonMode="split"></ej-splitbutton>
    <ul id="target">
    <li><a href="#">Open..</a></li>
    <li><a href="#">Save</a></li>
    <li><a href="#">Delete</a></li>
    </ul>  

{% endhighlight %}

Initialization of **ejSplitButton** in script

{% highlight html %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    checkstatus: boolean;
    constructor() {
        this.checkstatus = true;
    }
}

{% endhighlight %}

Output of above steps

![](/Angular/SplitButton/Getting-Started_images/Getting-Started_img2.png) 

