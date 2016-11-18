---
title: Getting Started for Angular 2 ReportViewer
description: ReportViewer
platform: Angular2
control: ReportViewer
documentation: ug
keywords: ejReportViewer, ReportViewer, js ReportViewer
---

# Getting Started

This section explains briefly about how to integrate a **ReportViewer** control in your application with **Angular 2**.

## Create your first ReportViewer in Angular2

### Add Scripts, Styles and Control in HTML Page

Create a **HTML** page and add the scripts and CSS references in the order mentioned in the following code example.

{% highlight html %}

    <!DOCTYPE html>
    <html>
    <head> 
        <link href="http://cdn.syncfusion.com/14.3.0.52/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
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

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use it during deployment, as it contains all the widgets, which results in deploying large script file. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize and configure the control

Set the desired `reportPath` and `reportServiceUrl` to ReportViewer. The code example for defining ReportViewer control in Angular2 is as follows,

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportserviceurl]="serviceUrl" [processingmode]="Remote"  [reportpath]="reportPath">
</ej-reportviewer>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/tGroupingAgg.component.html'   
})

export class GroupingAggComponent {
    public serviceUrl: string;    
    public reportPath: string;

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/RDLReport';      
        this.reportPath = 'GroupingAgg.rdl';
    }
}
    
{% endhighlight %}

N> Default RDL Report will be rendered, which is used in the online service. You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate).

### Run the Application

Run the sample application and you can see the ReportViewer on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}

## Load SSRS Server Reports

ReportViewer supports to load RDL/RDLC files from SSRS Server. The following steps help you to load reports from SSRS Server.

1. Set the `reportPath` from SSRS and SSRS `reportServerUrl` in the ReportViewer properties.

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportserviceurl]="serviceUrl" [processingmode]="Remote" [reportserverurl]="serverUrl" [reportpath]="reportPath">
</ej-reportviewer>

{% endhighlight %}

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/components/reportviewer/territorysales.component.html'    
})

export class TerritorySalesComponent {
    public serviceUrl: string;
    public serverUrl: string;
    public reportPath: string;

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/SSRSReport';
        this.serverUrl = 'http://mvc.syncfusion.com/reportserver';
        this.reportPath = '/SSRSSamples2/Territory Sales new';
    }
}
    
{% endhighlight %}

N> The credential information for Report Server is provided in online service. 

2. Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![](Getting-Started_images/Getting-Started_img2.png) 
   
   Report from SSRS
   {:.caption}

