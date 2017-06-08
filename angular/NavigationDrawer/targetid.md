---
layout: post
title: targetid
description: targetid
platform: Angular-2
control: Navigation Drawer
documentation: ug
---

# TargetId

The targetId property is used to define the target Id for Navigation Drawer. The drawer opens while you click on the specified target element.

In the HTML page set the targetId of Navigationdrawer.

{% highlight html %}

    <div ej-navigationdrawer id="navpane" targetId="drawerTarget" direction="left" [enableListView]="enablelistview" position="fixed" [listViewSettings]="listviewsettings">
        <ul>
            <li>Settings</li>
            <li>Read</li>
            <li>Help</li>
            <li>About</li>
        </ul>   
    </div>
    <div>
        <input type="button" ej-button id="drawerTarget" text="Open Drawer" style="top:200px;left:400px;position:absolute" />
    </div>

{% endhighlight %}

{% highlight ts %}
 
    export class AppComponent {
        enablelistview: any;
        listviewsettings: any;
        constructor() {
            this.enablelistview = true;
            this.listviewsettings = { height: 500 };
        }
    }

{% endhighlight %}

The following screenshots illustrates the output.

![](targetid_images\targetid_img1.png)

Before target click
{:.caption}

![](targetid_images\targetid_img2.png)

After target click
{:.caption}

