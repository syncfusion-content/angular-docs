---
layout: post
title: customize-position
description: customize position
platform: Angular-2
control: Navigation Drawer
documentation: ug
---

# Customize Position

The position property is used to specify the position whether it is in fixed or relative to the page. When you set a normal value to position property, it appears within the container. Otherwise, it appears in the whole body. The possible position values are fixed and normal. The Default value is normal.

In the HTML page set the position of Navigationdrawer.

{% highlight html %}

    <div ej-navigationdrawer id="navpane" targetId="drawerTarget" direction="left" [enableListView]="enablelistview" position="fixed" [listViewSettings]="listviewsettings">
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

The following screenshot illustrates the output by swiping from left to right at the left end of the screen.

![](customize-position_images\customize-position_img1.png)

