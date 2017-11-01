---
layout: post
title: RTL-support
description: rtl support
platform: Angular
control: Toggle Button
documentation: ug
---

# RTL support

In some cases, it is necessary to use right to left alignment. You can render **RTL** support by using **enableRTL** property. In **RTL** mode, when there is more than one content (image/text, image/image) in button, then the content is aligned in right to left format. For example, when text is in left and image is in right position, after applying right to left alignment these positions are interchanged.

The following steps explains you the details about rendering the **Toggle Button** with Right to left alignment support.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" imagePosition="imageleft" id="toggle_rtl" contentType="textandimage" [showRoundedCorner]="true" [enableRTL]="true" size="small" defaultText="play" activeText="next" defaultPrefixIcon="e-icon e-mediaplay" [toggleState]="state" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
             </td>
         </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    state: boolean;
    constructor() {
        this.state = false;

    }
}

{% endhighlight %}

In above mentioned code example **prefixIcon** property is used and the icon that is to be on left side, (before text) is rendered on right side as **enableRTL** property is used with **prefixIcon.**  Consequently, the alignment is changed in right to left order.

Output of above steps



![](/Angular/ToggleButton/RTL-support_images/RTL-support_img1.png) 


