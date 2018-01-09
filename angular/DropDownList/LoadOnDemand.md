---
layout: post
title: Load on demand in DropDownList widget
description: Load on demand in DropDownList widget
platform: AngularJS
control: DropDownList
documentation: ug
keywords: loadOnDemand, DropDownList, dropdown

---
## Load On Demand

Load on demand feature allows the DropDownList items load on request from the service/database, during only on click the DropDown icon or DropDownList. This functionality helps to improve performance on control initial rendering time. Because data items load on request. 

The loadOnDemand property is used to enable or disable the load on demand functionality of the DropDownList.

{% highlight html %}

    <input id="bookSelect" ej-dropdownlist [dataSource]="data" [fields]="fields" width="50%"  [loadOnDemand]="loadOnDemand"/>
     
{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: './default.component.html'
})
export class DefaultComponent {
    data: Array<Object> = [];
    fields: Object;
    value: string;
	loadOnDemand: true;
    constructor() {
        this.data = [
            { empid: 'cr1', text: 'Dodge Avenger', value: 'Dodge Avenger' },
            { empid: 'cr2', text: 'Chrysler 200', value: 'Chrysler 200' },
            { empid: 'cr3', text: 'Ford Focus', value: 'Ford Focus' },
            { empid: 'cr4', text: 'Ford Taurus', value: 'Ford Taurus' },
            { empid: 'cr5', text: 'Dazzler', value: 'Dazzler' },
            { empid: 'cr6', text: 'Chevy Spark', value: 'Chevy Spark' },
            { empid: 'cr7', text: 'Chevy Volt', value: 'Chevy Volt' },
            { empid: 'cr8', text: 'Honda Fit', value: 'Honda Fit' },
            { empid: 'cr9', text: 'Honda Crosstour', value: 'Honda Crosstour' },
            { empid: 'cr10', text: 'Acura RL', value: 'Acura RL' },
            { empid: 'cr11', text: 'Hyundai Elantra', value: 'Hyundai Elantra' },
            { empid: 'cr12', text: 'Mazda3', value: 'Mazda3' }
        ];
        this.fields = { dataSource: this.data, text: 'text', value: 'value' };
        this.value = 'Dazzler';
		this.loadOnDemand = true;
    }
}

{% endhighlight %}

![](LoadOnDemand_images/loadondemand.png)