---
layout: post
title: Image and File browser in RichTextEditor widget
description: Configuring and working with Image and File browser in RichTextEditor  
platform: Angular2
control: RichTextEditor
documentation: ug
---
# Image and File browser

The editor allows you to manage the images and files using **FileExplorer**. The FileExplorer enables you to insert images from online source as well as local computer where you want to insert the image in your content. The Image and file browser is the ability to upload pictures and link file to the editor. 

## Insert a Image from Online Source

If you want to insert an image from online source like Google, Ping, etc., you need to enable images tool on the editor’s toolbar. By default, the images tool is open a simple dialog which allows you to inserting an image from online source.

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [(toolsList)]="toolslist" [(tools)]="tools"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    toolslist: any;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.toolslist = ["images"];
        this.tools = { images: ["image"] };
    }
}

{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img1.png)

## Insert a Image from Your Computer

Configure the imageBrowser and fileBrowser property to insert an image from your computer. You can specify the settings required by the FileExplorer for create, read, upload, and destroy the files and images from the explorer. 

{% highlight html %}

<textarea id="texteditor" ej-rte [minWidth]="150" [height]="250" [(toolsList)]="toollist" [(tools)]="tools" [imageBrowser]="imageBrowser" [fileBrowser]="fileBrowser"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    toolslist: any;
    tools: Object;
    imageBrowser: Object;
    fileBrowser: Object;
    constructor() {
        this.toolslist = ["images"];
        this.tools = { images: ["image"] };
        this.imageBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
        this.fileBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.txt, *.png, *.pdf,*.jpeg" };
    }
}

{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img2.png)

N> FileExplorer component has been implemented and integrated with the editor in Volume 1, 2015 release. For more information about FileExplorer component, see [here](http://helpjs.syncfusion.com/js/fileexplorer/overview#).

## Image Properties

You can set or modify properties of an image using the image dialog. It allows you to add links to images, apply border and additional styles. The editor provides option to specify the alternate text for an image, if the image cannot be displayed.

![](ImageandFilebrowser_images/ImageandFilebrowser_img3.png)


## Resize an Image

You can able to resize an image either manually or set the width and height in the image dialog. 

### Resize Manually

You can resize an image by manually select an image, and drag a handle until the image is the desired size. 

![](ImageandFilebrowser_images/ImageandFilebrowser_img4.png)

N> Set the default height and width of the Images which was inserted into the RTE text area in “change” event of RTE - {{'[Link](http://jsplayground.syncfusion.com/Sync_rghpsadi)'| markdownify }}

### Set Width and Height

The editor provides you to set the width and height properties to change the size of an image (rather than forcing you to set in style attributes) using [showDimensions](http://help.syncfusion.com/api/js/ejrte#members:showdimensions) property. By default, the Constrain Proportion checkbox is selected to resize an image to an exact proportion. To apply the exact width and height that you specify into the Height and Width textboxes, uncheck the Constrain Proportions checkbox.

{% highlight html %}

<textarea id="texteditor" ej-rte [value]="val" [(toolsList)]="toolslist" [(tools)]="tools" [showDimensions]="true"></textarea>

{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    val: string;
    toolslist: any;
    tools: Object;
    constructor() {
        this.val = "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
        this.toolslist = ["images"];
        this.tools = { images: ["image"] };
    }
}

{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img5.png)

## Suppression of the Image Browser

The General and Advanced tabs in the RTE Image browser can be removed by setting its corresponding display CSS property to none.

{% highlight html %}

import {Component} from '@angular/core';
import {ViewEncapsulation} from '@angular/core'; 

@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html',
  styleUrls: ['app/components/rte/rte.component.css'],
  encapsulation: ViewEncapsulation.None
})
export class RTEComponent {
}

{% endhighlight %}

Add the below styles in rte.component.css file.

{% highlight css %}

    div.e-rte-imageTab.e-tab.e-js.e-widget {
        display: none;
    }
  
{% endhighlight %}
 
Can remove the Add `NewFolder` button by using [removeToolbarItem](https://help.syncfusion.com/api/js/ejrte#methods:removetoolbaritem) property of Image Browser in the RTE create event. 

{% highlight html %}

<textarea id="texteditor" ej-rte [minWidth]="150" [height]="250" [(toolsList)]="toollist" [(tools)]="tools" [imageBrowser]="imageBrowser" [fileBrowser]="fileBrowser" (create)="onCreate($event)"></textarea>
    
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    toolslist: any;
    tools: Object;
    imageBrowser: Object;
    fileBrowser: Object;
    constructor() {
        this.toolslist = ["images"];
        this.tools = { images: ["image"] };
        this.imageBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
        this.fileBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.txt, *.png, *.pdf,*.jpeg" };
    }
    onCreate(event) {
        var obj = $("#texteditor").data("ejRTE");
        obj._explorerObj.removeToolbarItem("NewFolder");
    }
}

{% endhighlight %}
 
In RTE control, there is no direct support for the autoUpload option. But this can be achieved by enabling the autoUpload at create event of RTE.

{% highlight html %}

<textarea id="texteditor" ej-rte [minWidth]="150" [height]="250" [(toolsList)]="toollist" [(tools)]="tools" [imageBrowser]="imageBrowser" [fileBrowser]="fileBrowser" (create)="onCreate($event)"></textarea>
    
{% endhighlight %}

{% highlight html %}

import {Component} from '@angular/core';
@Component({
  selector: 'sd-home',
  templateUrl: 'app/components/rte/rte.component.html'
})
export class RTEComponent {
    toolslist: any;
    tools: Object;
    imageBrowser: Object;
    fileBrowser: Object;
    constructor() {
        this.toolslist = ["images"];
        this.tools = { images: ["image"] };
        this.imageBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
        this.fileBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations", extensionAllow: "*.txt, *.png, *.pdf,*.jpeg" };
    }
    onCreate(event) {
        var obj = $("#texteditor").data("ejRTE");
        obj._explorerObj._uploadtag.data("ejUploadbox").option("autoUpload", true);
    }
}

{% endhighlight %}