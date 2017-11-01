---
layout: post
title: Arrow-Position
description: arrow position
platform: angular
control: Split Button
documentation: ug
---

# Arrow Position

To provide a good look and feel for **Split Button**, position of arrow in **Split Button** is important. Using **arrowPosition** property, you can easily customize the position of arrow inside **Split Button** without using any complex CSS. **arrowPosition** property is applicable for both **Split Button** and **Dropdown Button**. This property represent the position of arrow with menu content.

List of arrow position

<table><tr>
<th>
Arrow Position</th><th>Description</th></tr>
<tr>
<td>
left</td><td>
Support for arrow in left.</td></tr>
<tr>
<td>
right</td><td>
Support for arrow in right. </td></tr>
<tr>
<td>
top</td><td>
Support for arrow in top. </td></tr>
<tr>
<td>
bottom</td><td>
Support for arrow in bottom.</td></tr>
</table>


The following steps explain you the details on rendering the **Split Button** with above mentioned arrow position options.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton11" target="#Ul11" size="large" [showRoundedCorner]=true contentType="imageonly" prefixIcon="e-icon e-login" text="login" arrowPosition="left"></ej-splitbutton>
                    <ul id="Ul11">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton21" target="#Ul21" size="mini" arrowPosition="top" [showRoundedCorner]=true text="login"></ej-splitbutton>
                    <ul id="Ul21">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton31" target="#Ul31" size="small"  arrowPosition="bottom" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul31">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton41" target="#Ul41" size="medium"  arrowPosition="right" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul41">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
     </table>
    </div>
    <style>
        .e-split {
        float: left;
        padding-left: 65px;
    }
    </style>

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

![](/Angular/SplitButton/Arrow-Position_images/Arrow-Position_img1.png) 



