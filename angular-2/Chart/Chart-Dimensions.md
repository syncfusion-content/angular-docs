---
layout: post
title: Chart size
description: Learn how to set Chart size and make it responsive. 
platform: angular2
control: Chart
documentation: ug
---

# Chart Dimensions

You can set the size of the chart directly on the chart or to the container of the chart. When you do not specify the size, it takes 450px as the height and window size as its width, by default. 

## Set size for the parent container

You can customize the chart dimension by setting the width and height for the container element. 

{% highlight html %}

  <body>
        <ej-chart id="chartcontainer" style="width:620px; height:300px;">
        </ej-chart>
 </body>

{% endhighlight %}


## Set size in pixels

You can also set the chart dimension by using the [`size`] property of the chart. 

{% highlight html %}

    <ej-chart id="chartcontainer" size.width="600" size.height="450">
    </ej-chart>

{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img1.png)


## Setting size relative to the container size

You can specify the chart size in percentage by using the [`size`] property. The chart gets its dimension with respect to its container.

{% highlight html %}

  <div id="container" style="width:700px; height:500px">
      <ej-chart id="chartcontainer" size.width="80%" size.height="90%">
      </ej-chart>
 </div>


{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the [`isResponsive`] property to **true**, where the chart adapts to the changes in size of the container.

{% highlight html %}

      <ej-chart id="chartcontainer" [isResponsive]="true">
      </ej-chart>

{% endhighlight %} 
