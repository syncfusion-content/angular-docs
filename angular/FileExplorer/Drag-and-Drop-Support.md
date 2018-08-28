---
title: Drag and Drop Support
description: Drag and Drop option in FileExplorer
platform: Angular
control: FileExplorer
documentation: UG
keywords: Drag and drop option
---

# Drag and Drop Support

The FileExplorer allows files to be moved from one folder to another by using drag and drop. It also supports uploading a file by dragging it from Windows Explorer to a folder in the FileExplorer control.

You can enable or disable this support by using “**allowDragAndDrop**” API of FileExplorer.
The [dragStart](https://help.syncfusion.com/api/angular/ejfileexplorer#events:dragstart), [drag](https://help.syncfusion.com/api/angular/ejfileexplorer#events:drag), [dragStop](https://help.syncfusion.com/api/angular/ejfileexplorer#events:dragstop) and [drop](https://help.syncfusion.com/api/angular/ejfileexplorer#events:drop) events occur in the mentioned order when a drag and drop operation is performed.


{% highlight html %}

<ej-fileexplorer id="fileExplorer" path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
    ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
    [allowDragAndDrop]="false" style="display:block">
</ej-fileexplorer>

{% endhighlight %}