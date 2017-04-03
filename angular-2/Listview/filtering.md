---
layout: post
title: filtering
description: filtering
platform: Angular-2
control: ListView
documentation: ug
---

## Filtering

Filtering is one of the key features of ListView component. The Filtering option is added into the ListView component when the enableFiltering property is set to True. This enables a simple interface to filter items from a large collection of ListView items.

Refer the following code examples.

{% highlight html %}

<div style="width:400px;">
    <ej-listview headertitle="List Items" enableFiltering="true">
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

![https://help.syncfusion.com/js/ListView/Filtering_images/Filtering_img1.png](filtering_images\filtering_img1.png)

_Before Filtering_

![https://help.syncfusion.com/js/ListView/Filtering_images/Filtering_img2.png](filtering_images\filtering_img2.png)

_After Filtering_

