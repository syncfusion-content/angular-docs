---
title: ToolTip
description: ToolTip
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# ToolTip

Allows you to display the details of the cell on hovering value cells. By default, tooltip is enabled.  You can disable tooltip in PivotGrid by setting the [`enableToolTip`](/api/angular/ejpivotgrid#members:enabletooltip)  property to false.

{% highlight html %}

 <ej-pivotgrid id="PivotGrid1" [enableToolTip]="false">
</ej-pivotgrid>

{% endhighlight %}

## ToolTip Animation

The PivotGrid provides option to animate tooltip displayed in the grid. The animation enhances the appearance of tooltip by displaying it slowly.  You can enable animation in tooltip by setting [`enableToolTipAnimation`](/api/angular/ejpivotgrid#members:enabletooltip) property to true.

{% highlight html %}

 <ej-pivotgrid id="PivotGrid1" [enableToolTipAnimation]="true">
</ej-pivotgrid>

{% endhighlight %}

![](ToolTip_images/ToolTip.png)

