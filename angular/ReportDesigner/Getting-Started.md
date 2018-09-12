---
title: Getting Started for Angular ReportDesigner
description: ReportDesigner
platform: Angular
control: ReportDesigner
documentation: ug
keywords: ejReportDesigner, ReportDesigner, js ReportDesigner
---

# Getting Started

This section explains briefly about how to create a ReportDesigner in your web application with Angular.

## Add Scripts, Styles and Control in HTML Page

Create a **HTML** page and add the scripts and CSS references mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html>
<head> 
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.reportdesigner.min.css" rel="stylesheet" />
    <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.css" rel="stylesheet" />
    <link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.css" rel="stylesheet" />
    <script src="node_modules/core-js/client/shim.min.js"></script>
    <script src="node_modules/zone.js/dist/zone.js"></script>
    <script src="node_modules/reflect-metadata/Reflect.js"></script>
    <script src="node_modules/systemjs/dist/system.src.js"></script>
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.reportdesigner.min.js" type="text/javascript"></script>
    <script src ="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.angular2.min.js"></script>
    <script src="systemjs.config.js"></script>
</head>
<body>
<ej-app>Loading...</ej-app>
</body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js` script reference has been added for demonstration purpose. It is not recommended to use it during deployment, as it contains all the widgets, which results in deploying large script file. Instead, you can use [CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize and configure the control

Add necessary HTML elements and CSS style to render ReportDesigner and set the desired `ServiceUrl` to ReportDesigner. The code example for defining ReportDesigner control in Angular is as follows,

{% highlight html %}

<ej-reportdesigner id="reportdesigner_Control" [serviceUrl] = "serviceUrl">
</ej-reportdesigner>

{% endhighlight %}

{% highlight css %}

ej-reportdesigner {
    display: block;
    height: 550px;
}

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/reportdesigner/reportdesigner.component.html',
	styleUrls: ['src/reportdesigner/reportdesigner.component.css']
})

export class ReportDesignerComponent {
    public serviceUrl: string;  

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/ReportDesigner';        
    }
}

{% endhighlight %}

## Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportDesigner** tab to view the ReportDesigner output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started-img1.png) 
