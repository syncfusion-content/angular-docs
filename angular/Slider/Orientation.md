---
title: Orientation for Angular Slider
description: Orientation for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Orientation

This property is used to set the **Slider** in either horizontal or vertical direction. By default, **Slider** renders in horizontal direction. Data type of this property is “enum”.

Possible **Slider** orientations are as follows,

Property Table for JavaScript

<table>
<tr>
<th>
Property</th><th>
Allowed values</th><th>
Description</th></tr>
<tr>
<td rowspan = "2">
orientation</td><td>
ej.Orientation.Vertical</td><td>
Displays the Slider in vertical direction</td></tr>
<tr>
<td>
ej.Orientation.Horizontal (default value)</td><td>
Displays the Slider in horizontal direction</td></tr>
</table>


The following steps explains you on how to configure the **orientation** property.

In an **HTML** page, add a **<div>** element to render it as a **Slider** widget.


{% highlight html %}

<ej-slider id='rangeSlider' [height]='height' [width]='width' [values]='slidevalue' [orientation]='orientation'></ej-slider>

{% endhighlight %}

{% highlight html %}

 <script>

import { Component } from '@angular/core';
import { SliderModule } from '@syncfusion/ej2-ng-inputs';

@Component({
    selector: 'control-content',
    templateUrl: 'app/components/slider/slider.component.html'',
})
export class DefaultSliderComponent {
    public slideValue: number = 60; 
    public height: number = 16;
    public width: number = 150;
    public orientation:'vertical';
}
</script>

Execute the above code example to render the following output.

![](Orientation_images/orientation_img1.png) 



