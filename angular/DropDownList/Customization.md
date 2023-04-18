---
layout: post
title: Customization in Angular DropDownList Control | Syncfusion
description: Learn here about Customization in Syncfusion Essential Angular DropDownList Control, its elements, and more.
platform: Angular
control: DropDownList
documentation: ug
---

# Customization in Angular DropDownList

## Adding watermark text

It provides the short description of the expected value in dropdown and will display the text until any item is selected. You can set this text using [watermarkText](http://help.syncfusion.com/api/js/ejdropdownlist#members:watermarktext) property.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [watermarkText]="watermark"/>
     
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: Array<Object>;
    fieldsvalues: Object;
    watermark: string;
    constructor() {
        this.data = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 5",
                value: "item5"
        }];
        this.fieldsvalues = { text: "text", value: "value" };
        this.watermark = "Select an Item";
    }
}

{% endhighlight %}

![Angular DropDownList customization](Customization_images/Customization_img1.png)

![Angular DropDownList watermark text](Customization_images/Customization_img2.png)

## Applying Rounded Corner

You can use [showRoundedCorner](http://help.syncfusion.com/api/js/ejdropdownlist#members:showroundedcorner) property to add rounded borders to the input and popup elements. By default, rounded corner property is disabled in DropDownList.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [showRoundedCorner]="true"/>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: Array<Object>;
    fieldsvalues: Object;
    constructor() {
        this.data = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 5",
                value: "item5"
        }];
        this.fieldsvalues = { text: "text", value: "value" };
    }
}

{% endhighlight %}

![Angular DropDownList applying rounded corner](Customization_images/Customization_img3.png)

I> The browser support details for rounded corner is given [here](http://www.w3schools.com/cssref/css3_pr_border-radius.asp).

## Enable/Disable the widget

The [enabled](http://help.syncfusion.com/api/js/ejdropdownlist#members:enabled) property is used to indicate whether the widget can respond to the user interaction or not. You can disable it by assigning false to this property. When the widget is disabled state, you cannot interact with the control.

N> you can also use [enable()](http://help.syncfusion.com/api/js/ejdropdownlist#methods:enable)  or [disable()](http://help.syncfusion.com/api/js/ejdropdownlist#methods:disable)  public methods.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [enabled]="false"/>
     
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: Array<Object>;
    fieldsvalues: Object;
    constructor() {
        this.data = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 5",
                value: "item5"
        }];
        this.fieldsvalues = { text: "text", value: "value" };
    }
}

{% endhighlight %}

![Angular DropDownList enable disable](Customization_images/Customization_img4.png)

N> you can disable/enable the single or multiple list items by using [disableItemsByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:disableitemsbyindices) and [enableItemsByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:enableitemsbyindices) property.


## Applying HTML Attributes

Additional HTML attributes can be applied to the widget by using [htmlAttributes](http://help.syncfusion.com/api/js/ejdropdownlist#members:htmlattributes) property. The valid attributes such as name, required, read-only and disabled are directly applied to the input element of DropDownList, and other attributes such as style, class will be applied to the outer wrapper element of DropDownList. Please refer to the [How-to](http://help.syncfusion.com/js/dropdownlist/howto#apply-html-attributes-such-as-color-and-class-directly-to-the-input-element-rather-than-the-outer-wrapper-element-of-dropdownlist) section.

N>when you add an item dynamically to the widget, you can specify the HTML attributes in the [addItem()](http://help.syncfusion.com/api/js/ejdropdownlist#methods:additem) method parameters.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [htmlAttributes]="htmlAttr"/>
     
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: Array<Object>;
    fieldsvalues: Object;
    constructor() {
        this.data = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 5",
                value: "item5"
        }];
        this.fieldsvalues = { text: "text", value: "value" };
        this.htmlAttr = { style: 'border:1px solid red' };
    }
}

{% endhighlight %}

![Angular DropDownList HTML Attributes](Customization_images/Customization_img5.png)