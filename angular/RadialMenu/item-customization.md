---
layout: post
title: Syncfusion Radial Menu item-customization
description: item customization
platform: Angular
control: Radial Menu
documentation: ug
---

# Item Customization

You can customize individual Radial Menu items by using the items properties.

## Adding image and text to RadialMenu Items

The **imageUrl** property specifies the URL of the image for the items. **text** attribute is used to specify the item text. 

Refer to the following code example.

Define imageUrl and text values in HTML page.


{% highlight html %}

    <ej-radialmenu id="defaultRadialMenu" e-targetelementid="radialtarget1" [radius]="radius">
    <e-items>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/copy.png" text="Copy"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/paste.png" text="Paste"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/redo.png" text="Redo"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/undo.png" text="Undo"></e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}


The following screenshot illustrates the output.

![Item customization](item-customization_images\item-customization_img1.png)

## Adding events to Radial Menu

You can specify the click event to the Radial Menu for performing some specific action. You need to handle the click event in script manually for each item click.

Declare **click** event values in HTML page.


{% highlight html %}


    <ej-radialmenu id="defaultRadialMenu" targetelementid="radialtarget1" (click)="onItemClick($event)">
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

Define the click functions and radialMenu show function in constructor file.
    
{% highlight javascript %}

    export class AppComponent {
    content: string; 
    radius: any;  
    constructor() {
    this.content = "Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it. The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram. Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants. The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusability and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.A view requests from the model the information that it needs to generate an output representation to the user.";	
	this.radius = 200;
    $(window).resize(function() {
    if (ej.isMobile() && ej.isPortrait())
    $('#apiRadialMenu').css({ "left": 25 })
    }); 
    }

    onSelect(event) {
    var rteObj = $("#rteSample1").data("ejRTE");
    var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
      // To get Iframe positions
      iframeY = target.offset().top + event.event.clientY, iframeX = target.offset().left + event.event.clientX,
      // To set Radial Menu position within target
      x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
      y = (iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0)) + radialRadius;
    $('#defaultRadialMenu').ejRadialMenu("setPosition", x, y);
    $('iframe').contents().find('body').blur();
    }
    onChange(event) {
        $('#defaultRadialMenu').ejRadialMenu("enableItem", "Undo");
    }   
    onItemClick(e) {
    var rteObj = $("#rteSample1").data("ejRTE");
    var itemName = (ej.isNullOrUndefined(e.text)) ? "none" : e.text.toLowerCase();
    switch (itemName) {
      case 'bold':
        rteObj.executeCommand('bold');
        break;
      case 'italic':
        rteObj.executeCommand('italic');
        break;
      case 'undo':
        rteObj.executeCommand('undo');
        break;
      case 'redo':
        rteObj.executeCommand('redo');
        break;
      case 'numbering':
        rteObj.executeCommand('insertorderedList');
        break;
      case 'bullets':
        rteObj.executeCommand('insertunorderedList');
        break;
      case 'left':
        rteObj.executeCommand('justifyLeft');
        break;
      case 'right':
        rteObj.executeCommand('justifyRight');
        break;
    }
    } 
    }

{% endhighlight %}


The following screenshot illustrates the output.

![Adding events](item-customization_images\item-customization_img2.png)


## Badge Customization in Radial Menu Items

You can specify set badges for the items by using badge settings in the radial menu. You can set value for the badge and enable badge with a default value.

The **badge-enabled** property to enable or disable badges. **badge-value** attribute is to set the badge value.

Declare badge properties in HTML Page.


{% highlight html %}

    <ej-radialmenu id="defaultRadialMenu" e-targetelementid="radialtarget1">
    <e-items>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/copy.png" text="Copy" enabled="true" [badge]="badgeSettings"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/paste.png" text="Paste"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/redo.png" text="Redo"></e-item>
        <e-item imageUrl="http://js.syncfusion.com/demos/web/content/images/RadialMenu/undo.png" text="Undo"></e-item>
    </e-items>
    </ej-radialmenu>


{% endhighlight %}


Define badge properties in constructor file.

{% highlight javascript %}

    export class AppComponent {    
    badgeSettings:any;  
    constructor() {   
	this.badgeSettings={enabled:true,value:3};  	 
    }

{% endhighlight %}

The following screenshot illustrates the output.

![Badge customization](item-customization_images\item-customization_img3.png)

## Slider Customization in Radial Menu Items

You can customize the Radial Menu with slider settings. The **type** property specifies the type of radial menu item, where you can set the type for RadialMenu item.

You can customize the Radial Menu slider settings by using the **ticks**, **strokeWidth** and **labelSpace** properties. The **sliderSettings-ticks** property specifies the slider ticks for radial menu item. **sliderSettings-strokeWidth** attribute is used to specify the slider’s stroke width value. **sliderSettings-labelSpace** attribute is used to specify the value of slider label space.

Refer to the following code example.


{% highlight html %}

    <ej-radialmenu id="defaultRadialMenu" targetelementid="radialtarget1" (click)="onItemClick($event)">
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

Define slider ticks values in constructor file.
    
{% highlight javascript %}

    export class AppComponent {    
    badgeSettings:any;  
    sliderSettings:any;
    constructor() {    
	this.badgeSettings={enabled:true,value:2};
	this.sliderSettings={ ticks : [0, 2, 4, 6, 8, 10, 12, 14],
        strokeWidth : 1
		};  
    }
{% endhighlight %}

The following screenshot illustrates the output.

![Slider Customization](item-customization_images\item-customization_img4.png)

















