---
layout: post
title: Service reference for ejGantt widget
description: What are the exporting services used in Essential JavaScript Gantt.
workbookation: api
platform: Angular
keywords: ejGantt, Services, Essential JS Gantt, Gantt, Excel Exporting Service, Gantt Exporting
metaname: 
metacontent:
control: ejGantt
api: /api/js/ejgantt
---
# Gantt Exporting services

## Description

Find the Gantt exporting type below,

* Excel Export.

## Excel export

### URL

`http://js.syncfusion.com/ejServices/api/JSGanttExport/ExcelExport`

### Parameter

Type1:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
</table>

Type2:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
It specifies the file name an extension to be downloaded</td></tr>
<tr>
<td>
excelVersion</td><td>
String</td><td>
Excel version in which workbook should download</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
</table>

Type3:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
It specifies the file name and extension to be downloaded</td></tr>
<tr>
<td>
excelVersion</td><td>
String</td><td>
Excel version in which workbook should download</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
</table>

Type4:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append it to something else before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type5:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to ???Export???</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type6:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
excelName</td><td>
String</td><td>
With this parameter you can set the downloaded file name. By default it is set to ???Export???</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type7:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
Workbook</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which workbook the file export should append, it holds the internally stored excel files which is exported previously.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type8:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
excelName</td><td>
string</td><td>
With this parameter you can set the downloaded file name. By default it is set to ???Export???.</td></tr>
<tr>
<td>
Workbook</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which workbook the file export should append, it holds the internally stored excel files which is exported previously.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type9:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
excelName</td><td>
string</td><td>
With this parameter you can set the downloaded file name. By default it is set to ???Export???.</td></tr>
<tr>
<td>
filePath</td><td>
String</td><td>
With this parameter you can set the location where the exporting file should downloaded. It can be local or server machine file path.</td></tr>
<tr>
<td>
Workbook</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which workbook the file export should append, it holds the internally stored excel files which is exported previously.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

Type10:

<table>
<tr>
<td>
Name</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
GanttProperties</td><td>
Object</td><td>
It takes Gantt model properties that should be pass to exporting</td></tr>
<tr>
<td>
datasource</td><td>
object</td><td>
It holds the data to be exported in Excel</td></tr>
<tr>
<td>
GanttExportSettings</td><td>
object</td><td>
Returns the exporting settings like unicode support, columns fit to width, hidden column.</td></tr>
<tr>
<td>
excelName</td><td>
string</td><td>
With this parameter you can set the downloaded file name. By default it is set to ???Export???.</td></tr>
<tr>
<td>
multipleExport </td><td>
Boolean</td><td>
Is a boolean argument, and value `false` specifies the exporting is completed and download it, value `true` specifies the export Gantt internally and append something else to it before download starts.</td></tr>
<tr>
<td>
Workbook</td><td>
Object</td><td>
It specifies in case of multiple exporting, in which workbook the file export should append, it holds the internally stored excel files which is exported previously.</td></tr>
<tr>
<td>
MultipleExportType </td><td>
Object</td><td>
It specifies in case of multiple export, it returns the exporting type whether the file should append to the sheet or it should export in new sheet</td></tr>
<tr>
<td>
headerText</td><td>
String</td><td>
headerText is to specify the title for export workbook.</td></tr>
</table>

### Request

{% highlight javascript %}

<ej-gantt
    //...
    [toolbarSettings]= "toolbarSettings"
    (toolbarClick)="toolbarClick($event)">
</ej-gantt>

{% endhighlight %}

{% highlight javascript %}

import {Component} from '@angular/core';

@Component({
    selector: 'ej-app',
    templateUrl: 'app/app.component.html',
})
export class AppComponent {
    public toolbarSettings: any;
    constructor() {

        this.toolbarSettings = {
            showToolbar: true,
            toolbarItems: [
                ej.Gantt.ToolbarItems.ExcelExport,
                ej.Gantt.ToolbarItems.PdfExport
            ]
        }

    }
    toolbarclick(sender) {
        var id = $(sender.currentTarget).attr("id");
        var gantt = $("#GanttControl").ejGantt("instance");
        gantt.exportGrid = gantt["export"];
        if (sender.itemName == "Excel Export") {
            gantt.exportGrid('http://js.syncfusion.com/ejServices/api/JSGanttExport/ExcelExport', "", false);
            sender.cancel = true;
        }
    }
}

{% endhighlight %}


Following example will take part in the project service


~~~csharp

public void ExcelExport()

{

string gridModel = HttpContext.Current.Request.Params["GanttModel"];

GanttProperties gridProperty = ConvertGridObject(gridModel);

ExcelExport exp = new ExcelExport();

TaskDetailsCollection tc = new TaskDetailsCollection();

IEnumerable<TaskDetails> result = tc.GetDataSource();

exp.Export(gridProperty, result, "ExcelExport.xlsx", ExcelVersion.Excel2010, new GanttExportSettings() { Theme = ExportTheme.FlatAzure });

}

~~~

