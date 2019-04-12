---
layout: post
title: Grouping in Syncfusion ComboBox widget
description: Describes about the grouping in ComboBox widget
platform: Angular
control: ComboBox
documentation: ug
keywords: ComboBox, combobox, Grouping
---

# Grouping

The ComboBox supports wrapping nested elements into a group based on different categories. The category of each list item can be mapped through the [groupBy](https://help.syncfusion.com/api/js/ejcombobox#members:fields-groupby) &nbsp;field in
the data table. The group header is displayed both as inline and fixed headers. The fixed group header content is updated dynamically on scrolling the popup list with its category value.

In the following sample, vegetables are grouped according on its category using `groupBy` field.

{% highlight html %}
	
	<input id="List" ej-combobox [dataSource]="data" [fields]="fields"  [placeholder]="placeholder" />
			
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
                this.data = [{ vegetable: 'Cabbage', category: 'Leafy and Salad' }, { vegetable: 'Spinach', category: 'Leafy and Salad' },
	                         { vegetable: 'Wheatgrass', category: 'Leafy and Salad' }, { vegetable: 'Yarrow', category: 'Leafy and Salad' },
                             { vegetable: 'Chickpea', category: 'Beans' }, { vegetable: 'Green bean', category: 'Beans' },
	                         { vegetable: 'Horse gram', category: 'Beans' }, { vegetable: 'Garlic', category: 'Bulb and Stem' },
	                         { vegetable: 'Nopal', category: 'Bulb and Stem' }, { vegetable: 'Onion', category: 'Bulb and Stem' }];
               this.fields = { groupBy: 'category', text: 'vegetable',value: 'vegetable'};
			   this.placeholder = 'Select a Vegetable';
              }
            }		
	
{% endhighlight %}