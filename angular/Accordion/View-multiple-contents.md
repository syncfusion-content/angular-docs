---
layout: post
title: View-multiple-contents
description: view multiple contents
platform: Angular
control: Accordion 
documentation: ug
---

# View multiple contents

By default **Accordion** allows only one panel to be in expanded state. But you can enable multiple panels in expanded state by setting [enableMultipleOpen](https://help.syncfusion.com/api/js/ejaccordion#members:enablemultipleopen) to **true.**

## Enabling multiple panel open

The following code helps you to enable multiple panel for **Accordion**.

{% highlight html %}   

<ej-accordion [enableMultipleOpen]="true">
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

Following screenshot is the output for Accordion control on enableMultipleOpen set to true.

![](View-multiple-contents_images/View-multiple-contents_img1.png)