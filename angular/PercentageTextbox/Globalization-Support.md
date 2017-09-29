---
layout: post
title: Globalization-Support
description: globalization support
platform: Angular
control: PercentageTextBox 
documentation: ug
---

# Globalization Support

**Globalization** is language support based on the culture in **Textboxes**. You can achieve the **Globalization** using “**locale”** property in **PercentageTextBox** . 

The **PercentageTextBox** widget provides multi-language support using globalization. You can customize the **PercentageTextBox** with your own language style by using this feature. You can change the globalization by using the **locale** property. The default value for **locale** property is **en-US** in **PercentageTextBox** control.More than 350 culture specific files are available to localize the value.

 N> All the culture-specific script files are available within the below specified location, once you have installed Essential Studio in your machine, therefore it is not necessary to download these files explicitly.

<table>
<tr>
<td>

    '(installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n'
 </td>
 </tr>
 <tr>
 <td>

    For example, If you have installed the Essential Studio package within C:\Program Files (x86), then navigate to the below location, 
    C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n

</td></tr>
</table>

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}


You can dynamically change the language based on their culture.

## Configure Globalization

The following example describes the way to use Globalization for **PercentageTextBox** widget.

{% highlight html %}

<input id="percent" type="text" ej-percentagetextbox [value]="value" [locale]="locale" [decimalPlaces]="decimalPlaces"/>

{% endhighlight %}


{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/percentagetextbox/percentagetextbox.component.html'
})
export class PercentageTextboxComponent {
    public value: number;
    public locale: string;
    public decimalPlaces: number;
    constructor() {
        this.value = 21234;
        this.locale = "de-DE";
        this.decimalPlaces = 3;
    }
}

{% endhighlight %}

The output for **PercentageTextBox** with Globalization.

![](/angular/PercentageTextbox/Globalization-Support_images/Globalization-Support_img1.png)

PercentageTextBox with de-DE locale
{:.caption}

![](/angular/PercentageTextbox/Globalization-Support_images/Globalization-Support_img2.png)

PercentageTextBox with en-US locale				
{:.caption}