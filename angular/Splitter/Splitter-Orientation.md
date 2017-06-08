---
layout: post
title:  Splitter Orientation
description: Splitter Orientation
platform: Angular
control: Splitter
documentation: ug
---

# Splitter Orientation

 **Splitter** supports both vertical and horizontal orientation of the pane. You can define **orientation** with enum values **“ej.Orientation.Vertical“** or **“ej.Orientation.Horizontal”**. Or else set value of orientation as string.

## Configure Splitter Orientation

The following steps explain the implementation of Splitter orientation option.

In the **HTML** page set the **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <ej-splitter id="outterSpliter" class="ang-splitter" height ="100%" width="485" [properties]="proper" enableAutoResize="true" [orientation]="orientation">					                
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

Define the splitter orientation as **“ej.Orientation.Vertical”** in constructor file.

{% highlight javascript %}

    export class AppComponent {
     proper:any;
     orientation:any;	 
	 constructor() {
	  this.orientation = ej.Orientation.Vertical;
    }

{% endhighlight %}


The output of Splitter with **ej.Orientation.Vertical** orientation as follows,

![](Splitter-Orientation_images\Splitter-Orientation_img1.png) 

The output of Splitter with **ej.Orientation.Horizontal** orientation as follows,

![](Splitter-Orientation_images\Splitter-Orientation_img2.png) 

