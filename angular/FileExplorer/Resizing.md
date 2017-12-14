---
layout: post
title: Resizing
description: resize support
platform: Angular
control: File Explorer
documentation: ug
---

# Resizing 

The FileExplorer has the resize support through the resize handle which appears at right-bottom corner of footer. By clicking the resize handle the user can resize the FileExplorer through the UI. While resizing the dimension of the FileExplorer is automatically adjusted.

The resize behavior can be enabled through the `enableResize` property. 

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
   [enableResize]="true" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

## Responsiveness

By enabling the `isResponsive` property, you can make the FileExplorer as responsive. While resizing the FileExplorer component, the inner content and toolbar items are automatically adjusted to equalize the size. The toolbar items are displayed within Dropdown on enabling the responsive. Otherwise it floated to the next line to equalize the space. 

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
   [enableResize]="true" [isResponsive]="true" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

## Restriction on Resize

You can restrict the dimension of the FileExplorer by setting the `minHeight`, `maxHeight` and `minWidth`, `maxWidth` properties while resizing the FileExplorer. 

{% highlight html %}

<ej-fileexplorer id="fileExplorer" 
   path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
   ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
   [enableResize]="true" [isResponsive]="true" minHeight="200px" maxHeight="400px"  
   minWidth="300px" maxWidth= "1200px" maxWidth= "1200px" style="display:block">
</ej-fileexplorer>

{% endhighlight %}