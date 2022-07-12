---
layout: post
title: Appearance and Styling in Angular Accordion Control | Syncfusion
description: Learn here about appearance and styling in Syncfusion Essential Angular Accordion Control, its elements, and more.
platform: Angular
control: Accordion 
documentation: ug
---

# Appearance and Styling in Angular Accordion

## Adjusting Accordion size

You can customize the **Accordion** panel height using [heightAdjustMode](https://help.syncfusion.com/api/js/ejaccordion#members:heightadjustmode) property. It can be set to **enum** values like content, fill or auto. By default **heightAdjustMode** is set to **content** so that the panel height is adjusted to the content size.

### Configure Height of Accordion panel

The following steps explains you on how to configure **Accordion** panel height.

In the `Accordion` component HTML file add the below given code.

{% highlight html %}

<ej-accordion [heightAdjustMode]="mode">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
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
    mode: string;
    constructor() {
        this.mode = "auto";
    }
}

{% endhighlight %}


Output for Accordion control when panel height is set to auto so that the maximum content height and Fill for minimum content height in all the panels is as follows.


![Angular Accordion Rounded corner](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 

## Rounded corner

You can customize the shape of the **Accordion** widget from regular rectangular shape to rounded rectangle shape enabling [showRoundedCorner](https://help.syncfusion.com/api/js/ejaccordion#members:showroundedcorner) property that is set to false by default.

### Enabling Rounded corner property

The following steps explains you in enabling the **showRoundedCorner** property for an **Accordion** control. You can refer to the below code.

{% highlight html %}

<ej-accordion [showRoundedCorner]="true">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}


Output for accordion widget when “showRoundedCorner” is set to “true” is as follows.

![Angular Accordion Customize Accordion icon](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) 

## Customize Accordion icon

**Accordion** widget allows you to customize the icons using [customIcon](https://help.syncfusion.com/api/js/ejaccordion#members:customicon) property that has two properties **header** and **selectedHeader**. By default, the classes of header and selectedHeader are e-collapse and e-expand respectively. By setting the desired CSS class names for these properties as required overrides the default icons with customized icons.

### Configuring custom icon for Accordion

The following steps explains the configuration of icon for an **Accordion** control.You can refer to the below code.

{% highlight html %}

<ej-accordion [customIcon.header]="header" [customIcon.selectedHeader]="selectedheader">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/accordion/accordion.component.html',
})
export class AccordionComponent {
    header: string;
    selectedheader: string;
    constructor() {
        this.header = "e-arrowhead-down";
        this.selectedheader = "e-arrowheadup";
    }
}

{% endhighlight %}

Output for Accordion widget with customized icons is as follows.

![Angular Accordion Animations](Appearance-and-Styling_images/Appearance-and-Styling_img3.png) 

## Animations

### Set animation

By default the **Animation** for expanding and collapsing is enabled. To remove the Animation you can set the [enableAnimation](https://help.syncfusion.com/api/js/ejaccordion#members:enableanimation) property to **false**. This restricts customizing animations as well. By default **enableAnimation** is set to **true**.

Following code disables **Animation** for **Accordion**.

{% highlight html %}

<ej-accordion [enableAnimation]="false">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}


## Expand and collapse speed

This feature allows you to set the speed for expanding and collapsing the **Accordion** panels. By default it is set to 300 in milliseconds. By configuring the animation speed you can optimize the delay in loading the panel content.

The following code sample sets value for [expandSpeed](https://help.syncfusion.com/api/js/ejaccordion#members:expandspeed) and [collapseSpeed](https://help.syncfusion.com/api/js/ejaccordion#members:collapsespeed) properties,

{% highlight html %}

<ej-accordion [expandSpeed]="600" [collapseSpeed]="1000" [collapsible]="true">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}


## Theme

You can control the style and appearance of Accordion control based on **CSS** classes. In order to apply styles to the Accordion widget, you can refer two files, **ej.widgets.core.min.css** and **ej.theme.min.css**. When you refer **ej.widgets.all.min.css** file, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.widgets.all.min.css is the combination of these two. 

By default, there are 12 themes support available for **Accordion** control namely

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark


## CSS class

**CSS** class can be used to customize the **Accordion** control appearance. Define a **CSS** class as you’re your requirement and assign the class name to [cssClass](https://help.syncfusion.com/api/js/ejaccordion#members:cssclass) property.

### Configure AutoComplete textbox using CSS class

The following steps allows you to configure **CSS** class for an **Accordion** widget.You can refer to the below code.

{% highlight html %}

<ej-accordion [cssClass]="customcss">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</ej-accordion>

{% endhighlight %}


Define CSS class for customizing the Accordion.

{% highlight css %}

<style class="cssStyles">
    .customcss {
        font-style: italic;
        text-align: justify;
    }
    .customcss span.e-icon {
        display: none !important;
    }
    .customcss h3 {
        text-decoration: underline;
        text-align: center;
    }
</style>

{% endhighlight %}


Output for Accordion with customized CSS property to hide the Accordion icon and format its content is as follows.

![Angular Accordion appearance](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)