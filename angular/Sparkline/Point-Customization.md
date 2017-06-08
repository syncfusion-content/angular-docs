---
layout: post
title: Point Customization
description: Learn how to customize points in Sparkline.
platform: Angular
control: Sparkline
documentation: ug
---

## Point Customization

You can customize points by initializing the point colors. The customization options allow you to differentiate the [`first`], [`last`], [`highest`], [`lowest`], and [`negative`] points. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}

<ej-sparkline id="sparklinecontainer" negativePointColor="red" highPointColor="blue" lowPointColor="orange" startPointColor="green" endPointColor="green">          
                               
</ej-sparkline>

{% endhighlight %}

![](Point-Customization_images/Point-Customization_img1.png)