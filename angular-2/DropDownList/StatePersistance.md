---
layout: post
title: State Persistance with DropDownList widget
description: State Persistence support to DropDownList widget
platform: Angular2
control: DropDownList
documentation: ug
---

# State Persistence

DropDownList stores its model is local storage by defining the property [enablePersistence](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablepersistence).
You can sustain the below given functionalities in DropDownList by enabling persistence property,

* selected items value in the textbox 
* item’s selection state in the popup list 

Widget model will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.
The following properties are not included while maintaining DropDownList’s state in local storage to keep localStorage compact.

* Fields
* Data source
* Query 

{% highlight html %}

<input id="dropdown1" ej-dropdownlist [dataSource]="items" [fields]="fieldsvalues" [enablePersistence]="true"/>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
selector: 'sd-home',
templateUrl: 'app/components/dropdown/dropdown.component.html'
})
export class DropDownListComponent {
   	items: Array<Object>;
    fieldsvalues: Object;
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
                text: "jenneth",
                value: "emp5"
        }];
        this.fieldsvalues = { dataSource: this.items, text: "text", value: "value" };
    }
}

{% endhighlight %}