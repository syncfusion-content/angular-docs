---
title: Getting Started for Angular 2 ReportViewer
description: ReportViewer
platform: Angular2
control: ReportViewer
documentation: ug
keywords: ejReportViewer, ReportViewer, js ReportViewer
---

# Getting Started

To get start with how to use the ReportViewer component within Angular-2 platform, refer the basic requisites and the configurations needs to be done on the system from [here](/angular-2/overview).

Once the configurations are done, run the below commands in the command prompt to clone the repository for `SystemJS` starter and to install the required dependency packages automatically.

{% highlight html %}

    > git clone https://github.com/syncfusion/angular2-seeds/ -b systemjs
    > cd angular2-seeds
    > npm install
 
{% endhighlight %}

Once the cloned seed application is created, now it is ready to make use of any of our Syncfusion components within it.

## Copying ReportViewer source file

Copy the required `reportviewer.component.ts` source file from the following location and add it under the **src/ej** folder within the newly cloned **angular2-seeds** folder.

* (**Installed location**)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets-src\angular2\

N> `core.ts` source file is mandatory for all Syncfusion JavaScript Angular 2 components. 

## Adding ReportViewer HTML file

Create a folder named **reportviewer** within the **src** folder. Now, create a html file and name it as **reportviewer.component.html** under the _src/reportviewer folder. Place the reportviewer rendering code within this file as depicted below,

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Remote" [reportPath] = "reportPath" >
</ej-reportviewer>

{% endhighlight %}

Create a **reportviewer.component.css** file under the same **src/reportviewer** folder. Place the reportviewer CSS style within this file as depicted below,

{% highlight css %}

ej-reportviewer {
    display: block;
    height: 550px;
}

{% endhighlight %}

Create a **reportviewer.component.ts** file under the same **src/reportviewer** folder, where the reportPath and serviceUrl needs to be defined.

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
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/RDLReport';        
        this.reportPath = 'GroupingAgg.rdl';
    }
}

{% endhighlight %}

N> Default RDL Report will be rendered, which is used in the online service.

## Configure the Router and Navigation

Configure the route navigation link for the newly created ReportViewer sample within the **src/app.component.html** file as shown below,

{% highlight html %}

	<ul class="nav navbar-nav">
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#" [routerLink]="['/']">Syncfusion Angular 2</a></li>
		<li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#home" [routerLink]="['/home']">Home</a></li>
        <!-- ReportViewer sample navigation link -->
        <li><a data-toggle="collapse" data-target="#skeleton-navigation-navbar-collapse.in" href="#reportviewer" [routerLink]="['/reportviewer']">ReportViewer</a></li>
	</ul>

{% endhighlight %}

Now, import and define the ReportViewer sample's route within the **src/app.routes.ts** file as shown below,

{% highlight ts %}

    import { Routes } from '@angular/router';
    import { ReportViewerComponent } from './reportviewer/reportviewer.component'; // imports ReportViewer component
    import { HomeComponent } from './home/home.component';

    export const rootRouterConfig: Routes = [
        { path: '', redirectTo: 'home', pathMatch: 'full' },
        { path: 'home', component: HomeComponent },
    	{ path: 'reportviewer', component: ReportViewerComponent } // ReportViewer sample path
    ];


{% endhighlight %}

Now, finally make sure to import and declare the ReportViewer's source and sample component files into the **app.module.ts** as shown in the below code snippet.

{% highlight ts %}
    
    // imports the ReportViewer's source and sample component files
    import { AppComponent } from './app.component';
    import { HomeComponent } from './home/home.component';

    import { EJ_REPORTVIEWER_COMPONENTS } from './ej/reportviewer.component';
    import { ReportViewerComponent } from './reportviewer/reportviewer.component';
    
    import { rootRouterConfig } from './app.routes';
    
    // Declare the source and sample files here in this module declaration part
    @NgModule({
        imports: [BrowserModule, FormsModule, HttpModule, RouterModule.forRoot(rootRouterConfig, { useHash: true })],
        declarations: [AppComponent, HomeComponent, EJ_REPORTVIEWER_COMPONENTS, ReportViewerComponent],
        bootstrap: [AppComponent]
    })

{% endhighlight %}

## Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportViewer** tab to view the ReportViewer output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}.

## Load SSRS Server Reports

### Adding ReportViewer HTML file
Create a folder named **reportviewer** within the **src** folder. Now, create a html file and name it as **reportviewer.component.html** under the _src/reportviewer folder. Place the reportviewer rendering code within this file as depicted below,

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Remote" [reportServerUrl] = "serverUrl" [reportPath] = "reportPath" >
</ej-reportviewer>

{% endhighlight %}

Create a **reportviewer.component.css** file under the same **src/reportviewer** folder. Place the reportviewer CSS style within this file as depicted below,

{% highlight css %}

ej-reportviewer {
    display: block;
    height: 550px;
}

{% endhighlight %}

Create a **reportviewer.component.ts** file under the same **src/reportviewer** folder, where the reportPath and serviceUrl needs to be defined.

{% highlight ts %}

import { Component } from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'src/reportviewer/reportviewer.component.html',
	styleUrls: ['src/reportviewer/reportviewer.component.css']
})

export class ReportViewerComponent {
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

### Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportViewer** tab to view the ReportViewer output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img2.png) 
   
Report from SSRS
{:.caption}

## Load RDLC Reports

The ReportViewer has data binding support to visualize the RDLC reports. The following code example helps you to bind data to ReportViewer.

### Adding ReportViewer HTML file
Create a folder named **reportviewer** within the **src** folder. Now, create a html file and name it as **reportviewer.component.html** under the _src/reportviewer folder. Place the reportviewer rendering code to load RDLC report within this file as depicted below,

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Local"	 [reportServerUrl] = "serverUrl" [reportPath] = "reportPath" [dataSources]="reportData" >
</ej-reportviewer>

{% endhighlight %}

Create a **reportviewer.component.css** file under the same **src/reportviewer** folder. Place the reportviewer CSS style within this file as depicted below,

{% highlight css %}

ej-reportviewer {
    display: block;
    height: 550px;
}

{% endhighlight %}

Create a **reportviewer.component.ts** file under the same **src/reportviewer** folder, where the reportPath, serviceUrl and dataSources needs to be defined.

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
        this.serviceUrl = 'http://js.syncfusion.com/ejservices/api/RDLCReport';        
        this.reportPath = 'AreaCharts.rdlc"';
		this.reportData = [{
      value: [
        { SalesPersonID: 281, FullName: 'Ito', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 0, Y2003: 28000, Y2004: 3018725 },
        { SalesPersonID: 282, FullName: 'Saraiva', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 25000, Y2003: 14000, Y2004: 3189356 },
        { SalesPersonID: 283, FullName: 'Cambell', Title: 'Sales Representative', SalesTerritory: 'North West', Y2002: 12000, Y2003: 13000, Y2004: 1930885 },
        { SalesPersonID: 275, FullName: 'Blythe', Title: 'Sales Representative', SalesTerritory: 'North East', Y2002: 19000, Y2003: 47000, Y2004: 4557045 },
        { SalesPersonID: 276, FullName: 'Mitchell', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 28000, Y2003: 46000, Y2004: 5240075 },
        { SalesPersonID: 277, FullName: 'Carson', Title: 'Sales Representative', SalesTerritory: 'Central', Y2002: 33000, Y2003: 49000, Y2004: 3857163 },
        { SalesPersonID: 278, FullName: 'Vargas', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 11000, Y2003: 14000, Y2004: 1764938 },
        { SalesPersonID: 279, FullName: 'Reiter', Title: 'Sales Representative', SalesTerritory: 'South East', Y2002: 32000, Y2003: 26000, Y2004: 2811012 }
      ],
      name: 'AdventureWorksXMLDataSet'
    }];
    }
}

{% endhighlight %}

N> Default RDLC Report will be rendered, which is used in the online service.

### Run the Application

Execute the below command in the command prompt.

* npm start

The application gets opened in the browser automatically and now, navigate to the **ReportViewer** tab to view the ReportViewer output on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img3.png) 

Area Chart RDLC Report
{:.caption}
