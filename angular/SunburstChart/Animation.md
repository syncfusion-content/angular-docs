---
layout: post
title: Animation
description: Learn how to animate the SunburstChart .
platform: Angular
control: SunburstChart
documentation: ug
---

# Animation

Sunburst chart allows you to animate the chart segments. You can enable animation using **enableAnimation** property. 

{% highlight html %}

<ej-sunburstchart id="sunburst"                           
                  [enableanimation]="true">
</ej-sunburstchart>

{% endhighlight %}


## Animation Types 
Sunburst chart provide options to animate the chart segments in different ways using **e-animationtype** property.
FadeIn – It gradually changes opacity of the chart segment.
Rotation – During an animation, control rotate from 0 to 360 angle.

### Fade In

The Fade In animation is enabled as follows 

{% highlight html %}

<ej-sunburstchart id="sunburst"                           
                  [enableAnimation]="true" [enableAnimation.type]="fadeIn">
</ej-sunburstchart>


{% endhighlight %}

![](Animation_images/Animation_img1.gif)




### Rotation

The following example shows how to enable rotation animation in ejSunburstChart

{% highlight html %}

<ej-sunburstchart id="sunburst"                           
                  [enableAnimation]="true" [enableAnimation.type]="rotation">
</ej-sunburstchart>

{% endhighlight %}

![](Animation_images/Animation_img2.gif)


[Click](http://ng2jq.syncfusion.com/#/sunburst/animation) here to view the online demo sample of  Animation in  the Sunburst Chart.
