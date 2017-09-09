---
layout: post
title: Template Support.
description: Template Support.
platform: Angular
control: Radial Menu
documentation: ug
---

## Template Support

 Template support for RadialMenu items will allow you to use any type of [\<svg\>](https://developer.mozilla.org/en-US/docs/Web/SVG/Element#SVG_elements) Permittable tags inside our template. Here for example, using this template support you can use the SVG icons in Radial Menu instead of image tags. To use SVG icons in RadialMenu, you need to use [prependTo](https://help.syncfusion.com/api/js/ejradialmenu#members:items-prependTo) property.

 ### Add SVG to item Icon

Using SVG icon will optimize the icons quality and to reduce space occupation by normal images and svg images are scalable and zoomable. Define the text element for SVG with x and y position and code for rendering the font icons. Assign the SVG element ID to **prependTo** property.

{% highlight html %}

    <div id="radialtarget1">
     <textarea id="rteSample1"  style="height: 440px" [showContextMenu]="false"   ej-rte width="100%" [showToolbar]="false" height="400" [(value)]="content" (select)="onSelect($event)" (ejchange)="onChange($event)">
    </textarea>
	<svg id="template1" style="display: none" xmlns="http://www.w3.org/2000/svg">
        <text x="210" y="100">&#xe636;</text>
    </svg>
    <svg id="template2" style="display: none" xmlns="http://www.w3.org/2000/svg">
        <text x="210" y="218">&#xe635;</text>
    </svg>
    <svg id="template3" style="display: none" xmlns="http://www.w3.org/2000/svg">
        <text x="90" y="215">&#xe606;</text>
    </svg>
    <svg id="template4" style="display: none" xmlns="http://www.w3.org/2000/svg">
        <text x="93" y="100">&#xe607;</text>
    </svg>
        </div>     
    <ej-radialmenu id="defaultradialmenu"  backImageClass= "backimageclass" targetElementId= "rteSample1" (ejclick)="onItemClick($event)">
    <e-items>
        <e-item prependTo="#template1" text="Bold" ></e-item>
        <e-item prependTo="#template2" text="Italic" ></e-item>
        <e-item prependTo="#template3" text="Redo" ></e-item>
        <e-item prependTo="#template4" text="Undo" enabled=false></e-item>
    </e-items>
    </ej-radialmenu>
         
    
{% endhighlight %}

Now add the following in corresponding typescript file,

{% highlight javascript %}

     import { Component,ViewEncapsulation } from '@angular/core';

        declare var $: any;
        @Component({
        selector: 'ej-app',
        templateUrl: './default.component.html',
          styleUrls: ['./default.component.css'],
        encapsulation: ViewEncapsulation.None
        })
        export class DefaultComponent {
         content: any;
         constructor() {
         this.content = 'Model–view–controller (MVC) is a software architecture pattern which separates the representation of information  from the user' +
         'interaction with it.The model consists of application data, business rules, logic, and functions.A view can be; any output representation of data,' +
          'such as a chart or a diagram.Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.' +
         ' The controller mediates input, converting it to commands for the model or view.<br/> The central ideas behind MVC are code reusability and in addition' +
         ' to dividing the application into three kinds of components, the MVC design defines the interactions between them.A controller can send commands' +
        ' to its associated view to change the view presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model state' +
         '(e.g., editing a document).A model notifies its associated views and controllers when there has been a change in its state.This notification allows the views to produce updated' +
        ' output, and the controllers to change the available set of commands.A passive     implementation of MVC omits these' +
        ' notifications, because the application does not require them or the software platform does not support them.A view requests from the model the information that it needs to' +
      ' generate an output representation to the user.';
        }
     onSelect(event) {
      let target;
      let radialRadius;
      let radialDiameter;
      let iframeY;
      let iframeX;
      let xPos;
      let yPos;
      let x;
      let y;
      target = $('#radialtarget1');
      $('#defaultradialmenu').ejRadialMenu({autoOpen: true});
      radialRadius = 150;
      radialDiameter = 2 * radialRadius;
      iframeY = target.offset().top + event.event.clientY;
      iframeX = target.offset().left + event.event.clientX;
      xPos = (iframeX > radialRadius ? iframeX - radialRadius : 0);
      yPos = (iframeY > radialRadius ? iframeY - radialRadius : 0);
      x = iframeX > (target.width() - radialRadius) ? (target.width() - radialDiameter) : xPos;
      y = iframeY > (target.height() - radialRadius) ? (target.height() - radialDiameter) : yPos;
      $('#defaultradialmenu').ejRadialMenu('setPosition', x, y);
    }
    onChange(event) {
        $('#defaultradialmenu').ejRadialMenu('enableItem', 'Undo');
    }
    onItemClick(e) { 
        let rteObj = $('#rteSample1').data('ejRTE');
        let itemName = (ej.isNullOrUndefined(e.model.items[e.index].text)) ? 'none' : e.model.items[e.index].text.toLowerCase();
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
        }
      }
    }


{% endhighlight %}

Add the following in style sheet,

{% highlight css %}

    <style>
         .e-radialmenu .image-class {
            background-image: url(../content/images/RadialMenu/settings.png);
        }
        @font-face {
            font-family: 'ej-webfont';
           
        }

        .e-radialmenu .e-abs.e-radialshow, .e-radialmenu .e-abs.e-scaleshow {
            /* use !important to prevent issues with browser extensions that change fonts */
            font-family: 'ej-webfont' !important;
            speak: none;
            font-size: 20px;
            font-style: normal;
            font-weight: normal;
            font-variant: normal;
            text-transform: none;
            line-height: 1;
            -webkit-font-smoothing: antialiased;
            /* Better Font Rendering =========== */
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

    </style>

{% endhighlight %}

The following screenshot illustrates the output,

![](template-support\img1.png)

 N> This is the example sample for SVG icon support for Radial Menu.Like wise you can add any SVG element to it, but you need to customize and position the element individually.  


