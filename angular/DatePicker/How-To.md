---
layout: post
title: How-to
description: How-to section
platform: Angular
control: DatePicker
documentation: ug
---
# How to?

## Customizing template with range selection between two DatePicker. 

You can customize the date field to emphasize the particular dates in DatePicker calendar with help of specialDates and set the date range using minDate and maxDate property. Refer the sample from the link Hotel Booking to know how to customize date with date range.

## Localize DatePicker with browser specific culture

You can get the browser culture name at page load or document ready state. Based on the culture name, DatePicker can be initiated with that specific culture value by assigning to locale property. Refer the sample from the link Browser Specific Culture to create DatePicker with browser specific culture.

## Disable specific dates to restrict user

DatePicker allows you to restrict date selection in specific range by using date range option. But you can also restrict selective date in DatePicker calendar by utilizing beforeDateCreate event. This event will get triggered at each date creation. So you can disable the selective date in this event to restrict the user.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" (beforedatecreate)="restrictDate($event)" ej-datepicker [(ngmodel)]="value" />
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './default.component.html'
})
export class DefaultComponent {
  value: string;
  constructor() {
    this.value = Date();
  }
  restrictDate(args) {
      var disableDate = new Date("09/22/2015");
      if (+args.date === +disableDate)
          args.element.addClass('e-disable');   
    }
}

{% endhighlight %}

