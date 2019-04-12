---
layout: post
title: Data binding in Syncfusion ComboBox widget.
description: Describes about the data binding in ComboBox widget
platform: Angular
control: ComboBox
documentation: ug
keywords: ComboBox, combobox, data binding
---

# Data Binding

The ComboBox loads the data either from local data sources or remote data services using the dataSource property. It supports the data type of array or DataManager.

The ComboBox also supports different kinds of data services such as OData, OData V4, and Web API, and data formats such as XML, JSON, and JSONP with the help of DataManager adaptors.

## Fields

The below listed fields are the data collection fields which maps fields for the data items of the ComboBox. 

| Fields | Type | Description |
|------|------|-------------|
| text |  `string` | Specifies the display text of each list item. |
| value |  `string` | Specifies the hidden data value mapped to each list item that should contain a unique value. |
| groupBy |  `string` | Specifies the category under which the list item has to be grouped. |
| iconCss |  `string` | Specifies the icon class of each list item. |

> When binding complex data to the ComboBox, fields should be mapped correctly. Otherwise, the selected item remains undefined.

## Binding Local Data

Local data can be represented in two ways as described below.

### 1. Array of Simple Data

The ComboBox has support to load array of primitive data such as strings and numbers. Here, both value and text field act the same.

{% highlight html %}
	
	<input id="List" ej-combobox [dataSource]="data"/>
			
{% endhighlight %}
	
{% highlight html%}	
	
		import {Component} from '@angular/core';

         @Component({
           selector: 'ej-app',
           templateUrl: 'app/components/combobox/combobox.component.html' //give the path file for ComboBox component html file.
          })
          export class DropDownListComponent {
                data: Array<Object> = [];
                fields: Object;
                constructor() {
                   this.data = ['Badminton', 'Cricket', 'Football', 'Golf'];
              }
            }		
	
{% endhighlight %}

### 2. Array of JSON Data

The ComboBox can generate its list items through an array of complex data. For this, the appropriate columns should be mapped to the [fields](https://help.syncfusion.com/api/js/ejcombobox#members:fields) property.

In the following example, `Id` column and `Game` column from complex data have been mapped to the `value` field and `text` field, respectively.

{% highlight html %}
	
	<input id="List" ej-combobox [dataSource]="data" [fields]="fields" width="100%" [placeholder]="placeholder"/>
			
{% endhighlight %}
		
{% highlight html%}	
	
		import {Component} from '@angular/core';

         @Component({
           selector: 'ej-app',
           templateUrl: 'app/components/combobox/combobox.component.html' //give the path file for ComboBox component html file.
          })
          export class DropDownListComponent {
                data: Array<Object> = [];
                fields: Object;
                value: string;
				placeholder: string;
                constructor() {
                this.data = [
                   { id: 'level1', game: 'American Football' }, { id: 'level2', game: 'Badminton' },
	               { id: 'level3', game: 'Basketball' }, { id: 'level4', game: 'Cricket' },
	               { id: 'level5', game: 'Football' }, { id: 'level6', game: 'Golf' },
	               { id: 'level7', game: 'Hockey' }, { id: 'level8', game: 'Rugby' },
	               { id: 'level9', game: 'Snooker' }, { id: 'level10', game: 'Tennis' }
                  ];
              this.fields = { dataSource: this.data, text: "game", value: "id" };
			   this.placeholder = 'Select a game';
              }
            }		
	
{% endhighlight %}

## Binding Remote Data

The ComboBox supports retrieval of data from remote data services with the help of [DataManager](https://help.syncfusion.com/js/datamanager/getting-started) component. The [Query](https://help.syncfusion.com/api/js/ejquery) property is used to fetch data from the database and bind it to the ComboBox.

In the following sample, displayed first 6 contacts from the `customer` table of `Northwind` Data Service.

{% highlight html %}
	
	  <input id="List" ej-combobox [dataSource]="data" [fields]="fields" [query]="queries"  [placeholder]="placeholder"  />
			
{% endhighlight %}
	
{% highlight html%}	
	
		import {Component} from '@angular/core';

         @Component({
           selector: 'ej-app',
           templateUrl: 'app/components/combobox/combobox.component.html' //give the path file for ComboBox component html file.
          })
          export class DropDownListComponent {
                data: Array<Object> = [];
                fields: Object;
				queries: any;
				placeholder: string;
                constructor() {
                  let dataManager = new ej.DataManager({
                      url: 'https://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Customers',
                      crossDomain: true
               });
                  let query = new ej.Query().take(6);
                  this.queries = query;
		          this.data = dataManager;
                  this.fields = {text: "CustomerID", value: "CustomerID" };
				  this.placeholder = 'Select a customer';
              }
            }		
	
{% endhighlight %}

![RemoteData](DataBinding_images/DataBinding_image1.png)