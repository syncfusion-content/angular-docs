---
layout: post
title: State-Maintenance
description: state maintenance
platform: Angular
control: ProgressBar
documentation: ug
---

# State Maintenance

Saves current model value to cookies for **State Maintenance**. While refreshing the ProgressBar widget, page retains the model value applied from browser cookies. By default, the [enablePersistence](https://help.syncfusion.com/api/js/ejprogressbar#members:enablepersistence) property is set to ‘**false**’ in the ProgressBar.

The following code enables the **State Maintenance** in the ProgressBar control.

{% highlight html %}

<div class="control">
    <ej-progressbar id="progressBar" [enablePersistence]="true" [value]="val" [height]="height" [width]="width" (create)="onCreate($event)"></ej-progressbar>  
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
    constructor() {
        this.val = 80;
        this.height = 20;
        this.width = 500;
    }
    onCreate($event) {
        var progress = $("#progressBar").data("ejProgressBar");
        progress.setModel({ text: progress.getValue() });
    }
}

{% endhighlight %}

The following screenshot displays the output.

![](State-Maintenance_images/State-Maintenance_img1.png) 

