---
layout: post
title: Data-binding
description: data binding
platform: Angular
control: Toolbar
documentation: ug
---

# Data binding

**Toolbar** provides you a flexible approach for binding data from various data sources. There are various properties in **Toolbar** for Data Binding.

## Data fields and configuration 

The following sub-properties provides a way to bind either the local/remote data to the **Toolbar** control.

Property Table of JavaScript Toolbar control

<table>
<tr>
<th>
Property</th><th>
Syntax</th><th>
Description</b></th></tr>
<tr>
<td>
dataSource</td><td>
dataSource: window.countriesField</td><td>
It specifies the data source of the Toolbar. The data source contains the list of data for generating the Toolbar items. By default, its value is null and its data type is object. </td></tr>
<tr>
<td>
field</td><td>
fields: {text: "name", value: "key" }</td><td>
It specifies the mapping fields for the data items of the Toolbar. By default, its value is null and its data type is object.</td></tr>
<tr>
<td>
query</td><td>
query: ej.Query().from("Suppliers").select("ContactName");       	 </td><td>
It specifies the query to retrieve the data from online server. By default, its value is null and its data type is object. </td></tr>
<tr>
<td>
id</td><td>
id</td><td>
It specifies the id of the tag and its default value is null and data type is string. </td></tr>
<tr>
<td>
text</td><td>
text</td><td>
It specifies the text content of the tag and its default value is null and data type is string. </td></tr>
<tr>
<td>
imageUrl</td><td>
imageUrl</td><td>
This property defines the imageURL for the image location. While setting images, the folder name in which the images are stored should be set to imageUrl property. The value set to this property should be <b>string</b> type.</td></tr>
<tr>
<td>
imageAttributes</td><td>
imageAttributes</td><td>
This property defines style for the image. While setting an image, styles can be applied such as height, width by using this property. The value set to this property should be <b>string</b> type.</td></tr>
<tr>
<td>
spriteCssClass</td><td>
spriteCssClass</td><td>
This property sets the Sprite CSS for the image tag in Toolbar. The value set to this property should be <b>string</b> type.</td></tr>
<tr>
<td>
htmlAttributes</td><td>
htmlAttributes</td><td>
This property sets the <b>HTML</b> attribute for the Toolbar item. The value set to this property should be <b>object</b> type. It can be any <b>HTML</b> attribute such as id, class, style.</td></tr>
<tr>
<td>
tooltipText  </td><td>
tooltipText  </td><td>
This property sets the text value for Toolbar item while mouse over in Toolbar. The value set to this property should be <b>string</b> type.</td></tr>
</table>

The following code example depicts you the way to bind data to the **Toolbar** widget.

{% highlight html %}
    
<ej-toolbar id="toolbar" [dataSource]="data" [fields]="fieldsvalues" [width]="250"></ej-toolbar>

{% endhighlight %}

{% highlight html %}

    import {Component,ViewEncapsulation} from '@angular/core';
    import {encapsulation} from '@angular/core'; 
    @Component({
    selector: 'sd-home',
    templateUrl: 'app/components/toolbar/toolbar.component.html',
    styleUrls: ['app/components/toolbar/toolbar.component.css'],
    encapsulation: ViewEncapsulation.None
    })
    export class ToolBarComponent {
    fieldsvalues: Object;
    data: Array<Object>;
    constructor() {
        this.data = [
        {
        iconid: "1",
        spriteCss: "mailtools movetofolder",

        }, {
        iconid: "2",
        spriteCss: "mailtools categorize",

        }, {
        iconid: "3",
        spriteCss: "mailtools flag",

        }, {
        iconid: "4",
        spriteCss: "mailtools forward",

        }, {
        iconid: "5",
        spriteCss: "mailtools newmail",

        },
        {
        iconid: "6",
        spriteCss: "mailtools reply",

        },
        {
        iconid: "7",
        spriteCss: "mailtools done",

        }
        ];
        this.fieldsvalues = { id: "iconid", spriteCssClass: "spriteCss" };
    }
    }

{% endhighlight %}

Add the below css in toolbar.component.css file.

{% highlight css %}

    .e-tooltxt .mailtools {
        background-image: url('../../content/images/maild.png');
    }
    .e-tooltxt .mailtools {
        display: block;
        background-image: url('../../content/images/maill.png');
        height: 24px;
        width: 24px;
        background-repeat: no-repeat;
    }
    .e-tooltxt:hover .mailtools, .darktheme .cols-sample-area .e-tooltxt:hover .mailtools {
        background-image: url('../../content/images/mailh.png');
    }
    .mailtools.done {
        background-position: -11px -140px;
    }
    .mailtools.movetofolder {
        background-position: -12px -40px;
    }
    .mailtools.categorize {
        background-position: -14px -248px;
    }
    .mailtools.flag {
        background-position: -13px -282px;
    }
    .mailtools.forward {
        background-position: -14px -314px;
    }
    .mailtools.newmail {
        background-position: -14px -348px;
    }
    .mailtools.reply {
        background-position: -14px -388px;
    } 
    .frame {
        height: 280px;
        width: 695px;
        border-radius: none;
        margin-left: 0;
        margin-top: 40px;
        padding: 0;
    }
    .control {
        margin: 120px 200px 0;
    }

{% endhighlight %}

![](Data-binding_images/Data-binding_img1.png)