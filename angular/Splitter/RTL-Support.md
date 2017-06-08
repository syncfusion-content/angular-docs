---
layout: post
title: RTL Support
description: RTL Support
platform: Angular
control: Splitter
documentation: ug
---

# RTL Support

**Splitter** provides you with **RTL (Right-To-Left)** support. The alignment of Splitter can be changed from Left-To-Right to Right-To-Left.

## Enable RTL

The following steps explain enabling the right-to-left property for Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner Splitter component.


{% highlight html %}

        
    <ej-splitter id="outterSpliter" class="ang-splitter" height ="100%" width="485" [properties]="proper1"
            enableAutoResize="true" [orientation]="orientation" [enableRTL]="enablertl">
    <div>
    <div style="padding: 0px 15px;">
        <h3 class="h3"> JavaScript </h3>
    </div>
    </div>	
    <div>		  
        <ej-splitter id="innersplitter" [properties]="proper2" width="600">
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Tools </h3>
            Essential Tools is an collection of user interface components used to create interactive
            JavaScript applications.
        </div>
    </div>
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Chart </h3>
            Essential Chart is a business-oriented charting component.
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

Define **“enableRTL”** property as true in constructor file.

{% highlight javascript %}

       
    export class AppComponent {
        proper1:any;
        orientation:any;
        proper2:any;
        enablertl:any;	 
        constructor() {
        this.proper1 = [{ paneSize: 60 }];
        this.orientation = ej.Orientation.Vertical;
        this.proper2 = [{ paneSize: 200 }, { paneSize: 170 }];
        this.enablertl=true;
    }

{% endhighlight %}

The output for Splitter when **enableRTL** is “true”.

![](RTL-Support_images\RTL-Support_img1.png) 

