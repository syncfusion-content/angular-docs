---
layout: post
title: Multiple Selection
description: FileExplorer allows the user to select multiple files
platform: Angular
control: File Explorer
documentation: ug
---


# Multiple Selection

The FileExplorer allows the user to select multiple files by enabling the `allowMultiSelection` property. The multiple selection can be done by pressing the **Ctrl** key or **Shift** key. You can select all the files in the directory by pressing “**Ctrl + A**”. The multiple selection is useful on copy pasting multiple files, deleting multiple files and downloading multiple files.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
    ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
    [allowMultiSelection]="true" style="display:block">
</ej-fileexplorer>

{% endhighlight %}