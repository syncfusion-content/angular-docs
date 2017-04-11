---
layout: post
title: customize-direction
description: customize-direction
platform: Angular-2
control: Navigation Drawer
documentation: ug
---

# Customize Direction

By using direction property, you can set the drawer to be open from right to left direction or left to right direction. The possible direction values are Right, Left and the default value is Left. Refer to the following code example.

{% highlight html %}

    <div ej-navigationdrawer id="navpane" targetId="drawerTarget" direction="right" [enableListView]="enablelistview" position="fixed" [listViewSettings]="listviewsettings">
        <ul>
            <li>Settings</li>
            <li>Read</li>
            <li>Help</li>
            <li>About</li>
        </ul>  
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

The following screenshot displays the output by swiping from right to left at the right side end of the screen.

![](customize-direction_images\customize-direction_img1.png) 





