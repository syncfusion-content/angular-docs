---
layout: post
title: Globalization-Support
description: globalization support
platform: Angular
control: MaskEdit  
documentation: ug
---

# Globalization Support in MaskEdit

We have provided the globalization support in **MaskEdit** control. Our **MaskEdit** control mainly rendered based on the **maskFormat** property, so we have provided the globalization support based on the maskFormat literals. We have given this globalization support option on below maskFormat literals in **MaskEdit** control. You can change the globalization by using the [locale](https://help.syncfusion.com/api/angular/ejmaskedit#members:locale) property. The default value for **locale** property is 'en-US' in **MaskEdit** control.

<table class="props">
<thead>
<tr>
<th>Formats</th>
<th class="last">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="formats">
$</td>
<td class="description">Currency symbol value will be changed based on the corresponding culture.</td>
</tr>
<tr>
<td class="formats">
.</td>
<td class="description">Decimal Separator value will be changed based on the corresponding culture.</td>
</tr>
<tr>
<td class="formats">
,</td>
<td class="description">Thousand Separator will be changed based on the corresponding culture.</td>
</tr>
</tbody>
</table>

To know more about EJ globalize support, please refer the below link

[https://help.syncfusion.com/js/localization](https://help.syncfusion.com/js/localization)


The following example describes the way to use localization for **MaskEdit** widgets.

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

 {% highlight javascript %}
   
           <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>
                
 {% endhighlight %}

{% highlight html %}

<input id="maskEdit" ej-maskedit [value]="value" [maskFormat]="format" [locale]="locale" [inputMode]="inputMode" />

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';

@Component({
  selector: 'ej-app',
  templateUrl: 'src/maskEdit/maskEdit.component.html'
})
export class MaskEditComponent {
    public value: string;
    public format: any;
    public inputMode: any;
    public locale: string;
    constructor() {
        this.value = 1234567;
        this.format = "$99,999.99";
        this.inputMode = ej.InputMode.Text;
        this.locale = "de-DE";
    }
}

{% endhighlight %}

The output for **MaskEdit** with Globalization.

![](/js/MaskEdit/Globalization-Support_images/Globalization-Support_img1.jpg)

MaskEdit with `de-DE` locale
{:.caption}

![](/js/MaskEdit/Globalization-Support_images/Globalization-Support_img2.jpg)

MaskEdit with `en-US` locale
{:.caption}