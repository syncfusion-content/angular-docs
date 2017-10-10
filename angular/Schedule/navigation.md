---
title: Date, Appointment, and View navigation
description: Navigation between views, appointments, and date
platform: Angular
control: schedule
documentation: ug
keywords: view navigation, date navigation, appointment navigation
---
# Navigation

Navigation in Scheduler can be classified based on Scheduler views, date and also the appointments in it.

## View Navigation

By default, all the available [view options](/angular/schedule/views) except the Custom View are available at the top right corner of the Schedule header, which can be traverse through continuously as and when needed.

Clicking on the particular date header in the Week/Work Week/Month/Custom View will navigate to the day view automatically. Also, clicking on the week header ranges displayed at the left side in the month view will navigate to the Week view. These particular actions can take place only if the Week and Day view options are present in the `views` Collection.

### Handling View navigation actions

Usually, the `navigation` event gets triggered whenever the views/dates are being navigated. To block the navigation to day and week views from month view, the **navigation** event can be used in the following way.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" (navigation)="onNavigation($event)" [appointmentSettings.dataSource]=dataSource>
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
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }

    onNavigation (args) {
        //args.target.currentTarget – target element which is clicked.
        var target = $(args.target.currentTarget);
        if (args.requestType == "viewNavigate" && (target.hasClass("e-headercells") || target.hasClass("e-monthheader") || target.hasClass("e-timecells")))
            args.cancel = true;
    }
}

{% endhighlight %}

N> Based on the navigation, the appointments that lies between the particular date ranges of the current view are fetched and rendered in the Scheduler.

## Date Navigation

The Scheduler date can be navigated on two aspects either in a continuous or random manner. On pressing the previous and next navigation arrow icons in the Scheduler header will move the scheduler one date back and forth respectively.

Another way of navigating through date is by making use of the built-in calendar available within the Scheduler, which pops out when the header date range is clicked. Selecting any date in the calendar will make the Scheduler to move to that particular date appropriately.

### Handling date navigation actions

To handle the date navigation actions, the `navigation` event can be used. For example, to block the date navigation, follow the below code example.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" (navigation)="onNavigation($event)" [appointmentSettings.dataSource]=dataSource>
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
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }

    onNavigation (args) {
        //args.target – target element which is clicked.
        //args.currentDate – current date of the Scheduler.
        //args.requestType – Specifies the navigation type.
        if (args.requestType == "dateNavigate")
            args.cancel = true;
    }
}

{% endhighlight %}

## Appointment Navigation

The Appointment navigation bars (labeled **Previous/Next Appointment**) are rendered parallel to each other on the left and right centric corners of the Schedule control. It is controlled by an API `showAppointmentNavigator` which is set to true by default. When it is set to false, these bars will not be displayed on the Scheduler.

Whenever the previous/Next Appointment bars are clicked, it navigates the Scheduler to the corresponding closest date where the appointments are available. If no appointments are available beyond the current date, then these appointment bars will be in a disabled state.

The following code example shows the way to define the **showAppointmentNavigator** property for Scheduler.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [showAppointmentNavigator]=AppointmentNavigator [appointmentSettings.dataSource]=dataSource>
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
    public AppointmentNavigator: boolean;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.AppointmentNavigator = true;
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
    }
}

{% endhighlight %}
