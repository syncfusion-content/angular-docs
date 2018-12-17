---
layout: post
title: Syncfusion Splitter Apperance and Styling
description: Apperance and Styling
platform: Angular
control: Splitter
documentation: ug
---

# Appearance and Styling

## Html Attributes

You can add styles to Splitter component by using **htmlAttributes** option. The following steps explain the implementation of **htmlAttributes** option in the Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner splitter component.


{% highlight html %}

    <ej-splitter id="splitter" class="ang-splitter" height ="100%" width="485" [properties]="proper" [orientation]="orientation" [htmlAttributes]="htmlAttributes">					                
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
                </div>
            </div>
    </ej-splitter>

{% endhighlight %}

Define **“htmlAttributes”** properties in constructor file.

{% highlight javascript %}

    export class AppComponent {
        proper:any;
        orientation:any;
        htmlAttributes:any;	 
        constructor() {
        this.proper1 = [{}, {}];
        this.orientation = ej.Orientation.Vertical;
        this.htmlAttributes = { class: "my-class", style: "border:1px solid red" };
      }
    }

{% endhighlight %}

The output for the above code as follows,

![Appearance and Styling](Appearance-and-Styling_images\Appearance-and-Styling_img1.png) 

## Enabling Responsiveness

The **isResponsive** option allows the Splitter component to adapt its rendering based on the parent container where it is actually placed. When this option is set to true, the Splitter component adjusts its height and width based on the outer container.

The following steps explain the implementation of Responsive option in the Splitter component.
In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner splitter component.

{% highlight html %}

    <ej-splitter id="outterSpliter" class="ang-splitter" height ="100%" width="485" [properties]="proper1"
        [isResponsive]="responsive1" [orientation]="orientation">
    <div>
    <div style="padding: 0px 15px;">
        <h3 class="h3"> JavaScript </h3>
    </div>
    </div>	
    <div>		  
        <ej-splitter id="innersplitter" [properties]="proper2" width="600" [isResponsive]="responsive2">
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Tools </h3>
            Essential Tools is an collection of user interface components used to create interactive
            JavaScript applications.
        </div>
    </div>  
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Grid </h3>
            Essential JavaScript Grid offers full featured a Grid control with extensive support for
            Grouping and the display of hierarchical data.
        </div>
    </div>
    </ej-splitter>
    </div>
    </ej-splitter>   


{% endhighlight %}

Define **“isResponsive”** true in constructor file.

{% highlight javascript %}

    export class AppComponent {
        proper1:any;
        orientation:any;
        responsive1:any;
        responsive2:any;	 
        constructor() {
        this.proper1 = [{ paneSize: 60 }];
        this.orientation = ej.Orientation.Vertical;
        this.responsive1 = true;
        this.responsive2 = true;
      }
    }

{% endhighlight %}

## Animation Support

**Splitter** provides you animation support when you expand or collapse the pane. The animation speed can be modified by using the **animationSpeed** property that has values in milliseconds.

### Enabling Animation with Animation Speed

The following steps explain the implementation of **enableAnimation** option in the Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <ej-splitter id="splitter" class="ang-splitter" height ="100%" width="485" [properties]="proper" [orientation]="orientation" [enableAnimation]="animation" [animationSpeed]="speed">					                
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
                </div>
            </div>
    </ej-splitter>

{% endhighlight %}

Define **“animationSpeed”** and **“enableAnimation”** properties in constructor file.

{% highlight javascript %}

    export class AppComponent {
        proper:any;
        orientation:any;
        animation:any;
        speed:any;	 
        constructor() {
        this.proper1 = [{}, { collapsible: true }];
        this.speed = 300;
        this.animation = true;
        }
    }

{% endhighlight %}

The output for **Splitter** when **enableAnimation** is “True”. Expanding or collapsing the outer pane in the Splitter produces the animation effect with the animation speed.

![Enable Animation](Appearance-and-Styling_images\Appearance-and-Styling_img2.png) 

## Dimensions configuration

   You can adjust the splitter size by height, width, maxSize, minSize and paneSize properties.

### Height
   The height of Splitter can be modified by using the **height** property. The default value for e-height property is null in Splitter. You can set the height property by pixel or percentage values.

### Width

   The width of Splitter can be modified by using the **width** property. The default value for e-width property is null in Splitter. You can set the width property by pixel or percentage values.

### MaxSize

   Defines the maximum resizable size of the pane when you resize the Splitter component. The default value of **maxSize** is null in Splitter. You can set the maxSize property by pixel values.

### MinSize

   Defines the minimum resizable size of the pane when you resize the Splitter component. The default value of **minSize** is 10px in Splitter. You can set the minSize property by pixel values.
### PaneSize

   Defines the pane size in the Splitter component. The default value of **paneSize** is 0px in Splitter. You can set the paneSize property in pixels or percentage values.

### Resizable

   Defines whether the pane in the Splitter is resizable or not. Setting the **resizable** property as “False” disables the resize option to the pane. The default value of resizable property is true in Splitter.

   The following steps explain the implementation of Splitter properties.
    
   In the **HTML** page set the **&lt;div&gt;** element for rendering Splitter component.
    
   {% highlight html %}
   
    <ej-splitter id="splitter" class="ang-splitter" height ="100%" width="485" [properties]="proper">					                
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
                </div>
            </div>
    </ej-splitter>
   
   {% endhighlight %}
   
   Define **“Resizable”** property set as true in constructor file.
   
   {% highlight javascript %}
   
    export class AppComponent {
        proper:any;   
        constructor() {
        this.proper = [{}, { collapsible: true, minSize: 100, maxSize: 800, paneSize: 300, resizable: true }]; 
        }   
    }

   {% endhighlight %}
   
## Theme

**Splitter** component style and appearance can be controlled based on CSS classes. To apply styles to the Splitter component, refer 2 files namely: **ej.widgets.core.min.css** and **ej.theme.min.css**. If the file ej.web.all.min.css is referred, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project, as **ej.web.all.min.css** is the combination of these two.
By default, the following themes support available for Splitter component namely

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
* high-contrast-01
* high-contrast-02
* material
* office-365

### Customize using CSS class

The CSS properties can be customized by using **e-cssClass** in the Splitter component. The following steps explain the implementation of e-cssClass option in the Splitter component.
In the **HTML** page set the corresponding **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <ej-splitter id="splitter" class="ang-splitter" height ="100%" width="485" [cssClass]="cssClass">					                
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
                </div>
            </div>
    </ej-splitter>

{% endhighlight %}

Define **“cssClass”** in constructor file.

{% highlight javascript %}

    export class AppComponent {
        cssClass:any;   
        constructor() {
        this.cssClass ="customCSS";
        }
    }

{% endhighlight %}

Customize the **CSS** class by setting CSS properties.

{% highlight css %}

    .customCSS {
        border-color: #661e19;
    }

    /*Customize SplitBar*/
    .customCSS .e-splitbar {
        background-color: #f9c89f;
    }

    /*Customize Splitter pane*/
    .customCSS .e-pane {
        color: #b21010;
        background-color: #f6e492;
    }     

{% endhighlight %}

The output for Splitter after customizing the CSS class.

![Customize using class](Appearance-and-Styling_images\Appearance-and-Styling_img3.png) 





