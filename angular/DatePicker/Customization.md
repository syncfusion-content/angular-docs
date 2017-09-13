---
layout: post
title: DatePicker Customization
description: DatePicker customization such as dimension, highlight dates, other months, etc.
platform: Angular
control: DatePicker
documentation: ug
---
# Customization

DatePicker provides more flexible way to customize the below listed properties.

## Set Dimension 

By default DatePicker has standard height and width (height: ‘30px’ and width: ’143px’). You can change this height and width by using height and width property respectively.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value"  height="50px" width="300px"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  constructor() {
    this.value = Date();
  }
}

{% endhighlight %}

Mostly dimension plays a vital role in web application to get responsive layout in all devices. DatePicker is a form control and you can make it as responsive by specifying its width as “**100%**".

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value" width="100%"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  constructor() {
    this.value = Date();
  }
}

{% endhighlight %}

## Show Footer

You can show or hide the footer of DatePicker calendar by using showFooter property. 

{% highlight html %}

     <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value" [(showFooter)]="showfooter"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  showfooter: boolean;
  constructor() {
    this.value = Date();
    this.showfooter = false;
  }
}

{% endhighlight %}

N>  Footer contains the today button to quickly navigate to the current date. By turning off it, you have to select current date by manually. 

## Show Popup Button

DatePicker textbox contains a button to open the DatePicker calendar. You can hide this DatePicker calendar button using showPopupButton value as false.

By hiding this button, you can open the DatePicker by focusing the input textbox element itself.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value"  [(showPopupButton)]="showpopupbutton"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  rtl: boolean;
  showpopupbutton: boolean;
  constructor() {
    this.value = Date();
    this.rtl = true;
    this.showpopupbutton = false;
  }
}

{% endhighlight %}

## Show Other Months

You can show or hide the other month days from DatePicker calendar by using showOtherMonths property.

{% highlight html %}

    <div align="center">  
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value"  [(showOtherMonths)]="showothermonths"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  showothermonths: boolean;
  constructor() {
    this.value = Date();
    this.showothermonths = false;
  }
}

{% endhighlight %}

## Highlight Special Date

DatePicker allows you to highlight the special dates in DatePicker calendar by using specialDates property. It receives the array of JSON data, in which the data should contain the date value, icon CSS class and tooltip as field values with any names.

And you can map those above field names to DatePicker by using fields property, which holds following members.

<table>
<tr>
<th>
Members</th><th>
Description</th></tr>
<tr>
<td>
date<br/><br/></td><td>
It specifies the mapping field of special date<br/><br/></td></tr>
<tr>
<td>
iconClass<br/><br/></td><td>
It specifies the mapping field of icon CSS class.<br/><br/></td></tr>
<tr>
<td>
tooltip<br/><br/></td><td>
It specifies the mapping field of tool tip text.<br/><br/></td></tr>
</table>

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="today"  [(specialDates)]="special" [(cssClass)]= "specialClass"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './special-dates.component.html',
  styleUrls: ['./common.component.css'], encapsulation: ViewEncapsulation.None,
})
export class SpecialDatesComponent {
  special: Object;
  year: number;
  today: any;
  month: number;
  specialClass: string;
  constructor() {
    this.specialClass = 'splClass';
    this.today = new Date();
    this.year = this.today.getFullYear();
    this.month = this.today.getMonth();
    this.special = [{ date: new Date(this.year, this.month, 8), tooltip: 'In Australia', iconClass: 'flags sprite-Australia' },
        { date: new Date(this.year, this.month, 21), tooltip: 'In France', iconClass: 'flags sprite-France' },
        { date: new Date(this.year, this.month, 17), tooltip: 'In USA', iconClass: 'flags sprite-USA' },
        { date: new Date(this.year, this.month + 1, 15), tooltip: 'In Germany', iconClass: 'flags sprite-Germany' },
        { date: new Date(this.year, this.month - 1, 22), tooltip: 'In India', iconClass: 'flags sprite-India' }
    ];
  }
}

{% endhighlight %}

