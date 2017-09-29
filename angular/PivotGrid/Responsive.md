---
layout: post
title: Responsive
description: responsive
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Responsive

PivotGrid and PivotTable Field list control supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotGrid by setting [`isResponsive`](/api/angular/ejpivotgrid#members:isresponsive) property to true. 

On resizing the browser, the PivotTable Field list will get collapse and an icon will appear on the left-hand side of the browser. User can toggle its view and perform UI interaction.

{% highlight html %}

 <ej-pivotgrid id="PivotGrid1" [isResponsive]="true">
</ej-pivotgrid>

{% endhighlight %}

![](Responsive_images/normal.png)

_Normal PivotGrid_
{:.caption}

![](Responsive_images/responsive.png)

_Responsive PivotGrid_
{:.caption}

![](Responsive_images/res-schema.png)

_Responsive PivotTable Field List - Collapsed_
{:.caption}

![](Responsive_images/res-schema1.png)

_Responsive PivotTable Field List - Expanded_
{:.caption}

