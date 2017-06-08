---
layout: post
title: image-customization
description: image customization
platform: Angular
control: Radial Slider
documentation: ug
---

## Image customization

## Customizing inner circle

### Using Class

The **RadialSlider** property **innerCircleimageclass** allow to set image for the inner circle of the RadialSlider. By default, the Radial Slider innerCircleImageClass is set as **null**. Refer to the following code example.

Add the following code in your HTML page to render the RadialSlider.


{% highlight html %}

    <ej-radialslider innerCircleImageUrl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png" [radius]="radius" [innerCircleImageClass]="imageclass">
    </ej-radialslider>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}


    @Component({
    styles: ['.myclass{ background-image : url("http://js.syncfusion.com/UG/Mobile/Content/sent.png");}']
    })
    export class AppComponent {
        radius: number;
        imageclass:any;
        constructor() {
            this.radius = 100;
            this.imageclass="myclass";
        }
    }

{% endhighlight %}

The following screenshot illustrates the output of above code.

![](Image_customization_images\usingclass_img1.png)

### Using image URL

The **RadialSlider** property **innerCircleImageUrl** allow to set URL image to the inner circle of the RadialSlider. By default, the Radial Slider innerCircleImageUrl is set as **null**.

Refer to the following code example.

Add the following code in your HTML page to render the **RadialSlider**.


{% highlight html %}

    <ej-radialslider [radius]="radius" [innerCircleImageUrl]="imageurl">

    </ej-radialslider>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        radius: number;
        imageurl:any;
        constructor() {
            this.radius = 100;
            this.imageurl= "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
        }
    }

{% endhighlight %}

The following screenshot illustrates the output of above code.

![https://help.syncfusion.com/js/radialslider/image-customization_images/image-customization_img2.png](Image_customization_images\usingimageurl_img1.png)

