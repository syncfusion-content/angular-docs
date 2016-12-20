---
layout: post
title: Frames
description: frames
platform: angular2
control: Digital Gauge
documentation: ug
---

# Frames

## Inner and Outer Width Customization

**Frames** are space that enclose the **Digital Gauge**. The inner width of the **Frame** is the distance between the canvas element and the frame. The outer width is the distance from the frame. The code example to set frame’s **innerWidth** and **outerWidth** is as follow.

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" value="WELCOME" [frame.innerWidth]=6 [frame.outerWidth]=10>
</ej-digitalgauge>

{% endhighlight %}

Execute the above code examples to render the **Digital****Gauge** as follows.

![](Frames_images/Frames_img1.png)



## Setting Background Image

For a better appearance, you can set the **background****image** for the **Digital Gauge** using the property **backgroundImageUrl.** 

{% highlight html %}

<ej-digitalgauge id="DigitalGauge1" value="RADAR" frame.backgroundImageUrl="board3.jpg" [items]="[{position: {x: 95,y: 10}}]">
</ej-digitalgauge>

{% endhighlight %}


Execute the above code examples to render the **Digital Gauge** as follows.

![](Frames_images/Frames_img2.png)

