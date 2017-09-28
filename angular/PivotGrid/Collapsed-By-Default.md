---
title: Collapse by default
description: Collapse by default
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Collapse by default

I> This feature is applicable only for Relational datasource.

Allows you to collapse all members displayed in the grid. You can enable collapsing all members by default in PivotGrid by setting [`enableCollapseByDefault`](/api/angular/ejpivotgrid#members:enablecollapsebydefault) property to true.

{% highlight html %}
<ej-pivotgrid [enableCollapseByDefault]="true">
    </ej-pivotgrid>

{% endhighlight %}

![](Collapsed-By-Default_images/Collapse-members.png)

