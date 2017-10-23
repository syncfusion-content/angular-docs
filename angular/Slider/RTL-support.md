---
title: RTL-support for Angular Slider
description: RTL-support for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# RTL support

**Slider** includes the Right to Left alignment support. Operations in the **Slider** is performed from Right to Left.

## Enabling RTL

Use the **enableRTL** property to enable the RTL support. By default this property is disabled. Data type of this property is “Boolean”.

The following steps explains you on how to enable RTL support in **Slider**.

In an **HTML** page, specify the **div** elements to render the **Range Slider.**

{% highlight html %}

<ej-slider id='rangeSlider' [type]='range' [values]='value' [enableRtl]='isEnableRtl'></ej-slider>

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
    public value: number[] = [25,75],
    public range: string ='range';
    public isEnableRtl: boolean = true;
}
</script>

{% endhighlight %}

Execution of above code will render the following output.

![](RTL-support_images/RTL-support_img1.png)