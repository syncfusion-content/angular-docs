---
layout: post
title: Template Support in VUe Tabs Control | Syncfusion
description: Learn here about Template Support with Syncfusion Essential Angular Tabs control, its elements, and more.
platform: angular
control: Tab
documentation: ug
---

# Template Support in VUe Tabs Control

We can use this option to load any HTML elements and showcase it in the Tab panels as per our requirement.

We can load the contents or HTML elements directly inside the &lt;div&gt; element which we are going to convert as Tab control.

{% highlight html %}

<ej-tab id="dishtype">
    <ul>
        <li><a href="#corn">Corn & Spinach </a></li>
        <li><a href="#chicken">Chicken Delite</a></li>
    </ul>
    <div id="corn" style="background-color: #F5F5F5">
        <div class="e-content">
            <img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach"/>
            <div class="ingredients">
                Rate    : $70<br /> Ingredients : cheese, sweet corn &amp; green capsicums.
                <br />
                Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.
            </div>
        </div>
    </div>
    <div id="chicken" style="background-color: #F5F5F5">
        <!--Content for Chicken Delite-->
    </div>
</ej-tab>

{% endhighlight %}

The following screenshot illustrates the **Tab** with **Template** support.

![Template Support in VUe Tabs Control.](Template-Support_images/template-support-in-vue-tabs-control.png) 