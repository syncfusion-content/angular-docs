---
layout: post
title:  Syncfusion Splitter Nested Support
description: Nested Splitter Support
platform: Angular
control: Splitter
documentation: ug
---

# Nested Splitter Support

**Splitter** provides nested pane support that allows you to add a pane between two pane elements.

## Configure Nested Splitter

The following steps explain the implementation of the **“nested splitter”** option.

In the HTML page set the corresponding **&lt;div&gt;** elements for outer and inner Splitter component.

{% highlight html %}
    
    <ej-splitter id="outterSpliter" class="ang-splitter" height ="100%" width="485" [properties]="proper1"
            enableAutoResize="true" [orientation]="orientation">
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

Define properties of outerSplitter and innerSplitter in constructor file.

{% highlight javascript %}

    export class AppComponent {
        proper1:any;
        orientation:any;
        proper2:any;	 
        constructor() {
        this.proper1 = [{ paneSize: 60 }];
        this.orientation = ej.Orientation.Vertical;
        this.proper2 = [{ paneSize: 200 }, { paneSize: 170 }];
    }

{% endhighlight %}

The output for the above code as follows.

![Nested Splitter Support](Nested-Splitter-Support_images\Nested-Splitter-Support_img1.png) 