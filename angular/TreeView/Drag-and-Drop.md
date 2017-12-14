---
layout: post
title: Drag-and-Drop
description: drag and drop
platform: Angular
control: TreeView
documentation: ug
---

# Drag and drop 

To perform drag and drop operation in TreeView, specify [allowDragAndDrop](http://help.syncfusion.com/api/js/ejtreeview#members:allowdraganddrop) as true. It allows you to drag and drop node in all level of same TreeView.


 {% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='field' [allowDragAndDrop]='allowDragAndDrop'>
 </ej-treeview>

  {% endhighlight %}

N> TreeView provides much easier option to drop the dragged nodes at any levels by indicator lines with icons.

## Position Indicators

TreeView provides much easier option to drop the dragged nodes at any levels by indicator lines with icons such as line, plus/minus and restrict icons while dragging and dropping the nodes. It represents exact position where the node to be dropped as sibling or child. Refer below screen shot of position indicator.

<table>
<tr>
<th>
Indicators</th><th>
description</th></tr>
<tr>
<td>
Plus icon<br/><br/></td><td>
represents the dragged node to be added as child of targeted node<br/><br/></td></tr>
<tr>
<td>
Minus with restrict icon<br/><br/></td><td>
represents the dragged node not to be dropped at the hovered region<br/><br/></td></tr>
<tr>
<td>
In between icon<br/><br/></td><td>
represents the dragged node to be dropped in between the nodes as siblings<br/><br/></td></tr>
</table>

## Restriction

You can restrict the dragged nodes to be dropped at siblings or children’s level by using [allowDropSibling](http://help.syncfusion.com/api/js/ejtreeview#members:allowdropsibling) and [allowDropChild](http://help.syncfusion.com/api/js/ejtreeview#members:allowdropchild) property.

 {% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='field' [allowDragAndDrop]='allowDragAndDrop' 
   [allowDropSibling]='allowDropSibling'>
 </ej-treeview>

  {% endhighlight %}

## Drag and Drop between Trees

You can drag and drop tree nodes between two TreeView by setting [allowDragAndDrop](http://help.syncfusion.com/api/js/ejtreeview#members:allowdraganddrop) as true along with [allowDragAndDropAcrossControl](http://help.syncfusion.com/api/js/ejtreeview#members:allowdraganddropacrosscontrol) as true. 


{% highlight html %} 
 
 <ej-treeview id='treeview' [fields]='field' [allowDragAndDrop]='allowDragAndDrop' 
   [allowDragAndDropAccessControl]='allowDragAndDropAccessControl' 
   [allowDropSibling]='allowDropSibling' 
   [allowDropChild]='allowDropChild' >
 </ej-treeview>

{% endhighlight %}

For more details about drag and drop between TreeView, refer the sample [here](http://jsplayground.syncfusion.com/40z0fek2#). 

