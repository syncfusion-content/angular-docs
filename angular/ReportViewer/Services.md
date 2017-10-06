---
title: Service reference for ejReportViewer widget
description: Services used in Essential JavaScript ReportViewer.
platform: Angular
control: ReportViewer
documentation: api
keywords: ejReportViewer, Services, Essential JS ReportViewer, ReportViewer
---
## ReportViewer services

### RDL Report Services

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/PostReportAction 

### Parameter

### ReportLoad

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to load the report
</td>
</tr>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
String
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportPath
</td>
<td class="datatype">
String 
</td>
<td class="description">
Report path of the report 
</td>
</tr>
<tr>
<td class="parameter name">
reportServerUrl
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the Report Server url to accessing the report
</td>
</tr>
<tr>
<td class="parameter name">
processingMode
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the processing mode of the report  
</td>
</tr>
</tbody>
</table>

### GetDatasourceCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the Datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
<tr>
<td class="parameter name">
parameters
</td>
<td class="datatype">
String 
</td>
<td class="description">
Specify the parameter collections 
</td>
</tr>
</tbody>
</table>

### ValidateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to validate the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### UpdateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### GetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the parameters
</td>
</tr>
</tbody>
</table>

### SetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to set the parameters
</td>
</tr>
<tr>
<td class="parameter name">
parameters 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to set the parameters
</td>
</tr>
</tbody>
</table>

### UpdateParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the parameters
</td>
</tr>
<tr>
<td class="parameter name">
update param 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to update the parameters
</td>
</tr>
</tbody>
</table>

### UpdateDataSource

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource
</td>
</tr>
</tbody>
</table>

### GetPageModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the page model
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
Specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
Specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page layout is print or not
</td>
</tr>
</tbody>
</table>

### GetPrintModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the print model
</td>
</tr>
</tbody>
</table>

### DrillDown

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process drill down
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
toggleInfo 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
specify the toggle information to process toggle
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page layout is print or not  
</td>
</tr>
</tbody>
</table>

### ClearCache

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to clear the cache
</td>
</tr>
</tbody>
</table>

### DrillThrough

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process the drill through
</td>
</tr>
<tr>
<td class="parameter name">
reportName  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the child report name to drill through navigation
</td>
</tr>
<tr>
<td class="parameter name">
parameters  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to process drill through
</td>
</tr>
<tr>
<td class="parameter name">
authentication Key  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the authentication key to process drill through
</td>
</tr>
</tbody>
</table>

### Request

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

    constructor() {
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/ReportViewer';        
        this.reportPath = 'GroupingAgg.rdl';
    }
}

{% endhighlight %}

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:

Browser will render the reportviewer control with specified RDL report.

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnInitReportOptions 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
    reportOption.ReportModel.ReportingServer = new ReportingServerExt();
    reportOption.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("guest", "demo");   
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be Initialized for RDL report

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnReportLoaded 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
        reportOptions.ReportModel.DataSources.Clear();
        var DataSources = reportOptions.ReportModel.DataSources;   
        List<ReportParameter> parameters = new List<ReportParameter>();
        parameters.Add(new ReportParameter() { Name = "InvoiceID", Labels = new List<string>() { "InvoiceID" }, Values = new List<string>() { "10250" } });
        reportOptions.ReportModel.Parameters = parameters;      
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be updated when loading the RDL report.

### RDLC Report Services

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/PostReportAction 

### Parameter

### ReportLoad

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to load the report
</td>
</tr>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
String
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportPath
</td>
<td class="datatype">
String 
</td>
<td class="description">
Report path of the report 
</td>
</tr>
<tr>
<td class="parameter name">
reportServerUrl
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the Report Server url to accessing the report
</td>
</tr>
<tr>
<td class="parameter name">
processingMode
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the processing mode of the report  
</td>
</tr>
</tbody>
</table>

### GetDatasourceCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the Datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
<tr>
<td class="parameter name">
parameters
</td>
<td class="datatype">
String 
</td>
<td class="description">
Specify the parameter collections 
</td>
</tr>
</tbody>
</table>

### ValidateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to validate the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### UpdateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### GetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the parameters
</td>
</tr>
</tbody>
</table>

### SetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to set the parameters
</td>
</tr>
<tr>
<td class="parameter name">
parameters 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to set the parameters
</td>
</tr>
</tbody>
</table>

### UpdateParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the parameters
</td>
</tr>
<tr>
<td class="parameter name">
update param 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to update the parameters
</td>
</tr>
</tbody>
</table>

### UpdateDataSource

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource
</td>
</tr>
</tbody>
</table>

### GetPageModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the page model
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
Specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
Specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page layout is print or not
</td>
</tr>
</tbody>
</table>

### GetPrintModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the print model
</td>
</tr>
</tbody>
</table>

### DrillDown

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process drill down
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
toggleInfo 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
specify the toggle information to process toggle
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page layout is print or not  
</td>
</tr>
</tbody>
</table>

### ClearCache

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to clear the cache
</td>
</tr>
</tbody>
</table>

### DrillThrough

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process the drill through
</td>
</tr>
<tr>
<td class="parameter name">
reportName  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the child report name to drill through navigation
</td>
</tr>
<tr>
<td class="parameter name">
parameters  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to process drill through
</td>
</tr>
<tr>
<td class="parameter name">
authentication Key  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the authentication key to process drill through
</td>
</tr>
</tbody>
</table>

### Request

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

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:

Browser will render the reportviewer control with specified RDLC report.

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnInitReportOptions 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
            if (reportOption.ReportModel.IsDrillthroughReport)            
                return;
            var reportName = reportOption.ReportModel.ReportPath;
            reportOption.ReportModel.ReportPath = ReportViewerHelper.GetReportPath(reportOption.ReportModel.ReportPath);
            if (reportName.Contains("Product Catalog.rdlc"))
            {
                reportOption.ReportModel.DataSources.Clear();
                reportOption.ReportModel.DataSources.Add(new ReportDataSource { Name = "ProductCatalog", Value = ProductCatalog.GetData() });
            }  
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be Initialized for RDLC Report

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnReportLoaded 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
            var reportName = reportOption.ReportModel.ReportPath;
            if (reportName.Contains("Region.rdlc"))
            {
                reportOption.ReportModel.DataSources.Clear();
                reportOption.ReportModel.DataSources.Add(new ReportDataSource { Name = "StoreSales", Value = StoreSales.GetData() });
            }        
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be updated when loading the RDLC report.

### SSRS Report Services

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/PostReportAction 

### Parameter

### ReportLoad

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to load the report
</td>
</tr>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
String
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportPath
</td>
<td class="datatype">
String 
</td>
<td class="description">
Report path of the report 
</td>
</tr>
<tr>
<td class="parameter name">
reportServerUrl
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the Report Server url to accessing the report
</td>
</tr>
<tr>
<td class="parameter name">
processingMode
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the processing mode of the report  
</td>
</tr>
</tbody>
</table>

### GetDatasourceCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the Datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
<tr>
<td class="parameter name">
parameters
</td>
<td class="datatype">
String 
</td>
<td class="description">
Specify the parameter collections 
</td>
</tr>
</tbody>
</table>

### ValidateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to validate the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### UpdateDSCredential

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource credential
</td>
</tr>
<tr>
<td class="parameter name">
dataSources 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Datasource of the report 
</td>
</tr>
</tbody>
</table>

### GetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the parameters
</td>
</tr>
</tbody>
</table>

### SetParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to set the parameters
</td>
</tr>
<tr>
<td class="parameter name">
parameters 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to set the parameters
</td>
</tr>
</tbody>
</table>

### UpdateParameters

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the parameters
</td>
</tr>
<tr>
<td class="parameter name">
update param 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to update the parameters
</td>
</tr>
</tbody>
</table>

### UpdateDataSource

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to update the datasource
</td>
</tr>
</tbody>
</table>

### GetPageModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the page model
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
Specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
Specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
Specify whether the page layout is print or not
</td>
</tr>
</tbody>
</table>

### GetPrintModel

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to get the print model
</td>
</tr>
</tbody>
</table>

### DrillDown

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process drill down
</td>
</tr>
<tr>
<td class="parameter name">
pageIndex 
</td>
<td class="datatype">
Int
</td>
<td class="description">
specify the page index of the report
</td>
</tr>
<tr>
<td class="parameter name">
toggleInfo 
</td>
<td class="datatype">
JSON
</td>
<td class="description">
specify the toggle information to process toggle
</td>
</tr>
<tr>
<td class="parameter name">
refresh
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the report refresh or not 
</td>
</tr>
<tr>
<td class="parameter name">
dataRefresh 
</td>
<td class="datatype">
Boolean 
</td>
<td class="description">
specify whether the data refresh or not
</td>
</tr>
<tr>
<td class="parameter name">
pageInit 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page initialized or not  
</td>
</tr>
<tr>
<td class="parameter name">
isPrint 
</td>
<td class="datatype">
Boolean
</td>
<td class="description">
specify whether the page layout is print or not  
</td>
</tr>
</tbody>
</table>

### ClearCache

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to clear the cache
</td>
</tr>
</tbody>
</table>

### DrillThrough

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
reportAction  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Input data in the JSON format to process the drill through
</td>
</tr>
<tr>
<td class="parameter name">
reportName  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the child report name to drill through navigation
</td>
</tr>
<tr>
<td class="parameter name">
parameters  
</td>
<td class="datatype">
JSON
</td>
<td class="description">
Specify the parameters details to process drill through
</td>
</tr>
<tr>
<td class="parameter name">
authentication Key  
</td>
<td class="datatype">
String
</td>
<td class="description">
Specify the authentication key to process drill through
</td>
</tr>
</tbody>
</table>

### Request

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

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:

Browser will render the reportviewer control with specified SSRS report.

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnInitReportOptions 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
                string reportserverUrl = WebConfigurationManager.AppSettings["ReportServerUrl"];
                reportOption.ReportModel.ReportServerUrl = reportserverUrl;           
                reportOption.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("ssrs", "RDLReport1");
                reportOption.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("NorthWindIO", "ssrs1", "RDLReport1"));  
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be Initialized for SSRS report

### URL: http://js.syncfusion.com/demos/ejServices/api/ReportViewer/OnReportLoaded 

### Parameter

<table>
<thead>
<tr>
<th>
Parameter name
</th>
<th>
Data type
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td class="parameter name">
controlId
</td>
<td class="datatype">
string
</td>
<td class="description">
Control ID of the widget 
</td>
</tr>
<tr>
<td class="parameter name">
reportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Report model items.
</td>
</tr>
<tr>
<td class="parameter name">
SubReportModel
</td>
<td class="datatype">
property
</td>
<td class="description">
Contains the collections of Sub Report model items.
</td>
</tr>
</tbody>
</table>

### Request

~~~csharp
        reportOptions.ReportModel.DataSources.Clear();
        var DataSources = reportOptions.ReportModel.DataSources;  
        List<ReportParameter> parameters = new List<ReportParameter>();
        parameters.Add(new ReportParameter() { Name = "InvoiceID", Labels = new List<string>() { "InvoiceID" }, Values = new List<string>() { "10250" } });
        reportOptions.ReportModel.Parameters = parameters;      
~~~

### Response

#### Code:  200

#### Content-Type:”application/json:charset=utf-8”;

#### Response Text:
ReportOptions will be updated when loading the SSRS report.

## ReportViewerHelper

ReportViewerHelper class used to process the ReportViewer control in server side.

### Methods:

### ProcessReport(Dictionary<string, object> jsonResult, IReportController reportController)

Process the Report in Reportviewer Control  with specified report details

Code snippet:

return.ProcessReport(jsonResult, this);

### GetReport(string key, string type)

Getting the Report to be processed in Reportviewer Control

Code snippet:

return.GetReport(string key, string type);

### GetResource(string key, string resourceType, bool isPrint)

Getting the Resource from Reportviewer Control and It will process the report Exporting.

Code snippet:

return.GetResource(string key, string resourceType, bool isPrint);

### GetParameters()

Getting the Report Parameters of the Reportviewer Control

Code snippet:

return.GetParameters();

### GetDataSources()

Getting the Report DataSource of the Reportviewer Control

Code snippet:

return.GetDataSources();

### GetDataSetNames()

Getting the Report Dataset of the Reportviewer Control

Code snippet:

return.GetDataSetNames();