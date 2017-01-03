---
layout: post
title: Axis Customize
description: Learn how to customize axis in Sparkline.
platform: angular2
control: Sparkline
documentation: ug
---

## Axis Customize 

The Sparkline axis can be collapsed using visible property in [`axisLineSetting`] and this not applicable for win-loss. You can customize [`color`], [`width`] and [`dash array`] of axis line.

 {% highlight html %}
 
<ej-sparkline id="sparklinecontainer" size.width="170px" [axisLineSettings.visible]="true" axisLineSettings.color="#ff14ae">    

</ej-sparkline>

{% endhighlight %}

![](Axis-Customize_images/Axis-Customize_img1.png)