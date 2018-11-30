---
layout: post
title: data binding
description: data binding
platform: Angular
control: Autocomplete 
documentation: ug
---

## Data Binding

In order to render the AutoComplete component, the data needs to be bound to it in a proper way. The below sections explains about how to bind either the local or remote data to the AutoComplete component.

## Fields

The AutoComplete component has **fields** property (object) which holds the properties to map with datasource fields. For example, the field object has a text property which is necessary to map with specific field in the datasource to render the suggestion items in the AutoComplete component. Or else empty suggestion list appears.

The field object contains the following properties.

* [text](http://help.syncfusion.com/api/js/ejautocomplete)

* [key](http://help.syncfusion.com/api/js/ejautocomplete)

* [groupBy](http://help.syncfusion.com/api/js/ejautocomplete)

* [htmlAttributes](http://help.syncfusion.com/api/js/ejautocomplete)

## Local data

The local data can be an array of JSON objects which is assigned for the Autocomplete component’s **dataSource** property. Refer the below example.

Here the name and index fields are mapped with text and key properties of the field object respectively.

{% highlight html %}

<input type="text" id="databindinglocal" ej-autocomplete width="100%" watermarkText="Select a state" [fields]="fields" [dataSource]="states" />

{% endhighlight %}

{% highlight js %}

export class AppComponent {
     states: Array<any>;
    fields: Object;
    value: string;
    constructor() {
        this.fields = { key: 'index', text: 'countryName' };
        this.states = [
            { index: 's1', countryName: 'Alabama' }, { index: 's2', countryName: 'Alaska' },
            { index: 's3', countryName: 'Arizona' }, { index: 's4', countryName: 'Arkansas' },
            { index: 's5', countryName: 'California' }, { index: 's6', countryName: 'Colorado' },
            { index: 's7', countryName: 'Connecticut' },
            { index: 's8', countryName: 'Delaware' },
            { index: 's9', countryName: 'Florida' },
            { index: 's10', countryName: 'Georgia' },
            { index: 's11', countryName: 'Hawaii' },
            { index: 's12', countryName: 'Idaho' }, { index: 's13', countryName: 'Illinois' },
            { index: 's14', countryName: 'Indiana' }, { index: 's15', countryName: 'Iowa' },
            { index: 's16', countryName: 'Kansas' }, { index: 's17', countryName: 'Kentucky' },
            { index: 's18', countryName: 'Louisiana' }, { index: 's19', countryName: 'Maine' },
            { index: 's20', countryName: 'Maryland' }, { index: 's21', countryName: 'Massachusetts' },
            { index: 's22', countryName: 'Michigan' }, { index: 's23', countryName: 'Montana' },
            { index: 's24', countryName: 'New Mexico' }, { index: '25', countryName: 'New York' },
            { index: '26', countryName: 'North Carolina' }, { index: 's27', countryName: 'Nevada' },
            { index: 's28', countryName: 'New Jersey' }, { index: 's29', countryName: 'Pennsylvania' },
            { index: 's30', countryName: 'Ohio' }, { index: 's31', countryName: 'Oklahoma' },
            { index: 's32', countryName: 'Oregon' },
            { index: 's33', countryName: 'Rhode Island' },
            { index: 's34', countryName: 'South Carolina' }, { index: 's35', countryName: 'South Dakota' },
            { index: 's36', countryName: 'Tennessee' }, { index: 's37', countryName: 'Texas' },
            { index: 's38', countryName: 'Utah' },
            { index: 's39', countryName: 'Vermont' }, { index: 's40', countryName: 'Virginia' },
            { index: 's41', countryName: 'Washington' }, { index: 's42', countryName: 'West Virginia' },
            { index: 's43', countryName: 'Wisconsin' }, { index: 's44', countryName: 'Wyoming' }
        ];

    }
}

{% endhighlight %}


Run the above code to render the following output.

![](databinding_images\localdata_img1.png)

## Remote data

### OData

[OData](http://help.syncfusion.com/js/datamanager/data-binding) is a standardized protocol for creating and consuming the data. You can retrieve data from OData service by using [ej.DataManager](http://help.syncfusion.com/js/datamanager/getting-started).

Here the ContactName and SupplierID fields are mapped with text and key properties respectively, of the field object. The queries can be created using [ej.Query()](http://helpjs.syncfusion.com/js/datamanager/query).

{% highlight html %}

  <input type="text" ej-autocomplete width="300" [query]="query" [fields]="fields" watermarkText="Search a customer" [dataSource]="dataManger" />

{% endhighlight %}

{% highlight js %}

export class AppComponent {
     dataManger: any;
    fields: any;
    query: any;
    value: string;
    constructor() {
        this.fields = { text: 'ContactName', key: 'SupplierID' };
        this.dataManger = ej.DataManager({ url: 'http://mvc.syncfusion.com/Services/Northwnd.svc/' }); 
        this.query = ej.Query().from('Suppliers').select('SupplierID', 'ContactName');
    }
}

{% endhighlight %}


Run the above code to render the following output.

![](databinding_images\odata_img1.png)


### WebAPI

[ASP.NET Web API](https://msdn.microsoft.com/en-us/library/hh833994(v=vs.108).aspx) is a Framework for building HTTP services. You can retrieve data from ASP.NET Web API by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

Here the ContactName field is mapped with text property of the field object.

{% highlight html %}

 <input type="text" ej-autocomplete width="300"  [fields]="fields" watermarkText="Search a customer" [dataSource]="dataManger" />



{% endhighlight %}



{% highlight js %}


export class AppComponent {
     dataManger: any;
    fields: any;
    query: any;
    value: string;
    constructor() {
        this.fields = { text: 'ContactName', key: 'SupplierID' };
        this.dataManger = ej.DataManager({ url: "api/Suppliers", crossDomain: true }); 
        this.query = ej.Query().from('Suppliers').select('SupplierID', 'ContactName');
    }
}

{% endhighlight %}


Run the above code to render get the following output.

![](databinding_images\webapi_img1.png)

NOTE

In the above data manager configuration, “crossDomain” must be set to true to access the data from Web API. [Cross domain](http://helpjs.syncfusion.com/js/grid/data-binding) requests can be possible using ej.DataManager.


### Handling errors

In remote binding, the server might not return data sometimes due to various reasons. In such cases we need to handle the error properly. We can handle this errors using the [`actionFailure`](http://help.syncfusion.com/api/js/ejautocomplete) event.

### See Also

[action complete](http://help.syncfusion.com/api/js/ejautocomplete) event

[action success](http://help.syncfusion.com/api/js/ejautocomplete) event
