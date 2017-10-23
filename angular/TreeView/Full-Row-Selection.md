---
layout: post
title: Full-Row-Selection
description: full row selection
platform: Angular
control: TreeView
documentation: ug
---


# Full Row Selection

The TreeView control provides the option to highlight a full row of tree view nodes. When [fullRowSelect](https://help.syncfusion.com/api/js/ejtreeview#members:fullrowselect) is **true**, a selection highlights the entire width of the tree view, display instead of the width of just the tree node text. It makes selection easier.


{% highlight html %} 
 
 <ej-treeview id='treeView' [fields]='field' [spriteCssClass]='spriteCssClass' [imageUrl]='imageUrl' [htmlAttribute]='htmlAttribute' [linkAttribute]='linkAttribute' [imageAttribute]='imageAttribute' [fullRowSelect]='fullRowSelect'></ej-treeview>

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

{ id: 1, text: "Item 1", expanded: true, nodeProperty: { class: "textblue", value: "Item 1" } },

{ id: 2, text: "Item 2", linkProperty: { class: "textunderline", href: "http://www.syncfusion.com", target: "_blank" } },

{ id: 3, text: "Item 3", selected: true, spriteImage: "mailicon sprite-calendar" },

{ id: 4, text: "Item 4", checked: true, imageProperty: { width: 20, height: 20 }, imageUrl: "http://cdn.syncfusion.com/13.3.0.7/js/web/flat-azure/images/ajax-loader.gif" },

{ id: 5, parent: 1, text: "Item 1.1" },

{ id: 6, parent: 1, text: "Item 1.2" },

{ id: 7, parent: 1, text: "Item 1.3" },

{ id: 8, parent: 3, text: "Item 3.1" },

{ id: 9, parent: 3, text: "Item 3.2" },

{ id: 10, parent: 5, text: "Item 1.1.1" }

];
    public field:Object = { dataSource: this.continents, id: 'id', parentid:'parent' text: 'text', selected:'selected'};
	public spriteCssClass: string ='spriteImage';
	public imageUrl: string ='imageurl';
	public htmlAttribute: string ='nodeProperty';
	public linkAttribute: string ='linkProperty';
	public imageAttribute: string='imageProperty';
	public fullRowSelect: boolean= true;
}

</script>

 {% endhighlight %}


For more details about full row selection in TreeView, refer the sample [here](http://js.syncfusion.com/demos/web/#!/bootstrap/treeview/fullrowselect).
