---
layout: post
title: Easy-Customization
description: easy customization
platform: Angular
control: Toggle Button
documentation: ug
---

# Easy Customization

**Toggle Button** is used in all applications. Toggle Button Size, Content and content location is varied according to each application. The following section contains some customizable option for **Toggle Button** that can perform easily. 

## Toggle State

**Toggle Button** has two states like off / on state in a switch. By default you can set any state at initial and then you can move from one state to another state by clicking on the **Toggle Button**. These two states are **Default** and **Active.** **toggleState** property is used to set the state of **Toggle Button** as default state or active state.

The following steps explains you the details about rendering the **Toggle Button** with different toggle state.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_default" contentType="textandimage" defaultText="Play" [toggleState]="false" size="small" activeText="Pause" defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
             </td>
         </tr>
        <tr>
            <td colspan="2">
                <ej-togglebutton type="checkbox" id="toggle_active" contentType="textandimage" defaultText="Play" [toggleState]="true" size="large" activeText="Pause" defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
            </td>
        </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    constructor() {
    }
}

{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img1.png) 


## Toggle state with icons

### Prefix and Suffix Icons

You can add icons in prefix and suffix position of **Toggle Button**. Location of Icon is customized easily using the following mentioned option. This is applicable for the content type’s **imageOnly**, **textandimage**, **imagetextimage** and **imageboth**.

**Toggle Button** control also supports the Built-in icon libraries. The **ej.widgets.core.min.css** contains the definition for important icons that are used in toggle buttons. You can use these Built-in icons by mentioning the icon class name as value in **defaultPrefixIcon**, **defaultSuffixIcon**, **activePrefixIcon**, and **activeSuffixIcon** property. You can use any font icons that is defined in **ej.widgets.core.min.css**. It avoids the complexity in specifying icon using sprite image and CSS.

For example the following mentioned Built-in CSS class are used to show the font icons that are used by media player.

* e-mediaback
* e-mediaforward
* e-medianext
* e-mediaprev
* e-mediaeject
* e-mediaclose
* e-mediapause
* e-mediaplay

### Prefix Icon

It inserts the icon at the starting position of **Toggle Button**. After this prefix icon, you can use text or suffix icon.

### Suffix Icon

It inserts the icon at the ending position of **Toggle Button**. Before this suffix icon, you can use text or prefix icon.

You can also set icon in different location (prefix, suffix) and in different state (default, active) by using the option provided. The following properties are defined for merging the option to add text, icon with different position and in toggle states.

Property Table

<table>
<tr><th>Property Type</th>
    <th>Description</th></tr>
<tr>
<td>
activeText</td><td>
Specifies the text of toggle button in active state</td></tr>
<tr>
<td>
    activePrefixIcon</td><td>
Specifies the prefix icon of toggle button in active state</td></tr>
<tr>
<td>
activeSuffixIcon</td><td>
Specifies the suffix icon of toggle button in active state</td></tr>
<tr>
<td>
defaultText</td><td>
Specifies the text of toggle button in default state.</td></tr>
<tr>
<td>
defaultPrefixIcon</td><td>
Specifies the prefix icon of toggle button in default state</td></tr>
<tr>
<td>
defaultSuffixIcon</td><td>
Specifies the suffix icon of toggle button in default state</td></tr>
</table>


The following steps explains you the details about rendering the **Toggle Button** with above mentioned customization properties.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget


{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_content" contentType="textandimage"  [showRoundedCorner]="true" defaultText="forward" [toggleState]="false" activeText="backward" defaultPrefixIcon="e-icon e-mediaforward" activePrefixIcon="e-icon e-mediaback" defaultSuffixIcon="e-icon e-undo" activeSuffixIcon="e-icon e-redo"></ej-togglebutton>
                 <label id="toggle_content"></label>
             </td>
         </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    constructor() {
    }
}

{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img2.png) 


![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img3.png) 


## Toggle button size

You can render the **Toggle Button** in different sizes. You can use some predefined size option for rendering a **Toggle Button** in easiest way. Each size option has different height and width. It mainly avoids the complexity in rendering **Toggle Button** with complex CSS class. You can mention the **size** of the **Toggle Button** using the following five predefined size options. 

Predefined Toggle Button size

<table>
<tr><th>Button Size</th><th>Description</th></tr>
<tr>
<td>
normal</td><td>
Creates toggle button with content size.</td></tr>
<tr>
<td>
mini</td><td>
Creates toggle button with Built-in mini size height, width specified.</td></tr>
<tr>
<td>
small</td><td>
Creates toggle button with Built-in small size height, width specified.</td></tr>
<tr>
<td>
medium</td><td>
Creates toggle button with Built-in medium size height, width specified.</td></tr>
<tr>
<td>
large</td><td>
Creates toggle button with Built-in large size height, width specified.</td></tr>
</table>


You can also set your own width and height for toggle button using height and width property.

The following steps explains you the details about rendering the **Toggle Button** with above mentioned size options.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}


    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td> Normal</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="togglebutton1" contentType="imageonly"  size="normal" defaultPrefixIcon="e-icon e-mediaplay" [toggleState]="state" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
             </td>
         </tr>
         <tr>
             <td> Mini</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="togglebutton2" contentType="textandimage" defaultText="Play" [toggleState]="state" size="mini" activeText="Pause" ></ej-togglebutton>
             </td>
         </tr>

         <tr>
             <td> Small</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="togglebutton3" contentType="textandimage" defaultText="Play" [toggleState]="state" size="small" activeText="Pause" ></ej-togglebutton>
             </td>
         </tr>
         <tr>
             <td> Medium</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="togglebutton4" contentType="textandimage" defaultText="Play" [toggleState]="state" size="medium" activeText="Pause" ></ej-togglebutton>
             </td>
         </tr>
         <tr>
             <td> Large</td>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="togglebutton5" contentType="textandimage" defaultText="Play" [toggleState]="state" size="large" activeText="Pause" defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
             </td>
         </tr>
     </table>
    </div>
    <style>
       td{
			padding:5px;
		}
    </style>
	
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    state: boolean;
    constructor() {
        this.state = false;
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img4.png) 

## Content type

The content of the **Toggle Button** is mainly text and images. Instead of using complex CSS classes to render **Toggle Button** with different content types, you can use some predefined content type options as listed in the following table. Using this content type you can easily add different types of content for **Toggle Button**. The **Toggle Button** supports the following content types.

List of Content types

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
Supports image for both ends of the toggle button.</td></tr>
<tr>
<td>
textandimage</td><td>
Supports image with the text content.</td></tr>
<tr>
<td>
imagetextimage</td><td>
Supports image with both ends and middle in text.</td></tr>
</table>


The following steps explains you the details about rendering the **Toggle Button** with above mentioned **content type** options.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageonly" contentType="imageonly" defaultPrefixIcon="e-icon e-mediaplay" [showRoundedCorner]="state" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageonly">Toggle</label>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_textonly" contentType="textonly" defaultText="Play" [showRoundedCorner]="state"  activeText="Next"></ej-togglebutton>
                 <label for="toggle_textonly">Toggle</label>
             </td>
         </tr>
         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageboth" contentType="imageboth"  [showRoundedCorner]="state" defaultPrefixIcon="e-icon e-mediaforward" activePrefixIcon="e-icon e-mediaback" defaultSuffixIcon="e-icon e-undo" activeSuffixIcon="e-icon e-redo" ></ej-togglebutton>
                 <label for="toggle_imageboth">Toggle</label>
              </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_textandimage" contentType="textandimage" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_textandimage">Toggle</label>
              </td>
         </tr>
         <tr>           
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imagetextimage" contentType="imagetextimage" defaultText="forward" [showRoundedCorner]="state"  activeText="backward" defaultSuffixIcon="e-icon e-undo" activeSuffixIcon="e-icon e-redo"  ></ej-togglebutton>
                 <label for="toggle_imagetextimage">Toggle</label>
             </td>
         </tr>
     </table>
    <table width="500px"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageonly_small" contentType="imageonly" defaultPrefixIcon="e-icon e-mediaplay" [showRoundedCorner]="state" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageonly_small">Toggle</label>
             </td>
         </tr>
         <tr>  
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageboth_small" contentType="textonly" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" ></ej-togglebutton>
                 <label for="toggle_imageboth_small">Toggle</label>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_textandimage_small" contentType="imageboth" [showRoundedCorner]="state"  defaultPrefixIcon="e-icon e-mediaforward" activePrefixIcon="e-icon e-mediaback" defaultSuffixIcon="e-icon e-undo" activeSuffixIcon="e-icon e-redo"></ej-togglebutton>
                 <label for="toggle_textandimage_small">Toggle</label>
              </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imagetextimage_small" contentType="textandimage" defaultText="Play" [showRoundedCorner]="state"  activeText="Next"  defaultPrefixIcon="e-icon e-mediaplay" activePrefixIcon="e-icon e-mediapause" ></ej-togglebutton>
                 <label for="toggle_imagetextimage_small">Toggle</label>
              </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_textandimage_small" contentType="imagetextimage" defaultText="forward" [showRoundedCorner]="state" activeText="backward" defaultPrefixIcon="e-icon e-mediaforward" activePrefixIcon="e-icon e-mediaback" defaultSuffixIcon="e-icon e-undo" activeSuffixIcon="e-icon e-redo"></ej-togglebutton>
                 <label for="toggle_textandimage_small">Toggle</label>
             </td>
         </tr>
     </table>
    </div>
    
{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    state: boolean;
    constructor() {
        this.state = false;
    }
}

{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img5.png) 


## Image position

To provide the best look and feel for **Toggle Button**, position of images in toggle button is important. You can easily customize the position of images inside toggle button using **imagePosition** property without using any complex CSS. **imagePosition** property is applicable only with the **textandimage** content type property. This property represent the position of images with respect to text.

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


The following steps explains you the details about rendering the **Toggle Button** with above mentioned image Position options.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageleft_normal" size="normal" contentType="textandimage"  imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageleft_normal">Toggle</label>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageleft_mini" size="mini" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageleft_mini">Toggle</label>
             </td>
         </tr>

         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageleft_small" size="small" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageleft_small">Toggle</label>
              </td>
         </tr>
         <tr>
          
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageleft_medium" size="medium" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageleft_medium">Toggle</label>
              </td>
         </tr>
         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageleft_large" size="large" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageleft_large">Toggle</label>
             </td>
         </tr>
     </table>
    <table width="500px"> 
         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageright_normal" size="normal" contentType="textandimage" imagePosition="imageright" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageright_normal">Toggle</label>
             </td>
         </tr>
         <tr>
             
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageright_mini" size="mini" contentType="textandimage" imagePosition="imageright" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause" ></ej-togglebutton>
                 <label for="toggle_imageright_mini">Toggle</label>
             </td>
         </tr>

         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageright_small" size="small" contentType="textandimage" imagePosition="imageright" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageright_small">Toggle</label>
              </td>
         </tr>
         <tr>
            
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageright_medium" size="medium" contentType="textandimage" imagePosition="imageright" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause" ></ej-togglebutton>
                 <label for="toggle_imageright_medium">Toggle</label>
              </td>
         </tr>
         <tr>
             
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_imageright_large" size="large" contentType="textandimage" imagePosition="imageright" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_imageright_large">Toggle</label>
             </td>
         </tr>
        <tr>
            <td colspan="2">
                <ej-togglebutton type="checkbox" id="toggle_imagetop" height="60" contentType="textandimage" imagePosition="imagetop" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                <label for="toggle_imagetop">Toggle</label>
            </td>
        </tr>
        <tr>

            <td colspan="2">
                <ej-togglebutton type="checkbox" id="toggle_imagebottom" height="60" contentType="textandimage" imagePosition="imagebottom" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state" activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                <label for="toggle_imagebottom">Toggle</label>
            </td>
        </tr>
     </table>
    </div>

{% endhighlight %}

{% highlight html }

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    state: boolean;
    constructor() {
        this.state = false;
    }
}

{% endhighlight %}

Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img6.png) 



## Theme support

You can control the style and appearance of **Toggle Button** based on CSS classes. To apply styles to the **Toggle Button** control, you can refer two files, **ej.widgets.core.min.css** and **ej.theme.min.css**. When you refer **ej.widgets.all.min.css** file, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project**,** as **ej.widgets.all.min.css** is the combination of these two. 

By default, there are 12 themes support available for **Toggle Button** control namely,

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

You can use the CSS to customize the **Toggle Button** control appearance. Define a CSS class as per requirement and assign the class name to **cssClass** property.

The following steps explains you the details about rendering the **Toggle Button** with custom CSS.

In the **HTML** page, add the following button elements to configure **Toggle Button** widget.

{% highlight html %}

    <div align="center">
    <table width="500px" align="center"> 
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_customCss1"   cssClass="customCss1" size="small" contentType="textandimage"  imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_customCss1">Toggle</label>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_customCss2"  cssClass="customCss2" size="small" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_customCss2">Toggle</label>
             </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_customCss3"  cssClass="customCss3" size="small" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_customCss3">Toggle</label>
              </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_customCss4"  cssClass="customCss4" size="small" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_customCss4">Toggle</label>
              </td>
         </tr>
         <tr>
             <td colspan="2">
                 <ej-togglebutton type="checkbox" id="toggle_customCss5"  cssClass="customCss5" size="small" contentType="textandimage" imagePosition="imageleft" defaultPrefixIcon="e-icon e-mediaplay" defaultText="Play" [showRoundedCorner]="state"  activeText="Next" activePrefixIcon="e-icon e-mediapause"></ej-togglebutton>
                 <label for="toggle_customCss5">Toggle</label>
             </td>
         </tr>
     </table>
    </div>
    <style type="text/css" class="cssStyles">
    /* Customize the button background */
    .e-togglebutton.customCss1 {
        background-color: #121111;
    }
    .e-togglebutton.customCss2 {
        background-color: #94bbd5;
    }

    .e-togglebutton.customCss3 {
        background-color: #f3533c;
    }

    .e-togglebutton.customCss4 {
        background-color: #d1eeed;
    }

    .e-togglebutton.customCss5 {
        background-color: #deb66e;
    }
    /* Customize the button image & text color */
    .e-togglebutton.customCss1.e-btn.e-select .e-icon, .e-togglebutton.customCss1.e-btn.e-select .e-btntxt {
        color: #94bbd5;
    }

    .e-togglebutton.customCss2.e-btn.e-select .e-icon, .e-togglebutton.customCss2.e-btn.e-select .e-btntxt {
        color: #121111;
    }

    .e-togglebutton.customCss3.e-btn.e-select .e-icon, .e-togglebutton.customCss3.e-btn.e-select .e-btntxt {
        color: #cef6f7;
    }

    .e-togglebutton.customCss5.e-btn.e-select .e-icon, .e-togglebutton.customCss5.e-btn.e-select .e-btntxt {
        color: #534f4f;
    }
    </style>

{% endhighlight %}

{% highlight html %}

import { Component } from '@angular/core';
@Component({
    selector: 'ej-app',
    templateUrl: './togglebutton.component.html'
})
export class ToggleButtonComponent {
    state: boolean;
    constructor() {
        this.state = false;
    }
}

{% endhighlight %}


Execute the above code to render the following output.

![](/Angular/ToggleButton/Easy-Customization_images/Easy-Customization_img7.png) 



