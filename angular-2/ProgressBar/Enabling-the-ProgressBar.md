---
layout: post
title: Enabling-the-ProgressBar
description: enabling the progressbar
platform: Angular2
control: ProgressBar
documentation: ug
---

# Enabling the ProgressBar

The ProgressBar is enabled by using the [enabled](https://help.syncfusion.com/api/js/ejprogressbar#members:enabled) Property. When this property is set to ‘**false**’, it disables the ProgressBar widget. By default, ‘**enabled**’ property is set to ‘**true**’ in the ProgressBar widget.

The following code explains how to disable the ProgressBar widget when [enabled](https://help.syncfusion.com/api/js/ejprogressbar#members:enabled) property is set to ‘**false**’.

{% highlight html %}

<div class="control">
    <ej-progressbar id="progressBar" [enabled]="false" [value]="val" [height]="height" [width]="width" (create)="onCreate($event)"></ej-progressbar>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/progressbar/progressbar.component.html'
})
export class ProgressBarComponent {  
    val: number;
    height: number;
    width: number;
    onCreate($event) {
        var progress = $("#progressBar").data("ejProgressBar");
        progress.setModel({ text: progress.getValue() + " %" });
    }
    constructor() {
        this.val = 50;
        this.height = 40;
        this.width = 500;
    }
}

{% endhighlight %}

The following screenshot displays the output for the above code.

![](Enabling-the-ProgressBar_images/Enabling-the-ProgressBar_img1.png) 

