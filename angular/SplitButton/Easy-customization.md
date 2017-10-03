---
layout: post
title: Easy-customization
description: easy customization
platform: angular
control: Split Button
documentation: ug
---

# Easy customization

**Split Button** is used in many applications. **Split Button** Size, Content and content location is varied according to each application. The following sections describes you some customizable options for **Split Button** that can perform easily.

## Content for Split button

The **target** is a mandatory one, without this field it acts as normal button on two sides. This **target** property is used to specify the list of content for **Split Button**. The list of content is rendered as a vertical menu list. This vertical menu list is open, when you click on the down arrow of the **Split Button**.

The following steps explains you the details about rendering the **Split Button** with content.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="spltbutton11" target="#menu" size="small"  contentType="textandimage" prefixIcon="e-icon e-login" [showRoundedCorner]=true text="login"></ej-splitbutton>
                 <ul id="menu">
                     <li><span>User</span></li>
                     <li><span>Guest</span></li>
                     <li><span>Admin</span></li>
                 </ul>
             </td>
         </tr>
     </table>
    </div>
    
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}
    
{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Easy-customization_images/Easy-customization_img1.png) 

## Button Size

You can render the **Split Button** in different sizes. The following table contains some predefined size option for rendering a **Split Button** in easiest way. Each size option has different height and width. Mainly it avoids the complexity in rendering **Split Button** with complex **CSS** class. 

List of Button size

<table>
<tr><th>Button Size</th><th>Description</th></tr>
<tr>
<td>
normal</td><td>
Creates split button with content size.</td></tr>
<tr>
<td>
mini</td><td>
Creates split button with Built-in mini size height, width specified.</td></tr>
<tr>
<td>
small</td><td>
Creates split button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
medium</td><td>
Creates split button with Built-in medium size height, width specified.</td></tr>
<tr>
<td>
Large</td><td>
Creates split button with Built-in large size height, width specified.</td></tr>
</table>


Apart from the above mentioned predefined size option, you can set your own width and height for **Split Button** using **height** and **width** property.

The following steps explains you the details about rendering the **Split Button** with above mentioned size options.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td> Normal</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_normal" target="#Ul11" size="normal" [showRoundedCorner]=true contentType="imageonly" prefixIcon="e-icon e-login" text="login" width="50px"></ej-splitbutton>
                    <ul id="Ul11">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td> Mini</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_mini" target="#Ul21" size="mini" [showRoundedCorner]=true text="login"></ej-splitbutton>
                    <ul id="Ul21">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>

         <tr>
             <td> Small</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_small" target="#Ul31" size="small" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul31">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td> Medium</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_medium" target="#Ul41" size="medium" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul41">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td> Large</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_large" target="#Ul51" size="large" [showRoundedCorner]=true contentType="textandimage" prefixIcon="e-icon e-login" text="login"></ej-splitbutton>
                    <ul id="Ul51">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td> Large</td>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customSize" target="#Ul61" size="large" height="50" width="150" [showRoundedCorner]=true contentType="textandimage" prefixIcon="e-icon e-login" text="login"></ej-splitbutton>
                    <ul id="Ul61">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
     </table>
    </div>
    <style>
    .control {
        width: 500px;
    }

    .e-split {
        float: left;
        padding-left: 10px;
    }
    </style>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}
    
{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/SplitButton/Easy-customization_images/Easy-customization_img2.png) 

## Content Type

The content of the **Split Button** is mainly rendered as text and images. Instead of using complex **CSS** classes to render **Split Button** with different content types, you can use some predefined content type options listed in the following table. Using this content types you can easily add different types of content for **Split Button**. Split Button supports the following content types.

List of content types

<table>
<tr><th>Content Type</th><th>Description</th></tr>
<tr>
<td>
textonly</td><td>
Supports only for text content only.</td></tr>
<tr>
<td>
imageonly</td><td>
Supports only for image content only</td></tr>
<tr>
<td>
imageboth</td><td>
Supports image for both ends of the button.</td></tr>
<tr>
<td>
textandimage</td><td>
Supports image with the text content.</td></tr>
<tr>
<td>
imagetextimage</td><td>
Supports image with both ends and middle in text.</td></tr>
</table>

### Prefix and Suffix icons

Icons inside the **Split Button** is added easily using **prefixIcon and suffixIcon** property. Location of the icon in **Split Button** is a necessary thing. You can customize the location of Icon easily using the following mentioned options.

**Split Button** control also supports the Built-in icon libraries. The **ej.widgets.core.min** CSS contains definitions for important icons that are used in **Split Buttons**. You can use these Built-in icons by mentioning the icon class name as value in **prefixIcon** and **suffixIcon** property. You can use any font icons that is defined in **ej.widgets.core.min** CSS. It avoids the complexity in specifying icon using sprite image and CSS.

For example the following Built-in CSS class are used to display the font icons that is used by media player.

* e-mediaback
* e-mediaforward
* e-medianext
* e-mediaprev
* e-mediaeject
* e-mediaclose
* e-mediapause
* e-mediaplay

**Prefix Icon**

It inserts the icon at the starting position of **Split Button**. After this prefix icon, you can use text or suffix icon.

**Suffix Icon**

It inserts the icon at the ending position of **Split Button**. Before this suffix icon, you can use text or prefix icon.

The following steps explains you the details on rendering the **Split Button** with above mentioned **content type**, **prefix** and **suffix icon** options

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageonly" target="#Ul11" size="medium" [showRoundedCorner]=true contentType="imageonly" prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul11">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_textonly" target="#Ul21" size="medium"   contentType="textonly" [showRoundedCorner]=true text="login"></ej-splitbutton>
                    <ul id="Ul21">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>

         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageboth" target="#Ul31" size="medium" contentType="imageboth" suffixIcon="e-icon e-palette" prefixIcon="e-icon e-handup" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul31">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_textandimage" target="#Ul41" contentType="textandimage"  prefixIcon="e-icon e-handup" size="medium" [showRoundedCorner]=true text="login" ></ej-splitbutton>
                    <ul id="Ul41">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imagetextimage" target="#Ul51" size="large" [showRoundedCorner]=true contentType="imagetextimage" prefixIcon="e-icon e-handup" suffixIcon="e-icon e-palette" text="login"></ej-splitbutton>
                    <ul id="Ul51">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html %}

 
import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Easy-customization_images/Easy-customization_img3.png) 

## Image Position

To provide the best look and feel for **Split Button**, position of images in **Split Button** is important. Using **imagePosition** property, you can easily customize the position of images inside **Split Button** without using any complex CSS. **imagePosition** property is applicable only with the **textandimage** content type property. This property represent the position of images with respect to text.

Property Table

<table>
<tr><th>Image Position</th><th>Description</th></tr>
<tr>
<td>
imageleft</td><td>
Support for aligning text in right and image in left.</td></tr>
<tr>
<td>
imageright</td><td>
Support for aligning text in left and image in right.</td></tr>
<tr>
<td>
imagetop</td><td>
Support for aligning text in bottom and image in top.</td></tr>
<tr>
<td>
imagebottom</td><td>
Support for aligning text in top and image in bottom.</td></tr>
</table>

The following steps explains you the details on rendering the **Split Button** with above mentioned image position options.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageleft_normal" target="#Ul11" size="small"imagePosition="imageleft" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul11">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageleft_small" target="#Ul21" size="small"  imagePosition="imageleft" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul21">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
         
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageleft_medium" target="#Ul31" size="medium" imagePosition="imageleft" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login" ></ej-splitbutton>
                    <ul id="Ul31">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr> 
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageleft_large" target="#Ul41" size="large" imagePosition="imageleft" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login" ></ej-splitbutton>
                    <ul id="Ul41">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>  
             <td colspan="2">
                 <ej-splitbutton id="splitButton_imageright_normal" target="#Ul51" size="medium" imagePosition="imageright" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul51">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
     </table>
    <table width="500px" align="center">
        <tr>
            <td colspan="2">
                <ej-splitbutton id="splitButton_imageright_small" target="#Ul1" size="small" imagePosition="imageright" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                <ul id="Ul1">
                    <li><span>User</span></li>
                    <li><span>Guest</span></li>
                    <li><span>Admin</span></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <ej-splitbutton id="splitButton_imageright_medium" target="#Ul2" size="medium" imagePosition="imageright" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                <ul id="Ul2">
                    <li><span>User</span></li>
                    <li><span>Guest</span></li>
                    <li><span>Admin</span></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <ej-splitbutton id="splitButton_imageright_large" target="#Ul3" size="large" imagePosition="imageright" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                <ul id="Ul3">
                    <li><span>User</span></li>
                    <li><span>Guest</span></li>
                    <li><span>Admin</span></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <ej-splitbutton id="splitButton_imagetop" target="#Ul4" height="60" size="medium" imagePosition="imageright" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                <ul id="Ul4">
                    <li><span>User</span></li>
                    <li><span>Guest</span></li>
                    <li><span>Admin</span></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="2">
                <ej-splitbutton id="splitButton_imagebottom" target="#Ul5" height="60" size="medium" imagePosition="imagebottom" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                <ul id="Ul5">
                    <li><span>User</span></li>
                    <li><span>Guest</span></li>
                    <li><span>Admin</span></li>
                </ul>
            </td>
        </tr>
    </table>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/SplitButton/Easy-customization_images/Easy-customization_img4.png) 

## Theme support

You can control the style and appearance of **Split Button** based on **CSS** classes. In order to apply styles to the **Split Button** control, you can refer two files namely, **ej.widgets.core.min.css** and **ej.theme.min.css**. When you refer the **ej.widgets.all.min.css** file, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project**,** as **ej.widgets.all.min.css** is the combination of these two. 

By default, there are 12 themes support available for **Split Button** control namely

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

## Custom CSS

You can use the **CSS** class to customize the **Split Button** control appearance. Define a **CSS** class as per requirement and assign the class name to **cssClass** property.

The following steps explains you the details about rendering the **Split Button** with custom **CSS**.

In the **HTML** page, add the following button elements to configure **Split Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customCss1" target="#Ul11" cssClass="customCss1" size="small" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul11">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customCss2" target="#Ul21" cssClass="customCss2" size="small" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul21">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customCss3" target="#Ul31" cssClass="customCss3" size="small" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login" ></ej-splitbutton>
                    <ul id="Ul31">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customCss4" target="#Ul41" cssClass="customCss4" size="small" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login" ></ej-splitbutton>
                    <ul id="Ul41">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-splitbutton id="splitButton_customCss5" target="#Ul51" cssClass="customCss5" size="small" contentType="textandimage" [showRoundedCorner]=true  prefixIcon="e-icon e-handup" text="login"></ej-splitbutton>
                    <ul id="Ul51">
                        <li><span>User</span></li>
                        <li><span>Guest</span></li>
                        <li><span>Admin</span></li>
                    </ul>
             </td>
         </tr>
     </table>
    </div>
    <style type="text/css">
    /* Customize the button background */
    .e-split .customCss1 {
        background-color: #121111;
    }

    .e-split .customCss2 {
        background-color: #94bbd5;
    }

    .e-split .customCss3 {
        background-color: #f3533c;
    }

    .e-split .customCss4 {
        background-color: #d1eeed;
    }

    .e-split .customCss5 {
        background-color: #deb66e;
    }
    /* Customize the button image & text color */
    .e-split .customCss1.e-btn.e-select .e-icon, .e-split .customCss1.e-btn.e-select .e-btntxt {
        color: #94bbd5;
    }

    .e-split .customCss2.e-btn.e-select .e-icon, .e-split .customCss2.e-btn.e-select .e-btntxt {
        color: #121111;
    }

    .e-split .customCss3.e-btn.e-select .e-icon, .e-split .customCss3.e-btn.e-select .e-btntxt {
        color: #cef6f7;
    }

    .e-split .customCss5.e-btn.e-select .e-icon, .e-split .customCss5.e-btn.e-select .e-btntxt {
        color: #534f4f;
    }

    .e-split {
        float: left;
        padding-left: 25px;
    }
    </style>
    

{% endhighlight %}

{% highlight html %}


import { Component } from '@angular/core';
import { ViewEncapsulation } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: './splitButton.component.html',
	encapsulation: ViewEncapsulation.None,
})
export class SplitButtonComponent {
    constructor() {}
}

{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/SplitButton/Easy-customization_images/Easy-customization_img5.png) 

