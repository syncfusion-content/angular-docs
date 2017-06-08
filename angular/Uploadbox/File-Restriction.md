---
layout: post
title: Restricting-uploading-files-based-on-its-extension
description: restricting uploading files based on its extension
platform: Angular
control: Uploadbox
documentation: ug
---

# Restricting uploading files based on its extension

## Allow Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using **browse** button. The [extensionsAllow](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsallow) property allows upload of the selected extensions only. You can give multiple extensions by using comma (,).  The data type is **string**.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following code explains you for the configuration of [extensionsAllow](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsallow) property in **Uploadbox**. 

{% highlight html %}

<div style="width:100px;height:35px;">

<ej-uploadbox id="UploadDefault" [saveUrl]="saveURL" [removeUrl]="removeURL" [extensionsAllow]="extensions"></ej-uploadbox>

</div>

{% endhighlight %}

{% highlight html %}

 import {Component} from '@angular/core';
    @Component({
    selector: 'ej-app',
        templateUrl: 'app/components/uploadbox/uploadbox.component.html'
    })
    export class UploadBoxComponent {
        saveURL:string;
        removeURL:string;
        extensions: string;
        constructor() {
        this.saveURL = '../saveFiles.ashx';
        this.saveURL = '../removeFiles.ashx';
        this.extensions=".docx, .pdf";
        }
    }

{% endhighlight %}

Configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively. 

## Deny Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using **browse** button. The [extensionsDeny](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsdeny) property denies upload of the selected extensions. You can give multiple extensions by using comma (,).  The data type is **string**.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following code helps you for the configuration of [extensionsDeny](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsdeny) property in **Uploadbox**

{% highlight html %}

<div style="width:100px;height:35px;">

<ej-uploadbox id="UploadDefault" [saveUrl]="saveURL" [removeUrl]="removeURL" [extensionsDeny]="extensions"></ej-uploadbox>

</div>

{% endhighlight %}

{% highlight html %}

 import {Component} from '@angular/core';
    @Component({
    selector: 'ej-app',
        templateUrl: 'app/components/uploadbox/uploadbox.component.html'
    })
    export class UploadBoxComponent {
        saveURL:string;
        removeURL:string;
        extensions: string;
        constructor() {
        this.saveURL = '../saveFiles.ashx';
        this.saveURL = '../removeFiles.ashx';
        this.extensions=".docx, .pdf";
        }
    }

{% endhighlight %}

Configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively.