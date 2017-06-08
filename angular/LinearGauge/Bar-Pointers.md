---
layout: post
title: Bar-Pointers
description: bar pointers
platform: Angular
control: Linear Gauge
documentation: ug
---

# Bar Pointers

**Bar Pointer** value points out the actual value set in the **Linear Gauge** as marker pointer. You can set the values of the various bar pointer attributes such as value, width, border and color in bar pointer collection.  You can also customize the pointers to improve the appearance of gauge.

## Adding bar pointer collection

You can add Bar Pointer collection directly to the scale object. Refer the following code example.


{% highlight html %}

 <ej-lineargauge id="LinearGauge1" [value]="78" [frame.innerWidth]=8 [frame.outerWidth]=10 
                         frame.backgroundImageUrl="../images/gauge/Gauge_linear_light.png" >
   <e-scales>
        <e-scale backgroundColor="transparent" [showMarkerPointers]="false" 
                 [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
          <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey"></e-barpointer>
           </e-barpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" [distanceFromScale]="
                                                                     {x:7, y: 0 }"></e-tick>
               <e-tick type="minorinterval" [width]=1 [height]=6 color="#8c8c8c" 
                                               [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
        </e-scale>
   </e-scales>
</ej-lineargauge>

{% endhighlight %}


Execute the above code to render the following output.


![](Bar-Pointers_images/Bar-Pointers_img1.png)



## Adding bar pointer value

Bar pointer value is also important element in the **Linear Gauge** as it indicates the gauge value. Real purpose of the **Linear Gauge** is based on the pointer value. You can set the bar pointer value either directly during rendering the control or it can be achieved by public method.



{% highlight html %}

 <ej-lineargauge id="LinearGauge1">
   <e-scales>
        <e-scale backgroundColor="transparent" [showMarkerPointers]="false" 
              [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
          <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey" [value]=91 ></e-barpointer>
           </e-barpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" 
                         [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
               <e-tick type="minorinterval" [width]=1 [height]=6 color="#8c8c8c" 
                                    [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
        </e-scale>
   </e-scales>
</ej-lineargauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Bar-Pointers_images/Bar-Pointers_img2.png)

## Pointer Styles

**Appearance**

* Based on the value, the bar pointer points out the label value. You can set the bar pointer width using **width** property and you can also adjust the opacity of the pointer using **opacity** property that holds the value between 0 and 1. You can add the gradient effects to the pointer using **gradient** object. 

* The marker pointer border is modified with the object **border**. It has two border property, **color** and **width** which are used to customize the border color of the scale and border width of the marker pointer. The background color can be customized with attribute **backgroundColor**.


{% highlight html %}

 <ej-lineargauge id="LinearGauge1">
   <e-scales>
        <e-scale backgroundColor="transparent" [showMarkerPointers]="false" 
             [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
          <e-barpointers>
              <e-barpointer  [width]="5" backgroundColor="grey" [value]=91 
              backgroundColor="red" [opacity]=0.7 [border]="{ color: '#860201', width: 2 }" >
              </e-barpointer>
           </e-barpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" 
               [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
               <e-tick type="minorinterval" [width]=1 [height]=6 color="#8c8c8c" 
               [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
        </e-scale>
   </e-scales>
</ej-lineargauge>

{% endhighlight %}


Execute the above code to render the following output.



![](Bar-Pointers_images/Bar-Pointers_img3.png)

## Positioning the pointer	

* Bar pointer can be positioned with two properties such as **distanceFromScale** and **placement**. The **distanceFromScale** property defines the distance between the scale and pointer element. 

* The **placement** property is used to locate the pointer with respect to scale either inside or outside the scale or along the scale. It is an enumerable data type.


{% highlight html %}

 <ej-lineargauge id="LinearGauge1">
   <e-scales>
        <e-scale backgroundColor="transparent" [showMarkerPointers]="false" 
         [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
          <e-barpointers>
              <e-barpointer  [width]="10" backgroundColor="grey" [value]=91 
               backgroundColor="#8BABFF" [opacity]=0.7 [border]="{ color: '#860201',
                                width: 2 }" placement="near" [distanceFromScale]=20 >
              </e-barpointer>
           </e-barpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" 
                         [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
               <e-tick type="minorinterval" [width]=1 [height]=6 color="#8c8c8c"
                                   [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
        </e-scale>
   </e-scales>
</ej-lineargauge>

{% endhighlight %}



Execute the above code to render the following output.


![](Bar-Pointers_images/Bar-Pointers_img4.png)

## Multiple Bar Pointers

**Linear Gauge** can contain multiple bar pointers on it. You can use any combination and any number of pointers in a gauge. That is, a Gauge can contain any number of marker pointer and any number of bar pointers. Refer the following code example containing multiple bar pointers.

{% highlight html %}

 <ej-lineargauge id="LinearGauge1" [height]=500 [width]=300 labelColor="grey" [enableAnimation]="false">
   <e-scales>
        <e-scale backgroundColor="transparent" [showCustomLabels]="true" 
              [customLabels]="customLabels" [showMarkerPointers]="false" 
              [showBarPointers]="true" [border]="{ color: 'transparent', width: 0 }">
          <e-barpointers>
              <e-barpointer  [width]="10" backgroundColor="#8BABFF" [value]=91 
               placement="near" [distanceFromScale]=60 ></e-barpointer>
              <e-barpointer  [width]="10" backgroundColor="#FDB761" [value]=51 
               placement="near" [distanceFromScale]=20 ></e-barpointer>
              <e-barpointer  [width]="10" backgroundColor="#FF0000" [value]=88 
               placement="near" [distanceFromScale]=100 ></e-barpointer>
           </e-barpointers>	
          <e-ticks>
               <e-tick type="majorinterval" [width]=2 color="#8c8c8c" 
                         [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
               <e-tick type="minorinterval" [width]=1 [height]=6 color="#8c8c8c" 
                         [distanceFromScale]="{ x: 7, y: 0 }"></e-tick>
          </e-ticks>
        </e-scale>
   </e-scales>
</ej-lineargauge>

{% endhighlight %}

{% highlight ts %}

//Adding custom label collection
this.customLabels = [{
    value: "Mathematics Mark Comparision", position: { x: 55, y: 97 }
},
{ value: "Halfyearly", position: { x: 72, y: 87 }, textAngle: 90 },
{ value: "Quaterly", position: { x: 56, y: 87 }, textAngle: 90 },
{ value: "Annual", position: { x: 87, y: 87 }, textAngle: 90 }];

{% endhighlight %}



Execute the above code to render the following output.


![](Bar-Pointers_images/Bar-Pointers_img5.png)

