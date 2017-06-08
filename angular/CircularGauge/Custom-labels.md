---
layout: post
title: Custom-labels
description: custom labels
platform: Angular
control: Circular Gauge
documentation: ug
---

# Custom labels

Custom labels are the texts that you can use them in any location of the **Gauge**.

## Adding Custom Label Collection

Custom labels collection is directly added to the scale object. Refer the following code to add custom labels collection in a **Gauge** control.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1">
     <e-scales>
          <e-scale showCustomLabels="true" [customLabels]="[{color: 'Red', value: 'KM / H', 
                                                              position:{x: 170, y:220}}]">
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}

**Basic Customization**

You can customize custom labels using the properties such as **textAngle**, **color** and **font**. **textAngle** attribute is used to display the custom labels in the specified angles and **color** attribute is used to display the custom labels in specified color. 

You can use **Value** attribute to set the text value in the custom labels. To display the custom labels, set **showCustomLabels** as ‘true’. To set the location of the custom label in **Circular Gauge**, **location** property is used. By using **x** and **y** axis you can adjust the position of the custom labels.

Font option is also available on  custom labels. The basic three properties of fonts such as size, family and style can be achieved by **size**, **fontStyle** and **fontFamily** attributes. 

{% highlight html %}

 <ej-CircularGauge id="circularGauge1">
     <e-scales>
          <e-scale showCustomLabels="true" [customLabels]="[{color: 'Red', font:
           { size: '18px',fontFamily: 'Arial',fontStyle: 'bold'} textAngle: 10, 
           value: 'CustomLabel1', position:{x: 170, y:220}}]" [size]=2 [shadowOffset]=10
            [showCustomLabels]="true" [showRanges]="true" [showScaleBar]="true" [radius]=150 >
          </e-scale>
    </e-scales>
</ej-CircularGauge>

{% endhighlight %}


Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img1.png)

## Multiple Custom Labels

You can set multiple custom labels in a single **Circular Gauge** by adding an array of custom label objects. Refer the following code example for multiple custom label functionality.

{% highlight html %}

 <ej-CircularGauge id="circularGauge1">
     <e-scales>
          <e-scale showCustomLabels="true" [customLabels]="[{color: 'Red', font: 
           { size: '18px',fontFamily: 'Arial',fontStyle: 'bold'},textAngle: 10,
           value: 'CustomLabel1', position:{x: 180, y:100}}, {color: 'Red', 
           font: { size: '18px',fontFamily: 'Arial',fontStyle: 'bold'}, textAngle: 10, 
           value: 'CustomLabel2', position:{x: 180, y:250}}]"                         
           [size]=2 [shadowOffset]=10 [showCustomLabels]="true" [showRanges]="true" 
           [showScaleBar]="true" [radius]=150 >
        </e-scale>
    </e-scales>
  </ej-CircularGauge>

{% endhighlight %}

Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img2.png)

## Outer Custom Label

**Outer Custom Label** is used to show custom labels outside the **gauge** control. The **Outer Custom Label** can be positioned with API called **outerCustomLabelPosition.** The value for this API is enumerable type and its possible values are,

* Right

* Left

* Top

* Bottom

When a custom label is to be displayed as an **Outer Custom Label**, set the API **customLabelType** as Outer. Refer to the following code example to get the **Outer Custom Label**.


{% highlight html %}

 <ej-CircularGauge id="circularGauge1" outerCustomLabelPosition="right" [tooltip.showCustomLabelTooltip]="true">
     <e-scales>
          <e-scale showCustomLabels="true" [customLabels]="[{color: 'Red', font: { 
              size: '18px',fontFamily: 'Arial',fontStyle: 'bold'},textAngle: 10, 
              value: 'Average Speed', position:{x: 360, y:30}},positionType: 'outer']" 
              [size]=2 [shadowOffset]=10 [showCustomLabels]="true" [showRanges]="true" 
              [showScaleBar]="true" [radius]=150 >
            <e-pointers>
                <e-pointer [value]="60" [length]="100">
                </e-pointer>
            </e-pointers>
          </e-scale>
       </e-scales>
  </ej-CircularGauge>

{% endhighlight %}


Execute the above code to render the following output.

![](Custom-labels_images/Custom-labels_img3.png)

