---
layout: post
title: Layout
description: layout
platform: Angular
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the `itemsLayoutMode` property of the TreeMap.

There are four different **TreeMap** layouts such as

* Squarified
* SliceAndDiceAuto
* SliceAndDiceHorizontal
* SliceAndDiceVertical

## Squarified

**Squarified** layout creates rectangles with best aspect ratio.

{% highlight html %}

<ej-treemap id="treemap"  [dataSource]="population_data" itemsLayoutMode="squarified"
                          weightValuePath= "Population"  colorValuePath= "Growth">
     <e-levels>
         <e-level groupPath="Continent" [groupGap]=5></e-level>
     </e-levels>
</ej-treemap>

{% endhighlight %}



![](Layout_images/Layout_img1.png)

## SliceAndDiceAuto

**SliceAndDiceAuto** layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.

{% highlight html %}

<ej-treemap id="treemap"  [dataSource]="population_data" itemsLayoutMode="sliceanddiceauto"
                                 weightValuePath= "Population"  colorValuePath= "Growth">
    <e-levels>
         <e-level groupPath="Continent" [groupGap]=5></e-level>
    </e-levels>
</ej-treemap>

{% endhighlight %}



![](Layout_images/Layout_img2.png)

## SliceAndDiceHorizontal

**SliceAndDiceHorizontal** layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% highlight html %}

<ej-treemap id="treemap"  [dataSource]="population_data" 
        itemsLayoutMode="sliceanddicehorizontal" weightValuePath= "Population"
        colorValuePath= "Growth">
       <e-levels>
           <e-level groupPath="Continent" [groupGap]=5></e-level>
       </e-levels>
</ej-treemap>

{% endhighlight %}



![](Layout_images/Layout_img3.png)

## SliceAndDiceVertical

**SliceAndDiceVertical** layout creates rectangles with high aspect ratio and displays them sorted vertical.

{% highlight html %}

<ej-treemap id="treemap"  [dataSource]="population_data" 
       itemsLayoutMode="sliceanddicevertical" weightValuePath= "Population"
                                                  colorValuePath= "Growth">
     <e-levels>
        <e-level groupPath="Continent" [groupGap]=5></e-level>
     </e-levels>
</ej-treemap>

{% endhighlight %}



![](Layout_images/Layout_img4.png)

