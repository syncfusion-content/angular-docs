---
layout: post
title: Asynchronous-Upload
description: asynchronous upload
platform: Angular
control: Uploadbox
documentation: ug
---

# Asynchronous Upload

This feature allows you to upload and remove files **asynchronously**. To achieve this, set the [asyncUpload](https://help.syncfusion.com/api/js/ejuploadbox#members:asyncupload) property to ‘**true**’. The default value of [asyncUpload](https://help.syncfusion.com/api/js/ejuploadbox#members:asyncupload) property is ‘**true**’. The data type is **Boolean.**

The following code helps to upload the file **asynchronously**.

{% highlight html %}

<div style="width:100px;height:35px;">

<ej-uploadbox id="UploadDefault" [saveUrl]="saveURL" [removeUrl]="removeURL" [asyncUpload]="true"></ej-uploadbox>

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
        constructor() {
        this.saveURL = '../saveFiles.ashx';
        this.saveURL = '../removeFiles.ashx';
        }
    }

{% endhighlight %}

Configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively.