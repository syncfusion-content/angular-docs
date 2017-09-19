---
title: Show or Hide indicator, all day row, header, timescale
description: Show or hide time indicator, all day row, header, timescale
platform: Angular
control: schedule
documentation: ug
keywords: time indicator, all day, header, timescale
---
# Miscellaneous

## Time Indicator

The current system time can be depicted in a scheduler with an indication of a piece of text displaying the time over a horizontal line across today’s date (Vertical Scheduler mode). In Horizontal mode, the time indicator is displayed as a small vertical line within the header time cells (depicting current time).

It is enabled by default in Scheduler and to hide it, `showCurrentTimeIndicator` property needs to be set as **false** as shown below.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showCurrentTimeIndicator]=CurrentTimeIndicator [appointmentSettings.dataSource]=dataSource>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataSource;
    public CurrentTimeIndicator: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.CurrentTimeIndicator = false;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }
}

{% endhighlight %}

N> When Scheduler rendered with multiple resources, multiple time indicators are displayed in Vertical mode – whereas single indicator displays for horizontal mode.

## Show/Hide All-Day Row

The All-day row cell is a single row region displayed at the top of the work cells area to hold the all-day appointments together. The Scheduler displays it by default and if it needs to be hidden, the `showAllDayRow` property can be set to **false** as shown below.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showAllDayRow]=AllDayRow [appointmentSettings.dataSource]=dataSource>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataSource;
    public AllDayRow: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.AllDayRow = false;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }
}

{% endhighlight %}

N> The All-day row expands vertically, whenever more number of appointments are populated in one or more days.

## Show/Hide Header bar

The header bar is the top most region of the Scheduler which includes the date navigation icons and view navigation options – and also shown on the Scheduler by default. To hide the header bar, set the `showHeaderBar` property to **false** as shown below.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showHeaderBar]=ShowHeaderBar [appointmentSettings.dataSource]=dataSource>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataSource;
    public ShowHeaderBar: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.ShowHeaderBar = false;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }
}

{% endhighlight %}

## Show/Hide TimeScale

The TimeScale is the left most region of the Scheduler in vertical mode and the same is displayed at the top position in horizontal mode. It depicts the time interval either in a 12 or 24 hour mode. By default, the timeScale is displayed in the Scheduler and in order to hide it – set the `showTimeScale` option to **false** as shown below.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showTimeScale]=ShowTimeScale [appointmentSettings.dataSource]=dataSource>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataSource;
    public ShowTimeScale: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.ShowTimeScale = false;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }
}

{% endhighlight %}

## Show/Hide Location Field

The Location field in the default appointment window can be displayed or hidden from it using the `showLocationField` property. By default, this property is set to false. To display the location option in the appointment window, then set **showLocationField** to **true** and also bind the appropriate field to the location property within the appointmentSettings as shown below.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showLocationField]=ShowLocation [appointmentSettings.dataSource]=dataSource appointmentSettings.location="Location">
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataSource;
    public ShowLocation: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.ShowLocation = true;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0),
            Location: "RDU"
        }];
    }
}

{% endhighlight %}
