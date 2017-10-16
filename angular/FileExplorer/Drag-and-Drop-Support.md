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


{% highlight html %}

<ej-fileexplorer id="fileExplorer" path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
    ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
    [allowDragAndDrop]="false" style="display:block">
</ej-fileexplorer>

{% endhighlight %}