---
layout: post
title: Dimension
description: Dimension
platform: Angular
control: Radial Slider
documentation: ug
---

# Dimension 

## Stroke Width

**Radial Slider** strokeWidth property specifies the width of the outline . By default, the **Radial slider** strokeWidth is set as 2. Refer to the following code example.

{% highlight html %}

    <ej-radialslider style="margin:0 auto;" [strokeWidth]="sWidth" innerCircleImageUrl="app/content/images/radialslider/chevron-right.png">
    </ej-radialslider>
    
{% endhighlight %}

Add the following code in typescript file.
    
{% highlight js %}

    export class DefaultComponent {
    sWidth:number;
    constructor() {
    this.sWidth=5;
	  }
    }

{% endhighlight %}


The following screenshot illustrates the output of the above code.

![](dimension_images\dimension_img1.png)


## Setting radius

The **RadialSlider** property **radius**  indicates the radius of the RadialSlider's circle ant its allow to change radius value.  By default, the **Radial Slider** radius is set to 200. Refer to the following code example.

{% highlight html %}

       <ej-radialslider style="margin:0 auto;" [radius]="radius" innerCircleImageUrl="app/content/images/radialslider/chevron-right.png">
    </ej-radialslider>

{% endhighlight %}

{% highlight js %}

    export class DefaultComponent {
       radius: number;
       constructor() {
       this.radius = 100;
		  }
       }

{% endhighlight %}


The following screenshot illustrates the output of the above code.

![](dimension_images\dimension_img2.png)
