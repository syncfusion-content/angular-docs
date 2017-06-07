---
layout: post
title: orientation
description: orientation
platform: angular-2
control: rotator
documentation: ug
---

## Orientation

The Rotator component supports both vertical and horizontal orientations allowing it to fit into any scenario. The Rotator property **orientation** defines the orientation where the component is rendered. The value set to this property is enum or string type. It accepts the following values.

ej.Orientation.Horizontal or “Horizontal”

ej.Orientation.Vertical or “Vertical”

The following steps explain you how to set orientation for the Rotator.

### Horizontal

This property sets the Rotator in horizontal orientation. You can refer the following steps to set horizontal orientation for Rotator component.

In View, create ul-li list of Rotator items and invoke the Rotator helper.

Add the following script in your HTML page.

{% highlight html %}
<ul ej-rotator id="sliderContent" slideWidth="500px" slideHeight="300px" orientation="orien" >

            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures"/>
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
            </li>
            <li>
                <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
            </li>
        </ul>

{% endhighlight %}



{% highlight js %}

export class AppComponent {
     orien:any;
    constructor() {
    this.orien = ej.Orientation.Horizontal;
    }
}



{% endhighlight %}



### Vertical

This property sets the Rotator in vertical orientation. You can refer the following steps to set vertical orientation for Rotator component.

Create ul-li list of Rotator items and invoke the Rotator helper.

Add the following script in your HTML page.

{% highlight js %}


<script>
export class AppComponent {
     orien:any;
    constructor() {
    this.orien = ej.Orientation.Vertical;
    }
}

{% endhighlight %}





