---
layout: post
title: Dropdown-Button
description: dropdown button
platform: angular
control: Split Button
documentation: ug
---

# Dropdown Button

You can change the **Split Button** as **Dropdown Button** that consists of a single button that when clicked displays a drop-down list of mutually exclusive items. You can achieve this by using default functionality of **Split Button**.Initially the **target** is a mandatory one.

The following steps explain how to change the **Split Button** as **Dropdown Button.**

In the **HTML** page, add the following button elements to configure **Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton11" target="#menu" size="medium" [showRoundedCorner]=true text="login"></ej-splitbutton>
                 <ul id="menu">
                     <li><span>User</span></li>
                     <li><span>Guest</span></li>
                     <li><span>Admin</span></li>
                 </ul>
             </td>
         </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Dropdown-Button_images/Dropdown-Button_img1.png) 

