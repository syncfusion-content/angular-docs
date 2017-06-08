---
layout: post
title: Rendering Mode in DropDownList widget
description: Describes about rendering mode in DropDownList widget.
platform: Angular
control: DropDownList
documentation: ug
---

# Rendering Mode

DropDownList widget can be created in three ways.

*  Using an input element 
*  Using a select element 
*  Using UL-LI 

## Using an input element

Create an input element with the HTML "id" attribute set to it. To initialize the DropDownList, you should call the "ejDropDownList" jQuery plug-in function with the options as parameter

You can bind the local JSON array data source to the DropDownList using [dataSource](http://help.syncfusion.com/api/js/ejdropdownlist#members:datasource) and [fields](http://help.syncfusion.com/api/js/ejdropdownlist#members:fields) properties. Fields property is used to map with the corresponding columns.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues"/>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
	data: Array<Object> = [];
	fieldsvalues: Object;
	constructor() {
	this.data = [
		{text: "ListItem 1", value: "ListItem 1" },
		{text: "ListItem 2", value: "ListItem 2" },
		{text: "ListItem 3", value: "ListItem 3" },
		{text: "ListItem 4", value: "ListItem 4" },
		{text: "ListItem 5", value: "ListItem 5" }
		];
	this.fieldsvalues = { dataSource: this.data, text: "text", value: "value" };
	}
}

{% endhighlight %}

## Using Select Element

You can create a DropDownList using a select element. Refer to the below code.

{% highlight html %}

<select id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues"></select>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
	data: Array<Object> = [];
	fieldsvalues: Object;
	constructor() {
	this.data = [
		{text: "ListItem 1", value: "ListItem 1" },
		{text: "ListItem 2", value: "ListItem 2" },
		{text: "ListItem 3", value: "ListItem 3" },
		{text: "ListItem 4", value: "ListItem 4" },
		{text: "ListItem 5", value: "ListItem 5" }
		];
	this.fieldsvalues = { dataSource: this.data, text: "text", value: "value" };
	}
}

{% endhighlight %}

## Using UL-LI

You can bind the predefined set of UL-LI elements to generate the list of popup items. These items can be customized by adding any images, div elements, radio buttons, text boxes etc.

Create a div with UL-LI elements and assign that div id into [targetID](http://helpjs.syncfusion.com/api/js/ejdropdownlist#members:targetid ) property and initialize the widget.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [targetID]="list"/>
<div id="mailtoolslist">
	<ul>
		<li><div class="mailtools categorize"></div>Categorize and Move</li>
		<li><div class="mailtools done"></div>Done</li>
		<li><div class="mailtools flag"></div>Flag & Move</li>
		<li><div class="mailtools forward"></div>Forward</li>
		<li><div class="mailtools movetofolder"></div>Move to Folder</li>
		<li><div class="mailtools newmail"></div>New E-mail</li>
		<li><div class="mailtools meeting"></div>New Meeting</li>
		<li><div class="mailtools reply"></div>Reply & Delete</li>
	</ul>
</div>

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
	list: string;
    constructor() {
        this.list = "mailtoolslist";
    } 
}

{% endhighlight %}

Add the below css in dropdown.component.css file.

{% highlight css %}
    	 
    .mailtools {
        	display: block;
        	background-image: url('iconsapps.png');
            height: 25px;
            width: 25px;
            background-position: center center;
            background-repeat: no-repeat;
        }
		.mailtools.done {
			background-position: 0 0;
		}

		.mailtools.movetofolder {
			background-position: 0 -22px;
		}

		.mailtools.categorize {
			background-position: 0 -46px;
		}

		.mailtools.flag {
			background-position: 0 -70px;
		}

		.mailtools.forward {
			background-position: 0 -94px;
		}

		.mailtools.newmail {
			background-position: 0 -116px;
		}

		.mailtools.reply {
			background-position: 0 -140px;
		}

		.mailtools.meeting {
			background-position: 0 -164px;
		}

{% endhighlight %}

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\ng1 app\content\images<br/>
	
	
![](RenderingMode_images/RenderingMode_img1.png)