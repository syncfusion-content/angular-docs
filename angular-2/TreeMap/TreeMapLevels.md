---
layout: post
title: TreeMapLevels
description: treemaplevels
platform: angular2
control: TreeMap
documentation: ug
---

# TreeMapLevels

The levels of **TreeMap** can be categorized into two types as,

* FlatLevel
* Hierarchical Level

## Flat Level

### GroupPath

You can use `groupPath` property for every flat level of the **TreeMap** control. It is a path to a field on the source object that serves as the **“Group”** for the level specified. You can group the data based on the `groupPath` in the **TreeMap** control. When the `groupPath` is not specified, then the items are not grouped and the data is displayed in the order specified in the `dataSource`.

### GroupGap

You can use `groupGap` property to separate the items from every flat level and to differentiate the levels mentioned in the **TreeMap** control.

{% highlight html %}

<ej-treemap id="treemap" [dataSource]="population_data" weightValuePath="Population"
                                                           colorValuePath="Growth" >
    <e-levels>
       <e-level groupPath="Continent" [groupGap]=5></e-level>
    </e-levels>
</ej-treemap>

{% endhighlight %}



![](TreeMapLevels_images/TreeMapLevels_img1.png)
