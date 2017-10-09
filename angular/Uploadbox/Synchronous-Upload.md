---
layout: post
title: Synchronous-Upload
description: synchronous upload 
platform: angular
control: Uploadbox
documentation: ug
api: /angular/ejuploadbox
---

# Synchronous Upload 

This features allow you to upload and remove the files **synchronously**.When multiple files are chosen in Synchronous upload,all files will be uploaded only on form submission.Multitasking is not possible here. To achieve this, set the **asyncUpload** property to ‘**false**’. The data type is **Boolean.**

N> By default, Uploadbox widget works with asynchronous upload option only.



The following steps guide you in uploading the file **synchronously**.

In the **HTML** page, create a form with action and post method and then add the **&lt;div&gt;** element into the form to configure the **Uploadbox** element.

{% highlight html %}

<div id="Uploadbox"></div>

{% endhighlight %}

{% highlight js %}

    // Initialize the control in JavaScript.
    $(function () {
        //Declaration.
        $("#Uploadbox").ejUploadbox({
            saveUrl: "saveFiles.ashx",
            removeUrl: "removeFiles.ashx",
            asyncUpload: false
        });
    });

{% endhighlight %}

For **JS**, configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively. 

Once the form is submitted by using **submit** button, it triggers the **saveFiles.ashx** handler. In the handler, save the files as usual.

The following screenshot displays the output.



![](/js/UploadBox/Synchronous-Upload_images/Synchronous-Upload_img1.png) 

