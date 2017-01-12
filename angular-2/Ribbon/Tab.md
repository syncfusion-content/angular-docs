---
layout: post
title:  Tab
description: tab 
documentation: ug
platform: js
keywords: ribbon tab
---

# Tab

Tab is a collection of control [`groups`](http://help.syncfusion.com/api/js/ejribbon#members:tabs-groups) which enables you to organize related commands into single view.  Tabs can be added to Ribbon using [`tabs`](http://help.syncfusion.com/api/js/ejribbon#members:tabs) property. [`id`](http://help.syncfusion.com/api/js/ejribbon#members:tabs-id) & [`text`](http://help.syncfusion.com/api/js/ejribbon#members:tabs-text) properties are used to set unique ID and header text to Tab. 

{% highlight html %}

   <ej-ribbon id="Default" width="500px" applicationTab.type="menu" applicationTab.menuItemID="ribbonmenu">
        <e-tabs>
            <e-tab id="home" text="HOME" [groups]="groups1">
            </e-tab>
            <e-tab id="sendrec" text="Send/Receive" [groups]="sendreceive">
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
  selector: 'sd-home',
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
   sendreceive = [{
        type: "custom",
        contentID: "sendReceive"
   }];
    
{% endhighlight %}

![](/Tab_images/Tab_img1.png)

