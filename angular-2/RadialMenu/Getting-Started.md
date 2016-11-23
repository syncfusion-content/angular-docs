---
layout: post
title: Getting-Started
description: getting started
platform: angular2
control: RadialMenu
documentation: ug
---

# Getting Started

This section helps to get started of the RadialMenu component in an Angular2 application.

![](Getting_Started_images/getting-started_img1.png)

## Create a RadialMenu

The following steps guide you to add a RadialMenu component.

To get start with how to use the RadialMenu component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](https://help.syncfusion.com/angular-2/overview).

Create a simple RadialMenu by adding ej-radialmenu attribute for initializing an empty RadialMenu component on the application. 

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "radialtarget1">
    </ej-radialmenu>


{% endhighlight %}

> _Note:_ _You can find the RadialMenu properties from the_ [API reference](https://help.syncfusion.com/api/js/ejradialmenu) _document_

## Configure Items

To configure items for RadialMenu component, define e-items in component file. You can set the images for each item by giving the image URL with the **imageUrl** attribute in the inner list element and text with **text** attribute for the Item. In order to display items in RadialMenu component, you need to map the items fields to RadialMenu items. The required mapping field are listed as follows. 

* `text` - Map the item name to use as `text` values to items.

* `imageUrl` - Map the image for items to use as image to items within `Field` object.

In order to display items in RadialMenu component, you need to use **e-items** of **ej-radialmenu**.

Refer to the following code example. Initialize Radial Menu component with items and set its target content as follows.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "radialtarget1">
    <e-items>
        <e-item imageUrl="app/content/images/RadialMenu/font.png" text="Bold" ></e-item>
        <e-item imageUrl="app/content/images/RadialMenu/f1.png" text="Italic" ></e-item>
        <e-item imageUrl="app/content/images/RadialMenu/redo.png" text="Redo" ></e-item>
        <e-item imageUrl="app/content/images/RadialMenu/undo.png" text="Undo" ></e-item>
    </e-items>

    </ej-radialmenu>

{% endhighlight %}

Refer to the following code example to add target content to the RadialMenu. You need to perform any actions while selecting the RTE content, you need to add **Select** and **change** events in RTE.

{% highlight html %}

    <div id="radialtarget1">
        <textarea id="rteSample1" ej-rte width="100%" [showToolbar]="false" height="400" [(value)]="content" (select)="onSelect($event)" (change)="onChange($event)">
        </textarea>
    </div>   

{% endhighlight %}

Define the RTE content in component constructor’s file.

{% highlight ts %}

    export class AppComponent {
    content: string;
    constructor() {
        this.content = "Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it. The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram. Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants. The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusability and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.
    A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).
    A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.
    A view requests from the model the information that it needs to generate an output representation to the user.";
        }


{% endhighlight %}

## Displaying RadialMenu

You can display the Radial Menu by performing desired action on the target content while selecting the text inside the target. Therefore, call the **Select** event handler to perform the select action of the RTE content. Refer to the following code example and add it to event handler function.

{% highlight ts %}

    onSelect(event) {
        var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
        // To get Iframe positions
        iframeY = target.offset().top + event.event.clientY, iframeX = target.offset().left + event.event.clientX,
        // To set Radial Menu position within target
        x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
        y = (iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0)) + radialRadius;
        $('#defaultradialmenu').ejRadialMenu("setPosition", x, y);
        $('iframe').contents().find('body').blur();
    }


{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the following output.

![](Getting_Started_images\getting-started_img2.png)

## RadialMenu item functionalities

You can set the functionalities for each item and define click event by using **Click** event of RadialMenu. Refer to the following code example. Define the click event for Radial Menu component as follows.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "radialtarget1" (click)="onItemClick($event)">
        <e-items>
            <e-item imageUrl="app/content/images/RadialMenu/font.png" text="Bold" ></e-item>
            <e-item imageUrl="app/content/images/RadialMenu/f1.png" text="Italic" ></e-item>
            <e-item imageUrl="app/content/images/RadialMenu/redo.png" text="Redo" ></e-item>
            <e-item imageUrl="app/content/images/RadialMenu/undo.png" text="Undo" ></e-item>
        </e-items>
    </ej-radialmenu>


{% endhighlight %}

Refer to the following code example to add functionalities for each items in event handler for items click and you can enable items in RadialMenu by using **Change** event in component constructor’s file.



{% highlight ts %}

    onChange(event) {
        $('#defaultradialmenu').ejRadialMenu("enableItem", "Undo");
    }
    onItemClick(e) {
        var rteObj = $("#rteSample1").data("ejRTE");
        var itemName = (ej.isNullOrUndefined(e.text)) ? "none" : e.text.toLowerCase();
        switch (itemName) {
        case "bold":
            rteObj.executeCommand("bold");
            break;
        case "italic":
            rteObj.executeCommand("italic");
            break;
        case "undo":
            rteObj.executeCommand("undo");
            break;
        case "redo":
            rteObj.executeCommand("redo");
            break;
    }

{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the RadialMenu component. Click **bold** item in RadialMenu component, to render the following output.

![](Getting_Started_images\Getting_Started_img3.png)







