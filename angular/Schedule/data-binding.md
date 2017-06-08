---
title: Data binding with Schedule	
description: Binding local and remote data to Scheduler
platform: Angular
control: schedule
documentation: ug
keywords: data binding, local data, remote data
---
# Data Binding

## Appointment Fields

The below listed names are the appointment fields which holds the appropriate column names from the dataSource.

<table>
<tr>
<th>
Field name<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
id<br/><br/></td><td>
Binds the <b>id</b> field name for indexing and performing CRUD operation on the appointments. It’s optional.<br/><br/></td></tr>
<tr>
<td>
startTime<br/><br/></td><td>
Binds the appointment start time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
startTimeZone<br/><br/></td><td>
Binds the name of the start timezone field in the dataSource and also its related validation rules. If the <b>startTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
endTime<br/><br/></td><td>
Binds the appointment end time field name which is <b>mandatory</b> and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
endTimeZone<br/><br/></td><td>
Binds the name of the end timezone field in the dataSource and also its related validation rules. If the <b>endTimeZone</b> field is not mentioned, then the appointment makes use of the Scheduler timeZone or System timeZone.<br/><br/></td></tr>
<tr>
<td>
subject<br/><br/></td><td>
Binds the appointment subject field name which holds the summary of the appointment and also its related validation rules. <br/><br/></td></tr>
<tr>
<td>
location<br/><br/></td><td>
Binds the name of the location field and also its related validation rules. It indicates the appointment location/occurrence place. This field needs to be bind to the Scheduler, when an API <b>showLocationField</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
description<br/><br/></td><td>
Binds the appointment description field name and also its related validation rules.<br/><br/></td></tr>
<tr>
<td>
allDay<br/><br/></td><td>
Binds the name of the `allDay` field. It accepts the <b>boolean</b> value and indicates whether the appointment is an all-day appointment or not.<br/><br/></td></tr>
<tr>
<td>
categorize<br/><br/></td><td>
Binds the name of the categorize field and also its related validation rules. It indicates the category or status value (red categorize, green, yellow and so on). <br/><br/></td></tr>
<tr>
<td>
priority<br/><br/></td><td>
Binds the name of the priority field, its related validation rules and also indicates the priority (high, low, medium and none) of the appointments. This field should be bind to the Scheduler, when <b>prioritySettings.enable</b> is set to true.<br/><br/></td></tr>
<tr>
<td>
resourceFields<br/><br/></td><td>
Binds one or more fields in the resource collection. It maps the resource field names with the appointments, denoting to which resource the appointments actually belongs.<br/><br/></td></tr>
<tr>
<td>
recurrence<br/><br/></td><td>
Binds the name of the recurrence field. It accepts the <b>boolean</b> value and indicates whether the appointment is a recurrence appointment or not.<br/><br/></td></tr>
<tr>
<td>
recurrenceRule<br/><br/></td><td>
Binds the name of the recurrenceRule field. It holds the recurrence pattern associated with the appointments.<br/><br/></td></tr>
<tr>
<td>
recurrenceId<br/><br/></td><td>
Binds the recurrence Id field which acts as a parent id for Scheduler recurrence appointments.<br/><br/></td></tr>
<tr>
<td>
recurrenceExDate<br/><br/></td><td>
Binds the recurrence Exception field which accepts the recurrence Exception date values.<br/><br/></td></tr>
</table>

The below example depicts the appointment fields accepting the string type mapper fields,

{% highlight html %}

<ej-schedule id="Schedule1" [currentDate]=currentdate [showLocationField]=showLocation [categorizeSettings.enable]=enableCategorize [prioritySettings.enable]=enablePriority [appointmentSettings.dataSource]=scheduleData appointmentSettings.id="Id" appointmentSettings.subject="Subject" appointmentSettings.startTime="StartTime" appointmentSettings.endTime="EndTime" appointmentSettings.allDay="AllDay" appointmentSettings.recurrence="Recurrence" appointmentSettings.recurrenceRule="RecurrenceRule" appointmentSettings.resourceFields="OwnerId" appointmentSettings.categorize="Categorize" appointmentSettings.priority="Priority" appointmentSettings.location="location" [group]=group>
    <e-resources>
        <e-resource field="OwnerId" title="Owner" name="Owners" [resourceSettings]=resourceData></e-resource>
    </e-resources>
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
    public currentdate: Date;
    public group: any;
    public allowMultiple: Boolean;
    public resourceData: any;
    public showLocation: Boolean;
    public enableCategorize: Boolean;
    public enablePriority: Boolean;
    constructor() {
        this.showLocation = true;
        this.enableCategorize = true;
        this.enablePriority = true;
        this.scheduleData = [{
            Id: 1,
            Subject: "Music Class",
            StartTime: new Date(2017, 5, 4, 1, 30),
            StartTimeZone: "UTC +05:30",
            EndTime: new Date(2017, 5, 4, 1, 30),
            EndTimeZone: "UTC +05:30",
            Description: "Never Giveup on Obstacles",
            location: "US",
            AllDay: false,
            Recurrence: true,
            RecurrenceRule: "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15",
            Categorize: "1",
            Priority: "medium",
            OwnerId: 3,
            RecurrenceId: 1,
            RecurrenceExDate: null
        }];
        this.currentdate = new Date(2017, 5, 5);
        this.group = {
            resources: ['Owners']
        };
        this.resourceData = {
            dataSource: [{
                text: "Nancy",
                id: 1,
                color: "#f8a398"
            }, {
                text: "Steven",
                id: 3,
                color: "#56ca85"
            }, {
                text: "Michael",
                id: 5,
                color: "#51a0ed"
            }],
            text: 'text',
            id: 'id',
            color: 'color'
        };
    }
}
{% endhighlight %} 

## Appointment Field Validation

It is possible to validate the required fields of the appointment window from client-side before submitting it, by adding appropriate validation rules to each fields. The appointment fields have been extended to accept both String and object type values. Therefore, in order to perform validations, it is necessary to specify object values for the appointment fields.  

Refer the appointment fields specified with validation rules from the following code example.

{% highlight html %}

<ej-schedule id="Schedule1" [categorizeSettings.enable]=enableCategorize appointmentSettings.id="Id" [appointmentSettings.subject]=subject [appointmentSettings.description]=description appointmentSettings.startTime="StartTime" appointmentSettings.endTime="EndTime" appointmentSettings.allDay="AllDay" appointmentSettings.recurrence="Recurrence" appointmentSettings.recurrenceRule="RecurrenceRule" [appointmentSettings.categorize]=categorize>
</ej-schedule>>

{% endhighlight %}

{% highlight ts %}
import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public enableCategorize: Boolean;
    public subject: Object;
    public description: Object;
    public categorize: Object;
    constructor() {
        this.enableCategorize = true;
        this.subject = { field: "Subject", validationRules: { required: true } };
        this.description = { field: "Description", validationRules: { required: true, minlength: 5, maxlength: 500 } };
        this.categorize = { field: "Categorize", validationRules: { required: true, messages: { required: "Categories are required." } } };
    }
}
{% endhighlight %} 

## Binding to JSON Data Array

To bind the Scheduler events data as array of JSON objects, refer the below code example.

**Example** - Array of JSON Data Binding

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
    public dataSource: Object[];
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 10, 5);
        this.dataSource = [{
            Id: 1,
            Subject: "Music Class",
            StartTime: new Date("2017/11/7 06:00 AM"),
            EndTime: new Date("2017/11/7 07:00 AM")
        }, {
            Id: 2,
            Subject: "School",
            StartTime: new Date("2017/11/7 9:00 AM"),
            EndTime: new Date("2017/11/7 02:30 PM")
        }];
    }
}
{% endhighlight %}

## Binding Remote Data Service

The appointment data can be bound to the Scheduler through the [Odata](http://www.odata.org) remote services, where the service URL is mapped with `Data manager` and then configured to the Schedule dataSource API.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [currentDate]=currentDate [appointmentSettings.dataSource]=dataManager
        [appointmentSettings.query]=query>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataManager;
    public query;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 5, 5);
        this.dataManager = ej.DataManager({
            // referring data from remote service (url binding)
            url: "http://js.syncfusion.com/ejServices/api/Schedule/LoadData",
            crossDomain: true
        });
        // query to fetch the records from the specified table “Events”
        this.query = ej.Query().from("Events").take(10);
    }
}

{% endhighlight %}

## OData V4

The OData v4 is an improved version of OData protocols and the DataManager can also retrieve and consume appointment data from [OData v4](http://www.odata.org/documentation) services. 

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [currentDate]=currentDate [appointmentSettings.dataSource]=dataManager
        appointmentSettings.subject="ShipName" appointmentSettings.startTime="OrderDate" appointmentSettings.endTime="RequiredDate"
        appointmentSettings.description="ShipAddress">
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataManager;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(1997, 2, 23);
        this.dataManager = ej.DataManager({
            //OData v4 service 
            url: "http://services.odata.org/V4/Northwind/Northwind.svc/Orders/",
            adaptor: new ej.ODataV4Adaptor()
        });
    }
}

{% endhighlight %}


## WebAPI Binding

The Schedule appointment data can be bound through the Web API service and it is a programmatic interface to define the request and response messages system that is mostly exposed in **JSON** or **XML**.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [currentDate]=currentDate [appointmentSettings.dataSource]=dataManager>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataManager;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 5, 5);
        this.dataManager = ej.DataManager({
            // get the required appointments from Web API service
            url: "http://js.syncfusion.com/ejServices/api/Schedule/LoadData",
            // enable cross domain
            crossDomain: true
        });
    }
}

{% endhighlight %}

The server-side code to retrieve the appointments are as follows.

{% highlight c# %}

// To retrieve the appointments from database and bind it to Scheduler
public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
{
    return new NORTHWNDEntities().Events.ToList();
}

{% endhighlight %}

## Loading Data on Demand

Load on demand feature allows the Scheduler to retrieve only the filtered appointment data (for the current Scheduler date range) from the service/database during **loading time**, and that too only for the current Scheduler view. There are 3 parameters made available on the server-side namely **CurrentDate**, **CurrentView** and **CurrentAction** through which only the necessary appointments are retrieved from the database and then assigned to the Scheduler dataSource. With this kind of Scheduler action, consuming only lesser data will reduce the usage of network bandwidth size and loading time. 

The **enableLoadOnDemand** property is used to enable or disable the load on demand functionality of the schedule.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [enableLoadOnDemand]="true" [currentDate]=currentDate [appointmentSettings.dataSource]=dataManager>
</ej-schedule>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
})
export class ScheduleComponent {
    public dataManager;
    public currentDate: Date;
    constructor() {
        this.currentDate = new Date(2017, 5, 5);
        this.dataManager = ej.DataManager({
            // get the required appointments from service
            url: "http://js.syncfusion.com/ejServices/api/Schedule/LoadCurrentData",
            // enable cross domain
            crossDomain: true
        });
    }
}

{% endhighlight %}

The server-side code to handle the load on demand is as follows.

{% highlight c# %}

// retrieve the appointments based on the current date.
public IEnumerable<Event> GetData(String CurrentDate, String CurrentView, String CurrentAction)
{
    var dateString = Regex.Match(CurrentDate.ToString(), @"^(\w+\b.*?){4}").ToString(); 
    string format = "ddd MMM dd yyyy"; 
    DateTime dateTimeValue;
    try
    {
        dateTimeValue = DateTime.ParseExact(dateString, format, CultureInfo.InvariantCulture);
    }
    catch(FormatException)
    {
        var dateSplit = CurrentDate.Split(' ');//For IE<=10 Fri Mar 20 11:00:22 UTC+0530 2015
        if (dateSplit[2].Length == 1) dateSplit[2] = string.Concat("0", dateSplit[2]);
        dateString = string.Concat(dateSplit[0], ' ', dateSplit[1], ' ', dateSplit[2], ' ', dateSplit[dateSplit.Length - 1]);
        dateTimeValue = DateTime.ParseExact(dateString, format, CultureInfo.InvariantCulture);
    }
	// AppointmentReposit is a user-defined class within which the FilterAppointment method is defined. 
    AppointmentReposit rep = new AppointmentReposit();
    var data = rep.FilterAppointment(dateTimeValue, CurrentAction, CurrentView); 
    return data;
}

// Method to filter the appointments based on the date range
public List<Event> FilterAppointment(DateTime CurrentDate, String CurrentAction, String CurrentView)
{
    DateTime CurrDate = Convert.ToDateTime(CurrentDate);
    DateTime StartDate = FirstWeekDate(CurrDate.Date);
    DateTime EndDate = FirstWeekDate(CurrDate.Date);
    List<Event> appointmentList = new NORTHWNDEntities().Events.ToList();
    switch (CurrentView)
    {
        case "day":
            StartDate = CurrentDate;
            EndDate = CurrentDate;
            break;
        case "week":
            EndDate = EndDate.AddDays(7);
            break;
        case "workweek":
            EndDate = EndDate.AddDays(5);
            break;
        case "month":
            StartDate = CurrDate.Date.AddDays(-CurrDate.Day + 1);
            EndDate = StartDate.AddMonths(1);
            break;
    }
    appointmentList = new NORTHWNDEntities().Events.ToList().Where(app =>
    ((Convert.ToDateTime(app.StartTime).Date >= Convert.ToDateTime(StartDate.Date)) &&
    (Convert.ToDateTime(app.EndTime).Date <= Convert.ToDateTime(EndDate.Date)))).ToList();
    return appointmentList;
}

internal static DateTime FirstWeekDate(DateTime CurrentDate)
{
    try
    {
        DateTime FirstDayOfWeek = CurrentDate;
        DayOfWeek WeekDay = FirstDayOfWeek.DayOfWeek;
        switch (WeekDay)
        {
            case DayOfWeek.Sunday:
                break;
            case DayOfWeek.Monday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-1);
                break;
            case DayOfWeek.Tuesday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-2);
                break;
            case DayOfWeek.Wednesday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-3);
                break;
            case DayOfWeek.Thursday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-4);
                break;
            case DayOfWeek.Friday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-5);
                break;
            case DayOfWeek.Saturday:
                FirstDayOfWeek = FirstDayOfWeek.AddDays(-6);
                break;
        }
        return (FirstDayOfWeek);
    }
    catch
    {
        return DateTime.Now;
    }
}

{% endhighlight %}
