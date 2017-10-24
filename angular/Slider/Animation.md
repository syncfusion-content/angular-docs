---
title: Animation for Angular Slider
description: Animation for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Animation

This feature includes the animation effect for the **Slider** when moving the **Slider** handle.

## Enabling Animation

By default, animation is enabled in the **Slider**. Using the **enableAnimation** property you can enable/disable the animation effects. Data type of this property is “Boolean”.

The following steps explains you on how to disable the animation effect in **Slider**.

In the **HTML** page, specify the **<div>** elements to render the “Default Slider”.



{% highlight html %}

<ej-slider id='default' [value]='value' [enableAnimation]='isAnimation'></ej-slider>

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
    public value: number = 30; 
    public isAnimation: boolean = true; 
}
</script>

{% endhighlight %}

## Customizing Animation speed

Animation speed of the **Slider** indicates the speed at which the slider handle can be moved. Higher the value specified for this property decreases the rate of speed at which the **Slider** handle can be moved. You can customize the animation speed of the **Slider** using the **animationSpeed** property. Default value of this property is “500”.

The following steps explains you on how to customize the animation speed.

In an **HTML** page, specify the **<div>** elements to render the “Default Slider”.

{% highlight html %}

<ej-slider id='default' [value]='value' [animationSpeed]='speed'></ej-slider>

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
    public value: number = 60; 
    public speed: number = 600; 
}
</script>

{% endhighlight %}