---
title: Export
description: export
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Exporting

The PivotGrid control can be exported to the following file formats.

* Excel
* Word
* PDF
* CSV

The PivotGrid control can be exported by invoking **"exportPivotGrid"** method, with an appropriate export option as parameter.

## JSON Export

{% tabs %}

{% highlight html %}

<ej-pivotgrid [dataSource]="dataSource"></ej-pivotgrid>
<input id="btnExport" ej-button size="normal" (click)="onExport($event)" value="Export" 

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    }
}

{% endhighlight %}

{% endtabs %}

### Excel Export

User can export the contents of PivotGrid to an Excel document for future archival, references and analysis purposes.

To achieve Excel export, service URL and file name is sent as the parameter.

{% highlight ts %}

export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    }
}

{% endhighlight %}

### Word Export

User can export the contents of PivotGrid to a Word document for future archival, references and analysis purposes.

To achieve Word export, service URL and file name is sent as the parameter.

{% highlight ts %}

export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/WordExport", "fileName");
    }
}

{% endhighlight %}

### PDF Export

User can export the contents of PivotGrid to a PDF document for future archival, references and analysis purposes.

To achieve PDF export, service URL and file name is sent as the parameter.

{% highlight ts %}

export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/PDFExport", "fileName");
    }
}

{% endhighlight %} 

### CSV Export

User can export the contents of PivotGrid to a CSV document for future archival, references and analysis purposes.

To achieve CSV export, service URL and file name is sent as the parameter.

{% highlight ts %}

export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/CSVExport", "fileName");
    }
}

{% endhighlight %} 

### Customize the export document name

For customizing file name, we need to send file name as parameter to the **exportPivotGrid**  method along with service URL.

{% highlight ts %}

export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    }
}

{% endhighlight %} 

## Exporting Customization

You can add title and description to the exporting document by using title and description property obtained in the "beforeExport" event.

{% tabs %}

{% highlight html %}

<ej-pivotgrid [dataSource]="dataSource" (beforeExport)="beforeExport($event)"></ej-pivotgrid>
<input id="btnExport" ej-button size="normal" (click)="onExport($event)" value="Export" 

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    onExport() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        pGridObj.exportPivotGrid("http://js.syncfusion.com/ejservices/api/PivotGrid/Olap/ExcelExport", "fileName");
    }
    beforeExport(args) {
        args.title = "PivotGrid";
        args.description = "Displays both OLAP and Relational datasource in tabular format";
    }
}

{% endhighlight %}

{% endtabs %}

The below screenshot shows the PivotGrid control exported to Excel document.

![](Export_images/ExportPivotExcel.png)

The below screenshot shows the PivotGrid control exported to Word document.

![](Export_images/ExportPivotWord.png)

The below screenshot shows the PivotGrid control exported to PDF document.

![](Export_images/ExportPivotPDF.png)

The below screenshot shows the PivotGrid control exported to CSV document.

![](Export_images/ExportPivotCSV.png)
