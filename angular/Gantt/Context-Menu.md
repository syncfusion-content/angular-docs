---
layout: post
title: Context-Menu
description: context menu
platform: Angular
control: Gantt
documentation: ug
api: /api/js/ejgantt
---
# Context Menu

## Default Menu Items

Context menu in Gantt has the following default menu items,

* Task Details
* Add New Task
* Indent
* Outdent
* Delete

The following code example explains how to enable the context menu in Gantt control.

{% highlight javascript %}

<ej-gantt id="GanttControl" [enableContextMenu]="true">
</ej-gantt>

{% endhighlight %}

The following screenshot shows the default context menu in Gantt control.

![](Context-Menu_images/Context-Menu_img1.png)

## Custom Menu Item

It is possible to add a custom context menu item in Gantt control. The following code example explains on how to add the custom context menu item

{% highlight javascript %}

<ej-gantt id="GanttControl" (contextMenuOpen)="onganttcontextMenuOpen($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    constructor() {

    }
    onganttcontextMenuOpen(sender) {
        sender.contextMenuItems.push({
            headerText: "Expand/Collapse",
            menuId: "expand",
            iconPath: "url(Expand-02-WF.png)",
            eventHandler: function() {
                //event handler for custom menu items
            }
        });
    }
}

{% endhighlight %}

The screenshot of the custom context menu items in Gantt control is as follows.

![](Context-Menu_images/Context-Menu_img2.png)

### Custom menu item with sub menu item

It is possible to create a custom menu item with a sub menu by mapping the parentMenuId property from the contextMenuItems argument in the contextMenuOpen event.

The following code example explains on how to add sub context menu for custom menu items.

{% highlight javascript %}

<ej-gantt id="GanttControl" (contextMenuOpen)="onganttcontextMenuOpen($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    constructor() {
      //...

    }
    onganttcontextMenuOpen(sender) {
        {
            sender.contextMenuItems.push({
                headerText: "Expand/Collapse",
                menuId: "expand",
                iconPath: "url(Navigation-Up-02-WF.png)",
                eventHandler: function() {
                    //event handler for custom menu items
                }
            });
            sender.contextMenuItems.push({
                headerText: "ExpandAll",
                menuId: "expandall",
                parentMenuId: "expand",
                iconPath: "url(Expand-02-WF.png)",
                eventHandler: function() {
                    //event handler for custom menu items
                }
            });
            sender.contextMenuItems.push({
                headerText: "CollapseAll",
                menuId: "collapseall",
                parentMenuId: "expand",
                iconPath: "url(shrink2.png)",
                eventHandler: function() {
                    //event handler for custom menu items
                }
            });
        }
    }

{% endhighlight %}

The screenshot of the custom context menu items in Gantt control is as follows.

![](Context-Menu_images/Context-Menu_img3.png)

[Click](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/contextmenu/customcontextmenu) here to view the online demo sample for custom context menu in Gantt.
