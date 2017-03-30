---
layout: post
title: Data-Binding
description: data-binding
platform: Angular2
control: TagCloud
documentation: ug
---

# Data-Binding

To render the **TagCloud** widget, it is necessary to bind the data to it in a proper way. The following sub-properties provides you a way to bind local or remote data to the **TagCloud** widget by binding the appropriate data fields to the corresponding options.

## Fields 

### dataSource 

This property assigns the local **JSON** data or remote (URL binding) data to the **TagCloud** control.

### query 

It accepts the data of object type that is usually the query string to fetch the required data from a specific table based on certain conditions. As this property is optional, when it is not specified, then the entire records that are initially assigned through dataSource is taken into consideration.

### text

It maps the corresponding text field name from the data table or **JSON** data that is assigned to the dataSource with the text property of the **TagCloud** control. The text value that is fetched from the table renders the value to be displayed in the **TagCloud**.

### URL

URL field in the data table or **JSON** data assigned the datasource is mapped to the URL property of the **TagCloud** control. The URL property defines the link to be navigated on clicking the corresponding text item.

### frequency

It maps to the frequency field name from the data table or **JSON** data that is assigned to the dataSource. The frequency value that is fetched from the table should be a number to categorize the font size.

In data binding concept of TagCloud control, need to set the fields using two way binding that is you need to assign the values of the fields using scope variable.

The following example depicts you the way to bind data to the **TagCloud** widget,

{% highlight html %}

<ej-tagcloud id="tag" titleText="Popular Sites" [dataSource]="list"></ej-tagcloud>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
        @Component({
           selector: 'sd-home',
            templateUrl: 'app/components/tagcloud/tagcloud.component.html'
         })
        export class TagCloudComponent {
          list: Array<Object>;
          constructor() {      
          this.list = [
            { text: "Google", url: "http://www.google.co.in", frequency: 12 },
            { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
            { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
            { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
            { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
            { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
            { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
            { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
            { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
            { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
            { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
            { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
            { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
            { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
            { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
            { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
            { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
            { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }
            ];
            }
       }

{% endhighlight %}

The following screenshot illustrates a **TagCloud** control using AngularJS data binding,

![](Data-Binding_images/Data-Binding_img1.png)