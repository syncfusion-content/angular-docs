---
layout: post
title:  Quick Access Toolbar
description: quick access toolbar
documentation: ug
platform: angular
keywords: quick access toolbar,ribbon quick access toolbar
api: /api/js/ejribbon
---

# Quick Access Toolbar

Quick Access Toolbar provides the shortcuts to the most commonly used commands by placing the controls at the Quick Access Toolbar section. It can be placed at the top or bottom of the Ribbon.

Set [`showQAT`](https://help.syncfusion.com/api/angular/ejribbon#members:showqat) as true to enable Quick Access Toolbar in Ribbon. It supports the Button, Split Button, Toggle Button controls. The [`quickAccessMode`](https://help.syncfusion.com/api/angular/ejribbon#members:tabs-groups-content-groups-quickaccessmode) is used to change the controls state in Quick Access Toolbar through options as `toolbar`,`menu` and `none`. Default value is `none` and QAT toolbar is created with specified controls added in Toolbar.

The `toolbar` option used to set controls visibility in Quick Access Toolbar.The `menu` option shows the controls in Quick Access Menu and does not show controls in Quick Access Toolbar.

Once the controls are visible in Toolbar , then controls state will be set as ticked in Quick Access Menu and vice versa.  

The client side event for Quick Access Toolbar menu click is [`qatMenuItemClick`](https://help.syncfusion.com/api/angular/ejribbon#events:qatmenuitemclick) and it will be triggered with QAT menu item click.

`More Commands` command provides with Quick Access Menu. This can be customized using [`qatMenuItemClick`](https://help.syncfusion.com/api/angular/ejribbon#events:qatmenuitemclick) event, such as to show popup dialog. 

{% highlight html %}

<ej-ribbon id="Default" width="500px" [showQAT]="showQAT" applicationTab.type="menu" applicationTab.menuItemID="ribbon">
   <e-tabs>
        <e-tab id="home" text="HOME" [groups]="groups1">
        </e-tab>
   </e-tabs>
</ej-ribbon>
<ul id="ribbon">
			<li>
				<a>FILE</a>
				<ul>
					<li><a>New</a></li>
				</ul>
			</li>
		</ul>
		<ul id="split">
			<li><span>Paste</span></li>
		</ul>

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
	public showQAT:boolean = true;
	public groups1:any = [{
                       text: "SplitButton",
							alignType: ej.Ribbon.alignType.columns,
							content: [{
								groups: [{
									id: "paste",
									text: "paste",
									toolTip: "Paste",
									type: ej.Ribbon.type.splitButton,
									quickAccessMode: ej.Ribbon.quickAccessMode.toolBar,
									splitButtonSettings: {
										contentType: ej.ContentType.ImageOnly,
										targetID: "split",
										prefixIcon: "e-icon e-ribbon e-ribbonpaste",
										buttonMode: "dropdown",
										arrowPosition: "bottom"
									}
								}],
								defaults: {
									type: ej.Ribbon.type.splitButton,
									width: 50,
									height: 70
								}
							}]
						}, {
							text: "Button",
							alignType: ej.Ribbon.alignType.rows,
							content: [{
								groups: [{
									id: "italic",
									text: "Italic",
									toolTip: "Italic",
									type: ej.Ribbon.type.button,
									quickAccessMode: ej.Ribbon.quickAccessMode.toolBar,
									toggleButtonSettings: {
										contentType: ej.ContentType.ImageOnly,
										defaultText: "Italic",
										activeText: "Italic",
										prefixIcon: "e-icon e-ribbon e-ribbonitalic"
									}
								}]
							}]
						}, {
							text: "Toggle",
							alignType: ej.Ribbon.alignType.columns,
							content: [{
								groups: [{
									id: "bold",
									toolTip: "Bold",
									type: ej.Ribbon.type.toggleButton,
									quickAccessMode: ej.Ribbon.quickAccessMode.toolBar,
									toggleButtonSettings: {
										contentType: ej.ContentType.ImageOnly,
										defaultText: "Bold",
										activeText: "Bold",
										defaultPrefixIcon: "e-icon e-ribbon bold",
										activePrefixIcon: "e-icon e-ribbon bold"
									}
								}],
	
							}]
   }]
  }    
{% endhighlight %}

{% highlight html %}
    <style type="text/css">
        .e-ribbon .e-rbnquickaccessbar .e-ribbonpaste:before {
				font-size: 27px;
				left: -5px;
				top: -6px;
			}
			.e-ribbon .e-ribbonpaste:before {
				font-family: 'ej-ribbonfont';
				content: "\e169";
				font-size: 36px;
				position: relative;
				left: -9px;
				top: -4px;
			}
			.e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
				font-family: 'ej-ribbonfont';
				font-size: 16px;
				left: -1px;
				position: relative;
				top: -1px;
			}
			.e-ribbon .e-ribbonitalic:before ,.e-ribbon .bold:before{
				content: "\e163";
			}
			.e-ribbon .bold:before {
				content: "\e15a";
			}
			.e-ribbon .e-rbnquickaccessbar .e-undo::before {
				font-size: 18px;
				line-height: 12px;
				text-indent: -3px;
			}    
    </style>

{% endhighlight %}

![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img1.png)
