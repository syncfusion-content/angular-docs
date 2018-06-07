---
title: Getting Started for Angular PDF viewer
description: PDF viewer 
platform: Angular
control: PDF viewer
documentation: ug
keywords: ejPdfViewer, PDF viewer, js pdfviewer
---

# Getting Started

This section explains briefly about how to integrate a **PDF viewer** control in your application with **Angular**.

## Script and CSS Reference

Create a **HTML** page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}

    <!DOCTYPE html>
    <html>
    <head> 
        <link href="//cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="node_modules/core-js/client/shim.min.js"></script>
        <script src="node_modules/zone.js/dist/zone.js"></script>
        <script src="node_modules/reflect-metadata/Reflect.js"></script>
        <script src="node_modules/systemjs/dist/system.src.js"></script>
        <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
        <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
        <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
        <script src ="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.angular2.min.js"></script>
        <script src="systemjs.config.js"></script>
    </head>
    <body>
    <ej-app>Loading...</ej-app>
    </body>
    </html>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use it during deployment, as it contains all the widgets, which results in deploying large script file. Instead, you can use [CSG](http://csg.syncfusion.com/#) utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize and configure the control

The code example for defining PDF viewer control in Angular is as follows,


{% highlight html %}

    <ej-pdfviewer [(serviceUrl)]="service" id="pdfviewer" style="width:100%;min-height:600px;display:block">
    </ej-pdfviewer>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/default.component.html'
})
export class DefaultComponent {
    service: string;
    constructor() {
        this.service = 'http://js.syncfusion.com/demos/ejservices/api/PdfViewer';
    }
}
    
{% endhighlight %}


Now, the PDF viewer control is rendered with default PDF document, which used in the services.

![](getting-started_images/pdfviewer.png)
