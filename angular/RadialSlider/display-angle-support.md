---
layout: post
title: display-angle-support
description: display angle support
platform: Angular
control: Radial Slider
documentation: ug
---

## Display Angle Support

### Start Angle

The **RadialSlider** property **startAngle** allows you to change the start angle level of the RadialSlider. By default, the Radial Slider start angle is set as 0. Refer to the following code example.

Add the following code in your HTML page to render the RadialSlider.


{% highlight html %}

    <ej-radialslider [radius]="radius" [innerCircleImageUrl]="imageurl" [startAngle]="startangle">
    </ej-radialslider>

{% endhighlight %}

Add the following code in constructor file.

{% highlight javascript %}

    export class AppComponent {
        radius: number;
        imageurl:any;
        startangle:any;
        constructor() {
            this.radius = 100;
            this.imageurl= "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
        this.startangle=20;
        }
    }

{% endhighlight %}

The following screenshot illustrates the output of the above code.

![https://help.syncfusion.com/js/radialslider/display-angle-settings_images/display-angle-settings_images_img1.png](display-angle-settings_images\startangle_img1.png)

### End Angle

The  **RadialSlider** property endAngle allows you to change the end angle level of the RadialSlider. By default, the Radial Slider end angle is set as 360. Refer to the following code example.

Add the following code in your HTML page to render the RadialSlider.


{% highlight html %}

    <ej-radialslider [radius]="radius" [innerCircleImageUrl]="imageurl" [endAngle]="endangle">
    </ej-radialslider>

{% endhighlight %}


Add the following code in constructor file.

{% highlight javascript %}

syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.endangle = 300;
    });


{% endhighlight %}


The following screenshot illustrates the output of the above code.

![https://help.syncfusion.com/js/radialslider/display-angle-settings_images/display-angle-settings_images_img2.png](display-angle-settings_images\endangle_img1.png)

