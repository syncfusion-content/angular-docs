---
layout: post
title: Dimension
description: Dimension
platform: Angular-2
control: Radial Menu
documentation: ug
---

# Dimension

You can customize **Radial Menu** dimension by using **radius** and **position** properties.

## Radius

You can customize the **Radial Menu** size by using the **radius** property. By default, the Radial Menu radius is set as 150px. Refer to the following code example.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "radialtarget1" (click)="onItemClick($event)" [radius]="radius">
    <e-items>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/font.png" text="Bold" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/f1.png" text="Italic" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/redo.png" text="Redo" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/undo.png" text="Undo" ></e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}

Define **radius** value in constructor file.
    
{% highlight javascript %}

    export class AppComponent {    
    radius:any;
    constructor() {    
	this.radius=200;  
    }

{% endhighlight %}

The following screenshot illustrates the Radial Menu while clicking on the settings icon.

![](dimension-images\dimension_img1.png)

Selecting text in the page
{:.caption}



The following screenshot illustrates the **Radial Menu** while clicking on the settings icon.

![](dimension-images\dimension_img2.png)

## Position 

To display the **Radial Menu** in the web page in a specific area, we can use the **position** property. By default, the Radial Menu position is set as null.

Refer to the following code example.

In the HTML page set the **position** value to the RadialMenu component.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "radialtarget1" (click)="onItemClick($event)" [position]="position">
    <e-items>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/font.png" text="Bold" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/f1.png" text="Italic" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/redo.png" text="Redo" ></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/undo.png" text="Undo" ></e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}

Define **position** value in constructor file.
    
{% highlight javascript %}

    export class AppComponent {    
    position:any;
    constructor() {
	this.position={x:10,y:10};  	
    }

{% endhighlight %}

The following screenshot illustrates the output while selecting the text in the page.

![](dimension-images\dimension_img4.png)






