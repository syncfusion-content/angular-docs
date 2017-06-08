---
layout: post
title:  Ribbon-Application-Tab
description: application tab
documentation: ug
platform: Angular
keywords: application tab, ribbon application tab
---

# Application Tab

The Application Tab is used to represent a `Menu` that do some operations, such as File menu to create, open, and print documents. Application Tab classified by [`applicationTab.type`](http://help.syncfusion.com/api/js/ejribbon#members:applicationtab-type) property with the following:

*  menu
*  backstage

## Application Menu

The Application Menu is similar to traditional file menu options and Syncfusion `ejMenu` control is used internally to render this. To show Application Menu in Ribbon, set the [`applicationTab.type`](http://help.syncfusion.com/api/js/ejribbon#members:applicationtab-type) as `menu` and [`applicationTab.menuSettings`](http://help.syncfusion.com/api/js/ejmenu) to customize properties of `ejMenu`.

### _Create Using Template_

Set the UL element `id` to [`applicationTab.menuItemID`](http://help.syncfusion.com/api/js/ejribbon#members:applicationtab-menuitemid) property to create Application Menu and it will acts as template to render menu.

{% highlight html %}
    
     <ej-ribbon id="Default" width="500px" applicationTab.type="menu" applicationTab.menuItemID="ribbonmenu" applicationTab.menuSettings.openOnClick="false">
        <e-tabs>
            <e-tab id="home" text="HOME" [groups]="groups1">
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
     <div id="Contents">Custom control</div>
  
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
        text: 'New', type: 'custom', contentID: "Contents"
   }];
}

{% endhighlight %}

![](Application-Tab_images/Application-Tab_img1.png)
