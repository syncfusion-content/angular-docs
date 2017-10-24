---
title: Persistence Support for Angular Slider
description: Persistence Support for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Persistence Support

This feature supports you to save current model value to browser cookies for state maintenance. When you refresh the web page, the **Slider** control retains the model value apply from browser cookies. The data type of **enablePersistence** is Boolean type. 

The following steps explain you on how to enable the **enablePersistence** property.

In an **HTML** page, add a **<div>** element to render it as a **Slider** widget.

{% highlight html %}

<ej-slider id='defaultSlider' [type]='range' [enablePersistence]='isEnablePersistence'></ej-slider>

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
    public enablePersistence: boolean = true,
    public range: string ='range';
}
</script>

{% endhighlight %}

Execution of above code will render the below output 

![](Enable_persistence_images/persist_img1.png)

Change the handle values and refresh the page will shows the output like below.

![](Enable_persistence_images/persist_img2.png)