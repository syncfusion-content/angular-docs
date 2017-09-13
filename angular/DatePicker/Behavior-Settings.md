---
layout: post
title: Behaviour Settings
description: Configure DatePicker Behaviour settings
platform: Angular
control: DatePicker
documentation: ug
---
# Behavior Settings

DatePicker has some default behavior settings which helps you to perform more operation by Built-in.

## Selected Date

DatePicker value can be selected through picking date from DatePicker calendar or you can set it by using value property.

{% highlight html %}
  
    <div class="row">
    <div class="date-align">  
	<div>
		<label class="dtlabel">End Date</label>   
		<input id="enddate" ej-datepicker [(value)]= "dtValue" (select)= "onSelectDate($event)" />
	</div>
    </div>    
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './date-range.component.html',
  styleUrls: ['./common.component.css']
})
export class DateRangeComponent {
  today: any;
  currentYear: number;
  currentMonth: number;
  currentDay: number;
  dtValue: any;
  constructor() {
      this.today = new Date();
      this.currentYear = this.today.getFullYear();
      this.currentMonth = this.today.getMonth();
      this.currentDay = this.today.getDate();
      this.dtValue = new Date(this.currentYear, this.currentMonth, this.currentDay + 7);
  }
  onSelectDate(args) {
      alert(" previous date is : " + args.prevDate + " \n selected date is : " + args.value);
  }
}

{% endhighlight %}

DatePicker allows only the valid date to be entered and it should be within the specified range. By default, strict mode is enabled in DatePicker, so it will restrict invalid date and resets to previous date if it’s not valid. To know more about strict mode refer [Strict Mode](#strict-mode).

## Date Range

DatePicker provides an option to restrict the user to pick the date from specified range of value. You can utilize this option by make use of minDate and maxDate property.

**minDate** - specifies the minimum date to be picked in DatePicker calendar by disabling below date of minDate.

**maxDate** -  specifies the maximum date to be picked in DatePicker calendar by disabling above date of maxDate. 

{% highlight html %}
     
    <div class="row">
    <div class="date-align">  
	<div>   
		<label class="dtlabel">Start Date</label>
		<input id="stdate" ej-datepicker [(value)]= "startDateValue" [(minDate)]= "minStartDate" [(maxDate)]= "maxStartDate" [(width)]= "width" (select)= "onStartSelectDate($event)" />
	</div>
	<div>
		<label class="dtlabel">End Date</label>   
		<input id="enddate" ej-datepicker [(value)]= "startDateValue" [(minDate)]= "minStartDate" [(maxDate)]= "maxStartDate" [(width)]= "width" (select)= "onEndSelectDate($event)" />
	</div>
    </div>    
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './date-range.component.html',
  styleUrls: ['./common.component.css']
})
export class DateRangeComponent {
  today: any;
  currentYearStart: number;
  currentMonthStart: number;
  currentDayStart: number;
  today1: any;
  currentYearEnd: number;
  currentMonthEnd: number;
  currentDayEnd: number;
  startDateValue: any;
  endDateValue: any;
  minStartDate: any;
  minEndDate: any;
  maxStartDate: any;
  maxEndDate: any;
  width: string;
  constructor() {
      this.width = '100%';
      this.today = new Date();
      this.currentYearStart = this.today.getFullYear();
      this.currentMonthStart = this.today.getMonth();
      this.currentDayStart = this.today.getDate();
      this.startDateValue = this.today;
      this.minStartDate = new Date(this.currentYearStart, this.currentMonthStart, this.currentDayStart - 7);
      this.maxStartDate = new Date(this.currentYearStart, this.currentMonthStart + 3, this.currentDayStart);
      this.endDateValue = new Date(this.currentYearStart, this.currentMonthStart, this.currentDayStart + 7);
      this.minEndDate = this.today;
      this.maxEndDate = new Date(this.currentYearStart, this.currentMonthStart + 3, this.currentDayStart);
  }
  onStartSelectDate(args) {
      let curDate = new Date(args.value);
      this.minEndDate =  curDate;
      this.endDateValue =  new Date(curDate.getFullYear(), curDate.getMonth(), curDate.getDate() + 7);
  }
  onEndSelectDate(args) {
      this.maxStartDate = args.value;
  }
}

{% endhighlight %}

N> You can change the ‘**minDate’** and ‘**maxDate’** value dynamically like ‘**value’** property

## Display Inline Mode

DatePicker provides an option to act as calendar by setting the displayInline property as true. In this mode the DatePicker calendar has been placed open state constantly to pick the date. 

You can make use of ‘div’ element to create DatePicker when you going for inline mode, which gives good visualization as like calendar in page instead of creating with ‘input’ element. 

{% highlight html %}

    <div align="center">
    <div id="datepick" ej-datepicker [(ngModel)]="value" [(displayInline)]="inline"> </div> <br />
    <div id="label">Selected date: {{value}}</div>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './display-inline.component.html'
})
export class DisplayInlineComponent {
  value: string;
  inline: boolean;
  constructor() {
    this.value = Date();
    this.inline = true;
  }
}

{% endhighlight %}

## Strict Mode

Strict mode in DatePicker allows you to enter valid or invalid date in input textbox, but an error class will get added to exhibit if it’s an invalid date. When you set enableStrictMode to false, DatePicker allows you to enter only the valid date or else it will resets with previous value. 

Also the valid date should be defined in specified range or else it resets to min or maximum date when the entered date is out of range

By default “**enableStrictMode**” is true, so you can enter any value other than date too, but an **error** class (**‘.** **e** **-** **error’**) will get added to wrapper to highlight the invalid date.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(enableStrictMode)]="enable"/>
    </div>
    <style>
    /* error class to highlight invalid date */
    .e-error .e-input {
        color: Red; /* highlights invalid date font color in input */
    }
    </style>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  enable: boolean;
  constructor() {
    this.enable = true;
  }
}

{% endhighlight %}

You can also override the **“** **error** **”** class to highlight when invalid date is entered.
