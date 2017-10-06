---
title: SSRS Configuration
description: ssrs configuration
platform: Angular
control: ReportViewer
documentation: ug
keywords: SSRS, SSRS server, Network Credentials, DataSource Credentials
---

# SSRS Configuration

The ReportViewer has support to load RDL/RDLC reports from SSRS server. You have to set your SSRS server URL to ReportViewer’s `reportServerUrl` property and set the relative path of RDL/RDLC file in SSRS to ReportViewer’s `reportPath` property. 

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Remote" [reportServerUrl] = "serverUrl" [reportPath] = "reportPath">
</ej-reportviewer>

{% endhighlight %}

{% highlight ts %}
import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/reportviewer/reportviewer.component.html',	
	styleUrls: ['src/reportviewer/reportviewer.component.css']
})

export class ReportViewerComponent {
    public serviceUrl: string;    
    public reportPath: string;
	public serverUrl: string;		

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/demos/ejServices/api/ReportViewer'; 
        this.serverUrl = 'http://mvc.syncfusion.com/reportserver'; 		
        this.reportPath = '/SSRSSamples2/Territory Sales new';		
    }
}

{% endhighlight %}

## Network Credentials for SSRS

The Network credentials can be given at Web API Controller to connect the SSRS server.

{% highlight c# %}
/// <summary>
/// Report Initialization method that is triggered when report begins to process.
/// </summary>
/// <param name="reportOptions">The ReportViewer options.</param>
public void OnInitReportOptions(ReportViewerOptions reportOptions) 
{
    //Adds SSRS Server and Database Credentials here.
    reportOptions.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("ssrs", "RDLReport1");
    reportOptions.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("AdventureWorks", "ssrs1", "RDLReport1"));
}
{% endhighlight %}

N> DataSource credentials must be added to the ReportViewer for Shared DataSources that do not have credentials in the connection string and used in the SSRS Reports.



