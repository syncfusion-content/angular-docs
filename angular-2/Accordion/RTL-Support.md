---
layout: post
title: RTL-Support
description: rtl support
platform: Angular2
control: Accordion 
documentation: ug
---

# RTL Support

This feature supports to change the left-to-right alignment of the **Accordion** widget to right-to-left (**RTL**). 

## Enabling RTL Support

The following code helps you for enabling the right-to-left property for an **Accordion**.

{% highlight html %}

<ej-accordion [enableRTL]="true">
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

Output for accordion when “enableRTL” is set to “true” is as follows,

![](RTL-Support_images/RTL-Support_img1.png)