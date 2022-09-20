---
layout: post
title: Labels in Angular Circular Gauge Control | Syncfusion
description: Learn here all about labels support in Syncfusion Essential Angular Circular Gauge control, its elements, and more.
platform: Angular
control: Circular Gauge
documentation: ug
---

# Labels in Essential Angular Circular Gauge

**Labels** are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Adding Label Collection 

**Label collection** is directly added to the scale object. Refer the following code example to add label collection in a **Gauge**.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1" >
     <e-scales>
          <e-scale [labels]="[{ angle: 30 }]">
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}


Execute the above code to render the following output.

![Angular Circular Gauge adding labels collection](Labels_images/Labels_img1.png)

## Label Customization

**Appearance**

The **attribute** angle is used to display the labels in the specified angles and **color** attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property **opacity** and the values of it lies between 0 and 1. You can adjust the labels based on the tick’s direction by setting **autoAngle** as true. **includeFirstValue** is an special property especially used in some special scenarios such as in clock, where the value 0 needs to be replaced with that of 12. By enabling this property the first value of the label is not rendered.

Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by **size**, **fontStyle** and **fontFamily**. Labels are two types such as major and minor.Major types labels are for major interval values and minor types labels are for minor interval values.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1" >
     <e-scales>
          <e-scale backgroundColor="#FAF4B5" [showScaleBar]="true" [radius]=150 
           [width]=10 [border]="{ width: 2, color: 'Yellow' }" [labels]="pointerLabels">
          	<e-pointers>
                <e-pointer [value]=70 [length]="100" backgroundColor="#FAF4B5" [width]=16
                 [opacity]=0.6 [border]="{ color: 'Yellow', width: 2 }"></e-pointer>
            </e-pointers>
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}



{% highlight ts %}

this.pointerLabels = [{
    // For setting label angle
    angle: 10,
    // For setting label opacity
    opacity: 0.8,
    // For disable the include first value prperty
    includeFistValue: false,
    // For setting label color
    color: "Yellow",
    // For setting label font
    font: {
        size: "15px",
        fontFamily: "Arial",
        fontStyle: "bold"
    }
}];

{% endhighlight %}



Execute the above code to render the following output.

![Angular Circular Gauge labels customization](Labels_images/Labels_img2.png)

**Unit text and Position**

**unitText** is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. You can achieve this by using an enumerable property **unitTextPosition**. With this you can position the unit text in front or back.

Labels can be positioned with the help of two properties such as **distanceFromScale** and **placement**. **distanceFromScale** property defines the distance between the scale and labels.  Placement property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1" >
     <e-scales>
          <e-scale [showRanges]="true" backgroundColor="#5DF243" [showScaleBar]="true" 
           [radius]=150 [size]=2 [labels]="[{ unitText: "kmpH", unitTextPosition: 'back'}]" >
          	<e-pointers>
                <e-pointer [value]=40 [length]="100" [showBackNeedle]="true" >
                </e-pointer>
            </e-pointers>
            <e-ranges>
                <e-range [distanceFromScale]='-30' [startValue]='0' [endValue]='50' 
                    backgroundColor="Green" placement="far"></e-range>
                <e-range [distanceFromScale]='-30' [startValue]='50' [endValue]='80' 
                    backgroundColor="Yellow" placement="far"></e-range>
                <e-range [distanceFromScale]='-30' [startValue]='80' [endValue]='100' 
                    backgroundColor="red" placement="far"></e-range>
            </e-ranges>
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}

Execute the above code to render the following output.

![Angular Circular Gauge unit text and position](Labels_images/Labels_img3.png)

## Multiple Labels

You can achieve multiple labels such as minor and major in a **Gauge** sample scale. Refer the following code example for multiple labels variation.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1" >
     <e-scales>
          <e-scale [showRanges]="true" backgroundColor="#5DF243" [showScaleBar]="true" 
                    [radius]=150 [size]=2 [labels]="[{type='minor', color: 'yellow'}, 
                    {type='major', color: 'red'}]" >
          	<e-pointers>
                <e-pointer backgroundColor="yellow" [length]="110" 
                         [border]="{ width: 1.5, color: 'Red' }">
                </e-pointer>
            </e-pointers>
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}

Execute the above code to render the following output.

![Angular Circular Gauge multiple labels](Labels_images/Labels_img4.png)

