---
layout: post
title: data binding
description: data binding
platform: Angular
control: ListView
documentation: ug
---

# Data Binding

## Local Data Binding

The ListView component provides Data Binding support. Data Binding provides a simple and consistent way for applications to present and interact with data. Elements can be bounded to data from a variety of data sources. In local data binding, the data source is written inside the program. Then it is handled by the ListView component. DataSource is used to get the **data source** that holds the list items.

Create div element to render the ListView sample.

{% highlight html %}

<ej-listview [dataSource]="listdata" [fieldSettings]="fieldsdata" [width]="width">
</ej-listview>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    listdata: any;
    width: any;
    fieldsdata: any;
    constructor() {
         this.listdata =
           [{ Texts: 'Discover Music' },
            { Texts: 'Sales and Events' },
            { Texts: 'Categories' },
            { Texts: 'MP3 Albums' },
            { Texts: 'More in Music' }];
        this.fieldsdata = { 'text': 'Texts' };
        this.width = 400;      
    }
}

{% endhighlight %}

Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Data-Binding_images/localdatabinding_img1.png](databinding_images\localdatabinding_img1.png)

## Remote Data Binding

ListView component also provides support for Remote Data Binding.

### OData

[OData](https://help.syncfusion.com/js/datamanager/data-binding) is a standardized protocol for creating and consuming the data. You can retrieve data from OData service by using [ej.DataManager](https://help.syncfusion.com/js/datamanager/getting-started).

Here the CustomerID field is mapped with text property of the field object. The queries can be created using [ej.Query()](https://help.syncfusion.com/js/datamanager/query).

{% highlight html %}

 <ej-listview [dataSource]="listdata" [fieldSettings]="fieldsdata" [width]="width" [query]="query">
 </ej-listview>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    listdata: any;
    width: any;
    fieldsdata: any;
    query: any;
    constructor() {
        this.listdata = ej.DataManager({
             //OData service
             url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
        });
        this.query = ej.Query().from('Customers').take(10);
        this.fieldsdata = { 'text': 'CustomerID' };
        this.width = 400;      
    }
}

{% endhighlight %}

Run the above code to render the following output.

![](databinding_images\odata_img1.png)

### WebAPI

[ASP.NET Web API](https://msdn.microsoft.com/en-us/library/hh833994%28v=vs.108%29.aspx) is a Framework for building HTTP services. You can retrieve data from ASP.NET Web API by using [ej.DataManager](https://help.syncfusion.com/js/datamanager/getting-started).

{% highlight html %}

<ej-listview [dataSource]="listdata" [fieldSettings]="fieldsdata" [height]="height">
</ej-listview>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    listdata: any;
    fieldsdata: any;
    height: any;
    constructor() {
        this.listdata = ej.DataManager({
            url: "http://js.syncfusion.com/ejservices/Wcf/Northwind.svc/",
            crossDomain: true
        });
        this.fieldsdata = { text: "CustomerID" };
        this.height = 500;    
    }
}

{% endhighlight %}

**NOTE**

In the above data manager configuration, “crossDomain” must be set to true to access the data from Web API.

Run the above code to render the following output.

![](databinding_images\webapi_img1.png)


## FieldSettings

The fieldSettings property is used to map the DataSource with the list item fields. In addition to the list [item specific properties](https://help.syncfusion.com/js/listview/grouped-list), the following fields are available while mapping.

**FieldSettings**

<table>
<tr>
<td>
<b>Properties</b></td><td>
<b>Definition</b></td></tr>
<tr>
<td>
ParentPrimaryKey</td><td>
In DB, you can relate any child item to some other item. Set here is ‘PrimaryKey’ for the parent item. Here ‘ParentPrimaryKey’ defines the ‘PrimaryKey’ of some parent item to identify its parent.</td></tr>
<tr>
<td>
Attributes</td><td>
In DB, you can define your desired class name or styles for the list item through the ‘Attributes’ field.</td></tr>
<tr>
<td>
navigateUrl</td><td>
This will helps to <a href=http://dictionary.cambridge.org/dictionary/english/direct>direct</a> the navigation for a location</td></tr>
<tr>
<td>
text</td><td>
Defines the specific field name in the data source to load the suggestion list with data.</td></tr>
<tr>
<td>
primarykey</td><td>
This primarykey field name in the data source defines the ‘PrimaryKey’ of an item</td></tr>
<tr>
<td>
checked</td><td>
This filed will helps the value to be checked</td></tr>
</table>

Please refer the following code examples.

{% highlight html %}

 <ej-listview [dataSource]="listdata" [fieldSettings]="fieldsdata" showHeader="true" headerTitle="List Items">
</ej-listview>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    listdata: any;
    fieldsdata: any;
    constructor() {
        this.listdata = [{ "Texts": "Discover Music", "PrimaryKeys": "1", "Title": "Discover Music", "BackIconText": "back" },
            { "Texts": "Hot Singles", "ParentPrimaryKeyss": "1" },
            { "Texts": "Rising Artists", "PrimaryKeyss": null, "ParentPrimaryKeyss": "1" },
            { "Texts": "Live Music", "ParentPrimaryKeyss": "1" },
            { "Texts": "Best of 2013 So Far", "ParentPrimaryKeyss": "1" },
            { "Texts": "Sales and Events", "PrimaryKeys": "2", "Title": "Sales and Events", "BackIconText": "back" },
            { "Texts": "100 Albums - $5 Each", "ParentPrimaryKeyss": "2" },
            { "Texts": "Hip-Hop and R&B Sale", "ParentPrimaryKeyss": "2" },
            { "Texts": "CD Deals", "ParentPrimaryKeyss": "2" },
            { "Texts": "Categories", "PrimaryKeys": "3", "Title": "Categories", "BackIconText": "back" },
            { "Texts": "Songs", "ParentPrimaryKeyss": "3" },
            { "Texts": "Bestselling Albums", "ParentPrimaryKeyss": "3" },
            { "Texts": "New Releases", "ParentPrimaryKeyss": "3" },
            { "Texts": "Bestselling Songs", "ParentPrimaryKeyss": "3" },
            { "Texts": "MP3 Albums", "PrimaryKeys": "4", "Title": "MP3 Albums", "BackIconText": "back" },
            { "Texts": "Rock", "ParentPrimaryKeyss": "4" },
            { "Texts": "Gospel", "ParentPrimaryKeyss": "4" },
            { "Texts": "Latin Music", "ParentPrimaryKeyss": "4" },
            { "Texts": "Jazz", "ParentPrimaryKeyss": "4" },
            { "Texts": "More in Music", "PrimaryKeys": "5", "Title": "More in Music", "BackIconText": "back" },
            { "Texts": "Music Trade-In", "ParentPrimaryKeyss": "5" },
            { "Texts": "Redeem a Gift Card", "ParentPrimaryKeyss": "5" },
            { "Texts": "Band T-Shirts", "ParentPrimaryKeyss": "5" },
            { "Texts": "Web MVC", "ParentPrimaryKeyss": "5" }];
        this.fieldsdata = {
            "text": "Texts",
            "primaryKey": "PrimaryKeys",
            "parentPrimaryKey": "ParentPrimaryKeyss",
            "childHeaderTitle": "Title",
            "childHeaderBackButtonText": "BackIconText" };   
    }
}

{% endhighlight %}

Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Data-Binding_images/fieldsettings_img1.png](databinding_images\fieldsettings_img1.png)

When you click on the parent item, it navigates to its corresponding child list item as follows.

![https://help.syncfusion.com/js/ListView/Data-Binding_images/fieldsettings_img1.png](databinding_images\fieldsettings_img2.png)


