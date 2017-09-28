---
title: Grid-Layout
description: Layouts
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Grid Layout

## Normal Layout

A layout in which summary cells are positioned at the bottom of each parent member and their child members appear next to them. Normal layout is the default layout in PivotGrid control. The enumeration property [`layout`](/api/angular/ejpivotgrid#members:layout) needs to be set to **"ej.PivotGrid.Layout.Normal"** in-order to view PivotGrid in normal layout. 

{% tabs %}

{% highlight html %}

<ej-pivotgrid [layout]="layout">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}
export class PivotGridComponent {
    public layout;
    constructor() {
        //..
        this.layout = ej.PivotGrid.Layout.Normal; 
    }
}

{% endhighlight %}

{% endtabs %}

![](Grid-Layout_images/layout-normal.png)

## No Summaries Layout

I> This feature is applicable only for OLAP datasource.

A layout in which summary cells are completely hidden and the child members appear next to their parent member.  The enumeration property [`layout`](/api/angular/ejpivotgrid#members:layout) needs to be set to **"ej.PivotGrid.Layout.NoSummaries"** in-order to view PivotGrid without summaries.

{% highlight ts %}

export class PivotGridComponent {
    public layout;
    constructor() {
        //..
        this.layout = ej.PivotGrid.Layout.NoSummaries; 
    }
}

{% endhighlight %}
 
![](Grid-Layout_images/layout-nosummary.png)

## Excel-like Layout
A layout in which summary cells are positioned besides each parent member and their child members appear next to them. The enumeration property [`layout`](/api/angular/ejpivotgrid#members:layout) needs to be set to **"ej.PivotGrid.Layout.ExcelLikeLayout"** in-order to view PivotGrid in excel-like layout.


{% highlight ts %}

export class PivotGridComponent {
    public layout;
    constructor() {
        //..
        this.layout = ej.PivotGrid.Layout.ExcelLikeLayout; 
    }
}

{% endhighlight %}

![](Grid-Layout_images/layout-excel.png)
