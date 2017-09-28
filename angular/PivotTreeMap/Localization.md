---
layout: post
title: Localization
description: localizaton
platform: Angular
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Localization

## Localization and Globalization of Cube Info (Client Mode)

Content displayed within the PivotTreeMap control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.

* To get localized data from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture in the **"data"** property present inside **"dataSource"**. 

{% highlight html %}

//1036 refers to “fr-FR” culture.
<ej-pivottreemap id="PivotTreeMap1" dataSource.data="http://bi.syncfusion.com/olap/msmdpump.dll; Locale Identifier=1036;" dataSource.catalog="Adventure Works DW 2008 SE" dataSource.cube="Adventure Works" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values" [dataSource.filters]="filters" (renderSuccess)="renderSuccess($event)">
</ej-pivottreemap>

{% endhighlight %}


![](Localization_images/localization.png) 

