---
title: Schedule - Customization	
description: Customization of working hours, date, and appointment window
platform: Angular-2
control: schedule
documentation: ug
keywords: customization, work hours, appointment window, display hours, Query cell info
---
# Customization

The Scheduler can be customized in various aspects like - 

* Setting different Start/end hour limits
* Highlighting the working hours 
* Setting different date format
* Specifying minimum and maximum date ranges 
* Customize the entire appointment window with the user required fields
* Setting different time Slot duration
* Complete Scheduler customization using queryCellInfo event
* Setting different first day of week

## Hour Customization

It includes customization of displaying Scheduler with specific Start/End hours and also defining the working hour time range which is differentiated as business hours.

### Schedule Display Hours

It denotes the start and end hour time limits to be displayed on the Scheduler. To set this time limit, two properties namely `startHour` and `endHour` can be used. 

* **startHour** - The hour from which the Scheduler time display actually starts.
* **endHour** - The hour on which the Scheduler time display should end.

The following code example renders the scheduler from 7.00 AM to 6.00 PM.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource>
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
        }]
    }
}

{% endhighlight %}

### Working Hours

Working hours indicates the work hour limit within the Scheduler, which is highlighted visually with white colored work cells. To enable the highlighting of work hours on the Scheduler, set the **highlight** option available within the workHours property to **true**. By default, it is set to true. `workHour` is a object property which contains the below specified options,

* **highlight** – enables/disables the highlighting of work hours.
* **start** - sets the start time of the working/business hour in a day. 
* **end** - sets the end time limit of the working/business hour in a day. 


{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [workHours.highlight]="true" [workHours.start]="8" [workHours.end]="16" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource>
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
        }]
    }
}

{% endhighlight %}

N> By default, work hour **start** is set to **9** and **end** is set to **18**. Also, the Scheduler cells automatically scrolls up or down based on the starting work hour, to make the user to view that particular time initially.

## TimeScale

The `TimeScale` allows the user to set the required time slot duration for the work cells that displays on the Scheduler. It provides option to customize both the major and minor slots using template option. It includes the below properties such as,

* `enable` - It accepts true or false value, denoting whether to show or hide the time slots. Its default value is `true`.
* `majorSlot` – Specifies the major time slot duration.
* `minorSlotCount` – Specifies the value, based on which the minor time slots are divided into appropriate count.
* TimeScale templates - 2 template options available for customizing timeScales namely `minorSlotTemplateId` and `majorSlotTemplateId`. 

The majorSlot and minorSlot can be set on the Scheduler with the following code example.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [timeScale.enable]="true" [timeScale.majorSlot]="60" [timeScale.minorSlotCount]="6" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource>
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
        }]
    }
}

{% endhighlight %}

## Date Customization

The date in the Scheduler can be customized by setting specific minimum and maximum date ranges and also defining various date formats to it.

### Current Date

The Current date indicates the date with which the Scheduler loads initially and based on which the appropriate date range displays in the week/workweek/month/agenda views. To set the current date to the Scheduler – use the following code example,

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource>
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
        }]
    }
}

{% endhighlight %}

N> By default, the System current date will be taken as Scheduler’s current date.

### MinDate and MaxDate

Providing the `minDate` and `maxDate` property with some date values, allows the Scheduler to set the minimum and maximum date range. The Scheduler date that lies beyond these minimum and maximum date range will be in a disabled state, so that the date navigation is blocked beyond these specified date range. Also, the appointments that lies beyond these date ranges will not be displayed on the Scheduler.  

The following code example shows how to set the minDate and maxDate properties of the Scheduler.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [minDate]="minDate" [maxDate]="maxDate" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource>
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
    public minDate: Date;
    public maxDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.minDate = new Date(2017, 11, 4);
        this.maxDate = new Date(2017, 11, 8);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }]
    }
}
{% endhighlight %}

N> The **maxDate** value provided should always be greater than that of **minDate** value.


## Scheduler Customization using queryCellInfo

It is possible to format and customize almost every child elements of scheduler such as work cells, header cells, time cells and so on using `queryCellInfo` event.

The following code snippet shows how to customize the appointment and work cells based on the query cell info event.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" (queryCellInfo)="checkInfo($event)">
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    checkInfo(args: any) {
        switch (args.requestType) {
            case "workcells":
                args.element.css("background-color", "#ffe9cc");
                break;
            case "monthcells":
                args.element.css("background-color", "#faa41a");
                args.element.css("border-color", "#faa41a");
                break;
        }
    }
}

{% endhighlight %}

The Scheduler elements are listed below which can be formatted through this event. The names are listed in the format with which it can be accessed or used within the requestType argument of the event.

<table class="params">
    <thead>
        <tr>
            <th>Request Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">appointment</td>
            <td class="description">Depicts the appointment element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">agendacells</td>
            <td class="description">Depicts the Agenda Cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">alldaycells</td>
            <td class="description">Depicts the AllDay cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headercells</td>
            <td class="description">Depicts the header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourceheadercells</td>
            <td class="description">Depicts the resource header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftheadercells</td>
            <td class="description">Depicts the left empty space on header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftindentcells</td>
            <td class="description">Depicts the left empty space on date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">timecells</td>
            <td class="description">Depicts the left side time panel cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headerdate</td>
            <td class="description">Depicts the header date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">emptytd</td>
            <td class="description">Depicts the empty space above the vertical scroller within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourcegroupheader</td>
            <td class="description">Depicts the header group cell in horizontal orientation in the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">monthcells</td>
            <td class="description">Depicts the month cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">workcells</td>
            <td class="description">Depicts the work cell element within the Scheduler.</td>
        </tr>
    </tbody>
</table>
