---
title: Save and Load Report
description: save and load report
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Save and Load Report

Allows you to save the current report of PivotGrid and render the control with the saved report later.

## Save Report to Local Storage

To save the current report of PivotGrid to local storage, we need to call the [`saveReport`](/api/angular/ejpivotgrid#members:saveReport) method in PivotGrid.

{% tabs %}

{% highlight html %}

<ej-pivotgrid (saveReport)="saveToLocal($event)">
</ej-pivotgrid>
<input id="btnSave" ej-button size="normal" (click)="onSave($event)" value="Save" 

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    onSave() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        url = "",
        name = "report",
        storage = "local",
        pGridObj.saveReport(name, storage, url);
    }
    saveToLocal(args) {
        localStorage.setItem("report", JSON.stringify(args.report));
    }
}

{% endhighlight %}

{% endtabs %}

## Load Report from Local Storage

To load the stored report of PivotGrid from local storage, we need to call the ['loadReport'](/api/angular/ejpivotgrid#members:loadReport) method in PivotGrid.

{% tabs %}

{% highlight html %}

<ej-pivotgrid (loadReport)="loadFromLocal($event)">
</ej-pivotgrid>
<input id="btnLoad" ej-button size="normal" (click)="onLoad($event)" value="load" 

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    //..
    onLoad() {
        let pGridObj = $('.e-pivotgrid').data("ejPivotGrid");
        url = "",
        name = "report",
        storage = "local",
        pGridObj.loadReport(name, storage, url);
    }
    loadFromLocal(args) {
        args.targetControl.model.dataSource = JSON.parse(localStorage.getItem("report"));
    }
}

{% endhighlight %}

{% endtabs %}
