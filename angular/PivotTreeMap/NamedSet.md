---
layout: post
title: Named Set
description: named set
platform: Angular
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Named Sets

Named Sets is a multidimensional expression (MDX) that returns a set of dimension members, which can be created by combining cube data, arithmetic operators, numbers and functions.

You can bind the Named Sets in PivotTreeMap by setting it's unique name in the `field-name` property either in row or column axis and `is-named-sets` boolean property to "true".

{% tabs %}

{% highlight html %}

<ej-pivottreemap id="PivotTreeMap1" dataSource.data="http://bi.syncfusion.com/olap/msmdpump.dll" dataSource.catalog="Adventure Works DW 2008 SE" dataSource.cube="Adventure Works" [dataSource.rows]="rows" [dataSource.columns]="columns" [dataSource.values]="values" [dataSource.filters]="filters" (renderSuccess)="renderSuccess($event)">
</ej-pivottreemap>

{% endhighlight %}

{% highlight ts %}
    //..
    export class PivotTreeMapComponent {
        public rows; columns; values; filters;
        constructor() {
          this.rows = [{ fieldName: "[Core Product Group]", isNamedSets: true }];
          this.columns = [{ fieldName: "[Customer].[Customer Geography]" }];
          this.values = [{ measures: [{ fieldName: "[Measures].[Customer Count]", }], axis: "columns" }];
          this.filters = [];
        }
        renderSuccess(args){
         let treemapTarget = $('#PivotTreeMap1TreeMapContainer').data('ejTreeMap');
         treemapTarget.model.tooltipTemplate = null;
         treemapTarget.model.showTooltip = false;
         treemapTarget.refresh();
        }
    }

{% endhighlight %}

{% endtabs %}

![](NamedSets_images/namedset.png)