---
layout: post
title: Interaction-and-Animation
description: interaction and animation
platform: angular2
control: Linear Gauge
documentation: ug
---

# Interaction and Animation

* **Linear Gauge** control contains **Interaction** feature. You can use this interaction feature to change the pointer values manually either by clicking or dragging the pointer over the **Gauge.** It dynamically changes the value of pointer when dragged. To Enable/Disable the user interaction you can use the **readOnly** Boolean property. The user interaction option is enabled when you set **readOnly** property as false. By default it holds the true value.

* **Linear Gauge** contains another attractive concept called **Animation**. The animation option enables the movement of the pointer from the minimum value to the current value. You can use animation option to change the pointer value dynamically. You can enable/ disable it using **enableAnimation** property. To enable animation set **enableAnimation** to "true". 

* By default it holds the true value. You can control the speed of the pointer during animating using **animationSpeed**. It is a numerical value that holds the time in milliseconds. That is when setting value is 1000, it is considered as 1 second.


{% highlight html %}

<ej-lineargauge id="lineargauge" [value]=78 [enableAnimation]="true" [animationSpeed]=1000 [readOnly]="false" >
    <e-scales>
       <e-scale [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
           <e-markerpointers>
              <e-markerpointer  [width]="10" [length]=10 backgroundColor="grey" [distanceFromScale]=-12></e-markerpointer>
           </e-markerpointers>	
          <e-ticks>
              <e-tick type="majorinterval" [width]="2" color="#8c8c8c" [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
              <e-tick type="minorinterval" [height]="6" [width]="1" color="#8c8c8c" [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-lineargauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Interaction-and-Animation_images/Interaction-and-Animation_img1.png)



