---
layout: post
title: State-Persistence
description: state persistence
platform: Angular2
control: Accordion 
documentation: ug
---

# State Persistence

**Accordion** widget can store the model value in the browser cookies and on every time after initial rendering, the control get the model from the cookie only. Using [enablePersistence](https://help.syncfusion.com/api/js/ejaccordion#members:enablepersistence) property you can store the model value in cookies. Thus, when any changes are made dynamically then those values are updated in cookies. On refreshing the page, the past state of the **Accordion** control is maintained in cookie and control is rendered from it.

## Configure state persistence of Accordion panel

The following code helps to enable state maintenance for **Accordion**.

{% highlight html %}

<ej-accordion [enablePersistence]="true">
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


Output after page refresh maintaining the previous state of Accordion widget is as follows.


![](State-Persistence_images/State-Persistence_img1.png)