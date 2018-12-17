---
layout: post
title: Syncfusion ListBox DataBinding
description: databinding
platform: Angular
control: ListBox
documentation: ug
---

# Data binding

## Field mapping

The ListBox component has a field property (object) which holds the properties to map with datasource fields. For example, the field object has a text property which is necessary to map with specific field in the datasource to render the items in the ListBox component.

The field object contains the following properties.

* [text](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [toolTipText](http://helpjs.syncfusion.com/js/api/ejlistbox#members:fields)

* [id](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [selectBy](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [groupBy](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [checkBy](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [tableName](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [imageUrl](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [imageAttributes](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [spriteCssClass](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

* [htmlAttributes](http://help.syncfusion.com/js/api/ejlistbox#members:fields)

## Local data

The local data can be an array of JSON objects which is assigned for the datasource property of ListBox component.

Here the employeeId and text are fields with it's mapped to the id and value fields of object respectively.

{% highlight html %}

   <div id="control">
       <ej-listbox [dataSource]="data" [fields]="fieldList"></ej-listbox>
    </div>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    data:array;
    fieldList:object;
    value:string;
    constructor() {
    this.data=[
        { employeeId: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { employeeId: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { employeeId: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { employeeId: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { employeeId: "cr5", text: "Dazzler", value: "Dazzler" },
        { employeeId: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { employeeId: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { employeeId: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { employeeId: "cr9", text: "Honda Cross tour", value: "Honda Cross tour" },
        { employeeId: "cr10", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { employeeId: "cr11", text: "Mazda3", value: "Mazda3" }
    ];
    this.fieldList={dataSource:this.data,text:"text",value:"value"};
    }
}
{% endhighlight %}

![FieldSetting Listbox](Databinding_images\Databinding_img1.png)

## Remote data

### OData

[OData](http://helpjs.syncfusion.com/js/datamanager/data-binding) is a standardized protocol for creating and consuming the data. You can retrieve data from OData service by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

Here the CustomerID field is mapped with text property of the field object. The queries can be created using [ej.Query()](http://helpjs.syncfusion.com/js/datamanager/query).

{% highlight html %}

     <div id="control">
       <ej-listbox [dataSource]="dataManager" [fields]="fieldList" [query]="query"></ej-listbox>
    </div>   

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    fieldList: object;
    query: any;
    dataManager: any;
    constructor() {
        this.dataManager = ej.DataManager({
            //OData service
            url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
        });
        this.query = ej.Query().from("Customers").take(10);
        this.fieldList = { text: "CustomerID" };       
    }
}

{% endhighlight %}

![Alt text](Databinding_images\Databinding_img2.png)

### WebAPI

[ASP.NET Web API](https://msdn.microsoft.com/en-us/library/hh833994%28v=vs.108%29.aspx) is a Framework for building HTTP services. You can retrieve data from ASP.NET Web API by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

{% highlight html %}

    <div id="control">
        <ej-listbox [dataSource]="dataManager" [fields]="fieldList"></ej-listbox>
    </div>   

{% endhighlight %}

{% highlight ts %}

 export class AppComponent {
    fieldList: object;
    dataManager: any;
    constructor() {
        this.dataManager = ej.DataManager({
            url: "http://mvc.syncfusion.com/UGService/api/Orders",
            crossDomain: true
        });
        this.fieldList = { text: "CustomerID" };       
    }
}

{% endhighlight %}

N> _In the above data manager configuration, “crossDomain” must be set to true to access the data from Web API._

 {% seealso %} [Cross domain](http://help.syncfusion.com/js/grid/data-binding) {% endseealso %}

![Alt text](Databinding_images\Databinding_img3.png)

### Handling errors

 In remote binding, the server might not return data sometimes due to various reasons. In such cases we need to handle the error properly. We can handle it using the “actionFailure” event. 

{% seealso %} [actionComplete](http://help.syncfusion.com/js/api/ejlistbox#events:actioncomplete) and [actionSuccess](http://help.syncfusion.com/js/api/ejlistbox#events:actionsuccess) {% endseealso %}

{% highlight javascript %}

    <div id="control">
         <ej-listbox [dataSource]="dataManager" [fields]="fieldList" [query]="query" (actionFailure)="actionFailure($event)"></ej-listbox>   
    </div>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    fieldList: object;
    dataManager: any;
    query: any;
    constructor() {
        this.dataManager = ej.DataManager({
            url: "http://mvc.syncfusion.com/Services/Northwnd.svc/",
            crossDomain: true
        });
        this.query = ej.Query().from("Customers");
        this.fieldList = { text: "CustomerID" };       
    }
    actionFailure(event) {
         //handle errors
    }
}

{% endhighlight %}












