---
layout: post
title: Syncfusion Radial Slider Getting-Started
description: Getting Started
platform: Angular
control: RadialSlider
documentation: ug
---

# Getting Started

This section helps you to understand the getting started of the Radial Slider component with the step-by-step instructions.

## Create a Radial Slider component

The following steps guide you to add a Radial Slider control.

1)	To get start with how to use the Radial Slider component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/gettingstarted/overview).

2)	Create a radial slider by adding [`ej-radialslider`] attribute for rendering the Radial Slider component on the application. 

{% highlight javascript %}

      <ej-radialslider innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png" [radius]="radius">
      </ej-radialslider>

{% endhighlight %}

Define the radius in the component’s constructor file. Refer to the below mentioned code.

{% highlight javascript %}

        export class AppComponent {
            radius: number;
            constructor() {
                this.radius = 100;
            }
        }

{% endhighlight %}

To get the following output from the above-mentioned code.

![Getting Started](getting-started-images\getting-started-img.png)


N> You can find the Radial Slider component properties from the [API reference](https://help.syncfusion.com/api/js/ejradialslider)              
