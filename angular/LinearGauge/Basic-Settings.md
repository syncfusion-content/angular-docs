---
layout: post
title: Basic-Settings
description: basic settings
platform: Angular
control: Linear Gauge
documentation: ug
---

# Basic Settings

## Adding Dimension

* The basic customization for any control is setting the dimension. Here dimension refers the two major attributes, height and width. The height and width assigned in the control will render the canvas element in the given size. 

* The value attribute is used to set all pointer value in the Linear Gauge control. The attributes, minimum and maximum value are used to set the minimum value and maximum value for all the scales exist in the Linear Gauge control.


{% highlight html %}

<ej-lineargauge id="lineargauge" [height]="500" [width]="300" [minimum]=10 [maximum]=110 [value]=78>
    <e-scales>
       <e-scale backgroundColor="transparent" [showMarkerPointers]="false" [showBarPointers]="true"
              [border]="{ color: 'transparent', width: 0 }">
           <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey"></e-barpointer>
           </e-barpointers>	
          <e-ticks>
              <e-tick type="majorinterval" [width]="2" color="#8c8c8c" 
                                  [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
              <e-tick type="minorinterval" [height]="6" [width]="1" color="#8c8c8c" 
                                  [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-lineargauge>

{% endhighlight %}

Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img1.png)



## Adding frame

* Frame is the element that decides the appearance of the **Linear Gauge**. You can customize it by using the object called **frame.** It contains frame inner width, frame outer width and frame background image URL properties. 

* The **innerWidth** of the frame defines the distance between the canvas element and the frame and the **outerWidth** refers to distance from the frame. **backgroundUrl** is used to set the background image for the frame.


{% highlight html %}

<ej-lineargauge id="lineargauge" [height]="500" [width]="300" [minimum]=10 [maximum]=110 
                                   [value]=80 [frame.innerWidth]=8 [frame.outerWidth]=10 
                        frame.backgroundImageUrl="../images/gauge/Gauge_linear_light.png" >
    <e-scales>
       <e-scale backgroundColor="transparent" [showMarkerPointers]="false" [showBarPointers]="true"
        [border]="{ color: 'transparent', width: 0 }">
           <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey"></e-barpointer>
           </e-barpointers>	
          <e-ticks>
              <e-tick type="majorinterval" [width]="2" color="#8c8c8c" 
                               [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
              <e-tick type="minorinterval" [height]="6" [width]="1" color="#8c8c8c" 
                               [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-lineargauge>

{% endhighlight %}

Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img2.png)



## Appearance

* The attribute orientation is used to render the Linear Gauges either in horizontal position or vertical position.You can set the background color for the Linear Gauge for better appearance using the backgroundColor property. borderColor specifies the border color of the Linear Gauge. You can also add gradient effects to Linear Gauge with the help of pointerGradient1 and pointerGradient2 attribute.

* Theme is the basic property of any control. It is used to set the theme for Linear Gauge. There are two types of themes used for Linear Gauge such as

 * flatlight

 * flatdark


{% highlight html %}

<ej-lineargauge id="lineargauge" [height]="100" [width]="400" [minimum]=10 [maximum]=110 
             [value]=80 orientation="Horizontal" labelColor="Black" 
             frame.backgroundImageUrl="../images/gauge/Gauge_linear_light.png" theme="flatlight" >
    <e-scales>
       <e-scale backgroundColor="transparent" [showMarkerPointers]="false" [showBarPointers]="true"
                                                     [border]="{ color: 'transparent', width: 0 }">
           <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey"></e-barpointer>
           </e-barpointers>	
          <e-ticks>
              <e-tick type="majorinterval" [width]="2" color="#8c8c8c" 
                           [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
              <e-tick type="minorinterval" [height]="6" [width]="1" color="#8c8c8c" 
                           [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-lineargauge>

{% endhighlight %}


Execute the above code to render the following output.

![](Basic-Settings_images/Basic-Settings_img3.png)



## Responsive 

* For any display devices, the control is to be rendered based on the space in that device. The control must be responsive. For this purpose resizing property is present in **Linear Gauge** control. 

* The **Linear Gauge** renders with the specified value. When the browser changes its size, the canvas element checks the dimension with its parent element and if there are any changes in parent dimension, gauge control also changes the dimension based on its parent changes. You can enable this feature using **isResponsive** property**.**


{% highlight html %}

<ej-lineargauge id="lineargauge" [height]="100" [width]="400" labelColor="Black" 
                frame.backgroundImageUrl="../images/gauge/Gauge_linear_light.png" 
                theme="flatlight" [isResponsive]="true" >
    <e-scales>
       <e-scale backgroundColor="transparent" direction="clockwise" [showMarkerPointers]="false" 
                         [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
           <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey"></e-barpointer>
           </e-barpointers>	
          <e-ticks>
              <e-tick type="majorinterval" [width]="2" color="#8c8c8c" 
                                        [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
              <e-tick type="minorinterval" [height]="6" [width]="1" color="#8c8c8c" 
                                        [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
        </e-ticks>
       </e-scale>
    </e-scales>
</ej-lineargauge>

{% endhighlight %}

Execute the above code to render the following output.


![](Basic-Settings_images/Basic-Settings_img4.png)



