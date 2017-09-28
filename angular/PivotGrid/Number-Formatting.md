---
title: Number format
description: Number format
platform: Angular
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Number Format 

Allows us to specify the required number format that PivotGrid should use in its values by setting the `format` option. Following number formats that are supported:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction

## RELATIONAL

{% tabs %}

{% highlight html %}

<ej-pivotgrid [dataSource.values]="values">
</ej-pivotgrid>

{% endhighlight %}

{% highlight ts %}
//..
export class PivotGridComponent {
    //..
    constructor() {
        //..
        this.values= [{ fieldName: "Amount", fieldCaption: "Amount", format: "currency" },
                    { fieldName: "Quantity", fieldCaption: "Quantity", format: "decimal" }
        ],
        this.filters= []
    }
}

{% endhighlight %}

{% endtabs %}

![](Number-Format_images/RelationalClient.png)

## OLAP

{% highlight ts %}
//..
export class PivotGridComponent {
    //..
    constructor() {
        //..
        this.values= [{ measures: [{ fieldName: "[Measures].[Internet Sales Amount]",
                                format: "percent" //Specify the format here 
                            }], 
                    axis: "columns" 
                }
        ],
        this.filters= []
    }
}

{% endhighlight %}

![](Number-Format_images/OlapClient.png)