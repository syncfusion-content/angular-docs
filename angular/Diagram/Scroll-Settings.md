---
layout: post
title: Read the current scroll status and programmatically pan Diagrams
description: How to read/modify the scroll status of the Diagram?
platform: Angular
control: Diagram
documentation: ug
---

# Scroll Settings
The Diagram can be scrolled by using the vertical and horizontal scrollbars. In addition to the scrollbars, you can use mouse wheel to scroll the Diagram. 
Diagram's `scrollSettings` enables you to read the current scroll status, view port size, current zoom, and zoom factor. It also allows you to scroll the Diagram programmatically. 

## Get current scroll status

Scroll settings allows you to read the scroll status, view port size, and current zoom factor with a set of properties. To explore those properties, see [Scroll Settings](/api/js/ejDiagram#members:scrollsettings "Scroll Settings")

## Define scroll status
Diagram allows you to pan the Diagram before loading, so that any desired region of a large Diagram is made to view. You can programmatically pan the Diagram with the `horizontalOffset` and `verticalOffset` properties of scroll settings. The following code illustrates how to set pan the Diagram programmatically.

{% highlight html %}

<div>
   <ej-diagram id="diagram" width="100%" height="600" [pageSettings]="pageSettings" [scrollSettings] ="scrollSettings">
</div>

{% endhighlight %}

{% highlight javascript %}

import { Component, ViewChild} from '@angular/core';
import { EJComponents } from './../../ej/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/components/diagram/scrollsettings.component.html',
})
export class scrollSettingsComponent {
    @ViewChild('diagram') diagram: EJComponents<any, any>;
    pageSettings: Object;
    scrollSettings: Object;
    constructor() {
        this.pageSettings = {
            pageHeight: 500,
            pageWidth: 500
        };
        this.scrollSettings = {
                horizontalOffset: 100,
                verticalOffset: 50,
                zoomFactor: 0.2
            };
    }
}

{% endhighlight %}

In the example given below, the vertical scroll bar is scrolled down by 50px and horizontal scroll bar is scrolled to right by 100px. 

![define scroll status in Diagram.](/angular/Diagram/Scroll-Settings_images/Scroll-Settings_img1.png)

## AutoScroll 

Autoscroll feature automatically scrolls the Diagram whenever the node or connector is moved beyond the boundary of the Diagram. So that, it is always visible during dragging, resizing, and multiple selection operations. Autoscroll is automatically triggered when any one of the following is done towards the edges of the Diagram.

* Node dragging, resizing 
* Connection editing
* Rubber band selection
* Label dragging

## Autoscroll border

The Autoscroll border is used to specify the maximum distance between the object and Diagram edge to trigger Autoscroll. The default value is set as 15 for all sides (left, right, top, and bottom) and it can be changed by using the `autoScrollBorder` property of page settings. The following code example illustrates how to set Autoscroll border. 

{% highlight html %}

<div>
   <ej-diagram id="diagram" width="100%" height="600" [pageSettings]="pageSettings">
</div>
{% endhighlight %}

{% highlight javascript %}

export class scrollSettingsComponent {
    @ViewChild('diagram') diagram: EJComponents<any, any>;
    pageSettings: Object;
    constructor() {
        this.pageSettings = {
        autoScrollBorder: {
            left: 150,
            top: 15,
            right: 15,
            bottom: 15
            }
        };
    }
}

{% endhighlight %}

## Scroll limit

The scroll limit allows you to define the scrollable region of the Diagram. It includes the following options.

* Allows to scroll in all directions without any restriction.
* Allows to scroll within the Diagram content.
* Allows to scroll within the specified scrollable area.

`scrollLimit` property of scroll settings helps to limit the scrolling. For the accepted values of the scrollLimit, refer to [Scroll Limit](/api/js/ejDiagram#scroll-limit "Scroll Limit").

The following code example illustrates how to specify the scroll limit.

{% highlight javascript %}

export class scrollSettingsComponent {
    @ViewChild('diagram') diagram: EJComponents<any, any>;
    pageSettings: Object;
    constructor() {
        this.pageSettings = {
        scrollLimit: "diagram"
        };
    }
}

{% endhighlight %}

## Scrollable Area

You can restrict scrolling beyond any particular rectangular area by using the `scrollableArea` property of scroll settings. To restrict scrolling beyond any custom region, you have to set the `scrollLimit` as "limited". The following code example illustrates how to customize scrollable area.

{% highlight html %}

<div>
    <ej-diagram #diagram width="100%" height="600" [pageSettings]="pageSettings">
</div>

{% endhighlight %}

{% highlight javascript %}

export class PageSettingsComponent {
    @ViewChild('diagram') diagram: EJComponents<any, any>;
    pageSettings: Object;
    constructor() {
        this.pageSettings = {
            //Sets scroll limit as limited
            scrollLimit: "limited",
            //Sets the limited scrollable area
            scrollableArea: {
                x: 0,
                y: 0,
                width: 100,
                height: 100
            },
            autoScrollBorder: {
                left: 150,
                top: 15,
                right: 15,
                bottom: 15
            }
        }
    }
}
{% endhighlight %}
