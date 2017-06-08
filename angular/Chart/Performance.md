---
layout: post
title: Performance tips 
description: How to improve the performance of Essential Angular Chart
platform: Angular
control: Chart
documentation: ug
---

# Performance 

* When there are large number of points to load, you can enable canvas rendering mode in chart. Canvas rendering is faster than SVG because it does not involve manipulating DOM elements as much as SVG rendering.   

{% highlight html %}

<ej-chart id="chartcontainer" [enableCanvasRendering]="true">
</ej-chart>

{% endhighlight %}

* Instead of enabling data markers and labels when there are large number of data points, you can use **trackball** and **tooltip** to view point information.

## Lazy Loading

Lazy loading feature provides an effective way for loading data on demand by scrolling and viewing a smaller range of data from a larger collection.

{% highlight ts %}

this.axis = {
    scrollbarSettings: {

        // enable the scrollbar
        visible: true,
        // enable the resize option 
        canResize: true,
        range: {
            min: "2009/1/1",
            max: "2014/1/1"
        }
    }
};
{% endhighlight %}

{% highlight html %}

<ej-chart id="chartcontainer" [primaryXAxis]="axis">
</ej-chart>

{% endhighlight %}

![](Performance_images/Perform_img1.png)