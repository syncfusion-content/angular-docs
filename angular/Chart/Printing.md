---
layout: post
title: Printing option in Essential Angular Chart Control | Syncfusion
description: Learn here about printing support in Syncfusion Essential Angular Chart Control, its elements, and more.
form: Angular
control: Chart
documentation: ug
---

# Printing Chart in Angular Chart
The rendered chart can be printed directly from the browser by calling the public method **print**. ID of the chart div element must be passed as argument to that method.

{% highlight html %}

<button type="button" onclick="print()" ></button> 
<ej-chart id="container">
</ej-chart>
<script>
function print() {
var chartObj = $("#container").ejChart("instance");
chartObj.print("container");
        }
</script>
</body>

{% endhighlight %}

This print method can be called by performing any action on the web page. For example, by clicking a button. While calling the print method in chart, print preview will be displayed in the browser.

![Angular Chart multiple chart](Printing_images/Printing_img1.png)

[Click](http://ng2jq.syncfusion.com/#/chart/export) here to view the Printing chart online demo sample

## Printing Multiple chart

Multiple charts in a web page can be printed together. For printing multiple charts, ID of the chart div elements have to be passed as shown in the below code 


{% highlight html %}

<button type="button" onclick="print()" ></button> 
<ej-chart id="container1">
</ej-chart>
<ej-chart id="container2">
</ej-chart>
<script>
function print() {
var chartObj = $("#container1").ejChart("instance");
chartObj.print("container1","container2");
        }
</script>
</body>

{% endhighlight %}

The Print preview of multiple Charts is shown below 

![Angular Chart page setup](Printing_images/Printing_img2.png)

## Page Setup

Some of print options are not configurable through JavaScript code. You need to customize layout, paper size, margins options through browser's page setup dialog. Please find the following guidelines link to browser page setup.

* [Chrome](https://support.google.com/chrome/answer/1379552?hl=en)
* [Firefox](https://support.mozilla.org/en-US/kb/how-print-web-pages-firefox)
* [Safari](http://www.mintprintables.com/print-tips/adjust-margins-osx/)
* [IE](http://www.helpteaching.com/help/print/index.htm) 

