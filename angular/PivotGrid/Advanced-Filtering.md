---
title: Advanced Filtering and Sorting
description: advance filtering and sorting
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Advanced Filtering & Sorting

It allows to filter and sort the field members in PivotGrid. You can enable the Advanced Filtering and Sorting option in PivotGrid by setting the [`enableAdvancedFilter`](/api/angular/ejpivotgrid#members:enableAdvancedFilter) property to true.

{% highlight html %}

<ej-pivotgrid [enableGroupingBar]="true" [enableAdvancedFilter]="true">
</ej-pivotgrid>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field either in ascending or descending order. 


![](AdvanceFiltering_images/sorting.png)

## Label Filtering

Label filtering provides an option to filter the members of a field purely based on their caption. 

![](AdvanceFiltering_images/filtering.png)

![](AdvanceFiltering_images/filtering_dialog.png)


## Value Filtering

Value filtering provides an option to filter members based on the total values of the appropriate measure between the members of the level. 

![](AdvanceFiltering_images/valuefilter.png)

![](AdvanceFiltering_images/valuefilter_dialog.png)
