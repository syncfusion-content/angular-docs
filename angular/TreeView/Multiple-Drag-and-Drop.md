---
layout: post
title: Multiple-Drag-and-Drop
description: multiple drag and drop
platform: Angular
control: TreeView
documentation: ug
---


# Drag and Drop Multiple Nodes

TreeView supports to drag and drop multiple nodes by specifying [allowMultiSelection](http://help.syncfusion.com/api/js/ejtreeview#members:allowmultiselection) as true along with [allowDragAndDrop](https://help.syncfusion.com/api/js/ejtreeview#members:allowdraganddrop) as true. It allows you to drag and drop multiple nodes in TreeView.

{% highlight html %}

 <ej-treeview id="dragdrop" [fields]='field' [allowMultiSelection]='allowMultiSelection' [allowDragAndDrop]='allowDragAndDrop'></ej-treeview>

{% endhighlight %}

{% highlight html %}

<script>

import { Component, Inject } from '@angular/core';

@Component({
    selector: 'control-content',
    templateUrl: 'app/components/treeview/dragdrop.component.html'
})
export class DragdropTreeViewComponent {

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
    public allowMultiSelection:boolean = true;
    public allowDragAndDrop:boolean = true;
}

</script>

For more details about multiple drag and drop in TreeView, refer the sample [here](http://jsplayground.syncfusion.com/Sync_1mo2awgk).

