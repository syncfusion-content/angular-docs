---
layout: post
title: CheckBox with DropDownList widget 
description: Describes about Checkbox functionalities in DropDownList widget 
platform: Angular2
control: DropDownList
documentation: ug
---

# Checkbox

DropDownList displays checkboxes to the left of each item when you set [showCheckBox](http://help.syncfusion.com/api/js/ejdropdownlist#members:showcheckbox) property to true. It allows you to select more than one item at a time from DropDownList. Popup list stays open until the user finishes selection. When you click on an item’s text or checkbox then the checkbox checked status get change.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [showCheckbox]="true"/>
     
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

![](Checkbox_images/Checkbox_img1.png)

N> if you want to showcase the DropDownList with default checked items on data binding, specify selected field with Boolean values.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [showCheckbox]="true"/>
     
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
            { text: "ListItem 1", value: "item1", selected: true },
            { text: "ListItem 2", value: "item2", selected: false },
            { text: "ListItem 3", value: "item3", selected: true },
            { text: "ListItem 4", value: "item4", selected: false },
            { text: "ListItem 5", value: "item5", selected: false }
        ];
        this.fieldsvalues = { dataSource: this.data, text: "text", value: "value", selected:"selected" };
    }
}

{% endhighlight %}

![](Checkbox_images/Checkbox_img2.png)

## Selection Modes

The [multiSelectMode](http://help.syncfusion.com/api/js/ejdropdownlist#members:multiselectmode) property enables you to make multiple selections in the following two ways:

* Delimiter 
* Visual Mode

I> “multiSelectMode” property accepts both the **string** and **ej.MultiSelectMode** enum value.

### Delimiter

Each checked item’s text is appended to the textbox with delimiter “,” by default. This is enabled by assigning **“delimiter”** (string) or **ej.MultiSelectMode.Delimiter** (enum) value to multiSelectMode property. You can customize the delimiter option by using [delimiterChar](http://help.syncfusion.com/api/js/ejdropdownlist#members:delimiterchar) property.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [showCheckbox]="true" [(multiSelectMode)]="selectmode" [delimiterChar]="delimiter"/>
     
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
    delimiter: string;
    selectmode: any;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.fieldsvalues = { dataSource: this.data, text: "text", value: "value" };
        this.selectmode = ej.MultiSelectMode.Delimiter;
        this.delimiter = "-";
    }
}

{% endhighlight %}

![](Checkbox_images/Checkbox_img3.png)

### Visual Mode

When you enable this option in DropDownList widget, each checked item’s text is appended to the text box in a box model layout. This is enabled by assigning **“visualmode”** (string) or **ej.MultiSelectMode.VisualMode** (enum) value to multiSelectMode property.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [showCheckbox]="true" [(multiSelectMode)]="selectmode"/>
     
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
    selectmode: any;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.fieldsvalues = { dataSource: this.data, text: "text", value: "value" };
        this.selectmode = ej.MultiSelectMode.VisualMode;
    }
}

{% endhighlight %}

![](Checkbox_images/Checkbox_img4.png)

## Check/Uncheck All

You can check/uncheck all the list items at run time by using [checkAll](http://help.syncfusion.com/api/js/ejdropdownlist#methods:checkall) and [uncheckAll](http://help.syncfusion.com/api/js/ejdropdownlist#methods:uncheckall) method. By default no item will be in checked state. 

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [(value)]="value" [showCheckbox]="true"/>
<input type="checkbox" id="tbutton" ej-togglebutton (change)="onCheckUncheckAll($event)"/>
     
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
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" },

        ];
        this.fieldsvalues = { text: "text", value: "value" };
    }
    onCheckUncheckAll(event) {
        var dropdownObj = $('#dropdown1').data("ejDropDownList");
        if (event.target.checked) dropdownObj.checkAll();
        else dropdownObj.unCheckAll();
    }
}

{% endhighlight %}