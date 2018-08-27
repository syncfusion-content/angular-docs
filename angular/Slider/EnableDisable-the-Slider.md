---
layout: post
title: EnableDisable-the-Slider
description: enable/disable the slider
platform: Angular
control: Slider
documentation: ug
---

# Enable/Disable the Slider

**Slider** widget includes an option to enable/disable it. When you disable the Slider, it is displayed in a blur state and you cannot perform any operations in it.

## Enabled	

Using this **enabled** property you can enable/disable the **Slider**. Data type of this property is “boolean”.

Also you can enable/disable the **Slider** by using [enable](https://help.syncfusion.com/api/angular/ejslider#methods:enable) and [disable](https://help.syncfusion.com/api/angular/ejslider#methods:disable) methods.

The following steps explains you on how to disable the **Slider**.

{% highlight html %}

   <div class="txt">Default Slider</div>
   <ej-slider id="enale" [value]="value" width="500" [enabled]="enabled"></ej-slider>

{% endhighlight %}

{% highlight html %}
<script>
 import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: './slider.component.html'
})
export class SliderComponent { 
    public enabled: boolean = false;
    public value: number = 60;
    constructor() {
    }
}
</script>

{% endhighlight %}

Execute the above code example to render the following output.


![](EnableDisable-the-Slider_images/EnableDisable-the-Slider_img1.png) 

