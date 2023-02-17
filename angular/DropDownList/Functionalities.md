---
layout: post
title: Functionalities in the Angular DropDownList | Syncfusion
description: Learn here about Functionalities in Syncfusion Essential Angular DropDownList Control, its elements, and more.
platform: Angular
control: DropDownList
documentation: ug
---
# Functionalities in the Angular DropDownList

## Selection

By default only one item can be selected from the popup list. For multiple selection, you have to enable [checkboxes](Checkbox). The selected item consist of active class (“e-active”) to differentiate it from other items.

The following API’s, select the items in the DropDownList via text or value or indices.

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
            {{'[value](http://help.syncfusion.com/api/js/ejdropdownlist#members:value)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s value via value property.
            <br/>
            Multiple items can select via value property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[text](http://help.syncfusion.com/api/js/ejdropdownlist#members:text)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s text via text property.
            <br/>
            Multiple items can select via text property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectedIndex](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindex)'| markdownify }} 
            <br/>
        </td>
        <td>
            Select a single item by passing an index value to the selectedIndex property.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
             {{'[selectedIndices](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindices)'| markdownify }}
            <br/>
        </td>
        <td>
            Select more than one items by passing index values to the selectedIndices property when multi selection enabled. 
            <br/>
        </td>
    </tr>
</table>

N> Index starts from 0 here.
N> To use “selectedIndices” property, you should enable with showCheckbox or multiSelectMode property.

The following methods, select the items in the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[selectItemByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectitembyindices)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select the list of items in the DropDownList through the Index of the items.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByText](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectItemByText)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given text value.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectitembyvalue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given value.
            <br/>
        </td>
    </tr>
</table>

The following methods, used to retrieve the items from the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[getListData](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getlistdata)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items that are bound with the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedItem](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselecteditem)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to get the selected items in the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getSelectedValue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items value that are selected in the DropDownList.
            <br/>
        </td>
    </tr>
</table>

I> When multiSelectMode is enabled in a DropDownList and selected items having same text but its value is different means, the items can be selected. Please refer the online [link](http://jsplayground.syncfusion.com/Sync_5fgywhmb)

### Using value or text

To select an item initially you can pass the item’s value via [value](http://help.syncfusion.com/api/js/ejdropdownlist#members:value) property or [selectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectitembyvalue) method. To achieve this DropDownList widget must be initiated with the associate value. 

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="field" [(value)]="val"/>
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
    data: Array<Object> = [];
    field: Object;
    val: string;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.field = { dataSource: this.data, text: "text", value: "value" };
        this.val="item3";
    }
}

{% endhighlight %}

![Using value or text in Angular DropDownList](Functionalities_images/Functionalities_img1.png)

N> To retrieve the selected item’s LI elements and value you can use [getSelectedItem](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselecteditem), [getSelectedValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselectedvalue) methods respectively.

{% highlight javascript %}
	
  //create an instance from an existing DropDownList.

        // only after control creation we can get dropdownObj otherwise it throws exception.
        var obj = $('#dropdown1').data("ejDropDownList");
        //the below given code will return the li element of the selected item
        console.log(obj.getSelectedItem());
        //the below given code will return the JSON object of the selected item
        console.log(JSON.parse(obj.getSelectedValue()));
    });
	
{% endhighlight %}

### Using indices

You can select a single or more than one item by passing index values to the properties [selectedIndex](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindex) or [selectedIndices](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindices) respectively. Index starts from 0 here.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="field" [selectedIndex]="index"/>
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	data: Array<Object> = [];
    field: Object;
    index: number;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.field = { dataSource: this.data, text: "text", value: "value" };
        this.index = 1;
    }
}

{% endhighlight %}

![Using indices in Angular DropDownList](Functionalities_images/Functionalities_img2.png)

I> To use "selectedIndices" property, you should enable either showCheckbox or multiSelectMode property First.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="field" [selectedIndices]="select" [showCheckbox]="true"/>
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	data: Array<Object> = [];
    field: Object;
    select: Array<Number>;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.field = { dataSource: this.data, text: "text", value: "value" };
        this.select = [1, 2];
    }
}

{% endhighlight %}

### Unselect items

Similarly, you can unselect a single or multiple items by using [unselectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembyvalue) or [unselectItemByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembyindices) or [unselectItemByText](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembytext) methods. This will remove the selection state of the corresponding data item from the popup list and textbox. 

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="field" [selectedIndices]="select" [showCheckbox]="true"/>
<button (click)="unselect()">Unselect</button>
  
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	data: Array<Object> = [];
    field: Object;
    select: Array<Number>;
    constructor() {
        this.data = [
            { text: "ListItem 1", value: "item1" },
            { text: "ListItem 2", value: "item2" },
            { text: "ListItem 3", value: "item3" },
            { text: "ListItem 4", value: "item4" },
            { text: "ListItem 5", value: "item5" }
        ];
        this.field = { dataSource: this.data, text: "text", value: "value" };
        this.select = [1, 2, 3];
    }
    unselect() {
        var obj = $('#dropdown1').data("ejDropDownList");
        obj.unselectItemByValue("item2");
        obj.unselectItemsByIndices(2);
        obj.unselectItemByText("ListItem 4");
    }
}

{% endhighlight %}

## Grouping

The DropDownList items can be categorized by using a specific field in the popup list. This is enabled by using [groupBy](http://help.syncfusion.com/api/js/ejdropdownlist#members:fields-groupby) field on data source binding. By default grouping is disabled in DropDownList.
The below given example explains the behavior of grouping with JSON array binding.

{% highlight html %}

<input type="text" id="dropdown1" ej-dropdownlist [width]="width" [dataSource]="data" [fields]="field" [watermarkText]="watermark" [popupHeight]="height" />
     
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {   	
    data: Array<Object>;
    field: Object;
    watermark: string;
    height: number;
    constructor() {
        this.data = [{
            skill: "Cabbage",
            category: "Leafy and Salad"
            }, {
                skill: "Pea",
                category: "Leafy and Salad"
            }, {
                skill: "Spinach",
                category: "Leafy and Salad"
            }, {
                skill: "Wheat grass",
                category: "Leafy and Salad"
            }, {
                skill: "Yarrow",
                category: "Leafy and Salad"
            }, {
                skill: "Chickpea",
                category: "Beans"
            }, {
                skill: "Green bean",
                category: "Beans"
            }, {
                skill: "Horse gram",
                category: "Beans"
            }, {
                skill: "Peanut",
                category: "Beans"
            }, {
                skill: "Pigeon pea",
                category: "Beans"
            }, {
                skill: "Garlic",
                category: "Bulb and Stem"
            }, {
                skill: "Garlic Chives",
                category: "Bulb and Stem"
            }, {
                skill: "Lotus root",
                category: "Bulb and Stem"
            }, {
                skill: "Nopal",
                category: "Bulb and Stem"
            }, {
                skill: "Onion",
                category: "Bulb and Stem"
            }, {
                skill: "Shallot",
                category: "Bulb and Stem"
            }, {
                skill: "Beetroot",
                category: "Root and Tuberous"
            }, {
                skill: "Carrot",
                category: "Root and Tuberous"
            }, {
                skill: "Ginger",
                category: "Root and Tuberous"
            }, {
                skill: "Potato",
                category: "Root and Tuberous"
            }, {
                skill: "Radish",
                category: "Root and Tuberous"
            }, {
                skill: "Turmeric",
                category: "Root and Tuberous"
            }];
        this.field = { text: "skill", value: "value",groupBy:"category" };
        this.watermark = "Select a vegetable";
        this.height = 300;
    }
}

{% endhighlight %}

![Grouping in Angular DropDownList](Functionalities_images/Functionalities_img3.png)

I> Virtual scrolling is not supported with Grouping.

## Sorting

Sorting is enabled to order to display the items alphabetically in either ascending or descending order. By default the items is displayed in the initialized order, use [enableSorting](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablesorting) property to automatically sort strings based on text field value. You can assign either “ascending” or “descending” string values to the [sortOrder](http://help.syncfusion.com/api/js/ejdropdownlist#members:sortorder) property to sort out the list items. By default ascending order is followed when "sortOrder" property is not specified. 

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="data" [fields]="field" [enableSorting]="true" [sortOrder]="order"/>
                
{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	data: Array<Object> = [];
    field: Object;
    select: Array<Number>;
    order: any;
    constructor() {
        this.data = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 5",
                value: "item5"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
        }];
        this.field = { dataSource: this.data, text: "text", value: "value" };
        this.order = ej.SortOrder.Ascending;
    }
}

{% endhighlight %}

I> Virtual scrolling is not supported with Sorting.

## Cascading

This works for series of DropDownList in which items are filtered based on the previous DropDownList‘s selection. Cascading is performed based on the value field and this field should be bounded with a foreign key. To perform cascading, specify the child DropDownList’s id in [cascadeTo](http://help.syncfusion.com/api/js/ejdropdownlist#members:cascadeto) property and use delimiter (“,”) to specify more than one child DropDownList.

Configuring the data items for cascading to the series of DropDownList is demonstrated below

{% highlight html %}

<div style="float: left;">
	<span>Select Group</span>
	<input id="groupslist" type="text" ej-dropdownlist [dataSource]="groups" [fields]="groupField" [cascadeTo]="cascade"/>
</div>
<div style="float: right;">
	<span>Select Country</span>
	<input id="country" type="text" ej-dropdownlist [dataSource]="countries" [fields]="countryField" [enabled]="false" />
</div>

{% endhighlight %}

{% highlight html %}
    
import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
 groups: Array<Object>;
    countries: Array<Object>;
    cascade: string;
    groupField: Object;
    countryField: Object;
    constructor() {
        this.groups = [{
            parentId: 'a',
            text: "Group A"
            }, {
                parentId: 'b',
                text: "Group B"
            }, {
                parentId: 'c',
                text: "Group C"
            }, {
                parentId: 'd',
                text: "Group D"
            }, {
                parentId: 'e',
                text: "Group E"
            }];
        //second dropdown
        this.countries = [{
            value: 11,
            parentId: 'a',
            text: "Algeria"
            }, {
                value: 12,
                parentId: 'a',
                text: "Armenia"
            }, {
                value: 13,
                parentId: 'a',
                text: "Bangladesh"
            }, {
                value: 14,
                parentId: 'a',
                text: "Cuba"
            }, {
                value: 15,
                parentId: 'b',
                text: "Denmark"
            }, {
                value: 16,
                parentId: 'b',
                text: "Egypt"
            }, {
                value: 17,
                parentId: 'c',
                text: "Finland"
            }, {
                value: 18,
                parentId: 'c',
                text: "India"
            }, {
                value: 19,
                parentId: 'c',
                text: "Malaysia"
            }, {
                value: 20,
                parentId: 'd',
                text: "New Zealand"
            }, {
                value: 21,
                parentId: 'd',
                text: "Norway"
            }, {
                value: 22,
                parentId: 'd',
                text: "Poland"
            }, {
                value: 23,
                parentId: 'e',
                text: "Romania"
            }, {
                value: 24,
                parentId: 'e',
                text: "Singapore"
            }, {
                value: 25,
                parentId: 'e',
                text: "Thailand"
            }, {
                value: 26,
                parentId: 'e',
                text: "Ukraine"
            }];
        this.groupField = { dataSource: this.groups, text: "text", value: "parentId" };
        this.countryField = { dataSource: this.countries, text: "text", value: "parentId" };
        this.cascade = "country";
    }
}

{% endhighlight %}

![Sorting in Angular DropDownList](Functionalities_images/Functionalities_img5.png)

![Cascading in Angular DropDownList](Functionalities_images/Functionalities_img6.jpeg)

## Search

Items are searched based on the keyed in values to the textbox. There are two types of searches,

* Incremental Search
* Filter Search

### Incremental Search

Selects the item in the popup list based on the keyed in value. If the time taken to type exceeds 1000 milliseconds then filtered items will be reset based on the current input value. By default this mode of search is enabled. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use [caseSensitiveSearch](http://help.syncfusion.com/api/js/ejdropdownlist#members:casesensitivesearch) property.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="items" [fields]="field" [enableIncrementalSearch]="true" [caseSensitiveSearch]="true"/>
                
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	items: Array<Object>;
    field: Object;
    constructor() {
        this.items = [{
            text: "Adams",
            value: "emp1"
            }, {
                text: "James",
                value: "emp2"
            }, {
                text: "Maria",
                value: "emp3"
            }, {
                text: "Jessica",
                value: "emp4"
            }, {
                text: "Jenneth",
                value: "emp5"
            }];
        this.field = { dataSource: this.items, text: "text", value: "value" };
    }
}

{% endhighlight %}

![Incremental Search in Angular DropDownList](Functionalities_images/Functionalities_img8.png)

### Filter search

You can quickly locate specific item within a large data source by filtering matches with a search box. A text box appears in the popup list for searching when [enableFilterSearch](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablefiltersearch) property is enabled. By default, filtering returns the matched items list based on text in search textbox. 
You can configure the search filter by using [filterType](http://help.syncfusion.com/api/js/ejdropdownlist#members:filtertype) property. There is two types of filter options,

* Starts With 
* Contains

N> Items are filtered based on “contains” filter type by default.

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="items" [fields]="field" [enableFilterSearch]="true" [filterType]="type"/>
                
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'ej-app',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	items: Array<Object>;
    field: Object;
    type: any;
    constructor() {
        this.items = [{
            text: "Adams",
            value: "emp1"
            }, {
                text: "James",
                value: "emp2"
            }, {
                text: "Maria",
                value: "emp3"
            }, {
                text: "Jessica",
                value: "emp4"
            }, {
                text: "Jenneth",
                value: "emp5"
            }];
        this.field = { dataSource: this.items, text: "text", value: "value" };
        this.type = "startsWith";
    }
}

{% endhighlight %}

![Filter search in Angular DropDownList](Functionalities_images/Functionalities_img9.png)

## Validation

You can validate the DropDownList value on form submission by applying “validationRules” and “validationMessage” to the DropDownList. 

N> [jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js) script file should be referred for validation, for more details, refer [here](http://jqueryvalidation.org/documentation).

### Validation Rules

The validation rules help you to verify the selected text by adding validation attributes to the input element. This can be set by using [validationRules](https://help.syncfusion.com/api/js/ejdropdownlist#members:validationrules) property.

### Validation Messages 

You can set your own custom error message by using [validationMessage](https://help.syncfusion.com/api/js/ejdropdownlist#members:validationmessage) property. To display the error message, specify the corresponding annotation attribute followed by the message to display.

N> jQuery predefined error messages to that annotation attribute will be shown when this property is not defined. The below given example explain this behavior of ‘required’ attribute,

When you initialize the DropDownList widget, it creates an input hidden element which is used to store the selected items value. Hence, the validation is performed based on the value stored in this hidden element.

Required field and min value validation is demonstrated in the below given example.

{% highlight html %}

    <form id="form1">
    	<input ej-dropdownlist [dataSource]="data" [fields]="field" type="text" id="dropdown1" [validationRules]="validRule"  [validationMessage]="validMessage"  />
   
    	<input type="submit" value="Validate" />
	</form>
                
{% endhighlight %}

{% highlight javascript %}
	
 import { Component } from '@angular/core';
@Component({
  selector: 'ej-app',
  templateUrl: 'src/dropdown/dropdown.component.html',
})
export class DropDownListComponent { 
	  validRule: any;
	  validMessage: any;
      data: Array<Object> = [];
      field: Object; 
     constructor() {
	   this.data = [{
            text: "10",
            value: 10
        }, {
            text: "20",
            value: 20
        }, {
            text: "30",
            value: 30
        }, {
            text: "40",
            value: 40
        }, {
            text: "50",
            value: 50
        }];
	  $['validator'].setDefaults({
        ignore: [],// To include hidden input validation.
        errorClass: 'e-validation-error', // to get the error message on jQuery validation
        errorPlacement: function (error, element) {
            $(error).insertAfter(element.closest(".e-widget"));
        }
    });
     $['validator'].addMethod("min",
        function (value, element, params) {
            if (!/Invalid|NaN/.test(value)) {
                return parseInt(value) > params;
            }
        }, 'Must be greater than 30.');
  this.field = { dataSource: this.data, text: 'text', value: 'value' };
  	  this.validRule={
      required: true ,
      min: 30   
   };
   this.validMessage={
    required: "* Required",
    min: "Select > 30"
  
   };

   }

 }
	
{% endhighlight %}

![Validation Messages in Angular DropDownList](Functionalities_images/Functionalities_img10.jpeg)

