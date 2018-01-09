---
layout: post
title: Duration-Round-Off
description: Rounding off duration
platform: Angular
control: Gantt
documentation: ug
---

## Round-off start date, end date and duration value on taskbar editing
In Gantt start date, end date and duration values can be round-off as per current `scheduleHeaderSettings.scheduleHeaderType` value on taskbar resizing and dragging actions. This can be achieved by setting `roundOffDuration` argument value as `true` in `taskbarEditing` event.

The below code example explains how to achieve this requirement. 

{% highlight javascript %}

<ej-gantt id="GanttControl" (taskbarEditing)="taskbarEditing($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public taskbarEditing: any;
	constructor() {
		public taskbarEditing = function (args) {
		args.roundOffDuration= true;
		}
	}
}

{% endhighlight %}

![](Duration-Round-Off_images/OnResizing_img1.png)

![](Duration-Round-Off_images/AfterResizing_img2.png)