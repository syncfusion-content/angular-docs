---
layout: post
title: Legend
description: legend
platform: Angular
control: PivotTreeMap
documentation: ug
keywords: ejpivottreemap, pivottreemap, js pivottreemap
---

# Legend

## Legend Visibility

The legend shows the value range differences and color occurrence in the respective leaf node while you hover it with the cursor.

N> By default, the legend is visible in PivotTreeMap.

![](Legend_images/Legend_img1.png)

You can disable the legend by setting the property **showLegend** as **false**. The following code example shows how to disable the legend.

{% tabs %}

{% highlight html %}

<ej-pivottreemap (renderSuccess)="showLegend($event)">
</ej-pivottreemap>

{% endhighlight %}

{% highlight ts %}
    //..
export class PivotTreeMapComponent {
    showLegend(args){
        let treemapTarget = $('#PivotTreeMap1TreeMapContainer').data('ejTreeMap');
        pivotTreeMap.model.showLegend = false;
        treemapTarget.refresh();
    }
}

{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img2.png)