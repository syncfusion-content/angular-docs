---
title: Events
description: events
platform: Angular
control: ReportViewer
documentation: ug
keywords: ReportViewer Events, RenderingBegin, RenderingComplete, ReportError, ReportLoaded
---

# Events

The ReportViewer has the following client-side events support to listen to the control action.

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
destroy</td><td>
Fires when the ReportViewer is destroyed.</td></tr>
<tr>
<td>
drillThrough</td><td>
Fires during drill through action done in report and event can be canceled.</td></tr>
<tr>
<td>
renderingBegin</td><td>
Fires before report rendering is completed.</td></tr>
<tr>
<td>
renderingComplete</td><td>
Report loaded method that is triggered when report and sub report begin loading.</td></tr>
<tr>
<td>
reportError</td><td>
Fires when any error occurs while rendering the report and event can be canceled.</td></tr>
<tr>
<td>
reportLoaded</td><td>
Fires when the report is loaded.</td></tr>
</table>


{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Local" [reportPath] = "reportPath" (reportLoaded) = "reportLoaded($event)">
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
		
		this.serviceUrl = 'http://localhost:49771/api/ReportApi';        
        this.reportPath = '~/Reports/IndicatorReport.rdlc';  		
    }
	
	reportLoaded(event) {
		    let desc2013 = [
                        {
                            No: 1, Name: "Carlos Slim", NetWorth: 73.0, Age: 73, CitizenShip: "Mexico", Source: "Telmex,America Movil, Grupo Carso", RankingStatus: 50, ProfitStatus: 75
                        },
                        {
                            No: 2, Name: "Bill Gates", NetWorth: 67.0, Age: 57, CitizenShip: "United States", Source: "Microsoft", RankingStatus: 50, ProfitStatus: 75
                        },
                        {
                            No: 3, Name: "Amancio Ortega", NetWorth: 57.0, Age: 57, CitizenShip: "Spain", Source: "Inditex Group", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 4, Name: "Warren Buffett", NetWorth: 53.0, Age: 82, CitizenShip: "United States", Source: "Berkshire Hathaway", RankingStatus: 25, ProfitStatus: 75
                        },
                        {
                            No: 5, Name: "Larry Ellison", NetWorth: 43.0, Age: 68, CitizenShip: "United States", Source: "Oracle Corporation", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 6, Name: "Charles Koch", NetWorth: 34.0, Age: 77, CitizenShip: "United States", Source: "Koch Industries", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 7, Name: "David Koch", NetWorth: 34.0, Age: 72, CitizenShip: "United States", Source: "Koch Industries", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 8, Name: "Li Ka-shing", NetWorth: 32.0, Age: 84, CitizenShip: "Hong Kong/ Canada", Source: "Cheung Kong Holdings", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 9, Name: "Liliane Bettencourt", NetWorth: 30.0, Age: 90, CitizenShip: "France", Source: "L'Oreal", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 10, Name: "Bernard Arnault", NetWorth: 29.0, Age: 63, CitizenShip: "France", Source: "LVMH Moet Hennessy Louis Vuitton", RankingStatus: 25, ProfitStatus: 25
                        }];

            let desc2012 = [
                        {
                            No: 1, Name: "Carlos Slim", NetWorth: 69.0, Age: 72, CitizenShip: "Mexico", Source: "Telmex,America Movil, Grupo Carso", RankingStatus: 50, ProfitStatus: 25
                        },
                        {
                            No: 2, Name: "Bill Gates", NetWorth: 61.0, Age: 56, CitizenShip: "United States", Source: "Microsoft", RankingStatus: 50, ProfitStatus: 75
                        },
                        {
                            No: 3, Name: "Warren Buffett", NetWorth: 44.0, Age: 81, CitizenShip: "United States", Source: "Berkshire Hathaway", RankingStatus: 50, ProfitStatus: 25
                        },
                        {
                            No: 4, Name: "Bernard Arnault", NetWorth: 41.0, Age: 63, CitizenShip: "France", Source: "LVMH Moet Hennessy Louis Vuitton", RankingStatus: 50, ProfitStatus: 75
                        },
                        {
                            No: 5, Name: "Amancio Ortega", NetWorth: 37.5, Age: 75, CitizenShip: "Spain", Source: "Inditex Group", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 6, Name: "Larry Ellison", NetWorth: 36.0, Age: 67, CitizenShip: "United States", Source: "Oracle Corporation", RankingStatus: 25, ProfitStatus: 75
                        },
                        {
                            No: 7, Name: "Eike Batista", NetWorth: 30.0, Age: 55, CitizenShip: "Brazil", Source: "EBX Group", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 8, Name: "Stefan Persson", NetWorth: 26.5, Age: 64, CitizenShip: "Sweden", Source: "H&M", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 9, Name: "Li Ka-shing", NetWorth: 25.0, Age: 83, CitizenShip: "Hong Kong/ Canada", Source: "Cheung Kong Holdings", RankingStatus: 75, ProfitStatus: 75
                        },
                        {
                            No: 10, Name: "Karl Albrecht", NetWorth: 25.4, Age: 92, CitizenShip: "Germany", Source: "Aldi", RankingStatus: 75, ProfitStatus: 25
                        }];


            let description = [
           {
               Status: 25, Description: "Has not changed from the previous ranking."
           },
           {
               Status: 50, Description: "Has increased from the previous ranking."
           },
           {
               Status: 75, Description: "Has decreased from the previous ranking."
           }];
           
            event.model.dataSources = [{
                value: ej.DataManager(desc2013).executeLocal(ej.Query()),
                name: "DataSet1"
            }, {
                value: ej.DataManager(desc2012).executeLocal(ej.Query()),
                name: "DataSet2"
            }, {
                value: ej.DataManager(description).executeLocal(ej.Query()),
                name: "DataSet3"
            }];
	}
}

{% endhighlight %}















