---
layout: post
title: Virutual-Scrolling
description: Virutual-Scrolling
platform: Angular
control: ListBox
documentation: ug
---

# Virtual Scrolling

 The ListBox component provides support to load its data on demand via scrolling behavior to improve the application’s performance. This can be achieved using `allowVirtualScrolling` property. There are two ways to load data based on the scrolling type.

1. Normal scrolling

2. Continuous Scrolling

The scrolling type can be defined via `virtualScrollMode` property.

## **Normal Scrolling**

This mode allows you to load the list box data while scrolling i.e. each time the scroll bar is scrolled, it will send request to the server to load the data.

{% highlight javascript %}
       <div id="controlitem">
            <ej-listbox id="selectExperts" [dataSource]="dataManger" [query]="query" [allowMultiSelection]="true" [fields]="fieldList"
            [allowVirtualScrolling]="true"></ej-listbox>
        </div>

{% endhighlight %}

{% highlight ts %}

export class VirtualScrollingComponent {
    dataManger: any;
    query: any;
    fieldList: object;
    constructor() {
        this.dataManger = ej.DataManager({ url: 'http://mvc.syncfusion.com/Services/Northwnd.svc/' });
        this.query = ej.Query().from('Customers');
        this.fieldList = { text: "CustomerID" };  
    }
}
            
{% endhighlight %}

N> _By default, the value of “virtualScrollMode” property is normal._

![Alt text](Databinding_images\Databinding_img5.png)

## **Continuous Scrolling**

This mode allows you to load the list box data when the scrollbar reaches the end point. In this mode, we can specify the number of items to be loaded per request.

The number of items to be loaded per request can be specified using the “itemRequestCount” property.

{% highlight html %}

<div id="controlitem">
            <ej-listbox id="selectExperts" [dataSource]="dataManger" [query]="query" [allowMultiSelection]="true" [fields]="fieldList"
            [allowVirtualScrolling]="true" [virtualScrollMode]="virtualmode"></ej-listbox>
</div>

{% endhighlight %}

{% highlight ts %}

export class appComponent {
    dataManger: any;
    query: any;
    fieldList: object;
    virtualmode: any;
    constructor() {
        this.dataManger = ej.DataManager({ url: 'http://mvc.syncfusion.com/Services/Northwnd.svc/' });
        this.query = ej.Query().from('Customers');
        this.fieldList = { text: "CustomerID" };  
        this.virtualmode = ej.VirtualScrollMode.Continuous;
    }
}
 
{% endhighlight %}

N> _The “itemRequestCount” property will work only when “virtualScrollMode” is “continuous”._

![Alt text](Databinding_images\Databinding_img7.png)

