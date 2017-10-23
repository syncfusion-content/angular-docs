---
title: Updating slider value for Angular Slider
description: Updating slider value for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Updating slider value

**Slider** widget includes an option to specify/update its value. And also you can specify the starting and ending value for the **Slider** using the **minValue** and **maxValue** properties.

## Value

This property is used to set the value in the “Default” and “Min-Range” Sliders. By default its value is null when no value is specified. Data type of this property is “number”.

## Values

This property is used to set the value in “Range Slider”. By default range values is from 0 to 100. This property is of “Array” data type.

The following steps explains you the configuration of “value” and “values” property.

In an **HTML** page, specify the **<div>** elements to render the “Range Slider” and “Default Slider”.

{% highlight html %}

<div>Default Slider</div>
<ej-slider id='defaultSlider' [type]='default' [width]='width' [value]='value'></ej-slider>

<div>Range Slider</div>

<ej-slider id='rangeSlider' [type]='range' [width]='width' [values]='values'></ej-slider>

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
    public value: number = '60';
    public default : string = 'default';  
}
</script>

<script>

import { Component } from '@angular/core';
import { SliderModule } from '@syncfusion/ej2-ng-inputs';

@Component({
    selector: 'control-content',
    templateUrl: 'app/components/slider/slider.component.html'',
})
export class RangeSliderComponent {
    public values: number = [10,90];
    public range: string ='range';  
}
</script>

{% endhighlight %}

Execute the above code example to render the following output.


![](Updating-slider-value_images/Updating-slider-value_img1.png) 

## MinValue

To set the minimum/starting value of the Slider, you can use the minValue property. By default its value is 0. Data type of this property is “number”.

## MaxValue

To set the maximum/ending value of the Slider, you can use the maxValue property. By default its value is 100. Data type of this property is “number”.

The following steps explains you on how to configure minValue and maxValue property.

In an **HTML** page, specify the **<div>** elements to render the **Default Slider** and **Range Slider**.


{% highlight html %}

<div>Default Slider</div>
<ej-slider id='defaultSlider' [type]='default' [width]='width' [value]='value' [min]='minvalue' [max]='maxvalue' ></ej-slider>

<div>Range Slider</div>

<ej-slider id='rangeSlider' [type]='range' [width]='width' [values]='values' [min]='minvalue' [max]='maxvalue' ></ej-slider>

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
    public value: number = '60';
    public default : string = 'default';  
    public minvalue : string = '40';
    public maxvalue : string = '80';

}
</script>

<script>

import { Component } from '@angular/core';
import { SliderModule } from '@syncfusion/ej2-ng-inputs';

@Component({
    selector: 'control-content',
    templateUrl: 'app/components/slider/slider.component.html'',
})
export class RangeSliderComponent {
    public values: number = [10,90];
    public range: string ='range';
    public minvalue : string = '10';
    public maxvalue : string = '90';
    
}
</script>

{% endhighlight %}

Execute the above code example to render the following output.

![](Updating-slider-value_images/Updating-slider-value_img2.png) 

In the above example, for **Default Slider** the slider value starts from “40” (min value) and ends in “80” (max value), so the slider handle is placed at the center of the Slider while specifying the value as “60”.

For **Range Slider**, the value starts from “10” (min value) and ends in “90” (max value). The range shadow occupies the entire **Slider**, since the range (values) is specified as “[10, 90]”.

