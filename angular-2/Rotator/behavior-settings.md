---
layout: post
title: Behavior Settings
description: Behavior Settings
platform: angular-2
control: rotator
documentation: ug
---

# Behavior settings

### Enabling rotator

The **enabled** property enables or disables the Rotator control. The default value is ‘true’. The value set to this property is Boolean type. You can refer the following code example to set this property.

{% highlight html %}

<ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton]="true" [enabled]="true" slideWidth="400px" slideHeight="300px">
                        </ul>


{% endhighlight %}


### Device Responsiveness 

The **isResponsive** property resizes the Rotator when the browser window is resized. The default value is ‘false’. The value set to this property is Boolean.

{% highlight html %}

<ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton]="true" [isResponsive]="true" slideWidth="400px" slideHeight="300px">
                        </ul>


{% endhighlight %}

### Auto Play option

By using the **enableAutoPlay**, we can able to play the rotator slides automatically without our interference when it is set as true. The default value is ‘false’. The value set to this property is Boolean.

{% highlight html %}

<ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton]="true" [enableAutoPlay]="true" slideWidth="400px" slideHeight="300px">
                        </ul>


{% endhighlight %}

### Stop sliding on hover

The **stopOnHover** property pauses the auto play while mouse over the Rotator content. The default value is ‘false’. The value set to this property is Boolean.

{% highlight html %}
<ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton]="true" [enableAutoPlay]="true" [stopOnHover]="true" slideWidth="400px" slideHeight="300px">
                        </ul>


{% endhighlight %}


### Pager settings

#### Show pager

The **showPager** property turns on or off the pager support in the Rotator control. The Pager is used to navigate the Rotator Items. The default value is ‘true’. The value set to this property is Boolean.

{% highlight html %}
<ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton="true" [showPager]="true" slideWidth="400px" slideHeight="300px">
                        </ul>

{% endhighlight %}



![](behavior settings_images\showpager_img1.png)

#### Pager position

This property specifies the position of the Pager in the Rotator Item. The default value is ‘outside’. The value set to this property is string or enum.

ej.Rotator.PagerPosition.BottomLeft

ej.Rotator.PagerPosition.BottomRight

ej.Rotator.PagerPosition.Outside

ej.Rotator.PagerPosition.TopCenter

ej.Rotator.PagerPosition.TopLeft

ej.Rotator.PagerPosition.TopRight





{% highlight html %}
   <ul ej-rotator id="sliderContent" [dataSource]="data" [fields]="fieldList" [showPlayButton]="true" [pagerPosition]="position" [enabled]="true" slideWidth="400px" slideHeight="300px"> </ul>
{% endhighlight %}



{% highlight js %}

export class AppComponent {
    data: Array<any>;
    fieldList: Object;
    position :any;
    constructor() {
        this.data = [
        { text: "Snowfall", url: " http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" },
          { text: "Green", url: " http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" },
          { text: "Beatutiful Bird", url: " http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" },
          { text: "Tablet", url: " http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" },
          { text: "Nature", url: " http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" }

        ];
        this.fieldList = { dataSource: this.data, text: 'text', url: 'url' };
        this.position = ej.Rotator.PagerPosition.BottomLeft;
    }
    }
   



{% endhighlight %}

![](behavior settings_images\pagerposition_img1.png)





