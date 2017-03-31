---
layout: post
title: dimensions
description: dimensions
platform: Angular-2
control: ListView
documentation: ug
---

## Dimensions

To customize the ListView dimensions, width and height properties are used.

Refer to the following code examples.

{% highlight html %}

<div style="width:400px;">
    <ej-listview headertitle="List Items" [height]="height" [width]="width">
        <ul>
            <li data-ej-text="Artwork"></li>
            <li data-ej-text="Abstract"></li>
            <li data-ej-text="2 Acrylic Mediums"></li>
            <li data-ej-text="Creative Acrylic"></li>
            <li data-ej-text="Modern Painting"></li>
            <li data-ej-text="Canvas Art"></li>
            <li data-ej-text="Black white"></li>
            <li data-ej-text="Children"></li>
            <li data-ej-text="Preschool Crafts"></li>
            <li data-ej-text="School-age Crafts"></li>
        </ul>
    </ej-listview>
</div>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    height: any;
    width: any;
    constructor() {
        this.width = 400;
        this.height = 500;
    }
}

{% endhighlight %}

Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Dimensions_images/Dimensions_img1.png](dimensions_images\dimensions_img1.png)



