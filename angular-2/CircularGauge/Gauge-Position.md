---
layout: post
title: Gauge-Position
description: gauge position
platform: angular2
control: Circular Gauge
documentation: ug
---

# Gauge Position

**Semi-circular Gauge** can be positioned within the canvas element which provides better appearance for the gauge in the canvas.

**Positioning**

Semi-circular Gauge can be positioned with the help of the attribute called gaugePosition. It is an enumerable value. You can position the gauge away from the corner with the help of the distanceFromCorner attribute. 

The possible enum values for the gaugePosition are as follows:

* Topleft

* Topcenter

* Topright

* Middleleft

* Center

* Middleright

* Bottomleft

* Bottomcenter

* Bottomright

{% highlight html %}

<div style="float: left" id="gauge1"></div>
<div id=" CoreCircularGaugehalfright "></div>

{% endhighlight %}


{% highlight html %}

 <ej-CircularGauge id="circularGauge1" backgroundColor="transparent" [width]=800 [height]=500 [radius]=120 [value]=60 [distanceFromCorner]=30
                                    frame.frameType="halfcircle" [frame.halfCircleFrameStartAngle]=270 [frame.halfCircleFrameEndAngle]=90 >
     <e-scales>
          <e-scale [startAngle]=270 [sweepAngle]="180" [radius]="160"
		                   [showScaleBar]="true" [size]="1" [maximum]="120" [majorIntervalValue]="20" [minorIntervalValue]="10" [border.width]=0.5 >
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

Execute the above code to render the following output.

![](Gauge-Position_images/Gauge-Position_img1.png)

