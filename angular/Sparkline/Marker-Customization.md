---
layout: post
title: Markers Customization
description: Learn how to add markers to Sparkline.
platform: Angular
control: Sparkline
documentation: ug
---

## Marker Customization

You can customize markers by initializing the [`markerSettings`] property. The customization options allow you to change the [`fill`], [`width`], [`opacity`] and [`border`] for marker. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}

<ej-sparkline id="sparklinecontainer" [markerSettings.visible]="true" [markerSettings.border.width]=1 [markerSettings.width]=4 markerSettings.fill="#ff14ae">          
                               
</ej-sparkline>

{% endhighlight %}

![](Marker-Customization_images/Marker-Customization_img1.png)
