---
layout: post
title: Template-Support
description: template support
platform: Angular
control: Accordion 
documentation: ug
---

# Template Support

In **JavaScript**, you can load the contents or **HTML** elements directly inside the **&lt;div&gt;** element that you are going to convert as **Accordion** control.

{% highlight html %}

<ej-accordion [enableMultipleOpen]="true">
   <h3>
        <a href="#">GARDEN FRESH (Veg)</a>
    </h3>
    <div>
        <img src="../content/accordion/garden-veggie.png" alt="garden-fresh" />
        <div class="ingredients">
            Rate    : $50
            <br />
            Ingredients : cheese, onions, green capsicums & tomatoes.
        </div>
    </div>
    <h3>
        <a href="#">CORN & SPINACH (Veg)</a>
    </h3>
    <div>
        <img src="../content/accordion/corn-and-spinach-05.png" alt="garden-fresh" />
        <div class="ingredients">
            Rate    : $70
            <br />
            Ingredients : cheese, sweet corn & green capsicums.
        </div>
    </div>
    <h3>
        <a href="#">CHICKEN DELITE (Non-veg)</a>
    </h3>
    <div>
        <img src="../content/accordion/chicken-delite.png" alt="garden-fresh" />
        <div class="ingredients">
            Rate    : $100
            <br />
            Ingredients : cheese, chicken chunks, onions & pineapple chunks.
        </div>
    </div>
</ej-accordion>

{% endhighlight %}

![](Template-Support_images/Template-Support_img1.png)