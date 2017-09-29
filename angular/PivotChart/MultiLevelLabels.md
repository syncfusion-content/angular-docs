---
layout: post
title: Multi-level Labels
description: multilevellabels
platform: Angular
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Multi-level Labels

Multi-level labels allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expander present in the OlapChart. You can enable the option by setting the property [`enableMultiLevelLabels`](/api/js/ejchart#members:enableMultiLevelLabels) as **“true”.**

{% highlight javascript %}

    $("#PivotChart1").ejPivotChart(
    {
        //..
        //Enable Multi-level Labels
        enableMultiLevelLabels: true,
        //..
    });
{% endhighlight %}


## Relational

![](MultiLevelLabels_images/relational.png)

## OLAP

![](MultiLevelLabels_images/olap.png)

