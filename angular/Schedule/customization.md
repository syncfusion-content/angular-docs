---
title: Schedule - Customization	
description: Customization of working hours, date, and appointment window
platform: Angular
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

## Appointment Window Customization

It is possible to use the custom appointment window option to design it with the user-required extra fields apart from the other default available fields. To make use of the customized appointment window, it is necessary to use the `appointmentWindowOpen` event within which the display of default appointment window is prevented.

The following code example lets you create the custom appointment window (using recurrence editor feature) with a single extra field for defining the appointment type.

{% highlight html %}

<ej-schedule id="Schedule1" width="100%" height="525px" [currentDate]=currentDate [appointmentSettings.dataSource]=dataSource
    (appointmentWindowOpen)="onAppointmentWindowOpen($event)">
</ej-schedule>

<ej-dialog width="600px" height="auto" [showOnInit]="false" [enableModal]="true" title="Appointment Window" [enableResize]="false"
    (close)="clearFields($event)" id="customWindow" style="display: none">
    <div id="appWindow">
        <form id="custom">
            <table width="100%" cellpadding="5">
                <tbody>
                    <tr style="display: none">
                        <td>
                            Id:
                        </td>
                        <td colspan="2">
                            <input id="customId" type="text" name="Id" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Subject:
                        </td>
                        <td colspan="2">
                            <input id="subject" type="text" value="" name="Subject" style="width: 100%" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            Description:
                        </td>
                        <td colspan="2">
                            <textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            StartTime:
                        </td>
                        <td>
                            <input id="StartTime" ej-datetimepicker width="150" type="text" value="" name="StartTime" />
                        </td>
                    </tr>
                    <tr>
                        <td>
                            EndTime:
                        </td>
                        <td>
                            <input id="EndTime" ej-datetimepicker width="150" type="text" value="" name="EndTime" />
                        </td>
                    </tr>
                    <tr>
                        <td>Appointment Type:</td>
                        <td><input type="text" ej-dropdownlist [dataSource]="appointmentType" fields.text="text" fields.id="id"
                                fields.value="text" id="AppointmentType" /></td>
                    </tr>
                    <tr>
                        <td colspan="3">
                            <div class="customcheck">AllDay:</div>
                            <div class="customcheck">
                                <input id="allDay" type="checkbox" name="AllDay" (change)="allDayCheck($event)" />
                            </div>
                            <div class="customcheck">Recurrence:</div>
                            <div>
                                <input id="recurrence" type="checkbox" name="Recurrence" />
                            </div>
                        </td>
                    </tr>
                    <tr id="summary" style="display:none;">
                        <td colspan="3">
                            <div class="recSummary">Summary:</div>
                            <div>
                                <label id="recSummary" name="Summary"></label>
                            </div>
                        </td>
                    </tr>
                    <tr id="edit" style="display:none;">
                        <td colspan="3">
                            <div><a id="recedit" (click)="recurrenceRule()">Edit</a></div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </form>
        <div>
            <button type="button" (ejclick)="cancel($event)" ej-button width="85px" text="Cancel" id="btncancel" style="float:right;margin-right:20px;margin-bottom:10px;"></button>
            <button type="button" (ejclick)="save($event)" ej-button width="85px" text="Submit" id="btnsubmit" style="float:right;margin-right:20px;margin-bottom:10px;"></button>
        </div>
    </div>
    <div id="recWindow" style="display: none">
        <div id="recurrenceEditor"></div>
        <br />
        <div>
            <input ej-button (ejclick)="onRecurrenceClick($event)" text="Cancel" type="button" id="recCancel" />
            <input ej-button (ejclick)="onRecurrenceClick($event)" text="Submit" type="button" id="recSubmit" />
        </div>
    </div>
</ej-dialog>

{% endhighlight %}

The styles to be applied for the controls within the custom appointment window are as follows.

{% highlight html %}

    .customcheck {
    float: left;
    margin-right: 10px;
    }
	
    .error {
    background-color: #FF8A8A;
    }
	
    #custom table td {
    padding:5px;
    }

{% endhighlight %}

On clicking the **Submit** button within the Custom Appointment window, the following function gets executed – which will validate the appointment fields and then save it appropriately.

{% highlight ts %}

import { Component, ViewEncapsulation } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/schedule/schedule.component.html',
    styleUrls: ['src/schedule/schedule.component.css'],
    encapsulation: ViewEncapsulation.None
})
export class ScheduleComponent {
    public dataSource;
    public currentDate: Date;
    public appointmentType;
    constructor() {
        this.currentDate = new Date(2017, 11, 5);
        this.dataSource = [{
            Id: 101,
            Subject: "Talk with Nature",
            StartTime: new Date(2017, 11, 5, 10, 0),
            EndTime: new Date(2017, 11, 5, 11, 0)
        }];
        this.appointmentType = [{
            text: "Tentative",
            id: 1
        }, {
            text: "Busy",
            id: 3
        }, {
            text: "Free",
            id: 5
        }, {
            text: "Out Of Office",
            id: 7
        }];
    }
    public recurRule;
    // This function executes before the default appointment window opens
    onAppointmentWindowOpen(args: any): void {
        args.cancel = true; // prevents the display of default appointment window
        // defining recurrence editor control to be used as custom appointment window
        $("#recurrenceEditor").ejRecurrenceEditor({ selectedRecurrenceType: 0, frequencies: ["daily", "weekly", "monthly", "yearly", "everyweekday"] });
        $("#recurrence").ejCheckBox({ change: this.recurCheck });
        var schObj = $("#Schedule1").data("ejSchedule");
        // When double clicked on the Scheduler cells, fills the StartTime and EndTime fields appropriately
        $("#StartTime").ejDateTimePicker({ value: args.startTime });
        $("#EndTime").ejDateTimePicker({ value: args.endTime });
        $("#recWindow").css("display", "none");
        $("#appWindow").css("display", "");
        if (!ej.isNullOrUndefined(args.target)) {
            // When double clicked on the Scheduler cells, if the target is all day or month cells – only then enable check mark on the all day checkbox
            if ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23))
                $("#allDay").prop("checked", true);
            else
                args.model.currentView == "month" ? $("#allDay").prop("checked", true) : $("#allDay").prop("checked", false);
            // If the target is all day or month cells – disable the StartTime and EndTime fields
            $("#StartTime,#EndTime").ejDateTimePicker({
                enabled: ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23) || $(args.target.currentTarget).hasClass("e-monthcells") || args.model.currentView == "month") ? false : true
            });
        }
        // If double clicked on the appointments, fill the custom appointment window fields with appropriate values.
        if (!ej.isNullOrUndefined(args.appointment)) {
            $("#customId").val(args.appointment.Id);
            $("#subject").val(args.appointment.Subject);
            $("#StartTime").ejDateTimePicker({ value: new Date(args.appointment.StartTime) });
            $("#EndTime").ejDateTimePicker({ value: new Date(args.appointment.EndTime) });
            // Fills the Appointment type dropdown with its value
            var value = args.appointment.AppointmentType;
            $("#AppointmentType").ejDropDownList("clearText");
            $("#AppointmentType").ejDropDownList({
                text: value,
                value: value
            });
            $("#allDay").prop("checked", args.appointment.AllDay);
            $("#recurrence").ejCheckBox({ checked: args.appointment.Recurrence });
            if (args.appointment.Recurrence) {
                $("#edit").css("display", "");
                $("#recSummary").html(args.appointment.RecurrenceRule);
                $("#summary").css("display", "");
                var recObj = $("#recurrenceEditor").ejRecurrenceEditor('instance');
                recObj._recRule = args.appointment.RecurrenceRule; // app recurrence rule is stored in Recurrence editor object
                recObj.recurrenceRuleSplit(args.appointment.RecurrenceRule, args.appointment.recurrenceExDate); //splitting the recurrence rule
                recObj.showRecurrenceSummary(args.appointment.Id); // updating the recurrence rule in Recurrence editor
            }
        }
        $("#customWindow").ejDialog("open");
    }

    save() {
        // checks if the subject value is not left blank before saving it.
        if ($.trim($("#subject").val()) == "") {
            $("#subject").addClass("error");
            return false;
        }
        var obj = {};
        var formElement = $("#customWindow").find("#custom").get(0);
        // looping through the custom form elements to get each value and form a JSON object
        for (var index = 0; index < formElement.length; index++) {
            var columnName = formElement[index].name, $element = $(formElement[index]);
            if (columnName != undefined) {
                if (columnName != "" && obj[columnName] == null) {
                    var value = formElement[index].value;
                    if (columnName == "Id" && value != "") {
                        value = parseInt(value);
                    }
                    if ($element.hasClass("e-datetimepicker")) {
                        value = new Date(value);
                    }
                    if (formElement[index].type == "checkbox") {
                        value = formElement[index].checked;
                    }
                    obj[columnName] = value;
                }
            }
        }
        obj["RecurrenceRule"] = (obj["Recurrence"]) ? this.recurRule : null;
        var appTypeObj = $("#AppointmentType").data("ejDropDownList");
        obj["AppointmentType"] = appTypeObj.getSelectedValue();
        $("#customWindow").ejDialog("close");
        var schObj = $("#Schedule1").data("ejSchedule");
        schObj.saveAppointment(obj);
        this.clearFields();
    }

    // This function executes when the cancel button in the custom appointment window is pressed.
    cancel(): void {
        this.clearFields();
        $("#customWindow").ejDialog("close");
    }

    // Clears all the field values of the custom window after saving appointments
    clearFields(): void {
        $("#customId").val("");
        var recObj = $("#recurrenceEditor").ejRecurrenceEditor('instance');
        recObj.clearRecurrenceFields();
        $("#subject").val("");
        $("#AppointmentType").val("");
        $("#recSummary").html("");
        $("#summary").css("display", "none");
        $("#recurrence").ejCheckBox({ checked: false });
        $("#edit").css("display", "none");
        $("#StartTime,#EndTime").ejDateTimePicker({ enabled: true });
    }

    // This function executes when the recurrence checkbox is checked in the custom appointment window
    recurCheck(args: any): void {
        if (args.isInteraction) {
            if (args.isChecked) {
                $("#recWindow").css("display", "");
                $("#appWindow").css("display", "none");
                $("#edit").css("display", "");
            } else {
                $("#recWindow").css("display", "none");
                $("#edit").css("display", "none");
                $("#recSummary").html("");
                $("#summary").css("display", "none");
            }
        }
    }

    // This function executes when the All-day checkbox is checked in the custom appointment window
    allDayCheck(): void {
        // Disables and sets the specific hours to the StartTime and EndTime fields, when the all-day checkbox is checked
        if ($("#allDay").prop("checked")) {
            $("#StartTime").ejDateTimePicker({
                value: new Date(new Date($("#StartTime").data("ejDateTimePicker").model.value).setHours(0, 0, 0)),
                enabled: false
            });
            $("#EndTime").ejDateTimePicker({
                value: new Date(new Date($("#EndTime").data("ejDateTimePicker").model.value).setHours(0, 0, 0)),
                enabled: false
            });
        } else {
            $("#StartTime").ejDateTimePicker({
                enabled: true
            });
            $("#EndTime").ejDateTimePicker({
                enabled: true
            });
        }
    }

    // This function executes when the submit/cancel button in the recurrence editor window is pressed.
    onRecurrenceClick(args: any): void {
        if ($(args.e.currentTarget).attr("id") === "recSubmit") {
            var recObj = $("#recurrenceEditor").ejRecurrenceEditor('instance');
            recObj.closeRecurPublic();
            this.recurRule = recObj._recRule;
            $("#recSummary").html(this.recurRule);
        } else {
            if (($(args.e.currentTarget).attr("id") === "recCancel")) {
                if ($("#recSummary").html() === "") {
                    $("#edit").css("display", "none");
                    $("#recurrence").ejCheckBox({ checked: false });
                } else {
                    $("#recurrence").ejCheckBox({ checked: true });
                }
            }
        }
        $("#recWindow").css("display", "none");
        $("#appWindow").css("display", "");
        if ($("#recSummary").html() !== "") {
            $("#summary").css("display", "");
        }
    }

    // This function executes when the Edit anchor tag in the edit appointment window is clicked.
    recurrenceRule(): void {
        $("#recWindow").css("display", "");
        $("#appWindow").css("display", "none");
    }
}

{% endhighlight %}

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
            <td class="name">empty td</td>
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
