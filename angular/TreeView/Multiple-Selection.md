---
layout: post
title: Multiple-Selection
description: Multiple-Selection support for TreeView
platform: Angular
control: TreeView
documentation: ug
---

# Multiple Selection

TreeView supports to select the multiple nodes by specifying [allowMultiSelection](https://help.syncfusion.com/api/angular/ejtreeview#members:allowmultiselection) as true. It allows you to select more than one nodes in TreeView.

 {% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='fields' [allowMultiSelection]='allowMultiSelection'></ej-treeview>

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
    public localData : any = [
          { id: 1, name: { nodeName: "Discover Music"}, hasChild: true, expanded: true },
          { id: 2, pid: 1, name: {nodeName:"Hot Singles" }},
          { id: 3, pid: 1, name: {nodeName:"Rising Artists" }},
          { id: 4, pid: 1, name:{nodeName: "Live Music" }}];

    public fields:any = { id: "id", parentId: "pid", text: "name.nodeName", hasChild: "hasChild", dataSource: this.localData, expanded: "expanded" }
    public allowMultiSelection: boolean = true;
}

</script>

 {% endhighlight %}


## Select Nodes

To select more than one nodes of TreeView, you can use [selectedNodes](https://help.syncfusion.com/api/angular/ejtreeview#members:selectednodes) property. It will select the TreeView nodes from the given indexes.

{% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='fields' [allowMultiSelection]='allowMultiSelection'></ej-treeview>

  <input type="button" ej-button id="button" value="Button" (ejclick)="treeSelect($event)" />

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
     public localData : any = [
          { id: 1, name: { nodeName: "Discover Music"}, hasChild: true, expanded: true },
          { id: 2, pid: 1, name: {nodeName:"Hot Singles" }},
          { id: 3, pid: 1, name: {nodeName:"Rising Artists" }},
          { id: 4, pid: 1, name:{nodeName: "Live Music" }}];

    public fields:any = { id: "id", parentId: "pid", text: "name.nodeName", hasChild: "hasChild", dataSource: this.localData, expanded: "expanded" }
    public allowMultiSelection: boolean = true;
    constructor() {
    }
    treeSelect(){
        // create instance for TreeView
		var treeObj = $("#treeview").data("ejTreeView");
        treeObj.option("selectedNodes", [0, 2, 3]); //select the TreeView nodes from the given indexes
    }
   
}

</script>

 {% endhighlight %}

 ## Get Selected Nodes

To get the selected Nodes of TreeView, you can use [getSelectedNodes](https://help.syncfusion.com/api/angular/ejtreeview#methods:getselectednodes) method. It returns the collections of TreeView selected nodes.

{% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='fields' [allowMultiSelection]='allowMultiSelection'></ej-treeview>

  <input type="button" ej-button id="button" value="Button" (ejclick)="getTreeSelectNodes($event)" />

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
     public localData : any = [
          { id: 1, name: { nodeName: "Discover Music"}, hasChild: true, expanded: true },
          { id: 2, pid: 1, name: {nodeName:"Hot Singles" }},
          { id: 3, pid: 1, name: {nodeName:"Rising Artists" }},
          { id: 4, pid: 1, name:{nodeName: "Live Music" }}];

    public fields:any = { id: "id", parentId: "pid", text: "name.nodeName", hasChild: "hasChild", dataSource: this.localData, expanded: "expanded" }
    public allowMultiSelection: boolean = true;
    constructor() {
    }
    getTreeSelectNodes(){
        // create instance for TreeView
		var treeObj = $("#treeview").data("ejTreeView");
        treeObj.getSelectedNodes(); //returns the collections of TreeView selected nodes
    }
   
}

</script>

 {% endhighlight %}
