---
title: Setting dimension
description: Setting dimension for Schedule control
platform: angular-2
control: schedule
documentation: ug
keywords: dimension, cell dimension, cell width, cell height 
---
# Setting Dimension

The dimension normally refers to the height and width of the element. With Scheduler, it is possible to set 2 kinds of dimensions.

* Scheduler dimension (Scheduler control height and width)
* Cell dimension (Scheduler cells height and width)

## Scheduler Dimension

The `height` and `width` properties can be defined to set the outer dimension of the Scheduler control.

{% highlight html %}

<ej-schedule id="Schedule1" width="70%" height="500px">
</ej-schedule> 

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        constructor() {        
        }
    }

{% endhighlight %}

N> The height and width properties accepts both **pixel** and **percentage** values.

## Scheduler Cell Dimensions

### Cell Height

The `cellHeight` property allows the Scheduler to set the height of the cells in pixels. The appointment height in vertical mode changes accordingly as per the cell size within which it renders.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" cellHeight="40px" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData >
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %}

N> In **desktop** mode, the default height value of the cells is set to **20px**, whereas for **mobile** mode – the Scheduler cells are rendered with **40px** by default.

### Cell Auto-Height

The height of the cells specifically in timeline view can be made to adjust automatically based on its exceeding appointment count. It is controlled by an API named `showOverflowButton` which accepts true or false value, denoting whether to enable/disable the cell auto-height adjusting option. To enable this option, set the value of `showOverflowButton` as `false` whereas its default value is `true`.

In **Vertical** view, the same functionality is made applicable only in the **Month View** whereas in **Horizontal** mode, it is applicable in all the views.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" currentView="month" [showOverflowButton]="false" currentDate="5/4/2014" [appointmentSettings.dataSource]=scheduleData>
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %}

### Cell Width

The `cellWidth` property allows the Scheduler to set the width of the cells in pixels. The appointment width adjusts based on the cell width of the Scheduler.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" cellWidth="97px" currentDate="5/4/2014"
    [appointmentSettings.dataSource]=scheduleData >
</ej-schedule>

{% endhighlight %} 

{% highlight ts %}

    import { Component } from '@angular/core';

    @Component({
        selector: 'ej-app',
        templateUrl: 'src/schedule/schedule.component.html',
    })
    export class ScheduleComponent {
        public scheduleData: any;
        constructor() {
            this.scheduleData = [{ Id: 100, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 5, 10, 0), EndTime: new Date(2014, 4, 5, 11, 0), Description: "", AllDay: false, Recurrence: false, Categorize: "1,3" }, 
		                 { Id: 101, Subject: "Bering Sea Gold", StartTime: new Date(2014, 4, 2, 16, 0), EndTime: new Date(2014, 4, 2, 17, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "2,5" }, 
						 { Id: 102, Subject: "What Happened Next?", StartTime: new Date(2014, 4, 4, 1, 0), EndTime: new Date(2014, 4, 4, 1, 30), Description: "", AllDay: false, Recurrence: false, Categorize: "3,6" }];
        }
    }

{% endhighlight %}

N> When the **cellHeight** and **cellWidth** properties are set with some specific pixel values, the cell size does not adapt to the responsive behavior of the Scheduler while resizing it in desktop/mobile mode.
