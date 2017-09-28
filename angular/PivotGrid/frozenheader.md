---
title:  Frozen Header
description:  frozen header
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Frozen Header

Allows you to freeze the header of the Grid so that it will be always visible when scrolling the content with a large number of rows or columns providing a precise view.

{% highlight html %}

<ej-pivotgrid [frozenHeaderSettings.enableFrozenHeaders]="true">
</ej-pivotgrid>

{% endhighlight %}

![](FrozenHeader_images/row_col_freeze.png)

We can also freeze the row/column headers individually by setting the below properties.

{% highlight html %}

<ej-pivotgrid [frozenHeaderSettings.enableFrozenRowHeaders]="true">
</ej-pivotgrid>

{% endhighlight %}

![](FrozenHeader_images/row_freeze.png)

{% highlight html %}

<ej-pivotgrid [frozenHeaderSettings.enableFrozenColumnHeaders]="true">
</ej-pivotgrid>

{% endhighlight %}

![](FrozenHeader_images/col_freeze.png)