---
layout: post
title: Orientation
description: orientation
platform: Angular
control: Rating
documentation: ug
---

# Orientation

**Rating** provides support for **vertical** orientation. By default Rating renders with **horizontal** orientation. You can the change the orientation by the [orientation](https://help.syncfusion.com/api/js/ejrating#members:orientation) property.

The following code example is used to render the Rating control with **vertical** **orientation**.

 Add the following HTML to render Rating with customized orientation.

{% highlight html %}

    <ej-rating id="rating" [orientation]="orientation"> </ej-rating>
    
 {% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'src/rating/rating.component.html'
})
export class RatingComponent {
    orientation: any;
    constructor() {
        this.orientation = ej.Rating.Orientation.Vertical;
    }
}

{% endhighlight %}

The following screenshot illustrates the **Rating** with **vertical orientation**.

![](Orientation_images/Orientation_img1.png)