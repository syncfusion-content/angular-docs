---
layout: post
title: Miscellaneous
description: Configure start day of week, step month, and enable/disable
platform: Angular
control: DatePicker
documentation: ug
---
# Miscellaneous 

## Start Day

By default DatePicker calendar starts with “Sunday” and ends with “Monday”. You can redefine this start day by using startDay property.

Refer below code to start Wednesday as start day. 

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value" [startDay]="start"/>
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
  start: number;
  constructor() {
    this.value = Date();
    this.start = 2;
  }
}

{% endhighlight %}

## Step Months

DatePicker calendar allows you to quick navigate back and forth from one month to previous or next month by clicking the arrow button. By default it’s navigate one by one month. You can also navigate by skipping months in odd or even or any count by using stepMonths property. 

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(ngModel)]="value" [stepMonths]="start"/>
    </div>

{% endhighlight %}

{% highlight html %}
  
import { Component } from '@angular/core';

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  value: string;
  start: number;
  constructor() {
    this.value = Date();
    this.start = 2;
  }
}

{% endhighlight %}

## Read Only

You can make DatePicker as read only by setting readOnly property as true. It allows only to read the value and it can’t be changed by interaction.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(readOnly)]="read"/>
    </div>

{% endhighlight %}

{% highlight html %}
  
import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
    read: boolean;
  constructor() {
      this.read = true;
  }
}

{% endhighlight %}

## Enable or Disable

You can enable or disable the DatePicker textbox by using enabled property. In inline mode DatePicker calendar also gets enabled or disabled. 

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker [(enabled)]="enable"/>
    </div>

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
    this.enable = false;
  }
}

{% endhighlight %}

