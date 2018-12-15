---
layout: post
title: Sorting
description: sorting support
platform: Angular
control: ListBox
documentation: ug
---

# Sorting

We can change ListBox items rendering order either as ascending or descending, by using "sortOrder" property. By default sortOrder will be "None". Please use code as like in below,

{% highlight html %} 

    <div class="frame">
        <div class="ctrllabel">Select a car</div>
      <ej-listbox id="defaultlistbox" style="display:block;" width="100%" [dataSource]="data" width="100%" [fields]="fieldList" [sortOrder]="sorting"></ej-listbox>
    </div>

{% endhighlight %}

 Please use the below JavaScript code to get sorted items in listbox.

  {% highlight ts %}

    export class DefaultComponent {
    data: Array<{ empid: string, text: string, value: string }>;
    fieldList: Object;
    value: string;
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
        this.fieldList = { dataSource: this.data, text: 'text', value: 'value' };
        this.sorting=ej.SortOrder.Descending;
    }
}

  {% endhighlight %}

![](Sorting-Images\img1.png)