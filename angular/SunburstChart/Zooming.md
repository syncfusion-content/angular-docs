---
layout: post
title: Sunburst Zooming
description: Learn how to Zoom the SunburstChart for better data visualization
platform: Angular
control: Sunburst Chart
documentation: ug
---

# Zooming

Sunburst chart provides zooming (drill down) experience with animation for both mouse and touch enabled devices. It allows you to virtualize large sets of data into minimum data view.The zooming is achieved by using the property of `zoomSettings`

The following code shows how to initialize the zooming.

{% highlight js %}

<ej-sunburstchart  id="sunburst"   [zoomSettings.enable]="true" >
</ej-sunburstchart>

{% endhighlight %}

![](Zooming_images/Zooming_img1.gif)

## Zooming toolbar
By default, zooming toolbar will be enabled while zooming the segment.It contains both back and reset option.
You can align the zooming toolbar position by using `zoomSettings.toolbarHorizontalAlignment` and `zoomSettings.toolbarVerticalAlignment` property.


{% highlight js %}

<ej-sunburstchart  id="sunburst"  [zoomSettings.enable]="true" zoomSettings.toolbarHorizontalAlignment="left">
</ej-sunburstchart>

{% endhighlight %}

![](Zooming_images/Zooming_img2.png)

[Click](http://ng2jq.syncfusion.com/#/sunburst/zooming) here to view the Zooming sample of the  Sunburst Chart.
