---
layout: post
title: Data-binding
description: data binding
platform: Angular2
control: Rating
documentation: ug
---

# Data-binding

In data binding concept of Rating control, need to set the value property using two way binding that is you need to assign the rating value in corresponding ts file.

The following example depicts the way to bind data to the **Rating** control.

Add the following code to render Rating with data binding.

{% highlight html %}

<ej-rating id="rating" [value]="ratingValue"></ej-rating>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: 'src/rating/rating.component.html'
})
export class RatingComponent {
    ratingValue: number;
    constructor() {
        this.ratingValue = 4;
    }
}

{% endhighlight %}

The following screenshot displays the output of **Rating** with **data binding** support.

![](Data-binding_images/Data-binding_img1.png)