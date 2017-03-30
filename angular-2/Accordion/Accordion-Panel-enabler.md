---
layout: post
title: Accordion-Panel-enabler
description: accordion panel enabler
platform: Angular2
control: Accordion 
documentation: ug
---

# Accordion Panel Enabler

## Enable/Disable widget

**You can enable or disable the Accordion** widget on initial rendering using the [enabled](https://help.syncfusion.com/api/js/ejaccordion#members:enabled) property. By default **enabled** property is set to true and the **Accordion** panels are always active. 

The following steps explain that how to disable the **Accordion** widget

In the `Accordion` component HTML file add the below given code.

{% highlight html %}

<ej-accordion [enabled]="false">
<h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>
 
{% endhighlight %}

Output for disabled Accordion control is as follows.

![](Accordion-Panel-enabler_images/Accordion-Panel-enabler_img1.png) 

## Enable panel items

You can enable the **Accordion** widget items on initial loading using [enabledItems](https://help.syncfusion.com/api/js/ejaccordion#members:enableditems) property. This property takes array of indices whose panel needs to be enabled in **Accordion** widget. 

The **disabledItems** property disables the **Accordion** items based on the index. This takes array of indices whose panel is to be disabled. 

### Enabling accordion panel items

The following steps explains you on how to enable the panel items in **Accordion** widget

In the `Accordion` component HTML file add the below given code.

{% highlight html %}
   
<ej-accordion [enableMultipleOpen]="true" [enabledItems]="enableditems" [disabledItems]="disableditems" [selectedItemIndex]="1">
<h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}

Create the Accordion control as follows.

{% highlight html %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/accordion/accordion.component.html',
})
export class AccordionComponent {
    enableditems: int;
    disableditems: int;
    constructor() {
        this.enableditems = [1, 2];
        this.disableditems = [0];
    }
}

{% endhighlight %}

Output for Accordion control with some enabled and disabled items, where first panel is disabled and it can’t be expanded or collapsed is as follows.


![](Accordion-Panel-enabler_images/Accordion-Panel-enabler_img2.png)