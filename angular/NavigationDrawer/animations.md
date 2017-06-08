---
layout: post
title: animations
description: animations
platform: Angular
control: Navigation Drawer
documentation: ug
---

# Animations

You can set the transition type of the Navigation Drawer by using type property. The possible transition types are slide and overlay.

* Slide - Both navigation panel and content page slides towards left/right direction to view the navigation panel items.
* Overlay - Only the navigation panel slides over the content page to view the navigation panel items. That is, part of the content page is hidden under navigation panel.


N> ![](animations_images\animations_img1.png)_ Transition slide type works only with fixed position._

The default value is Overlay.

In the HTML page set the type and position of Navigationdrawer.


{% highlight html %}

    <div ej-navigationdrawer id="navpane" targetId="drawerTarget" type="slide" direction="left" [enableListView]="enablelistview" position="fixed" [listViewSettings]="listviewsettings">
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
  
The following screenshot illustrates the output.

![](animations_images\animations_img2.png)

Before target click
{:.caption}

![](animations_images\animations_img3.png)

After target click
{:.caption}

