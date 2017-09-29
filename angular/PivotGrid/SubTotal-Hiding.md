---
title:  SubTotal Hiding
description: SubTotal Hiding
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Sub Total Hiding

N> This feature is applicable only for Relational data source.

You can hide the **Sub Total** for respective fields in rows and columns by setting the property `showSubTotal` to `false`

{% tabs %}

{% highlight html %}
<ej-pivotgrid [dataSource.rows]="rows">
    </ej-pivotgrid>


{% endhighlight %}

{% highlight ts %}

export class PivotGridComponent {
    
    public  rows;

    constructor()
    {
        this.rows = [{ fieldName: "Country", fieldCaption: "Country", showSubTotal: false },{ fieldName: "State", fieldCaption: "State" }]; 
        //..
    }
 }

{% endhighlight %}

{% endtabs %}

![](SubTotal-Hiding_images/SubTotal.png)
