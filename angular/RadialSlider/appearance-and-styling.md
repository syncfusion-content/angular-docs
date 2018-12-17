---
layout: post
title: Syncfusion Radial slider appearance-and-styling
description: appearance and styling
platform: Angular
control: Radial Slider
documentation: ug
---

## Appearance and Styling

### Theme

You can customize RadialSlider component style and the appearance by using available themes or **cssClass** property.

In order to apply styles to the RadialSlider component, refer to 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. When you refer ej.web.all.min.css file, it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.web.all.min.css is the combination of these two.

By default, there are 17 theme support available for RadialSlider component, namely:

* flat-azure

* flat-azure-dark

* fat-lime

* flat-lime-dark

* flat-saffron

* flat-saffron-dark

* gradient-azure

* gradient-azure-dark

* gradient-lime

* gradient-lime-dark

* gradient-saffron

* gradient-saffron-dark

* bootstrap

* material

* high-contrast-01

* high-contrast-02

* office-365

### CSS Class

**RadialSlider** component also allows you to customize its appearance using user-defined CSS. To apply custom themes you can use **cssClass** property, which sets the root class for RadialSlider theme.

Using this cssClass you can override the existing styles under the theme style sheet. In the following example, the value of cssClass property is set as “purple-dark”. purple-dark is added as root class to RadialSlider component at the runtime. From this root class, you can customize the RadialSlider appearance.

Add the following code in your HTML page to render the RadialSlider.

{% highlight html %}

    <ej-radialslider [radius]="radius" [innerCircleImageUrl]="imageUrl" [cssClass]="cssClass">
    </ej-radialslider>

{% endhighlight %}

In the following style sheet the exiting theme style sheet file has been over-ridden using root class **purple-dark**.

Add the following code in constructor file.

{% highlight js %}


    @Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
    styles:['.purple-dark{ background-color:pink; }']
    })
    export class AppComponent {
        radius: number;
        imageUrl:any;
    cssClass:any;
        constructor() {
            this.radius = 100;
        this.imageUrl= "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
        this.cssClass= "purple-dark";
        }
    }

{% endhighlight %}


The following screenshot illustrates the output of the above code.

![Appearance and Styling](Appearance-and-Styling_images\cssClass_img1.png)


