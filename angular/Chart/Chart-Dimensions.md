---
layout: post
title: Chart Dimension in Angular Chart Control | Syncfusion
description: Learn here about chart dimensions support in Syncfusion Essential Angular Chart Control, its elements, and more.
platform: Angular
control: Chart
documentation: ug
---

# Chart Dimensions in Essential Angular Chart

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

You can also set the chart dimension by using the `size` property of the chart. 

{% highlight html %}

<ej-chart id="chartcontainer" size.width="600" size.height="450">
</ej-chart>

{% endhighlight %}

![Set size in Angular Chart](Chart-Dimensions_images/Chart-Dimensions_img1.png)


## Setting size relative to the container size

You can specify the chart size in percentage by using the `size` property. The chart gets its dimension with respect to its container.

N> Chart is using custom tag for rendering. For custom tag, default display style attribute will not be applied. So, you need to specify chart container display style as `block` to get the actual size.

{% highlight html %}

<ej-chart id="chartcontainer" style="display:block; width:700px; height:500px" size.width="80%" size.height="90%">
</ej-chart>


{% endhighlight %}

![Responsive chart in Angular Chart](Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the `isResponsive` property to **true**, where the chart adapts to the changes in size of the container.

{% highlight html %}

<ej-chart id="chartcontainer" [isResponsive]="true">
</ej-chart>

{% endhighlight %} 
