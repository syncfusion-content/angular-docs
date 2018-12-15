---
layout: post
title: Databinding
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

Here the empId and text are fields with it's mapped to the id and value fields of object respectively.

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
        { empId: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
        { empId: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
        { empId: "cr3", text: "Ford Focus", value: "Ford Focus" },
        { empId: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
        { empId: "cr5", text: "Dazzler", value: "Dazzler" },
        { empId: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
        { empId: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
        { empId: "cr8", text: "Honda Fit", value: "Honda Fit" },
        { empId: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
        { empId: "cr10", text: "Acura RL", value: "Acura RL" },
        { empId: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
        { empId: "cr12", text: "Mazda3", value: "Mazda3" }
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
       <ej-listbox [dataSource]="datamanager" [fields]="fieldList" [query]="query"></ej-listbox>
    </div>   

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    fieldList: object;
    query: any;
    datamanager: any;
    constructor() {
        this.datamanager = ej.DataManager({
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
        <ej-listbox [dataSource]="datamanager" [fields]="fieldList"></ej-listbox>
    </div>   

{% endhighlight %}

{% highlight ts %}

 export class AppComponent {
    fieldList: object;
    datamanager: any;
    constructor() {
        this.datamanager = ej.DataManager({
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
         <ej-listbox [dataSource]="datamanager" [fields]="fieldList" [query]="query" (actionFailure)="actionfailure($event)"></ej-listbox>   
    </div>

{% endhighlight %}

{% highlight ts %}

export class AppComponent {
    fieldList: object;
    datamanager: any;
    query: any;
    constructor() {
        this.datamanager = ej.DataManager({
            url: "http://mvc.syncfusion.com/Services/Northwnd.svc/",
            crossDomain: true
        });
        this.query = ej.Query().from("Customers");
        this.fieldList = { text: "CustomerID" };       
    }
    actionfailure(event) {
         //handle errors
    }
}

{% endhighlight %}












