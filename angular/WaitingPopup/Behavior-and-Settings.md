---
layout: post
title: Behavior-and-Settings
description: behavior and settings
platform: Angular
control: WaitingPopup
documentation: ug
---

# Behavior and Settings

## Automatic Initializing WaitingPopup widget

**WaitingPopup** widget contains [showOnInit](https://help.syncfusion.com/api/js/ejwaitingpopup#members:showoninit) property that allows the popup to display over a target on page load automatically. By default, **showOnInit** property is set as false.

The following code helps you on how to display the **WaitingPopup** on page load.

{% highlight html %}

<div id="parent">
    <ej-waitingpopup id="waitingPopUp" [target]="target" [showOnInit]="true"></ej-waitingpopup>  
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core'; 
@Component({
    selector: 'sd-home',
    templateUrl: 'app/components/waitingpopup/waitingpopup.component.html',
    styleUrls: ['app/components/waitingpopup/waitingpopup.component.css'],
    encapsulation: ViewEncapsulation.None
    })
    export class WaitingPopupComponent {
        target: string;
        constructor() {
            this.target = "#parent";
        }                        
    }

{% endhighlight %}

 Add the following styles to render **WaitingPopup** widget in waitingpopup.component.css.

{% highlight css %}

 #parent {
    height: 320px;
    width: 600px;
 }

{% endhighlight %}

The following screenshot illustrates the **WaitingPopup** when **showOnInit** is set to “**true**”.

![](Behavior-and-Settings_images/Behavior-and-Settings_img1.png) 

## Enable / Disable Popup Indicator

You can show or hide the popup indicator of **WaitingPopup** widget using [showImage](https://help.syncfusion.com/api/js/ejwaitingpopup#members:showimage) property. By default, **showImage** property is set as **true**.

The following code helps you to enable / disable popup indicator in **WaitingPopup** widget.

{% highlight html %}

// To configure Enable / Disable popup indicator in WaitingPopup, use the following code.
    //Enable popup indicator:
    <div id="parent">
        <ej-waitingpopup id="waitingPopUp" [target]="target" [showOnInit]="true" [showImage]="true" [text]="text"></ej-waitingpopup>  
    </div>  
    
   //Disable popup indicator:
    <div id="parent">
        <ej-waitingpopup id="waitingPopUp" [target]="target" [showOnInit]="true" [showImage]="false" [text]="text"></ej-waitingpopup>  
   </div>  
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core'; 
@Component({
    selector: 'sd-home',
    templateUrl: 'app/components/waitingpopup/waitingpopup.component.html',
    styleUrls: ['app/components/waitingpopup/waitingpopup.component.css'],
    encapsulation: ViewEncapsulation.None
    })
    export class WaitingPopupComponent { 
        text: string;
        target: string;
        constructor(){
            this.text="Loading... Please wait...";
            this.target = "#parent";
        }                        
    }

{% endhighlight %}

Add the following styles to render **WaitingPopup** widget in waitingpopup.component.css.

{% highlight css %}

  #parent {
    height: 320px;
    width: 600px;
  }

{% endhighlight %}

Execute the above code to render the following output.

![](Behavior-and-Settings_images/Behavior-and-Settings_img2.png) 

![](Behavior-and-Settings_images/Behavior-and-Settings_img3.png) 

## Show / Hide WaitingPopup

Using [show()](https://help.syncfusion.com/api/js/ejwaitingpopup#methods:show) and [hide()](https://help.syncfusion.com/api/js/ejwaitingpopup#methods:hide) methods, you can display or hide the **WaitingPopup** widget over the target area.

The following code helps you to show / hide the **WaitingPopup** widget.

{% highlight html %}

<div id="parent">
    <ej-waitingpopup id="waitingPopUp" [target]="target"></ej-waitingpopup>
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core'; 
@Component({
    selector: 'sd-home',
    templateUrl: 'app/components/waitingpopup/waitingpopup.component.html',
    styleUrls: ['app/components/waitingpopup/waitingpopup.component.css'],
    encapsulation: ViewEncapsulation.None
    })
    export class WaitingPopupComponent { 
        target: string;
        constructor() {
            this.target = "#parent";
        }
    }

{% endhighlight %}

{% highlight js %}

   //Create an instance from an existing WaitingPopup.

   // only after control creation we can get waitingPopupObj otherwise it throws exception.

    var waitingPopupObj = $("#waitingPopUp").data("ejWaitingPopup");

    //Show WaitingPopup

        waitingPopupObj.show();

    //Hide WaitingPopup

        waitingPopupObj.hide();

{% endhighlight %}

Add the following styles to render **WaitingPopup** widget in the css file as mentioned in above samples.

{% highlight css %}

 #parent {
    height: 320px;
    width: 600px;
 }

{% endhighlight %}

The following screenshot illustrates a **WaitingPopup** when **show()** method is invoked.

![](Behavior-and-Settings_images/Behavior-and-Settings_img4.png)