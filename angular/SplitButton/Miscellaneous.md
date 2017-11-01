---
layout: post
title: Miscellaneous
description: miscellaneous
platform: angular
control: Split Button
documentation: ug
---

# Miscellaneous

## Text

It is necessary to display the user defined text for **Split Button**. Using **text** property, you can easily set text content for **Split Button**. This text property overwrites the text that is provided on input button element.

The following steps explains you the details about rendering the **Split Button** with specified text.

In the **HTML** page, add the following button elements to configure **Split Button** widget.


{% highlight html %}

    <ej-splitbutton id="splitButton_rtl" target="#target" size="small" text="signIn"></ej-splitbutton>
    <ul id="target">
    <li><span>User</span></li>
    <li><span>Guest</span></li>
    <li><span>Admin</span></li>
    </ul> 
    <style>
    .spltspan {
        margin-left: 120px;
    }
    </style>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    constructor() {
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Miscellaneous_images/Miscellaneous_img1.png) 

In output “login” text in **Split Button** is replaced by text property value.

## Show Rounded Corner

Specifies the corner of **Split Button** in rounded shape. By default, the edges of **Split Button** is not rounded. To set rounded corner, you can enable **showRoundedCorner** property**.**

The following steps explains you the details about rendering the **Split Button** with rounded corner.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}


    <ej-splitbutton id="splitButton_rtl" target="#target" size="small" [(showRoundedCorner)]="showrounded" text="login"></ej-splitbutton>
    <ul id="target">
    <li><span>User</span></li>
    <li><span>Guest</span></li>
    <li><span>Admin</span></li>
    </ul> 
    <style>
    .spltspan {
        margin-left: 120px;
    }
    </style>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html',
})
export class DefaultComponent {
    showrounded: boolean;
    constructor() {
        this.showrounded = true;
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Miscellaneous_images/Miscellaneous_img2.png) 

