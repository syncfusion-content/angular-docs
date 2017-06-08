---
layout: post
title: Virtual Scrolling
description: virtual scrolling
platform: Angular
control: ListView
documentation: ug
---

# Virtual Scrolling

  We can load large data on demand using "allowVirtualScrolling" property. By default, "allowVirtualScrolling" set as boolean value of **"false"**. When it is set true, list items will be loaded on every scroll action. The number of items to be loaded per request can be specified using the “itemRequestCount” property.By default “itemRequestCount” value will be 5. We have provided two type of option for virtualScrolling,

## Normal Mode
   This mode allows you to load the list view data while scrolling i.e. each time the scroll bar is scrolled, it will send request to the server to load the data.

## Continuous Mode
    This mode allows you to load the list view data when the scrollbar reaches the end point. In this mode, we can specify the number of items to be loaded per request.

Please refer the following code examples.

{% highlight html %}

    <ej-listview [dataSource]="listdata" [fieldSettings]="fieldsdata" [width]="width" [height]="height" [allowVirtualScrolling]="true" [virtualScrollMode]="VirtualMode" [query]="query" [itemRequestCount]="requestCount">
    </ej-listview>

{% endhighlight %}
Add following code in Typescript file.

    {% highlight ts %}

    export class DefaultComponent {
    listdata: any;
    width: any;
    fieldsdata: any;
    query: any;
    requestCount:any;
    constructor() {
        this.listdata = ej.DataManager({
             //OData service
             url: "http://js.syncfusion.com/ejservices/Wcf/Northwind.svc/"
        });
        this.query = ej.Query().from('Customers');
        this.fieldsdata = { 'text': 'CustomerID' };
        this.width = 50; 
		this.height=200;
        this.requestCount=8;
		this.VirtualMode=ej.VirtualScrollMode.Continuous
                }
            }

    {% endhighlight %}