---
title: Keyboard Interaction for Angular Slider
description: Keyboard Interaction for Angular Slider
platform: Angular
control: Slider
documentation: Ug
keywords: ejslider, js slider, slider
---

# Keyboard Interaction

You can use Keyboard shortcut keys as an alternative to the mouse for using the **Slider** widget. All options in the **Slider** can be accessed using keyboard shortcuts. The following table explains the keyboard shortcut keys and the operations that can be performed using the corresponding keys.

List of Keyboard shortcuts

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Alt + j	</td><td>
Focuses into the Slider handle</td></tr>
<tr>
<td>
Up/Right</td><td>
Increments the Slider value</td></tr>
<tr>
<td>
Down/Left</td><td>
Decrements the Slider value</td></tr>
<tr>
<td>
Home</td><td>
Slider handle moves to the start value </td></tr>
<tr>
<td>
End</td><td>
Slider handle moves to the end value</td></tr>
<tr>
<td>
Esc</td><td>
Focuses out from the Slider handle</td></tr>
</table>


## Configure keyboard interaction

The following steps explains you on how to enable keyboard support in **Slider**.

In an **HTML** page, specify the **<div>** elements to render the **Range Slider.**

{% highlight html %}

<ej-slider id='default' [values]='value'></ej-slider>

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
    public value: number = [25,75]; 
}
</script>

{% endhighlight %}
