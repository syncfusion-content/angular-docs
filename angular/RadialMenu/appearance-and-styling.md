---
layout: post
title: Syncfusion Radial Menu Appearance and Styling 
description: appearance and styling
platform: Angular
control: RadialMenu
documentation: ug
---

# Appearance and Styling

You can customize RadialMenu component style and the appearance by using available themes or **cssClass** property.

## Theme

RadialMenu component style and appearance can be controlled based on CSS classes. In order to apply styles to the RadialMenu component, refer 2 files namely: ej.widgets.core.min.css and ej.theme.min.css. If the file ej.web.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project, as ej.web.all.min.css is the combination of these two.

By default, the following themes support available for **RadialMenu** component namely

* flat-azure
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme
* office-365
* material theme
* high contrast 01
* high contrast 02


## CSS Class

RadialMenu component’s appearance can only be customized using its CSS classes. Define CSS class, as per requirement and assign the class name to cssClass property.

### Configure RadialMenu using CSS class

Define cssClass to customize the RadialMenu.

In the HTML page, define the li items for RadialMenu component.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" targetelementid="radialtarget1" (click)="onItemClick($event)" imageClass= "imageclass" backImageClass="backimageclass" cssClass="customCss">
    <e-items>        
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/fontsize.png" text="Bold"></e-item>
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

    <style type="text/css">

        /* Customize the radialMenu */

      .e-radialmenu .e-default, .e-radialmenu .e-outerdefault.customCss 

       {
             fill:#808080;
       } 

    </style>

{% endhighlight %}

Output of RadialMenu configured based on CSS class is as follow,

![Appearance and Styling](apperance-and-styling-images\appearance-and-styling_img1.png)


