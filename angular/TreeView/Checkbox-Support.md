---
layout: post
title: Checkbox for Syncfusion TreeView
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
 
<ej-treeview id='treeview' [fields]='field' [showCheckbox]='true' [autoCheckParentNode]='autoCheckParentNode'>
</ej-treeview>

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
   public Data:Object[] = [
        { id: 1, name: 'Discover Music', hasChild: true, expanded: true },
        { id: 2, parent: 1, name: 'Hot Singles', selected: true },
        { id: 3, parent: 1, name: 'Rising Artists', selected: true },
        { id: 4, parent: 1, name: 'Live Music', selected: true },
        { id: 6, parent: 1, name: 'Best of 2013 So Far' },
        { id: 7, name: 'Sales and Events', hasChild: true, expanded: true },
        { id: 8, parent: 7, name: '100 Albums - $5 Each' },
        { id: 9, parent: 7, name: 'Hip-Hop and R&B Sale' },
        { id: 10, parent: 7, name: 'CD Deals' },
        { id: 11, name: 'Categories', hasChild: true },
        { id: 12, parent: 11, name: 'Songs' },
        { id: 13, parent: 11, name: 'Bestselling Albums' },
        { id: 14, parent: 11, name: 'New Releases' },
        { id: 15, parent: 11, name: 'Bestselling Songs' },
        { id: 16, name: 'MP3 Albums', hasChild: true },
        { id: 17, parent: 16, name: 'Rock' },
        { id: 18, parent: 16, name: 'Gospel' },
        { id: 19, parent: 16, name: 'Latin Music' },
        { id: 20, parent: 16, name: 'Jazz' },
        { id: 21, name: 'More in Music', hasChild: true },
        { id: 22, parent: 21, name: 'Music Trade-In' },
        { id: 23, parent: 21, name: 'Redeem a Gift Card' },
        { id: 24, parent: 21, name: 'Band T-Shirts' },
        { id: 25, parent: 21, name: 'Mobile MVC' }];
    
    public field:Object = { id: 'id', parentId: 'parent', text: 'name', hasChild: 'hasChild', dataSource: this.Data, expanded: 'expanded', selected: 'selected'};
    public autoCheckParentNode: boolean = false;
}

</script>

 {% endhighlight %}


## Auto Checkable

By default checkbox state of child nodes depends up on parent node checkbox state and also parent node state gets updated based on child nodes state. You can turn off this option by setting [autoCheck](http://help.syncfusion.com/api/js/ejtreeview#members:autocheck) as false to make independent parent and child nodes checkboxes.


 {% highlight html %} 
 
 <ej-treeview id='treeView' [fields]='field' [autoCheck]='false'></ej-treeview>

  {% endhighlight %}



