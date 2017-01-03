---
layout: post
title: TreeMap-Elements
description: treemap elements
platform: angular2
control: TreeMap
documentation: ug
---

# TreeMap Elements

TreeMap contains various elements such as,

* Legend
* Headers
* Labels

## Legend

You can set the color value of **leaf nodes** using `treeMapLegend`. This legend is appropriate only for the **TreeMap** whose leaf nodes are colored using `rangeColorMapping`.

You can set `showLegend` property value to **“True”** to enable or disable legend visibility.

### TreeMap Legend

You can decide the size of the legend icons by setting `iconWidth` and `iconHeight` properties of the `treeMapLegend` property avail in **TreeMap**.

### Label for Legend

You can customize the labels of the **legend item** using `legendLabel` property of `rangeColorMapping`. 

{% highlight html %}

<ej-treemap id="treemap"  dataSource="population_data" colorValuePath= "Growth"
       weightValuePath= "Population" [showLegend]="true"  itemsLayoutMode="Squarified"
          [legendSettings.height]=40 [legendSettings.width]=700>
    <e-levels>
       <e-level groupPath="Continent" [groupGap]="5"></e-level>
    </e-levels>
    <e-rangecolormapping>
       <e-rangecolor [from]="0" [to]="1" color="#77D8D8"></e-rangecolor>
       <e-rangecolor [from]="1" [to]="1.5" color="#AED960"></e-rangecolor>
       <e-rangecolor [from]="1.5" [to]="2" color="#FFAF51"></e-rangecolor>
       <e-rangecolor [from]="2" [to]="3" color="#F3D240"></e-rangecolor>
	</e-rangecolormapping>
</ej-treemap>

{% endhighlight %}

![](TreeMap-Elements_images/TreeMap-Elements_img1.png)


### Interactive Legend

The legends can be made interactive with an arrow mark indicating the exact range color in the legend when the mouse hovers over the corresponding treemap items. You can enable this option by setting `mode` property in `legendSettings` value as “interactive” and default value of `mode` property is “default” to enable the normal legend.

#### Title for Interactive Legend

You can provide the title for interactive legend by using `title` property in `legendSettings`.

#### Label for Interactive Legend

You can provide the left and right labels to interactive legend by using `leftLabel` and `rightLabel` properties in `legendSettings`. 


{% highlight html %}

<ej-treemap id="treemap" [legendSettings.height]=15 [legendSettings.width]=150
         legendSettings.mode="interactive" legendSettings.title="Population"
           legendSettings.leftLabel="0.5M" legendSettings.rightLabel="40M" 
            legendSettings.dockPosition="top">
   <!-- Add range color mappings here-->
 </ej-treemap>

{% endhighlight %}

![](TreeMap-Elements_images/Interactive_Legend.png)


## Header

You can set headers for each level by setting the `showHeader` property of the each **TreeMap** levels. The `headerHeight` property helps to set the height of the header and Group path value determines the header value. You can customize the default header appearance by setting the `headerTemplate` of the **TreeMap** levels.

{% highlight html %}

<ej-treemap id="treemap" >
    <e-levels>
       <e-level groupPath="Continent" [groupGap]=2 headerTemplate="headertemplate"></e-level>
    </e-levels>                                                     
</ej-treemap> 

 <script  id="headertemplate" type="application/jsrender">
    <div style="background-color: white; margin:5px">
       <label style="color:black;font-size:large;" >{{:header}}</label><br />            
    </div>                        
 </script>                      


{% endhighlight %}



![](TreeMap-Elements_images/TreeMap-Elements_img2.png)

## Label

You can also set labels for the leaf nodes by setting the `showLabels` property as true. Group path value is displayed as a label for leaf nodes. You can customize the default label appearance by setting the `labelTemplate` of the **TreeMap** levels.

{% highlight html %}

<ej-treemap id="treemap" [legendSettings.height]=40 [legendSettings.width]=700 
       leafItemSettings.labelPath="Region" [leafItemSettings.showLabels]="true">
    <e-levels>
       <e-level groupPath="Continent" [showLabels]="true" [groupGap]=2 
             [headerHeight]="20" [groupPadding]="5"  headerTemplate="headertemplate">
       </e-level>
    </e-levels>                                                     
</ej-treemap> 
    
<script  id="headertemplate" type="application/jsrender">
     <div style="background-color: white; margin:5px">
     <label style="color:black;font-size:medium;" >{{:header}}</label><br />            
     </div>                        
</script>             


{% endhighlight %}



![](TreeMap-Elements_images/TreeMap-Elements_img3.png)

