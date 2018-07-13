---
layout: post
title: RTL-Support
description: rtl support
platform: Angular
control: ProgressBar
documentation: ug
---

# RTL Support

Right-To-Left starts from the right of the page and continues to the left. By default, this option is set to ‘**false**’ in the ProgressBar control. The [enableRTL](https://help.syncfusion.com/api/js/ejprogressbar#members:enablertl) property allows the ProgressBar control to display it in the right to left direction.

The following code helps that how to **enable** the **RTL** property of the ProgressBar control.

{% highlight html %}

<div class="control">
  <ej-progressbar id="progressBar" [enableRTL]="true" [value]="val" [text]="text" [height]="height" [width]="width"></ej-progressbar>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/progressbar/progressbar.component.html'
})
export class ProgressBarComponent {  
    val: number;
    text: any;
    height: number;
    width: number;
    constructor() {
        this.val = 80;
        this.text = 80;
        this.height = 20;
        this.width = 500;
    }
}

{% endhighlight %}

The following screenshot displays the output.

![](RTL-Support_images/RTL-Support_img1.png)


















