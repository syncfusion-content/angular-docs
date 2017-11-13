---
title: Report Parameters
description: report parameters
platform: Angular
control: ReportViewer
documentation: ug
keywords: Report Parameters,ReportViewer parameters 
---

# Report Parameters

The ReportViewer has support to add report Parameters to ReportViewer at runtime. The ReportViewer has `parameters` property that is the list of ReportParameter type to add collection of report parameters to it. You can add report parameters either through ReportViewer model when creating ReportViewer control or through Web API.

The following code example illustrates how to add ReportParameter at control creation.

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Local" [reportPath] = "reportPath" [parameters] = "parameters">
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
	public parameters: any;

    constructor() {	
		
		this.serviceUrl = 'http://js.syncfusion.com/demos/ejServices/api/ReportViewer';        
        this.reportPath = '~/InvoiceTemplate';  
		this.parameters = [{
			name: 'InvoiceID', 
			labels: ['InvoiceID'], 
			values: [10250], 
			nullable: false 
			}];
    }	
}

{% endhighlight %}

The following code example illustrates how to add ReportParameter in Web API.

{% highlight c# %}

public class ReportsController : ApiController, IReportController
{
    /// <summary>
    /// Report Initialization method that is triggered when report begins to be processed.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnInitReportOptions(ReportViewerOptions reportOptions)
    {
        List<ReportParameter> parameters = new List<ReportParameter>();
        parameters.Add(new ReportParameter() { Name = "InvoiceID", Labels = new List<string>() { "InvoiceID" }, Values = new List<string>() { "10250" } });
        reportOptions.ReportModel.Parameters = parameters;
    }        
}

{% endhighlight %}



