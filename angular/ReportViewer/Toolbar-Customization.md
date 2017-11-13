---
title: Toolbar Customization
description: toolbar customization
platform: Angular
control: ReportViewer
documentation: ug
keywords: Toolbar Customization, ReportViewer ToolbarSettings, Hide ToolbarItems
---

# Toolbar Customization

The ReportViewer has an option to show or hide items in the toolbar. To customize the toolbar items, use the ReportViewer’s `toolbarSettings` property. The toolbar template can also be customized by specifying custom template to ReportViewer toolbar.

{% highlight html %}

<ej-reportviewer id="reportViewer_Control" [reportServiceUrl] = "serviceUrl" [processingMode] = "Remote" [reportPath] = "reportPath" [toolbarSettings] = "toolbarSettings">
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
	public reportData: any;
	public toolbarSettings: any;

    constructor() {	
		
		this.serviceUrl = '~/api/ReportViewer';        
        this.reportPath = 'Invoice.rdl';  
		this.toolbarSettings = {
        items: ej.ReportViewer.ToolbarItems.All & ~ej.ReportViewer.ToolbarItems.Parameters
        };
    }	
}

{% endhighlight %}



