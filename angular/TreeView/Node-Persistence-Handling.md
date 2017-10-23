---
layout: post
title: State-Persistence
description: State Persistence
platform: Angular
control: TreeView
documentation: ug
---

# State Persistence

TreeView state can be persisted by using [enablePersistence](http://help.syncfusion.com/api/js/ejtreeview#members:enablepersistence). In which entire modal has been persisted excluding data source in order to maintain performance. 

The model values of below are maintained through Id basis of tree node.

* **selected**
* **checked**
* **expanded/collapsed state**

N>  "Ul-li" template option, state has been persisted by index.

TreeView stores its model in local storage / cookies of browser before page refreshes and reinitialized with their stored model after refresh.

% highlight html %}

 <ej-treeview id="dragdrop" [fields]='field' [enablePersistence]='enablePersistence'></ej-treeview>

{% endhighlight %}

{% highlight html %}

<script>

import { Component, Inject } from '@angular/core';

@Component({
    selector: 'control-content',
    templateUrl: 'app/components/treeview/enablePersistence.component.html'
})
export class enablePersistenceTreeViewComponent {

   public hierarchicalData: Object[] = [
        {
            id: 1, name: 'ASP.NET MVC Team', expanded: true,
            child: [
                { id: 2, parentId: 1, name: 'Smith', isSelected: true },
                { id: 3, parentId: 1, name: 'Johnson', isSelected: true },
                { id: 4, parentId: 1, name: 'Anderson' },
            ]
        },
        {
            id: 5, name: 'Windows Team',
            child: [
                { id: 6, parentId: 5, name: 'Clark' },
                { id: 7, parentId: 5, name: 'Wright' },
                { id: 8, parentId: 5, name: 'Lopez' },
            ]
        },
        {
            id: 9, name: 'Web Team',
            child: [
                { id: 11, parentId: 9, name: 'Joshua' },
                { id: 12, parentId: 9, name: 'Matthew' },
                { id: 13, parentId: 9, name: 'David' },
            ]
        },
        {
            id: 14, name: 'Build Team',
            child: [
                { id: 15, parentId: 14, name: 'Ryan' },
                { id: 16, parentId: 14, name: 'Justin' },
                { id: 17, parentId: 14, name: 'Robert' },
            ]
        },
        {
            id: 18, name: 'WPF Team',
            child: [
                { id: 19, parentId: 18, name: 'Brown' },
                { id: 20, parentId: 18, name: 'Johnson' },
                { id: 21, parentId: 18, name: 'Miller' },
            ]
        }
    ];
    public field:Object ={ dataSource: this.hierarchicalData, id: 'id', text: 'name', child: 'child', selected: 'isSelected' };
    public enablePersistence:boolean = true;
}
