---
layout: post
title:  onDemand
description: onDemand
documentation: ug
platform: angular
keywords: onDemand
api: /api/angular/ejribbon
---

# Load on Demand

Set [`enableOnDemand`](https://help.syncfusion.com/api/angular/ejribbon#members:enableondemand) as true to enable load tab and backstage contents dynamically. Loading content on demand improves the initial rendering time of the ribbon by rendering tab and backstage content when tabs and backstage items are clicked.

{% highlight html %}

<ej-ribbon id="Default" width="500px" [enableOnDemand]="enableOnDemand" [applicationTab] ="applicationTab">
   <e-tabs>
        <e-tab id="home" text="HOME" [groups]="groups1">
        </e-tab>
        <e-tab id="layout" text="LAYOUT" [groups]="groups2">
        </e-tab>
   </e-tabs>
</ej-ribbon>
<div id="newCon">
            <table>
                        <tr>
                            <td>
                            <input type="button" class="e-bsnewbtnstyle" ej-button id="btn1" [prefixIcon]='prefixIcon' [imagePosition]='imagePosition' [contentType]='contentType' [width]='width' [height]='height' value="Blank WorkBook" [size]="size"/>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="accountCon">
                    <div class="e-userDiv">
                        <span>User Information</span>
                        <div>
                            <div class="e-accuser e-newpageicon"></div>
                            <div class="e-userCon">
                                <div>user</div>
                                <div>any@syncfusion.com</div>
                            </div>
                        </div>
                    </div>
                    <a href="#">Sign out</a>
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
	public enableOnDemand:boolean = true;
    public size: string = "large";
    public height: number = 200;
    public width:number= 225;
    public contentType:string ="textandimage";
    public imagePosition:string = "imagetop";
    public prefixIcon:string = "e-icon e-blank e-infopageicon";
    public applicationTab:any = { 
                    type: ej.Ribbon.ApplicationTabType.Backstage,
                    backstageSettings: {
                        text: "FILE",
                        height: 360,
                        width: 600,
                        headerWidth: 125,
                        pages: [{ id: "new", text: "New", contentID: "newCon" },
                                { id: "close", text: "Close", enableSeparator: true, itemType: ej.Ribbon.itemType.button },
                                { id: "account", text: "Office Account", contentID: "accountCon"}]
                    }}
	public groups1:any = [{
                       text: "Clipboard",
                       alignType: ej.Ribbon.AlignType.Columns, 
                       groupExpanderSettings: {
                            toolTip: "Clipboard"
                        }, content: [{
                            groups: [{
                                id: "paste",
                                text: "paste",
                                toolTip: "Paste",
                                buttonSettings: {
                                    contentType: ej.ContentType.ImageOnly,
                                    prefixIcon: "e-icon e-ribbon e-ribbonpaste"
                                }
                            }
                            ],
                            defaults: {
                                type: ej.Ribbon.Type.Button,
                                isBig: true,
                                width: 50,
                                height: 70
                            }
                        }]
                    },
                  	{
					    text: "New", alignType: ej.Ribbon.AlignType.Rows, content: [{
					        groups: [{
					            id: "new",
					            text: "New",
					            toolTip: "New",
					            buttonSettings: {
					                contentType: ej.ContentType.ImageOnly,
					                imagePosition: ej.ImagePosition.ImageTop,
					                prefixIcon: "e-icon e-ribbon e-new"
					            }
					        }
					        ],
					        defaults: {
					            type: ej.Ribbon.Type.Button,
					            width: 60,
					            height: 70
					        }
					    }]
					}]
    public groups2:any = [{
        text: "Alignment", 
        alignType: ej.Ribbon.AlignType.Rows, 
        content: [
						{
						    groups: [{
						        id: "bullet",
						        text: "Bullet Format",
						        toolTip: "Bullets",
						        buttonSettings: {
						            contentType: ej.ContentType.ImageOnly,
						            prefixIcon: "e-icon e-ribbon e-bullet"
						        }
						    },
                             {
                                 id: "number",
                                 text: "Number Format",
                                 toolTip: "Numbering",
                                 buttonSettings: {
                                     contentType: ej.ContentType.ImageOnly,
                                     prefixIcon: "e-icon e-ribbon e-numbericon"
                                 }
                             }],
						    defaults: {
						        type: ej.Ribbon.Type.Button,
						        isBig: false
						    }
						}]
				    }] 
  }    
{% endhighlight %}

{% highlight html %}
    <style type="text/css">
         .e-accuser {
           background-image: url("../content/ejthemes/common-images/ribbon/User.jpg"),url("content/ejthemes/common-images/ribbon/User.jpg");
        }
        .e-blank {
           background-image: url("../content/ejthemes/common-images/ribbon/blank.png"),url("content/ejthemes/common-images/ribbon/blank.png");
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>

{% endhighlight %}

![](On_Demand_images/onDemand_img1.png)

# Initially Collapsible

Set [`collapsible'](https://help.syncfusion.com/api/angular/ejribbon#members:collapsible) as true to render ribbon control in collapsed state, which results ribbon tabs to render without any content initially.
While using initially collapsible ribbon with [`enableOnDemand`](https://help.syncfusion.com/api/angular/ejribbon#members:enableondemand) feature improves the performance by reducing initial loading time of ribbon.

{% highlight html %}

<ej-ribbon id="Default" width="500px" [enableOnDemand]="enableOnDemand" [applicationTab] ="applicationTab">
   <e-tabs>
        <e-tab id="home" text="HOME" [groups]="groups1">
        </e-tab>
        <e-tab id="new" text="NEW" [groups]="groups2">
        </e-tab>
        <e-tab id="layout" text="LAYOUT" [groups]="groups3">
        </e-tab>
   </e-tabs>
</ej-ribbon>
<div id="newCon">
                    <table>
                        <tr>
                            <td>
                                <input type="button" class="e-bsnewbtnstyle" ej-button id="btn1" [prefixIcon]='prefixIcon' [imagePosition]='imagePosition' [contentType]='contentType' [width]='width' [height]='height' value="Blank WorkBook" [size]="size"/>
                            </td>
                        </tr>
                    </table>
                </div>
                <div id="accountCon">
                    <div class="e-userDiv">
                        <span>User Information</span>
                        <div>
                            <div class="e-accuser e-newpageicon"></div>
                            <div class="e-userCon">
                                <div>user</div>
                                <div>any@syncfusion.com</div>
                            </div>
                        </div>
                    </div>
                    <a href="#">Sign out</a>
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
	public enableOnDemand:boolean = true;
    public size: string = "large";
    public height: number = 200;
    public width:number= 225;
    public collapsible:boolean= true;
    public contentType:string ="textandimage";
    public imagePosition:string = "imagetop";
    public prefixIcon:string = "e-icon e-blank e-infopageicon";
    public applicationTab:any = { 
                    type: ej.Ribbon.ApplicationTabType.Backstage,
                    backstageSettings: {
                        text: "FILE",
                        height: 360,
                        width: 600,
                        headerWidth: 125,
                        pages: [{ id: "new", text: "New", contentID: "newCon" },
                                { id: "close", text: "Close", enableSeparator: true, itemType: ej.Ribbon.itemType.button },
                                { id: "account", text: "Office Account", contentID: "accountCon"}]
                    }}
	public groups1:any = [{
                      text: "Clipboard", alignType: ej.Ribbon.AlignType.Columns, groupExpanderSettings: {
                            toolTip: "Clipboard"
                        }, content: [{
                            groups: [{
                                id: "paste",
                                text: "paste",
                                toolTip: "Paste",
                                buttonSettings: {
                                    contentType: ej.ContentType.ImageOnly,
                                    prefixIcon: "e-icon e-ribbon e-ribbonpaste"
                                }
                            }
                            ],
                            defaults: {
                                type: ej.Ribbon.Type.Button,
                                isBig: true,
                                width: 50,
                                height: 70
                            }
                        }]
					}]
    public groups2:any = [{
       text: "New", alignType: ej.Ribbon.AlignType.Rows, content: [{
					        groups: [{
					            id: "new",
					            text: "New",
					            toolTip: "New",
					            buttonSettings: {
					                contentType: ej.ContentType.ImageOnly,
					                imagePosition: ej.ImagePosition.ImageTop,
					                prefixIcon: "e-icon e-ribbon e-new"
					            }
					        }
					        ],
					        defaults: {
					            type: ej.Ribbon.Type.Button,
					            width: 60,
					            height: 70
					        }
					    }]
				    }]
    public groups3:any = [{
            id: "layout", text: "LAYOUT", groups: [{
				        text: "Alignment", alignType: ej.Ribbon.AlignType.Rows, content: [
						{
						    groups: [{
						        id: "bullet",
						        text: "Bullet Format",
						        toolTip: "Bullets",
						        buttonSettings: {
						            contentType: ej.ContentType.ImageOnly,
						            prefixIcon: "e-icon e-ribbon e-bullet"
						        }
						    },
                             {
                                 id: "number",
                                 text: "Number Format",
                                 toolTip: "Numbering",
                                 buttonSettings: {
                                     contentType: ej.ContentType.ImageOnly,
                                     prefixIcon: "e-icon e-ribbon e-numbericon"
                                 }
                             }],
						    defaults: {
						        type: ej.Ribbon.Type.Button,
						        isBig: false
						    }
						}]
				    }]
    }] 
  }    
{% endhighlight %}

{% highlight html %}
    <style type="text/css">
         .e-accuser {
           background-image: url("../content/ejthemes/common-images/ribbon/User.jpg"),url("content/ejthemes/common-images/ribbon/User.jpg");
        }
        .e-blank {
           background-image: url("../content/ejthemes/common-images/ribbon/blank.png"),url("content/ejthemes/common-images/ribbon/blank.png");
        }
        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }
        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }
        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }
        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>

{% endhighlight %}


![](On_Demand_images/onDemand_img2.png)