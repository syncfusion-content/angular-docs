---
layout: post
title:  Tab
description: tab 
documentation: ug
platform: Angular
keywords: ribbon tab
---

# Tab

Tab is a collection of control [`groups`](http://help.syncfusion.com/api/angular/ejribbon#members:tabs-groups) which enables you to organize related commands into single view.  Tabs can be added to Ribbon using [`tabs`](http://help.syncfusion.com/api/angular/ejribbon#members:tabs) property. [`id`](http://help.syncfusion.com/api/angular/ejribbon#members:tabs-id) & [`text`](http://help.syncfusion.com/api/angular/ejribbon#members:tabs-text) properties are used to set unique ID and header text to Tab. The manipulation of given text tab in the ribbon control can be done by using  [`addTab`](https://help.syncfusion.com/api/angular/ejribbon#methods:addtab), [`removeTab`](https://help.syncfusion.com/api/angular/ejribbon#methods:removetab), [`hideTab`](https://help.syncfusion.com/api/angular/ejribbon#methods:hidetab),
[`showTab`](https://help.syncfusion.com/api/angular/ejribbon#methods:showtab) methods and [`tabAdd`](https://help.syncfusion.com/api/angular/ejribbon#events:tabadd), [`tabCreate`](https://help.syncfusion.com/api/angular/ejribbon#events:tabcreate), [`tabRemove`](https://help.syncfusion.com/api/angular/ejribbon#events:tabremove), [`tabClick`](https://help.syncfusion.com/api/angular/ejribbon#events:tabclick) and [`tabSelect`](https://help.syncfusion.com/api/angular/ejribbon#events:tabselect) events.

{% highlight html %}

   <ej-ribbon id="Default" width="500px" applicationTab.type="menu" applicationTab.menuItemID="ribbonmenu">
        <e-tabs>
            <e-tab id="home" text="HOME" [groups]="groups1">
            </e-tab>
            <e-tab id="sendrec" text="Send/Receive" [groups]="group2">
            </e-tab>
        </e-tabs>
   </ej-ribbon>

<ul id="ribbonmenu">
    <li>
        <a>FILE</a>
        <ul>
            <li><a>New</a></li>
            <li><a>Open</a></li>
            <li><a>Save</a></li>
            <li><a>Save as</a></li>
            <li><a>Print</a></li>
        </ul>
    </li>
</ul>
<div id="sendReceive">
     Send/Receive All Folders
</div>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {NorthwindService} from '../../services/northwind.service';

@Component({
  selector: 'ej-app',
  templateUrl: 'app/components/ribbon/ribbon.component.html',
  providers: [NorthwindService]
})
export class RibbonComponent {
    constructor(public northwindService: NorthwindService) {}

 groups1 = [{
        text: "Save",
        content: [{
            groups: [{
                text: "Save",
                isBig: true,
                buttonSettings: {
                    prefixIcon: "e-icon e-save",
                    contentType: "imageonly"
                }
            }]
        }]
     }, {
            text: "Print",
            content: [{
                groups: [{
                    text: "Print",
                    isBig: true,
                    type: "togglebutton",
                    toggleButtonSettings: {
                        contentType: "imageonly",
                        defaultText: "Print",
                        activeText: "Print",
                        defaultPrefixIcon: "e-icon e-print",
                        activePrefixIcon: "e-icon e-print",
                    }
                }]
            }]
        }];
   group2 = [{
        type: "custom",
        contentID: "sendReceive"
   }];
    
{% endhighlight %}

![](/Tab_images/Tab_img1.png)

