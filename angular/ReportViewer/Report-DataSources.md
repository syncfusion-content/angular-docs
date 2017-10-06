---
title: Report DataSources
description: report datasources
platform: Angular
control: ReportViewer
documentation: ug
keywords: Report DataSources, RDLC reports
---

# Report DataSources

The ReportViewer has support to add data sources to ReportViewer for RDLC reports at runtime. You can add SQL Server, Oracle, MS Azure, XML, Business Object, and SQL Server Compact DataSources to ReportViewer. The ReportViewer has `dataSources` property that is the list of ReportDataSource type to add collection of DataSources to it. You can add DataSources either through ReportViewer model when creating ReportViewer control or through Web API.

The following code example illustrates how to add DataSource at control creation.

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Local" [reportPath] = "reportPath">
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
	public reportData: any;

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/demos/ejServices/api/ReportViewer';        
        this.reportPath = 'AreaCharts.rdlc"';
		this.reportData = [{
      value: [
        { SalesPersonID: 281, FullName: 'Ito', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 0, Y2003: 28000, Y2004: 3018725 },
        { SalesPersonID: 282, FullName: 'Saraiva', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 25000, Y2003: 14000, Y2004: 3189356 },
        { SalesPersonID: 283, FullName: 'Cambell', Title: 'Sales Representative', SalesTerritory: 'North West', Y2002: 12000, Y2003: 13000, Y2004: 1930885 }       
      ],
      name: 'AdventureWorksXMLDataSet'
    }];
    }
}

{% endhighlight %}

The following code example illustrates how to add DataSource in Web API.

{% highlight c# %}

public class ReportsController : ApiController, IReportController
{
    /// <summary>
    /// Report loaded method that is triggered when report and sub report are loaded.
    /// </summary>
    /// <param name="reportOptions">The ReportViewer options.</param>
    public void OnReportLoaded(ReportViewerOptions reportOptions)
    {
        //Adds data sources to report model.
        reportOptions.ReportModel.DataSources.Clear();
        SalesDetail salesList = new SalesDetail();
        reportOptions.ReportModel.DataSources.Add(new ReportDataSource { Name = "AdventureWorksXMLDataSet", Value = salesList.GetData() });            
    }
}

public class SalesDetail
{
       public double SalesPersonID { get; set; }
       public string FullName { get; set; }
       public string Title { get; set; }
       public string SalesTerritory { get; set; }
       public double Y2002 { get; set; }
       public double Y2003 { get; set; }
       public double Y2004 { get; set; }

       public IList GetData()
       {
           List<SalesDetail> dataList = new List<SalesDetail>();
           SalesDetail data = null;
           data = new SalesDetail() { SalesPersonID = 281, FullName = "Ito", Title = "Sales Representative", SalesTerritory = "South West", Y2002 = 0, Y2003 = 28000, Y2004 = 3018725 };
           dataList.Add(data);
           data = new SalesDetail() { SalesPersonID = 282, FullName = "Saraiva", Title = "Sales Representative", SalesTerritory = "Canada", Y2002 = 25000, Y2003 = 14000, Y2004 = 3189356 };
           dataList.Add(data);
           data = new SalesDetail() { SalesPersonID = 283, FullName = "Cambell", Title = "Sales Representative", SalesTerritory = "North West", Y2002 = 12000, Y2003 = 13000, Y2004 = 1930885 };
           dataList.Add(data);
           return dataList;
       }
}
{% endhighlight %}

## DataSource Credentials

The DataSource credentials can be given at Web API Controller to connect data source.

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



