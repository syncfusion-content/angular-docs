---
layout: post
title: RTL-Support
description: rtl support
platform: Angular
control: Button
documentation: ug
---

# RTL Support

In some cases you can use right to left alignment. Here, RTL support is provided using **enableRTL** property. In RTL mode when you have more than one content (image/text, image/image) in button, then these content are aligned in right to left format. For example, when text is in left and image is in right position, after applying right to left alignment these position are interchanged.

The following steps explains the details about rendering the button with Right to left alignment support.

In the **HTML** page, add the following button elements to configure button widget.

{% highlight html %}

    <table width="500px">
    <tr>
        <td>
            <button id="buttonType_button" [showRoundedCorner]="true" [enableRTL]="true" size="large" contentType="TextAndImage"  prefixIcon="e-icon e-login" type="button" ej-button text="button"></button> 
  
    </tr>
    </table>

{% endhighlight %}

{% highlight html %}

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

In above mentioned code example prefixIcon property is used and the icon that is to be on left side, (before text) is rendered on right side as enableRTL property is used with prefixIcon.  Consequently, the alignment is changed in right to left order.

Execute the above code to render the following output.

![](RTL-Support_images/RTL-Support_img1.png) 

