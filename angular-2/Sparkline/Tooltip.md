---
layout: post
title: Tooltip
description: Learn how to add Tooltip to Sparkline .
platform: angular2
control: Sparkline
documentation: ug
---

## Tooltip  

A tooltip follows the pointer movement and is used to indicate the value of a point. This feature is applicable for line, column, pie, and area Sparkline. You can customize the tooltip [`fill color`], [`border`] and [`font`].

{% highlight html %}

  <ej-sparkline id="sparklinecontainer" [tooltip.visible]="true">          
                               
  </ej-sparkline>

{% endhighlight %}

![](Tooltip_images/Tooltip_img1.png)

## Tooltip Template   

HTML elements can be displayed in the tooltip by using the [`template`] option of the tooltip. The template option takes the value of the id attribute of the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the x and y values of the corresponding point.

{% highlight html %}

<div id="item" style="display: none;">
    <div>
        <div>#point.x#</div>
        <div>#point.y#</div>
    </div>
</div>

  <ej-sparkline id="sparklinecontainer" [tooltip.visible]="true" tooltip.template="item">          
                               
  </ej-sparkline>

{% endhighlight %}

![](Tooltip_images/Tooltip_img2.png)