---
layout: post
title: Template support with DropDownList widget
description: Template Support with DropDownList widget
platform: Angular2
control: DropDownList
documentation: ug
---

# Template Support

By default you can add any text or image to the DropDownList list item. To customize the items layout or to create your own visualized elements you can use this template support.

## Header Template

You can create the popup header by using [headerTemplate](http://helpjs.syncfusion.com/api/js/ejdropdownlist#members:headertemplate) property. You can add any HTML content in header template.

N> Refer the check all option in popup list : [link](http://help.syncfusion.com/js/dropdownlist/howto#add-check-all-option-in-popup-list)

## Template Field

Create a set of div containers with common syntax or elements and assign it to the [template](http://helpjs.syncfusion.com/api/js/ejdropdownlist#members:template) property. You can add any HTML mark-up element inside the DropDownList list using this property.

In the demo, a JSON array is created with text, imgId, role and country which is initialized with dataSource property. Content template is created by using the corresponding fields and assigned in template property. The content template is customized with images and custom CSS styles to visualize the items in popup.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="empList" [width]="width" [headerTemplate]="headertemplate" [template]="template">
	 
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html',
styleUrls: ['app/components/dropdown/dropdown.component.css'],
encapsulation: ViewEncapsulation.None
})
export class DropDownListComponent {
   	empList: Array<Object>;
    headertemplate: string;
    template: string;
    width: any;
    constructor() {
        this.empList = [{
            text: "Erik Linden",
            imgId: "3",
            role: "Representative",
            country: "England"
             }, {
                text: "John Linden",
                imgId: "6",
                role: "Representative",
                country: "Norway"
            }, {
                text: "Louis",
                imgId: "7",
                role: "Representative",
                country: "Australia"
            }, {
                text: "Lawrence",
                imgId: "8",
                role: "Representative",
                country: "India"
        }];
        this.headertemplate = "<div class='eheader'><span>PHOTO</span> <span>DETAILS</span></div>";
        this.template = '<div><img class="imgId" src="Employee/${imgId}.png" alt="employee"/>' + '<div class="ename"> ${text} </div><div class="role"> ${role} </div><div class="cont"> ${country} </div></div>';
        this.width = "200";
    }
}

{% endhighlight %}

Add the below css in dropdown.component.css file.

{% highlight css %}
	
    .imgId {
        margin: 0;
        padding: 3px 10px 3px 3px;
        border: 0 none;
        width: 60px;
        height: 60px;
        float: left;
    }
    
    .eheader {
        font-weight: bold;
        border-bottom: 1px solid #c8c8c8;
        background: #c8c8c8;
    }
    
    .eheader > span {
        display: inline-block;
        padding: 10px;
    }
    
    .ename {
        font-weight: bold;
        padding: 6px 3px 1px 3px;
    }
    
    .role, .cont {
        font-size: smaller;
        padding: 3px 3px -1px 0px;
    }
		 
{% endhighlight %}

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\ng2 app\app\content\images<br/>

![](TemplateSupport_images/TemplateSupport_img1.png)