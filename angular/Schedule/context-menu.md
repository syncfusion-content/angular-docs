---
title: Schedule - Context Menu	
description: Default and Custom context menu options for appointments and cells in Scheduler
platform: Angular
control: schedule
documentation: ug
keywords: context-menu
---
# Context Menu

Scheduler provides default context menu options for both appointments as well as work cells. It also allows to define additional custom context menu options.

The options that are available under `contextMenuSettings` are as follows,

* **enable** - Enables/disables the context menu option in Scheduler.
* **menuItems** - Contains the sub-menu collections related to both the appointment and cells.

## Default Menu Options

The menu items contains two separate collection based on the appointment and cells.

### Appointment

The appointment collection includes the following options.

<table>
    <tr>
        <td>Open Appointment (default)</td>
    </tr>
    <tr>
        <td>Delete Appointment (default)</td>
    </tr>
    <tr>
        <td>Print Appointment</td>
    </tr>
    <tr>
        <td>Categorize</td>
    </tr>
</table>

### Cells

The default options available within the cell collection includes -

<table>
    <tr>
        <td>New Appointment</td>
    </tr>
    <tr>
        <td>New Recurring Appointment</td>
    </tr>
    <tr>
        <td>Today</td>
    </tr>
    <tr>
        <td>Go to date</td>
    </tr
    <tr>
        <td>Settings (View, TimeMode, Work Hours) </td>
    </tr>
</table>

The following code snippet shows how to enable the context menu settings in Scheduler and to make use of it with default available options.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate contextMenuSettings.enable=true [contextMenuSettings.menuItems]=scheduleMenuItems>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public scheduleMenuItems;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.scheduleMenuItems = {
            appointment: [{
                id: "open",
                text: "Open Appointment"
            }, {
                id: "delete",
                text: "Delete Appointment"
            }],
            cells: [{
                id: "new",
                text: "New Appointment"
            }, {
                id: "recurrence",
                text: "New Recurring Appointment"
            }, {
                id: "today",
                text: "Today"
            }, {
                id: "goToDate",
                text: "Go to date"
            }, {
                id: "settings",
                text: "Settings"
            }, {
                id: "view",
                text: "View",
                parentId: "settings"
            }, {
                id: "timeMode",
                text: "TimeMode",
                parentId: "settings"
            }, {
                id: "view_Day",
                text: "Day",
                parentId: "view"
            }, {
                id: "view_Week",
                text: "Week",
                parentId: "view"
            }, {
                id: "view_Workweek",
                text: "Workweek",
                parentId: "view"
            }, {
                id: "view_Month",
                text: "Month",
                parentId: "view"
            }, {
                id: "timeMode_Hour12",
                text: "12 Hours",
                parentId: "timeMode"
            }, {
                id: "timeMode_Hour24",
                text: "24 Hours",
                parentId: "timeMode"
            }, {
                id: "workhours",
                text: "Work Hours",
                parentId: "settings"
            }]
        }
    }
}

{% endhighlight %}

N> In agenda view, only the appointment menu items shows up in the context menu options. For default menu items, the id must be defined the same as mentioned in the above code example ??? as we have processed the menus based on this id within our source.

## Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu of both the appointment and cell collection.

The following code example depicts how **to add the custom menu items** to the appointment and cell collection of the context menu settings.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate contextMenuSettings.enable=true [contextMenuSettings.menuItems]=scheduleMenuItems [appointmentSettings.dataSource]=dataSource>
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
    public scheduleMenuItems;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
        this.scheduleMenuItems = {
            appointment: [{
                id: "open",
                text: "Open Appointment"
            }, {
                id: "delete",
                text: "Delete Appointment"
            }, {
                id: "option1",
                text: "User Option 1"
            }],
            cells: [{
                id: "celloption1",
                text: "Custom Option 1"
            }]
        };
    }
}

{% endhighlight %}

N> The **id** given for the custom menu items **must be unique** in both the appointment and cell collection.

## Handling Menu Actions

To define specific actions for a click made on the custom menu items, the client-side event `menuItemClick` can be used as depicted in the below code example.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate (menuItemClick)="onMenuItemClick($event)" contextMenuSettings.enable=true [contextMenuSettings.menuItems]=scheduleMenuItems [appointmentSettings.dataSource]=dataSource>
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
    public scheduleMenuItems;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
        this.scheduleMenuItems = {
            appointment: [{
                id: "open",
                text: "Open Appointment"
            }, {
                id: "delete",
                text: "Delete Appointment"
            }, {
                id: "option1",
                text: "User Option 1"
            }]
        };
    }

    onMenuItemClick(args: any): void {
        //args.events contains information of the clicked menu item.
        if (args.events.ID == "option1")
            alert("Custom menu clicked");
    }
}

{% endhighlight %}

Also, it is possible to predict the target on which the right click is made, either on the cells or appointments with the use of the event `beforeContextMenuOpen`. The below code example shows how to block the display of context menu, when right clicked on the cells by setting **args.cancel** as **true**.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate (beforeContextMenuOpen)="onBeforeContextMenuOpen($event)" contextMenuSettings.enable=true [contextMenuSettings.menuItems]=scheduleMenuItems [appointmentSettings.dataSource]=dataSource>
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
    public scheduleMenuItems;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
        this.scheduleMenuItems = {
            appointment: [{
                id: "open",
                text: "Open Appointment"
            }, {
                id: "delete",
                text: "Delete Appointment"
            }, {
                id: "option1",
                text: "User Option 1"
            }]
        };
    }

    onBeforeContextMenuOpen(args: any): void {
        //args.events.target ??? target information to depict either cell/appointment
        if ($(args.events.target).hasClass("e-workcells") || $(args.events.target).hasClass("e-monthcells"))
            args.cancel = true;
    }
}

{% endhighlight %}

## Adding Categorize Option

To include the default categorize option within the context menu, it is necessary to enable the `categorizeSettings` property as shown in the below code example.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [startHour]="7" [endHour]="18" [currentDate]=currentDate categorizeSettings.enable=true contextMenuSettings.enable=true [contextMenuSettings.menuItems]=scheduleMenuItems [appointmentSettings.dataSource]=dataSource>
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
    public scheduleMenuItems;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
        this.scheduleMenuItems = {
            appointment: [{
                id: "open",
                text: "Open Appointment"
            }, {
                id: "delete",
                text: "Delete Appointment"
            }, {
                id: "option1",
                text: "User Option 1"
            }]
        };
    }
}

{% endhighlight %}

N> The **categorize** option must be added only to the **appointment** collection, which displays on right clicking the appointments.
