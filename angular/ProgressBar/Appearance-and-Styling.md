---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: Angular
control: ProgressBar
documentation: ug
---

# Appearance and Styling

## Adjusting ProgressBar size

**ProgressBar** widget provides the ability to change or adjust the ProgressBar size. The [height](https://help.syncfusion.com/api/js/ejprogressbar#members:height) and [width](https://help.syncfusion.com/api/js/ejprogressbar#members:width) properties in the ProgressBar widget allows you to set the maximum height and maximum width for the ProgressBar. The value set to this property is **string or Number** type.

The following code helps that you on how to adjust the ProgressBar size.

{% highlight html %}

<div class="control">
    <ej-progressbar id="progressBar" [value]="val" [height]="height" [width]="width" (create)="onCreate($event)"></ej-progressbar>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/progressbar/progressbar.component.html'
})
export class ProgressBarComponent {  
    val: number;
    height: number;
    width: number;
    constructor() {
        this.val = 50;
        this.height = 40;
        this.width = 400;
    }
    onCreate($event) {
        var progress = $("#progressBar").data("ejProgressBar");
        progress.setModel({ text: progress.getValue() + " %" });
    }
}

{% endhighlight %}

The following screenshot displays the output.

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 

## Custom text

**Custom text** is displayed when the **ProgressBar** shows different levels of progress in the ProgressBar. Support for **Custom text** to mention the percentage or any other message inside the **ProgressBar** is possible by using [text](https://help.syncfusion.com/api/js/ejprogressbar#members:text) property.

The following steps explain the configuration of the **Custom text** for the ProgressBar widget.

In the **HTML** page, add a **&lt;div&gt;** element to render the ProgressBar widget.

{% highlight html %}

<div class="control">
    <ej-progressbar id="progressBar" [value]="val" [text]="text" [height]="height" [width]="width"></ej-progressbar>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/progressbar/progressbar.component.html'
})
export class ProgressBarComponent {  
    val: number;
    text: any;
    height: number;
    width: number;
    constructor() {
        this.val = 35;
        this.height = 20;
        this.width = 500;
        this.text = "loading";
    }
}

{% endhighlight %}

The following screenshot displays the output.      

 ![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) 

## Theme

The ProgressBar widget style and appearance are controlled based on **CSS** classes. In order to apply **Theme** to the ProgressBar widget, you can refer two files, namely, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.widgets.all.min.css is referred, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project, as **ej.widgets.all.min.css** is the combination of these both. 

By default, there are 12 themes’ support available for the **ProgressBar** widget namely,

* Default-theme
* Flat-azure-dark
* Fat-lime
* Flat-lime-dark
* Flat-saffron
* Flat-saffron-dark
* Gradient-azure
* Gradient-azure-dark
* Gradient-lime
* Gradient-lime-dark
* Gradient-saffron
* Gradient-saffron-dark

## CSS class

To apply custom styles to the ProgressBar widget, you can specify the [cssClass](https://help.syncfusion.com/api/js/ejprogressbar#members:cssclass) property. The specified **CSS** name is added in the root of the **ProgressBar** widget.

The following code example is used to render the ProgressBar widget with customized style.

{% highlight html %}

<div class="control">
    <ej-progressbar id="progressBar" [value]="val" cssClass="custom" [height]="height" [width]="width" (create)="onCreate($event)"></ej-progressbar>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core'; 
@Component({
selector: 'sd-home',
templateUrl: 'app/components/progressbar/progressbar.component.html',
styleUrls: ['app/components/progressbar/progressbar.component.css'],
encapsulation: ViewEncapsulation.None 
})
export class ProgressBarComponent {  
    val: number;
    height: number;
    width: number;
    constructor() {
        this.val = 70;
        this.height = 20;
        this.width = 500;
    }
    onCreate($event) {
        var progress = $("#progressBar").data("ejProgressBar");
        progress.setModel({ text: progress.getValue() + " %" });
    }
}

{% endhighlight %}

Add the following styles in progressbar.component.css to render the ProgressBar with customized style.

{% highlight css %}

.custom .e-progress {
    background-color:gray;
}

{% endhighlight %}

The following screenshot displays the output.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)