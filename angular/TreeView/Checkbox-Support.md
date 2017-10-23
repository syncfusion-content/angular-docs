---
layout: post
title: Checkboxes
description: checkboxes
platform: Angular
control: TreeView
documentation: ug
---

# Checkboxes

TreeView consists of in-build checkbox option and it can be displayed to the left of the tree node by setting the [showCheckbox](http://help.syncfusion.com/api/js/ejtreeview#members:showcheckbox) property as true. It allows you to select more than one node at a time. 

## Indeterminate Checkboxes

TreeView supports tristate checkboxes in addition with standard two state checkboxes. By default TreeView has been enabled with tristate in checkboxes. You can enable 2-state checkboxes by using [autoCheckParentNode](http://help.syncfusion.com/api/js/ejtreeview#members:autocheckparentnode) as false.

 {% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='field' [autoCheckParentNode]='autoCheckParentNode'></ej-treeview>

  {% endhighlight %}

{% highlight html %}  

<script>

import { Component } from '@angular/core';
import { TreeViewComponent } from '@syncfusion/ej2-ng-navigations';

@Component({
    selector: 'app-container',
    templateUrl: 'app/components/treeview/treeview.component.html'',
})
export class AppComponent {
    constructor() {
    }
    //define the data source
    public continents:Object[] = [
        {
        code: 'AF', name: 'Africa', countries: [
            { code: 'NGA', name: 'Nigeria' },
            { code: 'EGY', name: 'Egypt' },
            { code: 'ZAF', name: 'South Africa' }
        ]
    },
    {
        code: 'AS', name: 'Asia', expanded: true, countries: [
            { code: 'CHN', name: 'China' },
            { code: 'IND', name: 'India', selected: true },
            { code: 'JPN', name: 'Japan' }
        ]
    },
    {
        code: 'EU', name: 'Europe', countries: [
            { code: 'DNK', name: 'Denmark' },
            { code: 'FIN', name: 'Finland' },
            { code: 'AUT', name: 'Austria' }
        ]
    },
    {
        code: 'NA', name: 'North America', countries: [
            { code: 'USA', name: 'United States of America' },
            { code: 'CUB', name: 'Cuba' },
            { code: 'MEX', name: 'Mexico' }
        ]
    },
    {
        code: 'SA', name: 'South America', countries: [
            { code: 'BRA', name: 'Brazil' },
            { code: 'COL', name: 'Colombia' },
            { code: 'ARG', name: 'Argentina' }
        ]
    },
    {
        code: 'OC', name: 'Oceania', countries: [
            { code: 'AUS', name: 'Australia' },
            { code: 'NZL', name: 'New Zealand' },
            { code: 'WSM', name: 'Samoa' }
        ]
    },
    {
        code: 'AN', name: 'Antarctica', countries: [
            { code: 'BVT', name: 'Bouvet Island' },
            { code: 'ATF', name: 'French Southern Lands' }
        ]
    }
    ];
    
    public field:Object = { dataSource: this.continents, id: 'code', text: 'name', child: 'countries' };

    public autoCheckParentNode: boolean = false;
}

</script>

 {% endhighlight %}


## Auto Checkable

By default checkbox state of child nodes depends up on parent node checkbox state and also parent node state gets updated based on child nodes state. You can turn off this option by setting [autoCheck](http://help.syncfusion.com/api/js/ejtreeview#members:autocheck) as false to make independent parent and child nodes checkboxes.


 {% highlight html %} 
 
 <ej-treeview id='treeView' [fields]='field' [autoCheck]='autocheck'></ej-treeview>

  {% endhighlight %}



