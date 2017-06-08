---
layout: post
title: animation-effect
description: animation effect
platform: Angular
control: Radial Slider
documentation: ug
---

## Animation Effect

The **animation** effect for the **RadialSlider** can be enabled or disabled using the **enableAnimation** property. By default, it is set as true, so that the handle movement will be animated.

Add the following code in your HTML page to render the RadialSlider.


{% highlight html %}

    <ej-radialslider [radius]="radius" [innerCircleImageUrl]="imageurl" [enableAnimation]="animation">
    </ej-radialslider>

{% endhighlight %}

Add the following script in your code and this will stop the handle movement’s animation.

{% highlight javascript %}

    export class AppComponent {
        radius: number;
        imageurl:any;
        animation:any;
        constructor() {
            this.radius = 100;
            this.imageurl= "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
            this.animation=false;
        }
    }

{% endhighlight %}

