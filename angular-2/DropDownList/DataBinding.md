---
layout: post
title: Data binding in DropDownList widget
description: Describes about the data binding in DropDownList widget 
platform: Angular2
control: DropDownList
documentation: ug
---

# Data Binding

To populate data in the DropDownList widget, define [dataSource](http://help.syncfusion.com/api/js/ejdropdownlist#members:datasource) property with associated fields. In DropDownList, can bind either local array or OData, WebApi and other [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer) services.

## Fields

The below listed fields are the data collection fields which maps fields for the data items of the DropDownList. 

<table>
    <tr>
        <th>
            Properties
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            dataSource
            <br/>
        </td>
        <td>
            The data source contains the list of data for generating the popup list items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            query
            <br/>
        </td>
        <td>
            It specifies the query to retrieve the data from the online server.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            fields
            <br/>
        </td>
        <td>
            It specifies the mapping fields for the data items of the DropDownList widget.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            id
            <br/>
        </td>
        <td>
            It specifies the ID of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            text
            <br/>
        </td>
        <td>
            It specifies the text content of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            value
            <br/>
        </td>
        <td>
            It specifies the value of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            groupBy
            <br/>
        </td>
        <td>
            It is used to categorize the items based on a specific field.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            imageUrl
            <br/>
        </td>
        <td>
            It defines the image location.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            imageAttributes
            <br/>
        </td>
        <td>
            It defines the image attributes such as height, width, styles, etc.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            spriteCssClass
            <br/>
        </td>
        <td>
            It defines the sprite CSS for the image tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            htmlAttributes
            <br/>
        </td>
        <td>
            It defines the HTML attributes such as class and styles for an item.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            selected
            <br/>
        </td>
        <td>
            This field defines the tag value to be selected initially. Corresponding field mapped has Boolean values to select the list items on control creation. The data with value true in this field is selected automatically when the control is initialized with checkbox.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            tableName
            <br/>
        </td>
        <td>
            It defines the table name for the tag value or displays text while rendering remote data.
            <br/>
        </td>
    </tr>
</table>

## Local Data

Define a JSON array and initialize the widget with [dataSource](http://help.syncfusion.com/api/js/ejdropdownlist#members:datasource) property. Specify the column names in the [fields](#Fields) property.

N> The columns are bounded automatically when the fields are specified with the default names like id, text, etc...

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="empList" [fields]="fieldsvalues">
	
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	empList: Array<Object>;
    fieldsvalues: Object;
    constructor() {
        this.empList = [{
                text: "Erik Linden",
                role: "Representative",
                country: "England"
            }, {
                text: "John Linden",
                role: "Representative",
                country: "Norway"
            }, {
                text: "Louis",
                role: "Representative",
                country: "Australia"
            }, {
                text: "Lawrence",
                role: "Representative",
                country: "India"
        }];
        this.fieldsvalues = { text: "text", value: "country", groupBy:"role" };
    }
}

{% endhighlight %}

![](DataBinding_images/DataBinding_img1.png)

	
The JSON array to the [dataSource](http://help.syncfusion.com/api/js/ejdropdownlist#members:datasource) property can also be provided as an instance of the [ej.DataManager](http://help.syncfusion.com/api/js/ejdatamanager). When the JSON array is passed as an instance of [ej.DataManager](http://help.syncfusion.com/api/js/ejdatamanager), the [ej.JsonAdaptor](http://help.syncfusion.com/js/datamanager/data-adaptors#json-adaptor) will be used to manipulate the DropDownList data source. The following code explains this behavior,

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data">
	
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	data: any;
    constructor() {
        var items = [{
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
       this.data = ej.DataManager(items);
    }
}

{% endhighlight %}

## Binding Remote Data Service

To bind remote data to the DropDownList, assign a service data as an instance of `ejDataManager` to the `dataSource` property.

### OData

OData is a standardized protocol for creating and consuming data. Provide the [OData service](http://www.odata.org/) URL directly to the "ej.DataManager" class and then you can assign it to DropDownList "dataSource".

{% highlight html %}

 <input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" />
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    constructor() {
        this.data = ej.DataManager("http://mvc.syncfusion.com/Services/Northwnd.svc/Orders");
        this.fieldsvalues = { text: "ShipName", value: "ShipCountry" };
    }
}

{% endhighlight %}        
          
## OData Version 4

The OData v4 is an improved version of OData protocols and the Data Manager can also retrieve and consume data from [ODatav4](http://www.odata.org/) services.

By using URL property of “ej.DataManager” bind OData Version 4 Service link and specify adaptor as ej.ODataV4Adaptor.

{% highlight html %}

 <input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" />
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    constructor() {
        var dataManager = ej.DataManager({
            url: "http://services.odata.org/V4/Northwind/Northwind.svc/Regions/",
            adaptor: new ej.ODataV4Adaptor()
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "RegionDescription", value: "RegionID" };
    }
}

{% endhighlight %}      
           
![](DataBinding_images/DataBinding_img2.png)

N> Events associated with remote data bind is listed [here](http://help.syncfusion.com/api/js/ejdropdownlist#events). 

## WebAPI Binding

Using [ej.WebApiAdaptor](http://help.syncfusion.com/js/datamanager/data-adaptors#webapi-adaptor), bind WebApi service’s data to DropDownList. The data from WebApi service must be returned as an object that has property “Items” with its value as data source and another property “Count” with its value as dataSource’s total records count.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" />

{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    constructor() {
        var dataManager =  ej.DataManager({
        url: "/api/Orders",
        adaptor: new ej.WebApiAdaptor()
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "CustomerID", value: "CustomerID" };
    }
}

{% endhighlight %}   

{% highlight c# %}

    public class OrdersController : ApiController
    {
        // GET api/orders
        NorthwindDataContext db = new NorthwindDataContext();
        public PageResult<Order> Get(ODataQueryOptions opts)
        {
            List<Order> ord = db.Orders.ToList();

            return new PageResult<Order>(ord as IEnumerable<Order>, null, ord.Count);
        }

    }

{% endhighlight %}

![](DataBinding_images/DataBinding_img3.png)

## ASP.NET Web Method Binding

The data can retrieve data from ASP.NET Web methods by making use of the WebMethod Adaptor of ejDataManager.

The WebMethod Adaptor is used to bind data source from remote services and code behind methods. 
By using “[WebMethodAdaptor](http://help.syncfusion.com/js/datamanager/getting-started)” we can bind data from WebService to the DropDownList control and also we need to include “ScriptService” Attribute to WebService in order to enable request from client-side.

{% highlight html %}

<span> Please select... </span>
<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="dataList" [query]="queries" [fields]="fieldsvalues" />

{% endhighlight %}

{% highlight c# %}

    [System.Web.Script.Services.ScriptService]
    public class WebService1 : System.Web.Services.WebService
    {
        [WebMethod]
        public object Get()
        {
            List<Employee> EmpData = new List<Employee>();
            EmpData.Add(new Employee
            {
                Name = "Erik Linden",
                Role = "Executive"
                
            });
            EmpData.Add(new Employee
            {
                Name = "John Linden",
                Role = "Representative"
                
            });
            EmpData.Add(new Employee
            {
                Name = "Louis",
                Role = "Representative"
                
            });
            EmpData.Add(new Employee
            {
                Name = "Lawrence",
                Role = "Executive"
                
            });
            dynamic count = EmpData.Count;
            return new
            {
                result = EmpData,
                count = count
            };

        }
        public class Employee
        {
            public string Name { get; set; }
            public string Role { get; set; }
            
        }
    }
    
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    dataList: any;
    fieldsvalues: Object;
    queries: any;    
    constructor() {
         var data = ej.DataManager({
            url: "WebService1.asmx/Get",
            adaptor: new ej.WebMethodAdaptor()
        });
        var query = ej.Query().requiresCount();
        this.dataList = data;
        this.queries = query;
        this.fieldsvalues = { text: "Name", value: "Country" };
    }
}

{% endhighlight %} 

Use the above code example to use WebMethod adaptor and bind the data to the DropDownList.

## MVC controller Action Binding

The data can retrieve from MVC controller. This can be achieved by using the UrlAdaptor of ej.DataManager.

Defines the List of Employee Data and converted into JSON object. 

{% highlight c# %}

    using System.Web.Script.Serialization;
    public partial class DropdownlistController: Controller
    {
        public ActionResult DropdownlistFeatures()
        {
            return View();
         } 
        public class Employee
        {
            public string Name { get; set; }
            public string Role { get; set; }
        }
        public JsonResult getData()
        {
            List<Employee> EmpData = new List<Employee>();
            EmpData.Add(new Employee
            {
                Name = "Erik Linden",
                Role = "Executive"
            });
            EmpData.Add(new Employee
            {
                Name = "John Linden",
                Role = "Representative"
            });
            EmpData.Add(new Employee
            {
                Name = "Louis",
                Role = "Representative"
            });
            EmpData.Add(new Employee
            {
                Name = "Lawrence",
                Role = "Executive"
            });
            var jsonSerialiser = new JavaScriptSerializer();
            return Json(jsonSerialiser.Serialize(EmpData));
        }
    }
    
{% endhighlight %}

In client side, specify the URL of Data to url property and specify the type of Adaptor in adaptor property of DataManager and initialize the DropDownList with [dataSource](http://help.syncfusion.com/api/js/ejdropdownlist#members:datasource) property. Specify the column names in the [fields](http://help.syncfusion.com/api/js/ejdropdownlist#members:fields) property.

{% highlight html %}

<div class="ctrllabel"> Select an Employee</div>
<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" />

{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    constructor() {
        var dataManager = ej.DataManager({
        url: "/Dropdownlist/getData",
        adaptor: new ej.UrlAdaptor()
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "Name", value: "Role" };
    }
}

{% endhighlight %} 

## Other Restful web services

The [Custom Adaptor](http://help.syncfusion.com/js/datamanager/data-adaptors#custom-adaptor) concept of "ej.DataManager" allows to customize or generate your own adaptor which is used to process "query" and "result" data. 
When using remote data binding, the adaptor of "ej.DataManager" plays vital role in processing queries to make them suitable to sends along with data request and also process the response data from the server.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" />

{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    constructor() {
        var customAdaptor = new ej.Adaptor().extend({
        insert: function (dm, data) {
        return dm.dataSource.json.push(data);
        },
        processQuery: ej.JsonAdaptor.prototype.processQuery
        // reused process query from json adaptor
        });
        
        window.dropdownData = [{
            FirstName: "John",
            LastName: "Abraham"
        }, {
            FirstName: "Ben",
            LastName: "Nick"
        }, {
            FirstName: "Andrew",
            LastName: "Clarke"
        }];

        var dataManager = new ej.DataManager(window.dropdownData);

        // assigning custom adaptor to datamanager
        dataManager.adaptor = new customAdaptor();

        // insert from custom adaptor usage
        dataManager.insert({
            FirstName: "Joel",
            LastName: "Nick"
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "FirstName", value: "LastName" };
    }
}

{% endhighlight %} 

![](DataBinding_images/DataBinding_img4.png)


## Virtual Scrolling 

To improve the performance when displaying large data set, you can use “allowVirtualScrolling” and [virtualScrollMode](http://help.syncfusion.com/api/js/ejdropdownlist#members:virtualscrollmode) property. This retrieves only a fixed amount of list items and loads remaining data on scrolling. The items will be fetched via AJAX request.

This supports two modes of virtualization. They are,

* Normal Mode
* Continuous Mode

I> 1. Sorting and Grouping is not supported with Virtual Scrolling
I> 2. “virtualScrollMode” property accepts both the string and ej.VirtualScrollMode enum value.

### Normal Mode

It loads the data on scrolling the list of items. This can be achieved by setting [normal](http://help.syncfusion.com/api/js/ejdropdownlist#members:virtualscrollmode) value to the "virtualScrollMode" property.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [itemsCount]="count" [allowVirtualScrolling]="true" [virtualScrollMode]="mode"/>
     
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    mode: any;
    count: number;
    constructor() {
        var dataManager = ej.DataManager({
            url: "http://mvc.syncfusion.com/services/Northwnd.svc/Orders"
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "ShipName", value: "ShipCountry" };
        this.mode = ej.VirtualScrollMode.Normal;
        this.count =7;
    }
}

{% endhighlight %}

### Continuous Mode

It loads the set of items when the scroller reaches at the end. This behaves like infinity scrolling. So when scroll reaches the end, it will fetch the remaining set of items and bind with your DropDownList. This can be achieved by setting [continuous](http://help.syncfusion.com/api/js/ejdropdownlist#members:virtualscrollmode) value to the "virtualScrollMode" property.

N> In both modes, set of items will be fetched based on the count specified in the [itemsCount](http://help.syncfusion.com/api/js/ejdropdownlist#members:itemscount) property and next set of items will be loaded on scrolling.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="fieldsvalues" [itemsCount]="count" [allowVirtualScrolling]="true" [virtualScrollMode]="mode"/>
     
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: any;
    fieldsvalues: Object;
    mode: any;
    count: number;
    constructor() {
        var dataManager = ej.DataManager({
            url: "http://mvc.syncfusion.com/services/Northwnd.svc/Orders"
        });
        this.data = dataManager;
        this.fieldsvalues = { text: "ShipName", value: "ShipCountry" };
        this.mode = ej.VirtualScrollMode.Continuous;
        this.count =7;
    }
}

{% endhighlight %}