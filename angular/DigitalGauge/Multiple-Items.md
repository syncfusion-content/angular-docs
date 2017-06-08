---
layout: post
title: Multiple-Items
description: multiple items 
platform: Angular
control: Digital Gauge
documentation: ug
---

# Multiple Items 

The text in the **Digital Gauge** is positioned with position object. This object contains two attributes such as **x** and **y.** The **x** variable positions the text in the horizontal axis and **y** variable positions the text in the vertical axis.

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" with="1350" height="400" frame.backgroundImageUrl="board3.jpg"
              [items]="[{value: 'BLUE',segmentSettings: {color: 'blue'}, position: {x: 90,y: 0}},
              {value: 'RED',segmentSettings: {color: 'red'},position: {x: 90,y: 15}},
              {value: 'PINK',segmentSettings: {color: 'pink'},position: {x: 90,y: 30}}]">
</ej-digitalgauge>

{% endhighlight %}

Execute the above code example to render the **Digital****Gauge** as follows.

![](Multiple-Items_images/Multiple-Items_img1.png)

