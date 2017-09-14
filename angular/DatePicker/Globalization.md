---
layout: post
title: Globalization and Localization
description: Globalize formatting and Localize strings in DatePicker  
platform: js
platform: Angular
control: DatePicker
documentation: ug
---
# Globalization

DatePicker has been provided with Built-in localization support, so that it will be able adapt based on culture specific locale defined for it. 

More than 350 culture specific files are available to localize the date. 

N> Seven culture-specific script files are available in the below specified location. For all other culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

Set German culture to DatePicker at initialization.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker buttonText="current date" watermarkText="enter date value" locale="de-DE"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  start: number;
  constructor() {
    ej.DatePicker.Locale['de-DE'] = {
        watermarkText: "Zeitraum auswählen",
        buttonText: 'Heute'
    };
  }
}

{% endhighlight %}

## Watermark and Today Button Text

By default DatePicker input has **“select date”** as watermark text, you can also change this value by using watermarkText property. Also there’s a today button in DatePicker calendar which allows you to quick select the current date and its value can be changed by using **‘buttonText’** property.

{% highlight html %}

    <div align="center">
    <input type="text" id="datepick" ej-datepicker buttonText="current date" watermarkText="enter date value"/>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: './rtl.component.html'
})
export class RTLComponent {
  constructor() {
  }
}

{% endhighlight %}

Based on culture specific, only date gets localized but by changing the watermark and button text, you can completely localize the DatePicker UI too.

Refer below code example to update those value based some culture say for example English and German.

{% highlight javascript %}

    ej.DatePicker.Locale['en-US'] = {
        watermarkText: "Select date",
        buttonText: 'Today'
    };

    ej.DatePicker.Locale['de-DE'] = {
        watermarkText: "Zeitraum auswählen",
        buttonText: 'Heute'
    };

{% endhighlight %}

