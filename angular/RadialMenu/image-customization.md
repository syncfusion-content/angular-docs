---
layout: post
title: image-customization
description: image customization
platform: Angular
control: Radial Menu
documentation: ug
---

# Image Customization

You can customize the Radial Menu’s Center and Back images by using the **imageClass** and **backImageClass** properties. Every menu item can be added with image using **imageUrl** property. By using this imageClass attribute, you can customize the Radial Menu center image.

Sub-Items are also supported in the Radial Menu. To navigate Sub-Items, click the arrows in the outer ring and it displays the corresponding sub-items group. Clicking the center button when a sub-items group is shown, displays the items on the previous level. Nested Radial Menu has the second level back button. In this case, you can use the **backImageClass** attribute to change your second level back button. BackImageClass is used to customize the nestedRadialMenu back image. 

Refer to the following code example.

You can add the page content with text-area by referring to this section.


{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" targetelementid="radialtarget1" (click)="onItemClick($event)" imageClass= "imageclass" backImageClass="backimageclass">
    <e-items>        
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/fontsize.png" text="Bold" type="slider" [sliderSettings]="slidersetting"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/f1.png" text="Italic"></e-item>              
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/redo.png" text="Redo"></e-item>  
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/undo.png" text="Undo"></e-item>     
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/list.png" text="Bullets"></e-item>     
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/l5.png" text="Numbering"></e-item>     
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/a1.png" text="Left"></e-item>     
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/a2.png" text="Right"></e-item>                       
    </e-items>
    </ej-radialmenu>
{% endhighlight %}

Add the following styles in your code.
    
{% highlight css %}

    <style type="text/css" class="cssStyles">
    .e-radial.imageclass { 
    background-image: url(http://js.syncfusion.com/demos/web/content/images/RadialMenu/main.png); 
    } 
    .e-radial.backimageclass { 
    background-image: url(http://js.syncfusion.com/demos/web/content/images/RadialMenu/Back_button.png); 
    }
    </style>

{% endhighlight %}


The following screenshot illustrates the output.

![](image-customization_images\image-customization_img1.png)

Radial Menu - Image Customization – Main menu
{:.caption}

When you click the arrow, it navigates to the child item as illustrated in the following screenshot.

![](image-customization_images\image-customization_img2.png)

Radial Menu- Image Customization – Child menu 
{:.caption}



