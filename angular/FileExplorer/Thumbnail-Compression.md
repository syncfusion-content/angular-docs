---
title: Thumbnail Compression
description: Thumbnail image size reduction option in FileExplorer
platform: Angular
control: FileExplorer
documentation: UG
keywords: Thumbnail compression, image compression, reduce image size
---

# Thumbnail Compression

The “FileExplorer” allows thumbnail images to be compressed on the server side and loaded into the “FileExplorer” layout to improve performance when working with large size images.

You can enable this option using “**enableThumbnailCompress**” API of FileExplorer. Refer following code block that will be helpful to you.

{% highlight html %}

<ej-fileexplorer id="fileExplorer" path= "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/"
    ajaxAction="http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations" 
    width="100%" [layout]="tile" [enableThumbnailCompress]="true" style="display:block">
</ej-fileexplorer>

{% endhighlight %}

N> In server side, don’t forget to add “[GetImage](https://help.syncfusion.com/cr/cref_files/aspnetmvc/dociohelper/Syncfusion.EJ~Syncfusion.JavaScript.FileExplorerOperations~GetImage.html#)” handling operation that helps to reduce the image size before loading.