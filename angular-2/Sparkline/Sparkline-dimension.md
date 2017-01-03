---
layout: post
title: Sparkline size
description: Learn how to set Sparkline size and make it responsive. 
platform: angular2
control: Sparkline
documentation: ug
---

##Sparkline Dimensions

You can set the size directly on the Sparkline or to the container of the sparkline. When you do not specify the size, it takes 30px as the height and 50px as its width, by default.

## Set size for the container

You can customize the Sparkline dimension by setting the width and height for the container element.

{% highlight html %}

<ej-sparkline id="sparklinecontainer" style="width:820px;height:500px;">          
                               
</ej-sparkline>

{% endhighlight %} 

![](Sparkline-Dimensions_images/Sparkline-Dimensions_img1.png)

## Set size in pixels 

You can also set the Sparkline dimension by using the [`size`] property of the Sparkline.

{% highlight html %}

<ej-sparkline id="sparklinecontainer" size.width="170px" size.height="80px">          
                               
</ej-sparkline>

{% endhighlight %}

## Responsive Sparkline

To resize the Sparkline when the browser or the sparkline container is resized, set the [`isResponsive`] property to **true**, where the sparkline adapts to the changes in size of the container. 

{% highlight html %}

<ej-sparkline id="sparklinecontainer" [isResponsive]="true">          
                               
</ej-sparkline>

{% endhighlight %} 
