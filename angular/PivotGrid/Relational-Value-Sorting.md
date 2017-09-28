---
title: Value-Sorting
description: value Sorting
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Value Sorting

I> This feature is applicable for Relational datasource only at Client Mode.

Value Sorting allows to sort columns and rows based on value fields.

The headers of the column to be sorted is given in the 'headerText' property under 'valueSortSettings' in field wise order separated by a string.  The string which is used to separate the headers is given in the property 'headerDelimiters'.

{% tabs %}

{% highlight html %}
<ej-pivotgrid [valueSortSettings]="valueSortSettings">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}

export class PivotGridComponent {
   
    public  valueSortSettings;

        constructor()
        {
            this.valueSortSettings = {
                headerText: "Bike##Quantity",
                headerDelimiters: "##",
                sortOrder: ej.PivotAnalysis.SortOrder.Descending
            };
        }
 }

{% endhighlight %}

{% endtabs %}

![](Value-Sorting_images/Before.png) 

![](Value-Sorting_images/After.png) 



