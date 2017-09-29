---
title:  GrandTotal Hiding
description: GrandTotal Hiding
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Grand Total Hiding

Grand Total Hiding can be classified into three categories.

* Row Grand Total Hiding
* Column Grand Total Hiding
* Both

## Row Grand Total Hiding

You can hide the **Grand Total** in row alone by setting the property [`enableRowGrandTotal`](/api/angular/ejpivotgrid#members:enablerowgrandtotal) to `false`

{% highlight html %}

<ej-pivotgrid [enableRowGrandTotal]="false">
</ej-pivotgrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column Grand Total Hiding

You can hide the **Grand Total** in column alone by setting the property [`enableColumnGrandTotal`](/api/angular/ejpivotgrid#members:enablecolumngrandtotal) to `false`

{% highlight html %}

<ej-pivotgrid [enableColumnGrandTotal]="false">
</ej-pivotgrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the property [`enableGrandTotal`](/api/angular/ejpivotgrid#members:enablegrandtotal) to `false`

{% highlight html %}

<ej-pivotgrid [enableGrandTotal]="false">
</ej-pivotgrid>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableGrandTotal.png)