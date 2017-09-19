---
layout: post
title: Stripline
description: stripline
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---

# Stripline

Stripline in Gantt control is used to highlight the important event in Gantt chart part. By using this feature, you can add the striplines to highlight important days in your project. The following code example shows you how to add the stripline in Gantt control.

{% highlight javascript %}

<ej-gantt
    //...
    [stripLines]= "stripLines">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public stripLines: any;
    constructor() {
        this.stripLines = [{
            day: "01/02/2014",
            label: "Project Release",
            lineStyle: "dotted",
            lineColor: "Darkblue",
            lineWidth: 2
        }]
    }
}

{% endhighlight %}

The following screenshot shows stripline in Gantt control.

![](Stripline_images/Stripline_img1.png)
