---
layout: post
title:  Contextual-Tab-and-Tab-Set
description: contextual tab and tab set
documentation: ug
platform: Angular-2
keywords: contextual tab and tab set
---

# Contextual Tabs

[`Contextual Tabs`](http://help.syncfusion.com/api/js/ejribbon#members:contextualtabs) are collection of Tabs that extended styling and can be shown based on some criteria. Contextual Tabs can be added like [`tabs`](http://help.syncfusion.com/api/js/ejribbon#members:tabs) including groups and content section. You can set [`backgroundColor`](http://help.syncfusion.com/api/js/ejribbon#members:contextualtabs-backgroundcolor) and [`borderColor`](http://help.syncfusion.com/api/js/ejribbon#members:contextualtabs-bordercolor) to highlight them as Tab set

{% highlight html %}

<ej-ribbon id="Default" width="500px" applicationTab.type="menu" applicationTab.menuItemID="ribbonmenu" [contextualTabs]="contextualtab">
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
        </ul>
    </li>
</ul>
<div id="Contents">Custom Control</div>
<div id="headings" class="e-headings">
    <div>
        <p>AaBbCcDd</p>
        <p>No Spacing</p>
    </div>
    <div>
        <p class="e-strong">AaBbCcDd</p>
        <p>Strong</p>
    </div>
    <div>
        <p class="e-emphasis">AaBbCcDd</p>
        <p>Emphasis</p>
    </div>
</div>
<table id="design" class="e-designtablestyle">
    <tr>
        <td>
            <input type="checkbox" id="Check2" />
            <label for="Check2">First Column</label>
        </td>
        <td>
            <input type="checkbox" id="check4" checked="checked" />
            <label for="check4">Total Row</label>
        </td>
    </tr>
</table>
   
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
        text: "CustomControls",
        type: "custom",
        contentID: "Contents"
   }]
   contextualtab = [{
        backgroundColor: "#FCFBEB",
        borderColor: "#F2CC1C",
        tabs: [{
            id: "Design",
            text: "DESIGN",
            groups: [{
                text: "Table Style Options",
                type: "custom",
                contentID: "design"
            }]
        }]
    },
        {
            backgroundColor: "blue",
            borderColor: "lightblue",
            tabs: [{
                id: "tabset1",
                text: "Tabset1",
                groups: [{
                    text: "Tabset1 Style",
                    type: "custom",
                    contentID: "headings"
                }]
            }, {
                    id: "tabset2",
                    text: "Tabset2",
                    groups: [{
                        text: "TabSet2 Style",
                        content: [{
                            groups: [{
                                id: "uppercase",
                                text: "Upper Case",
                                buttonSettings: {
                                    contentType: ej.ContentType.ImageOnly,
                                    prefixIcon: "e-ribbon e-uppercase"
                                }
                            }, {
                                    id: "lowercase",
                                    text: "Lower Case",
                                    buttonSettings: {
                                        contentType: ej.ContentType.ImageOnly,
                                        prefixIcon: "e-ribbon e-lowercase"
                                    }
                                }],
                            defaults: {
                                isBig: true
                            }
                        }]
                    }]
                }]
        }]
}
  
{% endhighlight %}


![](Contextual-Tab-and-Tab-Set_images/Contextual-Tab-and-Tab-Set_img1.png)

